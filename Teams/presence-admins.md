---
title: Anwesenheit in Teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rakayala
description: Informations Administratoren müssen sich mit der Anwesenheit in Teams vertraut machen.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3fd6ac289df238d9f410266b1eca43a3a18f493e
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548525"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="f5b58-103">Anwesenheit in Teams</span><span class="sxs-lookup"><span data-stu-id="f5b58-103">User Presence in Teams</span></span>

<span data-ttu-id="f5b58-104">Anwesenheit ist Teil des Profils eines Benutzers in Microsoft Teams (und in Office 365) – und zeigt die aktuelle Verfügbarkeit und den Status des Benutzers an, die anderen Benutzern in der Organisation zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="f5b58-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) – and indicates the user’s current availability and status to other users in the organization.</span></span> <span data-ttu-id="f5b58-105">Standardmäßig können alle Personen in Ihrer Organisation, die Teams verwenden, in nahezu Echtzeit sehen, ob andere Benutzer online verfügbar sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="f5b58-105">By default, anyone in your organization using Teams can see - in nearly real time - whether or not other users are available online.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="f5b58-106">Anwesenheitsstatus in Teams</span><span class="sxs-lookup"><span data-stu-id="f5b58-106">Presence states in Teams</span></span>

<span data-ttu-id="f5b58-107">Die in Teams verfügbaren Benutzer Anwesenheitsstatus sind:</span><span class="sxs-lookup"><span data-stu-id="f5b58-107">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="f5b58-108">Benutzer konfiguriert</span><span class="sxs-lookup"><span data-stu-id="f5b58-108">User configured</span></span>|<span data-ttu-id="f5b58-109">App konfiguriert</span><span class="sxs-lookup"><span data-stu-id="f5b58-109">App configured</span></span>|
|:--- |:---|
| ![Vollständiges grünes Chek-Zeichen mit verfügbarem Anwesenheitsstatus](media/Presence_Available.png) <span data-ttu-id="f5b58-111">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="f5b58-111">Available</span></span>|![Vollständiges grünes Chek-Zeichen mit verfügbarem Anwesenheitsstatus](media/Presence_Available.png) <span data-ttu-id="f5b58-113">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="f5b58-113">Available</span></span>|
|| ![Open Green Chek Mark, der angibt, dass OOF verfügbar ist](media/Presence_Available_OOF.png) <span data-ttu-id="f5b58-115">Verfügbar, außer Haus</span><span class="sxs-lookup"><span data-stu-id="f5b58-115">Available, Out of Office</span></span> |
|  ![Vollständiger roter Kreis mit Anzeige von "beschäftigt"](media/Presence_Busy.png) <span data-ttu-id="f5b58-117">Beschäftigt</span><span class="sxs-lookup"><span data-stu-id="f5b58-117">Busy</span></span> |  ![Beschäftigt](media/Presence_Busy.png) <span data-ttu-id="f5b58-119">Beschäftigt</span><span class="sxs-lookup"><span data-stu-id="f5b58-119">Busy</span></span>  |
|| ![Vollständiger roter Kreis mit Anzeige von beschäftigt in einem Anruf](media/Presence_Busy.png) <span data-ttu-id="f5b58-121">In einem Anruf</span><span class="sxs-lookup"><span data-stu-id="f5b58-121">In a call</span></span>|
|| ![Vollständiger roter Kreis, der angibt, dass in einer Besprechung beschäftigt ist](media/Presence_Busy.png) <span data-ttu-id="f5b58-123">In einer Besprechung</span><span class="sxs-lookup"><span data-stu-id="f5b58-123">In a meeting</span></span> |
|| ![Roter Kreis öffnen, der auf busy OOF hinweist](media/Presence_Busy_OOF.png) <span data-ttu-id="f5b58-125">In einem Anruf: Abwesenheit</span><span class="sxs-lookup"><span data-stu-id="f5b58-125">In a call, out of office</span></span>|
|  ![Roter Kreis mit weißer Zeile, Anzeige "nicht stören"](media/Presence_DND.png) <span data-ttu-id="f5b58-127">Nicht stören</span><span class="sxs-lookup"><span data-stu-id="f5b58-127">Do not disturb</span></span> ||
|| ![Roter Kreis mit weißer Zeile, der die Präsentation angibt](media/Presence_DND.png) <span data-ttu-id="f5b58-129">Präsentieren</span><span class="sxs-lookup"><span data-stu-id="f5b58-129">Presenting</span></span>|
| ![Symbol "gelbe Uhr" mit Anzeige "Abwesend"](media/Presence_Away.png) <span data-ttu-id="f5b58-131">Abwesend</span><span class="sxs-lookup"><span data-stu-id="f5b58-131">Away</span></span>| ![abwesend](media/Presence_Away.png) <span data-ttu-id="f5b58-133">Abwesend</span><span class="sxs-lookup"><span data-stu-id="f5b58-133">Away</span></span>|
|| <span data-ttu-id="f5b58-134">![Symbol "gelbe Uhr", das](media/Presence_Away.png) die letzte Anzeige *Zeit* entfernt</span><span class="sxs-lookup"><span data-stu-id="f5b58-134">![Yellow clock icon, indicating away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Das gelbe Uhr-Symbol, das wegzeigt, ist gleich zurück](media/Presence_Away.png) <span data-ttu-id="f5b58-136">Bin gleich zurück</span><span class="sxs-lookup"><span data-stu-id="f5b58-136">Be right back</span></span>| |
|| ![Symbol "gelbe Uhr" mit Anzeige "Abwesend"](media/Presence_Away.png)  <span data-ttu-id="f5b58-138">Off-Arbeit</span><span class="sxs-lookup"><span data-stu-id="f5b58-138">Off Work</span></span>|
|| ![Grauer Kreis mit x, der Offline angibt](media/Presence_Offline.png) <span data-ttu-id="f5b58-140">Offline</span><span class="sxs-lookup"><span data-stu-id="f5b58-140">Offline</span></span> |
|| ![Grauer Kreis öffnen, Anzeige des Status unbekannt](media/Presence_Unknown.png) <span data-ttu-id="f5b58-142">Status unbekannt</span><span class="sxs-lookup"><span data-stu-id="f5b58-142">Status unknown</span></span>|
||![Öffnen des roten Kreises mit einer Diagonalen Zeile, die auf "blockiert" hinweist](media/Presence_Blocked.png) <span data-ttu-id="f5b58-144">Blockiert</span><span class="sxs-lookup"><span data-stu-id="f5b58-144">Blocked</span></span> |
|| ![Lila Kreis mit Pfeil, der auf Abwesenheit hinweist](media/Presence_OOF.png) <span data-ttu-id="f5b58-146">Abwesenheit</span><span class="sxs-lookup"><span data-stu-id="f5b58-146">Out of Office</span></span>|
|||
 
<span data-ttu-id="f5b58-147">Benutzer können Ihren aktuellen Anwesenheitsstatus manuell auf einige Optionen einstellen, und Ihr Status wird für alle anderen Benutzer wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="f5b58-147">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="f5b58-148">Zusätzliche Benutzeranwesenheitsinformationen werden auch automatisch auf der Grundlage von Benutzeraktivitäten (wie "verfügbar" oder "Abwesend"), von Outlook-Kalenderstatus (wie in einer Besprechung) oder von Teams-App-Zuständen (in einem Aufruf, Präsentation) an Zustände aktualisiert, die in der Liste eingerückt sind.</span><span class="sxs-lookup"><span data-stu-id="f5b58-148">Additional user presence details are also automatically updated based on user activity (such as Available or Away), Outlook calendar states (such as In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="f5b58-149">Es gibt ein 15-minütiges Inaktivitäts-Timeout, nach dem der aktuelle Anwesenheitsstatus Ihrer Benutzer auf "Abwesend" zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="f5b58-149">There is a 15 minute inactivity timeout, after which your users' current presence state will be reset to Away.</span></span>

<span data-ttu-id="f5b58-150">Benutzer können angeben, wer durchbrechen kann (setzen Sie die Einstellung "nicht stören" außer Kraft).</span><span class="sxs-lookup"><span data-stu-id="f5b58-150">Users can specify who can break through (contact them overriding a Do Not Disturb setting).</span></span> <span data-ttu-id="f5b58-151">Diese Einstellungen sind in-app verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f5b58-151">These settings are available in-app.</span></span>

## <a name="teams-is-not-skype-for-business"></a><span data-ttu-id="f5b58-152">Teams ist nicht Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f5b58-152">Teams is not Skype for Business</span></span>

<span data-ttu-id="f5b58-153">Die folgenden Administratoreinstellungen in Skype for Business unterscheiden sich in Teams:</span><span class="sxs-lookup"><span data-stu-id="f5b58-153">The following Admin settings in Skype for Business are different in Teams:</span></span>
- <span data-ttu-id="f5b58-154">Die Anwesenheits Freigabe ist in Teams für Benutzer in der Organisation immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f5b58-154">Presence sharing is always enabled in Teams for users in the organization.</span></span> <span data-ttu-id="f5b58-155">Der Datenschutz (die Entscheidung, wer Anwesenheitsinformationen sehen kann) steht in Teams nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f5b58-155">Privacy (deciding who can see Presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="f5b58-156">Anwesenheits Freigaben für alle (einschließlich der Verbunddienste) sind für Benutzer in Teams immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f5b58-156">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="f5b58-157">Ihre Kontaktliste (sofern Sie eine in SFB hatte) ist unter **Chat >-Kontakte** oder unter **Anrufe >-Kontakte**sichtbar.</span><span class="sxs-lookup"><span data-stu-id="f5b58-157">Their contact list (if they had one in SfB) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="f5b58-158">Der Client stört nicht, und Durchbruch Features sind für Benutzer in Teams immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f5b58-158">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="f5b58-159">Kalender (einschließlich Abwesenheits-& andere Kalenderinformationen) die Integration ist für Benutzer in Microsoft Teams immer aktiviert, wenn Sie in Outlook integriert ist.</span><span class="sxs-lookup"><span data-stu-id="f5b58-159">Calendar (includes OOF & other calendar info) integration  is always enabled for users in Teams if integrated with Outlook.</span></span>
- <span data-ttu-id="f5b58-160">Die *zuletzt* gesehene oder *Abwesenheits* Anzeige (falls in einer dualen Umgebung mit Skype for Business) ist für Benutzer in Teams immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f5b58-160">The *Last seen* or *Away since* (if in a dual environment with Skype for Business) indicator is always enabled for users in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="f5b58-161">Die Fähigkeit eines Teams-Administrators, diese Einstellungen anzupassen, wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f5b58-161">The ability of a Teams Admin to customize these settings is not currently supported.</span></span>


## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="f5b58-162">Koexistenz mit Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f5b58-162">Coexistence with Skype for Business</span></span>

<span data-ttu-id="f5b58-163">Weitere Informationen dazu, wie die Anwesenheit von Teams funktioniert, wenn Sie mit Skype for Business zusammen existieren, finden Sie unter [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md) .</span><span class="sxs-lookup"><span data-stu-id="f5b58-163">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when coexisting with Skype for Business.</span></span> 
