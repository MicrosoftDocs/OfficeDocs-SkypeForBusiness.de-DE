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
ms.openlocfilehash: e085f996226a59d88339b20e64dd06f68ef566ce
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908654"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="81b71-103">Einschränkungsrichtlinien für ausgehende Anrufe für Audiokonferenzen und PSTN-Anrufe</span><span class="sxs-lookup"><span data-stu-id="81b71-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="81b71-104">Als Administrator können Sie die Steuerelemente für ausgehende Anrufe verwenden, um den Typ der Audiokonferenzen und Endbenutzer-PSTN-Anrufe einzuschränken, die von Benutzern in Ihrer Organisation verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="81b71-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="81b71-105">Steuerelemente für ausgehende Anrufe können auf Benutzerebene angewendet werden und bieten die folgenden zwei Steuerelemente, um die einzelnen ausgehenden Anrufe unabhängig voneinander zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="81b71-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="81b71-106">Standardmäßig sind beide Steuerelemente so eingestellt, dass Auslands-und Inlandsanrufe zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="81b71-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="81b71-107">Steuerelement</span><span class="sxs-lookup"><span data-stu-id="81b71-107">Control</span></span>|<span data-ttu-id="81b71-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81b71-108">Description</span></span>|<span data-ttu-id="81b71-109">Steuerelementoptionen</span><span class="sxs-lookup"><span data-stu-id="81b71-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="81b71-110">PSTN-Anrufe für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="81b71-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="81b71-111">Schränkt den ausgehenden Typ ein</span><span class="sxs-lookup"><span data-stu-id="81b71-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="81b71-112">Anrufe, die innerhalb von zulässig sind</span><span class="sxs-lookup"><span data-stu-id="81b71-112">calls that are allowed from within</span></span> </br><span data-ttu-id="81b71-113">Besprechungen, die von einem Benutzer organisiert werden.</span><span class="sxs-lookup"><span data-stu-id="81b71-113">meetings organized by a user.</span></span>|<span data-ttu-id="81b71-114">Beliebiges Ziel (Standard)</span><span class="sxs-lookup"><span data-stu-id="81b71-114">Any destination (default)</span></span></br><span data-ttu-id="81b71-115">Im gleichen Land oder in derselben Region wie der Organisator</span><span class="sxs-lookup"><span data-stu-id="81b71-115">In the same country or region as the organizer</span></span> </br> <span data-ttu-id="81b71-116">[Zone nur für Länder oder Regionen](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="81b71-116">[Zone A countries or regions](audio-conferencing-zones.md) only</span></span> </br><span data-ttu-id="81b71-117">Nicht zulassen</span><span class="sxs-lookup"><span data-stu-id="81b71-117">Don't allow</span></span>|
|<span data-ttu-id="81b71-118">PSTN-Anrufe für Endbenutzer</span><span class="sxs-lookup"><span data-stu-id="81b71-118">End user PSTN calls</span></span>|<span data-ttu-id="81b71-119">Schränkt die Art der Anrufe ein</span><span class="sxs-lookup"><span data-stu-id="81b71-119">Restricts the type of calls</span></span> </br><span data-ttu-id="81b71-120">, die von einem Benutzer vorgenommen werden können.</span><span class="sxs-lookup"><span data-stu-id="81b71-120">that can be made by a user.</span></span>|<span data-ttu-id="81b71-121">International und Domestic (Standard)</span><span class="sxs-lookup"><span data-stu-id="81b71-121">International and Domestic (default)</span></span></br><span data-ttu-id="81b71-122">Inlandsanruf</span><span class="sxs-lookup"><span data-stu-id="81b71-122">Domestic</span></span></br><span data-ttu-id="81b71-123">Keine</span><span class="sxs-lookup"><span data-stu-id="81b71-123">None</span></span>|

<span data-ttu-id="81b71-124">Wenn Sie feststellen möchten, welche Länder und Regionen als Zone A gelten, lesen Sie [Länder-und Regions Zonen für Audiokonferenzen](audio-conferencing-zones.md).</span><span class="sxs-lookup"><span data-stu-id="81b71-124">To find out which countries and regions are considered Zone A, see [Country and region zones for Audio Conferencing](audio-conferencing-zones.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="81b71-125">Ein Anruf wird als "Domestic" bezeichnet, wenn sich die gewählte Rufnummer im selben Land befindet, in dem Microsoft 365 oder Office 365 für den Organisator der Besprechung eingerichtet wurde (im Fall von Audiokonferenzen) oder der Endbenutzer (im Fall von PSTN-anrufen des Endbenutzers).</span><span class="sxs-lookup"><span data-stu-id="81b71-125">A call is considered domestic if the number dialed is in the same country where Microsoft 365 or Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="81b71-126">Einschränken von ausgehenden Anrufen für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="81b71-126">Restrict audio conferencing outbound calls</span></span>

<span data-ttu-id="81b71-127">![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**</span><span class="sxs-lookup"><span data-stu-id="81b71-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="81b71-128">Klicken Sie in der linken Navigationsleiste auf **Benutzer** , und klicken Sie dann in der Liste der verfügbaren Benutzer auf den Anzeigenamen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="81b71-128">In the left navigation, click **Users** , and then click the display name of the user from the list of available users.</span></span>

3. <span data-ttu-id="81b71-129">Klicken Sie neben **Audiokonferenzen** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="81b71-129">Next to **Audio Conferencing** , click **Edit**.</span></span>

4. <span data-ttu-id="81b71-130">Wählen Sie unter **Einwahl von Besprechungen** die gewünschte Option für die Wahl Beschränkung aus.</span><span class="sxs-lookup"><span data-stu-id="81b71-130">Under **Dial-out from meetings** , select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="81b71-131">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="81b71-131">Click **Save**.</span></span> 

<span data-ttu-id="81b71-132">![Ein Symbol mit dem Skype for Business-Logo](media/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**</span><span class="sxs-lookup"><span data-stu-id="81b71-132">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="81b71-133">Wechseln Sie im **Skype for Business Admin Center** im linken Navigationsbereich zu **Audiokonferenz-**  >  **Benutzer** , und wählen Sie den Benutzer in der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="81b71-133">In the **Skype for Business admin center** , in the left navigation, go to **Audio conferencing** > **Users** , and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="81b71-134">Klicken Sie im Bereich „Aktion" auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="81b71-134">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="81b71-135">Wählen Sie unter **Einschränkungen für Auswahlen in Besprechungen dieses Benutzers** die gewünschte Option für das Auswählen von Einschränkungen aus.</span><span class="sxs-lookup"><span data-stu-id="81b71-135">Under **Restrictions to dial-outs from meetings of this user** , select the dial-out restriction option you want.</span></span>

      ![Die Einschränkungen für Optionen für Auswahlen](media/restrictions-to-dial-outs.png)
      

4. <span data-ttu-id="81b71-137">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="81b71-137">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="81b71-138">**Verwendung von PowerShell**</span><span class="sxs-lookup"><span data-stu-id="81b71-138">**Using PowerShell**</span></span>

<span data-ttu-id="81b71-139">Einschränkungen für ausgehende Anrufe werden durch eine einzelne Richtlinie mit dem Namen OnlineDialOutPolicy gesteuert, die ein Einschränkungs Attribut für jede hat.</span><span class="sxs-lookup"><span data-stu-id="81b71-139">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="81b71-140">Die Richtlinie kann nicht angepasst werden, es gibt jedoch vordefinierte Richtlinieninstanzen für jede Kombination der Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="81b71-140">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="81b71-141">Sie können das Get-CSOnlineDialOutPolicy-Cmdlet verwenden, um die ausgehenden Anruf Richtlinien anzuzeigen und Sie Benutzern mithilfe des Grant-CSDialOutPolicy-Cmdlets zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="81b71-141">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="81b71-142">(Bitte beachten Sie, dass das Grant-Cmdlet das Wort "Online" nicht enthält, wie es das Get-Cmdlet tut.)</span><span class="sxs-lookup"><span data-stu-id="81b71-142">(Please note that the Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span> 

<span data-ttu-id="81b71-143">Die folgende Tabelle enthält eine Übersicht über die einzelnen Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="81b71-143">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="81b71-144">Identity = ' Tag: DialoutCPCandPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="81b71-144">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="81b71-145">Der Benutzer in der Konferenz kann sich in Auslands-und Inlands Nummern einwählen, und dieser Nutzer kann auch ausgehende Anrufe an Auslands-und Inlands Nummern tätigen.</span><span class="sxs-lookup"><span data-stu-id="81b71-145">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="81b71-146">Identity = ' Tag: DialoutCPCDomesticPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="81b71-146">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="81b71-147">Der Benutzer in der Konferenz kann sich nur an inländische Rufnummern anwählen, und dieser Benutzer kann ausgehende Anrufe an Auslands-und Inlands Nummern tätigen.</span><span class="sxs-lookup"><span data-stu-id="81b71-147">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="81b71-148">Identity = ' Tag: DialoutCPCDisabledPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="81b71-148">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="81b71-149">Der Benutzer in der Konferenz kann keine Anrufe tätigen. Dieser Nutzer kann ausgehende Anrufe an Auslands-und Inlands Nummern tätigen.</span><span class="sxs-lookup"><span data-stu-id="81b71-149">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="81b71-150">Identity = ' Tag: DialoutCPCInternationalPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="81b71-150">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="81b71-151">Der Benutzer in der Konferenz kann sich in Auslands-und Inlands Nummern einwählen, und dieser Nutzer kann nur ausgehende Anrufe an eine inländische PSTN-Nummer tätigen.</span><span class="sxs-lookup"><span data-stu-id="81b71-151">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="81b71-152">Identity = ' Tag: DialoutCPCInternationalPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="81b71-152">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="81b71-153">Der Benutzer in der Konferenz kann sich in Auslands-und Inlands Nummern einwählen, und dieser Nutzer kann außer Notrufnummern keine ausgehenden Anrufe an eine PSTN-Nummer tätigen.</span><span class="sxs-lookup"><span data-stu-id="81b71-153">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="81b71-154">Identity = ' Tag: DialoutCPCandPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="81b71-154">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="81b71-155">Der Benutzer in der Konferenz kann sich nur an inländische Rufnummern anwählen, und dieser Benutzer kann nur ausgehende Anrufe an inländische PSTN-Nummern tätigen.</span><span class="sxs-lookup"><span data-stu-id="81b71-155">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="81b71-156">Identity = ' Tag: DialoutCPCDomesticPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="81b71-156">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="81b71-157">Der Benutzer in der Konferenz kann sich nur an inländische Rufnummern anwählen, und dieser Nutzer kann außer Notrufnummern keine ausgehenden Anrufe an eine PSTN-Nummer tätigen.</span><span class="sxs-lookup"><span data-stu-id="81b71-157">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="81b71-158">Identity = ' Tag: DialoutCPCDisabledPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="81b71-158">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="81b71-159">Der Benutzer in der Konferenz kann keine Anrufe tätigen, und dieser Benutzer kann nur ausgehende Anrufe an inländische PSTN-Nummern tätigen.</span><span class="sxs-lookup"><span data-stu-id="81b71-159">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="81b71-160">Identity = ' Tag: DialoutCPCandPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="81b71-160">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="81b71-161">Der Benutzer in der Konferenz kann keine Auswahlen vornehmen, und dieser Benutzer kann außer Notrufnummern keine ausgehenden Anrufe an eine PSTN-Nummer tätigen.</span><span class="sxs-lookup"><span data-stu-id="81b71-161">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="81b71-162">Identity = ' Tag: DialoutCPCZoneAPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="81b71-162">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="81b71-163">Der Benutzer in der Konferenz kann nur in die [Zone A Länder und Regionen](audio-conferencing-zones.md)wählen, und dieser Benutzer kann ausgehende Anrufe an Auslands-und Inlands Nummern tätigen.</span><span class="sxs-lookup"><span data-stu-id="81b71-163">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="81b71-164">Identity = ' Tag: DialoutCPCZoneAPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="81b71-164">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="81b71-165">Der Benutzer in der Konferenz kann nur in die [Zone A Countries (Länder und Regionen](audio-conferencing-zones.md)) wählen, und dieser Benutzer kann nur ausgehende Anrufe an eine inländische PSTN-Nummer tätigen.</span><span class="sxs-lookup"><span data-stu-id="81b71-165">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="81b71-166">Identity = ' Tag: DialoutCPCZoneAPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="81b71-166">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="81b71-167">Der Benutzer in der Konferenz kann sich nur in die [Zone A Countries (Länder) und Regionen](audio-conferencing-zones.md)einwählen, und dieser Nutzer kann nicht außer Notrufnummern ausgehende Anrufe an eine PSTN-Nummer tätigen.</span><span class="sxs-lookup"><span data-stu-id="81b71-167">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
