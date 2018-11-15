---
title: Vorhandensein eines Benutzers in Teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rakayala
description: Administratoren Informationen müssen zum Verständnis von Anwesenheitsinformationen in Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1934a602d89240c89ffb4f7410192d19a7dd2e61
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26533026"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="0fcd6-103">Vorhandensein eines Benutzers in Teams</span><span class="sxs-lookup"><span data-stu-id="0fcd6-103">User Presence in Teams</span></span>

<span data-ttu-id="0fcd6-104">Anwesenheit ist Teil der Profil eines Benutzers in Microsoft-Teams (und in der gesamten Office 365) – und gibt die aktuelle Verfügbarkeit und den Status für andere Benutzer in der Organisation des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="0fcd6-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) – and indicates the user’s current availability and status to other users in the organization.</span></span> <span data-ttu-id="0fcd6-105">Standardmäßig kann jeder Benutzer in Ihrer Organisation mithilfe von Teams anzeigen, und zwar unabhängig davon, ob andere Benutzer online zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="0fcd6-105">By default, anyone in your organization using Teams can see whether or not other users are available online.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="0fcd6-106">Anwesenheitsstatus in Teams</span><span class="sxs-lookup"><span data-stu-id="0fcd6-106">Presence states in Teams</span></span>

<span data-ttu-id="0fcd6-107">Die Benutzer-Anwesenheitsstatus in Teams verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="0fcd6-107">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="0fcd6-108">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="0fcd6-108">User configured</span></span>|<span data-ttu-id="0fcd6-109">App konfiguriert</span><span class="sxs-lookup"><span data-stu-id="0fcd6-109">App configured</span></span>|
|:--- |:---|
| ![Anwesenheit verfügbar](media/Presence_Available.png) <span data-ttu-id="0fcd6-111">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="0fcd6-111">Available</span></span>|![Anwesenheit verfügbar](media/Presence_Available.png) <span data-ttu-id="0fcd6-113">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="0fcd6-113">Available</span></span>|
|| ![Oof verfügbar](media/Presence_Available_OOF.png) <span data-ttu-id="0fcd6-115">Verfügbar, abwesend</span><span class="sxs-lookup"><span data-stu-id="0fcd6-115">Available, Out of Office</span></span> |
|  ![Ausgelastet](media/Presence_Busy.png) <span data-ttu-id="0fcd6-117">Ausgelastet</span><span class="sxs-lookup"><span data-stu-id="0fcd6-117">Busy</span></span> |  ![Ausgelastet](media/Presence_Busy.png) <span data-ttu-id="0fcd6-119">Ausgelastet</span><span class="sxs-lookup"><span data-stu-id="0fcd6-119">Busy</span></span>  |
|| ![Ausgelastet](media/Presence_Busy.png) <span data-ttu-id="0fcd6-121">Im Gespräch</span><span class="sxs-lookup"><span data-stu-id="0fcd6-121">In a call</span></span>|
|| ![Ausgelastet](media/Presence_Busy.png) <span data-ttu-id="0fcd6-123">In einer Besprechung</span><span class="sxs-lookup"><span data-stu-id="0fcd6-123">In a meeting</span></span> |
|| ![ausgelastet oof](media/Presence_Busy_OOF.png) <span data-ttu-id="0fcd6-125">Im Gespräch abwesend</span><span class="sxs-lookup"><span data-stu-id="0fcd6-125">In a call, out of office</span></span>|
|  ![Nicht stören](media/Presence_DND.png) <span data-ttu-id="0fcd6-127">Nicht stören</span><span class="sxs-lookup"><span data-stu-id="0fcd6-127">Do not disturb</span></span> ||
|| ![Nicht stören](media/Presence_DND.png) <span data-ttu-id="0fcd6-129">Einer Präsentation</span><span class="sxs-lookup"><span data-stu-id="0fcd6-129">Presenting</span></span>|
| ![Abwesend](media/Presence_Away.png) <span data-ttu-id="0fcd6-131">Abwesend</span><span class="sxs-lookup"><span data-stu-id="0fcd6-131">Away</span></span>| ![Abwesend](media/Presence_Away.png) <span data-ttu-id="0fcd6-133">Abwesend</span><span class="sxs-lookup"><span data-stu-id="0fcd6-133">Away</span></span>|
|| <span data-ttu-id="0fcd6-134">![Abwesend](media/Presence_Away.png) abwesend letzten gesehen *Zeit*</span><span class="sxs-lookup"><span data-stu-id="0fcd6-134">![away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Abwesend](media/Presence_Away.png) <span data-ttu-id="0fcd6-136">Bin gleich zurück</span><span class="sxs-lookup"><span data-stu-id="0fcd6-136">Be right back</span></span>| |
|| ![Abwesend](media/Presence_Away.png)  <span data-ttu-id="0fcd6-138">Nicht bei der Arbeit</span><span class="sxs-lookup"><span data-stu-id="0fcd6-138">Off Work</span></span>|
|| ![Offline](media/Presence_Offline.png) <span data-ttu-id="0fcd6-140">Offline</span><span class="sxs-lookup"><span data-stu-id="0fcd6-140">Offline</span></span> |
|| ![unbekannt](media/Presence_Unknown.png) <span data-ttu-id="0fcd6-142">Status unbekannt</span><span class="sxs-lookup"><span data-stu-id="0fcd6-142">Status unknown</span></span>|
||![blockiert](media/Presence_Blocked.png) <span data-ttu-id="0fcd6-144">Blockiert</span><span class="sxs-lookup"><span data-stu-id="0fcd6-144">Blocked</span></span> |
|| ![Abwesend](media/Presence_OOF.png) <span data-ttu-id="0fcd6-146">Abwesend</span><span class="sxs-lookup"><span data-stu-id="0fcd6-146">Out of Office</span></span>|
|||
 
<span data-ttu-id="0fcd6-147">Benutzer können ihre aktuellen Anwesenheitsstatus manuell auf einige Optionen festlegen, und deren Status Dient zum Abrufen und allen anderen Benutzern übernommen.</span><span class="sxs-lookup"><span data-stu-id="0fcd6-147">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="0fcd6-148">Zusätzliche Anwesenheitsinformationen Benutzerdetails werden auch automatisch aktualisiert, basierend auf Benutzeraktivität (beispielsweise verfügbar oder abwesend), Outlook-Kalenderstatus (wie in einer Besprechung) oder Teams app-Status (In einem Aufruf präsentieren angezeigt), um Zustände, die in der Liste eingezogen werden.</span><span class="sxs-lookup"><span data-stu-id="0fcd6-148">Additional user presence details are also automatically updated based on user activity (such as Available or Away), Outlook calendar states (such as In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="0fcd6-149">Es ist ein Timeout 15 Minuten Inaktivität, nach dem wird der Benutzer aktuelle Anwesenheitsstatus in Abwesend zurückgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="0fcd6-149">There is a 15 minute inactivity timeout, after which your users' current presence state will be reset to Away.</span></span>

<span data-ttu-id="0fcd6-150">Benutzer können angeben, die über unterbrechen können (in Kontakt treten Überschreiben einer Einstellung nicht stören).</span><span class="sxs-lookup"><span data-stu-id="0fcd6-150">Users can specify who can break through (contact them overriding a Do Not Disturb setting).</span></span> <span data-ttu-id="0fcd6-151">Diese Einstellungen sind verfügbar in-app.</span><span class="sxs-lookup"><span data-stu-id="0fcd6-151">These settings are available in-app.</span></span>

## <a name="teams-is-not-skype-for-business"></a><span data-ttu-id="0fcd6-152">Teams ist keine Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="0fcd6-152">Teams is not Skype for Business</span></span>

<span data-ttu-id="0fcd6-153">Die folgenden administratoreinstellung in Skype für Unternehmen unterscheiden sich in Teams:</span><span class="sxs-lookup"><span data-stu-id="0fcd6-153">The following Admin settings in Skype for Business are different in Teams:</span></span>
- <span data-ttu-id="0fcd6-154">Freigeben von Anwesenheitsinformationen wird immer in Teams für Benutzer in der Organisation aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0fcd6-154">Presence sharing is always enabled in Teams for users in the organization.</span></span> <span data-ttu-id="0fcd6-155">Datenschutz (entscheiden, die Anwesenheitsinformationen angezeigt werden) Konfiguration ist nicht verfügbar in Teams.</span><span class="sxs-lookup"><span data-stu-id="0fcd6-155">Privacy (deciding who can see Presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="0fcd6-156">Anwesenheit Freigabe für alle Benutzer (einschließlich Federated Dienste) ist für Benutzer in Teams immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0fcd6-156">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="0fcd6-157">Ihrer Kontaktliste (Wenn sie SfB in war) wird unter angezeigt **Chat > Kontakte** oder unter **Anrufe > Kontakte**.</span><span class="sxs-lookup"><span data-stu-id="0fcd6-157">Their contact list (if they had one in SfB) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="0fcd6-158">Client nicht stören und überzeugend Features sind für Benutzer in Teams immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0fcd6-158">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="0fcd6-159">Kalender (einschließlich OOF & andere Kalender Info) Integration ist für Benutzer in Teams immer aktiviert, wenn in Outlook integriert.</span><span class="sxs-lookup"><span data-stu-id="0fcd6-159">Calendar (includes OOF & other calendar info) integration  is always enabled for users in Teams if integrated with Outlook.</span></span>
- <span data-ttu-id="0fcd6-160">*Zuletzt gesehen* oder *Abwesend seit* (sofern in einer Umgebung mit zwei mit Skype für Unternehmen) Indikator ist für Benutzer in Teams immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0fcd6-160">The *Last seen* or *Away since* (if in a dual environment with Skype for Business) indicator is always enabled for users in Teams.</span></span>
- <span data-ttu-id="0fcd6-161">Festlegen einer benutzerdefinierten Anwesenheitsstatus ist für Benutzer in Teams nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0fcd6-161">Setting a custom presence status is not enabled for users in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="0fcd6-162">Die Möglichkeit zum Anpassen dieser Einstellungen einer Teams Admin wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0fcd6-162">The ability of a Teams Admin to customize these settings is not currently supported.</span></span>


## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="0fcd6-163">Koexistenz mit Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="0fcd6-163">Coexistence with Skype for Business</span></span>

<span data-ttu-id="0fcd6-164">Informationen zur Funktionsweise von Teams Anwesenheit bei Koexistenz mit Skype für Unternehmen finden Sie unter [Koexistenz mit Skype für Unternehmen](coexistence-chat-calls-presence.md) .</span><span class="sxs-lookup"><span data-stu-id="0fcd6-164">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when coexisting with Skype for Business.</span></span> 