---
title: Einschränkungsrichtlinien für ausgehende Anrufe für Audiokonferenzen und PSTN-Anrufe
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Administratoren können den Typ des audio-Konferenzen und Endbenutzer-PSTN-Anrufe steuern, die von Benutzern vorgenommen werden können.
ms.openlocfilehash: 36f116acb62cd16863cb547a11fe5687457a8a4e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881839"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="16865-103">Einschränkungsrichtlinien für ausgehende Anrufe für Audiokonferenzen und PSTN-Anrufe</span><span class="sxs-lookup"><span data-stu-id="16865-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="16865-104">Als Administrator können Sie die Steuerelemente für ausgehende Anrufe verwenden, um den Typ der Audiokonferenzen und Endbenutzer-PSTN-Anrufe einzuschränken, die von Benutzern in Ihrer Organisation verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="16865-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="16865-105">Ausgehende Anrufe für jeden Benutzer einzeln angewendet werden kann und ermöglichen die folgenden zwei Steuerelemente, um jede Art von ausgehenden Anrufen unabhängig voneinander zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="16865-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="16865-106">Standardmäßig werden beide Steuerelemente festgelegt, um internationaler und ausgehende Anrufe zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="16865-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="16865-107">Steuerung</span><span class="sxs-lookup"><span data-stu-id="16865-107">Control</span></span>|<span data-ttu-id="16865-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16865-108">Description</span></span>|<span data-ttu-id="16865-109">Steueroptionen</span><span class="sxs-lookup"><span data-stu-id="16865-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="16865-110">Audio-Konferenzen PSTN-Anrufe</span><span class="sxs-lookup"><span data-stu-id="16865-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="16865-111">Legt eine Beschränkung auf den Typ des ausgehenden</span><span class="sxs-lookup"><span data-stu-id="16865-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="16865-112">Anrufe, die innerhalb zulässig sind</span><span class="sxs-lookup"><span data-stu-id="16865-112">calls that are allowed from within</span></span> </br><span data-ttu-id="16865-113">von einem Benutzer organisierte Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="16865-113">meetings organized by a user.</span></span>|<span data-ttu-id="16865-114">Internationalisierung und National (Standard)</span><span class="sxs-lookup"><span data-stu-id="16865-114">International and Domestic (default)</span></span></br><span data-ttu-id="16865-115">Inlandsanruf</span><span class="sxs-lookup"><span data-stu-id="16865-115">Domestic</span></span></br><span data-ttu-id="16865-116">Keine </span><span class="sxs-lookup"><span data-stu-id="16865-116">None</span></span>|
|<span data-ttu-id="16865-117">Endbenutzer-PSTN-Anrufe</span><span class="sxs-lookup"><span data-stu-id="16865-117">End user PSTN calls</span></span>|<span data-ttu-id="16865-118">Legt eine Beschränkung auf den Typ von Anrufen</span><span class="sxs-lookup"><span data-stu-id="16865-118">Restricts the type of calls</span></span> </br><span data-ttu-id="16865-119">können von einem Benutzer vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="16865-119">that can be made by a user.</span></span>|<span data-ttu-id="16865-120">Internationalisierung und National (Standard)</span><span class="sxs-lookup"><span data-stu-id="16865-120">International and Domestic (default)</span></span></br><span data-ttu-id="16865-121">Inlandsanruf</span><span class="sxs-lookup"><span data-stu-id="16865-121">Domestic</span></span></br><span data-ttu-id="16865-122">Keine </span><span class="sxs-lookup"><span data-stu-id="16865-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="16865-123">Ein Aufruf ist bestimmt nationalen, wenn die gewählte Rufnummer in demselben Land als das Land ist, die in Office 365 für den Organisator der Besprechung (im Fall von Audiokonferenzen) oder die Endbenutzer (im Fall von Endbenutzer PSTN-Anrufe) festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="16865-123">A call is determined to be domestic if the called phone number is in the same country as the country that has been set in Office 365 for the organizer of the meeting (in the case of audio conferencing) or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="16865-124">Einschränken von Audiokonferenzen ausgehende Anrufe</span><span class="sxs-lookup"><span data-stu-id="16865-124">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="16865-125">![Teams-Logo-30x30.png](../images/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**</span><span class="sxs-lookup"><span data-stu-id="16865-125">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="16865-126">Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="16865-126">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="16865-127">Klicken Sie am oberen Rand der Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="16865-127">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="16865-128">Klicken Sie neben **Audiokonferenzen**auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="16865-128">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="16865-129">Wählen Sie unter **Dial-Out - Berechtigung von Besprechungen**die gewünschte Option der Dial-Out-Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="16865-129">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="16865-130">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="16865-130">Click **Save**.</span></span> 

<span data-ttu-id="16865-131">![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**</span><span class="sxs-lookup"><span data-stu-id="16865-131">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.  <span data-ttu-id="16865-132">Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer.</span><span class="sxs-lookup"><span data-stu-id="16865-132">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.  <span data-ttu-id="16865-133">Klicken Sie im Bereich „Aktion" auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="16865-133">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="16865-134">Wählen Sie unter **Dial-Outs von Besprechungen dieses Benutzers Einschränkungen**die gewünschte Option der Dial-Out-Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="16865-134">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![Die Einschränkungen auf DFÜ-Outs-Optionen](../images/restrictions-to-dial-outs.png)

5. <span data-ttu-id="16865-136">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="16865-136">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="16865-137">**Verwenden von PowerShell**</span><span class="sxs-lookup"><span data-stu-id="16865-137">**Using PowerShell**</span></span>

<span data-ttu-id="16865-138">Ausgehende Anrufe Einschränkungen werden durch eine einzelne Richtlinie aufgerufen OnlineDialOutPolicy über ein Attribut Einschränkung für jede gesteuert.</span><span class="sxs-lookup"><span data-stu-id="16865-138">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="16865-139">Die Richtlinie kann nicht angepasst werden, vielmehr vordefinierte Policy-Instanzen für jede Kombination der Einstellungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="16865-139">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="16865-140">Das Cmdlet Get-CSOnlineDialOutPolicy können Sie zeigen Sie die ausgehenden aufrufenden Richtlinien und weisen Sie diese Benutzer mit dem Cmdlet Grant-CSDialOutPolicy.</span><span class="sxs-lookup"><span data-stu-id="16865-140">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="16865-141">(Beachten Sie, dass das Cmdlet Grant das Wort "Online" enthalten, nicht wie das Get-Cmdlet.)</span><span class="sxs-lookup"><span data-stu-id="16865-141">(Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="16865-142">Die folgende Tabelle enthält eine Übersicht über die einzelnen Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="16865-142">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="16865-143">Identität = 'Tag: DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="16865-143">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="16865-144">Benutzer in der Konferenz kann eine ausgehende Verbindung internationaler und Zahlen, und dieser Benutzer kann auch ausgehende Anrufe bei Nummern internationaler und tätigen.</span><span class="sxs-lookup"><span data-stu-id="16865-144">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="16865-145">Identität = 'Tag: DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="16865-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="16865-146">Benutzer in der Konferenz kann nur eine ausgehende Verbindung nationalen Zahlen, und dieser Benutzer ausgehende Anrufe bei Nummern internationaler und machen kann.</span><span class="sxs-lookup"><span data-stu-id="16865-146">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="16865-147">Identität = 'Tag: DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="16865-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="16865-148">Benutzer in der Konferenz ist nicht möglich alle Zugriffsnummern stellen. Diese Benutzer kann ausgehende Anrufe bei Nummern internationaler und tätigen.</span><span class="sxs-lookup"><span data-stu-id="16865-148">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="16865-149">Identität = 'Tag: DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="16865-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="16865-150">Benutzer in der Konferenz kann eine ausgehende Verbindung internationaler und Zahlen, und dieser Benutzer kann nur ausgehende Anrufe an PSTN-Nummer nationalen tätigen.</span><span class="sxs-lookup"><span data-stu-id="16865-150">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="16865-151">Identität = 'Tag: DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="16865-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="16865-152">Benutzer in der Konferenz kann eine ausgehende Verbindung internationaler und Zahlen kann, und dieser Benutzer ausgehende Anrufe an PSTN-Nummer neben Notfall Zahlen.</span><span class="sxs-lookup"><span data-stu-id="16865-152">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="16865-153">Identität = 'Tag: DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="16865-153">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="16865-154">Benutzer in der Konferenz kann nur eine ausgehende Verbindung nationalen Zahlen, und dieser Benutzer kann nur ausgehenden Anrufe an PSTN-Nummern nationalen tätigen.</span><span class="sxs-lookup"><span data-stu-id="16865-154">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="16865-155">Identität = 'Tag: DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="16865-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="16865-156">Benutzer in der Konferenz kann nur eine ausgehende Verbindung nationalen Zahlen kann, und dieser Benutzer ausgehende Anrufe an PSTN-Nummer neben Notfall Zahlen.</span><span class="sxs-lookup"><span data-stu-id="16865-156">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="16865-157">Identität = 'Tag: DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="16865-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="16865-158">Benutzer in der Konferenz kann keine Client-stellen, und dieser Benutzer kann nur ausgehenden Anrufe an PSTN-Nummern nationalen tätigen.</span><span class="sxs-lookup"><span data-stu-id="16865-158">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="16865-159">Identität = 'Tag: DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="16865-159">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="16865-160">Benutzer in der Konferenz kann keine Client-stellen, und dieser Benutzer kann keine ausgehende Anrufe an PSTN-Nummer neben Notfall Zahlen tätigen.</span><span class="sxs-lookup"><span data-stu-id="16865-160">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
