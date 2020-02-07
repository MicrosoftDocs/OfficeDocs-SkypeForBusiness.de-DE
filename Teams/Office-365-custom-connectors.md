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
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: Mit Connectors kann sich Ihr Team auf dem Laufenden halten, da Inhalte und Updates von häufig verwendeten Diensten direkt in einen Kanal übermittelt werden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc65939048fd8e54bd122a4dc52d2a611b8453cc
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834375"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="7eaf1-103">Verwenden von Office 365 und benutzerdefinierten Connectors in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7eaf1-103">Use Office 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="7eaf1-p101">Connectors halten Ihr Team auf dem neuesten Stand, indem Sie häufig verwendete Inhalte und dienstupdates direkt in einem Kanal bereitstellen. Mit Connectors können Ihre Microsoft Teams-Benutzer Updates von beliebten Diensten wie Twitter, Trello, wunderlist, GitHub und Azure DevOps-Diensten innerhalb des Chat-Streams in Ihrem Team erhalten.</span><span class="sxs-lookup"><span data-stu-id="7eaf1-p101">Connectors keep your team current by delivering frequently used content and service updates directly into a channel. With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="7eaf1-106">Jedes Mitglied eines Teams kann sein Team mit den gängigen Cloud-Diensten mit den Connectors verbinden, wenn die Team Berechtigungen dies zulassen, und alle Teammitglieder werden über die Aktivitäten dieses Diensts benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="7eaf1-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="7eaf1-107">Connectors funktionieren auch dann weiterhin, wenn das Mitglied, das den Connector zunächst eingerichtet hat, den Link verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="7eaf1-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="7eaf1-108">Jedes Teammitglied, das über die Berechtigungen für Faxkomponente verfügt, kann Connectors-Setup von anderen Mitgliedern ändern.</span><span class="sxs-lookup"><span data-stu-id="7eaf1-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="7eaf1-109">Office 365-Connectors können sowohl mit Microsoft Teams als auch mit Office 365-Gruppen verwendet werden, wodurch es für alle Mitglieder einfacher ist, synchron zu bleiben und relevante Informationen schnell zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7eaf1-109">Office 365 connectors can be used with both Microsoft Teams and Office 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="7eaf1-110">Sowohl Microsoft Teams als auch Exchange verwenden das gleiche Connector-Modell, mit dem Sie dieselben Connectors in beiden Plattformen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="7eaf1-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="7eaf1-111">Beachten Sie jedoch, dass das Deaktivieren von Connectors für die Office 365-Gruppe, von der ein Team abhängig ist, auch die Möglichkeit zum Erstellen von Connectors für dieses Team deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="7eaf1-111">It is worth noting, however, that disabling connectors for the Office 365 Group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="7eaf1-112">Hinzufügen eines Verbinders zu einem Kanal</span><span class="sxs-lookup"><span data-stu-id="7eaf1-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="7eaf1-113">Derzeit können Sie mithilfe von Microsoft Teams-Desktop-und-Webclienten Connectors hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7eaf1-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="7eaf1-114">Informationen, die von diesen Konnektoren gepostet werden, können jedoch auf **allen Clients** , einschließlich Handy, angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7eaf1-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="7eaf1-115">Wenn Sie einen Verbinder zu einem Kanal hinzufügen möchten, klicken Sie auf die **Auslassungszeichen (...)** rechts neben einem Kanalnamen, und klicken Sie dann auf **Verbinder**.</span><span class="sxs-lookup"><span data-stu-id="7eaf1-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    ![Screenshot der Benutzeroberfläche von Teams mit ausgewählter Option "Verbinder".](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. <span data-ttu-id="7eaf1-117">Sie können aus einer Vielzahl von verfügbaren Connectors auswählen und dann auf **Hinzufügen**klicken.</span><span class="sxs-lookup"><span data-stu-id="7eaf1-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    ![Screenshot des Dialogfelds "Verbinder" mit verfügbaren Connectors](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. <span data-ttu-id="7eaf1-p105">Geben Sie die erforderlichen Informationen des ausgewählten Connectors ein, und klicken Sie auf **Speichern**. Jeder Connector erfordert verschiedene Informationen, damit er richtig funktioniert. Bei manchen dieser Informationen müssen Sie sich über die Links auf der Connector-Konfigurationsseite bei dem Dienst anmelden.</span><span class="sxs-lookup"><span data-stu-id="7eaf1-p105">Fill in the required information of the selected connector and click **Save**. Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![Screenshot der Konfigurationsseite für den RSS-Connector](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. <span data-ttu-id="7eaf1-122">Die vom Connector bereitgestellten Daten werden automatisch im Kanal gepostet.</span><span class="sxs-lookup"><span data-stu-id="7eaf1-122">Data provided by the connector is automatically posted to the channel.</span></span>

    ![Screenshot der Microsoft Teams-Benutzeroberfläche mit einer Unterhaltung in einem Kanal](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="7eaf1-124">Entwickeln von benutzerdefinierten Connectors</span><span class="sxs-lookup"><span data-stu-id="7eaf1-124">Develop custom connectors</span></span>
----------------------------

<span data-ttu-id="7eaf1-125">Sie können auch benutzerdefinierte Connectors sowie eingehende und ausgehende webhooks erstellen.</span><span class="sxs-lookup"><span data-stu-id="7eaf1-125">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="7eaf1-126">Weitere Informationen finden Sie in der [Dokumentation für Entwickler](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).</span><span class="sxs-lookup"><span data-stu-id="7eaf1-126">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
