---
title: Bereitstellen der Archivierung für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie die Archivierung für Skype for Business Server bereitgestellt wird.'
ms.openlocfilehash: 8611f83b6e3504d860cf37a7ad2c24c20b446671
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234515"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>Bereitstellen der Archivierung für Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie die Archivierung für Skype for Business Server bereitstellen.
  
Die Archivierung wird automatisch auf jedem Front-End-Server in Ihrer Skype for Business Server-Bereitstellung installiert, doch müssen Sie zunächst Setup-und Konfigurationsschritte ausführen, bevor Sie Sie verwenden können. Bevor Sie beginnen, stellen Sie sicher, dass Sie mit den Konzepten in [Plan für die Archivierung in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md)vertraut sind.
  
## <a name="deployment-checklist"></a>Checkliste für die Bereitstellung

Die Einrichtung der Archivierung ist abhängig von der jeweiligen Speicheroption: 
  
- Wenn Sie die Microsoft Exchange-Integration für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie die Skype for Business Server-Archivierungsrichtlinien für Ihre Benutzer nicht konfigurieren. Stattdessen konfigurieren Sie Exchange-in-situ-Speicherrichtlinien, um die Archivierung für Benutzer zu unterstützen, die sich in Exchange befinden, wobei ihre Postfächer in-situ gespeichert werden. Details zum Konfigurieren dieser Richtlinien finden Sie in der Exchange-Produktdokumentation.
    
- Wenn Sie die Microsoft Exchange-Integration nicht für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie Ihrer Topologie Skype for Business Server-Archivierungsdatenbanken (SQL Server-Datenbanken) hinzufügen, die aktualisierte Topologie veröffentlichen und dann Archivierungsrichtlinien konfigurieren und Einstellungen für Ihre Benutzer. Sie können Archivierungsdatenbanken zur gleichen Zeit bereitstellen, in der Sie Ihre anfängliche Topologie bereitstellen, oder nachdem Sie mindestens einen Front-End-Pool oder Standard Edition-Server bereitgestellt haben. In diesem Dokument wird beschrieben, wie Archivierungsdatenbanken bereitgestellt werden, indem Sie einer vorhandenen Bereitstellung hinzugefügt werden.
    
Wenn Sie die Archivierung in einem Front-End-Pool oder auf einem Standard Edition-Server aktivieren, sollten Sie sie für alle weiteren Front-End-Pools und Standard Edition-Server in Ihrer Bereitstellung ebenfalls aktivieren. Auf diese Weise können Benutzer, deren Kommunikation archiviert werden muss, zu Sofortnachrichten-Gruppenunterhaltungen oder Besprechungen eingeladen werden, die in einem anderen Pool gehostet werden. Wenn im Pool, der die Unterhaltung oder Besprechung hostet, die Archivierung nicht aktiviert wurde, kann möglicherweise die gesamte Sitzung nicht archiviert werden. In diesen Fällen können Sofortnachrichten mit archivierungsfähigen Benutzern trotzdem archiviert werden. Für Konferenzinhaltsdateien sowie für die Teilnahme an bzw. das Verlassen einer Konferenz ist dies aber nicht möglich.
  
> [!IMPORTANT]
> Wenn die Archivierung aus Kompatibilitätsgründen für Ihre Organisation von entscheidender Bedeutung ist, stellen Sie sicher, dass Sie die Archivierung durchführen, Richtlinien und andere Optionen auf der entsprechenden Ebene konfigurieren und dann die Archivierung für alle entsprechenden Benutzer aktivieren, bevor Sie diese Benutzer für Skype aktivieren. Business Server. 
  
Die folgende Tabelle bietet einen Überblick über die erforderlichen Schritte zur Bereitstellung einer Archivierung in einer vorhandenen Topologie.
  
|**Phase**|**Schritte**|**Rollen und Gruppenmitgliedschaften**|**Dokumentation**|
|:-----|:-----|:-----|:-----|
|**Installieren der erforderlichen Hardware und Software** <br/> |Wenn Sie die Microsoft Exchange-Integration verwenden möchten (mithilfe von Exchange für das Archivieren von Speicher für einige oder alle Benutzer), benötigen Sie eine vorhandene Exchange-Bereitstellung.  <br/> Wenn Sie separate Archivierungsdatenbanken (Verwendung von SQL Server-Datenbanken) als Archivierungsspeicher für einige oder alle Benutzer verwenden möchten, muss SQL Server auf dem Server ausgeführt werden, auf dem die Archivierungsdaten gespeichert werden.  <br/> Die Archivierung wird auf Front-End-Servern in einem Enterprise-Pool und Standard Edition-Servern ausgeführt. Abgesehen von den herkömmlichen Anforderungen zur Installation dieser Server bestehen keine zusätzlichen Hardware- oder Softwareanforderungen.  <br/> |Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.  <br/> |[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [Plan zur Integration von Skype for Business mit Exchange Server](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[System Anforderungen für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) |
|**Erstellen der geeigneten internen Topologie zur Unterstützung der Archivierung (nur, wenn Sie nicht die Microsoft Exchange-Integration für alle Benutzer in Ihrer Bereitstellung verwenden)** <br/> |Führen Sie den Topologie-Generator aus, um der Topologie Skype for Business Server-Archivierungsdatenbanken (SQL Server-Datenbanken) hinzuzufügen, und veröffentlichen Sie dann die Topologie.  <br/> |Zum Definieren einer Topologie für die Einbindung von Archivierungsdatenbanken; ein Konto, das Mitglied der Gruppe der lokalen Benutzer ist.  <br/> So veröffentlichen Sie die Topologie: ein Konto, das ein Mitglied der Gruppe "Domänen-Admins" und der RTCUniversalServerAdmins-Gruppe ist und das Vollzugriffsberechtigungen (Lesen/Schreiben/ändern) für die Dateifreigabe hat, die für den Dateispeicher von Skype for Business Server verwendet werden soll (damit die Topologie Builder kann die erforderlichen DACLs konfigurieren.  <br/> |[Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen Bereitstellung in Skype for Business Server](add-archiving-databases.md) <br/> |
|**Konfigurieren der Server-zu-Server-Authentifizierung (nur bei Verwendung der Microsoft Exchange-Integration)** <br/> |Konfigurieren Sie Server, um die Authentifizierung zwischen Skype for Business Server und Exchange zu ermöglichen. Es wird empfohlen, **Test-CsExchangeStorageConnectivity-testuser_sipUri** , um die Exchange-Archivierungsspeicher Konnektivität zu überprüfen, bevor die Archivierung aktiviert wird. <br/> |Ein Konto mit den entsprechenden Berechtigungen zum Verwalten von Zertifikaten auf den Servern.  <br/> |Verwalten der Server-zu-Server-Authentifizierung  <br/> |
|**Konfigurieren von Archivierungsoptionen und -richtlinien** <br/> |Konfigurieren Sie die Archivierung, einschließlich der Frage, ob Sie die Microsoft Exchange-Integration, die globale Richtlinie und alle Website-und Benutzerrichtlinien verwenden möchten (wenn Sie die Microsoft Exchange-Integration nicht für alle Datenspeicher verwenden), und bestimmte Archivierungsoptionen wie kritischer Modus und Daten Exportieren und bereinigen.  <br/> Wenn Sie die Microsoft Exchange-Integration verwenden, konfigurieren Sie Exchange-in-situ-Speicherrichtlinien nach Bedarf.  <br/> |Gruppe „RTCUniversalServerAdmins“ (nur Windows PowerShell) oder Zuweisung von Benutzern zur Rolle „CSArchivingAdministrator“ oder „CSAdministrator“  <br/> |[Konfigurieren von Archivierungsoptionen für Skype for Business Server](configure-archiving-options.md) <br/> Exchange-Produktdokumentation (bei Verwendung der Microsoft Exchange-Integration).  <br/> |
   

