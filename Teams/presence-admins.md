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
description: Informationen für Administratoren zur Anwesenheit in Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0bd57165cbb88df135827ae72fa3952dd8ddd452
ms.sourcegitcommit: 299f854bbb73887ba315b09b9adf9ea9ff91e8ec
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37062961"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="1b6fb-103">Anwesenheit in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1b6fb-103">User Presence in Teams</span></span>

<span data-ttu-id="1b6fb-104">"Anwesenheit" ist Teil des Benutzerprofils in Microsoft Teams (und innerhalb von Office 365). Sie zeigt anderen Benutzern die gegenwärtige Verfügbarkeit und den Status des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="1b6fb-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) that indicates the user’s current availability and status to other users.</span></span> <span data-ttu-id="1b6fb-105">Standardmäßig kann jeder Mitarbeiter in Ihrer Organisation, der Teams verwendet, (nahezu in Echtzeit) sehen, ob andere Benutzer online gerade verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1b6fb-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1b6fb-106">Wenn Sie den Skype for Business-Client deinstallieren, nachdem Sie einen Benutzer in den **Nur-Teams**-Modus verschoben haben, funktionieren die Anwesenheitsinformationen in Outlook und anderen Office-Apps nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="1b6fb-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="1b6fb-107">In Microsoft Teams funktionieren die Anwesenheitsinformationen einwandfrei.</span><span class="sxs-lookup"><span data-stu-id="1b6fb-107">Presence works fine in Teams.</span></span> <span data-ttu-id="1b6fb-108">Problemumgehung: Wenn Sie die Anwesenheitsinformationen in Outlook (und anderen Office-Apps) anzeigen möchten, muss Skype for Business installiert sein, auch wenn Sie Microsoft Teams im **Nur-Teams**-Modus ausführen.</span><span class="sxs-lookup"><span data-stu-id="1b6fb-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="1b6fb-109">Das Problem ist Microsoft bekannt, und es wird gerade an einer Lösung gearbeitet.</span><span class="sxs-lookup"><span data-stu-id="1b6fb-109">Microsoft is aware of this problem and is working on a fix.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="1b6fb-110">Anwesenheitsstatus in Teams</span><span class="sxs-lookup"><span data-stu-id="1b6fb-110">User Presence in Teams</span></span>

<span data-ttu-id="1b6fb-111">Die Anwesenheitsstatus in Team sind:</span><span class="sxs-lookup"><span data-stu-id="1b6fb-111">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="1b6fb-112">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="1b6fb-112">User configured</span></span>|<span data-ttu-id="1b6fb-113">Durch die App konfiguriert</span><span class="sxs-lookup"><span data-stu-id="1b6fb-113">App configured</span></span>|
|:--- |:---|
| ![Ein gefülltes grünes Häkchen zeigt an: verfügbar](media/Presence_Available.png) <span data-ttu-id="1b6fb-115">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="1b6fb-115">Available</span></span>|![Ein gefülltes grünes Häkchen zeigt an: verfügbar](media/Presence_Available.png) <span data-ttu-id="1b6fb-117">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="1b6fb-117">Available</span></span>|
|| ![Ein nicht gefülltes grünes Häkchen zeigt an: verfügbar – außer Haus](media/Presence_Available_OOF.png) <span data-ttu-id="1b6fb-119">Verfügbar – außer Haus</span><span class="sxs-lookup"><span data-stu-id="1b6fb-119">Available, Out of Office</span></span> |
|  ![Ein gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy.png) <span data-ttu-id="1b6fb-121">Beschäftigt</span><span class="sxs-lookup"><span data-stu-id="1b6fb-121">Busy Here.</span></span> |  ![Ein gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy.png) <span data-ttu-id="1b6fb-123">Beschäftigt</span><span class="sxs-lookup"><span data-stu-id="1b6fb-123">Busy Here.</span></span>  |
|| ![Ein gefüllter roter Kreis zeigt an: beschäftigt – am Telefon](media/Presence_Busy.png) <span data-ttu-id="1b6fb-125">Am Telefon</span><span class="sxs-lookup"><span data-stu-id="1b6fb-125">In a call</span></span>|
|| ![Ein gefüllter roter Kreis zeigt an: beschäftigt – in einer Besprechung](media/Presence_Busy.png) <span data-ttu-id="1b6fb-127">In einer Besprechung</span><span class="sxs-lookup"><span data-stu-id="1b6fb-127">In a meeting</span></span> |
|| ![Ein nicht gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy_OOF.png) <span data-ttu-id="1b6fb-129">Am Telefon – abwesend</span><span class="sxs-lookup"><span data-stu-id="1b6fb-129">In a call, out of office</span></span>|
|  ![Ein roter Kreis mit weißer Linie zeigt an: nicht stören](media/Presence_DND.png) <span data-ttu-id="1b6fb-131">Nicht stören</span><span class="sxs-lookup"><span data-stu-id="1b6fb-131">Do not disturb</span></span> ||
|| ![Ein roter Kreis mit weißer Linie zeigt an: hält Präsentation](media/Presence_DND.png) <span data-ttu-id="1b6fb-133">Hält Präsentation</span><span class="sxs-lookup"><span data-stu-id="1b6fb-133">Presenting</span></span>|
|| ![Ein roter Kreis mit weißer Linie zeigt an: fokussierend](media/Presence_DND.png) <span data-ttu-id="1b6fb-135">Fokussierend</span><span class="sxs-lookup"><span data-stu-id="1b6fb-135">Focusing</span></span>|
| ![Das Symbol "gelbe Uhr" zeigt an: abwesend](media/Presence_Away.png) <span data-ttu-id="1b6fb-137">Abwesend</span><span class="sxs-lookup"><span data-stu-id="1b6fb-137">Away</span></span>| ![Das Symbol "gelbe Uhr" zeigt an: abwesend](media/Presence_Away.png) <span data-ttu-id="1b6fb-139">Abwesend</span><span class="sxs-lookup"><span data-stu-id="1b6fb-139">Away</span></span>|
|| <span data-ttu-id="1b6fb-140">![Das Symbol "gelbe Uhr" zeigt an](media/Presence_Away.png): abwesend; zuletzt anwesend um *Zeit*</span><span class="sxs-lookup"><span data-stu-id="1b6fb-140">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Das Symbol "gelbe Uhr" zeigt an: abwesend – bin gleich zurück](media/Presence_Away.png) <span data-ttu-id="1b6fb-142">Bin gleich zurück</span><span class="sxs-lookup"><span data-stu-id="1b6fb-142">Be right back</span></span>| |
|| ![Das Symbol "gelbe Uhr" zeigt an: abwesend – nicht bei der Arbeit](media/Presence_Away.png)  <span data-ttu-id="1b6fb-144">Nicht bei der Arbeit</span><span class="sxs-lookup"><span data-stu-id="1b6fb-144">Off Work</span></span>|
|| ![Grauer Kreis mit x zeigt an: Offline](media/Presence_Offline.png) <span data-ttu-id="1b6fb-146">Offline</span><span class="sxs-lookup"><span data-stu-id="1b6fb-146">Offline</span></span> |
|| ![Offener grauer Kreis zeig an: Status unbekannt](media/Presence_Unknown.png) <span data-ttu-id="1b6fb-148">Status unbekannt</span><span class="sxs-lookup"><span data-stu-id="1b6fb-148">Status unknown</span></span>|
||![Nicht gefüllter roter Kreis mit diagonaler Linie zeig an: gesperrt](media/Presence_Blocked.png) <span data-ttu-id="1b6fb-150">Gesperrt</span><span class="sxs-lookup"><span data-stu-id="1b6fb-150">Blocked</span></span> |
|| ![Lila Kreis mit Pfeil zeigt an: außer Haus](media/Presence_OOF.png) <span data-ttu-id="1b6fb-152">Außer Haus</span><span class="sxs-lookup"><span data-stu-id="1b6fb-152">Out of Office</span></span>|
|||
 
<span data-ttu-id="1b6fb-153">Benutzer haben verschiedene Möglichkeiten, ihren aktuellen Anwesenheitsstatus festzulegen, und ihr Status wird für alle anderen Benutzer sichtbar.</span><span class="sxs-lookup"><span data-stu-id="1b6fb-153">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="1b6fb-154">Weitere Details zur Benutzeranwesenheit werden ebenfalls automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="1b6fb-154">More user presence details are also automatically updated.</span></span> <span data-ttu-id="1b6fb-155">Dies geschieht auf Basis von Benutzeraktivitäten (z. B. "verfügbar" oder "abwesend"), des Outlook-Kalenderstatus (z. B. "in einer Besprechung") oder des Teams-App-Status ("am Telefon", "hält Präsentation"), die in der Liste aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="1b6fb-155">The changes are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="1b6fb-156">Es gibt ein Inaktivitätszeitlimit von 15 Minuten. Danach wird der aktuelle Anwesenheitsstatus eines Benutzers auf "abwesend" zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="1b6fb-156">There is a 15-minute inactivity timeout, after which a current presence state is reset to Away.</span></span>

<span data-ttu-id="1b6fb-157">Benutzer können festlegen, wer sie unterbrechen darf, d. h. sie trotz eines „Nicht stören“-Status kontaktieren kann.</span><span class="sxs-lookup"><span data-stu-id="1b6fb-157">Users can specify who can break through (meaning contact them despite a Do Not Disturb state).</span></span> <span data-ttu-id="1b6fb-158">Diese Einstellungen stehen im Teams-Client zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1b6fb-158">These settings are available in the Teams client.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="1b6fb-159">Administratoreinstellungen in Teams im Vergleich zu Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1b6fb-159">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="1b6fb-160">Die folgenden Administratoreinstellungen in Skype for Business unterscheiden sich in Teams:</span><span class="sxs-lookup"><span data-stu-id="1b6fb-160">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="1b6fb-161">In Microsoft Teams ist die Freigabe des Anwesenheitsstatus für Benutzer in der Organisation immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1b6fb-161">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="1b6fb-162">Einstellungen zur Privatsphäre (d. h. das Definieren, wer den Anwesenheitsstatus sehen kann) sind in Teams nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1b6fb-162">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="1b6fb-163">Die Freigabe des Anwesenheitsstatus für jeden (einschließlich Verbunddienste) ist für Benutzer in Microsoft Teams immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1b6fb-163">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="1b6fb-164">Die Kontaktliste der Benutzer (sofern sie in Skype for Business eine hatten) wird unter **Chat > Kontakte** oder unter **Anrufe > Kontakte** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1b6fb-164">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="1b6fb-165">Die Features "Nicht stören" und "Unterbrechen" sind für Benutzer in Teams immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1b6fb-165">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="1b6fb-166">Die Kalenderintegration (einschließlich Abwesenheits- und andere Kalenderinformationen) ist für Benutzer in Teams, die in Outlook integriert sind, immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1b6fb-166">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="1b6fb-167">Die Anzeige *zuletzt anwesend* oder *abwesend seit* ist für Benutzer in Teams immer aktiviert, wenn die Organisation außerdem Skype for Business verwendet.</span><span class="sxs-lookup"><span data-stu-id="1b6fb-167">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="1b6fb-168">Die Möglichkeit, diese Einstellungen durch den Teams-Administrator anzupassen, wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1b6fb-168">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="1b6fb-169">Koexistenz mit Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1b6fb-169">Coexistence with Skype for Business</span></span>

<span data-ttu-id="1b6fb-170">Erfahren Sie unter [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md) mehr über die Anwesenheitsfunktionen, wenn Ihre Organisation außerdem Skype for Business verwendet.</span><span class="sxs-lookup"><span data-stu-id="1b6fb-170">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
