---
title: Erstellen oder Bearbeiten der Pushbenachrichtigungskonfiguration für mobile Clients
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
description: Pushbenachrichtigungen und das Push Notification Clearing House (PNCH) sind zwei wichtige Bestandteile des Mobilitätsfeatures. Pushbenachrichtigung ist der Prozess, bei dem eine Nachricht an das PNCH gesendet wird. Die Nachricht wird hier gehalten, bis sie an den mobilen Client zugestellt werden kann oder der Timeoutzeitraum abläuft.
ms.openlocfilehash: 0cd2b17f764891dbb1ad89ada27f6be0b6246ba0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810885"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a>Mobiler Client: Erstellen oder Bearbeiten der Konfiguration für Pushbenachrichtigung
 
Die Pushbenachrichtigung und das Push Notification Clearing House (PNCH) sind zwei wichtige Bestandteile des Mobilitätsfeatures. Pushbenachrichtigung ist der Prozess, bei dem eine Nachricht an das PNCH gesendet wird. Die Nachricht wird hier gehalten, bis sie an den mobilen Client zugestellt werden kann oder der Timeoutzeitraum abläuft. 
  
> [!NOTE]
> Der Zeitraum wird im Push Notification Clearing House festgelegt und kann vom Benutzer oder Administrator Ihrer Bereitstellung nicht konfiguriert werden. 
  
Gehen Sie wie folgt vor, um Pushbenachrichtigungen zu aktivieren:
  
1. **Bereich:** Beachten Sie den Bereich für diese Richtlinie. Es kann entweder **"Global"** sein, was für alle Benutzer in dieser Bereitstellung gilt, oder **"Site",** bei dem es sich nur um Benutzer handelt, die den Homeservern am angegebenen Standort zugewiesen sind.
    
    > [!IMPORTANT]
    > Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen überschreiben, die auf eine andere Richtlinienebene angewendet wurden. Richtlinienrangfolge ist: Benutzerrichtlinie (größter Einfluss) setzt eine Standortrichtlinie außer Kraft, und dann setzt eine Standortrichtlinie eine globale Richtlinie außer Kraft (geringster Einfluss). Dies bedeutet Folgendes: Je näher sich die Richtlinieneinstellung am betroffenen Objekt befindet, umso mehr Einfluss auf das Objekt hat sie. 
  
2. Wählen Sie die Pushbenachrichtigungsdienste aus, die Sie aktivieren möchten, indem Sie auf das Kontrollkästchen für:
    
   - **Wenn Sie die Pushbenachrichtigung von Microsoft** aktivieren, wird die Pushbenachrichtigung an den cloudbasierten PNCH für Windows Phone mit der Skype for Business-App aktiviert.
    
   - **Wenn Sie die Apple-Pushbenachrichtigung** aktivieren, wird die Pushbenachrichtigung an den Apple PNCH für Geräte aktiviert, auf denen Apples iOS ausgeführt wird (z. B. iPhone, iPad) und die Skype for Business-App verwendet wird.
    
3. Wenn Sie die Änderungen an der Richtlinie abgeschlossen haben, klicken Sie auf **"Commit",** um die Änderungen zu speichern. Wenn Sie die vorgenommenen Änderungen löschen müssen, wählen Sie **"Abbrechen" aus.** Es werden keine Änderungen an der Richtlinie gespeichert.
    

