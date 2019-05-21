---
title: Erstellen von Administratoren für die Skype for Business Server-Systemsteuerung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
description: 'Gehen Sie wie folgt vor, um den Zugriff auf Skype for Business Server 2015 zu gewähren:'
ms.openlocfilehash: 6fe5fee80921121c71ccdc4bb6e6de29ac4302fb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301876"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a>Erstellen von Administratoren für die Skype for Business Server-Systemsteuerung
 
Gehen Sie wie folgt vor, um den Zugriff auf Skype for Business Server 2015 zu gewähren:
  
1. Melden Sie sich als Mitglied der Gruppe „Domänen-Admins“ oder „RTCUniversalServerAdmins“ an.
    
2. Öffnen Sie **Active Directory-Benutzer und -Computer**, erweitern Sie Ihre Domäne, klicken Sie mit der rechten Maustaste auf den Container **Benutzer** und klicken Sie dann auf **Eigenschaften**.
    
3. Klicken Sie im Fenster **CSAdministrator-Eigenschaften** auf die Registerkarte **Mitglieder**.
    
4. Klicken Sie auf der Registerkarte „Mitglieder“ auf **Hinzufügen**. Wechseln Sie unter **Benutzer, Kontakte, Computer, Dienstkonten oder Gruppen auswählen** zur Option **Geben Sie die zu verwendenden Objektnamen ein**. Geben Sie die Benutzer- bzw. Gruppennamen ein, die zur Gruppe „CSAdministrators“ hinzugefügt werden sollen. Klicken Sie auf **OK**.
    
5. Überprüfen Sie auf der Registerkarte „Mitglieder“, ob die ausgewählten Benutzer bzw. Gruppen vorhanden sind. Klicken Sie auf **OK**.
    
> [!TIP]
> Das Skype for Business Server Control Panel ist ein rollenbasiertes Zugriffs Steuerungstool. Die Mitgliedschaft in der CsAdministrator-Gruppe gibt Benutzern, die das Skype for Business Server Control Panel verwenden, Vollzugriff für alle verfügbaren Konfigurationsfunktionen. Es sind weitere Rollen verfügbar, die für spezifische Funktionen konzipiert sind. Benutzer müssen für Skype for Business Server nicht aktiviert sein, damit Sie Mitglieder der Verwaltungsgruppen werden können. 
  
Weitere Rollen sind:
  
- **CsArchiving:** Mitglieder dieser Gruppe können alle Archivierungsfunktionen wie das Konfigurieren und Verwalten der Archivierungs Server Rolle ausführen.
    
- **CsHelpDesk:** Mitglieder dieser Gruppe können die Konfiguration und Bereitstellung einschließlich Benutzereigenschaften und Richtlinien anzeigen. Mitglieder können zudem bestimmte Problembehandlungsaufgaben ausführen.
    
- **CsLocationAdministrator:** Mitglieder verfügen über die niedrigste Berechtigungsstufe für die E9-1-1-Verwaltung. Sie können E9-1-1-Standorte und Netzwerk-IDs erstellen und in der Bereitstellung zuordnen.
    
- **CsResponseGroupAdministrator:** Mitglieder können den Reaktionsgruppendienst verwalten und konfigurieren.
    
- **CsServerAdministrator:** Mitglieder können alle Server mit Skype for Business Server verwalten, überwachen und beheben.
    
- **CsUserAdministrator:** Mitglieder können Benutzer verwalten, aktivieren und deaktivieren sowie vorhandene Richtlinien Benutzern zuweisen.
    
- **CsViewOnlyAdministrator:** Mitglieder können die Bereitstellung und Konfiguration der Server Informationen anzeigen. Diese Mitgliedschaft ermöglicht einem Mitglied, die Integrität der Server zu überwachen, auf denen Skype for Business Server 2015 ausgeführt wird.
    
- **CsVoiceAdministrator:** Mitglieder können sprachbezogene Einstellungen in Skype for Business Server erstellen, konfigurieren und verwalten.
    
Um die Integrität von Sicherheit und rollenbasierter Zugriffssteuerung zu erhalten, fügen Sie Benutzer zu den Gruppen hinzu, die definieren, welche Rolle der Benutzer bei der Verwaltung der Skype for Business Server-Bereitstellung übernimmt.
  

