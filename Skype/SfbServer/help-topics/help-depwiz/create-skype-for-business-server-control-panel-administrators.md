---
title: Erstellen von Administratoren für die Skype for Business Server-Systemsteuerung
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
description: 'Um Zugriff auf die Skype für Business Server 2015 gewähren möchten, führen Sie folgende Schritte aus:'
ms.openlocfilehash: 5d01066da5be34ba53f4eca37d35a3913d07142a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201339"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a>Erstellen von Administratoren für die Skype for Business Server-Systemsteuerung
 
Um Zugriff auf die Skype für Business Server 2015 gewähren möchten, führen Sie folgende Schritte aus:
  
1. Melden Sie sich als Mitglied der Gruppe „Domänen-Admins“ oder „RTCUniversalServerAdmins“ an.
    
2. Öffnen Sie **Active Directory-Benutzer und -Computer**, erweitern Sie Ihre Domäne, klicken Sie mit der rechten Maustaste auf den Container **Benutzer** und klicken Sie dann auf **Eigenschaften**.
    
3. Klicken Sie im Fenster **CSAdministrator-Eigenschaften** auf die Registerkarte **Mitglieder**.
    
4. Klicken Sie auf der Registerkarte „Mitglieder“ auf **Hinzufügen**. Wechseln Sie unter **Benutzer, Kontakte, Computer, Dienstkonten oder Gruppen auswählen** zur Option **Geben Sie die zu verwendenden Objektnamen ein**. Geben Sie die Benutzer- bzw. Gruppennamen ein, die zur Gruppe „CSAdministrators“ hinzugefügt werden sollen. Klicken Sie auf **OK**.
    
5. Überprüfen Sie auf der Registerkarte „Mitglieder“, ob die ausgewählten Benutzer bzw. Gruppen vorhanden sind. Klicken Sie auf **OK**.
    
> [!TIP]
> Die Skype Business Server-Systemsteuerung ist ein rollenbasierten. Die Mitgliedschaft in der Gruppe csadministrator hinzu ermöglicht einem Benutzer, der Skype für Business Server-Systemsteuerung Vollzugriff auf alle verfügbaren Konfigurationsfunktionen verwendet wird. Es sind weitere Rollen verfügbar, die für spezifische Funktionen konzipiert sind. Benutzer müssen nicht für Skype für Business Server aktiviert sein, damit die Mitglieder der Verwaltungsgruppen vorgenommen werden. 
  
Andere Rollen umfassen:
  
- **CsArchiving:** Mitglieder dieser Gruppe können alle Archivierungsfunktionen wie konfigurieren und Verwalten der Archivierungsserver-Rolle ausführen.
    
- **CsHelpDesk:** Mitglieder dieser Gruppe können die Konfiguration und Bereitstellung einschließlich Benutzereigenschaften und Richtlinien anzeigen. Mitglieder können zudem bestimmte Problembehandlungsaufgaben ausführen.
    
- **CsLocationAdministrator:** Mitglieder verfügen über die niedrigste Berechtigungsstufe für die E9-1-1-Verwaltung. Sie können E9-1-1-Standorte und Netzwerk-IDs erstellen und in der Bereitstellung zuordnen.
    
- **CsResponseGroupAdministrator:** Mitglieder können den Reaktionsgruppendienst verwalten und konfigurieren.
    
- **CsServerAdministrator:** Mitglieder können verwalten, überwachen und beheben alle Server mit Skype für Business Server.
    
- **CsUserAdministrator:** Mitglieder können Benutzer verwalten, aktivieren und deaktivieren sowie vorhandene Richtlinien Benutzern zuweisen.
    
- **CsViewOnlyAdministrator:** Mitglieder können die Bereitstellung und Konfiguration der Serverinformationen anzeigen. Diese Mitgliedschaft ermöglicht Mitglied, um die Integrität der von den Servern mit Skype für Business Server 2015 zu überwachen.
    
- **"Csvoiceadministrator":** Mitglieder können erstellen, konfigurieren und Verwalten von VoIP-bezogene Einstellungen in Skype für Business Server.
    
Um die Aufrechterhaltung von Sicherheit und Integrität der rollenbasierten-Steuerelement, Hinzufügen von Benutzern zu Gruppen, die definieren, welche Rolle der Benutzer bei der Verwaltung der der Skype für Business Server-Bereitstellung ausführt.
  

