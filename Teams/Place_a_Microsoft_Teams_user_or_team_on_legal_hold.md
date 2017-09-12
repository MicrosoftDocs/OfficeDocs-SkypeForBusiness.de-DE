---
title: "Festlegen der gesetzlichen Aufbewahrungspflicht für einen Benutzer oder ein Team in Microsoft Teams | Microsoft-Support"
author: LolaJacobsen
ms.author: lolaj
manager: serdar
ms.date: 08/10/2017
ms.topic: solution
ms.prod: teams
description: "Hier erfahren Sie, wie Sie die gesetzliche Aufbewahrungspflicht für einen Benutzer oder ein Team in Microsoft Teams unter Verwendung des Sicherheits- und Compliance-Portals festlegen können und welche Datenanforderungen für eine gesetzliche Aufbewahrung notwendig sind."
ms.openlocfilehash: b4e953447b683ed40d1b624739fde0b7d626e1b3
ms.sourcegitcommit: 3b9b3f07f4f67cd5f43da68f48d62222d7e49167
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2017
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a><span data-ttu-id="450b1-103">Festlegen der gesetzlichen Aufbewahrungspflicht für einen Benutzer oder ein Team in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="450b1-103">Place a Microsoft Teams user or team on legal hold</span></span>
=======================================

<span data-ttu-id="450b1-p101">Um die gesetzliche Aufbewahrung für einen Benutzer oder ein Team festzulegen, navigieren Sie zum [Security and Compliance-Portal](https://go.microsoft.com/fwlink/?linkid=854628). Wenn Sie einen neuen Anwendungsfall erstellen, wird die Option zum Aufbewahren von Postfächern und Sites angezeigt.</span><span class="sxs-lookup"><span data-stu-id="450b1-p101">To put a user or a team on Legal Hold, navigate to the [Security and Compliance Portal](https://go.microsoft.com/fwlink/?linkid=854628). When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

|||
|---------|---------|
|![](media/Place_a_Microsoft_Teams_user_or_team_on_legal_hold_image1.png)<br></br> <span data-ttu-id="450b1-106">Hinweis</span><span class="sxs-lookup"><span data-stu-id="450b1-106">Note:</span></span>     |<span data-ttu-id="450b1-107">Beim Aufbewahren von Daten eines Benutzers werden nicht automatisch die Daten einer Gruppe aufbewahrt (oder umgekehrt).</span><span class="sxs-lookup"><span data-stu-id="450b1-107">Placing a user on hold does not automatically place a group on hold or vice-versa.</span></span>         |
|![](media/Place_a_Microsoft_Teams_user_or_team_on_legal_hold_image2.png)<br></br> <span data-ttu-id="450b1-108">Wichtig</span><span class="sxs-lookup"><span data-stu-id="450b1-108">Important:</span></span>     |<span data-ttu-id="450b1-p102">Wenn die Daten eines Benutzers oder einer Gruppe aufbewahrt werden, werden alle Nachrichtenkopien beibehalten. Beispiel: Bob hat eine Nachricht in einem Kanal gepostet und die Nachricht dann verändert. In einem Aufbewahrungsszenario werden beide Kopien der Nachricht beibehalten. Ohne die gesetzliche Aufbewahrungspflicht wird nur die aktuelle Nachricht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="450b1-p102">When a user or group is placed on hold, all message copies will be retained. Example: Bob posted a message in a channel and then modified the message. In a hold scenario, both copies of the message are retained. Without Legal Hold, only the latest message is retained.</span></span>         |

<span data-ttu-id="450b1-p103">In der Abbildung unten sehen Sie eine Untersuchung im Zusammenhang mit Bob. Bob ist ein Mitglied des Produktionsspezifikationsteams.</span><span class="sxs-lookup"><span data-stu-id="450b1-p103">In the figure below, there is an investigation involving Bob. Bob is a member of the Manufacturing Specs team.</span></span>

<span data-ttu-id="450b1-115">Wenn für alle Kanäle, über die Bob Produktionspläne diskutiert haben könnte, eine gesetzliche Aufbewahrungspflicht festgelegt ist, stellen Sie sicher, dass die SharePoint-Site des Teams zur Siteliste „Gesetzliche Aufbewahrungspflicht“ sowie zu Bobs OneDrive for Business-Site hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="450b1-115">If we needed to Legal Hold all the places Bob could have discussed Manufacturing plans, ensure that the team’s SharePoint site is added to the Legal Hold site list, as well as Bob’s OneDrive for Business site.</span></span>

![](media/Place_a_Microsoft_Teams_user_or_team_on_legal_hold_image3.png)

<span data-ttu-id="450b1-116">Zusammenfassung: Verwenden Sie die Tabelle unten, um zu verstehen, für welche Daten basierend auf den Datenanforderungen eine gesetzliche Aufbewahrungspflicht besteht.</span><span class="sxs-lookup"><span data-stu-id="450b1-116">To recap, use the table below to understand what needs to be placed on Legal Hold based on data requirements:</span></span>

|<span data-ttu-id="450b1-117">Szenario</span><span class="sxs-lookup"><span data-stu-id="450b1-117">Scenario</span></span>  |<span data-ttu-id="450b1-118">Was muss aufbewahrt werden</span><span class="sxs-lookup"><span data-stu-id="450b1-118">What to place on hold</span></span>  |
|---------|---------|
|<span data-ttu-id="450b1-119">**Private Microsoft Teams-Chats**</span><span class="sxs-lookup"><span data-stu-id="450b1-119">**Microsoft Teams Private Chats**</span></span>     |<span data-ttu-id="450b1-120">Benutzerpostfächer</span><span class="sxs-lookup"><span data-stu-id="450b1-120">User mailbox</span></span>         |
|<span data-ttu-id="450b1-121">**Microsoft Teams-Kanalchats**</span><span class="sxs-lookup"><span data-stu-id="450b1-121">**Microsoft Teams Channel Chats**</span></span>    |<span data-ttu-id="450b1-122">Für das Team verwendete Gruppenpostfach</span><span class="sxs-lookup"><span data-stu-id="450b1-122">Group mailbox used for the team</span></span>         |
|<span data-ttu-id="450b1-123">**Microsoft Teams-Inhalt (z. B. Wiki, Dateien)**</span><span class="sxs-lookup"><span data-stu-id="450b1-123">**Microsoft Teams Content (e.g. Wiki, Files)**</span></span>     |<span data-ttu-id="450b1-124">Vom Team verwendete SharePoint-Site</span><span class="sxs-lookup"><span data-stu-id="450b1-124">SharePoint site used by the team</span></span>         |
|<span data-ttu-id="450b1-125">**Privater Inhalt**</span><span class="sxs-lookup"><span data-stu-id="450b1-125">**Private Content**</span></span>     |<span data-ttu-id="450b1-126">OneDrive for Business-Site des Benutzers</span><span class="sxs-lookup"><span data-stu-id="450b1-126">OneDrive for Business site of the user</span></span>         |
