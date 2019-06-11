---
title: 'Lync Server 2013: Features und Funktionen für Front-End-Server, Chat und Anwesenheit'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 739825eed3c8a3ba8239849e0c17c449180a2d95
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="decc4-102">Features und Funktionen für Front-End-Server, Chat und Anwesenheit in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="decc4-102">Features and functionality of Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="decc4-103">_**Letztes Änderungsdatum des Themas:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="decc4-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="decc4-104">Front-End-Server bieten die meisten lync Server-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="decc4-104">Front End Servers provide most Lync Server functionality.</span></span> <span data-ttu-id="decc4-105">Es stehen zwei Editionen zur Verfügung: lync Server Enterprise Edition, die in erster Linie für größere Organisationen konzipiert ist, und lync Server Standard Edition, die in erster Linie für kleinere Organisationen konzipiert ist, die eine kleinere Hardwareinvestition möchten und nicht höhere Verfügbarkeit erforderlich.</span><span class="sxs-lookup"><span data-stu-id="decc4-105">There are two editions available: Lync Server Enterprise Edition, which is designed primarily for larger organizations, and Lync Server Standard Edition, which is designed primarily for smaller organizations which want a smaller hardware investement and do not require high availability.</span></span> <span data-ttu-id="decc4-106">Beide Editionen unterstützen alle lync Server-Arbeitsauslastungen, einschließlich Chat, Anwesenheit, Konferenz und Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="decc4-106">Both editions support all Lync Server workloads including IM, presence, conferencing, and Enterprise Voice.</span></span>

<span data-ttu-id="decc4-107">Mit der Chatfunktion können Benutzer auf ihren Computern in Echtzeit über textbasierte Nachrichten miteinander kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="decc4-107">Instant messaging (IM) enables your users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="decc4-108">Es werden sowohl Chatsitzungen mit zwei Teilnehmern als auch Sitzungen mit mehreren Teilnehmern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="decc4-108">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="decc4-109">Ein Teilnehmer an einer Chatsitzung mit zwei Teilnehmern kann der Unterhaltung jederzeit einen dritten Teilnehmer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="decc4-109">A participant in a two-party IM conversation can add a third participant to the conversation at any time.</span></span> <span data-ttu-id="decc4-110">Wenn dies geschieht, ändert sich das Unterhaltungsfenster, um Konferenzfunktionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="decc4-110">When this happens, the Conversation window changes to support conferencing features.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="decc4-111">Lync-und Communicator-Clients werden, wenn Sie an einer 1:1-Kommunikation beteiligt sind, häufig als Peer-to-Peer bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="decc4-111">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="decc4-112">Technisch gesehen kommunizieren die beiden Clients in einer 1:1-Konversation mit der Instant Messaging-Multipoint-Steuereinheit (IMMCU) in der Mitte.</span><span class="sxs-lookup"><span data-stu-id="decc4-112">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="decc4-113">Die IMMCU ist eine Komponente des Front-End-Servers.</span><span class="sxs-lookup"><span data-stu-id="decc4-113">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="decc4-114">Wenn Sie den IMMCU in den erforderlichen Kommunikations Workflow einfügen, können Sie die Anrufdetailaufzeichnung und andere Features, die der Front-End-Server ermöglicht, aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="decc4-114">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="decc4-115">Die Kommunikation erfolgt von einem dynamischen Quell Port auf dem Client zum Front-End-Serverport TLS/TCP/5061 (unter der Voraussetzung, dass die empfohlene Transportschichtsicherheit verwendet wird).</span><span class="sxs-lookup"><span data-stu-id="decc4-115">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="decc4-116">Die Peer-to-Peer-Kommunikation (ebenso wie die Chat Unterhaltung mit mehreren Teilnehmern) ist im Entwurf nur möglich, wenn lync Server und IMMCU aktiv und verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="decc4-116">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<span data-ttu-id="decc4-117">*Anwesenheits* Informationen bieten Benutzern Informationen über den Status anderer Personen im Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="decc4-117">*Presence* provides information to users about the status of other on the network.</span></span> <span data-ttu-id="decc4-118">Der Anwesenheitsstatus eines Benutzers bietet Informationen, um anderen zu helfen, zu entscheiden, ob er versuchen soll, den Benutzer zu kontaktieren, und ob er Sofortnachrichten, Telefone oder e-Mails verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="decc4-118">A user’s presence status provides information to help others decide whether they should try to contact the user and whether to use instant messaging, phone, or email.</span></span> <span data-ttu-id="decc4-119">Anwesenheitsinformationen unterstützt die sofortige Kommunikation, wenn möglich, bietet aber auch Informationen darüber, ob sich ein Benutzer in einer Besprechung oder außerhalb des Büros befindet, was darauf hinweist, dass eine sofortige Kommunikation nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="decc4-119">Presence encourages instant communication when possible, but it also provides information about whether a user is in a meeting or out of the office, indicating that instant communication is not possible.</span></span> <span data-ttu-id="decc4-120">Dieser Anwesenheitsstatus wird in lync und anderen Anwendungen mit Anwesenheitsanzeige als Anwesenheitssymbol angezeigt, einschließlich des Microsoft Outlook-Messaging-und Zusammenarbeits Clients, Microsoft SharePoint Technologies, Microsoft Word und Microsoft Excel-Kalkulationstabelle. Software.</span><span class="sxs-lookup"><span data-stu-id="decc4-120">This presence status is displayed as a presence icon in Lync and other presence-aware applications, including the Microsoft Outlook messaging and collaboration client, Microsoft SharePoint technologies, Microsoft Word, and Microsoft Excel spreadsheet software.</span></span> <span data-ttu-id="decc4-121">Das Anwesenheitssymbol steht für die aktuelle Verfügbarkeit und Kommunikationsbereitschaft des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="decc4-121">The presence icon represents the user’s current availability and willingness to communicate.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

