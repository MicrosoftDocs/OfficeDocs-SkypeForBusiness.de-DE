---
title: Bereitstellung des Servers für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie den beständigen Chat Server für Skype for Business Server 2015 bereitstellen.'
ms.openlocfilehash: fed07d864bda6fc3e0e93932123b2651c226b4f6
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418115"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>Bereitstellung des Servers für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie den beständigen Chat Server für Skype for Business Server 2015 bereitstellen.
  
So stellen Sie den beständigen Chat Server bereit: 
  
- Verwenden des Topologie-Generators zum Definieren oder importieren und anschließend Veröffentlichen Ihrer Topologie und der Komponenten, die Sie bereitstellen möchten
    
- Vorbereiten Ihrer Umgebung für die Bereitstellung beständiger Chat Server Komponenten
    
- Installieren und Konfigurieren von Komponenten für beständigen Chat Server für Ihre Bereitstellung
    
Bevor Sie den Server für beständigen Chat bereitstellen, sollten Sie [in Skype for Business Server 2015 den Plan für beständigen Chat Server](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)lesen. Die Planungsthemen beschreiben die Hardware- und Softwareanforderungen sowie mögliche Topologien und Verbindungsszenarien. 
  
> [!NOTE] 
> Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. In Teams steht dieselbe Funktionalität zur Verfügung. Weitere Informationen finden Sie unter [Erste Schritte mit dem Upgrade für Microsoft Teams](/microsoftteams/upgrade-start-here). Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen. 

## <a name="deployment-checklist"></a>Bereitstellungscheckliste

Sie können beständigen Chat Server bereitstellen, nachdem Sie Ihre anfängliche Topologie bereitgestellt haben, einschließlich mindestens eines Skype for Business Server-Front-End-Pools oder eines Skype for Business Standard Edition-Servers. Die Checkliste für die Bereitstellung beschreibt die grundlegenden Schritte, die für die Bereitstellung von persistent Chat Server erforderlich sind, und enthält Links für weitere Informationen.
  
**Bereitstellungsprozess für beständigen Chat Server**

|**Aufgabe**|**Schritte**|**Erforderliche Rollen und Gruppenmitgliedschaften**|**Verwandte Themen**|
|:-----|:-----|:-----|:-----|
|**Installieren der erforderlichen Hardware und Software** <br/> | Installieren Sie die folgenden Komponenten auf einem Hardwaresystem, das die Systemanforderungen erfüllt: <br/>  Auf den beständigen Chat Server-Front-End-Servern: <br/>  Ein Betriebssystem, das die Systemanforderungen erfüllt <br/>  Software Voraussetzungen für Computer mit Skype for Business Server <br/>  Auf dem Server, auf dem die persistent Chat Server-Datenbank gehostet wird: <br/>  Eine unterstützte Version von SQL-Server <br/>  Wenn die beständige Chat Server-Kompatibilität erforderlich ist: <br/>  SQL Server auf dem Server, auf dem die Datenbank für beständigen Chat Server gehostet wird <br/> |Jeder Benutzer, der Mitglied der lokalen Gruppe „Administratoren“ ist.  <br/> |[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Hardware- und Softwareanforderungen an den Server für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**Erstellen der geeigneten internen Topologie zur Unterstützung des beständigen Chat Servers (und optional die Compliance für beständigen Chat)** <br/> | Führen Sie den Topologie-Generator aus, um Ihrer Topologie einen beständigen Chat Server Pool hinzuzufügen: <br/>  Hinzufügen von persistenten Chat Server-Komponenten zur Topologie <br/>  Erstellen einer SQL Server-Datenbank für den beständigen Chat Server Speicher (und ein Backup SQL Server für Disaster Recovery) <br/>  Definieren eines neuen Skype for Business-Dateispeichers oder Verwenden eines vorhandenen Skype for Business-Dateispeichers für persistente Chat Server Dateien <br/>  Zuordnen des Skype for Business Server-Pools, der Anfragen an diesen beständigen Chat-Serverpool weiterleiten kann <br/>  Wenn die Kompatibilität für den beständigen Chat erforderlich ist: <br/>  Kompatibilitäts Speicher für beständigen Chat hinzufügen <br/>  Aktivieren Sie das Kontrollkästchen Definition des beständigen Chat Server Pools, um die Kompatibilität zu aktivieren <br/>  Veröffentlichen Sie die Topologie. <br/>  Wenn Sie den Server für beständigen Chat auf Standard Edition installieren, muss der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des beständigen Chat Server Pools mit dem Standard Edition-Server übereinstimmen, und die SQL Server-Datenbanken sind auf der SQL Server Express-Instanz auf dem Standard Edition-Server <br/> |Zum Definieren einer Topologie. Ein Konto, das Mitglieder der lokalen Gruppe „Benutzer“ ist.  <br/> Um die Topologie zu veröffentlichen, muss ein Konto, das ein Mitglied der Gruppe "Domänen-Admins" und der RTCUniversalServerAdmins-Gruppe ist, und der Benutzer auch über die Berechtigung "Vollzugriff" (Lesen/Schreiben/ändern) im Skype for Business-Dateispeicher für persistente Chat Server Dateien verfügen (so dieser Topologie-Generator kann die erforderlichen DACLs konfigurieren.  <br/> |[Erstellen und Veröffentlichen einer neuen Topologie in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md) <br/> [Hinzufügen eines beständigen Chat Servers zu Ihrer Skype for Business Server 2015-Topologie](add-persistent-chat-server.md) <br/> |
|**Bereitstellen des Servers für beständigen Chat** <br/> | Führen Sie das Skype for Business Server-Setup auf allen Computern aus, auf denen der beständige Chat Server ausgeführt wird. Die Einrichtung des beständigen Chat Servers ist in den Skype for Business Server-Bereitstellungs-Assistenten integriert, der die folgenden Anweisungen enthält: <br/>  Den lokalen Verwaltungsspeicher bereitstellen <br/>  Installieren von beständigen Chat Diensten <br/>  Zertifikate anfordern und zuweisen <br/>  Dienste ausführen und starten <br/> |Jeder Benutzer, der Mitglied der lokalen Gruppe „Administratoren“ ist.  <br/> |[Bereitstellung des Servers für beständigen Chat in Skype for Business Server 2015](deploy-persistent-chat-server.md) <br/> |
|**Erstellen eines Administrators für beständigen Chat** <br/> |Fügen Sie der Sicherheitsgruppe „CsPersistentChatAdministrator“ Benutzer hinzu.  <br/> |Jeder Benutzer, der Mitglied der Domänenadministratoren ist.  <br/> |[Erstellen eines Administrators für beständigen Chat in Skype for Business Server 2015](create-a-persistent-chat-administrator.md) <br/> |
|**Konfigurieren des Server für beständigen Chat** <br/> | Konfigurieren von Benutzern: <br/>  Der Benutzer muss durch eine Richtlinie für den Zugriff auf beständigen Chat Server aktiviert sein. Die Richtlinie ist standardmäßig für alle Benutzer deaktiviert und kann auf globaler, Standort-, Pool- und Benutzerebene definiert werden. <br/>  Einstellungen konfigurieren <br/> |Der Benutzer muss Mitglied von „CsPersistentChatAdministrator“ sein. Benutzer müssen sich zum Ändern der Richtlinie mindestens in „CsUserAdministrator“ befinden.  <br/> |[Verwalten des Servers für beständigen Chat in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

