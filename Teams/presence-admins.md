---
title: Anwesenheit in Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Informieren Sie sich über die Anwesenheitsstatus in Teams sowie über die administrativen Einstellungen für das Anwesenheits Feature.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: c31439485f245b522a55c2e5e1134ca6cdddbdf7
ms.sourcegitcommit: b14ad0a6c454b20f34fccbd1d312de24379faef0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "46572350"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="5f444-103">Anwesenheit in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5f444-103">User presence in Teams</span></span>

<span data-ttu-id="5f444-104">Anwesenheit ist Teil des Profils eines Benutzers in Microsoft Teams (und in Microsoft 365 oder Office 365), das die aktuelle Verfügbarkeit und den Status des Benutzers für andere Benutzer angibt.</span><span class="sxs-lookup"><span data-stu-id="5f444-104">Presence is part of a user's profile in Microsoft Teams (and throughout Microsoft 365 or Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="5f444-105">Standardmäßig kann jeder Mitarbeiter in Ihrer Organisation, der Teams verwendet, (nahezu in Echtzeit) sehen, ob andere Benutzer online gerade verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5f444-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

<span data-ttu-id="5f444-106">Die Anwesenheit in Teams wird in Outlook ab der Outlook 2013-Desktop-App und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5f444-106">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="5f444-107">Anwesenheitsstatus in Teams</span><span class="sxs-lookup"><span data-stu-id="5f444-107">Presence states in Teams</span></span>

|<span data-ttu-id="5f444-108">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="5f444-108">User configured</span></span>|<span data-ttu-id="5f444-109">Durch die App konfiguriert</span><span class="sxs-lookup"><span data-stu-id="5f444-109">App configured</span></span>|
|:--- |:---|
| ![Ein gefülltes grünes Häkchen zeigt an: verfügbar](media/Presence_Available.png) <span data-ttu-id="5f444-111">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="5f444-111">Available</span></span>|![Ein gefülltes grünes Häkchen zeigt an: verfügbar](media/Presence_Available.png) <span data-ttu-id="5f444-113">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="5f444-113">Available</span></span>|
|| ![Ein nicht gefülltes grünes Häkchen zeigt an: verfügbar – außer Haus](media/Presence_Available_OOF.png) <span data-ttu-id="5f444-115">Verfügbar – außer Haus</span><span class="sxs-lookup"><span data-stu-id="5f444-115">Available, Out of Office</span></span> |
|  ![Ein gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy.png) <span data-ttu-id="5f444-117">Beschäftigt</span><span class="sxs-lookup"><span data-stu-id="5f444-117">Busy</span></span> |  ![Ein gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy.png) <span data-ttu-id="5f444-119">Beschäftigt</span><span class="sxs-lookup"><span data-stu-id="5f444-119">Busy</span></span>  |
|| ![Ein gefüllter roter Kreis zeigt an: beschäftigt – am Telefon](media/Presence_Busy.png) <span data-ttu-id="5f444-121">Am Telefon</span><span class="sxs-lookup"><span data-stu-id="5f444-121">On a call</span></span>|
|| ![Ein gefüllter roter Kreis zeigt an: beschäftigt – in einer Besprechung](media/Presence_Busy.png) <span data-ttu-id="5f444-123">In einer Besprechung</span><span class="sxs-lookup"><span data-stu-id="5f444-123">In a meeting</span></span> |
|| ![Ein nicht gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy_OOF.png) <span data-ttu-id="5f444-125">Am Telefon – abwesend</span><span class="sxs-lookup"><span data-stu-id="5f444-125">On a call, out of office</span></span>|
|  ![Ein roter Kreis mit weißer Linie zeigt an: nicht stören](media/Presence_DND.png) <span data-ttu-id="5f444-127">Nicht stören</span><span class="sxs-lookup"><span data-stu-id="5f444-127">Do not disturb</span></span> ||
|| ![Ein roter Kreis mit weißer Linie zeigt an: hält Präsentation](media/Presence_DND.png) <span data-ttu-id="5f444-129">Hält Präsentation</span><span class="sxs-lookup"><span data-stu-id="5f444-129">Presenting</span></span>|
|| ![Ein roter Kreis mit weißer Linie zeigt an: fokussierend](media/Presence_DND.png) <span data-ttu-id="5f444-131">Fokussierend</span><span class="sxs-lookup"><span data-stu-id="5f444-131">Focusing</span></span>|
| ![Das Symbol "gelbe Uhr" zeigt an: abwesend](media/Presence_Away.png) <span data-ttu-id="5f444-133">Abwesend</span><span class="sxs-lookup"><span data-stu-id="5f444-133">Away</span></span>| ![Das Symbol "gelbe Uhr" zeigt an: abwesend](media/Presence_Away.png) <span data-ttu-id="5f444-135">Abwesend</span><span class="sxs-lookup"><span data-stu-id="5f444-135">Away</span></span>|
|| <span data-ttu-id="5f444-136">![Das Symbol "gelbe Uhr" zeigt an](media/Presence_Away.png): abwesend; zuletzt anwesend um *Zeit*</span><span class="sxs-lookup"><span data-stu-id="5f444-136">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Das Symbol "gelbe Uhr" zeigt an: abwesend – bin gleich zurück](media/Presence_Away.png) <span data-ttu-id="5f444-138">Bin gleich zurück</span><span class="sxs-lookup"><span data-stu-id="5f444-138">Be right back</span></span>| |
|| ![Das Symbol "gelbe Uhr" zeigt an: abwesend – nicht bei der Arbeit](media/Presence_Away.png)  <span data-ttu-id="5f444-140">Nicht bei der Arbeit</span><span class="sxs-lookup"><span data-stu-id="5f444-140">Off Work</span></span>|
|| ![Grauer Kreis mit x zeigt an: Offline](media/Presence_Offline.png) <span data-ttu-id="5f444-142">Offline</span><span class="sxs-lookup"><span data-stu-id="5f444-142">Offline</span></span> |
|| ![Offener grauer Kreis zeig an: Status unbekannt](media/Presence_Unknown.png) <span data-ttu-id="5f444-144">Status unbekannt</span><span class="sxs-lookup"><span data-stu-id="5f444-144">Status unknown</span></span>|
||![Nicht gefüllter roter Kreis mit diagonaler Linie zeig an: gesperrt](media/Presence_Blocked.png) <span data-ttu-id="5f444-146">Gesperrt</span><span class="sxs-lookup"><span data-stu-id="5f444-146">Blocked</span></span> |
|| ![Lila Kreis mit Pfeil zeigt an: außer Haus](media/Presence_OOF.png) <span data-ttu-id="5f444-148">Außer Haus</span><span class="sxs-lookup"><span data-stu-id="5f444-148">Out of Office</span></span>|
|||

<span data-ttu-id="5f444-149">App-konfigurierte Anwesenheitsstatus basieren auf Benutzeraktivitäten (verfügbar, abwesend), Outlook-Kalenderstatus (in einer Besprechung) oder in Teams-App-Zuständen (in einem Anruf, Präsentation).</span><span class="sxs-lookup"><span data-stu-id="5f444-149">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span> <span data-ttu-id="5f444-150">Beachten Sie Folgendes: Wenn Sie sich im Fokusmodus auf Grundlage Ihres Kalenders befinden, wird die Fokussierung auf den Zustand der Personen in teans, aber in anderen Produkten als "nicht stören" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5f444-150">Note that when you are in focus mode based on your calendar, Focusing will be the state people see in Teans but will show as Do not disturb in other products.</span></span>

<span data-ttu-id="5f444-151">Ihr aktueller Anwesenheitsstatus wird in "Abwesend" geändert, wenn Sie Ihren Computer sperren oder wenn er in den Leerlauf-oder Ruhemodus wechselt.</span><span class="sxs-lookup"><span data-stu-id="5f444-151">Your current presence state changes to Away when you lock your computer or when it enters idle or sleep mode.</span></span> <span data-ttu-id="5f444-152">Auf mobilen Geräten wechselt Ihr Anwesenheitsstatus in abwesend, wenn sich die Teams-App im Hintergrund befindet.</span><span class="sxs-lookup"><span data-stu-id="5f444-152">On mobile, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="5f444-153">Die Benutzer erhalten alle an sie in Microsoft Teams gesendeten Chatnachrichten, unabhängig von ihrem Anwesenheitsstatus.</span><span class="sxs-lookup"><span data-stu-id="5f444-153">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="5f444-154">Wenn ein Benutzer offline ist, wenn jemand ihm eine Nachricht sendet, wird die Chatnachricht in Microsoft Teams angezeigt, wenn der Benutzer das nächste Mal online ist.</span><span class="sxs-lookup"><span data-stu-id="5f444-154">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="5f444-155">Wenn sich ein Benutzer in "nicht stören" befindet, erhält der Benutzer weiterhin Chatnachrichten, aber Banner Benachrichtigungen werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5f444-155">If a user is in Do not disturb, the user will still get chat messages but banner notifications aren't displayed.</span></span>

<span data-ttu-id="5f444-156">Benutzer erhalten Anrufe in allen Anwesenheitsstatus mit Ausnahme von "nicht stören", in dem eingehende Anrufe an Voicemail weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="5f444-156">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="5f444-157">Wenn der Empfänger den Anrufer blockiert hat, wird der Anruf nicht übermittelt, und dem Anrufer wird als Anwesenheitsstatus des Empfängers "Offline" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5f444-157">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="5f444-158">Benutzer können ihrer Vorrangliste Personen hinzufügen, indem sie in Microsoft Teams zu **Einstellungen** > **Privatsphäre** wechseln.</span><span class="sxs-lookup"><span data-stu-id="5f444-158">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="5f444-159">Personen mit Prioritätszugriff können sich an den Benutzer wenden, selbst wenn sich der Benutzer in "nicht stören" befindet.</span><span class="sxs-lookup"><span data-stu-id="5f444-159">People who have priority access can contact the user even when the user is in Do not disturb.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="5f444-160">Administratoreinstellungen in Teams im Vergleich zu Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5f444-160">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="5f444-161">Die folgenden Administratoreinstellungen in Skype for Business unterscheiden sich in Teams:</span><span class="sxs-lookup"><span data-stu-id="5f444-161">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="5f444-162">In Microsoft Teams ist die Freigabe des Anwesenheitsstatus für Benutzer in der Organisation immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="5f444-162">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="5f444-163">Einstellungen zur Privatsphäre (d. h. das Definieren, wer den Anwesenheitsstatus sehen kann) sind in Teams nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5f444-163">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="5f444-164">Die Freigabe des Anwesenheitsstatus für jeden (einschließlich Verbunddienste) ist für Benutzer in Microsoft Teams immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="5f444-164">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="5f444-165">Die Kontaktliste der Benutzer (sofern sie in Skype for Business eine hatten) wird unter **Chat > Kontakte** oder unter **Anrufe > Kontakte** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5f444-165">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="5f444-166">Die Features "Nicht stören" und "Unterbrechen" sind für Benutzer in Teams immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="5f444-166">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="5f444-167">Die Kalenderintegration (einschließlich Abwesenheits- und andere Kalenderinformationen) ist für Benutzer in Teams, die in Outlook integriert sind, immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="5f444-167">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="5f444-168">Die Anzeige *zuletzt anwesend* oder *abwesend seit* ist für Benutzer in Teams immer aktiviert, wenn die Organisation außerdem Skype for Business verwendet.</span><span class="sxs-lookup"><span data-stu-id="5f444-168">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="5f444-169">Die Möglichkeit, diese Einstellungen durch den Teams-Administrator anzupassen, wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5f444-169">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="5f444-170">Koexistenz mit Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5f444-170">Coexistence with Skype for Business</span></span>

<span data-ttu-id="5f444-171">Erfahren Sie unter [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md) mehr über die Anwesenheitsfunktionen, wenn Ihre Organisation außerdem Skype for Business verwendet.</span><span class="sxs-lookup"><span data-stu-id="5f444-171">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
