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
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Administratoren können den Typ von Audiokonferenz-und Endbenutzer-PSTN-anrufen steuern, die von Benutzern vorgenommen werden können.
ms.openlocfilehash: b4dbaf73b34da163c731a0514a90b5a3536427fa
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708821"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="b495d-103">Einschränkungsrichtlinien für ausgehende Anrufe für Audiokonferenzen und PSTN-Anrufe</span><span class="sxs-lookup"><span data-stu-id="b495d-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="b495d-104">Als Administrator können Sie die Steuerelemente für ausgehende Anrufe verwenden, um den Typ der Audiokonferenzen und Endbenutzer-PSTN-Anrufe einzuschränken, die von Benutzern in Ihrer Organisation verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="b495d-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="b495d-105">Steuerelemente für ausgehende Anrufe können auf Benutzerebene angewendet werden und bieten die folgenden zwei Steuerelemente, um die einzelnen ausgehenden Anrufe unabhängig voneinander zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="b495d-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="b495d-106">Standardmäßig sind beide Steuerelemente so eingestellt, dass Auslands-und Inlandsanrufe zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="b495d-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="b495d-107">Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b495d-107">Control</span></span>|<span data-ttu-id="b495d-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b495d-108">Description</span></span>|<span data-ttu-id="b495d-109">Steuerelementoptionen</span><span class="sxs-lookup"><span data-stu-id="b495d-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b495d-110">PSTN-Anrufe für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="b495d-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="b495d-111">Schränkt den ausgehenden Typ ein</span><span class="sxs-lookup"><span data-stu-id="b495d-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="b495d-112">Anrufe, die innerhalb von zulässig sind</span><span class="sxs-lookup"><span data-stu-id="b495d-112">calls that are allowed from within</span></span> </br><span data-ttu-id="b495d-113">Besprechungen, die von einem Benutzer organisiert werden.</span><span class="sxs-lookup"><span data-stu-id="b495d-113">meetings organized by a user.</span></span>|<span data-ttu-id="b495d-114">International und Domestic (Standard)</span><span class="sxs-lookup"><span data-stu-id="b495d-114">International and Domestic (default)</span></span></br><span data-ttu-id="b495d-115">Inlandsanruf</span><span class="sxs-lookup"><span data-stu-id="b495d-115">Domestic</span></span></br><span data-ttu-id="b495d-116">Keine</span><span class="sxs-lookup"><span data-stu-id="b495d-116">None</span></span>|
|<span data-ttu-id="b495d-117">PSTN-Anrufe für Endbenutzer</span><span class="sxs-lookup"><span data-stu-id="b495d-117">End user PSTN calls</span></span>|<span data-ttu-id="b495d-118">Schränkt die Art der Anrufe ein</span><span class="sxs-lookup"><span data-stu-id="b495d-118">Restricts the type of calls</span></span> </br><span data-ttu-id="b495d-119">, die von einem Benutzer vorgenommen werden können.</span><span class="sxs-lookup"><span data-stu-id="b495d-119">that can be made by a user.</span></span>|<span data-ttu-id="b495d-120">International und Domestic (Standard)</span><span class="sxs-lookup"><span data-stu-id="b495d-120">International and Domestic (default)</span></span></br><span data-ttu-id="b495d-121">Inlandsanruf</span><span class="sxs-lookup"><span data-stu-id="b495d-121">Domestic</span></span></br><span data-ttu-id="b495d-122">Keine</span><span class="sxs-lookup"><span data-stu-id="b495d-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="b495d-123">Ein Anruf gilt als "Domestic", wenn sich die gewählte Rufnummer im selben Land befindet, in dem Office 365 für den Organisator der Besprechung eingerichtet wurde (im Fall von Audiokonferenzen) oder der Endbenutzer (im Fall von PSTN-anrufen des Endbenutzers).</span><span class="sxs-lookup"><span data-stu-id="b495d-123">A call is considered domestic if the number dialed is in the same country where Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="b495d-124">Einschränken von ausgehenden Anrufen für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="b495d-124">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="b495d-125">![Ein Symbol, das das Microsoft Teams](media/teams-logo-30x30.png) -Logo **mit dem Microsoft Teams Admin Center** zeigt</span><span class="sxs-lookup"><span data-stu-id="b495d-125">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="b495d-126">Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="b495d-126">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="b495d-127">Klicken Sie oben auf der Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="b495d-127">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="b495d-128">Klicken Sie neben **Audiokonferenzen**auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="b495d-128">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="b495d-129">Wählen Sie unter " **Wähl Berechtigung für Besprechungen**" die gewünschte Option für die Wahl Beschränkung aus.</span><span class="sxs-lookup"><span data-stu-id="b495d-129">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="b495d-130">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="b495d-130">Click **Save**.</span></span> 

<span data-ttu-id="b495d-131">![Ein Symbol mit dem Skype for Business-Logo](media/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**</span><span class="sxs-lookup"><span data-stu-id="b495d-131">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.  <span data-ttu-id="b495d-132">Wechseln Sie im **Skype for Business Admin Center**im linken Navigationsbereich zu **Audiokonferenz** > -**Benutzer**, und wählen Sie den Benutzer in der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="b495d-132">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.  <span data-ttu-id="b495d-133">Klicken Sie im Bereich „Aktion" auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="b495d-133">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="b495d-134">Wählen Sie unter **Einschränkungen für Auswahlen in Besprechungen dieses Benutzers**die gewünschte Option für das Auswählen von Einschränkungen aus.</span><span class="sxs-lookup"><span data-stu-id="b495d-134">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![Die Einschränkungen für Optionen für Auswahlen](media/restrictions-to-dial-outs.png)

5. <span data-ttu-id="b495d-136">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="b495d-136">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="b495d-137">**Verwenden von PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b495d-137">**Using PowerShell**</span></span>

<span data-ttu-id="b495d-138">Einschränkungen für ausgehende Anrufe werden durch eine einzelne Richtlinie mit dem Namen OnlineDialOutPolicy gesteuert, die ein Einschränkungs Attribut für jede hat.</span><span class="sxs-lookup"><span data-stu-id="b495d-138">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="b495d-139">Die Richtlinie kann nicht angepasst werden, es gibt jedoch vordefinierte Richtlinieninstanzen für jede Kombination der Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="b495d-139">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="b495d-140">Sie können das Cmdlet Get-CSOnlineDialOutPolicy verwenden, um die ausgehenden Anruf Richtlinien anzuzeigen und Sie Benutzern mithilfe des Cmdlets Grant-CSDialOutPolicy zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="b495d-140">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="b495d-141">(Bitte beachten Sie, dass das Grant-Cmdlet das Wort "Online" nicht enthält, wie es das Get-Cmdlet tut.)</span><span class="sxs-lookup"><span data-stu-id="b495d-141">(Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="b495d-142">Die folgende Tabelle enthält eine Übersicht über die einzelnen Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="b495d-142">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b495d-143">Identity = ' Tag: DialoutCPCandPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="b495d-143">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="b495d-144">Der Benutzer in der Konferenz kann sich in Auslands-und Inlands Nummern einwählen, und dieser Nutzer kann auch ausgehende Anrufe an Auslands-und Inlands Nummern tätigen.</span><span class="sxs-lookup"><span data-stu-id="b495d-144">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="b495d-145">Identity = ' Tag: DialoutCPCDomesticPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="b495d-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="b495d-146">Der Benutzer in der Konferenz kann sich nur an inländische Rufnummern anwählen, und dieser Benutzer kann ausgehende Anrufe an Auslands-und Inlands Nummern tätigen.</span><span class="sxs-lookup"><span data-stu-id="b495d-146">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="b495d-147">Identity = ' Tag: DialoutCPCDisabledPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="b495d-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="b495d-148">Der Benutzer in der Konferenz kann keine Anrufe tätigen. Dieser Nutzer kann ausgehende Anrufe an Auslands-und Inlands Nummern tätigen.</span><span class="sxs-lookup"><span data-stu-id="b495d-148">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="b495d-149">Identity = ' Tag: DialoutCPCInternationalPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="b495d-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="b495d-150">Der Benutzer in der Konferenz kann sich in Auslands-und Inlands Nummern einwählen, und dieser Nutzer kann nur ausgehende Anrufe an eine inländische PSTN-Nummer tätigen.</span><span class="sxs-lookup"><span data-stu-id="b495d-150">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="b495d-151">Identity = ' Tag: DialoutCPCInternationalPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="b495d-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="b495d-152">Der Benutzer in der Konferenz kann sich in Auslands-und Inlands Nummern einwählen, und dieser Nutzer kann außer Notrufnummern keine ausgehenden Anrufe an eine PSTN-Nummer tätigen.</span><span class="sxs-lookup"><span data-stu-id="b495d-152">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="b495d-153">Identity = ' Tag: DialoutCPCandPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="b495d-153">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="b495d-154">Der Benutzer in der Konferenz kann sich nur an inländische Rufnummern anwählen, und dieser Benutzer kann nur ausgehende Anrufe an inländische PSTN-Nummern tätigen.</span><span class="sxs-lookup"><span data-stu-id="b495d-154">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="b495d-155">Identity = ' Tag: DialoutCPCDomesticPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="b495d-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="b495d-156">Der Benutzer in der Konferenz kann sich nur an inländische Rufnummern anwählen, und dieser Nutzer kann außer Notrufnummern keine ausgehenden Anrufe an eine PSTN-Nummer tätigen.</span><span class="sxs-lookup"><span data-stu-id="b495d-156">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="b495d-157">Identity = ' Tag: DialoutCPCDisabledPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="b495d-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="b495d-158">Der Benutzer in der Konferenz kann keine Anrufe tätigen, und dieser Benutzer kann nur ausgehende Anrufe an inländische PSTN-Nummern tätigen.</span><span class="sxs-lookup"><span data-stu-id="b495d-158">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="b495d-159">Identity = ' Tag: DialoutCPCandPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="b495d-159">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="b495d-160">Der Benutzer in der Konferenz kann keine Auswahlen vornehmen, und dieser Benutzer kann außer Notrufnummern keine ausgehenden Anrufe an eine PSTN-Nummer tätigen.</span><span class="sxs-lookup"><span data-stu-id="b495d-160">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
