---
title: Anwesenheit in Microsoft Teams
author: msdmaguire
ms.author: dmaguire
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
ms.openlocfilehash: 9f14aeaf83862cbdd695eb6ec4646d8da81a0c5b
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369210"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="85203-103">Anwesenheit in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="85203-103">User presence in Teams</span></span>

<span data-ttu-id="85203-104">Anwesenheit ist Teil des Profils eines Benutzers in Microsoft Teams (und in Microsoft 365 oder Office 365), das die aktuelle Verfügbarkeit und den Status des Benutzers für andere Benutzer angibt.</span><span class="sxs-lookup"><span data-stu-id="85203-104">Presence is part of a user's profile in Microsoft Teams (and throughout Microsoft 365 or Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="85203-105">Standardmäßig kann jeder Mitarbeiter in Ihrer Organisation, der Teams verwendet, (nahezu in Echtzeit) sehen, ob andere Benutzer online gerade verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="85203-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

<span data-ttu-id="85203-106">Die Anwesenheit in Teams wird in Outlook ab der Outlook 2013-Desktop-App und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="85203-106">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

 > [!Note]
 > <span data-ttu-id="85203-107">Ausführliche Informationen zu Teams-Benutzerprofilen auf unterschiedlichen Plattformen finden Sie unter [Teams-Features nach Plattform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="85203-107">For details about Teams user profiles on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="85203-108">Anwesenheitsstatus in Teams</span><span class="sxs-lookup"><span data-stu-id="85203-108">Presence states in Teams</span></span>

|<span data-ttu-id="85203-109">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="85203-109">User configured</span></span>|<span data-ttu-id="85203-110">Durch die App konfiguriert</span><span class="sxs-lookup"><span data-stu-id="85203-110">App configured</span></span>|
|:--- |:---|
| ![Ein gefülltes grünes Häkchen zeigt an: verfügbar](media/Presence_Available.png) <span data-ttu-id="85203-112">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="85203-112">Available</span></span>|![Ein gefülltes grünes Häkchen zeigt an: verfügbar](media/Presence_Available.png) <span data-ttu-id="85203-114">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="85203-114">Available</span></span>|
|| ![Ein nicht gefülltes grünes Häkchen zeigt an: verfügbar – außer Haus](media/Presence_Available_OOF.png) <span data-ttu-id="85203-116">Verfügbar – außer Haus</span><span class="sxs-lookup"><span data-stu-id="85203-116">Available, Out of Office</span></span> |
|  ![Ein gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy.png) <span data-ttu-id="85203-118">Beschäftigt</span><span class="sxs-lookup"><span data-stu-id="85203-118">Busy</span></span> |  ![Ein gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy.png) <span data-ttu-id="85203-120">Beschäftigt</span><span class="sxs-lookup"><span data-stu-id="85203-120">Busy</span></span>  |
|| ![Ein gefüllter roter Kreis zeigt an: beschäftigt – am Telefon](media/Presence_Busy.png) <span data-ttu-id="85203-122">Am Telefon</span><span class="sxs-lookup"><span data-stu-id="85203-122">On a call</span></span>|
|| ![Ein gefüllter roter Kreis zeigt an: beschäftigt – in einer Besprechung](media/Presence_Busy.png) <span data-ttu-id="85203-124">In einer Besprechung</span><span class="sxs-lookup"><span data-stu-id="85203-124">In a meeting</span></span> |
|| ![Ein nicht gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy_OOF.png) <span data-ttu-id="85203-126">Am Telefon – abwesend</span><span class="sxs-lookup"><span data-stu-id="85203-126">On a call, out of office</span></span>|
|  ![Ein roter Kreis mit weißer Linie zeigt an: nicht stören](media/Presence_DND.png) <span data-ttu-id="85203-128">Nicht stören</span><span class="sxs-lookup"><span data-stu-id="85203-128">Do not disturb</span></span> ||
|| ![Ein roter Kreis mit weißer Linie zeigt an: hält Präsentation](media/Presence_DND.png) <span data-ttu-id="85203-130">Hält Präsentation</span><span class="sxs-lookup"><span data-stu-id="85203-130">Presenting</span></span>|
|| ![Ein roter Kreis mit weißer Linie zeigt an: fokussierend](media/Presence_DND.png) <span data-ttu-id="85203-132">Fokussierend</span><span class="sxs-lookup"><span data-stu-id="85203-132">Focusing</span></span>|
| ![Das Symbol "gelbe Uhr" zeigt an: abwesend](media/Presence_Away.png) <span data-ttu-id="85203-134">Abwesend</span><span class="sxs-lookup"><span data-stu-id="85203-134">Away</span></span>| ![Das Symbol "gelbe Uhr" zeigt an: abwesend](media/Presence_Away.png) <span data-ttu-id="85203-136">Abwesend</span><span class="sxs-lookup"><span data-stu-id="85203-136">Away</span></span>|
|| <span data-ttu-id="85203-137">![Das Symbol "gelbe Uhr" zeigt an](media/Presence_Away.png): abwesend; zuletzt anwesend um *Zeit*</span><span class="sxs-lookup"><span data-stu-id="85203-137">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Das Symbol "gelbe Uhr" zeigt an: abwesend – bin gleich zurück](media/Presence_Away.png) <span data-ttu-id="85203-139">Bin gleich zurück</span><span class="sxs-lookup"><span data-stu-id="85203-139">Be right back</span></span>| |
|![Grauer Kreis mit x zeigt an: Offline](media/Presence_Offline.png) <span data-ttu-id="85203-141">Als offline anzeigen</span><span class="sxs-lookup"><span data-stu-id="85203-141">Appear offline</span></span> | ![Grauer Kreis mit x zeigt an: Offline](media/Presence_Offline.png) <span data-ttu-id="85203-143">Offline</span><span class="sxs-lookup"><span data-stu-id="85203-143">Offline</span></span>| |
|| ![Offener grauer Kreis zeig an: Status unbekannt](media/Presence_Unknown.png) <span data-ttu-id="85203-145">Status unbekannt</span><span class="sxs-lookup"><span data-stu-id="85203-145">Status unknown</span></span>|
|| ![Lila Kreis mit Pfeil zeigt an: außer Haus](media/Presence_OOF.png) <span data-ttu-id="85203-147">Außer Haus</span><span class="sxs-lookup"><span data-stu-id="85203-147">Out of Office</span></span>|
|||

<span data-ttu-id="85203-148">App-konfigurierte Anwesenheitsstatus basieren auf Benutzeraktivitäten (verfügbar, abwesend), Outlook-Kalenderstatus (in einer Besprechung) oder in Teams-App-Zuständen (in einem Anruf, Präsentation).</span><span class="sxs-lookup"><span data-stu-id="85203-148">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span> <span data-ttu-id="85203-149">Beachten Sie Folgendes: Wenn Sie sich im Fokusmodus auf Grundlage Ihres Kalenders befinden, wird die Fokussierung auf den Zustand der Personen in Teams festgelegt, wird aber in anderen Produkten als "nicht stören" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="85203-149">Note that when you are in focus mode based on your calendar, Focusing will be the state people see in Teams, but it will display as Do not disturb in other products.</span></span>

<span data-ttu-id="85203-150">Ihr aktueller Anwesenheitsstatus wird in "Abwesend" geändert, wenn Sie Ihren Computer sperren oder wenn Ihr Computer in den Leerlauf-oder Ruhemodus wechselt.</span><span class="sxs-lookup"><span data-stu-id="85203-150">Your current presence state changes to Away when you lock your computer or when your computer enters idle or sleep mode.</span></span> <span data-ttu-id="85203-151">Auf einem mobilen Gerät ändert sich Ihr Anwesenheitsstatus in abwesend, wenn sich die Teams-App im Hintergrund befindet.</span><span class="sxs-lookup"><span data-stu-id="85203-151">On a mobile device, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="85203-152">Die Benutzer erhalten alle an sie in Microsoft Teams gesendeten Chatnachrichten, unabhängig von ihrem Anwesenheitsstatus.</span><span class="sxs-lookup"><span data-stu-id="85203-152">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="85203-153">Wenn ein Benutzer offline ist, wenn jemand ihm eine Nachricht sendet, wird die Chatnachricht in Microsoft Teams angezeigt, wenn der Benutzer das nächste Mal online ist.</span><span class="sxs-lookup"><span data-stu-id="85203-153">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="85203-154">Wenn ein Benutzerstatus auf "nicht stören" festgelegt ist, wird der Benutzer weiterhin Chatnachrichten empfangen, aber Banner Benachrichtigungen werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="85203-154">If a user state is set to Do not disturb, the user will still receive chat messages, but banner notifications aren't displayed.</span></span>

<span data-ttu-id="85203-155">Benutzer erhalten Anrufe in allen Anwesenheitsstatus mit Ausnahme von "nicht stören", in dem eingehende Anrufe an Voicemail weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="85203-155">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="85203-156">Wenn der Empfänger den Anrufer blockiert hat, wird der Anruf nicht übermittelt, und dem Anrufer wird als Anwesenheitsstatus des Empfängers "Offline" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="85203-156">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="85203-157">Benutzer können ihrer Vorrangliste Personen hinzufügen, indem sie in Microsoft Teams zu **Einstellungen** > **Privatsphäre** wechseln.</span><span class="sxs-lookup"><span data-stu-id="85203-157">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="85203-158">Personen mit Prioritätszugriff können sich an den Benutzer wenden, auch wenn der Status des Benutzers auf "nicht stören" eingestellt ist.</span><span class="sxs-lookup"><span data-stu-id="85203-158">People who have priority access can contact the user even when the user's status is set to Do not disturb.</span></span>

## <a name="user-configured-states-expiration"></a><span data-ttu-id="85203-159">Ablaufdatum des Benutzer konfigurierten Status</span><span class="sxs-lookup"><span data-stu-id="85203-159">User configured states expiration</span></span>
<span data-ttu-id="85203-160">Wenn ein Benutzer einen bestimmten Anwesenheitsstatus auswählt, hat er Vorrang vor dem Update einer APP-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="85203-160">When a user selects a specific presence state, it takes precedence over any app activity update.</span></span> <span data-ttu-id="85203-161">Wenn sich ein Benutzer beispielsweise als "nicht stören" einstellt, bleibt sein Anwesenheitsstatus unverändert, auch wenn Sie an einer Besprechung teilnehmen oder einen Anruf entgegennehmen.</span><span class="sxs-lookup"><span data-stu-id="85203-161">For example, if a user sets herself as Do not disturb, her presence will remain as Do not disturb even if she attends a meeting or answers a call.</span></span>

<span data-ttu-id="85203-162">Benutzer konfigurierte Status weisen standardmäßige Ablaufeinstellungen in Teams auf, um zu verhindern, dass Benutzer einen Status anzeigen, der nach einer bestimmten Zeitspanne nicht relevant ist.</span><span class="sxs-lookup"><span data-stu-id="85203-162">User configured states have default expiration settings in Teams, in order to prevent users from displaying a status that may not be relevant after a period of time.</span></span>

|<span data-ttu-id="85203-163">Benutzer konfigurierter Zustand</span><span class="sxs-lookup"><span data-stu-id="85203-163">User configured state</span></span>|<span data-ttu-id="85203-164">Standardablaufdatum</span><span class="sxs-lookup"><span data-stu-id="85203-164">Default expiration</span></span>|
|:--- |:---|
| <span data-ttu-id="85203-165">Beschäftigt</span><span class="sxs-lookup"><span data-stu-id="85203-165">Busy</span></span>|<span data-ttu-id="85203-166">1 Tag</span><span class="sxs-lookup"><span data-stu-id="85203-166">1 day</span></span>|
| <span data-ttu-id="85203-167">Nicht stören</span><span class="sxs-lookup"><span data-stu-id="85203-167">Do not disturb</span></span>|<span data-ttu-id="85203-168">1 Tag</span><span class="sxs-lookup"><span data-stu-id="85203-168">1 day</span></span>|
| <span data-ttu-id="85203-169">Andere</span><span class="sxs-lookup"><span data-stu-id="85203-169">Others</span></span>|<span data-ttu-id="85203-170">7 Tage</span><span class="sxs-lookup"><span data-stu-id="85203-170">7 days</span></span>|
|||

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="85203-171">Administratoreinstellungen in Teams im Vergleich zu Skype for Business</span><span class="sxs-lookup"><span data-stu-id="85203-171">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="85203-172">Die folgenden Administratoreinstellungen in Skype for Business unterscheiden sich in Teams:</span><span class="sxs-lookup"><span data-stu-id="85203-172">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="85203-173">In Microsoft Teams ist die Freigabe des Anwesenheitsstatus für Benutzer in der Organisation immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="85203-173">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="85203-174">Einstellungen zur Privatsphäre (d. h. das Definieren, wer den Anwesenheitsstatus sehen kann) sind in Teams nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="85203-174">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="85203-175">Die Freigabe des Anwesenheitsstatus für jeden (einschließlich Verbunddienste) ist für Benutzer in Microsoft Teams immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="85203-175">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="85203-176">Die Kontaktliste der Benutzer (sofern sie in Skype for Business eine hatten) wird unter **Chat > Kontakte** oder unter **Anrufe > Kontakte** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="85203-176">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="85203-177">Die Features "Nicht stören" und "Unterbrechen" sind für Benutzer in Teams immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="85203-177">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="85203-178">Die Kalenderintegration (einschließlich Abwesenheits- und andere Kalenderinformationen) ist für Benutzer in Teams, die in Outlook integriert sind, immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="85203-178">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="85203-179">Die Anzeige *zuletzt anwesend* oder *abwesend seit* ist für Benutzer in Teams immer aktiviert, wenn die Organisation außerdem Skype for Business verwendet.</span><span class="sxs-lookup"><span data-stu-id="85203-179">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="85203-180">Die Möglichkeit, diese Einstellungen durch den Teams-Administrator anzupassen, wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="85203-180">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="85203-181">Koexistenz mit Skype for Business</span><span class="sxs-lookup"><span data-stu-id="85203-181">Coexistence with Skype for Business</span></span>

<span data-ttu-id="85203-182">Erfahren Sie unter [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md) mehr über die Anwesenheitsfunktionen, wenn Ihre Organisation außerdem Skype for Business verwendet.</span><span class="sxs-lookup"><span data-stu-id="85203-182">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
