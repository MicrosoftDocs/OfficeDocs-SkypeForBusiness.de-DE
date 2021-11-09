---
title: Erstellen von Administratoren für die Skype for Business Server-Systemsteuerung
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
ROBOTS: NOINDEX, NOFOLLOW
description: 'Gehen Sie folgendermaßen vor, um Zugriff auf die Skype for Business Server zu gewähren:'
ms.openlocfilehash: 42163cf1df7ae13b918f592b512d3f5fd89169de
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839017"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a>Erstellen von Administratoren für die Skype for Business Server-Systemsteuerung
 
Gehen Sie folgendermaßen vor, um Zugriff auf die Skype for Business Server zu gewähren:
  
1. Melden Sie sich als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    
2. Öffnen Sie **Active Directory-Benutzer und -Computer**, erweitern Sie Ihre Domäne, klicken Sie mit der rechten Maustaste auf den Container **Users**, und klicken Sie dann auf **Eigenschaften**.
    
3. Klicken Sie im Fenster **CSAdministrator-Eigenschaften** auf die Registerkarte **Mitglieder**.
    
4. Klicken Sie auf der Registerkarte "Mitglieder" auf **Hinzufügen**. Wechseln Sie unter **Benutzer, Kontakte, Computer, Dienstkonten oder Gruppen auswählen** zur Option **Geben Sie die zu verwendenden Objektnamen ein**. Geben Sie die Benutzer- bzw. Gruppennamen ein, die der Gruppe "CSAdministrators" hinzugefügt werden sollen. Klicken Sie auf **OK**.
    
5. Überprüfen Sie auf der Registerkarte "Mitglieder", ob die ausgewählten Benutzer bzw. Gruppen vorhanden sind. Klicken Sie auf **OK**.
    
> [!TIP]
> Die Skype for Business Server Systemsteuerung ist ein rollenbasiertes Zugriffssteuerungstool. Die Mitgliedschaft in der Gruppe "CsAdministrator" bietet einem Benutzer, der die Skype for Business Server Systemsteuerung verwendet, vollzugriff auf alle verfügbaren Konfigurationsfunktionen. Es sind weitere Rollen verfügbar, die für spezifische Funktionen konzipiert sind. Benutzer müssen nicht für Skype for Business Server aktiviert sein, um Mitglieder der Verwaltungsgruppen werden zu können. 
  
Weitere Rollen sind:
  
- **CsArchiving:** Mitglieder dieser Gruppe können alle Archivierungsfunktionen ausführen, z. B. das Konfigurieren und Verwalten der Rolle des Archivierungsservers.
    
- **CsHelpDesk:** Mitglieder dieser Gruppe können die Konfiguration und Bereitstellung einschließlich Benutzereigenschaften und Richtlinien anzeigen. Mitglieder können zudem bestimmte Problembehandlungsaufgaben ausführen.
    
- **CsLocationAdministrator:** Mitglieder verfügen über die niedrigste Berechtigungsstufe für die E9-1-1-Verwaltung. Sie können E9-1-1-Standorte und Netzwerk-IDs erstellen und in der Bereitstellung zuordnen.
    
- **CsResponseGroupAdministrator:** Mitglieder können den Reaktionsgruppendienst verwalten und konfigurieren.
    
- **CsServerAdministrator:** Mitglieder können alle Server verwalten, überwachen und Beheben von Problemen, die Skype for Business Server ausgeführt werden.
    
- **CsUserAdministrator:** Mitglieder können Benutzer verwalten, aktivieren und deaktivieren sowie vorhandene Richtlinien Benutzern zuweisen.
    
- **CsViewOnlyAdministrator:** Mitglieder können die Bereitstellung und Konfiguration der Serverinformationen anzeigen. Mit dieser Mitgliedschaft kann ein Mitglied den Status der Server überwachen, auf denen Skype for Business Server ausgeführt wird.
    
- **CsVoiceAdministrator:** Mitglieder können voIP-bezogene Einstellungen in Skype for Business Server erstellen, konfigurieren und verwalten.
    
Um die Integrität der Sicherheits- und rollenbasierten Zugriffssteuerung beizubehalten, fügen Sie Den Gruppen Benutzer hinzu, die definieren, welche Rolle der Benutzer bei der Verwaltung der Skype for Business Server Bereitstellung ausführt.
  

