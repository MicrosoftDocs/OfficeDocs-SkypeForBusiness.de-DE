---
title: Bereitstellen des Servers für beständigen Chat in Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie Skype for Business Server Server für beständigen Chat 2015 bereitstellen.'
---

# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>Bereitstellen des Servers für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie Skype for Business Server Server für beständigen Chat 2015 bereitstellen.
  
So stellen Sie den Server für beständigen Chat bereit: 
  
- Verwenden des Topologie-Generators zum Definieren oder Importieren und anschließenden Veröffentlichen der Topologie und der Komponenten, die Sie bereitstellen möchten
    
- Vorbereiten der Umgebung für die Bereitstellung von Komponenten des Servers für beständigen Chat
    
- Installieren und Konfigurieren von Komponenten des Servers für beständigen Chat für Ihre Bereitstellung
    
Bevor Sie den Server für beständigen Chat bereitstellen, sollten Sie ["Plan for Persistent Chat Server" in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md) lesen. In den Planungsthemen werden Hardware- und Softwareanforderungen, mögliche Topologien und Kollokationsszenarien beschrieben. 
  
> [!NOTE] 
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams-Upgrade](/microsoftteams/upgrade-start-here). Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität zum Teams benötigen, oder Skype for Business Server 2015 weiterhin verwenden. 

## <a name="deployment-checklist"></a>Prüfliste für die Bereitstellung

Sie können den Server für beständigen Chat nach der Bereitstellung Ihrer anfänglichen Topologie bereitstellen, einschließlich mindestens eines Skype for Business Server Front-End-Pools oder eines Skype for Business Standard Edition Servers. Die Prüfliste für die Bereitstellung beschreibt die grundlegenden Schritte, die zum Bereitstellen des Servers für beständigen Chat erforderlich sind, und enthält Links für weitere Details.
  
**Bereitstellungsprozess des Servers für beständigen Chat**

|**Aufgabe**|**Schritte**|**Erforderliche Rollen und Gruppenmitgliedschaften**|**Verwandte Themen**|
|:-----|:-----|:-----|:-----|
|**Installieren der erforderlichen Hardware und Software** <br/> | Installieren Sie die folgenden Komponenten auf einem Hardwaresystem, das die Systemanforderungen erfüllt: <br/>  Auf den Front-End-Servern des Servers für beständigen Chat: <br/>  Ein Betriebssystem, das die Systemanforderungen erfüllt <br/>  Softwarevoraussetzungen für Computer mit Skype for Business Server <br/>  Auf dem Server, auf dem die Datenbank des Servers für beständigen Chat gehostet wird: <br/>  Eine unterstützte Version von SQL Server <br/>  Wenn die Kompatibilität des Servers für beständigen Chat erforderlich ist: <br/>  SQL Server auf dem Server, auf dem die Kompatibilitätsdatenbank für den Server für beständigen Chat gehostet wird <br/> |Jeder Benutzer, der Mitglied der lokalen Administratorgruppe ist.  <br/> |[Serveranforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Umweltanforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Hardware- und Softwareanforderungen für den Server für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**Erstellen der geeigneten internen Topologie zur Unterstützung des Servers für beständigen Chat (und optional Kompatibilität des beständigen Chats)** <br/> | Führen Sie den Topologie-Generator aus, um Ihrer Topologie einen Serverpool für beständigen Chat hinzuzufügen: <br/>  Hinzufügen von Komponenten für den Server für beständigen Chat zur Topologie <br/>  Erstellen einer SQL Server Datenbank für den Serverspeicher für beständigen Chat (und einer Sicherungs-SQL Server für die Notfallwiederherstellung) <br/>  Definieren einer neuen Skype for Business datei Store oder Verwenden eines vorhandenen Skype for Business-Datei-Store für Dateien des Servers für beständigen Chat <br/>  Zuordnen des Skype for Business Server Pools, der Anforderungen an diesen Serverpool für beständigen Chat weiterleiten kann <br/>  Wenn Kompatibilität für beständigen Chat erforderlich ist: <br/>  Hinzufügen der Kompatibilität für beständigen Chat Store <br/>  Klicken Sie auf das Kontrollkästchen für die Pooldefinition für den Server für beständigen Chat, um die Kompatibilität zu aktivieren. <br/>  Veröffentlichen Sie die Topologie. <br/>  Wenn Sie den Server für beständigen Chat auf Standard Edition installieren, muss der vollqualifizierte Domänenname (FQDN) des Servers für beständigen Chat mit dem Standard Edition Server übereinstimmen, und die SQL Server Datenbanken sind mit der SQL Server Express Instanz auf der Standard Edition-Server <br/> |Zum Definieren einer Topologie. Ein Konto, das Mitglieder der lokalen Gruppe "Benutzer" ist.  <br/> Um die Topologie zu veröffentlichen, ein Konto, das Mitglied der Gruppe "Domänenadministratoren" und der Gruppe "RTCUniversalServerAdmins" ist, und der Benutzer sollte auch über Vollzugriffsberechtigungen (Lese-/Schreibzugriff/Änderung) für die Skype for Business Datei Store für Serverdateien für beständigen Chat verfügen (damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann).  <br/> |[Erstellen und Veröffentlichen einer neuen Topologie in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md) <br/> [Hinzufügen des Servers für beständigen Chat zu Ihrer Skype for Business Server 2015-Topologie](add-persistent-chat-server.md) <br/> |
|**Bereitstellen des Servers für beständigen Chat** <br/> | Führen Sie das Skype for Business Server Setup auf allen Computern aus, auf denen der Server für beständigen Chat ausgeführt wird. Das Setup des Servers für beständigen Chat ist in den Assistenten für Skype for Business Server Bereitstellung integriert, der die folgenden Anweisungen enthält: <br/>  Den lokalen Verwaltungsspeicher bereitstellen <br/>  Installieren von Diensten für beständigen Chat <br/>  Zertifikate anfordern und zuweisen <br/>  Dienste ausführen und starten <br/> |Jeder Benutzer, der Mitglied der lokalen Administratorgruppe ist.  <br/> |[Bereitstellen des Servers für beständigen Chat in Skype for Business Server 2015](deploy-persistent-chat-server.md) <br/> |
|**Erstellen eines Administrators für beständigen Chat** <br/> |Fügen Sie der Sicherheitsgruppe "CsPersistentChatAdministrator" Benutzer hinzu.  <br/> |Jeder Benutzer, der Mitglied der Domänenadministratoren ist.  <br/> |[Erstellen eines Administrators für beständigen Chat in Skype for Business Server 2015](create-a-persistent-chat-administrator.md) <br/> |
|**Konfigurieren von Persistent Chat Server** <br/> | Konfigurieren von Benutzern: <br/>  Der Benutzer muss über die Richtlinie für den Zugriff auf den Server für beständigen Chat aktiviert werden. Die Richtlinie ist standardmäßig für alle Benutzer deaktiviert und kann auf globaler, Standort-, Pool- und Benutzerebene definiert werden. <br/>  Einstellungen konfigurieren <br/> |Der Benutzer muss Mitglied von "CsPersistentChatAdministrator" sein. Benutzer müssen sich zum Ändern der Richtlinie mindestens in "CsUserAdministrator" befinden.  <br/> |[Verwalten des Servers für beständigen Chat in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

