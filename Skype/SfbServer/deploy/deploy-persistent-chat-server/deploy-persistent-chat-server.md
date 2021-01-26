---
title: Bereitstellen des Servers für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: 'Zusammenfassung: In diesem Thema erfahren Sie, wie Sie Skype for Business Server 2015 Persistent Chat Server bereitstellen.'
ms.openlocfilehash: 60dbabc84e278f6add3b7de408787f4969a164a7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830475"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>Bereitstellen des Servers für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie Skype for Business Server 2015 Persistent Chat Server bereitstellen.
  
Zum Bereitstellen des Servers für beständigen Chat: 
  
- Verwenden Sie den Topologie-Generator, um die Topologie und die komponenten, die Sie bereitstellen möchten, zu definieren oder zu importieren und anschließend zu veröffentlichen.
    
- Vorbereiten der Umgebung für die Bereitstellung von Komponenten für den Server für beständigen Chat
    
- Installieren und Konfigurieren von Komponenten für den Server für beständigen Chat für Ihre Bereitstellung
    
Bevor Sie den Server für beständigen Chat bereitstellen, sollten Sie ["Plan for Persistent Chat Server" in Skype for Business Server 2015 lesen.](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md) In den Planungsthemen werden Hardware- und Softwareanforderungen, mögliche Topologien und Kollokationsszenarien beschrieben. 
  
> [!NOTE] 
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams-Upgrade".](/microsoftteams/upgrade-start-here) Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Weiterhin Skype for Business Server 2015 verwenden. 

## <a name="deployment-checklist"></a>Prüfliste für die Bereitstellung

Sie können den Server für beständigen Chat nach der Bereitstellung Ihrer anfänglichen Topologie bereitstellen, einschließlich mindestens eines Skype for Business Server-Front-End-Pools oder eines Skype for Business Standard Edition-Servers. In der Prüfliste für die Bereitstellung werden die grundlegenden Schritte beschrieben, die zum Bereitstellen des Servers für beständigen Chat erforderlich sind, und links zu weiteren Details bereitgestellt.
  
**Bereitstellungsprozess für den Server für beständigen Chat**

|**Aufgabe**|**Schritte**|**Erforderliche Rollen und Gruppenmitgliedschaften**|**Verwandte Themen**|
|:-----|:-----|:-----|:-----|
|**Installieren der erforderlichen Hardware und Software** <br/> | Installieren Sie die folgenden Komponenten auf einem Hardwaresystem, das die Systemanforderungen erfüllt: <br/>  Auf den Front-End-Servern des Servers für beständigen Chat: <br/>  Ein Betriebssystem, das die Systemanforderungen erfüllt <br/>  Softwarevoraussetzungen für Computer mit Skype for Business Server <br/>  Auf dem Server, der die Datenbank des Servers für beständigen Chat hosten wird: <br/>  Eine unterstützte Version von SQL Server <br/>  Wenn Kompatibilität des Servers für beständigen Chat erforderlich ist: <br/>  SQL Server auf dem Server, der die Konformitätsdatenbank des Servers für beständigen Chat hosten soll <br/> |Jeder Benutzer, der Mitglied der lokalen Administratorgruppe ist.  <br/> |[Serveranforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Umgebungsanforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Hardware- und Softwareanforderungen für den Server für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**Erstellen der geeigneten internen Topologie zur Unterstützung des Servers für beständigen Chat (und optional kompatibilität für beständigen Chat)** <br/> | Führen Sie den Topologie-Generator aus, um Ihrer Topologie einen Pool für den Server für beständigen Chat hinzuzufügen: <br/>  Hinzufügen von Komponenten für den Server für beständigen Chat zur Topologie <br/>  Erstellen einer SQL Server für den Serverspeicher für beständigen Chat (und einer Sicherungsdatenbank SQL Server Notfallwiederherstellung) <br/>  Definieren eines neuen Skype for Business-Dateispeichers oder Verwenden eines vorhandenen Skype for Business-Dateispeichers für Dateien des Servers für beständigen Chat <br/>  Zuordnen des Skype for Business Server-Pools, der Anforderungen an diesen Serverpool für beständigen Chat routen kann <br/>  Wenn Kompatibilität für beständigen Chat erforderlich ist: <br/>  Hinzufügen des Konformitätsspeichers für beständigen Chat <br/>  Klicken Sie auf das Kontrollkästchen "Pooldefinition für beständigen Chat", um die Kompatibilität zu aktivieren. <br/>  Veröffentlichen Sie die Topologie. <br/>  Wenn Sie den Server für beständigen Chat auf der Standard Edition installieren, muss der vollqualifizierte Domänenname (FQDN) des Pools für den Server für beständigen Chat mit dem Standard Edition-Server übereinstimmen, und die SQL Server-Datenbanken werden auf der SQL Server -Express-Instanz auf dem Standard Edition-Server ausgeführt. <br/> |Zum Definieren einer Topologie. Ein Konto, das Mitglieder der lokalen Gruppe "Benutzer" ist.  <br/> Zum Veröffentlichen der Topologie sollte ein Konto, das Mitglied der Gruppe "Domänen-Admins" und "RTCUniversalServerAdmins" ist, und der Benutzer auch über Vollzugriffsberechtigungen (Lese-/Schreibzugriff/Änderung) für den Skype for Business-Dateispeicher für Dateien des Servers für beständigen Chat verfügen (damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann).  <br/> |[Erstellen und Veröffentlichen einer neuen Topologie in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md) <br/> [Hinzufügen eines Servers für beständigen Chat zu Ihrer Skype for Business Server 2015-Topologie](add-persistent-chat-server.md) <br/> |
|**Bereitstellen des Servers für beständigen Chat** <br/> | Führen Sie das Skype for Business Server-Setup auf allen Computern aus, auf denen der Server für beständigen Chat ausgeführt wird. Das Setup des Servers für beständigen Chat ist in den Skype for Business Server-Bereitstellungs-Assistenten integriert, der die folgenden Anweisungen enthält: <br/>  Den lokalen Verwaltungsspeicher bereitstellen <br/>  Installieren von Diensten für beständigen Chat <br/>  Zertifikate anfordern und zuweisen <br/>  Dienste ausführen und starten <br/> |Jeder Benutzer, der Mitglied der lokalen Administratorgruppe ist.  <br/> |[Bereitstellen des Servers für beständigen Chat in Skype for Business Server 2015](deploy-persistent-chat-server.md) <br/> |
|**Erstellen eines Administrators für beständigen Chat** <br/> |Fügen Sie der Sicherheitsgruppe "CsPersistentChatAdministrator" Benutzer hinzu.  <br/> |Jeder Benutzer, der Mitglied der Domänenadministratoren ist.  <br/> |[Erstellen eines Administrators für beständigen Chat in Skype for Business Server 2015](create-a-persistent-chat-administrator.md) <br/> |
|**Konfigurieren von Persistent Chat Server** <br/> | Konfigurieren von Benutzern: <br/>  Der Benutzer muss durch eine Richtlinie aktiviert werden, um auf den Server für beständigen Chat zugreifen zu können. Die Richtlinie ist standardmäßig für alle Benutzer deaktiviert und kann auf globaler, Standort-, Pool- und Benutzerebene definiert werden. <br/>  Einstellungen konfigurieren <br/> |Der Benutzer muss Mitglied von "CsPersistentChatAdministrator" sein. Benutzer müssen sich zum Ändern der Richtlinie mindestens in "CsUserAdministrator" befinden.  <br/> |[Verwalten des Servers für beständigen Chat in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

