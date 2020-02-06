---
title: Mobiler Client erstellen oder Bearbeiten der Push-Benachrichtigungskonfiguration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Die Pushbenachrichtigung und das Push Notification Clearing House (PNCH) sind zwei wichtige Teile der Mobilitätsfunktion. Bei der Pushbenachrichtigung wird eine Nachricht an das PNCH gesendet. Die Nachricht wird dort gehalten, bis sie an den mobilen Client übermittelt werden kann oder das Zeitlimit abläuft.
ms.openlocfilehash: ca302e0dbdde2c1628abc6c0257ee807f6f152a8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822668"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a>Mobiler Client: Erstellen oder Bearbeiten der Pushbenachrichtigungskonfiguration
 
Die Pushbenachrichtigung und das Push Notification Clearing House (PNCH) sind zwei wichtige Teile der Mobilitätsfunktion. Bei der Pushbenachrichtigung wird eine Nachricht an das PNCH gesendet. Die Nachricht wird dort gehalten, bis sie an den mobilen Client übermittelt werden kann oder das Zeitlimit abläuft. 
  
> [!NOTE]
> Der Zeitraum wird beim Push Notification Clearing House festgelegt und kann vom Benutzer oder Administrator der Bereitstellung nicht konfiguriert werden. 
  
Führen Sie die folgenden Schritte aus, um die Pushbenachrichtigung zu aktivieren:
  
1. **Bereich:** Beachten Sie den Bereich dieser Richtlinie. Er kann entweder **Global** lauten, was für alle Benutzer in dieser Bereitstellung gilt, oder **Standort**, was nur für Benutzer gilt, die Homeservern des angegebenen Standorts zugewiesen sind.
    
    > [!IMPORTANT]
    > Richtlinieneinstellungen, die auf einer bestimmten Richtlinienebene angewendet werden, können durch Einstellungen überschrieben werden, die auf einer anderen Richtlinienebene angewendet werden. Dabei gilt folgende Rangfolge: Benutzerrichtlinien (größter Einfluss) überschreiben Standortrichtlinien und diese überschreiben wiederum globale Richtlinien (geringster Einfluss). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt. 
  
2. Wählen Sie aus, welche Pushbenachrichtigungsdienste Sie aktivieren möchten, indem Sie das jeweilige Kontrollkästchen aktivieren:
    
   - **Aktivieren von Microsoft Push-Benachrichtigungen** aktiviert die Push-Benachrichtigung für die Cloud-basierte PNCH für Windows Phone mit der Skype for Business-App
    
   - **Apple Push-Benachrichtigung aktivieren** aktiviert die Push-Benachrichtigung an den Apple-PNCH für Geräte, auf denen Apples IOS ausgeführt wird (beispielsweise iPhone, iPad) und mit der Skype for Business-App
    
3. Klicken Sie nach Abschluss der Änderungen an der Richtlinie auf **Commit ausführen**, um Ihre Änderungen zu speichern. Falls Sie die vorgenommenen Änderungen löschen möchten, wählen Sie **Abbrechen**. Die Änderungen der Richtlinie werden dann nicht gespeichert.
    

