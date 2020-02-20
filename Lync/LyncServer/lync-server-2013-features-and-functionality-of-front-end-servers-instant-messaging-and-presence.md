---
title: 'Lync Server 2013: Features und Funktionen für Front-End-Server, Instant Messaging und Anwesenheit'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 639df8bdcee7531895eaafe9dd8ca5fac3f6fc3d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="eebea-102">Features und Funktionen von Front-End-Servern, Chatnachrichten und Anwesenheitsinformationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eebea-102">Features and functionality of Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eebea-103">_**Letztes Änderungsstand des Themas:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="eebea-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="eebea-104">Front-End-Server bieten die meisten lync Server Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="eebea-104">Front End Servers provide most Lync Server functionality.</span></span> <span data-ttu-id="eebea-105">Es stehen zwei Editionen zur Verfügung: lync Server Enterprise Edition, die in erster Linie für größere Organisationen entwickelt wurde, und lync Server Standard Edition, die in erster Linie für kleinere Organisationen entwickelt wurde, die einen kleineren Hardwareinvestition wünschen und nicht hohe Verfügbarkeit erforderlich.</span><span class="sxs-lookup"><span data-stu-id="eebea-105">There are two editions available: Lync Server Enterprise Edition, which is designed primarily for larger organizations, and Lync Server Standard Edition, which is designed primarily for smaller organizations which want a smaller hardware investement and do not require high availability.</span></span> <span data-ttu-id="eebea-106">Beide Editionen unterstützen alle lync Server Arbeitslasten einschließlich Sofortnachrichten, Anwesenheit, Konferenzen und Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="eebea-106">Both editions support all Lync Server workloads including IM, presence, conferencing, and Enterprise Voice.</span></span>

<span data-ttu-id="eebea-p102">Mit der Sofortnachrichtenfunktion (Instant Messaging, IM) können Benutzer auf ihren Computern in Echtzeit über textbasierte Nachrichten miteinander kommunizieren. Es werden sowohl Sofortnachrichtensitzungen mit zwei Teilnehmern als auch Sitzungen mit mehreren Teilnehmern unterstützt. Ein Teilnehmer an einer Sofortnachrichtensitzung mit zwei Teilnehmern kann der Unterhaltung jederzeit einen dritten Teilnehmer hinzufügen. Wenn dies geschieht, ändert sich das Unterhaltungsfenster, um Konferenzfunktionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="eebea-p102">Instant messaging (IM) enables your users to communicate with each other in real time on their computers using text-based messages. Both two-party and multiparty IM sessions are supported. A participant in a two-party IM conversation can add a third participant to the conversation at any time. When this happens, the Conversation window changes to support conferencing features.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="eebea-111">Lync-und Communicator-Clients werden, wenn Sie an einer Kommunikation mit einem einzelnen beteiligt sind, häufig als Peer-to-Peer bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="eebea-111">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="eebea-112">Technisch gesehen kommunizieren die beiden Clients in einer eins-zu-eins-Unterhaltung mit der Instant Messaging-Multipoint-Steuereinheit (IMMCU) in der Mitte.</span><span class="sxs-lookup"><span data-stu-id="eebea-112">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="eebea-113">IMMCU ist eine Komponente von Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="eebea-113">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="eebea-114">Wenn Sie die IMMCU in den erforderlichen Kommunikations Workflow einfügen, können Sie die Aufzeichnung von Anrufdetails und andere Features, die der Front-End-Server aktiviert, aktivieren.</span><span class="sxs-lookup"><span data-stu-id="eebea-114">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="eebea-115">Die Kommunikation erfolgt über einen dynamischen Quell Port auf dem Client zum Front-End-Server Port TLS/TCP/5061 (vorausgesetzt, dass die empfohlene Transportschichtsicherheit verwendet wird).</span><span class="sxs-lookup"><span data-stu-id="eebea-115">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="eebea-116">Die Peer-zu-Peer-Kommunikation (sowie mehr Parteien-Chat) ist nur möglich, wenn lync Server und IMMCU aktiv und verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="eebea-116">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<span data-ttu-id="eebea-117">*Presence* stellt Benutzern Informationen über den Status von other im Netzwerk zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="eebea-117">*Presence* provides information to users about the status of other on the network.</span></span> <span data-ttu-id="eebea-118">Der Anwesenheitsstatus eines Benutzers enthält Informationen, um anderen zu helfen, zu entscheiden, ob Sie versuchen sollen, den Benutzer zu kontaktieren und ob Chat, Telefon oder e-Mail verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="eebea-118">A user’s presence status provides information to help others decide whether they should try to contact the user and whether to use instant messaging, phone, or email.</span></span> <span data-ttu-id="eebea-119">Anwesenheit fördert die sofortige Kommunikation, wenn möglich, bietet aber auch Informationen darüber, ob sich ein Benutzer in einer Besprechung oder außerhalb des Büros befindet, was bedeutet, dass eine sofortige Kommunikation nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="eebea-119">Presence encourages instant communication when possible, but it also provides information about whether a user is in a meeting or out of the office, indicating that instant communication is not possible.</span></span> <span data-ttu-id="eebea-120">Dieser Anwesenheitsstatus wird in lync und anderen Anwendungen mit Anwesenheitsinformationen als Anwesenheitssymbol angezeigt, einschließlich der Microsoft Outlook Messaging-und Zusammenarbeits Clients, Microsoft SharePoint-Technologien, Microsoft Word und Microsoft Excel Kalkulationstabelle Software.</span><span class="sxs-lookup"><span data-stu-id="eebea-120">This presence status is displayed as a presence icon in Lync and other presence-aware applications, including the Microsoft Outlook messaging and collaboration client, Microsoft SharePoint technologies, Microsoft Word, and Microsoft Excel spreadsheet software.</span></span> <span data-ttu-id="eebea-121">Das Anwesenheitssymbol stellt die aktuelle Verfügbarkeit und Bereitschaft des Benutzers zur Kommunikation dar.</span><span class="sxs-lookup"><span data-stu-id="eebea-121">The presence icon represents the user’s current availability and willingness to communicate.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

