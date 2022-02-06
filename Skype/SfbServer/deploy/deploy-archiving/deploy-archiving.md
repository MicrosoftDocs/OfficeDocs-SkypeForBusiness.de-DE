---
title: Bereitstellen der Archivierung für Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie die Archivierung für Skype for Business Server bereitstellen.'
---

# <a name="deploy-archiving-for-skype-for-business-server"></a>Bereitstellen der Archivierung für Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie die Archivierung für Skype for Business Server bereitstellen.
  
Die Archivierung wird automatisch auf jedem Front-End-Server in Ihrer Skype for Business Server-Bereitstellung installiert, sie müssen jedoch erst setup- und konfigurationsschritte ausführen, bevor Sie sie verwenden können. Bevor Sie beginnen, sollten Sie mit den Konzepten in [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) vertraut sein.
  
## <a name="deployment-checklist"></a>Prüfliste für die Bereitstellung

Wie Sie die Archivierung einrichten, hängt davon ab, welche Speicheroption Sie auswählen: 
  
- Wenn Sie Microsoft Exchange Integration für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie Skype for Business Server Archivierungsrichtlinien für Ihre Benutzer nicht konfigurieren. Stattdessen konfigurieren Sie Exchange In-Place Aufbewahrungsrichtlinien, um die Archivierung für Benutzer zu unterstützen, die auf Exchange verwaltet werden, wobei ihre Postfächer In-Place Haltebereich gesetzt werden. Ausführliche Informationen zum Konfigurieren dieser Richtlinien finden Sie in der Exchange Produktdokumentation.
    
- Wenn Sie microsoft Exchange Integration nicht für alle Benutzer in Ihrer Bereitstellung verwenden, müssen Sie ihrer Topologie Skype for Business Server Archivierungsdatenbanken (SQL Server Datenbanken) hinzufügen, die aktualisierte Topologie veröffentlichen und anschließend Archivierungsrichtlinien und -einstellungen für Ihre Benutzer konfigurieren. Sie können Archivierungsdatenbanken gleichzeitig mit der Bereitstellung Ihrer anfänglichen Topologie oder nach der Bereitstellung mindestens eines Front-End-Pools oder Standard Edition Servers bereitstellen. In diesem Dokument wird beschrieben, wie Archivierungsdatenbanken bereitgestellt werden, indem sie einer vorhandenen Bereitstellung hinzugefügt werden.
    
Wenn Sie die Archivierung in einem Front-End-Pool oder Standard Edition-Server aktivieren, sollten Sie sie für alle anderen Front-End-Pools und Standard Edition Server in Ihrer Bereitstellung aktivieren. Auf diese Weise können Benutzer, deren Kommunikation archiviert werden muss, zu Sofortnachrichten-Gruppenunterhaltungen oder Besprechungen eingeladen werden, die in einem anderen Pool gehostet werden. Wenn die Archivierung in dem Pool, in dem die Unterhaltung oder Besprechung gehostet wird, nicht aktiviert ist, wird die vollständige Sitzung möglicherweise nicht archiviert. In diesen Fällen können IMs mit archivierungsfähigen Benutzern weiterhin archiviert werden, jedoch nicht für Konferenzinhaltsdateien und Konferenzteilnahme- oder -leave-Ereignisse.
  
> [!IMPORTANT]
> Wenn die Archivierung in Ihrer Organisation aus Compliancegründen wichtig ist, stellen Sie sicher, dass Sie die Archivierung bereitstellen, Richtlinien und andere Optionen auf der entsprechenden Ebene konfigurieren und dann die Archivierung für alle geeigneten Benutzer aktivieren, bevor Sie diese Benutzer für Skype for Business Server aktivieren. 
  
Die folgende Tabelle bietet einen Überblick über die erforderlichen Schritte zur Bereitstellung einer Archivierung in einer vorhandenen Topologie.
  
|**Phase**|**Schritte**|**Rollen und Gruppenmitgliedschaften**|**Dokumentation**|
|:-----|:-----|:-----|:-----|
|**Installieren der erforderlichen Hardware und Software** <br/> |Um die Integration von Microsoft Exchange (mit Exchange für archivierungsspeicher für einige oder alle Benutzer) zu verwenden, benötigen Sie eine vorhandene Exchange Bereitstellung.  <br/> Um separate Archivierungsdatenbanken (mit SQL Server Datenbanken) für den Archivierungsspeicher für einige oder alle Benutzer zu verwenden, SQL Server auf dem Server, der Archivierungsdaten speichert.  <br/> Die Archivierung wird auf Front-End-Servern eines Enterprise-Pools und Standard Edition Servern ausgeführt. Abgesehen von den herkömmlichen Anforderungen zur Installation dieser Server bestehen keine zusätzlichen Hardware- oder Softwareanforderungen.  <br/> |Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.  <br/> |[Serveranforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Umweltanforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [Plan zur Integration von Skype for Business mit Exchange Server](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[Systemanforderungen für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) |
|**Erstellen Sie die entsprechende interne Topologie zur Unterstützung der Archivierung (nur, wenn Sie microsoft Exchange Integration für alle Benutzer in Ihrer Bereitstellung nicht verwenden)** <br/> |Führen Sie den Topologie-Generator aus, um der Topologie Skype for Business Server Archivierungsdatenbanken (SQL Server-Datenbanken) hinzuzufügen und dann die Topologie zu veröffentlichen.  <br/> |Um eine Topologie zum Integrieren von Archivierungsdatenbanken zu definieren, ein Konto, das Mitglied der lokalen Benutzergruppe ist.  <br/> Zum Veröffentlichen der Topologie ein Konto, das Mitglied der Gruppe "Domänenadministratoren" und "RTCUniversalServerAdmins" ist und über Vollzugriffsberechtigungen (Lese-/Schreibzugriff/Ändern) für die Dateifreigabe verfügt, die für den Skype for Business Server Dateispeicher verwendet werden soll (damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann).  <br/> |[Hinzufügen von Archivierungsdatenbanken zu einer vorhandenen Bereitstellung in Skype for Business Server](add-archiving-databases.md) <br/> |
|**Konfigurieren der Server-zu-Server-Authentifizierung (nur bei Verwendung von Microsoft Exchange Integration)** <br/> |Konfigurieren Sie Server, um die Authentifizierung zwischen Skype for Business Server und Exchange zu aktivieren. Es wird empfohlen, **Test-CsExchangeStorageConnectivity testuser_sipUri -Folder Dumpster** auszuführen, um Exchange Archivierungsspeicherkonnektivität zu überprüfen, bevor die Archivierung aktiviert wird. <br/> |Ein Konto mit den entsprechenden Berechtigungen zum Verwalten von Zertifikaten auf den Servern.  <br/> |Verwalten der Server-zu-Server-Authentifizierung  <br/> |
|**Konfigurieren von Archivierungsoptionen und -richtlinien** <br/> |Konfigurieren Sie die Archivierung, einschließlich der Verwendung von Microsoft Exchange Integration, der globalen Richtlinie sowie aller Standort- und Benutzerrichtlinien (wenn Microsoft Exchange-Integration nicht für alle Datenspeicherung verwendet wird) und bestimmter Archivierungsoptionen, z. B. kritischer Modus sowie Datenexport und -bereinigung.  <br/> Wenn Sie Microsoft Exchange Integration verwenden, konfigurieren Sie Exchange In-Place Aufbewahrungsrichtlinien entsprechend.  <br/> |Gruppe „RTCUniversalServerAdmins“ (nur Windows PowerShell) oder Zuweisung von Benutzern zur Rolle „CSArchivingAdministrator“ oder „CSAdministrator“  <br/> |[Konfigurieren von Archivierungsoptionen für Skype for Business Server](configure-archiving-options.md) <br/> Exchange Produktdokumentation (bei Verwendung von Microsoft Exchange Integration).  <br/> |
   

