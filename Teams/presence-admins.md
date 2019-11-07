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
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b829fbffa728d3449ba19466d0a2cb85f266c9c2
ms.sourcegitcommit: b9710149ad0bb321929139118b7df0bc4cca08de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2019
ms.locfileid: "38010598"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="61537-103">Anwesenheit in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="61537-103">User presence in Teams</span></span>

<span data-ttu-id="61537-104">"Anwesenheit" ist Teil des Benutzerprofils in Microsoft Teams (und innerhalb von Office 365). Sie zeigt anderen Benutzern die gegenwärtige Verfügbarkeit und den Status des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="61537-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) that indicates the user’s current availability and status to other users.</span></span> <span data-ttu-id="61537-105">Standardmäßig kann jeder Mitarbeiter in Ihrer Organisation, der Teams verwendet, (nahezu in Echtzeit) sehen, ob andere Benutzer online gerade verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="61537-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61537-106">Wenn Sie den Skype for Business-Client deinstallieren, nachdem Sie einen Benutzer in den **Nur-Teams**-Modus verschoben haben, funktionieren die Anwesenheitsinformationen in Outlook und anderen Office-Apps nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="61537-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="61537-107">In Microsoft Teams funktionieren die Anwesenheitsinformationen einwandfrei.</span><span class="sxs-lookup"><span data-stu-id="61537-107">Presence works fine in Teams.</span></span> <span data-ttu-id="61537-108">Problemumgehung: Wenn Sie die Anwesenheitsinformationen in Outlook (und anderen Office-Apps) anzeigen möchten, muss Skype for Business installiert sein, auch wenn Sie Microsoft Teams im **Nur-Teams**-Modus ausführen.</span><span class="sxs-lookup"><span data-stu-id="61537-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="61537-109">Das Problem ist Microsoft bekannt, und es wird gerade an einer Lösung gearbeitet.</span><span class="sxs-lookup"><span data-stu-id="61537-109">Microsoft is aware of this problem and is working on a fix.</span></span>

<span data-ttu-id="61537-110">Die Anwesenheit von Teams in Outlook wird in der Outlook 2013-Desktop-App und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="61537-110">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="61537-111">Anwesenheitsstatus in Teams</span><span class="sxs-lookup"><span data-stu-id="61537-111">Presence states in Teams</span></span>

<span data-ttu-id="61537-112">Die Anwesenheitsstatus in Team sind:</span><span class="sxs-lookup"><span data-stu-id="61537-112">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="61537-113">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="61537-113">User configured</span></span>|<span data-ttu-id="61537-114">Durch die App konfiguriert</span><span class="sxs-lookup"><span data-stu-id="61537-114">App configured</span></span>|
|:--- |:---|
| ![Ein gefülltes grünes Häkchen zeigt an: verfügbar](media/Presence_Available.png) <span data-ttu-id="61537-116">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="61537-116">Available</span></span>|![Ein gefülltes grünes Häkchen zeigt an: verfügbar](media/Presence_Available.png) <span data-ttu-id="61537-118">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="61537-118">Available</span></span>|
|| ![Ein nicht gefülltes grünes Häkchen zeigt an: verfügbar – außer Haus](media/Presence_Available_OOF.png) <span data-ttu-id="61537-120">Verfügbar – außer Haus</span><span class="sxs-lookup"><span data-stu-id="61537-120">Available, Out of Office</span></span> |
|  ![Ein gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy.png) <span data-ttu-id="61537-122">Beschäftigt</span><span class="sxs-lookup"><span data-stu-id="61537-122">Busy</span></span> |  ![Ein gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy.png) <span data-ttu-id="61537-124">Beschäftigt</span><span class="sxs-lookup"><span data-stu-id="61537-124">Busy</span></span>  |
|| ![Ein gefüllter roter Kreis zeigt an: beschäftigt – am Telefon](media/Presence_Busy.png) <span data-ttu-id="61537-126">Am Telefon</span><span class="sxs-lookup"><span data-stu-id="61537-126">In a call</span></span>|
|| ![Ein gefüllter roter Kreis zeigt an: beschäftigt – in einer Besprechung](media/Presence_Busy.png) <span data-ttu-id="61537-128">In einer Besprechung</span><span class="sxs-lookup"><span data-stu-id="61537-128">In a meeting</span></span> |
|| ![Ein nicht gefüllter roter Kreis zeigt an: beschäftigt](media/Presence_Busy_OOF.png) <span data-ttu-id="61537-130">Am Telefon – abwesend</span><span class="sxs-lookup"><span data-stu-id="61537-130">In a call, out of office</span></span>|
|  ![Ein roter Kreis mit weißer Linie zeigt an: nicht stören](media/Presence_DND.png) <span data-ttu-id="61537-132">Nicht stören</span><span class="sxs-lookup"><span data-stu-id="61537-132">Do not disturb</span></span> ||
|| ![Ein roter Kreis mit weißer Linie zeigt an: hält Präsentation](media/Presence_DND.png) <span data-ttu-id="61537-134">Hält Präsentation</span><span class="sxs-lookup"><span data-stu-id="61537-134">Presenting</span></span>|
|| ![Ein roter Kreis mit weißer Linie zeigt an: fokussierend](media/Presence_DND.png) <span data-ttu-id="61537-136">Fokussierend</span><span class="sxs-lookup"><span data-stu-id="61537-136">Focusing</span></span>|
| ![Das Symbol "gelbe Uhr" zeigt an: abwesend](media/Presence_Away.png) <span data-ttu-id="61537-138">Abwesend</span><span class="sxs-lookup"><span data-stu-id="61537-138">Away</span></span>| ![Das Symbol "gelbe Uhr" zeigt an: abwesend](media/Presence_Away.png) <span data-ttu-id="61537-140">Abwesend</span><span class="sxs-lookup"><span data-stu-id="61537-140">Away</span></span>|
|| <span data-ttu-id="61537-141">![Das Symbol "gelbe Uhr" zeigt an](media/Presence_Away.png): abwesend; zuletzt anwesend um *Zeit*</span><span class="sxs-lookup"><span data-stu-id="61537-141">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Das Symbol "gelbe Uhr" zeigt an: abwesend – bin gleich zurück](media/Presence_Away.png) <span data-ttu-id="61537-143">Bin gleich zurück</span><span class="sxs-lookup"><span data-stu-id="61537-143">Be right back</span></span>| |
|| ![Das Symbol "gelbe Uhr" zeigt an: abwesend – nicht bei der Arbeit](media/Presence_Away.png)  <span data-ttu-id="61537-145">Nicht bei der Arbeit</span><span class="sxs-lookup"><span data-stu-id="61537-145">Off Work</span></span>|
|| ![Grauer Kreis mit x zeigt an: Offline](media/Presence_Offline.png) <span data-ttu-id="61537-147">Offline</span><span class="sxs-lookup"><span data-stu-id="61537-147">Offline</span></span> |
|| ![Offener grauer Kreis zeig an: Status unbekannt](media/Presence_Unknown.png) <span data-ttu-id="61537-149">Status unbekannt</span><span class="sxs-lookup"><span data-stu-id="61537-149">Status unknown</span></span>|
||![Nicht gefüllter roter Kreis mit diagonaler Linie zeig an: gesperrt](media/Presence_Blocked.png) <span data-ttu-id="61537-151">Gesperrt</span><span class="sxs-lookup"><span data-stu-id="61537-151">Blocked</span></span> |
|| ![Lila Kreis mit Pfeil zeigt an: außer Haus](media/Presence_OOF.png) <span data-ttu-id="61537-153">Außer Haus</span><span class="sxs-lookup"><span data-stu-id="61537-153">Out of Office</span></span>|
|||
 
<span data-ttu-id="61537-154">Benutzer haben verschiedene Möglichkeiten, ihren aktuellen Anwesenheitsstatus festzulegen, und ihr Status wird für alle anderen Benutzer sichtbar.</span><span class="sxs-lookup"><span data-stu-id="61537-154">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="61537-155">Weitere Details zur Benutzeranwesenheit werden ebenfalls automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="61537-155">More user presence details are also automatically updated.</span></span> <span data-ttu-id="61537-156">Dies geschieht auf Basis von Benutzeraktivitäten (z. B. "verfügbar" oder "abwesend"), des Outlook-Kalenderstatus (z. B. "in einer Besprechung") oder des Teams-App-Status ("am Telefon", "hält Präsentation"), die in der Liste aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="61537-156">The changes are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span> 

<span data-ttu-id="61537-157">Es gibt ein 15-minütiges Inaktivitäts-Timeout, nach dem ein aktueller Anwesenheitsstatus auf "Abwesend" zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="61537-157">There's a 15-minute inactivity timeout, after which a current presence state is reset to Away.</span></span>

<span data-ttu-id="61537-158">Benutzer können festlegen, wer sie unterbrechen darf, d. h. sie trotz eines „Nicht stören“-Status kontaktieren kann.</span><span class="sxs-lookup"><span data-stu-id="61537-158">Users can specify who can break through (meaning contact them despite a Do Not Disturb state).</span></span> <span data-ttu-id="61537-159">Diese Einstellungen stehen im Teams-Client zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="61537-159">These settings are available in the Teams client.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="61537-160">Administratoreinstellungen in Teams im Vergleich zu Skype for Business</span><span class="sxs-lookup"><span data-stu-id="61537-160">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="61537-161">Die folgenden Administratoreinstellungen in Skype for Business unterscheiden sich in Teams:</span><span class="sxs-lookup"><span data-stu-id="61537-161">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="61537-162">In Microsoft Teams ist die Freigabe des Anwesenheitsstatus für Benutzer in der Organisation immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="61537-162">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="61537-163">Einstellungen zur Privatsphäre (d. h. das Definieren, wer den Anwesenheitsstatus sehen kann) sind in Teams nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="61537-163">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="61537-164">Die Freigabe des Anwesenheitsstatus für jeden (einschließlich Verbunddienste) ist für Benutzer in Microsoft Teams immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="61537-164">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="61537-165">Die Kontaktliste der Benutzer (sofern sie in Skype for Business eine hatten) wird unter **Chat > Kontakte** oder unter **Anrufe > Kontakte** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="61537-165">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="61537-166">Die Features "Nicht stören" und "Unterbrechen" sind für Benutzer in Teams immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="61537-166">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="61537-167">Die Kalenderintegration (einschließlich Abwesenheits- und andere Kalenderinformationen) ist für Benutzer in Teams, die in Outlook integriert sind, immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="61537-167">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="61537-168">Die Anzeige *zuletzt anwesend* oder *abwesend seit* ist für Benutzer in Teams immer aktiviert, wenn die Organisation außerdem Skype for Business verwendet.</span><span class="sxs-lookup"><span data-stu-id="61537-168">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="61537-169">Die Möglichkeit, diese Einstellungen durch den Teams-Administrator anzupassen, wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="61537-169">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="61537-170">Koexistenz mit Skype for Business</span><span class="sxs-lookup"><span data-stu-id="61537-170">Coexistence with Skype for Business</span></span>

<span data-ttu-id="61537-171">Erfahren Sie unter [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md) mehr über die Anwesenheitsfunktionen, wenn Ihre Organisation außerdem Skype for Business verwendet.</span><span class="sxs-lookup"><span data-stu-id="61537-171">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
