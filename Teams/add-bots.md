---
title: "Hinzufügen von Bots für private Chats und Kanäle in Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Hier erfahren Sie, wie Sie in Microsoft Teams Bots für private Chats und Kanäle hinzufügen, benutzerdefinierte Bots erstellen und Ihren eigenen Bot für private Chats querladen."
ms.openlocfilehash: c7f2aec398728f310fab780e96d4df09e4b7f582
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2017
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="a5c91-103">Hinzufügen von Bots für private Chats und Kanäle in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a5c91-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="a5c91-p101">Bots sind automatisierte Programme, die Fragen beantworten oder Updates und Benachrichtigungen zu Details bereitstellen, für die Benutzer sich interessieren oder über die sie stets informiert sein möchten. Über Bots können Benutzer in Form von Chatunterhaltungen in Microsoft Teams mit Clouddiensten wie Aufgabenverwaltung, Planung und Umfragen interagieren. Bots für Microsoft Teams basieren auf [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370), und die mit diesem Framework entwickelten Bots können leicht für Microsoft Teams aktiviert werden. Weitere Informationen finden Sie unter [Aktivieren von Microsoft Teams-Funktionen in Ihrer Office 365-Organisation](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="a5c91-p101">Bots are automated programs that are set up to respond to queries or give updates and notifications about details users find interesting or want to stay informed about. Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams. Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370) and the bots that are developed using this framework can be enabled easily for Microsoft Teams.</span></span>

<span data-ttu-id="a5c91-p102">Zurzeit unterstützt Microsoft Teams Bots in privaten Chats und in Kanälen in einem Team. Administratoren können steuern, ob die Verwendung von Bots innerhalb des Office 365-Mandanten zulässig oder untersagt ist.<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="a5c91-p102">Currently, Microsoft Teams support bots in private chats and channels within a team. Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="a5c91-111">In Microsoft Teams können Bots genutzt werden, die von der Community entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="a5c91-111">Bots developed by the community can be leveraged within Microsoft Teams.</span></span> <span data-ttu-id="a5c91-112">Die Funktionen des Bots und das Querladen von Bots müssen auf Mandantenebene aktiviert werden, damit benutzerdefinierte Bots funktionieren.</span><span class="sxs-lookup"><span data-stu-id="a5c91-112">The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional.</span></span> <span data-ttu-id="a5c91-113">Bots können in privaten Chats oder in Kanälen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a5c91-113">Bots can be used in private chats or in channels.</span></span> <span data-ttu-id="a5c91-114">Für Kanäle können Teambesitzer oder -mitglieder Bots hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a5c91-114">For channels, team owners or members can add bots.</span></span>

<span data-ttu-id="a5c91-115">Weitere Informationen finden Sie unter [Apps und Dienste](https://support.office.com/en-us/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) im Abschnitt „Verwenden von Bots“.</span><span class="sxs-lookup"><span data-stu-id="a5c91-115">For more information, see the section "Using bots" in [Apps and services](https://support.office.com/en-us/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span></span> 








 

<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="a5c91-116">Erstellen von benutzerdefinierten Bots für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a5c91-116">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="a5c91-p104">Mit Microsoft Bot Framework können Sie leicht einen Bot erstellen, der in Ihre Branchenanwendungen integriert werden kann. Im Leitfaden zum [Erstellen und Testen eines Bots für Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) erfahren Sie, wie Sie Ihre eigenen Bots entwickeln und veröffentlichen können.</span><span class="sxs-lookup"><span data-stu-id="a5c91-p104">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework. Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="a5c91-119">Wenn Sie einen Bot erstellen und in Bot Framework registrieren, können Sie wählen, ob er veröffentlicht werden soll.</span><span class="sxs-lookup"><span data-stu-id="a5c91-119">When you create a bot and register it with the Bot Framework, you can choose to publish it.</span></span> <span data-ttu-id="a5c91-120">Wenn Sie den Bot nicht veröffentlichen, bleibt er privat.</span><span class="sxs-lookup"><span data-stu-id="a5c91-120">If you don't publish it, the bot remains private.</span></span> <span data-ttu-id="a5c91-121">Sie können auch festlegen, dass sich die Benutzer vor der Verwendung des Bots anmelden müssen.</span><span class="sxs-lookup"><span data-stu-id="a5c91-121">You can also require your users to log in before using the bot.</span></span> <span data-ttu-id="a5c91-122">Dadurch stellen Sie sicher, dass nur Mitarbeiter Ihrer Organisation auf den Bot zugreifen können, selbst wenn die Anwendungs-ID des Bots bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="a5c91-122">Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known.</span></span> <span data-ttu-id="a5c91-123">Ein [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372)-Codebeispiel auf GitHub zeigt, wie Sie mithilfe von Bots Benutzer gegenüber Active Directory authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="a5c91-123">See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="a5c91-124">Bots können mit dem [Bot Framework-Emulator](https://go.microsoft.com/fwlink/?linkid=854373) getestet werden, bevor sie für Ihre Teams bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a5c91-124">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="a5c91-125">Querladen Ihres eigenen Bots für private Chats</span><span class="sxs-lookup"><span data-stu-id="a5c91-125">Side load your own bot for private chat</span></span>
---------------------------------------

1.  <span data-ttu-id="a5c91-126">Wenn Sie Ihren Bot erstellt haben, navigieren Sie zur **Botdashboard**-[Seite](https://go.microsoft.com/fwlink/?linkid=854374) für den entwickelten Bot, und kopieren Sie unter **Details** die **Microsoft-App-ID**.![Screenshot der Detailseite für einen Bot mit hervorgehobener Microsoft-App-ID](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span><span class="sxs-lookup"><span data-stu-id="a5c91-126">After you have created your bot, go to the **Bot Dashboard** [page](https://go.microsoft.com/fwlink/?linkid=854374) for the bot you developed, and then under **Details**, copy the **Microsoft App ID**.![Screenshot of details page for a bot with the Microsoft App ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span></span> 



2.  <span data-ttu-id="a5c91-127">Wählen Sie in Microsoft Teams im Bereich **Chat** das **Symbol zum Hinzufügen eines Chats** aus.</span><span class="sxs-lookup"><span data-stu-id="a5c91-127">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**. For To:, paste your bot's Microsoft app ID.</span></span> <span data-ttu-id="a5c91-128">Fügen Sie in **An:** die **Microsoft-App-ID** Ihres Bots ein.</span><span class="sxs-lookup"><span data-stu-id="a5c91-128">For **To**, paste your bot's **Microsoft app ID**.</span></span> <span data-ttu-id="a5c91-129">![Screenshot eines Chatbereichs mit dem hervorgehobenen Symbol zum Hinzufügen eines Chats und der hervorgehobenen Zeile „An“ mit der Microsoft-App-ID](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span><span class="sxs-lookup"><span data-stu-id="a5c91-129">![Screenshot of a chat pane with the icon for Add chat and the To line with the Microsoft app ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span></span>



3.  <span data-ttu-id="a5c91-130">Die App-ID wird in den **Botnamen** aufgelöst. Dann können Sie eine Chatunterhaltung mit dem Bot beginnen.</span><span class="sxs-lookup"><span data-stu-id="a5c91-130">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>
