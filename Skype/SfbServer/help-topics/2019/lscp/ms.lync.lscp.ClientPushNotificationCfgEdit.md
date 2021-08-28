---
title: Erstellen oder Bearbeiten der Konfiguration von Pushbenachrichtigungen für mobile Clients
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
ROBOTS: NOINDEX, NOFOLLOW
description: Pushbenachrichtigungen und das Push Notification Clearing House (PNCH) sind zwei wichtige Teile des Mobilitätsfeatures. Pushbenachrichtigung ist der Prozess, bei dem eine Nachricht an die PNCH gesendet wird. Die Nachricht wird hier gespeichert, bis sie an den mobilen Client übermittelt werden kann oder der Timeoutzeitraum abläuft.
ms.openlocfilehash: 7e148074690f7895a04e2d217b513eac8f7f148c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583179"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a>Mobiler Client: Erstellen oder Bearbeiten der Konfiguration für Pushbenachrichtigung
 
Pushbenachrichtigungen und das Push Notification Clearing House (PNCH) sind zwei wichtige Teile des Mobilitätsfeatures. Pushbenachrichtigung ist der Prozess, bei dem eine Nachricht an die PNCH gesendet wird. Die Nachricht wird hier gespeichert, bis sie an den mobilen Client übermittelt werden kann oder der Timeoutzeitraum abläuft. 
  
> [!NOTE]
> Der Zeitraum wird im Clearing House für Pushbenachrichtigungen festgelegt und kann vom Benutzer oder dem Administrator Ihrer Bereitstellung nicht konfiguriert werden. 
  
Gehen Sie folgendermaßen vor, um die Pushbenachrichtigung zu aktivieren:
  
1. **Bereich:** Beachten Sie den Bereich für diese Richtlinie. Dies kann entweder **global** sein, was für alle Benutzer in dieser Bereitstellung gilt, oder **"Standort",** bei dem es sich nur um Benutzer handelt, die den Startservern des angegebenen Standorts zugewiesen sind.
    
    > [!IMPORTANT]
    > Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen überschreiben, die auf eine andere Richtlinienebene angewendet wurden. Richtlinienrangfolge: Benutzerrichtlinie (größter Einfluss) setzt eine Standortrichtlinie außer Kraft, und dann überschreibt eine Standortrichtlinie eine globale Richtlinie (geringster Einfluss). Dies bedeutet Folgendes: Je näher sich die Richtlinieneinstellung am betroffenen Objekt befindet, umso mehr Einfluss auf das Objekt hat sie. 
  
2. Wählen Sie aus, welche Pushbenachrichtigungsdienste Sie aktivieren möchten, indem Sie auf das Kontrollkästchen für Folgendes klicken:
    
   - **Aktivieren der Microsoft-Pushbenachrichtigung** aktiviert die Pushbenachrichtigung an die cloudbasierte PNCH für Windows Phone mit der Skype for Business-App
    
   - **"Apple-Pushbenachrichtigung aktivieren"** aktiviert die Pushbenachrichtigung an die Apple PNCH für Geräte mit Apples iOS (z. B. iPhone, iPad) und mithilfe der Skype for Business-App.
    
3. Wenn Sie die Bearbeitungen der Richtlinie abgeschlossen haben, klicken Sie auf **"Commit ausführen",** um Die Änderungen zu speichern. Wenn Sie die vorgenommenen Änderungen löschen müssen, wählen Sie **Abbrechen** aus. An der Richtlinie werden keine Änderungen gespeichert.
    

