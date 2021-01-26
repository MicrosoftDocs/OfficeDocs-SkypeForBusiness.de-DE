---
title: Bereitstellen der Archivierung für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: 'Zusammenfassung: In diesem Thema erfahren Sie, wie Sie die Archivierung für Skype for Business Server bereitstellen.'
ms.openlocfilehash: 32b25b373bd5399928d5e5eaed063c194942f697
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825215"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>Bereitstellen der Archivierung für Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie die Archivierung für Skype for Business Server bereitstellen.
  
Die Archivierung wird automatisch auf jedem Front-End-Server in Ihrer Skype for Business Server-Bereitstellung installiert, sie müssen jedoch erst die Einrichtungs- und Konfigurationsschritte ausführen, bevor Sie sie verwenden können. Bevor Sie beginnen, sollten Sie mit den Konzepten in [Plan for archiving in Skype for Business Server vertraut sein.](../../plan-your-deployment/archiving/archiving.md)
  
## <a name="deployment-checklist"></a>Prüfliste für die Bereitstellung

Wie Sie die Archivierung einrichten, hängt davon ab, welche Speicheroption Sie auswählen: 
  
- Wenn Sie die Microsoft Exchange-Integration für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie keine Skype for Business Server-Archivierungsrichtlinien für Ihre Benutzer konfigurieren. Stattdessen konfigurieren Sie Exchange In-Place-Archivrichtlinien, um die Archivierung für Benutzer zu unterstützen, die in Exchange gespeichert sind, und deren Postfächer im In-Place sind. Ausführliche Informationen zum Konfigurieren dieser Richtlinien finden Sie in der Exchange-Produktdokumentation.
    
- Wenn Sie die Microsoft Exchange-Integration nicht für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie Ihrer Topologie Skype for Business Server-Archivierungsdatenbanken (SQL Server-Datenbanken) hinzufügen, die aktualisierte Topologie veröffentlichen und dann Archivierungsrichtlinien und -einstellungen für Ihre Benutzer konfigurieren. Sie können Archivierungsdatenbanken gleichzeitig bereitstellen, wenn Sie Ihre anfängliche Topologie bereitstellen oder nachdem Sie mindestens einen Front-End-Pool oder Standard Edition Server bereitgestellt haben. In diesem Dokument wird beschrieben, wie Sie Archivierungsdatenbanken bereitstellen, indem Sie sie einer vorhandenen Bereitstellung hinzufügen.
    
Wenn Sie die Archivierung auf einem Front-End-Pool oder Standard Edition-Server aktivieren, sollten Sie sie für alle anderen Front-End-Pools und Standard Edition-Server in Ihrer Bereitstellung aktivieren. Auf diese Weise können Benutzer, deren Kommunikation archiviert werden muss, zu Sofortnachrichten-Gruppenunterhaltungen oder Besprechungen eingeladen werden, die in einem anderen Pool gehostet werden. Wenn die Archivierung für den Pool, in dem die Unterhaltung oder Besprechung gehostet wird, nicht aktiviert ist, wird die gesamte Sitzung möglicherweise nicht archiviert. In diesen Fällen können IMs mit archivierungsfähigen Benutzern weiterhin archiviert werden, jedoch nicht für Konferenzinhaltsdateien und Konferenzantritts- oder -austrittsereignisse.
  
> [!IMPORTANT]
> Wenn die Archivierung aus Compliancegründen in Ihrer Organisation wichtig ist, stellen Sie sicher, dass Sie die Archivierung bereitstellen, Richtlinien und andere Optionen auf der entsprechenden Ebene konfigurieren und dann die Archivierung für alle entsprechenden Benutzer aktivieren, bevor Sie diese Benutzer für Skype for Business Server aktivieren. 
  
Die folgende Tabelle bietet einen Überblick über die erforderlichen Schritte zur Bereitstellung einer Archivierung in einer vorhandenen Topologie.
  
|**Phase**|**Schritte**|**Rollen und Gruppenmitgliedschaften**|**Dokumentation**|
|:-----|:-----|:-----|:-----|
|**Installieren der erforderlichen Hardware und Software** <br/> |Zum Verwenden der Microsoft Exchange-Integration (mithilfe von Exchange für den Archivierungsspeicher für einige oder alle Benutzer) benötigen Sie eine vorhandene Exchange-Bereitstellung.  <br/> Wenn Sie separate Archivierungsdatenbanken (SQL Server Datenbanken) für den Archivierungsspeicher für einige oder alle Benutzer verwenden möchten, SQL Server auf dem Server, auf dem die Archivierungsdaten gespeichert werden.  <br/> Die Archivierung wird auf Front-End-Servern eines Unternehmenspools und Standard Edition-Servern ausgeführt. Abgesehen von den herkömmlichen Anforderungen zur Installation dieser Server bestehen keine zusätzlichen Hardware- oder Softwareanforderungen.  <br/> |Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.  <br/> |[Serveranforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Umgebungsanforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [Plan zur Integration von Skype for Business mit Exchange Server](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[Systemanforderungen für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) |
|**Erstellen Der entsprechenden internen Topologie zur Unterstützung der Archivierung (nur, wenn die Microsoft Exchange-Integration für alle Benutzer in Ihrer Bereitstellung nicht verwendet wird)** <br/> |Führen Sie den Topologie-Generator aus, um der Topologie Skype for Business SQL Server -Archivierungsdatenbanken (SQL Server) hinzuzufügen, und veröffentlichen Sie dann die Topologie.  <br/> |Zum Definieren einer Topologie zum Einbinden von Archivierungsdatenbanken ein Konto, das Mitglied der lokalen Benutzergruppe ist.  <br/> Zum Veröffentlichen der Topologie ein Konto, das Mitglied der Gruppe "Domänen-Admins" und "RTCUniversalServerAdmins" ist und über Vollzugriffsberechtigungen (Lesen/Schreiben/Ändern) für die Dateifreigabe verfügt, die für den Skype for Business Server-Dateispeicher verwendet werden soll (damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann).  <br/> |[Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen Bereitstellung in Skype for Business Server](add-archiving-databases.md) <br/> |
|**Konfigurieren der Server-zu-Server-Authentifizierung (nur bei Verwendung der Microsoft Exchange-Integration)** <br/> |Konfigurieren Sie Server, um die Authentifizierung zwischen Skype for Business Server und Exchange zu aktivieren. Es wird **empfohlen, "Test-CsExchangeStorageConnectivity" testuser_sipUri -Folder Dumpster** zu verwenden, um die Exchange-Archivierungsspeicherkonnektivität zu überprüfen, bevor Sie die Archivierung aktivieren. <br/> |Ein Konto mit den entsprechenden Berechtigungen zum Verwalten von Zertifikaten auf den Servern.  <br/> |Verwalten der Server-zu-Server-Authentifizierung  <br/> |
|**Konfigurieren von Archivierungsoptionen und -richtlinien** <br/> |Konfigurieren Sie die Archivierung, einschließlich der Verwendung der Microsoft Exchange-Integration, der globalen Richtlinie und aller Standort- und Benutzerrichtlinien (wenn nicht die Microsoft Exchange-Integration für alle Datenspeicher verwendet wird) und spezifische Archivierungsoptionen, z. B. kritischer Modus sowie Datenexport und -löschen.  <br/> Konfigurieren Sie bei Verwendung der Microsoft In-Place Exchange-In-Place A0 entsprechend.  <br/> |Gruppe „RTCUniversalServerAdmins“ (nur Windows PowerShell) oder Zuweisung von Benutzern zur Rolle „CSArchivingAdministrator“ oder „CSAdministrator“  <br/> |[Konfigurieren von Archivierungsoptionen für Skype for Business Server](configure-archiving-options.md) <br/> Exchange-Produktdokumentation (bei Verwendung der Microsoft Exchange-Integration).  <br/> |
   

