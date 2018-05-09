---
title: Ausgehende aufrufende einschränkungsrichtlinien für Audiokonferenzen und Benutzer PSTN-Anrufe
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Administratoren können den Typ des audio-Konferenzen und Endbenutzer-PSTN-Anrufe steuern, die von Benutzern vorgenommen werden können.
ms.openlocfilehash: 2929198a8bfff866f0d9f6d375593cd429885b2e
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="4deb3-103">Ausgehende aufrufende einschränkungsrichtlinien für Audiokonferenzen und Benutzer PSTN-Anrufe</span><span class="sxs-lookup"><span data-stu-id="4deb3-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="4deb3-104">Als Administrator können Sie ausgehende Anrufe Steuerelemente verwenden, um den Typ des audio-Konferenzen und Endbenutzer-PSTN-Anrufe zu beschränken, die von Benutzern in Ihrer Organisation hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="4deb3-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="4deb3-105">Ausgehende Anrufe für jeden Benutzer einzeln angewendet werden kann und ermöglichen die folgenden zwei Steuerelemente, um jede Art von ausgehenden Anrufen unabhängig voneinander zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="4deb3-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="4deb3-106">Standardmäßig werden beide Steuerelemente festgelegt, um internationaler und ausgehende Anrufe zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="4deb3-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="4deb3-107">Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4deb3-107">Control</span></span>|<span data-ttu-id="4deb3-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4deb3-108">Description</span></span>|<span data-ttu-id="4deb3-109">Steueroptionen</span><span class="sxs-lookup"><span data-stu-id="4deb3-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4deb3-110">Audio-Konferenzen PSTN-Anrufe</span><span class="sxs-lookup"><span data-stu-id="4deb3-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="4deb3-111">Legt eine Beschränkung auf den Typ des ausgehenden</span><span class="sxs-lookup"><span data-stu-id="4deb3-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="4deb3-112">Anrufe, die innerhalb zulässig sind</span><span class="sxs-lookup"><span data-stu-id="4deb3-112">calls that are allowed from within</span></span> </br><span data-ttu-id="4deb3-113">von einem Benutzer organisierte Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="4deb3-113">meetings organized by a user.</span></span>|<span data-ttu-id="4deb3-114">Internationalisierung und National (Standard)</span><span class="sxs-lookup"><span data-stu-id="4deb3-114">International and Domestic (default)</span></span></br><span data-ttu-id="4deb3-115">Inlandsanruf</span><span class="sxs-lookup"><span data-stu-id="4deb3-115">Domestic</span></span></br><span data-ttu-id="4deb3-116">Keine</span><span class="sxs-lookup"><span data-stu-id="4deb3-116">None</span></span>|
|<span data-ttu-id="4deb3-117">Endbenutzer-PSTN-Anrufe</span><span class="sxs-lookup"><span data-stu-id="4deb3-117">End user PSTN calls</span></span>|<span data-ttu-id="4deb3-118">Legt eine Beschränkung auf den Typ von Anrufen</span><span class="sxs-lookup"><span data-stu-id="4deb3-118">Restricts the type of calls</span></span> </br><span data-ttu-id="4deb3-119">können von einem Benutzer vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="4deb3-119">that can be made by a user.</span></span>|<span data-ttu-id="4deb3-120">Internationalisierung und National (Standard)</span><span class="sxs-lookup"><span data-stu-id="4deb3-120">International and Domestic (default)</span></span></br><span data-ttu-id="4deb3-121">Inlandsanruf</span><span class="sxs-lookup"><span data-stu-id="4deb3-121">Domestic</span></span></br><span data-ttu-id="4deb3-122">Keine</span><span class="sxs-lookup"><span data-stu-id="4deb3-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="4deb3-123">Ein Aufruf ist bestimmt nationalen, wenn die gewählte Rufnummer in demselben Land als das Land ist, die in Office 365 für den Organisator der Besprechung (im Fall von Audiokonferenzen) oder die Endbenutzer (im Fall von Endbenutzer PSTN-Anrufe) festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="4deb3-123">A call is determined to be domestic if the called phone number is in the same country as the country that has been set in Office 365 for the organizer of the meeting (in the case of audio conferencing) or the end user (in the case of end user PSTN calls).</span></span> 


## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="4deb3-124">Einschränken von Audiokonferenzen ausgehende Anrufe</span><span class="sxs-lookup"><span data-stu-id="4deb3-124">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="4deb3-125">![Teams-Logo-30x30.png](../images/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="4deb3-125">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="4deb3-126">Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="4deb3-126">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="4deb3-127">Klicken Sie am oberen Rand der Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="4deb3-127">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="4deb3-128">Klicken Sie auf das Menü neben **Konferenz Brücken**, und klicken Sie dann auf **Bearbeiten** , in der Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="4deb3-128">Click the menu next to **Conference Bridges**, and then click **Edit** in the drop-down list.</span></span>

4. <span data-ttu-id="4deb3-129">Klicken Sie im **Konferenz Bridge Anbieter** unter **Einschränkungen auf DFÜ-Outs von Besprechungen dieses Benutzers**die Option Dial-Out-Einschränkung gewünschten.</span><span class="sxs-lookup"><span data-stu-id="4deb3-129">In the **Conference bridge provider** pane, under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="4deb3-130">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="4deb3-130">Click **Apply**.</span></span> 

<span data-ttu-id="4deb3-131">![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**</span><span class="sxs-lookup"><span data-stu-id="4deb3-131">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.  <span data-ttu-id="4deb3-132">Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer.</span><span class="sxs-lookup"><span data-stu-id="4deb3-132">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.  <span data-ttu-id="4deb3-133">In the Action pane, click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="4deb3-133">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="4deb3-134">Wählen Sie unter **Dial-Outs von Besprechungen dieses Benutzers Einschränkungen**die gewünschte Option der Dial-Out-Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="4deb3-134">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![Die Einschränkungen auf DFÜ-Outs-Optionen](../images/restrictions-to-dial-outs.png)

5. <span data-ttu-id="4deb3-136">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4deb3-136">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="4deb3-137">**Verwenden von PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4deb3-137">**Using PowerShell**</span></span>

<span data-ttu-id="4deb3-138">Ausgehende Anrufe Einschränkungen werden durch eine einzelne Richtlinie aufgerufen OnlineDialOutPolicy über ein Attribut Einschränkung für jede gesteuert.</span><span class="sxs-lookup"><span data-stu-id="4deb3-138">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="4deb3-139">Die Richtlinie kann nicht angepasst werden, vielmehr vordefinierte Policy-Instanzen für jede Kombination der Einstellungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="4deb3-139">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="4deb3-140">Das Cmdlet Get-CSOnlineDialOutPolicy können Sie zeigen Sie die ausgehenden aufrufenden Richtlinien und weisen Sie diese Benutzer mit dem Cmdlet Grant-CSDialOutPolicy.</span><span class="sxs-lookup"><span data-stu-id="4deb3-140">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="4deb3-141">(Beachten Sie, dass das Cmdlet Grant das Wort "Online" enthalten, nicht wie das Get-Cmdlet.)</span><span class="sxs-lookup"><span data-stu-id="4deb3-141">(Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="4deb3-142">Die folgende Tabelle enthält eine Übersicht über die einzelnen Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="4deb3-142">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4deb3-143">Identität = 'Tag: DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="4deb3-143">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="4deb3-144">Benutzer in der Konferenz kann eine ausgehende Verbindung internationaler und Zahlen, und dieser Benutzer kann auch ausgehende Anrufe bei Nummern internationaler und tätigen.</span><span class="sxs-lookup"><span data-stu-id="4deb3-144">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="4deb3-145">Identität = 'Tag: DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="4deb3-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="4deb3-146">Benutzer in der Konferenz kann nur eine ausgehende Verbindung nationalen Zahlen, und dieser Benutzer ausgehende Anrufe bei Nummern internationaler und machen kann.</span><span class="sxs-lookup"><span data-stu-id="4deb3-146">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="4deb3-147">Identität = 'Tag: DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="4deb3-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="4deb3-148">Benutzer in der Konferenz ist nicht möglich alle Zugriffsnummern stellen. Diese Benutzer kann ausgehende Anrufe bei Nummern internationaler und tätigen.</span><span class="sxs-lookup"><span data-stu-id="4deb3-148">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="4deb3-149">Identität = 'Tag: DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="4deb3-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="4deb3-150">Benutzer in der Konferenz kann eine ausgehende Verbindung internationaler und Zahlen, und dieser Benutzer kann nur ausgehende Anrufe an PSTN-Nummer nationalen tätigen.</span><span class="sxs-lookup"><span data-stu-id="4deb3-150">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="4deb3-151">Identität = 'Tag: DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="4deb3-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="4deb3-152">Benutzer in der Konferenz kann eine ausgehende Verbindung internationaler und Zahlen kann, und dieser Benutzer ausgehende Anrufe an PSTN-Nummer neben Notfall Zahlen.</span><span class="sxs-lookup"><span data-stu-id="4deb3-152">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="4deb3-153">Identität = 'Tag: DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="4deb3-153">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="4deb3-154">Benutzer in der Konferenz kann nur eine ausgehende Verbindung nationalen Zahlen, und dieser Benutzer kann nur ausgehenden Anrufe an PSTN-Nummern nationalen tätigen.</span><span class="sxs-lookup"><span data-stu-id="4deb3-154">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="4deb3-155">Identität = 'Tag: DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="4deb3-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="4deb3-156">Benutzer in der Konferenz kann nur eine ausgehende Verbindung nationalen Zahlen kann, und dieser Benutzer ausgehende Anrufe an PSTN-Nummer neben Notfall Zahlen.</span><span class="sxs-lookup"><span data-stu-id="4deb3-156">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="4deb3-157">Identität = 'Tag: DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="4deb3-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="4deb3-158">Benutzer in der Konferenz kann keine Client-stellen, und dieser Benutzer kann nur ausgehenden Anrufe an PSTN-Nummern nationalen tätigen.</span><span class="sxs-lookup"><span data-stu-id="4deb3-158">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="4deb3-159">Identität = 'Tag: DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="4deb3-159">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="4deb3-160">Benutzer in der Konferenz kann keine Client-stellen, und dieser Benutzer kann keine ausgehende Anrufe an PSTN-Nummer neben Notfall Zahlen tätigen.</span><span class="sxs-lookup"><span data-stu-id="4deb3-160">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
