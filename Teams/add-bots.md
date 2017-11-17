---
title: "Hinzufügen von Bots für private Chats und Kanäle in Microsoft Teams | Microsoft-Support"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Hier erfahren Sie, wie Sie in Microsoft Teams Bots für private Chats und Kanäle hinzufügen, benutzerdefinierte Bots erstellen und Ihren eigenen Bot für private Chats querladen."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 1ada4bbc135498abe62fa721ad6814f1f67fb841
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2017
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="6b73a-103">Hinzufügen von Bots für private Chats und Kanäle in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6b73a-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="6b73a-p101">Bots sind automatisierte Programme, die so eingerichtet sind, dass sie auf Abfragen reagieren oder Updates und Benachrichtigungen zu Details bereitstellen, für die Benutzer sich interessieren oder über die sie stets informiert sein möchten. Über Bots können Benutzer durch Chatunterhaltungen in Microsoft Teams mit Clouddiensten wie Aufgabenverwaltung, Planung und Umfragen interagieren. Bots für Microsoft Teams basieren auf [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370), und die mit diesem Framework entwickelten Bots können leicht für Microsoft Teams aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="6b73a-p101">Bots are automated programs that are set up to respond to queries or give updates and notifications about details users find interesting or want to stay informed about. Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams. Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370) and the bots that are developed using this framework can be enabled easily for Microsoft Teams.</span></span>

<span data-ttu-id="6b73a-p102">Zurzeit unterstützt Microsoft Teams Bots in privaten Chats und in Kanälen in einem Team. Administratoren können steuern, ob die Verwendung von Bots innerhalb des Office 365-Mandanten zulässig oder untersagt ist.<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="6b73a-p102">Currently, Microsoft Teams support bots in private chats and channels within a team. Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="6b73a-p103">In Microsoft Teams können Bots genutzt werden, die von der Community entwickelt und verfügbar gemacht wurden. Die Funktionen des Bots und das Querladen von Bots müssen auf Mandantenebene aktiviert werden, damit benutzerdefinierte Bots funktionieren. Bots können in privaten Chats oder in Kanälen verwendet werden. Für Kanäle können Teambesitzer oder -mitglieder Bots hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6b73a-p103">Bots developed by the community and are made available, can be leveraged within Microsoft Teams. The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional. Bots can be used in private chats or in channels. For channels, team owners or members can add bots.</span></span>

<a name="add-bots-for-private-chat-and-channels"></a><span data-ttu-id="6b73a-113">Hinzufügen von Bots für private Chats und Kanäle</span><span class="sxs-lookup"><span data-stu-id="6b73a-113">Add bots for Private Chat and channels</span></span>
--------------------------------------

<span data-ttu-id="6b73a-114">Es gibt zwei Möglichkeiten, einen Bot für private Chats und Kanäle zu integrieren:</span><span class="sxs-lookup"><span data-stu-id="6b73a-114">There are two ways to integrate a bot for private chats and channels:</span></span>

1.  <span data-ttu-id="6b73a-p104">Installieren Sie öffentlich verfügbare Bots für **private Chats** oder für **Kanäle**. (Das ist die erste Option.)</span><span class="sxs-lookup"><span data-stu-id="6b73a-p104">Install publicly available bots for **private chat** or **channels**. (This is the first option.)</span></span>

2.  <span data-ttu-id="6b73a-117">Alternativ können Sie Bots suchen, indem Sie zu **Chat** navigieren, nach einem **Kontakt** suchen und dann auf **Apps entdecken** klicken.</span><span class="sxs-lookup"><span data-stu-id="6b73a-117">Alternatively, to find bots, navigate to **Chat**, search for a **contact,** and click **Discover apps.**</span></span>

![Screenshot des Suchfensters mit dem Suchergebnis „Apps entdecken“](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="6b73a-119">Wählen Sie wie unten gezeigt aus, mit welchem **Bot** Sie eine Unterhaltung führen möchten.</span><span class="sxs-lookup"><span data-stu-id="6b73a-119">Select which **Bot** you want to have a conversation with, as shown below.</span></span>

![Screenshot des Fensters „Apps entdecken“ mit ausgewählter Registerkarte „Bots“](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image2.png)

4.  <span data-ttu-id="6b73a-121">Erteilen Sie dem ausgewählten Bot **Berechtigungen**, und wählen Sie aus, ob Sie **Bots in einem privaten Chat** verwenden möchten, oder wählen Sie ein **Team** aus, in dem Sie den Bot verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="6b73a-121">Once selected, provide the bot **permissions,** and select whether you want to use **bots in a private chat** or select a **Team** to use it in.</span></span>

![Screenshot der App-Seite für AzureBot](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image3.png)

5.  <span data-ttu-id="6b73a-p105">Alternativ können Sie einen Bot in einem Kanal eines Teams verwenden, indem Sie einfach auf **View Team and Bots** (Team und Bots anzeigen) klicken. Hier können Sie weitere Bots entdecken.</span><span class="sxs-lookup"><span data-stu-id="6b73a-p105">Alternatively, to use a bot within a channel of a team, simply click **View Team and Bots**. Here you can Discover additional bots.</span></span>

6.  <span data-ttu-id="6b73a-p106">Ein Bot kann jederzeit aus dem Team entfernt werden. Klicken Sie einfach auf **View Team and Bots** (Team und Bots anzeigen), um alle Bots zu sehen, und **entfernen** Sie dann den gewünschten Bot.</span><span class="sxs-lookup"><span data-stu-id="6b73a-p106">At any time, a bot can be removed from the team. Simply click **View Team and Bots,** to see all bots and then **remove** the one you’d like.</span></span>

![Screenshot der Registerkarte „Bots“ mit der Beschreibung von AzureBot](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image4.png)

<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="6b73a-128">Erstellen von benutzerdefinierten Bots für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6b73a-128">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="6b73a-p107">Mit Microsoft Bot Framework können Sie leicht einen Bot erstellen, der in Ihre Branchenanwendungen integriert werden kann. Im Leitfaden zum [Erstellen und Testen eines Bots für Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) erfahren Sie, wie Sie Ihre eigenen Bots entwickeln und veröffentlichen können.</span><span class="sxs-lookup"><span data-stu-id="6b73a-p107">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework. Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="6b73a-p108">Wenn Sie einen Bot erstellen und in Bot Framework registrieren, können Sie wählen, ob er veröffentlicht werden soll. Wenn Sie den Bot nicht veröffentlichen, bleibt er privat. Sie können auch festlegen, dass sich die Benutzer vor der Verwendung des Bots anmelden müssen. Dadurch stellen Sie sicher, dass nur Mitarbeiter Ihrer Organisation auf den Bot zugreifen können, selbst wenn die Anwendungs-ID des Bots bekannt ist. Ein [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372)-Codebeispiel auf GitHub zeigt, wie Sie mithilfe von Bots Benutzer gegenüber Active Directory authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="6b73a-p108">When you create a bot and register it with the Bot Framework, you can choose to publish it or not. If you don't publish it, the bot remains private. You can also require your users to log in before using the bot. Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known. See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="6b73a-136">Bots können mit dem [Bot Framework-Emulator](https://go.microsoft.com/fwlink/?linkid=854373) getestet werden, bevor sie für Ihre Teams bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6b73a-136">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="6b73a-137">Querladen Ihres eigenen Bots für private Chats</span><span class="sxs-lookup"><span data-stu-id="6b73a-137">Side load your own bot for private chat</span></span>
---------------------------------------

1.  <span data-ttu-id="6b73a-138">Wenn Sie Ihren Bot erstellt haben, navigieren Sie zur **Botdashboard**-[Seite](https://go.microsoft.com/fwlink/?linkid=854374) für den entwickelten Bot, und kopieren Sie unter **Details** die **Microsoft-App-ID**.</span><span class="sxs-lookup"><span data-stu-id="6b73a-138">Once you have created your Bot, navigate to the **Bot Dashboard** [page](https://go.microsoft.com/fwlink/?linkid=854374) for the bot you developed, and under **Details**, copy the **Microsoft App ID**.</span></span>

![Screenshot der Detailseite für einen Bot mit hervorgehobener Microsoft-App-ID](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)

2.  <span data-ttu-id="6b73a-p109">Wählen Sie in Microsoft Teams im Bereich **Chat** das **Symbol zum Hinzufügen eines Chats** aus. Fügen Sie in **An:** die **Microsoft-App-ID** Ihres Bots ein.</span><span class="sxs-lookup"><span data-stu-id="6b73a-p109">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**. For **To:,** paste your bot's **Microsoft app ID**.</span></span>

![Screenshot eines Chatbereichs mit dem Symbol zum Hinzufügen eines Chats und der Zeile „An“ mit hervorgehobener Microsoft-App-ID](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)

3.  <span data-ttu-id="6b73a-143">Die App-ID wird in den **Botnamen** aufgelöst. Dann können Sie eine Chatunterhaltung mit dem Bot beginnen.</span><span class="sxs-lookup"><span data-stu-id="6b73a-143">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>
