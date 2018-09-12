---
title: Verwenden von Office 365 und benutzerdefinierten Connectors in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: lucarras
search.appverid: MET150
description: Mit Connectors kann sich Ihr Team auf dem Laufenden halten, da Inhalte und Updates von häufig verwendeten Diensten direkt in einen Kanal übermittelt werden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7b5a0af4327169c6ba8b640e48184591002c94ea
ms.sourcegitcommit: 6732f56535d60a46e6998cde64103e8530dd6452
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2018
ms.locfileid: "23937876"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="bad94-103">Verwenden von Office 365 und benutzerdefinierten Connectors in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bad94-103">Use Office 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="bad94-p101">Mit Connectors kann sich Ihr Team auf dem Laufenden halten, da Inhalte und Updates von häufig verwendeten Diensten direkt in einen Kanal übermittelt werden. Mit Connectors können Ihre Microsoft Teams-Benutzer Updates von beliebten Diensten wie Twitter, Trello, Wunderlist, GitHub und VSTS innerhalb des Chatstroms in ihrem Team erhalten.</span><span class="sxs-lookup"><span data-stu-id="bad94-p101">Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel. With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and VSTS within the chat stream in their team.</span></span>

<span data-ttu-id="bad94-106">Ein beliebiges Mitglied eines Teams kann ihr Team mit beliebte Clouddiensten mit Connectors verbinden, wenn die Teamberechtigungen zulassen, und alle Teammitglieder Aktivitäten von diesem Dienst benachrichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="bad94-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="bad94-107">Verbinder bleiben auch nach der Member-Funktion, die Anfangs Setup hat, die der Connector verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="bad94-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="bad94-108">Jedes Teammitglied mit den Berechtigungen zum hinzufügen/entfernen kann Konnektoren Setup anderer Mitglieder ändern.</span><span class="sxs-lookup"><span data-stu-id="bad94-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="bad94-109">Office 365-Connectors können mit beiden Microsoft-Teams verwendet werden und Office 365-Gruppen, erleichtert es für alle Mitglieder synchronisiert bleiben und relevanten Informationen schnell zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="bad94-109">Office 365 connectors can be used with both Microsoft Teams and Office 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="bad94-110">Microsoft-Teams und Exchange verwenden dasselbe Modell Connector, das Sie die gleichen Connectors in beiden Plattformen verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="bad94-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="bad94-111">Dabei ist zu beachten, jedoch, deaktivieren Connectors für die Office 365-Gruppe, die ein Team abhängig ist die Möglichkeit zum Erstellen von Konnektoren für dieses Team auch deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="bad94-111">It is worth noting, however, that disabling connectors for the Office 365 Group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<span data-ttu-id="bad94-p104">Zurzeit können Connectors mit den Microsoft Teams-Desktopclients und -Webclients hinzugefügt werden. Von diesen Connectors gepostete Informationen können jedoch mit **allen Clients**, auch den mobilen Clients, angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bad94-p104">Currently, connectors can be added by using Microsoft Teams desktop and web clients. However, information posted by these connectors can be viewed using **all clients** including mobile.</span></span>

1.  <span data-ttu-id="bad94-114">Um einen Connector zu einem Kanal hinzuzufügen, klicken Sie auf das **Auslassungszeichen (…)** rechts neben einem Kanalnamen und dann auf **Connectors**.</span><span class="sxs-lookup"><span data-stu-id="bad94-114">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors.**</span></span>

    ![Screenshot der Microsoft Teams-Benutzeroberfläche mit ausgewähltem Kanalnamen und ausgewählter Option „Connectors“](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2.  <span data-ttu-id="bad94-116">Benutzer können aus einer Vielfalt verfügbarer Connectors auswählen und dann auf **Hinzufügen** klicken.</span><span class="sxs-lookup"><span data-stu-id="bad94-116">Users can select from a variety of available connectors, then click **Add**.</span></span>

    ![Screenshot des Dialogfelds „Connectors“ mit den Connectors, die hinzugefügt werden können](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3.  <span data-ttu-id="bad94-p105">Geben Sie die erforderlichen Informationen des ausgewählten Connectors ein, und klicken Sie auf **Speichern**. Jeder Connector erfordert verschiedene Informationen, damit er richtig funktioniert. Bei manchen dieser Informationen müssen Sie sich über die Links auf der Connector-Konfigurationsseite bei dem Dienst anmelden.</span><span class="sxs-lookup"><span data-stu-id="bad94-p105">Fill in the required information of the selected connector and click **Save**. Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![Screenshot der Konfigurationsseite für den RSS-Connector](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4.  <span data-ttu-id="bad94-121">Die vom Connector bereitgestellten Daten werden automatisch im Kanal gepostet.</span><span class="sxs-lookup"><span data-stu-id="bad94-121">Data provided by the connector is automatically posted to the channel.</span></span>

    ![Screenshot der Microsoft Teams-Benutzeroberfläche mit einer Unterhaltung in einem Kanal](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="bad94-123">Entwickeln von benutzerdefinierten Connectors</span><span class="sxs-lookup"><span data-stu-id="bad94-123">Develop custom connectors</span></span>
-----------------------------

<span data-ttu-id="bad94-p106">Sie können ganz leicht benutzerdefinierte Connectors entwickeln, die in Ihre branchenspezifischen Anwendungen integriert werden können. Sie können den integrierten Connector **Incoming Webhook** (Eingehender Webhook) verwenden, um einen Endpunkt für einen Kanal zu erstellen, der mithilfe von HTTP-Post-Methoden Daten aus beliebigen Anwendungen abruft.</span><span class="sxs-lookup"><span data-stu-id="bad94-p106">It is very easy to develop custom connectors that can integrate into your Line-of-Business (LOB) applications. You can use the built-in **Incoming Webhook** connector to create an endpoint for a channel, that pulls data from any application using HTTP post methods.</span></span>

1.  <span data-ttu-id="bad94-126">Fügen Sie den **eingehenden Webhook** wie jeden anderen Connector hinzu.</span><span class="sxs-lookup"><span data-stu-id="bad94-126">Add the **Incoming Webhook** like any other connector.</span></span>

    ![Screenshot der Option zum Hinzufügen des Connectors „Incoming Webhook“ (Eingehender Webhook)](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2.  <span data-ttu-id="bad94-128">Um einen Webhook zu erstellen, geben Sie einen **Namen** an, aktualisieren Sie bei Bedarf das Webhook-Image, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="bad94-128">To create a Webhook, specify a **name**, update the Webhook image, if necessary, and click **Create**.</span></span>

    ![<span data-ttu-id="bad94-129">Screenshot der Konfigurationsseite für den Connector „Incoming Webhook“ (Eingehender Webhook)</span><span class="sxs-lookup"><span data-stu-id="bad94-129">Screenshot of the configuration page for the Incoming Webhook connector.</span></span> ](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3.  <span data-ttu-id="bad94-p107">Anwendungen, die Daten mithilfe von Push in diesen Kanal übertragen, benötigen die URL des Webhook-Connectors. Eine **eindeutige URL** wird erstellt, wenn Sie den **Webhook** erstellen. Geben Sie Ihren Entwicklern diese URL, damit sie bei Bedarf ihre Anwendungen für das Übertragen von Anwendungen mithilfe von Push konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="bad94-p107">Applications that push data to this channel, require the Webhook connector URL. A **unique URL** is created when you created the **Webhook**. Share this URL with your developers, so that they can configure their applications to push data, as needed.</span></span>

    ![Screenshot der eindeutigen URL des Webhooks](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4.  <span data-ttu-id="bad94-134">Wenn eine externe Anwendung mithilfe von Push Daten an einen Connector überträgt, wird die Nachricht in der Kanalunterhaltungsliste als spezielle Nachricht, das heißt als **Connectorkartennachricht**, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bad94-134">When an external application pushes data to a connector, the message is shown in the channel conversation list as a special message called a **Connector Card** message.</span></span>

    ![Screenshot der Microsoft Teams-Benutzeroberfläche mit einer Connectorkartennachricht](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

<span data-ttu-id="bad94-p108">Entwickler können ihre Anwendungen für das Erstellen dieser Karten konfigurieren, indem sie eine HTTP-Anforderung mit einer einfachen JSON-Nutzlast an eine Webhook-Adresse von Microsoft Teams senden, die eine vom Assistenten bereitgestellte eindeutige URL dieses Endpunkts darstellt. Ihre Entwickler finden im Microsoft Developer Network unter [Erste Schritte mit Office 365-Connectors für Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855783) detaillierte Anleitungen und Connector-Beispiele. Als weitere Ressourcen stehen [Verbinden von Apps mit Ihren Gruppen in Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) und [Office Dev Center – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="bad94-p108">Developers can configure their applications to create these cards, by sending an HTTP request with a simple JSON payload to a Microsoft Team’s Webhook address, that is a unique URL of that endpoint provided by the wizard. Have your developers refer to [Getting started with Office 365 Connectors for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855783), on the Microsoft Developer Network, with detailed instructions and connector samples. Other resources include [Connect apps to your groups in Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) and the [Office Dev Center – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784).</span></span>
