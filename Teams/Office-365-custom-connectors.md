---
title: Verwenden von Office 365 und benutzerdefinierten Connectors in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
description: Mit Connectors kann sich Ihr Team auf dem Laufenden halten, da Inhalte und Updates von häufig verwendeten Diensten direkt in einen Kanal übermittelt werden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2167022e3187924f5283ab5bee3a6b220595fd64
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2019
ms.locfileid: "34432856"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="e1035-103">Verwenden von Office 365 und benutzerdefinierten Connectors in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e1035-103">Use Office 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="e1035-104">Mit Connectors kann sich Ihr Team auf dem Laufenden halten, da Inhalte und Updates von häufig verwendeten Diensten direkt in einen Kanal übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="e1035-104">Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel.</span></span> <span data-ttu-id="e1035-105">Mit Connectors können Ihre Microsoft Teams-Benutzer Updates von beliebten Diensten wie Twitter, Trello, wunderlist, GitHub und Azure DevOps-Diensten innerhalb des Chat-Streams in Ihrem Team erhalten.</span><span class="sxs-lookup"><span data-stu-id="e1035-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="e1035-106">Jedes Mitglied eines Teams kann sein Team mit den gängigen Cloud-Diensten mit den Connectors verbinden, wenn die Team Berechtigungen dies zulassen, und alle Teammitglieder werden über die Aktivitäten dieses Diensts benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="e1035-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="e1035-107">Connectors funktionieren auch dann weiterhin, wenn das Mitglied, das den Connector zunächst eingerichtet hat, den Link verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="e1035-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="e1035-108">Jedes Teammitglied, das über die Berechtigungen für Faxkomponente verfügt, kann Connectors-Setup von anderen Mitgliedern ändern.</span><span class="sxs-lookup"><span data-stu-id="e1035-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="e1035-109">Office 365-Connectors können sowohl mit Microsoft Teams als auch mit Office 365-Gruppen verwendet werden, wodurch es für alle Mitglieder einfacher ist, synchron zu bleiben und relevante Informationen schnell zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e1035-109">Office 365 connectors can be used with both Microsoft Teams and Office 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="e1035-110">Sowohl Microsoft Teams als auch Exchange verwenden das gleiche Connector-Modell, mit dem Sie dieselben Connectors in beiden Plattformen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="e1035-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="e1035-111">Beachten Sie jedoch, dass das Deaktivieren von Connectors für die Office 365-Gruppe, von der ein Team abhängig ist, auch die Möglichkeit zum Erstellen von Connectors für dieses Team deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e1035-111">It is worth noting, however, that disabling connectors for the Office 365 Group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<span data-ttu-id="e1035-p104">Zurzeit können Connectors mit den Microsoft Teams-Desktopclients und -Webclients hinzugefügt werden. Von diesen Connectors gepostete Informationen können jedoch mit **allen Clients**, auch den mobilen Clients, angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e1035-p104">Currently, connectors can be added by using Microsoft Teams desktop and web clients. However, information posted by these connectors can be viewed using **all clients** including mobile.</span></span>

1.  <span data-ttu-id="e1035-114">Um einen Connector zu einem Kanal hinzuzufügen, klicken Sie auf das **Auslassungszeichen (…)** rechts neben einem Kanalnamen und dann auf **Connectors**.</span><span class="sxs-lookup"><span data-stu-id="e1035-114">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors.**</span></span>

    ![Screenshot der Benutzeroberfläche von Teams mit ausgewählter Option "Verbinder".](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2.  <span data-ttu-id="e1035-116">Benutzer können aus einer Vielfalt verfügbarer Connectors auswählen und dann auf **Hinzufügen** klicken.</span><span class="sxs-lookup"><span data-stu-id="e1035-116">Users can select from a variety of available connectors, then click **Add**.</span></span>

    ![Screenshot des Dialogfelds "Verbinder" mit verfügbaren Connectors](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3.  <span data-ttu-id="e1035-p105">Geben Sie die erforderlichen Informationen des ausgewählten Connectors ein, und klicken Sie auf **Speichern**. Jeder Connector erfordert verschiedene Informationen, damit er richtig funktioniert. Bei manchen dieser Informationen müssen Sie sich über die Links auf der Connector-Konfigurationsseite bei dem Dienst anmelden.</span><span class="sxs-lookup"><span data-stu-id="e1035-p105">Fill in the required information of the selected connector and click **Save**. Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![Screenshot der Konfigurationsseite für den RSS-Connector](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4.  <span data-ttu-id="e1035-121">Die vom Connector bereitgestellten Daten werden automatisch im Kanal gepostet.</span><span class="sxs-lookup"><span data-stu-id="e1035-121">Data provided by the connector is automatically posted to the channel.</span></span>

    ![Screenshot der Microsoft Teams-Benutzeroberfläche mit einer Unterhaltung in einem Kanal](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="e1035-123">Entwickeln von benutzerdefinierten Connectors</span><span class="sxs-lookup"><span data-stu-id="e1035-123">Develop custom connectors</span></span>
-----------------------------

<span data-ttu-id="e1035-p106">Sie können ganz leicht benutzerdefinierte Connectors entwickeln, die in Ihre branchenspezifischen Anwendungen integriert werden können. Sie können den integrierten Connector **Incoming Webhook** (Eingehender Webhook) verwenden, um einen Endpunkt für einen Kanal zu erstellen, der mithilfe von HTTP-Post-Methoden Daten aus beliebigen Anwendungen abruft.</span><span class="sxs-lookup"><span data-stu-id="e1035-p106">It is very easy to develop custom connectors that can integrate into your Line-of-Business (LOB) applications. You can use the built-in **Incoming Webhook** connector to create an endpoint for a channel, that pulls data from any application using HTTP post methods.</span></span>

1.  <span data-ttu-id="e1035-126">Fügen Sie den **eingehenden Webhook** wie jeden anderen Connector hinzu.</span><span class="sxs-lookup"><span data-stu-id="e1035-126">Add the **Incoming Webhook** like any other connector.</span></span>

    ![Screenshot der Option zum Hinzufügen des Connectors „Incoming Webhook“ (Eingehender Webhook)](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2.  <span data-ttu-id="e1035-128">Um einen Webhook zu erstellen, geben Sie einen **Namen** an, aktualisieren Sie bei Bedarf das Webhook-Image, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="e1035-128">To create a Webhook, specify a **name**, update the Webhook image, if necessary, and click **Create**.</span></span>

    ![Screenshot der Konfigurationsseite für den eingehenden webhook-Connector](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3.  <span data-ttu-id="e1035-p107">Anwendungen, die Daten mithilfe von Push in diesen Kanal übertragen, benötigen die URL des Webhook-Connectors. Eine **eindeutige URL** wird erstellt, wenn Sie den **Webhook** erstellen. Geben Sie Ihren Entwicklern diese URL, damit sie bei Bedarf ihre Anwendungen für das Übertragen von Anwendungen mithilfe von Push konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="e1035-p107">Applications that push data to this channel, require the Webhook connector URL. A **unique URL** is created when you created the **Webhook**. Share this URL with your developers, so that they can configure their applications to push data, as needed.</span></span>

    ![Screenshot der eindeutigen URL des Webhooks](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4.  <span data-ttu-id="e1035-134">Wenn eine externe Anwendung mithilfe von Push Daten an einen Connector überträgt, wird die Nachricht in der Kanalunterhaltungsliste als spezielle Nachricht, das heißt als **Connectorkartennachricht**, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e1035-134">When an external application pushes data to a connector, the message is shown in the channel conversation list as a special message called a **Connector Card** message.</span></span>

    ![Screenshot der Microsoft Teams-Benutzeroberfläche mit einer Connectorkartennachricht](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

<span data-ttu-id="e1035-p108">Entwickler können ihre Anwendungen für das Erstellen dieser Karten konfigurieren, indem sie eine HTTP-Anforderung mit einer einfachen JSON-Nutzlast an eine Webhook-Adresse von Microsoft Teams senden, die eine vom Assistenten bereitgestellte eindeutige URL dieses Endpunkts darstellt. Ihre Entwickler finden im Microsoft Developer Network unter [Erste Schritte mit Office 365-Connectors für Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors) detaillierte Anleitungen und Connector-Beispiele. Als weitere Ressourcen stehen [Verbinden von Apps mit Ihren Gruppen in Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) und [Office Dev Center – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e1035-p108">Developers can configure their applications to create these cards, by sending an HTTP request with a simple JSON payload to a Microsoft Team’s Webhook address, that is a unique URL of that endpoint provided by the wizard. Have your developers refer to [Getting started with Office 365 Connectors for Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors), on the Microsoft Developer Network, with detailed instructions and connector samples. Other resources include [Connect apps to your groups in Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) and the [Office Dev Center – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784).</span></span>
