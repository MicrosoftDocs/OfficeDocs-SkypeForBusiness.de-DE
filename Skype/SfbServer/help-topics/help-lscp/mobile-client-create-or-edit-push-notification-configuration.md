---
title: Mobiler Client erstellen oder Bearbeiten der Pushbenachrichtigungskonfiguration
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
description: Die Pushbenachrichtigung und das Push Notification Clearing House (PNCH) sind zwei wichtige Teile der Mobilitätsfunktion. Bei der Pushbenachrichtigung wird eine Nachricht an das PNCH gesendet. Die Nachricht wird dort gehalten, bis sie an den mobilen Client übermittelt werden kann oder das Zeitlimit abläuft.
ms.openlocfilehash: d9c3ae19255e58c9de5874d745107654a93f7a28
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882187"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a><span data-ttu-id="7461c-105">Mobiler Client: Erstellen oder Bearbeiten der Pushbenachrichtigungskonfiguration</span><span class="sxs-lookup"><span data-stu-id="7461c-105">Mobile Client: Create or Edit Push Notification Configuration</span></span>
 
<span data-ttu-id="7461c-p102">Die Pushbenachrichtigung und das Push Notification Clearing House (PNCH) sind zwei wichtige Teile der Mobilitätsfunktion. Bei der Pushbenachrichtigung wird eine Nachricht an das PNCH gesendet. Die Nachricht wird dort gehalten, bis sie an den mobilen Client übermittelt werden kann oder das Zeitlimit abläuft.</span><span class="sxs-lookup"><span data-stu-id="7461c-p102">Push Notification and the Push Notification Clearing House (PNCH) are two key parts of the mobility feature. Push notification is the process where a message is sent to the PNCH. The message is held here until it can be delivered to the mobile client, or the timeout period expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7461c-109">Der Zeitraum wird beim Push Notification Clearing House festgelegt und kann vom Benutzer oder Administrator der Bereitstellung nicht konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="7461c-109">The time period is set at the Push Notification Clearing House and is not configurable by the user or the administrator of your deployment.</span></span> 
  
<span data-ttu-id="7461c-110">Führen Sie die folgenden Schritte aus, um die Pushbenachrichtigung zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="7461c-110">To enable Push Notification, you do the following:</span></span>
  
1. <span data-ttu-id="7461c-p103">**Bereich:** Beachten Sie den Bereich dieser Richtlinie. Er kann entweder **Global** lauten, was für alle Benutzer in dieser Bereitstellung gilt, oder **Standort**, was nur für Benutzer gilt, die Homeservern des angegebenen Standorts zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="7461c-p103">**Scope:** Note the scope for this policy. It can either be **Global**, which applies to all users in this deployment, or **Site**, which is only users assigned to home servers in the specified site.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7461c-p104">Richtlinieneinstellungen, die auf einer bestimmten Richtlinienebene angewendet werden, können durch Einstellungen überschrieben werden, die auf einer anderen Richtlinienebene angewendet werden. Dabei gilt folgende Rangfolge: Benutzerrichtlinien (größter Einfluss) überschreiben Standortrichtlinien und diese überschreiben wiederum globale Richtlinien (geringster Einfluss). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.</span><span class="sxs-lookup"><span data-stu-id="7461c-p104">Policy settings that are applied at one policy level can override settings that are applied at another policy level. Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
2. <span data-ttu-id="7461c-116">Wählen Sie aus, welche Pushbenachrichtigungsdienste Sie aktivieren möchten, indem Sie das jeweilige Kontrollkästchen aktivieren:</span><span class="sxs-lookup"><span data-stu-id="7461c-116">Select which push notification services you want to enable by clicking the check box for:</span></span>
    
   - <span data-ttu-id="7461c-117">**Aktivieren von Microsoft-Pushbenachrichtigungen** aktivieren die Pushbenachrichtigung für die Cloud-basierten PNCH für Windows Phone mit der Skype für Geschäfts-app</span><span class="sxs-lookup"><span data-stu-id="7461c-117">**Enable Microsoft push notification** will enable the push notification to the cloud-based PNCH for Windows Phone with the Skype for Business app</span></span>
    
   - <span data-ttu-id="7461c-118">**Kontrollkästchen Apple-Pushbenachrichtigungen** aktivieren die Pushbenachrichtigung für die Apple-PNCH für Geräte von Apple iOS (beispielsweise iPhone, iPad) ausgeführt, und verwenden die Skype für Geschäfts-app</span><span class="sxs-lookup"><span data-stu-id="7461c-118">**Enable Apple push notification** will enable the push notification to the Apple PNCH for devices running Apple's iOS (for example, iPhone, iPad) and using the Skype for Business app</span></span>
    
3. <span data-ttu-id="7461c-p105">Klicken Sie nach Abschluss der Änderungen an der Richtlinie auf **Commit ausführen**, um Ihre Änderungen zu speichern. Falls Sie die vorgenommenen Änderungen löschen möchten, wählen Sie **Abbrechen**. Die Änderungen der Richtlinie werden dann nicht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7461c-p105">When you have completed the edits of the policy, click **Commit** to save your changes. If you need to delete the changes you have made, select **Cancel**. No changes will be saved to the policy.</span></span>
    

