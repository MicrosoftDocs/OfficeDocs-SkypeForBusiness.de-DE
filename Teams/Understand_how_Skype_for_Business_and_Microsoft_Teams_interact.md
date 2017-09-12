---
title: Interaktion von Skype for Business und Microsoft Teams | Microsoft-Support
author: LolaJacobsen
ms.author: lolaj
manager: serdar
ms.date: 08/11/2017
ms.topic: overview
ms.prod: teams
description: "Erfahren Sie hier, wie Skype for Business und Microsoft Teams interagieren – von Chats bis zu Anrufen."
ms.openlocfilehash: cb459fa444f7324a358fbd325e3ddb5cfd4c1966
ms.sourcegitcommit: 3b9b3f07f4f67cd5f43da68f48d62222d7e49167
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2017
---
<a name="how-skype-for-business-and-microsoft-teams-interact"></a><span data-ttu-id="64618-103">Interaktion von Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="64618-103">How Skype for Business and Microsoft Teams interact</span></span>
===================================================

<span data-ttu-id="64618-104">Wenn Ihre Organisation Skype for Business verwendet, sind Kenntnisse über die Interaktion zwischen Skype for Business und Microsoft Teams von großer Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="64618-104">If your organization uses Skype for Business today, it is important to understand how Skype for Business and Microsoft Teams will interact.</span></span>

<span data-ttu-id="64618-105">Im Hinblick auf die allgemeine Verfügbarkeit von Microsoft Teams ist die grundlegende Interoperabilität zwischen Microsoft Teams und Skype for Business Online oder Hybrid nur für Peer-zu-Peer (P2P)-Instant Messaging verfügbar.</span><span class="sxs-lookup"><span data-stu-id="64618-105">At general availability of Microsoft Teams, basic interoperability between Microsoft Teams and Skype for Business Online or Hybrid is available peer to peer (P2P) instant messaging only.</span></span>

<span data-ttu-id="64618-p101">Standardmäßig meldet sich der Microsoft Teams-Client sowohl bei den Microsoft Teams-Backend-Diensten als auch bei den Skype for Business-Diensten an (ein auf einem dualen Stapel basierter Ansatz). Der Microsoft Teams-Client stellt Skype for Business nur Instant Messaging-Funktionen zur Verfügung. Bei der Suche nach einem Microsoft Teams-Benutzer über Skype for Business wird der Benutzer wie im oberen Beispiel gezeigt mit „Nur Instant Messaging“ gekennzeichnet (Alix Wilber ist nur beim Microsoft Teams-Client angemeldet).</span><span class="sxs-lookup"><span data-stu-id="64618-p101">The default behavior is that the Microsoft Teams client will sign into both the Microsoft Teams backend services and the Skype for Business services (a dual-stack approach). The Microsoft Teams client will only present IM capabilities to Skype for Business, so looking up a Microsoft Teams user from Skype for Business will only indicate the user as IM Only – shown in the example below, Alix Wilber is only signed into the Microsoft Teams client.</span></span>

![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image1.png)

<span data-ttu-id="64618-108">In Microsoft Teams können Benutzer andere Benutzer innerhalb ihrer Organisation suchen, die derzeit nicht für Skype for Business aktiviert sind, und Instant Messaging-Chatsitzungen durchführen.</span><span class="sxs-lookup"><span data-stu-id="64618-108">From Microsoft Teams, users can search for other users within their organization who are currently only enabled for Skype for Business, and conduct instant messaging chat sessions.</span></span>

<span data-ttu-id="64618-109">Benutzer von Skype for Business können auf die Sofortnachrichten antworten, die im Chatfenster von Microsoft Teams ankommen.</span><span class="sxs-lookup"><span data-stu-id="64618-109">Users on Skype for Business can reply to the instant messages, which will arrive in Microsoft Teams’ chat window.</span></span>

![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image2.png)

<span data-ttu-id="64618-110">Falls Benutzer von Microsoft Teams ebenfalls für Skype for Business aktiviert sind, können sich mit ihren eigenen Clients gleichzeitig bei Microsoft Teams und bei Skype for Business anmelden.</span><span class="sxs-lookup"><span data-stu-id="64618-110">Users on Microsoft Teams, if enabled for Skype for Business as well, can sign in to Microsoft Teams and Skype for Business using their own respective clients simultaneously.</span></span>

<span data-ttu-id="64618-p102">Der letzte aktive Endpunkt wird berücksichtigt. Wenn der Benutzer also Microsoft Teams aktiv verwendet, werden alle von einem Skype for Business-Benutzer gesendeten Sofortnachrichten im Microsoft Teams-Chatfenster angezeigt. Wenn der Benutzer Skype for Business zum Empfangen oder Tätigen von Telefonanrufen verwendet oder einfach nur einen Anruf über Skype for Business beendet und nicht zum Microsoft Teams-Client zurückkehrt, kommen die von einem Skype for Business-Benutzer gesendeten eingehenden Sofortnachrichten beim Skype for Business-Client an, da dies der aktivste Endpunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="64618-p102">The last active endpoint will be honored, so if the user is actively using Microsoft Teams, any instant messages sent from a Skype for Business user will arrive in the Microsoft Teams chat window. If the user is currently using Skype for Business to receive/make phone calls or just finished taking a call using Skype for Business, and have not returned to Microsoft Teams client, incoming instant messages sent from a Skype for Business user will arrive in Skype for Business client as this will be the most active endpoint.</span></span>

<span data-ttu-id="64618-p103">Da Microsoft Teams derzeit nur Peer-zu-Peer (P2P)-Instant Messaging-Interoperabilität zwischen Skype for Business unterstützt, kommen alle Audio- bzw. Videoanrufe oder Einladungen zur Teilnahme an einer Skype for Business-Besprechung von anderen Skype for Business-Benutzern nur beim Skype for Business-Client an. Umgekehrt kommen alle Audio- bzw. Videoanrufe oder Einladungen zur Teilnahme an einem Gruppenanruf nur beim Microsoft Teams-Client an.</span><span class="sxs-lookup"><span data-stu-id="64618-p103">As Microsoft Teams only currently supports peer-to-peer (P2P) instant messaging interop between Skype for Business, any audio/video calls or invitation to join a Skype for Business meetings, for any modalities, from other Skype for Business users will arrive on the Skype for Business client only. In the reverse, any audio/video calls or invitation to join group calling, for any modalities from Microsoft Teams client, will only arrive on the Microsoft Teams client.</span></span>

<span data-ttu-id="64618-p104">Basierend auf dem oben erläuterten Verhalten können Endbenutzer Microsoft Teams und Skype for Business bequem gleichzeitig benutzen und den jeweiligen Kommunikationsanforderungen mit dem richtigen Tool begegnen. Für eine optimale Erfahrung der Endbenutzer können jedoch Kenntnisse über die Interoperabilität und deren Auswirkungen erforderlich sein.</span><span class="sxs-lookup"><span data-stu-id="64618-p104">With the above behavior, end users can comfortably use both Microsoft Teams and Skype for Business at the same time, and handle specific communications needs using the right tool. However, proper end user awareness may be required to understand how interoperability works and how it may impact end user experience.</span></span>


|  |  |
|---------|---------|
|![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image3.png)<br><span data-ttu-id="64618-117">Hinweis</span><span class="sxs-lookup"><span data-stu-id="64618-117">Note:</span></span></br>      |<span data-ttu-id="64618-118">Mit der Interoperabilität von Skype for Business werden in Teams ankommende Sofortnachrichten nicht im Skype for Business-Unterhaltungsverlauf aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="64618-118">With Skype for Business interoperability, instant messages that arrive in Teams will not be recorded in Skype for Business conversation history.</span></span>         |

<span data-ttu-id="64618-p105">Microsoft Teams bietet Benutzern die Möglichkeit, die Interoperabilität von Skype for Business in den Benachrichtigungseinstellungen zu deaktivieren. Diese Einstellung ist benutzerdefiniert, sodass jeder Benutzer sich für das jeweilige Verhalten entscheiden kann.</span><span class="sxs-lookup"><span data-stu-id="64618-p105">Microsoft Teams provides the ability for users to disable Skype for Business interoperability from within the Notification settings. This setting is user controlled, allowing each user to decide on the behavior they prefer.</span></span>
