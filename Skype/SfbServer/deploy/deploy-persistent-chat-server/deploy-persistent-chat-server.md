---
title: Bereitstellung des Servers für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: 'Zusammenfassung: Lesen Sie in diesem Thema erfahren, wie Skype für Business Server 2015 Persistent Chat Server bereitstellen.'
ms.openlocfilehash: 2b88d20437a85c9a634bf8a156a3dcec214c60fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894465"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>Bereitstellung des Servers für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Lesen Sie in diesem Thema erfahren, wie Skype für Business Server 2015 Persistent Chat Server bereitstellen.
  
Zum Bereitstellen von Persistent Chat Server Sie: 
  
- Verwenden Sie die Topologie-Generator zu definieren, und importieren anschließend Veröffentlichen Ihrer Topologie und Komponenten, die Sie bereitstellen möchten
    
- Vorbereiten der Umgebung für die Bereitstellung von Persistent Chat-Server-Komponenten
    
- Installieren und Konfigurieren von Persistent Chat Server-Komponenten für die Bereitstellung
    
Bevor Sie Persistent Chat Server bereitstellen, sollten Sie [Planen für Persistent Chat Server in Skype für Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)lesen. Die Planungsthemen beschreiben die Hardware- und Softwareanforderungen sowie mögliche Topologien und Verbindungsszenarien. 
  
> [!NOTE] 
> Beständiger Chat wird steht in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype Business Server 2019. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Weg von Skype für Unternehmen, die Microsoft-Teams](/microsoftteams/journey-skypeforbusiness-teams). Wenn Sie Persistent Chat verwenden müssen, sind Ihrer Auswahl an Benutzer, die diese Funktionalität Teams migrieren oder weiterhin Skype für Business Server 2015 verwenden. 

## <a name="deployment-checklist"></a>Bereitstellungscheckliste

Sie können Persistent Chat Server bereitstellen, nachdem Sie die anfängliche Topologie einschließlich mindestens einen Skype für Business Server-Front-End-Pool oder einen Skype für Business Standard Edition-Server bereitstellen. Die Prüfliste zur Bereitstellung beschreibt die grundlegenden Schritte zum Bereitstellen von Persistent Chat Server und enthält Links für weitere Details.
  
**Bereitstellungsprozess für persistent Chat Server**

|**Aufgabe**|**Schritte**|**Erforderliche Rollen und Gruppenmitgliedschaften**|**Verwandte Themen**|
|:-----|:-----|:-----|:-----|
|**Installieren der erforderlichen Hardware und Software** <br/> | Installieren Sie die folgenden Komponenten auf einem Hardwaresystem, das die Systemanforderungen erfüllt: <br/>  Klicken Sie auf der Persistent Chat Server-Front-End-Server: <br/>  Ein Betriebssystem, das die Systemanforderungen erfüllt <br/>  Erforderliche Software für Computer mit Skype für Business Server <br/>  Auf dem Server, auf der die Persistent Chat-Server-Datenbank gehostet wird: <br/>  Eine unterstützte Version von SQL-Server <br/>  Wenn Kompatibilität für Persistent Chat Server erforderlich ist: <br/>  SQL Server auf dem Server, auf der die Kompatibilitätsdatenbank Persistent Chat Server gehostet wird <br/> |Jeder Benutzer, der Mitglied der lokalen Gruppe „Administratoren“ ist.  <br/> |[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Hardware- und Softwareanforderungen an den Server für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**Erstellen der geeigneten internen Topologie zur Unterstützung der Persistent Chat Server (und optional Compliance beständigen Chat)** <br/> | Führen Sie die Topologie-Generator, um Ihrer Topologie einen Persistent Chat Server Pool hinzuzufügen: <br/>  Hinzufügen von Persistent Chat-Server-Komponenten zur Topologie <br/>  Erstellen Sie eine SQL Server-Datenbank für den Persistent Chat Server-Speicher (und eine Sicherung SQL Server für die Wiederherstellung) <br/>  Definieren Sie einer neuen Skype für Business-Dateispeicher, oder verwenden Sie eine vorhandene Skype für Business-Dateispeicher für Persistent Chat Server-Dateien <br/>  Ordnen Sie die Skype für Business Server-Pool, die Anfragen an diesem Persistent Chat Server Pool weiterleiten kann <br/>  Wenn die Kompatibilität für den beständigen Chat erforderlich ist: <br/>  Hinzufügen von Kompatibilitätsspeicher für beständigen Chat <br/>  Klicken Sie auf das Kontrollkästchen Persistent Chat Server Pool Definition zum ermöglichen der Kompatibilität <br/>  Veröffentlichen Sie die Topologie. <br/>  Wenn Sie Persistent Chat Server auf Standard Edition installieren, muss der vollqualifizierten Domänennamen (FQDN) des Pools Persistent Chat Server Standard Edition-Servers entsprechen, und die SQL Server-Datenbanken sind in der SQL Server Express-Instanz auf dem Standard verbunden Edition-server <br/> |Zum Definieren einer Topologie. Ein Konto, das Mitglieder der lokalen Gruppe „Benutzer“ ist.  <br/> Zum Veröffentlichen der Topologie, sollte ein Konto, das Mitglied der Gruppe Domänen-Admins und Gruppe RTCUniversalServerAdmins und der Benutzer ist auch Vollzugriff-Berechtigungen (Lese-/Schreibzugriff/ändern) auf die Skype für Business-Dateispeicher für Persistent Chat Server-Dateien (in diesem Fall mit der Topologie-Generator die erforderlichen freigegebenen Zugriffssteuerungslisten konfiguriert werden kann).  <br/> |[Erstellen und Veröffentlichen einer neuen Topologie in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md) <br/> [Hinzufügen von Persistent Chat Server zu Ihrer Skype für Business Server 2015 Topologie](add-persistent-chat-server.md) <br/> |
|**Bereitstellen des Servers für beständigen Chat** <br/> | Führen Sie die Skype für Business Server-Setup auf allen Computern mit Persistent Chat Server. Das Persistent Chat Server-Setup wird in der Skype für Business Server-Bereitstellungs-Assistenten integriert, die die folgenden Anweisungen bereitstellt: <br/>  Den lokalen Verwaltungsspeicher bereitstellen <br/>  Installieren von Persistent Chat-Dienste <br/>  Zertifikate anfordern und zuweisen <br/>  Dienste ausführen und starten <br/> |Jeder Benutzer, der Mitglied der lokalen Gruppe „Administratoren“ ist.  <br/> |[Bereitstellung des Servers für beständigen Chat in Skype for Business Server 2015](deploy-persistent-chat-server.md) <br/> |
|**Erstellen eines Administrators für beständigen Chat** <br/> |Fügen Sie der Sicherheitsgruppe „CsPersistentChatAdministrator“ Benutzer hinzu.  <br/> |Jeder Benutzer, der Mitglied der Domänenadministratoren ist.  <br/> |[Erstellen eines Administrators für beständigen Chat in Skype for Business Server 2015](create-a-persistent-chat-administrator.md) <br/> |
|**Konfigurieren des Server für beständigen Chat** <br/> | Konfigurieren von Benutzern: <br/>  Benutzer verfügt über Zugriff auf Persistent Chat Server durch eine Richtlinie aktiviert werden soll. Die Richtlinie ist standardmäßig für alle Benutzer deaktiviert und kann auf globaler, Standort-, Pool- und Benutzerebene definiert werden. <br/>  Einstellungen konfigurieren <br/> |Der Benutzer muss Mitglied von „CsPersistentChatAdministrator“ sein. Benutzer müssen sich zum Ändern der Richtlinie mindestens in „CsUserAdministrator“ befinden.  <br/> |[Verwalten des Servers für beständigen Chat in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

