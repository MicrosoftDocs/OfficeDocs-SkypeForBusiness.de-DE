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
ms.openlocfilehash: 054c3a639cc5857fb25a7e211a272868477dcb61
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573217"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="84e85-103">Anwesenheit in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84e85-103">User presence in Teams</span></span>

<span data-ttu-id="84e85-104">Anwesenheit ist Teil des Profils eines Benutzers in Microsoft Teams (und in Office 365), das die aktuelle Verfügbarkeit und den Status des Benutzers für andere Benutzer angibt.</span><span class="sxs-lookup"><span data-stu-id="84e85-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) that indicates the user’s current availability and status to other users.</span></span> <span data-ttu-id="84e85-105">Standardmäßig können alle Personen in Ihrer Organisation, die Teams verwenden, (nahezu in Echtzeit) sehen, ob andere Benutzer online verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="84e85-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84e85-106">Wenn Sie den Skype for Business-Client deinstallieren, nachdem Sie einen Benutzer in den **TeamsOnly**-Modus verschoben haben, funktionieren die Anwesenheitsinformationen in Outlook und anderen Office-Apps nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="84e85-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="84e85-107">In Microsoft Teams funktionieren die Anwesenheitsinformationen einwandfrei.</span><span class="sxs-lookup"><span data-stu-id="84e85-107">Presence works fine in Teams.</span></span> <span data-ttu-id="84e85-108">Problemumgehung: damit die Anwesenheit in Outlook (und anderen Office-Apps) angezeigt wird, muss Skype for Business installiert sein, auch wenn Sie nur Teams im Modus " **nur Teams** " ausführen.</span><span class="sxs-lookup"><span data-stu-id="84e85-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="84e85-109">Das Problem ist Microsoft bekannt, und es wird gerade an einer Lösung gearbeitet.</span><span class="sxs-lookup"><span data-stu-id="84e85-109">Microsoft is aware of this problem and is working on a fix.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="84e85-110">Anwesenheitsstatus in Teams</span><span class="sxs-lookup"><span data-stu-id="84e85-110">Presence states in Teams</span></span>

<span data-ttu-id="84e85-111">Die in Teams verfügbaren Benutzer Anwesenheitsstatus sind:</span><span class="sxs-lookup"><span data-stu-id="84e85-111">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="84e85-112">Benutzer konfiguriert</span><span class="sxs-lookup"><span data-stu-id="84e85-112">User configured</span></span>|<span data-ttu-id="84e85-113">App konfiguriert</span><span class="sxs-lookup"><span data-stu-id="84e85-113">App configured</span></span>|
|:--- |:---|
| ![Vollständiges grünes Häkchen, kennzeichnet Anwesenheitsstatus](media/Presence_Available.png) <span data-ttu-id="84e85-115">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="84e85-115">Available</span></span>|![Vollständiges grünes Häkchen, kennzeichnet Anwesenheitsstatus](media/Presence_Available.png) <span data-ttu-id="84e85-117">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="84e85-117">Available</span></span>|
|| ![Grünes Häkchen öffnen, kennzeichnet verfügbare Abwesenheit](media/Presence_Available_OOF.png) <span data-ttu-id="84e85-119">Verfügbar, außer Haus</span><span class="sxs-lookup"><span data-stu-id="84e85-119">Available, Out of Office</span></span> |
|  ![Vollständiger roter Kreis, zeigt "beschäftigt" an](media/Presence_Busy.png) <span data-ttu-id="84e85-121">Beschäftigt</span><span class="sxs-lookup"><span data-stu-id="84e85-121">Busy</span></span> |  ![Vollständiger roter Kreis, zeigt "beschäftigt" an](media/Presence_Busy.png) <span data-ttu-id="84e85-123">Beschäftigt</span><span class="sxs-lookup"><span data-stu-id="84e85-123">Busy</span></span>  |
|| ![Vollständiger roter Kreis, kennzeichnet beschäftigt in einem Anruf](media/Presence_Busy.png) <span data-ttu-id="84e85-125">In einem Anruf</span><span class="sxs-lookup"><span data-stu-id="84e85-125">In a call</span></span>|
|| ![Vollständiger roter Kreis, zeigt "beschäftigt" in einer Besprechung an](media/Presence_Busy.png) <span data-ttu-id="84e85-127">In einer Besprechung</span><span class="sxs-lookup"><span data-stu-id="84e85-127">In a meeting</span></span> |
|| ![Roter Kreis öffnen, zeigt "beschäftigt" an](media/Presence_Busy_OOF.png) <span data-ttu-id="84e85-129">In einem Anruf: Abwesenheit</span><span class="sxs-lookup"><span data-stu-id="84e85-129">In a call, out of office</span></span>|
|  ![Roter Kreis mit weißer Zeile, kennzeichnet "nicht stören"](media/Presence_DND.png) <span data-ttu-id="84e85-131">Nicht stören</span><span class="sxs-lookup"><span data-stu-id="84e85-131">Do not disturb</span></span> ||
|| ![Roter Kreis mit weißer Zeile, zeigt die Präsentation an](media/Presence_DND.png) <span data-ttu-id="84e85-133">Präsentieren</span><span class="sxs-lookup"><span data-stu-id="84e85-133">Presenting</span></span>|
|| ![Roter Kreis mit weißer Zeile, zeigt die Fokussierung an](media/Presence_DND.png) <span data-ttu-id="84e85-135">Fokussierung</span><span class="sxs-lookup"><span data-stu-id="84e85-135">Focusing</span></span>|
| ![Symbol "gelbe Uhr", zeigt "Abwesend" an](media/Presence_Away.png) <span data-ttu-id="84e85-137">Abwesend</span><span class="sxs-lookup"><span data-stu-id="84e85-137">Away</span></span>| ![Symbol "gelbe Uhr", zeigt "Abwesend" an](media/Presence_Away.png) <span data-ttu-id="84e85-139">Abwesend</span><span class="sxs-lookup"><span data-stu-id="84e85-139">Away</span></span>|
|| <span data-ttu-id="84e85-140">![Symbol "gelbe Uhr",](media/Presence_Away.png) zeigt "Abwesend" als letztes *mal* an</span><span class="sxs-lookup"><span data-stu-id="84e85-140">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Symbol "gelbe Uhr", "Abwesend", "gleich zurück"](media/Presence_Away.png) <span data-ttu-id="84e85-142">Bin gleich zurück</span><span class="sxs-lookup"><span data-stu-id="84e85-142">Be right back</span></span>| |
|| ![Symbol "gelbe Uhr", zeigt "Abwesend", "Arbeit" an](media/Presence_Away.png)  <span data-ttu-id="84e85-144">Off-Arbeit</span><span class="sxs-lookup"><span data-stu-id="84e85-144">Off Work</span></span>|
|| ![Grauer Kreis mit x, kennzeichnet offline](media/Presence_Offline.png) <span data-ttu-id="84e85-146">Offline</span><span class="sxs-lookup"><span data-stu-id="84e85-146">Offline</span></span> |
|| ![Grauer Kreis öffnen, kennzeichnet Status unbekannt](media/Presence_Unknown.png) <span data-ttu-id="84e85-148">Status unbekannt</span><span class="sxs-lookup"><span data-stu-id="84e85-148">Status unknown</span></span>|
||![Roter Kreis mit diagonaler Linienart öffnen, zeigt "blockiert" an](media/Presence_Blocked.png) <span data-ttu-id="84e85-150">Blockiert</span><span class="sxs-lookup"><span data-stu-id="84e85-150">Blocked</span></span> |
|| ![Lila Kreis mit Pfeil, kennzeichnet Abwesenheitsanzeige](media/Presence_OOF.png) <span data-ttu-id="84e85-152">Abwesenheit</span><span class="sxs-lookup"><span data-stu-id="84e85-152">Out of Office</span></span>|
|||
 
<span data-ttu-id="84e85-153">Benutzer können Ihren aktuellen Anwesenheitsstatus manuell auf einige Optionen einstellen, und Ihr Status wird für alle anderen Benutzer wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="84e85-153">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="84e85-154">Weitere Details zur Benutzer Anwesenheit werden ebenfalls automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="84e85-154">More user presence details are also automatically updated.</span></span> <span data-ttu-id="84e85-155">Die Änderungen basieren auf Benutzeraktivitäten (verfügbar, abwesend), Outlook-Kalender Zuständen (in einer Besprechung) oder Teams-App-Zustände (in einem Aufruf, Präsentation) an Zustände, die in der Liste eingerückt sind.</span><span class="sxs-lookup"><span data-stu-id="84e85-155">The changes are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="84e85-156">Es gibt ein 15-minütiges Inaktivitäts-Timeout, nach dem ein aktueller Anwesenheitsstatus auf "Abwesend" zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="84e85-156">There is a 15-minute inactivity timeout, after which a current presence state is reset to Away.</span></span>

<span data-ttu-id="84e85-157">Benutzer können angeben, wer durchbrechen kann (was bedeutet, dass Sie trotz des Zustands "nicht stören" Kontakt mit Ihnen aufnehmen können).</span><span class="sxs-lookup"><span data-stu-id="84e85-157">Users can specify who can break through (meaning contact them despite a Do Not Disturb state).</span></span> <span data-ttu-id="84e85-158">Diese Einstellungen sind im Team-Client verfügbar.</span><span class="sxs-lookup"><span data-stu-id="84e85-158">These settings are available in the Teams client.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="84e85-159">Administratoreinstellungen in Teams im Vergleich zu Skype for Business</span><span class="sxs-lookup"><span data-stu-id="84e85-159">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="84e85-160">Die folgenden Administratoreinstellungen für Skype for Business unterscheiden sich in Teams:</span><span class="sxs-lookup"><span data-stu-id="84e85-160">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="84e85-161">In Teams ist die Anwesenheits Freigabe für Benutzer in der Organisation immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="84e85-161">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="84e85-162">Der Datenschutz (in dem Sie definieren, wer Anwesenheitsinformationen sehen kann) ist in Microsoft Teams nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="84e85-162">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="84e85-163">Anwesenheits Freigaben für alle (einschließlich der Verbunddienste) sind für Benutzer in Teams immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="84e85-163">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="84e85-164">Ihre Kontaktliste (wenn Sie eine in Skype for Business hatte) ist unter **Chat #a0 Kontakte** oder unter **Anrufe #a1 Kontakte**sichtbar.</span><span class="sxs-lookup"><span data-stu-id="84e85-164">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="84e85-165">Der Client stört nicht, und Durchbruch Features sind für Benutzer in Teams immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="84e85-165">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="84e85-166">Kalender (einschließlich Abwesenheits-und anderer Kalenderinformationen) die Integration ist für Benutzer immer aktiviert, wenn Teams in Outlook integriert sind.</span><span class="sxs-lookup"><span data-stu-id="84e85-166">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="84e85-167">Der Indikator *zuletzt gesehen* oder *Abwesend* ist für Benutzer in Teams immer aktiviert, wenn die Organisation ebenfalls Skype for Business verwendet.</span><span class="sxs-lookup"><span data-stu-id="84e85-167">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="84e85-168">Die Fähigkeit eines Teams-Administrators, diese Einstellungen anzupassen, wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="84e85-168">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="84e85-169">Koexistenz mit Skype for Business</span><span class="sxs-lookup"><span data-stu-id="84e85-169">Coexistence with Skype for Business</span></span>

<span data-ttu-id="84e85-170">Weitere Informationen dazu, wie die Anwesenheit von Teams funktioniert, wenn Ihre Organisation ebenfalls Skype for Business verwendet, finden Sie unter [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md) .</span><span class="sxs-lookup"><span data-stu-id="84e85-170">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
