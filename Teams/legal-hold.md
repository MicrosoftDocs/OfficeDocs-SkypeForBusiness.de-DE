---
title: Festlegen der gesetzlichen Aufbewahrungspflicht für einen Benutzer oder ein Team in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die gesetzliche Aufbewahrungspflicht für einen Benutzer oder ein Team in Microsoft Teams unter Verwendung des Security & Compliance Center festlegen können und welche Datenanforderungen für eine gesetzliche Aufbewahrung notwendig sind.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 25bd8e235be79ed805a854cbda2b4947f1c1269b
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968036"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a><span data-ttu-id="01361-103">Festlegen der gesetzlichen Aufbewahrungspflicht für einen Benutzer oder ein Team in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="01361-103">Place a Microsoft Teams user or team on legal hold</span></span>
==================================================

<span data-ttu-id="01361-p101">Um die gesetzliche Aufbewahrung für einen Benutzer oder ein Team festzulegen, navigieren Sie zum [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=854628). Wenn Sie einen neuen Anwendungsfall erstellen, wird die Option zum Aufbewahren von Postfächern und Sites angezeigt.</span><span class="sxs-lookup"><span data-stu-id="01361-p101">To put a user or a team on Legal Hold, navigate to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=854628). When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

> [!NOTE]
> <span data-ttu-id="01361-106">Beim Aufbewahren von Daten eines Benutzers werden nicht automatisch die Daten einer Gruppe aufbewahrt (oder umgekehrt).</span><span class="sxs-lookup"><span data-stu-id="01361-106">Placing a user on hold does not automatically place a group on hold or vice-versa.</span></span>

> [!NOTE]
> <span data-ttu-id="01361-107">Wir unterstützen noch keine Konfiguration für den rechtlichen Besitz privater Kanal Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="01361-107">We don’t yet support configuration for legal hold of private channel messages.</span></span> <span data-ttu-id="01361-108">Der rechtliche Halt von Dateien, die in privaten Kanälen freigegeben werden, wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="01361-108">Legal hold of files shared in private channels is supported.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01361-109">Wenn ein Benutzer oder eine Gruppe in Wartestellung gesetzt wird, bleiben alle Nachrichten-Kopien erhalten.</span><span class="sxs-lookup"><span data-stu-id="01361-109">When a user or group is placed on hold, all message copies will be retained.</span></span> <span data-ttu-id="01361-110">Beispiel: Clay hat eine Nachricht in einem Kanal gepostet und die Nachricht dann verändert.</span><span class="sxs-lookup"><span data-stu-id="01361-110">Example: Clay posted a message in a channel and then modified the message.</span></span> <span data-ttu-id="01361-111">In einem Aufbewahrungsszenario werden beide Kopien der Nachricht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="01361-111">In a hold scenario, both copies of the message are retained.</span></span> <span data-ttu-id="01361-112">Ohne die gesetzliche Aufbewahrungspflicht wird nur die aktuelle Nachricht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="01361-112">Without Legal Hold, only the latest message is retained.</span></span>

<span data-ttu-id="01361-113">In der Abbildung unten sehen Sie eine Untersuchung im Zusammenhang mit Clay.</span><span class="sxs-lookup"><span data-stu-id="01361-113">In the figure below, there is an investigation involving Clay.</span></span> <span data-ttu-id="01361-114">Clay ist ein Mitglied des Makler-Händler-Teams.</span><span class="sxs-lookup"><span data-stu-id="01361-114">Clay is a member of the Brokers-Dealers team.</span></span>

<span data-ttu-id="01361-115">Wenn für alle Kanäle, über die Clay Maklerpläne diskutiert haben könnte, eine gesetzliche Aufbewahrungspflicht festgelegt ist, stellen Sie sicher, dass die SharePoint-Site des Teams zur Siteliste „Gesetzliche Aufbewahrungspflicht“ sowie zu Clays OneDrive for Business-Site hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="01361-115">If we needed to Legal Hold all the places Clay could have discussed Brokering plans, ensure that the team’s SharePoint site is added to the Legal Hold site list, as well as Clay’s OneDrive for Business site.</span></span>

![Screenshot des Dialogfelds „Neuen Fallspeicher erstellen“](media/Place_a_Microsoft_Teams_user_or_team_on_legal_hold_image3.png)

<span data-ttu-id="01361-117">Zusammenfassung: Verwenden Sie die Tabelle unten, um zu verstehen, für welche Daten basierend auf den Datenanforderungen eine gesetzliche Aufbewahrungspflicht besteht.</span><span class="sxs-lookup"><span data-stu-id="01361-117">To recap, use the table below to understand what needs to be placed on Legal Hold based on data requirements:</span></span>

|<span data-ttu-id="01361-118">Szenario</span><span class="sxs-lookup"><span data-stu-id="01361-118">Scenario</span></span>  |<span data-ttu-id="01361-119">Was muss aufbewahrt werden</span><span class="sxs-lookup"><span data-stu-id="01361-119">What to place on hold</span></span>  |
|---------|---------|
|<span data-ttu-id="01361-120">**Private Microsoft Teams-Chats**</span><span class="sxs-lookup"><span data-stu-id="01361-120">**Microsoft Teams Private Chats**</span></span>     |<span data-ttu-id="01361-121">Benutzerpostfächer</span><span class="sxs-lookup"><span data-stu-id="01361-121">User mailbox</span></span>         |
|<span data-ttu-id="01361-122">**Microsoft Teams-Kanalchats**</span><span class="sxs-lookup"><span data-stu-id="01361-122">**Microsoft Teams Channel Chats**</span></span>    |<span data-ttu-id="01361-123">Für das Team verwendete Gruppenpostfach</span><span class="sxs-lookup"><span data-stu-id="01361-123">Group mailbox used for the team</span></span>         |
|<span data-ttu-id="01361-124">**Microsoft Teams-Inhalt (z. B. Wiki, Dateien)**</span><span class="sxs-lookup"><span data-stu-id="01361-124">**Microsoft Teams Content (e.g. Wiki, Files)**</span></span>     |<span data-ttu-id="01361-125">Vom Team verwendete SharePoint-Site</span><span class="sxs-lookup"><span data-stu-id="01361-125">SharePoint site used by the team</span></span>         |
|<span data-ttu-id="01361-126">**Privater Inhalt**</span><span class="sxs-lookup"><span data-stu-id="01361-126">**Private Content**</span></span>     |<span data-ttu-id="01361-127">OneDrive for Business-Site des Benutzers</span><span class="sxs-lookup"><span data-stu-id="01361-127">OneDrive for Business site of the user</span></span>         |
