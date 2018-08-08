---
title: Aktivieren des Parkens von Anrufen für Benutzer in Skype für Unternehmen
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Aktivieren von Benutzern für das Parken von Anrufen in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 44e72cab776b08cbd0290bb15010d36d370d86b3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20968223"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a><span data-ttu-id="9c63c-103">Aktivieren des Parkens von Anrufen für Benutzer in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="9c63c-103">Enable Call Park for users in Skype for Business</span></span>
 
<span data-ttu-id="9c63c-104">Aktivieren von Benutzern für das Parken von Anrufen in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="9c63c-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="9c63c-105">Parken von Anrufen ist standardmäßig für alle Benutzer deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9c63c-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="9c63c-106">Benutzer können nicht Anrufe Parken oder Geparkte Anrufe abgerufen werden soll, bis sie für das Parken von Anrufen in VoIP-Richtlinie aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="9c63c-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="9c63c-107">Sie können das Parken von Anrufen auf globaler Ebene oder auf Standortebene oder Benutzerebene aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9c63c-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="9c63c-108">Benutzerbereich Vorrang gegenüber auf Standortebene und auf Standortebene Vorrang gegenüber globaler Ebene.</span><span class="sxs-lookup"><span data-stu-id="9c63c-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="9c63c-109">Wenn Sie mehrere VoIP-Richtlinien haben, überprüfen Sie alle Richtlinien zum Parken von Anrufen, nicht nur die globale Richtlinie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9c63c-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="9c63c-110">Skype für Business Server-Systemsteuerung zum Aktivieren des Parkens von Anrufen für Benutzer zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9c63c-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="9c63c-111">Melden Sie sich als Mitglied der Gruppe **RTCUniversalServerAdmins** oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** beim Computer an.</span><span class="sxs-lookup"><span data-stu-id="9c63c-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="9c63c-112">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="9c63c-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="9c63c-113">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.</span><span class="sxs-lookup"><span data-stu-id="9c63c-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="9c63c-114">Klicken Sie auf die Registerkarte **VoIP-Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="9c63c-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="9c63c-115">Doppelklicken Sie auf eine vorhandene VoIP-Richtlinie, um das Dialogfeld **VoIP-Richtlinie bearbeiten** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9c63c-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="9c63c-116">Wählen Sie unter **Anruffunktionen** die Option **Parken von Anrufen aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="9c63c-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="9c63c-117">Klicken Sie auf **OK**, um die VoIP-Richtlinie zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9c63c-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="9c63c-118">Zum Verwenden von Cmdlets zum Aktivieren des Parkens von Anrufen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="9c63c-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="9c63c-119">Melden Sie sich auf dem Computer als Mitglied der Gruppe „RTCUniversalServerAdmins“ oder als Benutzer mit der administrativen Rolle „CsVoiceAdministrator“, „CsServerAdministrator“ oder „CsAdministrator“ an.</span><span class="sxs-lookup"><span data-stu-id="9c63c-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="9c63c-120">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="9c63c-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="9c63c-121">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="9c63c-121">Run:</span></span>
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="9c63c-122">Wenn Sie beispielsweise zum Parken von Anrufen für die standardmäßige globale VoIP-Richtlinie zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="9c63c-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="9c63c-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c63c-123">See also</span></span>



[<span data-ttu-id="9c63c-124">Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungseinträge in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="9c63c-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

