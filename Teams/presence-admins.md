---
title: Anwesenheit in Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Informationen für Administratoren zur Anwesenheit in Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: ab24c6ee27f3e99a30a18af82f0a26196a049528
ms.sourcegitcommit: 477aac9e14fced139ee7dd827942ce35b9769b63
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2020
ms.locfileid: "43510774"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="0bbbe-103">Anwesenheit in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0bbbe-103">User presence in Teams</span></span>

<span data-ttu-id="0bbbe-104">Anwesenheit ist Teil des Profils eines Benutzers in Microsoft Teams (und in Office 365), das die aktuelle Verfügbarkeit und den Status des Benutzers für andere Benutzer angibt.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-104">Presence is part of a user's profile in Microsoft Teams (and throughout Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="0bbbe-105">Standardmäßig kann jeder Mitarbeiter in Ihrer Organisation, der Teams verwendet, (nahezu in Echtzeit) sehen, ob andere Benutzer online gerade verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

<span data-ttu-id="0bbbe-106">Die Anwesenheit in Teams wird in Outlook ab der Outlook 2013-Desktop-App und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-106">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="0bbbe-107">Anwesenheitsstatus in Teams</span><span class="sxs-lookup"><span data-stu-id="0bbbe-107">Presence states in Teams</span></span>

|<span data-ttu-id="0bbbe-108">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="0bbbe-108">User configured</span></span>|<span data-ttu-id="0bbbe-109">Durch die App konfiguriert</span><span class="sxs-lookup"><span data-stu-id="0bbbe-109">App configured</span></span>|
|:--- |:---|
| ![Ein gefülltes grünes Häkchen zeigt an: verfügbar](media/Presence_Available.png) <span data-ttu-id="0bbbe-111">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="0bbbe-111">Available</span></span>|![Ein gefülltes grünes Häkchen zeigt an: verfügbar](media/Presence_Available.png) <span data-ttu-id="0bbbe-113">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="0bbbe-113">Available</span></span>|
|| ![Ein nicht gefülltes grünes Häkchen zeigt an: verfügbar – außer Haus](media/Presence_Available_OOF.png) <span data-ttu-id="0bbbe-115">Verfügbar – außer Haus</span><span class="sxs-lookup"><span data-stu-id="0bbbe-115">Available, Out of Office</span></span> |
|  ![Ein gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy.png) <span data-ttu-id="0bbbe-117">Beschäftigt</span><span class="sxs-lookup"><span data-stu-id="0bbbe-117">Busy</span></span> |  ![Ein gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy.png) <span data-ttu-id="0bbbe-119">Beschäftigt</span><span class="sxs-lookup"><span data-stu-id="0bbbe-119">Busy</span></span>  |
|| ![Ein gefüllter roter Kreis zeigt an: beschäftigt – am Telefon](media/Presence_Busy.png) <span data-ttu-id="0bbbe-121">Am Telefon</span><span class="sxs-lookup"><span data-stu-id="0bbbe-121">On a call</span></span>|
|| ![Ein gefüllter roter Kreis zeigt an: beschäftigt – in einer Besprechung](media/Presence_Busy.png) <span data-ttu-id="0bbbe-123">In einer Besprechung</span><span class="sxs-lookup"><span data-stu-id="0bbbe-123">In a meeting</span></span> |
|| ![Ein nicht gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy_OOF.png) <span data-ttu-id="0bbbe-125">Am Telefon – abwesend</span><span class="sxs-lookup"><span data-stu-id="0bbbe-125">On a call, out of office</span></span>|
|  ![Ein roter Kreis mit weißer Linie zeigt an: nicht stören](media/Presence_DND.png) <span data-ttu-id="0bbbe-127">Nicht stören</span><span class="sxs-lookup"><span data-stu-id="0bbbe-127">Do not disturb</span></span> ||
|| ![Ein roter Kreis mit weißer Linie zeigt an: hält Präsentation](media/Presence_DND.png) <span data-ttu-id="0bbbe-129">Hält Präsentation</span><span class="sxs-lookup"><span data-stu-id="0bbbe-129">Presenting</span></span>|
|| ![Ein roter Kreis mit weißer Linie zeigt an: fokussierend](media/Presence_DND.png) <span data-ttu-id="0bbbe-131">Fokussierend</span><span class="sxs-lookup"><span data-stu-id="0bbbe-131">Focusing</span></span>|
| ![Das Symbol "gelbe Uhr" zeigt an: abwesend](media/Presence_Away.png) <span data-ttu-id="0bbbe-133">Abwesend</span><span class="sxs-lookup"><span data-stu-id="0bbbe-133">Away</span></span>| ![Das Symbol "gelbe Uhr" zeigt an: abwesend](media/Presence_Away.png) <span data-ttu-id="0bbbe-135">Abwesend</span><span class="sxs-lookup"><span data-stu-id="0bbbe-135">Away</span></span>|
|| <span data-ttu-id="0bbbe-136">![Das Symbol "gelbe Uhr" zeigt an](media/Presence_Away.png): abwesend; zuletzt anwesend um *Zeit*</span><span class="sxs-lookup"><span data-stu-id="0bbbe-136">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Das Symbol "gelbe Uhr" zeigt an: abwesend – bin gleich zurück](media/Presence_Away.png) <span data-ttu-id="0bbbe-138">Bin gleich zurück</span><span class="sxs-lookup"><span data-stu-id="0bbbe-138">Be right back</span></span>| |
|| ![Das Symbol "gelbe Uhr" zeigt an: abwesend – nicht bei der Arbeit](media/Presence_Away.png)  <span data-ttu-id="0bbbe-140">Nicht bei der Arbeit</span><span class="sxs-lookup"><span data-stu-id="0bbbe-140">Off Work</span></span>|
|| ![Grauer Kreis mit x zeigt an: Offline](media/Presence_Offline.png) <span data-ttu-id="0bbbe-142">Offline</span><span class="sxs-lookup"><span data-stu-id="0bbbe-142">Offline</span></span> |
|| ![Offener grauer Kreis zeig an: Status unbekannt](media/Presence_Unknown.png) <span data-ttu-id="0bbbe-144">Status unbekannt</span><span class="sxs-lookup"><span data-stu-id="0bbbe-144">Status unknown</span></span>|
||![Nicht gefüllter roter Kreis mit diagonaler Linie zeig an: gesperrt](media/Presence_Blocked.png) <span data-ttu-id="0bbbe-146">Gesperrt</span><span class="sxs-lookup"><span data-stu-id="0bbbe-146">Blocked</span></span> |
|| ![Lila Kreis mit Pfeil zeigt an: außer Haus](media/Presence_OOF.png) <span data-ttu-id="0bbbe-148">Außer Haus</span><span class="sxs-lookup"><span data-stu-id="0bbbe-148">Out of Office</span></span>|
|||

<span data-ttu-id="0bbbe-149">App-konfigurierte Anwesenheitsstatus basieren auf Benutzeraktivitäten (verfügbar, abwesend), Outlook-Kalenderstatus (in einer Besprechung) oder in Teams-App-Zuständen (in einem Anruf, Präsentation).</span><span class="sxs-lookup"><span data-stu-id="0bbbe-149">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span>

<span data-ttu-id="0bbbe-150">Ihr aktueller Anwesenheitsstatus wird in "Abwesend" geändert, wenn Sie Ihren Computer sperren oder wenn er in den Leerlauf-oder Ruhemodus wechselt.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-150">Your current presence state changes to Away when you lock your computer or when it enters idle or sleep mode.</span></span> <span data-ttu-id="0bbbe-151">Auf mobilen Geräten wechselt Ihr Anwesenheitsstatus in abwesend, wenn sich die Teams-App im Hintergrund befindet.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-151">On mobile, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="0bbbe-152">Die Benutzer erhalten alle an sie in Microsoft Teams gesendeten Chatnachrichten, unabhängig von ihrem Anwesenheitsstatus.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-152">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="0bbbe-153">Wenn ein Benutzer offline ist, wenn jemand ihm eine Nachricht sendet, wird die Chatnachricht in Microsoft Teams angezeigt, wenn der Benutzer das nächste Mal online ist.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-153">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="0bbbe-154">Wenn sich ein Benutzer in "nicht stören" befindet, erhält der Benutzer weiterhin Chatnachrichten, aber Banner Benachrichtigungen werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-154">If a user is in Do not disturb, the user will still get chat messages but banner notifications aren't displayed.</span></span>

<span data-ttu-id="0bbbe-155">Benutzer erhalten Anrufe in allen Anwesenheitsstatus mit Ausnahme von "nicht stören", in dem eingehende Anrufe an Voicemail weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-155">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="0bbbe-156">Wenn der Empfänger den Anrufer blockiert hat, wird der Anruf nicht übermittelt, und dem Anrufer wird als Anwesenheitsstatus des Empfängers "Offline" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-156">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="0bbbe-157">Benutzer können ihrer Vorrangliste Personen hinzufügen, indem sie in Microsoft Teams zu **Einstellungen** > **Privatsphäre** wechseln.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-157">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="0bbbe-158">Personen mit Prioritätszugriff können sich an den Benutzer wenden, selbst wenn sich der Benutzer in "nicht stören" befindet.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-158">People who have priority access can contact the user even when the user is in Do not disturb.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="0bbbe-159">Administratoreinstellungen in Teams im Vergleich zu Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0bbbe-159">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="0bbbe-160">Die folgenden Administratoreinstellungen in Skype for Business unterscheiden sich in Teams:</span><span class="sxs-lookup"><span data-stu-id="0bbbe-160">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="0bbbe-161">In Microsoft Teams ist die Freigabe des Anwesenheitsstatus für Benutzer in der Organisation immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-161">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="0bbbe-162">Einstellungen zur Privatsphäre (d. h. das Definieren, wer den Anwesenheitsstatus sehen kann) sind in Teams nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-162">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="0bbbe-163">Die Freigabe des Anwesenheitsstatus für jeden (einschließlich Verbunddienste) ist für Benutzer in Microsoft Teams immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-163">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="0bbbe-164">Die Kontaktliste der Benutzer (sofern sie in Skype for Business eine hatten) wird unter **Chat > Kontakte** oder unter **Anrufe > Kontakte** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-164">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="0bbbe-165">Die Features "Nicht stören" und "Unterbrechen" sind für Benutzer in Teams immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-165">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="0bbbe-166">Die Kalenderintegration (einschließlich Abwesenheits- und andere Kalenderinformationen) ist für Benutzer in Teams, die in Outlook integriert sind, immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-166">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="0bbbe-167">Die Anzeige *zuletzt anwesend* oder *abwesend seit* ist für Benutzer in Teams immer aktiviert, wenn die Organisation außerdem Skype for Business verwendet.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-167">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="0bbbe-168">Die Möglichkeit, diese Einstellungen durch den Teams-Administrator anzupassen, wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-168">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="0bbbe-169">Koexistenz mit Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0bbbe-169">Coexistence with Skype for Business</span></span>

<span data-ttu-id="0bbbe-170">Erfahren Sie unter [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md) mehr über die Anwesenheitsfunktionen, wenn Ihre Organisation außerdem Skype for Business verwendet.</span><span class="sxs-lookup"><span data-stu-id="0bbbe-170">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
