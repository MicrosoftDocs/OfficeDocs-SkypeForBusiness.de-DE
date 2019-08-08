---
title: Aktivieren des Anruf Parks für Benutzer in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Aktivieren von Benutzern für den Parken von Anrufen in Skype for Business Server Enterprise-VoIP
ms.openlocfilehash: 797b17cb3d9482d9059bedcbbc347c3dd592e478
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240375"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a><span data-ttu-id="208de-103">Aktivieren des Anruf Parks für Benutzer in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="208de-103">Enable Call Park for users in Skype for Business</span></span>
 
<span data-ttu-id="208de-104">Aktivieren von Benutzern für den Parken von Anrufen in Skype for Business Server Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="208de-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="208de-105">Standardmäßig ist der Parken von Anrufen für alle Benutzer deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="208de-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="208de-106">Benutzer können keine Anrufe parken oder geparkte Anrufe abrufen, bis Sie in der VoIP-Richtlinie für den Anruf Park aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="208de-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="208de-107">Sie können das Parken von Anrufen im globalen Bereich oder auf dem Website Bereich oder dem Benutzerbereich aktivieren.</span><span class="sxs-lookup"><span data-stu-id="208de-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="208de-108">Der Benutzerbereich hat Vorrang vor dem Website Bereich, und der Website Bereich hat Vorrang vor dem globalen Bereich.</span><span class="sxs-lookup"><span data-stu-id="208de-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="208de-109">Wenn Sie über mehrere VoIP-Richtlinien verfügen, überprüfen Sie alle Richtlinien, um den Anruf Park zu aktivieren, und nicht nur die globale Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="208de-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="208de-110">So verwenden Sie die Skype for Business Server-Systemsteuerung zum Aktivieren des Anruf Parks für Benutzer</span><span class="sxs-lookup"><span data-stu-id="208de-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="208de-111">Melden Sie sich als Mitglied der Gruppe **RTCUniversalServerAdmins** oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** beim Computer an.</span><span class="sxs-lookup"><span data-stu-id="208de-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="208de-112">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="208de-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="208de-113">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.</span><span class="sxs-lookup"><span data-stu-id="208de-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="208de-114">Klicken Sie auf die Registerkarte **VoIP-Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="208de-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="208de-115">Doppelklicken Sie auf eine vorhandene VoIP-Richtlinie, um das Dialogfeld **VoIP-Richtlinie bearbeiten** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="208de-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="208de-116">Wählen Sie unter **Anruffunktionen** die Option **Parken von Anrufen aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="208de-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="208de-117">Klicken Sie auf **OK**, um die VoIP-Richtlinie zu speichern.</span><span class="sxs-lookup"><span data-stu-id="208de-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="208de-118">So verwenden Sie Cmdlets zum Aktivieren des Anruf Parks für Benutzer</span><span class="sxs-lookup"><span data-stu-id="208de-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="208de-119">Melden Sie sich auf dem Computer als Mitglied der Gruppe „RTCUniversalServerAdmins“ oder als Benutzer mit der administrativen Rolle „CsVoiceAdministrator“, „CsServerAdministrator“ oder „CsAdministrator“ an.</span><span class="sxs-lookup"><span data-stu-id="208de-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="208de-120">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="208de-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="208de-121">Führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="208de-121">Run:</span></span>
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="208de-122">So können Sie beispielsweise den Anruf Park für die standardmäßige globale VoIP-Richtlinie aktivieren:</span><span class="sxs-lookup"><span data-stu-id="208de-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="208de-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="208de-123">See also</span></span>



[<span data-ttu-id="208de-124">Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="208de-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

