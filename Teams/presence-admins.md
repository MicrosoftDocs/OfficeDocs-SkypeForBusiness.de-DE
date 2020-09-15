---
title: Anwesenheit in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: 5a944616fef0c3fd9821486a41025adf5f0fdbcc
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814574"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="48f90-103">Anwesenheit in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="48f90-103">User presence in Teams</span></span>

<span data-ttu-id="48f90-104">Anwesenheit ist Teil des Profils eines Benutzers in Microsoft Teams (und in Microsoft 365 oder Office 365), das die aktuelle Verfügbarkeit und den Status des Benutzers für andere Benutzer angibt.</span><span class="sxs-lookup"><span data-stu-id="48f90-104">Presence is part of a user's profile in Microsoft Teams (and throughout Microsoft 365 or Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="48f90-105">Standardmäßig kann jeder Mitarbeiter in Ihrer Organisation, der Teams verwendet, (nahezu in Echtzeit) sehen, ob andere Benutzer online gerade verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="48f90-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

<span data-ttu-id="48f90-106">Die Anwesenheit in Teams wird in Outlook ab der Outlook 2013-Desktop-App und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="48f90-106">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

 > [!Note]
 > <span data-ttu-id="48f90-107">Weitere Informationen finden Sie unter [Team Features nach Plattform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3) .</span><span class="sxs-lookup"><span data-stu-id="48f90-107">See [Team features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3) for more information.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="48f90-108">Anwesenheitsstatus in Teams</span><span class="sxs-lookup"><span data-stu-id="48f90-108">Presence states in Teams</span></span>

|<span data-ttu-id="48f90-109">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="48f90-109">User configured</span></span>|<span data-ttu-id="48f90-110">Durch die App konfiguriert</span><span class="sxs-lookup"><span data-stu-id="48f90-110">App configured</span></span>|
|:--- |:---|
| ![Ein gefülltes grünes Häkchen zeigt an: verfügbar](media/Presence_Available.png) <span data-ttu-id="48f90-112">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="48f90-112">Available</span></span>|![Ein gefülltes grünes Häkchen zeigt an: verfügbar](media/Presence_Available.png) <span data-ttu-id="48f90-114">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="48f90-114">Available</span></span>|
|| ![Ein nicht gefülltes grünes Häkchen zeigt an: verfügbar – außer Haus](media/Presence_Available_OOF.png) <span data-ttu-id="48f90-116">Verfügbar – außer Haus</span><span class="sxs-lookup"><span data-stu-id="48f90-116">Available, Out of Office</span></span> |
|  ![Ein gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy.png) <span data-ttu-id="48f90-118">Beschäftigt</span><span class="sxs-lookup"><span data-stu-id="48f90-118">Busy</span></span> |  ![Ein gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy.png) <span data-ttu-id="48f90-120">Beschäftigt</span><span class="sxs-lookup"><span data-stu-id="48f90-120">Busy</span></span>  |
|| ![Ein gefüllter roter Kreis zeigt an: beschäftigt – am Telefon](media/Presence_Busy.png) <span data-ttu-id="48f90-122">Am Telefon</span><span class="sxs-lookup"><span data-stu-id="48f90-122">On a call</span></span>|
|| ![Ein gefüllter roter Kreis zeigt an: beschäftigt – in einer Besprechung](media/Presence_Busy.png) <span data-ttu-id="48f90-124">In einer Besprechung</span><span class="sxs-lookup"><span data-stu-id="48f90-124">In a meeting</span></span> |
|| ![Ein nicht gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy_OOF.png) <span data-ttu-id="48f90-126">Am Telefon – abwesend</span><span class="sxs-lookup"><span data-stu-id="48f90-126">On a call, out of office</span></span>|
|  ![Ein roter Kreis mit weißer Linie zeigt an: nicht stören](media/Presence_DND.png) <span data-ttu-id="48f90-128">Nicht stören</span><span class="sxs-lookup"><span data-stu-id="48f90-128">Do not disturb</span></span> ||
|| ![Ein roter Kreis mit weißer Linie zeigt an: hält Präsentation](media/Presence_DND.png) <span data-ttu-id="48f90-130">Hält Präsentation</span><span class="sxs-lookup"><span data-stu-id="48f90-130">Presenting</span></span>|
|| ![Ein roter Kreis mit weißer Linie zeigt an: fokussierend](media/Presence_DND.png) <span data-ttu-id="48f90-132">Fokussierend</span><span class="sxs-lookup"><span data-stu-id="48f90-132">Focusing</span></span>|
| ![Das Symbol "gelbe Uhr" zeigt an: abwesend](media/Presence_Away.png) <span data-ttu-id="48f90-134">Abwesend</span><span class="sxs-lookup"><span data-stu-id="48f90-134">Away</span></span>| ![Das Symbol "gelbe Uhr" zeigt an: abwesend](media/Presence_Away.png) <span data-ttu-id="48f90-136">Abwesend</span><span class="sxs-lookup"><span data-stu-id="48f90-136">Away</span></span>|
|| <span data-ttu-id="48f90-137">![Das Symbol "gelbe Uhr" zeigt an](media/Presence_Away.png): abwesend; zuletzt anwesend um *Zeit*</span><span class="sxs-lookup"><span data-stu-id="48f90-137">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Das Symbol "gelbe Uhr" zeigt an: abwesend – bin gleich zurück](media/Presence_Away.png) <span data-ttu-id="48f90-139">Bin gleich zurück</span><span class="sxs-lookup"><span data-stu-id="48f90-139">Be right back</span></span>| |
|| ![Das Symbol "gelbe Uhr" zeigt an: abwesend – nicht bei der Arbeit](media/Presence_Away.png)  <span data-ttu-id="48f90-141">Nicht bei der Arbeit</span><span class="sxs-lookup"><span data-stu-id="48f90-141">Off Work</span></span>|
|| ![Grauer Kreis mit x zeigt an: Offline](media/Presence_Offline.png) <span data-ttu-id="48f90-143">Offline</span><span class="sxs-lookup"><span data-stu-id="48f90-143">Offline</span></span> |
|| ![Offener grauer Kreis zeig an: Status unbekannt](media/Presence_Unknown.png) <span data-ttu-id="48f90-145">Status unbekannt</span><span class="sxs-lookup"><span data-stu-id="48f90-145">Status unknown</span></span>|
||![Nicht gefüllter roter Kreis mit diagonaler Linie zeig an: gesperrt](media/Presence_Blocked.png) <span data-ttu-id="48f90-147">Gesperrt</span><span class="sxs-lookup"><span data-stu-id="48f90-147">Blocked</span></span> |
|| ![Lila Kreis mit Pfeil zeigt an: außer Haus](media/Presence_OOF.png) <span data-ttu-id="48f90-149">Außer Haus</span><span class="sxs-lookup"><span data-stu-id="48f90-149">Out of Office</span></span>|
|||

<span data-ttu-id="48f90-150">App-konfigurierte Anwesenheitsstatus basieren auf Benutzeraktivitäten (verfügbar, abwesend), Outlook-Kalenderstatus (in einer Besprechung) oder in Teams-App-Zuständen (in einem Anruf, Präsentation).</span><span class="sxs-lookup"><span data-stu-id="48f90-150">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span> <span data-ttu-id="48f90-151">Beachten Sie Folgendes: Wenn Sie sich im Fokusmodus auf Grundlage Ihres Kalenders befinden, ist die Fokussierung der Status, den Personen in Teams angezeigt werden, aber in anderen Produkten als "nicht stören" angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="48f90-151">Note that when you are in focus mode based on your calendar, Focusing will be the state people see in Teams but will show as Do not disturb in other products.</span></span>

<span data-ttu-id="48f90-152">Ihr aktueller Anwesenheitsstatus wird in "Abwesend" geändert, wenn Sie Ihren Computer sperren oder wenn er in den Leerlauf-oder Ruhemodus wechselt.</span><span class="sxs-lookup"><span data-stu-id="48f90-152">Your current presence state changes to Away when you lock your computer or when it enters idle or sleep mode.</span></span> <span data-ttu-id="48f90-153">Auf mobilen Geräten wechselt Ihr Anwesenheitsstatus in abwesend, wenn sich die Teams-App im Hintergrund befindet.</span><span class="sxs-lookup"><span data-stu-id="48f90-153">On mobile, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="48f90-154">Die Benutzer erhalten alle an sie in Microsoft Teams gesendeten Chatnachrichten, unabhängig von ihrem Anwesenheitsstatus.</span><span class="sxs-lookup"><span data-stu-id="48f90-154">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="48f90-155">Wenn ein Benutzer offline ist, wenn jemand ihm eine Nachricht sendet, wird die Chatnachricht in Microsoft Teams angezeigt, wenn der Benutzer das nächste Mal online ist.</span><span class="sxs-lookup"><span data-stu-id="48f90-155">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="48f90-156">Wenn sich ein Benutzer in "nicht stören" befindet, erhält der Benutzer weiterhin Chatnachrichten, aber Banner Benachrichtigungen werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="48f90-156">If a user is in Do not disturb, the user will still get chat messages but banner notifications aren't displayed.</span></span>

<span data-ttu-id="48f90-157">Benutzer erhalten Anrufe in allen Anwesenheitsstatus mit Ausnahme von "nicht stören", in dem eingehende Anrufe an Voicemail weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="48f90-157">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="48f90-158">Wenn der Empfänger den Anrufer blockiert hat, wird der Anruf nicht übermittelt, und dem Anrufer wird als Anwesenheitsstatus des Empfängers "Offline" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="48f90-158">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="48f90-159">Benutzer können ihrer Vorrangliste Personen hinzufügen, indem sie in Microsoft Teams zu **Einstellungen** > **Privatsphäre** wechseln.</span><span class="sxs-lookup"><span data-stu-id="48f90-159">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="48f90-160">Personen mit Prioritätszugriff können sich an den Benutzer wenden, selbst wenn sich der Benutzer in "nicht stören" befindet.</span><span class="sxs-lookup"><span data-stu-id="48f90-160">People who have priority access can contact the user even when the user is in Do not disturb.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="48f90-161">Administratoreinstellungen in Teams im Vergleich zu Skype for Business</span><span class="sxs-lookup"><span data-stu-id="48f90-161">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="48f90-162">Die folgenden Administratoreinstellungen in Skype for Business unterscheiden sich in Teams:</span><span class="sxs-lookup"><span data-stu-id="48f90-162">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="48f90-163">In Microsoft Teams ist die Freigabe des Anwesenheitsstatus für Benutzer in der Organisation immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="48f90-163">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="48f90-164">Einstellungen zur Privatsphäre (d. h. das Definieren, wer den Anwesenheitsstatus sehen kann) sind in Teams nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="48f90-164">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="48f90-165">Die Freigabe des Anwesenheitsstatus für jeden (einschließlich Verbunddienste) ist für Benutzer in Microsoft Teams immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="48f90-165">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="48f90-166">Die Kontaktliste der Benutzer (sofern sie in Skype for Business eine hatten) wird unter **Chat > Kontakte** oder unter **Anrufe > Kontakte** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="48f90-166">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="48f90-167">Die Features "Nicht stören" und "Unterbrechen" sind für Benutzer in Teams immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="48f90-167">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="48f90-168">Die Kalenderintegration (einschließlich Abwesenheits- und andere Kalenderinformationen) ist für Benutzer in Teams, die in Outlook integriert sind, immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="48f90-168">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="48f90-169">Die Anzeige *zuletzt anwesend* oder *abwesend seit* ist für Benutzer in Teams immer aktiviert, wenn die Organisation außerdem Skype for Business verwendet.</span><span class="sxs-lookup"><span data-stu-id="48f90-169">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="48f90-170">Die Möglichkeit, diese Einstellungen durch den Teams-Administrator anzupassen, wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="48f90-170">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="48f90-171">Koexistenz mit Skype for Business</span><span class="sxs-lookup"><span data-stu-id="48f90-171">Coexistence with Skype for Business</span></span>

<span data-ttu-id="48f90-172">Erfahren Sie unter [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md) mehr über die Anwesenheitsfunktionen, wenn Ihre Organisation außerdem Skype for Business verwendet.</span><span class="sxs-lookup"><span data-stu-id="48f90-172">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
