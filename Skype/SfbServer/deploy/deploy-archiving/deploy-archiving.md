---
title: Bereitstellung einer Archivierung für Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: 'Zusammenfassung: Lesen Sie in diesem Thema erfahren, wie die Archivierung für Skype für Business Server bereitstellen.'
ms.openlocfilehash: 0598d1a35523cc38d85320206b065b85e025687e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895069"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>Bereitstellung einer Archivierung für Skype für Business Server
 
**Zusammenfassung:** Lesen Sie in diesem Thema erfahren, wie die Archivierung für Skype für Business Server bereitstellen.
  
Archivierung wird automatisch auf jedem Front-End-Server in Ihrer Skype für Business Server-Bereitstellung installiert, jedoch müssen Sie dennoch anfängliche Installations- und Konfigurationsschritte ausführen, bevor Sie es verwenden können. Bevor Sie beginnen, sollten Sie darauf achten Sie, dass Sie mit den Konzepten in [Planen der Archivierung in Skype für Business Server](../../plan-your-deployment/archiving/archiving.md)vertraut sind.
  
## <a name="deployment-checklist"></a>Checkliste für die Bereitstellung

Die Einrichtung der Archivierung ist abhängig von der jeweiligen Speicheroption: 
  
- Wenn Sie Microsoft Exchange-Integration für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie keine Skype für Business Server Archivierungsrichtlinien für Ihre Benutzer konfigurieren. Stattdessen konfigurieren Sie Exchange In-Place Hold Richtlinien zur Unterstützung der Archivierung für Benutzer in Exchange, mit ihren Postfächern Compliance-Archiv platzieren verwaltet. Ausführliche Informationen zur Konfiguration dieser Richtlinien finden Sie in der Exchange-Produktdokumentation.
    
- Wenn Sie nicht Microsoft Exchange-Integration für alle Benutzer in Ihrer Bereitstellung verwenden, Sie müssen Skype für Business Server Archivierungsdatenbanken (SQL Server-Datenbanken) zu Ihrer Topologie hinzufügen die aktualisierte Topologie veröffentlichen, und klicken Sie dann konfigurieren Archivierungsrichtlinien und Einstellungen für die Benutzer. Sie können die Archivierung bereitstellen Datenbanken gleichzeitig mit Ihrer anfängliche Topologie bereitstellen oder nachdem Sie mindestens einen Front-End-Pool oder Standard Edition-Server bereitgestellt haben. In diesem Dokument wird beschrieben, wie Archivierungsdatenbanken bereitstellen, indem sie zu einer vorhandenen Bereitstellung hinzufügen.
    
Wenn Sie die Archivierung in einem Front-End-Pool oder auf einem Standard Edition-Server aktivieren, sollten Sie sie für alle weiteren Front-End-Pools und Standard Edition-Server in Ihrer Bereitstellung ebenfalls aktivieren. Auf diese Weise können Benutzer, deren Kommunikation archiviert werden muss, zu Sofortnachrichten-Gruppenunterhaltungen oder Besprechungen eingeladen werden, die in einem anderen Pool gehostet werden. Wenn im Pool, der die Unterhaltung oder Besprechung hostet, die Archivierung nicht aktiviert wurde, kann möglicherweise die gesamte Sitzung nicht archiviert werden. In diesen Fällen können Sofortnachrichten mit archivierungsfähigen Benutzern trotzdem archiviert werden. Für Konferenzinhaltsdateien sowie für die Teilnahme an bzw. das Verlassen einer Konferenz ist dies aber nicht möglich.
  
> [!IMPORTANT]
> Wenn die Archivierung in Ihrer Organisation aus Gründen der Einhaltung von Bestimmungen wichtig ist, müssen Sie unbedingt Archivierung bereitstellen, konfigurieren Sie Richtlinien und andere Optionen auf der entsprechenden Ebene und klicken Sie dann auf die Archivierung für alle entsprechenden Benutzer, bevor Sie diese Benutzer für Skype für aktivieren aktivieren Business-Server. 
  
Die folgende Tabelle bietet einen Überblick über die erforderlichen Schritte zur Bereitstellung einer Archivierung in einer vorhandenen Topologie.
  
|**Phase**|**Schritte**|**Rollen und Gruppenmitgliedschaften**|**Dokumentation**|
|:-----|:-----|:-----|:-----|
|**Installieren der erforderlichen Hardware und Software** <br/> |Um Microsoft Exchange-Integration (Exchange als Archivierungsspeicher für einige oder alle Benutzer mit) zu verwenden, benötigen Sie eine vorhandene Exchange-Bereitstellung.  <br/> Wenn Sie separate Archivierungsdatenbanken (Verwendung von SQL Server-Datenbanken) als Archivierungsspeicher für einige oder alle Benutzer verwenden möchten, muss SQL Server auf dem Server ausgeführt werden, auf dem die Archivierungsdaten gespeichert werden.  <br/> Die Archivierung wird auf Front-End-Servern in einem Enterprise-Pool und Standard Edition-Servern ausgeführt. Abgesehen von den herkömmlichen Anforderungen zur Installation dieser Server bestehen keine zusätzlichen Hardware- oder Softwareanforderungen.  <br/> |Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.  <br/> |[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [Plan zur Integration von Skype for Business mit Exchange Server](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[Systemanforderungen für Skype für Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) |
|**Erstellen der geeigneten internen Topologie zur Unterstützung der Archivierung (nur bei Verwendung von Microsoft Exchange-Integration nicht für alle Benutzer in Ihrer Bereitstellung)** <br/> |Führen Sie Topologie-Generator zum Hinzufügen von Skype für Business Server Archivierungsdatenbanken (SQL Server-Datenbanken aus), um die Topologie, und klicken Sie dann veröffentlichen Sie die Topologie.  <br/> |Zum Definieren einer Topologie für die Einbindung von Archivierungsdatenbanken; ein Konto, das Mitglied der Gruppe der lokalen Benutzer ist.  <br/> So veröffentlichen die Topologie, ein Konto, das Mitglied der Domänengruppe-Admins und Gruppe RTCUniversalServerAdmins ist und dessen Vollzugriff-Berechtigungen (Lese-/Schreibzugriff/ändern) für die Dateifreigabe für den Skype für Dateispeicher Business Server verwendet werden soll (sodass Topologie Generator kann die erforderlichen freigegebenen Zugriffssteuerungslisten konfigurieren).  <br/> |[Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen Bereitstellung in Skype für Business Server](add-archiving-databases.md) <br/> |
|**Konfigurieren der Server-zu-Server-Authentifizierung (nur bei Verwendung von Microsoft Exchange-Integration)** <br/> |Konfigurieren Sie zum Aktivieren der Authentifizierung zwischen Skype für Business Server und Exchange Server. Wir empfehlen die Ausführung **Test-CsExchangeStorageConnectivity Testuser_sipUri-Ordner Dumpster** zum Überprüfen der Exchange-Speicher-Konnektivität vor dem Aktivieren der Archivierung archivieren. <br/> |Ein Konto mit den entsprechenden Berechtigungen zum Verwalten von Zertifikaten auf den Servern.  <br/> |Verwalten der Server-zu-Server-Authentifizierung  <br/> |
|**Konfigurieren von Archivierungsoptionen und -richtlinien** <br/> |Konfigurieren der Archivierung, einschließlich Microsoft Exchange-Integration, die globale Richtlinie und alle Standort- und Benutzerrichtlinien (bei Verwendung von Microsoft Exchange-Integration nicht für alle Datenspeicher) verwenden sollen, und bestimmte Archivierung Optionen wie kritischen Modus und Daten Exportieren und löschen.  <br/> Wenn Sie Microsoft Exchange-Integration verwenden, konfigurieren Sie Exchange In-Place Hold Policies entsprechend.  <br/> |Gruppe „RTCUniversalServerAdmins“ (nur Windows PowerShell) oder Zuweisung von Benutzern zur Rolle „CSArchivingAdministrator“ oder „CSAdministrator“  <br/> |[Konfigurieren von Archivierungsoptionen für Skype für Business Server](configure-archiving-options.md) <br/> Exchange-Produktdokumentation (bei Verwendung von Microsoft Exchange-Integration).  <br/> |
   

