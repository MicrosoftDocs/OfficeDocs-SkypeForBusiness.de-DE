---
title: Einrichten und Verwalten der Kanal Moderation
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Kanäle für die Moderation in Microsoft Teams einrichten, einschließlich des Hinzufügens von Teammitgliedern als Kanal Moderatoren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 77622bd2920ce0453d6ccbdbeb55696fc2925271
ms.sourcegitcommit: 56ceda54ca48d2984298d4d1f26017c0147d4431
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2020
ms.locfileid: "43505602"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a><span data-ttu-id="3a558-103">Einrichten und Verwalten der Kanal Moderation in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3a558-103">Set up and manage channel moderation in Microsoft Teams</span></span>

<span data-ttu-id="3a558-104">In Microsoft Teams können Teambesitzer die Moderation für einen Standardkanal aktivieren, um zu steuern, wer neue Beiträge starten und auf Beiträge in diesem Kanal Antworten kann.</span><span class="sxs-lookup"><span data-stu-id="3a558-104">In Microsoft Teams, team owners can turn on moderation for a standard channel to control who can start new posts and reply to posts in that channel.</span></span>

<span data-ttu-id="3a558-105">Teambesitzer können auch Teammitglieder als Moderatoren hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3a558-105">Team owners can also add team members as moderators.</span></span> <span data-ttu-id="3a558-106">Ein Teambesitzer verfügt möglicherweise nicht über die Fachkenntnisse auf Kanalebene, um die Kanal Moderation optimal zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3a558-106">A team owner might not have the subject matter expertise at the channel level to best support channel moderation.</span></span> <span data-ttu-id="3a558-107">Durch das zulassen, dass bestimmte Teammitglieder einen Kanal moderieren, wird die Verantwortung für die Verwaltung von Inhalt und Kontext innerhalb eines Kanals von Teambesitzern und Kanal Moderatoren geteilt.</span><span class="sxs-lookup"><span data-stu-id="3a558-107">By allowing specific team members to moderate a channel, the responsibility of managing content and context within a channel is shared between team owners and channel moderators.</span></span> <span data-ttu-id="3a558-108">Beispielsweise kann ein Teambesitzer Geschäftsbesitzer oder Inhaltsbesitzer als Moderatoren hinzufügen, wodurch Sie die Informationsfreigabe in diesem Kanal steuern können.</span><span class="sxs-lookup"><span data-stu-id="3a558-108">For example, a team owner can add business owners or content owners as moderators, which lets them control information sharing in that channel.</span></span>

> [!NOTE]
> <span data-ttu-id="3a558-109">Kanal Moderation steht für Standardkanäle zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3a558-109">Channel moderation is available for standard channels.</span></span> <span data-ttu-id="3a558-110">Sie ist für den Kanal "Allgemein" oder "Privat" nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3a558-110">It's not available for the General channel or private channels.</span></span>

## <a name="what-can-a-channel-moderator-do"></a><span data-ttu-id="3a558-111">Was kann ein Kanal Moderator tun?</span><span class="sxs-lookup"><span data-stu-id="3a558-111">What can a channel moderator do?</span></span>

<span data-ttu-id="3a558-112">Kanal Moderatoren können:</span><span class="sxs-lookup"><span data-stu-id="3a558-112">Channel moderators can:</span></span>

- <span data-ttu-id="3a558-113">Neue Beiträge im Kanal starten.</span><span class="sxs-lookup"><span data-stu-id="3a558-113">Start new posts in the channel.</span></span> <span data-ttu-id="3a558-114">Wenn die Moderation für einen Kanal aktiviert ist, können nur Moderatoren neue Beiträge in diesem Kanal starten.</span><span class="sxs-lookup"><span data-stu-id="3a558-114">When moderation is turned on for a channel, only moderators can start new posts in that channel.</span></span>
- <span data-ttu-id="3a558-115">Hinzufügen und Entfernen von Teammitgliedern als Moderatoren zu einem Kanal.</span><span class="sxs-lookup"><span data-stu-id="3a558-115">Add and remove team members as moderators to a channel.</span></span> <span data-ttu-id="3a558-116">Beachten Sie, dass Teambesitzer standardmäßig Kanal Moderatoren sind und nicht entfernt werden können.</span><span class="sxs-lookup"><span data-stu-id="3a558-116">Keep in mind that by default, team owners are channel moderators and can't be removed.</span></span>
- <span data-ttu-id="3a558-117">Steuern, ob Teammitglieder auf vorhandene Kanal Nachrichten antworten können und ob Bots und Connectors Kanal Nachrichten senden können.</span><span class="sxs-lookup"><span data-stu-id="3a558-117">Control whether team members can reply to existing channel messages and whether bots and connectors can submit channel messages.</span></span>

## <a name="scenarios"></a><span data-ttu-id="3a558-118">Szenarien</span><span class="sxs-lookup"><span data-stu-id="3a558-118">Scenarios</span></span>

<span data-ttu-id="3a558-119">Nachfolgend finden Sie einige Beispiele dafür, wie Ihre Organisation Kanal Moderation in Teams verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="3a558-119">Here's some examples of how your organization can use channel moderation in Teams.</span></span>

### <a name="use-a-channel-as-an-announcement-channel"></a><span data-ttu-id="3a558-120">Verwenden eines Kanals als Ankündigungs Kanal</span><span class="sxs-lookup"><span data-stu-id="3a558-120">Use a channel as an announcement channel</span></span>

<span data-ttu-id="3a558-121">Das Marketing Team verwendet einen bestimmten Kanal, um wichtige Projektankündigungen und-Ergebnisse freizugeben.</span><span class="sxs-lookup"><span data-stu-id="3a558-121">The Marketing team uses a specific channel to share key project announcements and deliverables.</span></span> <span data-ttu-id="3a558-122">Manchmal veröffentlichen Teammitglieder Inhalte in dem Kanal, der in anderen Kanälen angemessen gehört.</span><span class="sxs-lookup"><span data-stu-id="3a558-122">Sometimes team members post content to the channel that more appropriately belongs in other channels.</span></span> <span data-ttu-id="3a558-123">Der Teambesitzer möchte die Informationsfreigabe im Kanal auf Ankündigungen beschränken, damit die Teammitglieder diesen Kanal verwenden können, um über das Wesentliche zu informieren.</span><span class="sxs-lookup"><span data-stu-id="3a558-123">The team owner wants to restrict information sharing in the channel to only announcements so that team members can use that channel to stay on top of what's important.</span></span>

<span data-ttu-id="3a558-124">In diesem Szenario fügt der Teambesitzer Marketing Leads als Moderatoren hinzu, damit Sie Ankündigungen im Kanal veröffentlichen und die Möglichkeit für Teammitglieder, auf Nachrichten in diesem Kanal zu antworten, deaktivieren können.</span><span class="sxs-lookup"><span data-stu-id="3a558-124">In this scenario, the team owner adds Marketing leads as moderators so they can post announcements in the channel and turns off the ability for team members to reply to messages in that channel.</span></span>

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a><span data-ttu-id="3a558-125">Verwenden eines Kanals für Kurs Diskussionen in Teams für Education</span><span class="sxs-lookup"><span data-stu-id="3a558-125">Use a channel for class discussions in Teams for Education</span></span>

<span data-ttu-id="3a558-126">In Teams für Bildung möchte ein Wissenschaftslehrer einen Kanal verwenden, um Schüler in gezielte Diskussionen zu bestimmten Unterrichtsthemen einzubinden.</span><span class="sxs-lookup"><span data-stu-id="3a558-126">In Teams for Education, a science teacher wants to use a channel to engage students in focused discussions on specific classroom topics.</span></span>

<span data-ttu-id="3a558-127">In diesem Szenario ermöglicht der Lehrer seinen Lehrassistenten, den Kanal zu moderieren.</span><span class="sxs-lookup"><span data-stu-id="3a558-127">In this scenario, the teacher allows their teaching assistants to moderate the channel.</span></span> <span data-ttu-id="3a558-128">Die Lehrkräfte können dann neue Beiträge erstellen, um die Diskussionen mit den Kursteilnehmern zu initiieren und voranzutreiben.</span><span class="sxs-lookup"><span data-stu-id="3a558-128">The teaching assistants can then create new posts to initiate and drive discussions with students.</span></span>

## <a name="manage-channel-moderation"></a><span data-ttu-id="3a558-129">Verwalten der Kanal Moderation</span><span class="sxs-lookup"><span data-stu-id="3a558-129">Manage channel moderation</span></span>

<span data-ttu-id="3a558-130">Wechseln Sie in Microsoft Teams zum Kanal, klicken Sie auf **Weitere Optionen...**  >  **Kanal verwalten**.</span><span class="sxs-lookup"><span data-stu-id="3a558-130">In Teams, go to the channel, click **More options ...** > **Manage channel**.</span></span> <span data-ttu-id="3a558-131">Hier können Sie die Moderation aktivieren und deaktivieren, Teammitglieder als Moderatoren hinzufügen und Einstellungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="3a558-131">From here you can turn on and turn off moderation, add team members as moderators, and set preferences.</span></span>

<span data-ttu-id="3a558-132">Kanal Moderation ist eine kanalspezifische Einstellung.</span><span class="sxs-lookup"><span data-stu-id="3a558-132">Channel moderation is a per-channel setting.</span></span> <span data-ttu-id="3a558-133">Für die Kanal Moderation gibt es keine Einstellung auf Mandantenebene.</span><span class="sxs-lookup"><span data-stu-id="3a558-133">There's no tenant-level setting for channel moderation.</span></span> <span data-ttu-id="3a558-134">Wenn Sie möchten, dass wir eine Kanal Moderations Einstellung auf Mandantenebene hinzufügen, fordern Sie diese in [Teams UserVoice](https://microsoftteams.uservoice.com/)an.</span><span class="sxs-lookup"><span data-stu-id="3a558-134">If you'd like us to add a tenant-level channel moderation setting, request it on [Teams UserVoice](https://microsoftteams.uservoice.com/).</span></span>

![Manage-Channel-Moderation-in-Teams-Preferences. png](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a><span data-ttu-id="3a558-136">Aktivieren oder Deaktivieren der Moderation für einen Kanal</span><span class="sxs-lookup"><span data-stu-id="3a558-136">Turn on or turn off moderation for a channel</span></span>

<span data-ttu-id="3a558-137">Standardmäßig ist Moderation deaktiviert, was bedeutet, dass die üblichen Kanaleinstellungen für Teambesitzer und Teammitglieder gelten.</span><span class="sxs-lookup"><span data-stu-id="3a558-137">By default, moderation is off, which means that the usual channel settings apply to team owners and team members.</span></span> <span data-ttu-id="3a558-138">So können Sie beispielsweise neue Beiträge nur auf Teammitglieder einschränken oder allen, einschließlich Gästen, erlauben, neue Beiträge zu starten.</span><span class="sxs-lookup"><span data-stu-id="3a558-138">For example, you can restrict new posts to only team members or allow everyone, including guests, to start new posts.</span></span>

<span data-ttu-id="3a558-139">Wenn Sie die Moderation für einen Kanal aktivieren möchten **, klicken Sie**unter **Kanal Moderation**auf ein.</span><span class="sxs-lookup"><span data-stu-id="3a558-139">To turn on moderation for a channel, under **Channel moderation**, click **On**.</span></span> <span data-ttu-id="3a558-140">Wenn die Kanal Moderation aktiviert ist, können nur Moderatoren neue Beiträge beginnen.</span><span class="sxs-lookup"><span data-stu-id="3a558-140">When channel moderation is on, only moderators can start new posts.</span></span> 

### <a name="add-or-remove-channel-moderators"></a><span data-ttu-id="3a558-141">Hinzufügen oder Entfernen von Kanal Moderatoren</span><span class="sxs-lookup"><span data-stu-id="3a558-141">Add or remove channel moderators</span></span>

<span data-ttu-id="3a558-142">Klicken Sie unter **Wer sind die Moderatoren?** auf **Verwalten**, und fügen Sie dann Teammitglieder als Moderatoren hinzu oder entfernen Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="3a558-142">Under **Who are the moderators?**, click **Manage**, and then add or remove team members as moderators.</span></span> <span data-ttu-id="3a558-143">Team Besitzer und Moderatoren können andere Moderatoren hinzufügen und entfernen.</span><span class="sxs-lookup"><span data-stu-id="3a558-143">Team owners and moderators can add and remove other moderators.</span></span>  

### <a name="set-team-member-permissions"></a><span data-ttu-id="3a558-144">Einrichten von Berechtigungen für Teammitglieder</span><span class="sxs-lookup"><span data-stu-id="3a558-144">Set team member permissions</span></span>

<span data-ttu-id="3a558-145">Aktivieren Sie unter **Team Mitglied-Berechtigungen**die Kontrollkästchen neben den Aktivitäten, die Sie zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="3a558-145">Under **Team member permissions**, select the check boxes next to the activities  you want to allow.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3a558-146">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="3a558-146">Related topics</span></span>

- [<span data-ttu-id="3a558-147">Übersicht über Teams und Kanäle in Teams</span><span class="sxs-lookup"><span data-stu-id="3a558-147">Overview of teams and channels in Teams</span></span>](teams-channels-overview.md)
