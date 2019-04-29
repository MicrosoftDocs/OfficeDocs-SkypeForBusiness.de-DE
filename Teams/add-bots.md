---
title: Hinzufügen von Bots für private Chats und Kanäle in Microsoft Teams
author: LolaJacobsen, DamienDoumer
ms.author: lolaj, Damien
manager: serdars
ms.date: 12/05/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: lucarras
description: Hier erfahren Sie, wie Sie in Microsoft Teams Bots für private Chats und Kanäle hinzufügen, benutzerdefinierte Bots erstellen und Ihren eigenen Bot für private Chats querladen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a4e921ea668fc59b520fdb068355db82bfe24481
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400538"
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="43663-103">Hinzufügen von Bots für private Chats und Kanäle in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="43663-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="43663-104">Bots sind automatisierte Programme, die auf Abfragen antworten oder Updates und Benachrichtigungen zu Details herausgeben, die Benutzer interessant finden oder über die sie auf dem Laufenden bleiben möchten.</span><span class="sxs-lookup"><span data-stu-id="43663-104">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="43663-105">Bots Benutzern die Interaktion mit Clouddiensten wie vorgangsverwaltung, Planung und Abrufe, über Chat Unterhaltungen in Microsoft-Teams.</span><span class="sxs-lookup"><span data-stu-id="43663-105">Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams.</span></span> <span data-ttu-id="43663-106">Bots für Microsoft-Teams, basieren auf dem [Microsoft Bot-Framework](https://go.microsoft.com/fwlink/?linkid=854370).</span><span class="sxs-lookup"><span data-stu-id="43663-106">Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370).</span></span> <span data-ttu-id="43663-107">Die Bots, die mithilfe dieses Frameworks entwickelt werden kann auf einfache Weise für Microsoft-Teams, aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="43663-107">The bots that are developed using this framework can be enabled easily for Microsoft Teams.</span></span> <span data-ttu-id="43663-108">Weitere Informationen finden Sie unter [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="43663-108">For more information, see [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

<span data-ttu-id="43663-p102">Zurzeit unterstützt Microsoft Teams Bots in privaten Chats und in Kanälen in einem Team. Administratoren können steuern, ob die Verwendung von Bots innerhalb des Office 365-Mandanten zulässig oder untersagt ist.<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="43663-p102">Currently, Microsoft Teams support bots in private chats and channels within a team. Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="43663-111">In Microsoft Teams können Bots genutzt werden, die von der Community entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="43663-111">Bots developed by the community can be leveraged within Microsoft Teams.</span></span> <span data-ttu-id="43663-112">Die Funktionen des Bots und das Querladen von Bots müssen auf Mandantenebene aktiviert werden, damit benutzerdefinierte Bots funktionieren.</span><span class="sxs-lookup"><span data-stu-id="43663-112">The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional.</span></span> <span data-ttu-id="43663-113">Bots können in privaten Chats oder in Kanälen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="43663-113">Bots can be used in private chats or in channels.</span></span> <span data-ttu-id="43663-114">Für Kanäle können Teambesitzer oder -mitglieder Bots hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="43663-114">For channels, team owners or members can add bots.</span></span>

<span data-ttu-id="43663-115">Weitere Informationen finden Sie unter [Apps und Dienste](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) im Abschnitt „Verwenden von Bots“.</span><span class="sxs-lookup"><span data-stu-id="43663-115">For more information, see the section "Using bots" in [Apps and services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span></span> 




<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="43663-116">Erstellen von benutzerdefinierten Bots für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="43663-116">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="43663-p104">Mit Microsoft Bot Framework können Sie leicht einen Bot erstellen, der in Ihre Branchenanwendungen integriert werden kann. Im Leitfaden zum [Erstellen und Testen eines Bots für Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) erfahren Sie, wie Sie Ihre eigenen Bots entwickeln und veröffentlichen können.</span><span class="sxs-lookup"><span data-stu-id="43663-p104">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework. Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="43663-119">Wenn Sie einen Bot erstellen und in Bot Framework registrieren, können Sie wählen, ob er veröffentlicht werden soll.</span><span class="sxs-lookup"><span data-stu-id="43663-119">When you create a bot and register it with the Bot Framework, you can choose to publish it.</span></span> <span data-ttu-id="43663-120">Wenn Sie den Bot nicht veröffentlichen, bleibt er privat.</span><span class="sxs-lookup"><span data-stu-id="43663-120">If you don't publish it, the bot remains private.</span></span> <span data-ttu-id="43663-121">Sie können auch festlegen, dass sich die Benutzer vor der Verwendung des Bots anmelden müssen.</span><span class="sxs-lookup"><span data-stu-id="43663-121">You can also require your users to log in before using the bot.</span></span> <span data-ttu-id="43663-122">Dadurch stellen Sie sicher, dass nur Mitarbeiter Ihrer Organisation auf den Bot zugreifen können, selbst wenn die Anwendungs-ID des Bots bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="43663-122">Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known.</span></span> <span data-ttu-id="43663-123">Ein [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372)-Codebeispiel auf GitHub zeigt, wie Sie mithilfe von Bots Benutzer gegenüber Active Directory authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="43663-123">See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="43663-124">Bots können mit dem [Bot Framework-Emulator](https://go.microsoft.com/fwlink/?linkid=854373) getestet werden, bevor sie für Ihre Teams bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="43663-124">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="43663-125">Querladen Ihres eigenen Bots für private Chats</span><span class="sxs-lookup"><span data-stu-id="43663-125">Side load your own bot for private chat</span></span>
---------------------------------------

1. <span data-ttu-id="43663-126">Nachdem Sie Ihre Bot erstellt haben, wechseln Sie an den **Einstellungen** für den Robot, das, die Sie, klicken Sie dann unter **App-Einstellungen**entwickelt, kopieren Sie den Wert der Einstellung **MicrosoftAppId** . ![Screenshot der Seite Einstellungen für für ein Bot mit Microsoft App-ID hervorgehoben.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span><span class="sxs-lookup"><span data-stu-id="43663-126">After you have created your bot, go to the **Application Settings** for the bot you developed, then under **App settings**, copy the value of the **MicrosoftAppId** setting.![Screenshot of Application Settings page for a bot with the Microsoft App ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span></span>



2.  <span data-ttu-id="43663-127">Wählen Sie in Microsoft Teams im Bereich **Chat** das **Symbol zum Hinzufügen eines Chats** aus.</span><span class="sxs-lookup"><span data-stu-id="43663-127">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**.</span></span> <span data-ttu-id="43663-128">Fügen Sie in **An:** die **Microsoft-App-ID** Ihres Bots ein.</span><span class="sxs-lookup"><span data-stu-id="43663-128">For **To**, paste your bot's **Microsoft app ID**.</span></span> <span data-ttu-id="43663-129">![Screenshot eines Chatbereichs mit dem hervorgehobenen Symbol zum Hinzufügen eines Chats und der hervorgehobenen Zeile „An“ mit der Microsoft-App-ID](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span><span class="sxs-lookup"><span data-stu-id="43663-129">![Screenshot of a chat pane with the icon for Add chat and the To line with the Microsoft app ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span></span>



3.  <span data-ttu-id="43663-130">Die App-ID wird in den **Botnamen** aufgelöst. Dann können Sie eine Chatunterhaltung mit dem Bot beginnen.</span><span class="sxs-lookup"><span data-stu-id="43663-130">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>

<a name="side-load-your-bot-for-channels"></a><span data-ttu-id="43663-131">Seite laden Ihrer Bot für Kanäle</span><span class="sxs-lookup"><span data-stu-id="43663-131">Side load your bot for channels</span></span>
-----------------------------------

<span data-ttu-id="43663-132">Wenn Sie Ihre Bot mit Ihren Kollegen freigeben möchten, ist zum Hinzufügen und der verschiedenen Teams:</span><span class="sxs-lookup"><span data-stu-id="43663-132">If you want to share your bot with your colleagues, here's how to add it to channels of different teams:</span></span>

1. <span data-ttu-id="43663-133">Nachdem Sie [ein app-Paket für Ihre Bot erstellt](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)haben, öffnen Sie Teams, und navigieren Sie zu dem Team in dem Sie Seite den Robot geladen werden werden.</span><span class="sxs-lookup"><span data-stu-id="43663-133">After you have [created an app package for your bot](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload), open Teams and browse to the team in which you'll be side-loading the bot.</span></span>
2. <span data-ttu-id="43663-134">Fügen Sie die **[App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**, app, die Microsoft-Teams.</span><span class="sxs-lookup"><span data-stu-id="43663-134">Add **[App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**, app to Microsoft Teams.</span></span>
3. <span data-ttu-id="43663-135">Wählen Sie die Registerkarte **Manifest-Editor** in App Studio ![Manifest-Editor-Registerkarte Screenshot.](media/Adding_Bot_To_Teams.png)</span><span class="sxs-lookup"><span data-stu-id="43663-135">In App Studio, select the **Manifest Editor** Tab. ![Manifest Editor Tab Screenshot.](media/Adding_Bot_To_Teams.png)</span></span>
4. <span data-ttu-id="43663-136">Hinzufügen der Bot, Funktionen, Bot Wählen einer vorhandenen Bot hinzugefügt haben aus, und Sie haben die Möglichkeit zum Auswählen einer vorhandenen Bot aus einer oder geben Sie die Id eines Ihrer vorhandenen Bots.</span><span class="sxs-lookup"><span data-stu-id="43663-136">To add your bot, In capabilities, select bot and chose to add an existing bot, then you will have the option to chose an existing bot from a drop or enter the Id of one of your existing bots.</span></span>
<span data-ttu-id="43663-137">![Wählen Sie Ihre Bot Sie bereits erstellt haben.](media/Select_Existing_Bot.png)</span><span class="sxs-lookup"><span data-stu-id="43663-137">![Select your bot you already created.](media/Select_Existing_Bot.png)</span></span>
5. <span data-ttu-id="43663-138">Navigieren Sie zum Speicherort der app-Paket, wählen Sie sie aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="43663-138">Browse to the location of your app package, select it, and then click **Open**.</span></span>
6. <span data-ttu-id="43663-139">Wählen Sie Ihre Bot-Namen (vergessen Sie nicht, überprüfen Sie das Kontrollkästchen "Team" im Abschnitt Bereich)</span><span class="sxs-lookup"><span data-stu-id="43663-139">Select your bot's name (Don't forget to check the "Team" checkbox under the scope section)</span></span>
7. <span data-ttu-id="43663-140">Wählen Sie den Test, und verteilen Sie die Option.</span><span class="sxs-lookup"><span data-stu-id="43663-140">Select the Test and distribute option.</span></span>
8. <span data-ttu-id="43663-141">Wählen Sie das Team, in dem Ihre Bot zu im Dialogfeld verbinden die aufgerufen wird, werden soll.</span><span class="sxs-lookup"><span data-stu-id="43663-141">Select the team where you wish to connect your bot to in the dialog which pops up.</span></span>

<span data-ttu-id="43663-142">Mit dieser Option wird Ihre Bot in Ihrer Microsoft-Teams Team verfügbar.</span><span class="sxs-lookup"><span data-stu-id="43663-142">With this, your bot will be available in your Microsoft Team's team.</span></span>
