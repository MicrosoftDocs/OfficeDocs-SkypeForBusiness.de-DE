---
title: 'Lync Server 2013: Übersicht über den Server für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Persistent Chat Server
ms:assetid: 23f7c886-304d-495a-ae70-3cbb44241acd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425717(v=OCS.15)
ms:contentKeyID: 48183622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cd18a5943332f8c612ba10b74317666d609d558
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="c8db4-102">Übersicht über den Server für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8db4-102">Overview of Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8db4-103">_**Letztes Änderungsstand des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="c8db4-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="c8db4-104">Lync Server 2013 Server für beständigen Chat ermöglicht Benutzern die Teilnahme an mehrteiligen, themenbasierten Unterhaltungen, die im Laufe der Zeit beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="c8db4-104">Lync Server 2013, Persistent Chat Server enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="c8db4-105">Der Server für beständigen Chat kann Ihrer Organisation dabei helfen, Folgendes zu tun:</span><span class="sxs-lookup"><span data-stu-id="c8db4-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="c8db4-106">Verbesserung der Kommunikation zwischen geografisch verteilten und funktionsübergreifenden Teams.</span><span class="sxs-lookup"><span data-stu-id="c8db4-106">Improve communication between geographically dispersed and cross-functional teams.</span></span> <span data-ttu-id="c8db4-107">Mithilfe des beständigen Chats können Teams Informationen, Ideen und Entscheidungen effizient miteinander teilen.</span><span class="sxs-lookup"><span data-stu-id="c8db4-107">By using Persistent Chat, teams can efficiently share information, ideas, and decisions with one another.</span></span> <span data-ttu-id="c8db4-108">Die an Chatrooms (Diskussionsforen) gestellten Nachrichten können dauerhaft verfügbar sein (das heißt, Sie können im Laufe der Zeit zur Verfügung stehen), damit Personen an unterschiedlichen Standorten und Abteilungen teilnehmen können, auch wenn Sie nicht gleichzeitig online sind.</span><span class="sxs-lookup"><span data-stu-id="c8db4-108">The messages posted to chat rooms (discussion forums) can persist (that is, can be available over time), so that people from different locations and departments can participate, even when they are not simultaneously online.</span></span> <span data-ttu-id="c8db4-109">Wenn ein Benutzer eine Verbindung mit einem Chatroom herstellt, wird der Backchat (eine konfigurierbare Anzahl von Chatverlaufs Meldungen) automatisch in den Chatroom geladen, um dem Benutzer einen Kontext für die Unterhaltung zu geben.</span><span class="sxs-lookup"><span data-stu-id="c8db4-109">When a user connects to a chat room, backchat (a configurable number of chat-history messages) is automatically loaded in the chat room to give the user a context for the conversation.</span></span>

  - <span data-ttu-id="c8db4-110">Verbesserung des Informationsbewusstseins.</span><span class="sxs-lookup"><span data-stu-id="c8db4-110">Improve information awareness.</span></span> <span data-ttu-id="c8db4-111">Mithilfe von clientseitigen filtern können Benutzerbedingungen definieren (beispielsweise Schlüsselwörter im Nachrichteninhalt) oder den Wert des Felds "von" in einer Nachricht, um eine Benachrichtigung zu erhalten, wenn diese Bedingungen in Chatnachrichten oder Chatroom-Nachrichten für beständigen Chat erfüllt werden.</span><span class="sxs-lookup"><span data-stu-id="c8db4-111">By using client-side filters, users can define conditions—such as keywords in message content, or the value of the "from" field in a message—to receive notification when those conditions are met in Persistent Chat instant messages or chat room messages.</span></span> <span data-ttu-id="c8db4-112">Auf diese Weise können Benutzer auf dem neuesten Stand der Inhalte bleiben, die Sie am meisten interessieren.</span><span class="sxs-lookup"><span data-stu-id="c8db4-112">This way, users can stay up-to-date with the content that interests them most.</span></span>

  - <span data-ttu-id="c8db4-113">Verbessern der Kommunikation mit ihrer erweiterten Organisation.</span><span class="sxs-lookup"><span data-stu-id="c8db4-113">Improve communication with their extended organization.</span></span> <span data-ttu-id="c8db4-114">Durch die einfache Zusammenarbeit bei lang andauernden Themen mit anderen Personen in der Organisation und durch die Bereitstellungeines beständigen Ortes zur gemeinsamen Nutzung von Informationen hilft beständiger Chat die Kommunikation zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="c8db4-114">By making it easy to collaborate over long-running topics with others in the organization, and by providing a persistent place to share information, Persistent Chat helps improve communication.</span></span>

  - <span data-ttu-id="c8db4-115">Verringerung der Informationsüberlastung.</span><span class="sxs-lookup"><span data-stu-id="c8db4-115">Reduce information overload.</span></span> <span data-ttu-id="c8db4-116">Benutzer können Chatrooms und Nachrichten von größtem Interesse mithilfe von clientseitigen Filtern verfolgen und Chatrooms hinzufügen, die Sie zu Ihrer Kontaktliste weitergeben möchten.</span><span class="sxs-lookup"><span data-stu-id="c8db4-116">Users can follow chat rooms and messages of most interest by using client-side filters, and can add chat rooms they want to follow to their contact list.</span></span>

  - <span data-ttu-id="c8db4-117">Gezielte Weitergabe von wichtigem Wissen und wichtigen Informationen.</span><span class="sxs-lookup"><span data-stu-id="c8db4-117">Increase dispersion of important knowledge and information.</span></span> <span data-ttu-id="c8db4-118">Dokumente und Links können in Unterhaltungen eingefügt werden, damit das gesamte Team darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="c8db4-118">Documents and links can be included within conversations for access by all the team.</span></span> <span data-ttu-id="c8db4-119">Wenn sie Fragen an ein großes Team stellen, können Benutzer von den Antworten der Fachbereichsexperten profitieren.</span><span class="sxs-lookup"><span data-stu-id="c8db4-119">By posting questions to a broader team, users can benefit from responses by subject matter experts.</span></span> <span data-ttu-id="c8db4-120">Durch die Integration in andere Informationssysteme können wichtige organisatorische Daten einfach an große Gruppen kommuniziert werden.</span><span class="sxs-lookup"><span data-stu-id="c8db4-120">Integration with other information systems enables important organizational data to be easily communicated to large groups.</span></span>

<span data-ttu-id="c8db4-121">Um Chatrooms in lync Server 2013 zu aktivieren, stellen Sie beständiger Chat von lync Server 2013 bereit.</span><span class="sxs-lookup"><span data-stu-id="c8db4-121">To enable chat rooms in Lync Server 2013, deploy Lync Server 2013 Persistent Chat.</span></span> <span data-ttu-id="c8db4-122">Informationen zum Aktivieren von Chatrooms finden Sie in <https://go.microsoft.com/fwlink/p/?linkid=270945>der Hilfe zum beständigen Chat unter.</span><span class="sxs-lookup"><span data-stu-id="c8db4-122">For information about enabling chat rooms, see the Persistent Chat Help at <https://go.microsoft.com/fwlink/p/?linkid=270945>.</span></span> <span data-ttu-id="c8db4-123">Wenn Benutzer für lync Server aktiviert sind und lync Server-Unterstützung bereitgestellt wird, können Benutzer lync 2013 beständigen Chat installieren und verwenden, um Chat Raum Unterstützung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c8db4-123">If users are enabled for Lync Server, and Lync Server support is deployed, users can install and use Lync 2013 Persistent Chat to provide chat room support.</span></span>

<span data-ttu-id="c8db4-124">Wenn Ihre Organisation Compliance-Vorschriften einhalten muss, können Sie optional den Compliance-Dienst für beständigen Chat bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c8db4-124">If your organization is required to follow compliance regulations, you can optionally deploy Persistent Chat Compliance service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

