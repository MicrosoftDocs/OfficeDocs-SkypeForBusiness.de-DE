---
title: Anwesenheit in Microsoft Teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Informationen, die Administratoren benötigen, um Anwesenheit in Teams zu verstehen.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b3c36f0f83937e72ae4477ad38c9bd3187c6577
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244827"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="66b8c-103">Anwesenheit in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66b8c-103">User Presence in Teams</span></span>

<span data-ttu-id="66b8c-104">Anwesenheit ist Teil des Benutzerprofils in Microsoft Teams (und innerhalb von Office 365). Sie zeigt anderen Benutzern in der Organisation die gegenwärtige Verfügbarkeit und den Status des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="66b8c-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) – and indicates the user’s current availability and status to other users in the organization.</span></span> <span data-ttu-id="66b8c-105">Standardmäßig kann jeder Mitarbeiter in Ihrer Organisation, der Teams verwendet, in beinahe in Echtzeit sehen, ob andere Benutzer online gerade verfügbar sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="66b8c-105">By default, anyone in your organization using Teams can see – in nearly real time – whether or not other users are available online.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="66b8c-106">Anwesenheitsstatus in Teams</span><span class="sxs-lookup"><span data-stu-id="66b8c-106">User Presence in Teams</span></span>

<span data-ttu-id="66b8c-107">Die Anwesenheitsstatus in Team sind:</span><span class="sxs-lookup"><span data-stu-id="66b8c-107">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="66b8c-108">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="66b8c-108">User configured</span></span>|<span data-ttu-id="66b8c-109">Durch die App konfiguriert</span><span class="sxs-lookup"><span data-stu-id="66b8c-109">App configured</span></span>|
|:--- |:---|
| ![Ein gefülltes grünes Häkchen zeigt an: verfügbar](media/Presence_Available.png) <span data-ttu-id="66b8c-111">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="66b8c-111">Available</span></span>|![Ein gefülltes grünes Häkchen zeigt an: verfügbar](media/Presence_Available.png) <span data-ttu-id="66b8c-113">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="66b8c-113">Available</span></span>|
|| ![Ein nicht gefülltes grünes Häckchen zeigt an: verfügbar – abwesend](media/Presence_Available_OOF.png) <span data-ttu-id="66b8c-115">Verfügbar – außer Haus</span><span class="sxs-lookup"><span data-stu-id="66b8c-115">Available, Out of Office</span></span> |
|  ![Ein gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy.png) <span data-ttu-id="66b8c-117">Beschäftigt</span><span class="sxs-lookup"><span data-stu-id="66b8c-117">Busy Here.</span></span> |  ![Ein gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy.png) <span data-ttu-id="66b8c-119">Beschäftigt</span><span class="sxs-lookup"><span data-stu-id="66b8c-119">Busy Here.</span></span>  |
|| ![Ein gefüllter roter Kreis zeigt an: beschäftigt – in einem Gespräch](media/Presence_Busy.png) <span data-ttu-id="66b8c-121">Am Telefon</span><span class="sxs-lookup"><span data-stu-id="66b8c-121">In a call</span></span>|
|| ![Ein gefüllter roter Kreis zeigt an: beschäftigt – in einer Besprechung](media/Presence_Busy.png) <span data-ttu-id="66b8c-123">In einer Besprechung</span><span class="sxs-lookup"><span data-stu-id="66b8c-123">In a meeting</span></span> |
|| ![Ein offener roter Kreis zeigt an: beschäftigt – abwesend](media/Presence_Busy_OOF.png) <span data-ttu-id="66b8c-125">Am Telefon – abwesend</span><span class="sxs-lookup"><span data-stu-id="66b8c-125">In a call, out of office</span></span>|
|  ![Ein roter Kreis mit weißer Linie zeigt an: nicht stören](media/Presence_DND.png) <span data-ttu-id="66b8c-127">Nicht stören</span><span class="sxs-lookup"><span data-stu-id="66b8c-127">Do not disturb</span></span> ||
|| ![Ein roter Kreis mit weißer Linie zeigt an: hält Präsentation](media/Presence_DND.png) <span data-ttu-id="66b8c-129">Hält Präsentation</span><span class="sxs-lookup"><span data-stu-id="66b8c-129">Presenting</span></span>|
| ![Das Symbol "gelbe Uhr" zeigt an: abwesend](media/Presence_Away.png) <span data-ttu-id="66b8c-131">Abwesend</span><span class="sxs-lookup"><span data-stu-id="66b8c-131">Away</span></span>| ![Das Symbol "gelbe Uhr" zeigt an: abwesend](media/Presence_Away.png) <span data-ttu-id="66b8c-133">Abwesend</span><span class="sxs-lookup"><span data-stu-id="66b8c-133">Away</span></span>|
|| <span data-ttu-id="66b8c-134">![Das Symbol "gelbe Uhr" zeigt an](media/Presence_Away.png): abwesend; zuletzt anwesend um *Zeit*</span><span class="sxs-lookup"><span data-stu-id="66b8c-134">![Yellow clock icon, indicating away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Das Symbol „gelbe Uhr“ zeigt an: abwesend – bin gleich zurück](media/Presence_Away.png) <span data-ttu-id="66b8c-136">Bin gleich zurück</span><span class="sxs-lookup"><span data-stu-id="66b8c-136">Be right back</span></span>| |
|| ![Das Symbol "gelbe Uhr" zeigt an: abwesend – nicht bei der Arbeit](media/Presence_Away.png)  <span data-ttu-id="66b8c-138">Nicht bei der Arbeit</span><span class="sxs-lookup"><span data-stu-id="66b8c-138">Off Work</span></span>|
|| ![Grauer Kreis mit x zeigt an: Offline](media/Presence_Offline.png) <span data-ttu-id="66b8c-140">Offline</span><span class="sxs-lookup"><span data-stu-id="66b8c-140">Offline</span></span> |
|| ![Offener grauer Kreis zeig an: Status unbekannt](media/Presence_Unknown.png) <span data-ttu-id="66b8c-142">Status unbekannt</span><span class="sxs-lookup"><span data-stu-id="66b8c-142">Status unknown</span></span>|
||![Offener roter Kreis mit diagonaler Linie zeig an: gesperrt](media/Presence_Blocked.png) <span data-ttu-id="66b8c-144">Geblockt</span><span class="sxs-lookup"><span data-stu-id="66b8c-144">Blocked</span></span> |
|| ![Lila Kreis mit Pfeil zeigt an: außer Haus](media/Presence_OOF.png) <span data-ttu-id="66b8c-146">Außer Haus</span><span class="sxs-lookup"><span data-stu-id="66b8c-146">Out of Office</span></span>|
|||
 
<span data-ttu-id="66b8c-147">Benutzer haben verschiedene Möglichkeiten, Ihren aktuellen Anwesenheitsstatus festzulegen, und ihr Status wird für alle anderen Benutzer sichtbar.</span><span class="sxs-lookup"><span data-stu-id="66b8c-147">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="66b8c-148">Weitere Details zum Anwesenheitsstatus eines Benutzers werden basierend auf Benutzeraktivitäten (z. b. "verfügbar" oder "abwesend"), dem Outlook-Kalenderstatus (z. b. in einer Besprechung) oder dem Teams-App-Status (in einem Aufruf, hält Präsentation) aktualisiert, die in der Liste aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="66b8c-148">Additional user presence details are also automatically updated based on user activity (such as Available or Away), Outlook calendar states (such as In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="66b8c-149">Es gibt ein Inaktivitätszeitlimit von 15 Minuten. Danach wird der aktuelle Anwesenheitsstatus des Benutzers auf „abwesend“ zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="66b8c-149">There is a 15 minute inactivity timeout, after which your users' current presence state will be reset to Away.</span></span>

<span data-ttu-id="66b8c-150">Benutzer können festlegen, wer sie unterbrechen darf, d. h. sie trotz der „Nicht stören“-Einstellung kontaktieren kann.</span><span class="sxs-lookup"><span data-stu-id="66b8c-150">Users can specify who can break through (contact them overriding a Do Not Disturb setting).</span></span> <span data-ttu-id="66b8c-151">Diese Einstellungen stehen In-App zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="66b8c-151">These settings are available in-app.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="66b8c-152">Administratoreinstellungen in Teams im Vergleich zu Skype for Business</span><span class="sxs-lookup"><span data-stu-id="66b8c-152">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="66b8c-153">Die folgenden Administratoreinstellungen in Skype for Business unterscheiden sich in Teams:</span><span class="sxs-lookup"><span data-stu-id="66b8c-153">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="66b8c-154">In Teams ist die Freigabe des Anwesenheitsstatus für Benutzer in der Organisation immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="66b8c-154">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="66b8c-155">Datenschutz (d. h. die Entscheidung, wer den Anwesenheitsstatus sehen kann) ist in Teams nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="66b8c-155">Privacy (deciding who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="66b8c-156">Die Freigabe des Anwesenheitsstatus für jeden (einschließlich Verbunddienste) ist für Benutzer in Teams immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="66b8c-156">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="66b8c-157">Die Kontaktliste der Benutzer (sofern sie in Skype for Business eine hatten) wird unter **Chat > Kontakte** oder unter **Anrufe > Kontakte** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="66b8c-157">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="66b8c-158">Die Features „Nicht stören“ und „Unterbrechen“ sind für Benutzer in Teams immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="66b8c-158">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="66b8c-159">Die Kalenderintegration (einschließlich Abwesenheits- und andere Kalenderinformationen) ist für Benutzer in Teams, die in Outlook integriert sind, immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="66b8c-159">Calendar (includes out of office and other calendar information) integration  is always enabled for users in Teams if integrated with Outlook.</span></span>
- <span data-ttu-id="66b8c-160">Die Anzeige *zuletzt anwesend* oder *abwesend seit* (in einem dualen Umfeld mit Skype for Business) ist für Benutzer in Teams immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="66b8c-160">The *Last seen* or *Away since* (if in a dual environment with Skype for Business) indicator is always enabled for users in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="66b8c-161">Die Möglichkeit diese Einstellungen durch den Teams-Administrator anzupassen, wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="66b8c-161">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="66b8c-162">Koexistenz mit Skype for Business</span><span class="sxs-lookup"><span data-stu-id="66b8c-162">Coexistence with Skype for Business</span></span>

<span data-ttu-id="66b8c-163">Erfahren Sie unter [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md) mehr über die Anwesenheitsfunktionen im Rahmen einer Koexistenz mit Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="66b8c-163">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when coexisting with Skype for Business.</span></span> 
