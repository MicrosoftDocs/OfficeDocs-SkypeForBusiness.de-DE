---
title: Verwenden von Office 365 und benutzerdefinierten Connectors in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
description: Mit Connectors kann sich Ihr Team auf dem Laufenden halten, da Inhalte und Updates von häufig verwendeten Diensten direkt in einen Kanal übermittelt werden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a8235ce9eb950df0c04ab41949500a640376e612
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245208"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="fa934-103">Verwenden von Office 365 und benutzerdefinierten Connectors in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fa934-103">Use Office 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="fa934-104">Connectors halten Ihr Team auf dem neuesten Stand, indem Sie häufig verwendete Inhalte und dienstupdates direkt in einem Kanal bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="fa934-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="fa934-105">Mit Connectors können Ihre Microsoft Teams-Benutzer Updates von beliebten Diensten wie Twitter, Trello, wunderlist, GitHub und Azure DevOps-Diensten innerhalb des Chat-Streams in Ihrem Team erhalten.</span><span class="sxs-lookup"><span data-stu-id="fa934-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="fa934-106">Jedes Mitglied eines Teams kann sein Team mit den gängigen Cloud-Diensten mit den Connectors verbinden, wenn die Team Berechtigungen dies zulassen, und alle Teammitglieder werden über die Aktivitäten dieses Diensts benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="fa934-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="fa934-107">Connectors funktionieren auch dann weiterhin, wenn das Mitglied, das den Connector zunächst eingerichtet hat, den Link verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="fa934-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="fa934-108">Jedes Teammitglied, das über die Berechtigungen für Faxkomponente verfügt, kann Connectors-Setup von anderen Mitgliedern ändern.</span><span class="sxs-lookup"><span data-stu-id="fa934-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="fa934-109">Office 365-Connectors können sowohl mit Microsoft Teams als auch mit Office 365-Gruppen verwendet werden, wodurch es für alle Mitglieder einfacher ist, synchron zu bleiben und relevante Informationen schnell zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="fa934-109">Office 365 connectors can be used with both Microsoft Teams and Office 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="fa934-110">Sowohl Microsoft Teams als auch Exchange verwenden das gleiche Connector-Modell, mit dem Sie dieselben Connectors in beiden Plattformen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="fa934-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="fa934-111">Beachten Sie jedoch, dass das Deaktivieren von Connectors für die Office 365-Gruppe, von der ein Team abhängig ist, auch die Möglichkeit zum Erstellen von Connectors für dieses Team deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="fa934-111">It is worth noting, however, that disabling connectors for the Office 365 Group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="fa934-112">Hinzufügen eines Verbinders zu einem Kanal</span><span class="sxs-lookup"><span data-stu-id="fa934-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="fa934-113">Derzeit können Sie mithilfe von Microsoft Teams-Desktop-und-Webclienten Connectors hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fa934-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="fa934-114">Informationen, die von diesen Konnektoren gepostet werden, können jedoch auf **allen Clients** , einschließlich Handy, angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="fa934-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="fa934-115">Wenn Sie einen Verbinder zu einem Kanal hinzufügen möchten, klicken Sie auf die Auslassungszeichen **(...)** rechts neben einem Kanalnamen, und klicken Sie dann auf **Verbinder**.</span><span class="sxs-lookup"><span data-stu-id="fa934-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    ![Screenshot der Benutzeroberfläche von Teams mit ausgewählter Option "Verbinder".](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. <span data-ttu-id="fa934-117">Sie können aus einer Vielzahl von verfügbaren Connectors auswählen und dann auf **Hinzufügen**klicken.</span><span class="sxs-lookup"><span data-stu-id="fa934-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    ![Screenshot des Dialogfelds "Verbinder" mit verfügbaren Connectors](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. <span data-ttu-id="fa934-p105">Geben Sie die erforderlichen Informationen des ausgewählten Connectors ein, und klicken Sie auf **Speichern**. Jeder Connector erfordert verschiedene Informationen, damit er richtig funktioniert. Bei manchen dieser Informationen müssen Sie sich über die Links auf der Connector-Konfigurationsseite bei dem Dienst anmelden.</span><span class="sxs-lookup"><span data-stu-id="fa934-p105">Fill in the required information of the selected connector and click **Save**. Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![Screenshot der Konfigurationsseite für den RSS-Connector](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. <span data-ttu-id="fa934-122">Die vom Connector bereitgestellten Daten werden automatisch im Kanal gepostet.</span><span class="sxs-lookup"><span data-stu-id="fa934-122">Data provided by the connector is automatically posted to the channel.</span></span>

    ![Screenshot der Microsoft Teams-Benutzeroberfläche mit einer Unterhaltung in einem Kanal](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="fa934-124">Entwickeln von benutzerdefinierten Connectors</span><span class="sxs-lookup"><span data-stu-id="fa934-124">Develop custom connectors</span></span>
-----------------------------

<span data-ttu-id="fa934-125">Es ist sehr einfach, benutzerdefinierte Connectors zu entwickeln, die in Ihre Branchenanwendungen integriert werden können.</span><span class="sxs-lookup"><span data-stu-id="fa934-125">It is very easy to develop custom connectors that can integrate with your line-of-business (LOB) applications.</span></span> <span data-ttu-id="fa934-126">Sie können den integrierten **eingehenden webhook** -Connector verwenden, um einen Endpunkt für einen Kanal zu erstellen, der Daten aus einer beliebigen Anwendung mithilfe von HTTP Post-Methoden abruft.</span><span class="sxs-lookup"><span data-stu-id="fa934-126">You can use the built-in **Incoming Webhook** connector to create an endpoint for a channel that pulls data from any application using HTTP post methods.</span></span>

1. <span data-ttu-id="fa934-127">Fügen Sie den **eingehenden Webhook** wie jeden anderen Connector hinzu.</span><span class="sxs-lookup"><span data-stu-id="fa934-127">Add the **Incoming Webhook** like any other connector.</span></span>

    ![Screenshot der Option zum Hinzufügen des Connectors „Incoming Webhook“ (Eingehender Webhook)](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2. <span data-ttu-id="fa934-129">Um einen Webhook zu erstellen, geben Sie einen **Namen** an, aktualisieren Sie bei Bedarf das Webhook-Image, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="fa934-129">To create a Webhook, specify a **name**, update the Webhook image, if necessary, and click **Create**.</span></span>

    ![Screenshot der Konfigurationsseite für den eingehenden webhook-Connector](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3. <span data-ttu-id="fa934-131">Für Anwendungen, die Daten in diesen Kanal verschieben, ist die webhook-Connector-URL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fa934-131">Applications that push data to this channel require the Webhook connector URL.</span></span> <span data-ttu-id="fa934-132">Beim Erstellen des webhooks wird eine eindeutige URL erstellt.</span><span class="sxs-lookup"><span data-stu-id="fa934-132">A unique URL is created when you create the Webhook.</span></span> <span data-ttu-id="fa934-133">Geben Sie diese URL für Ihre Entwickler frei, damit Sie Ihre Anwendungen so konfigurieren können, dass Sie bei Bedarf Daten pushen.</span><span class="sxs-lookup"><span data-stu-id="fa934-133">Share this URL with your developers so that they can configure their applications to push data, as needed.</span></span>

    ![Screenshot der eindeutigen URL des Webhooks](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4. <span data-ttu-id="fa934-135">Wenn eine externe Anwendung mithilfe von Push Daten an einen Connector überträgt, wird die Nachricht in der Kanalunterhaltungsliste als spezielle Nachricht, das heißt als **Connectorkartennachricht**, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fa934-135">When an external application pushes data to a connector, the message is shown in the channel conversation list as a special message called a **Connector Card** message.</span></span>

    ![Screenshot der Microsoft Teams-Benutzeroberfläche mit einer Connectorkartennachricht](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

     <span data-ttu-id="fa934-137">Entwickler können Ihre Anwendungen so konfigurieren, dass Sie diese Karten erstellen, indem Sie eine HTTP-Anforderung mit einer einfachen JSON-Nutzlast an die webhook-Adresse eines Teams senden, bei der es sich um eine eindeutige URL dieses Endpunkts handelt, die vom Assistenten bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="fa934-137">Developers can configure their applications to create these cards by sending an HTTP request with a simple JSON payload to a team’s Webhook address, which is a unique URL of that endpoint provided by the wizard.</span></span> <span data-ttu-id="fa934-138">Lassen Sie Ihre Entwickler auf [Erste Schritte mit Office 365-Connectors für Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors)im Microsoft Developer Network verweisen, in dem detaillierte Anweisungen und Connector-Beispiele enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="fa934-138">Have your developers refer to [Getting started with Office 365 Connectors for Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors), on the Microsoft Developer Network, which has detailed instructions and connector samples.</span></span> <span data-ttu-id="fa934-139">Zu den anderen Ressourcen gehören das [Verbinden von apps mit ihren Gruppen in Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) und dem [Office dev Center – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784).</span><span class="sxs-lookup"><span data-stu-id="fa934-139">Other resources include [Connect apps to your groups in Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) and the [Office Dev Center – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784).</span></span>
