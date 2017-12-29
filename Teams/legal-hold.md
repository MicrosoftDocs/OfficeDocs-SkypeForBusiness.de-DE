---
title: "Festlegen der gesetzlichen Aufbewahrungspflicht für einen Benutzer oder ein Team in Microsoft Teams | Microsoft-Support"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Hier erfahren Sie, wie Sie die gesetzliche Aufbewahrungspflicht für einen Benutzer oder ein Team in Microsoft Teams unter Verwendung des Security & Compliance Center festlegen können und welche Datenanforderungen für eine gesetzliche Aufbewahrung notwendig sind."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 290462b78a0424bc02d1cbe3df5ae65672e187f7
ms.sourcegitcommit: 83aa84750e0bd210c24b3bd7315020a451d3f056
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2017
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a><span data-ttu-id="dabae-103">Festlegen der gesetzlichen Aufbewahrungspflicht für einen Benutzer oder ein Team in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dabae-103">Place a Microsoft Teams user or team on legal hold</span></span>
==================================================

<span data-ttu-id="dabae-p101">Um die gesetzliche Aufbewahrung für einen Benutzer oder ein Team festzulegen, navigieren Sie zum [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=854628). Wenn Sie einen neuen Anwendungsfall erstellen, wird die Option zum Aufbewahren von Postfächern und Sites angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dabae-p101">To put a user or a team on Legal Hold, navigate to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=854628). When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

> [!NOTE]
> <span data-ttu-id="dabae-106">Beim Aufbewahren von Daten eines Benutzers werden nicht automatisch die Daten einer Gruppe aufbewahrt (oder umgekehrt).</span><span class="sxs-lookup"><span data-stu-id="dabae-106">Placing a user on hold does not automatically place a group on hold or vice-versa.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dabae-107">Wenn für Daten eines Benutzers oder einer Gruppe die In-Situ-Speicherung aktiviert ist, werden alle Nachrichtenkopien beibehalten.</span><span class="sxs-lookup"><span data-stu-id="dabae-107">When a user or group is placed on hold, all message copies will be retained.</span></span> <span data-ttu-id="dabae-108">Beispiel: Clay hat eine Nachricht in einem Kanal gepostet und die Nachricht dann verändert.</span><span class="sxs-lookup"><span data-stu-id="dabae-108">Example: Clay posted a message in a channel and then modified the message.</span></span> <span data-ttu-id="dabae-109">In einem Aufbewahrungsszenario werden beide Kopien der Nachricht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="dabae-109">In a hold scenario, both copies of the message are retained.</span></span> <span data-ttu-id="dabae-110">Ohne die gesetzliche Aufbewahrungspflicht wird nur die aktuelle Nachricht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="dabae-110">Without Legal Hold, only the latest message is retained.</span></span>



<span data-ttu-id="dabae-111">In der Abbildung unten sehen Sie eine Untersuchung im Zusammenhang mit Clay.</span><span class="sxs-lookup"><span data-stu-id="dabae-111">In the figure below, there is an investigation involving Clay.</span></span> <span data-ttu-id="dabae-112">Clay ist ein Mitglied des Makler-Händler-Teams.</span><span class="sxs-lookup"><span data-stu-id="dabae-112">Clay is a member of the Brokers-Dealers team.</span></span>

<span data-ttu-id="dabae-113">Wenn für alle Kanäle, über die Clay Maklerpläne diskutiert haben könnte, eine gesetzliche Aufbewahrungspflicht festgelegt ist, stellen Sie sicher, dass die SharePoint-Site des Teams zur Siteliste „Gesetzliche Aufbewahrungspflicht“ sowie zu Clays OneDrive for Business-Site hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="dabae-113">If we needed to Legal Hold all the places Clay could have discussed Brokering plans, ensure that the team’s SharePoint site is added to the Legal Hold site list, as well as Clay’s OneDrive for Business site.</span></span>

![Screenshot des Dialogfelds „Neuen Fallspeicher erstellen“](media/Place_a_Microsoft_Teams_user_or_team_on_legal_hold_image3.png)

<span data-ttu-id="dabae-115">Zusammenfassung: Verwenden Sie die Tabelle unten, um zu verstehen, für welche Daten basierend auf den Datenanforderungen eine gesetzliche Aufbewahrungspflicht besteht.</span><span class="sxs-lookup"><span data-stu-id="dabae-115">To recap, use the table below to understand what needs to be placed on Legal Hold based on data requirements:</span></span>

|<span data-ttu-id="dabae-116">Szenario</span><span class="sxs-lookup"><span data-stu-id="dabae-116">Scenario</span></span>  |<span data-ttu-id="dabae-117">Was muss aufbewahrt werden</span><span class="sxs-lookup"><span data-stu-id="dabae-117">What to place on hold</span></span>  |
|---------|---------|
|<span data-ttu-id="dabae-118">**Private Microsoft Teams-Chats**</span><span class="sxs-lookup"><span data-stu-id="dabae-118">**Microsoft Teams Private Chats**</span></span>     |<span data-ttu-id="dabae-119">Benutzerpostfächer</span><span class="sxs-lookup"><span data-stu-id="dabae-119">User mailbox</span></span>         |
|<span data-ttu-id="dabae-120">**Microsoft Teams-Kanalchats**</span><span class="sxs-lookup"><span data-stu-id="dabae-120">**Microsoft Teams Channel Chats**</span></span>    |<span data-ttu-id="dabae-121">Für das Team verwendete Gruppenpostfach</span><span class="sxs-lookup"><span data-stu-id="dabae-121">Group mailbox used for the team</span></span>         |
|<span data-ttu-id="dabae-122">**Microsoft Teams-Inhalt (z. B. Wiki, Dateien)**</span><span class="sxs-lookup"><span data-stu-id="dabae-122">**Microsoft Teams Content (e.g. Wiki, Files)**</span></span>     |<span data-ttu-id="dabae-123">Vom Team verwendete SharePoint-Site</span><span class="sxs-lookup"><span data-stu-id="dabae-123">SharePoint site used by the team</span></span>         |
|<span data-ttu-id="dabae-124">**Privater Inhalt**</span><span class="sxs-lookup"><span data-stu-id="dabae-124">**Private Content**</span></span>     |<span data-ttu-id="dabae-125">OneDrive for Business-Site des Benutzers</span><span class="sxs-lookup"><span data-stu-id="dabae-125">OneDrive for Business site of the user</span></span>         |
