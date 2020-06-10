---
title: Einschränkungen für ausgehende Anrufe-Audiokonferenzen & PSTN-Anrufe
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Administratoren können den Typ von Audiokonferenz-und Endbenutzer-PSTN-anrufen steuern, die von Benutzern vorgenommen werden können.
ms.openlocfilehash: ca4b7920ccad27a9434cbd1e5f76d7d10c4f4612
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665907"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="37ac2-103">Einschränkungsrichtlinien für ausgehende Anrufe für Audiokonferenzen und PSTN-Anrufe</span><span class="sxs-lookup"><span data-stu-id="37ac2-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="37ac2-104">Als Administrator können Sie die Steuerelemente für ausgehende Anrufe verwenden, um den Typ der Audiokonferenzen und Endbenutzer-PSTN-Anrufe einzuschränken, die von Benutzern in Ihrer Organisation verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="37ac2-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="37ac2-105">Steuerelemente für ausgehende Anrufe können auf Benutzerebene angewendet werden und bieten die folgenden zwei Steuerelemente, um die einzelnen ausgehenden Anrufe unabhängig voneinander zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="37ac2-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="37ac2-106">Standardmäßig sind beide Steuerelemente so eingestellt, dass Auslands-und Inlandsanrufe zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="37ac2-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="37ac2-107">Steuerelement</span><span class="sxs-lookup"><span data-stu-id="37ac2-107">Control</span></span>|<span data-ttu-id="37ac2-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="37ac2-108">Description</span></span>|<span data-ttu-id="37ac2-109">Steuerelementoptionen</span><span class="sxs-lookup"><span data-stu-id="37ac2-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="37ac2-110">PSTN-Anrufe für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="37ac2-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="37ac2-111">Schränkt den ausgehenden Typ ein</span><span class="sxs-lookup"><span data-stu-id="37ac2-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="37ac2-112">Anrufe, die innerhalb von zulässig sind</span><span class="sxs-lookup"><span data-stu-id="37ac2-112">calls that are allowed from within</span></span> </br><span data-ttu-id="37ac2-113">Besprechungen, die von einem Benutzer organisiert werden.</span><span class="sxs-lookup"><span data-stu-id="37ac2-113">meetings organized by a user.</span></span>|<span data-ttu-id="37ac2-114">Beliebiges Ziel (Standard)</span><span class="sxs-lookup"><span data-stu-id="37ac2-114">Any destination (default)</span></span></br><span data-ttu-id="37ac2-115">Im gleichen Land oder in derselben Region wie die Organisator</span><span class="sxs-lookup"><span data-stu-id="37ac2-115">In the same country or region as the organizor</span></span> </br> </br><span data-ttu-id="37ac2-116">Zone nur für Länder oder Regionen</span><span class="sxs-lookup"><span data-stu-id="37ac2-116">Zone A countries or regions only</span></span> </br><span data-ttu-id="37ac2-117">Nicht zulassen</span><span class="sxs-lookup"><span data-stu-id="37ac2-117">Don't allow</span></span>|
|<span data-ttu-id="37ac2-118">PSTN-Anrufe für Endbenutzer</span><span class="sxs-lookup"><span data-stu-id="37ac2-118">End user PSTN calls</span></span>|<span data-ttu-id="37ac2-119">Schränkt die Art der Anrufe ein</span><span class="sxs-lookup"><span data-stu-id="37ac2-119">Restricts the type of calls</span></span> </br><span data-ttu-id="37ac2-120">, die von einem Benutzer vorgenommen werden können.</span><span class="sxs-lookup"><span data-stu-id="37ac2-120">that can be made by a user.</span></span>|<span data-ttu-id="37ac2-121">International und Domestic (Standard)</span><span class="sxs-lookup"><span data-stu-id="37ac2-121">International and Domestic (default)</span></span></br><span data-ttu-id="37ac2-122">Inlandsanruf</span><span class="sxs-lookup"><span data-stu-id="37ac2-122">Domestic</span></span></br><span data-ttu-id="37ac2-123">Keine</span><span class="sxs-lookup"><span data-stu-id="37ac2-123">None</span></span>|

<span data-ttu-id="37ac2-124">Informationen dazu, welche Länder/Regionen als Zone a gelten, finden Sie unter [Zone a Countries (Länder/Regionen](https://docs.microsoft.com/microsoftteams/calling-plans-for-office-365)).</span><span class="sxs-lookup"><span data-stu-id="37ac2-124">To find out which countries/regions are considered Zone A, see [Zone A countries/regions](https://docs.microsoft.com/microsoftteams/calling-plans-for-office-365).</span></span>

   > [!NOTE]
   > <span data-ttu-id="37ac2-125">Ein Anruf wird als "Domestic" bezeichnet, wenn sich die gewählte Rufnummer im selben Land befindet, in dem Microsoft 365 oder Office 365 für den Organisator der Besprechung eingerichtet wurde (im Fall von Audiokonferenzen) oder der Endbenutzer (im Fall von PSTN-anrufen des Endbenutzers).</span><span class="sxs-lookup"><span data-stu-id="37ac2-125">A call is considered domestic if the number dialed is in the same country where Microsoft 365 or Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="37ac2-126">Einschränken von ausgehenden Anrufen für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="37ac2-126">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="37ac2-127">![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**</span><span class="sxs-lookup"><span data-stu-id="37ac2-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="37ac2-128">Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="37ac2-128">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="37ac2-129">Klicken Sie oben auf der Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="37ac2-129">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="37ac2-130">Klicken Sie neben **Audiokonferenzen**auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="37ac2-130">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="37ac2-131">Wählen Sie unter " **Wähl Berechtigung für Besprechungen**" die gewünschte Option für die Wahl Beschränkung aus.</span><span class="sxs-lookup"><span data-stu-id="37ac2-131">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="37ac2-132">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="37ac2-132">Click **Save**.</span></span> 

<span data-ttu-id="37ac2-133">![Ein Symbol mit dem Skype for Business-Logo](media/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**</span><span class="sxs-lookup"><span data-stu-id="37ac2-133">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.    <span data-ttu-id="37ac2-134">Wechseln Sie im **Skype for Business Admin Center**im linken Navigationsbereich zu **Audiokonferenz-**  >  **Benutzer**, und wählen Sie den Benutzer in der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="37ac2-134">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.    <span data-ttu-id="37ac2-135">Klicken Sie im Bereich „Aktion" auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="37ac2-135">In the Action pane, click **Edit**.</span></span>

3.    <span data-ttu-id="37ac2-136">Wählen Sie unter **Einschränkungen für Auswahlen in Besprechungen dieses Benutzers**die gewünschte Option für das Auswählen von Einschränkungen aus.</span><span class="sxs-lookup"><span data-stu-id="37ac2-136">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![Die Einschränkungen für Optionen für Auswahlen](media/restrictions-to-dial-outs.png)

5. <span data-ttu-id="37ac2-138">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="37ac2-138">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="37ac2-139">**Verwendung von PowerShell**</span><span class="sxs-lookup"><span data-stu-id="37ac2-139">**Using PowerShell**</span></span>

<span data-ttu-id="37ac2-140">Einschränkungen für ausgehende Anrufe werden durch eine einzelne Richtlinie mit dem Namen OnlineDialOutPolicy gesteuert, die ein Einschränkungs Attribut für jede hat.</span><span class="sxs-lookup"><span data-stu-id="37ac2-140">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="37ac2-141">Die Richtlinie kann nicht angepasst werden, es gibt jedoch vordefinierte Richtlinieninstanzen für jede Kombination der Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="37ac2-141">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="37ac2-142">Sie können das Cmdlet Get-CSOnlineDialOutPolicy verwenden, um die ausgehenden Anruf Richtlinien anzuzeigen und Sie Benutzern mithilfe des Cmdlets Grant-CSDialOutPolicy zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="37ac2-142">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="37ac2-143">(Bitte beachten Sie, dass das Grant-Cmdlet das Wort "Online" nicht enthält, wie es das Get-Cmdlet tut.)</span><span class="sxs-lookup"><span data-stu-id="37ac2-143">(Please note that the Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span> 

<span data-ttu-id="37ac2-144">Die folgende Tabelle enthält eine Übersicht über die einzelnen Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="37ac2-144">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="37ac2-145">Identity = ' Tag: DialoutCPCandPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="37ac2-145">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="37ac2-146">Der Benutzer in der Konferenz kann sich in Auslands-und Inlands Nummern einwählen, und dieser Nutzer kann auch ausgehende Anrufe an Auslands-und Inlands Nummern tätigen.</span><span class="sxs-lookup"><span data-stu-id="37ac2-146">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="37ac2-147">Identity = ' Tag: DialoutCPCDomesticPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="37ac2-147">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="37ac2-148">Der Benutzer in der Konferenz kann sich nur an inländische Rufnummern anwählen, und dieser Benutzer kann ausgehende Anrufe an Auslands-und Inlands Nummern tätigen.</span><span class="sxs-lookup"><span data-stu-id="37ac2-148">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="37ac2-149">Identity = ' Tag: DialoutCPCDisabledPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="37ac2-149">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="37ac2-150">Der Benutzer in der Konferenz kann keine Anrufe tätigen. Dieser Nutzer kann ausgehende Anrufe an Auslands-und Inlands Nummern tätigen.</span><span class="sxs-lookup"><span data-stu-id="37ac2-150">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="37ac2-151">Identity = ' Tag: DialoutCPCInternationalPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="37ac2-151">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="37ac2-152">Der Benutzer in der Konferenz kann sich in Auslands-und Inlands Nummern einwählen, und dieser Nutzer kann nur ausgehende Anrufe an eine inländische PSTN-Nummer tätigen.</span><span class="sxs-lookup"><span data-stu-id="37ac2-152">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="37ac2-153">Identity = ' Tag: DialoutCPCInternationalPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="37ac2-153">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="37ac2-154">Der Benutzer in der Konferenz kann sich in Auslands-und Inlands Nummern einwählen, und dieser Nutzer kann außer Notrufnummern keine ausgehenden Anrufe an eine PSTN-Nummer tätigen.</span><span class="sxs-lookup"><span data-stu-id="37ac2-154">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="37ac2-155">Identity = ' Tag: DialoutCPCandPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="37ac2-155">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="37ac2-156">Der Benutzer in der Konferenz kann sich nur an inländische Rufnummern anwählen, und dieser Benutzer kann nur ausgehende Anrufe an inländische PSTN-Nummern tätigen.</span><span class="sxs-lookup"><span data-stu-id="37ac2-156">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="37ac2-157">Identity = ' Tag: DialoutCPCDomesticPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="37ac2-157">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="37ac2-158">Der Benutzer in der Konferenz kann sich nur an inländische Rufnummern anwählen, und dieser Nutzer kann außer Notrufnummern keine ausgehenden Anrufe an eine PSTN-Nummer tätigen.</span><span class="sxs-lookup"><span data-stu-id="37ac2-158">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="37ac2-159">Identity = ' Tag: DialoutCPCDisabledPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="37ac2-159">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="37ac2-160">Der Benutzer in der Konferenz kann keine Anrufe tätigen, und dieser Benutzer kann nur ausgehende Anrufe an inländische PSTN-Nummern tätigen.</span><span class="sxs-lookup"><span data-stu-id="37ac2-160">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="37ac2-161">Identity = ' Tag: DialoutCPCandPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="37ac2-161">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="37ac2-162">Der Benutzer in der Konferenz kann keine Auswahlen vornehmen, und dieser Benutzer kann außer Notrufnummern keine ausgehenden Anrufe an eine PSTN-Nummer tätigen.</span><span class="sxs-lookup"><span data-stu-id="37ac2-162">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="37ac2-163">Identity = ' Tag: DialoutCPCZoneAPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="37ac2-163">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="37ac2-164">Der Benutzer in der Konferenz kann nur in die Zone A Länder und Regionen wählen, und dieser Benutzer kann ausgehende Anrufe an Auslands-und Inlands Nummern tätigen.</span><span class="sxs-lookup"><span data-stu-id="37ac2-164">User in the conference can only dial out to Zone A countries and regions, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="37ac2-165">Identity = ' Tag: DialoutCPCZoneAPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="37ac2-165">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="37ac2-166">Der Benutzer in der Konferenz kann nur in die Zone A Countries (Länder und Regionen) wählen, und dieser Benutzer kann nur ausgehende Anrufe an eine inländische PSTN-Nummer tätigen.</span><span class="sxs-lookup"><span data-stu-id="37ac2-166">User in the conference can only dial out to Zone A countries and regions, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="37ac2-167">Identity = ' Tag: DialoutCPCZoneAPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="37ac2-167">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="37ac2-168">Der Benutzer in der Konferenz kann sich nur in die Zone A Countries (Länder) und Regionen einwählen, und dieser Nutzer kann nicht außer Notrufnummern ausgehende Anrufe an eine PSTN-Nummer tätigen.</span><span class="sxs-lookup"><span data-stu-id="37ac2-168">User in the conference can only dial out to Zone A countries and regions, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
