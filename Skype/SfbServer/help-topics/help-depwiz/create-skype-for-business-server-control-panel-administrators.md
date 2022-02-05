---
title: Erstellen von Administratoren für die Skype for Business Server-Systemsteuerung
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
description: 'Gehen Sie folgendermaßen vor, um Zugriff auf die Skype for Business Server 2015 zu gewähren:'
---

# <a name="create-skype-for-business-server-control-panel-administrators"></a>Erstellen von Administratoren für die Skype for Business Server-Systemsteuerung
 
Gehen Sie folgendermaßen vor, um Zugriff auf die Skype for Business Server 2015 zu gewähren:
  
1. Melden Sie sich als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    
2. Öffnen Sie **Active Directory-Benutzer und -Computer**, erweitern Sie Ihre Domäne, klicken Sie mit der rechten Maustaste auf den Container **Users**, und klicken Sie dann auf **Eigenschaften**.
    
3. Klicken Sie im Fenster **CSAdministrator-Eigenschaften** auf die Registerkarte **Mitglieder**.
    
4. Klicken Sie auf der Registerkarte "Mitglieder" auf **Hinzufügen**. Wechseln Sie unter **Benutzer, Kontakte, Computer, Dienstkonten oder Gruppen auswählen** zur Option **Geben Sie die zu verwendenden Objektnamen ein**. Geben Sie die Benutzer- bzw. Gruppennamen ein, die der Gruppe "CSAdministrators" hinzugefügt werden sollen. Klicken Sie auf **OK**.
    
5. Überprüfen Sie auf der Registerkarte "Mitglieder", ob die ausgewählten Benutzer bzw. Gruppen vorhanden sind. Klicken Sie auf **OK**.
    
> [!TIP]
> Die Skype for Business Server Systemsteuerung ist ein rollenbasiertes Zugriffssteuerungstool. Die Mitgliedschaft in der Gruppe "CsAdministrator" bietet einem Benutzer, der die Skype for Business Server Systemsteuerung verwendet, vollzugriff auf alle verfügbaren Konfigurationsfunktionen. Es sind weitere Rollen verfügbar, die für spezifische Funktionen konzipiert sind. Benutzer müssen nicht für Skype for Business Server aktiviert werden, um Mitglieder der Verwaltungsgruppen werden zu können. 
  
Weitere Rollen sind:
  
- **CsArchiving:** Mitglieder dieser Gruppe können alle Archivierungsfunktionen ausführen, z. B. das Konfigurieren und Verwalten der Rolle des Archivierungsservers.
    
- **CsHelpDesk:** Mitglieder dieser Gruppe können die Konfiguration und Bereitstellung einschließlich Benutzereigenschaften und Richtlinien anzeigen. Mitglieder können zudem bestimmte Problembehandlungsaufgaben ausführen.
    
- **CsLocationAdministrator:** Mitglieder verfügen über die niedrigste Berechtigungsstufe für die E9-1-1-Verwaltung. Sie können E9-1-1-Standorte und Netzwerk-IDs erstellen und in der Bereitstellung zuordnen.
    
- **CsResponseGroupAdministrator:** Mitglieder können den Reaktionsgruppendienst verwalten und konfigurieren.
    
- **CsServerAdministrator:** Mitglieder können alle Server verwalten, überwachen und Beheben von Problemen, die Skype for Business Server ausgeführt werden.
    
- **CsUserAdministrator:** Mitglieder können Benutzer verwalten, aktivieren und deaktivieren sowie vorhandene Richtlinien Benutzern zuweisen.
    
- **CsViewOnlyAdministrator:** Mitglieder können die Bereitstellung und Konfiguration der Serverinformationen anzeigen. Mit dieser Mitgliedschaft kann ein Mitglied den Status der Server überwachen, auf denen Skype for Business Server 2015 ausgeführt wird.
    
- **CsVoiceAdministrator:** Mitglieder können voIP-bezogene Einstellungen in Skype for Business Server erstellen, konfigurieren und verwalten.
    
Um die Integrität der Sicherheit und der rollenbasierten Zugriffssteuerung beizubehalten, fügen Sie Den Gruppen Benutzer hinzu, die definieren, welche Rolle der Benutzer bei der Verwaltung der Skype for Business Server Bereitstellung ausführt.
  

