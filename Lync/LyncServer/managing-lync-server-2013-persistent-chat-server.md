---
title: Verwalten von Lync Server 2013 Persistent Chat Server
description: Verwalten von lync Server 2013 Server für beständigen Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server 2013, Persistent Chat Server
ms:assetid: 82befdc6-5d32-45f1-bfd7-aaedffed1ab8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398657(v=OCS.15)
ms:contentKeyID: 48184672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe5306c79c738d61b70c3dd079fb55650e6fdae9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544581"
---
# <a name="managing-lync-server-2013-persistent-chat-server"></a><span data-ttu-id="763c8-103">Verwalten von Lync Server 2013 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="763c8-103">Managing Lync Server 2013, Persistent Chat Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="763c8-104">_**Letztes Änderungsstand des Themas:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="763c8-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="763c8-105">Sie können lync Server 2013 Server für beständigen Chat verwenden, um mehreren Benutzern die Teilnahme an Unterhaltungen zu ermöglichen, in denen Sie Inhalte zu bestimmten Themen, einschließlich Text, Links und Dateien, veröffentlichen und auf diese zugreifen.</span><span class="sxs-lookup"><span data-stu-id="763c8-105">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="763c8-106">Obwohl Benutzer während einer Sitzung in Echtzeit kommunizieren können, wird der Inhalt jeder Sitzung dauerhaft gespeichert und steht somit weiterhin zur Verfügung, nachdem eine Sitzung beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="763c8-106">Although users can communicate in real time during a session, the content of each session is persistent, which means that it continues to be available after a session ends.</span></span>

<span data-ttu-id="763c8-107">Der Inhalt von beständigen Chatrooms besteht in erster Linie aus kurzen Textnachrichten, kann aber auch längere Nachrichten enthalten, die als *Stories*bezeichnet werden, sowie Hyperlinks, Emoticons und hochgeladene Dokumente.</span><span class="sxs-lookup"><span data-stu-id="763c8-107">The content of Persistent Chat rooms consists primarily of short text messages, although it can include longer messages, referred to as *stories*, and also hyperlinks, emoticons, and uploaded documents.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="763c8-108">Dateiupload und-Download wird vom lync 2013-Client nicht unterstützt; Sie wird jedoch weiterhin von lync Server 2013 Server für beständigen Chat unterstützt.</span><span class="sxs-lookup"><span data-stu-id="763c8-108">File upload and download is not supported by the Lync 2013 client; however, it is still supported by Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="763c8-109">Der Legacy Gruppen Chat-Client kann Dateien bereitstellen und anzeigen, wenn jedoch auf den gleichen Chatroom über den lync 2013-Client zugegriffen wird, kann er nicht auf die Dateien zugreifen.</span><span class="sxs-lookup"><span data-stu-id="763c8-109">The legacy Group Chat client can post and view files, but if the same chat room is accessed via the Lync 2013 client, it will not be able to access the files.</span></span>



</div>

<span data-ttu-id="763c8-110">Der Zugang zu einem Chatroom wird durch eine Mitgliederliste gesteuert.</span><span class="sxs-lookup"><span data-stu-id="763c8-110">Access to a chat room is controlled by a membership list.</span></span> <span data-ttu-id="763c8-111">Der gesamte Chatroomverlauf steht allen Mitgliedern für den chronologischen Rückblick oder die Volltextsuche zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="763c8-111">The entire chat room history is available to any member for chronological review or full-text search.</span></span> <span data-ttu-id="763c8-112">Ausführliche Informationen zur Verwendung des Clients für beständigen Chat finden Sie in der Planungsdokumentation unter [Planning for Clients in lync Server 2013](lync-server-2013-planning-for-clients.md) und [Deploying Clients and Devices in lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="763c8-112">For details about using the Persistent Chat client, see [Planning for clients in Lync Server 2013](lync-server-2013-planning-for-clients.md) in the Planning documentation, and [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

<span data-ttu-id="763c8-113">Wenn Sie den Server für beständigen Chat für Ihre Organisation einrichten, geben Sie die anfängliche Konfiguration während der Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="763c8-113">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="763c8-114">Es kann jedoch vorkommen, dass Sie ändern möchten, wie Sie die Server Unterstützung für beständigen Chat implementieren.</span><span class="sxs-lookup"><span data-stu-id="763c8-114">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="763c8-115">Beispielsweise müssen Sie die Server Unterstützung für beständigen Chat und die Steuerelemente für ein bestimmtes Team oder eine bestimmte Gruppe in Ihrer Organisation unterschiedlich einrichten.</span><span class="sxs-lookup"><span data-stu-id="763c8-115">For example, you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="763c8-116">Dieser Abschnitt enthält Informationen und Verfahren, mit denen Sie Ihre Server Bereitstellung für beständigen Chat anpassen können.</span><span class="sxs-lookup"><span data-stu-id="763c8-116">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="763c8-117">Ausführliche Informationen zu den Features und Funktionen, die Sie für den Server für beständigen Chat konfigurieren können, finden Sie unter [Definieren der Anforderungen Ihrer Organisation für den Server für beständigen Chat in lync Server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) in der Planungsdokumentation und Funktions [Weise des Servers für beständigen Chat in lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in der Planungsdokumentation, in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="763c8-117">For details about the features and functionality that you can configure for Persistent Chat Server, see [Defining your organization's requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) in the Planning documentation, and [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="763c8-118">Ausführliche Informationen zum Bereitstellen des Servers für beständigen Chat für lync Server 2013 finden Sie unter [Deploying persistent Chat Server in lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="763c8-118">For details about deploying Persistent Chat Server for Lync Server 2013, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="763c8-119">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="763c8-119">In This Section</span></span>

  - [<span data-ttu-id="763c8-120">Funktionsweise von persistent Chat Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="763c8-120">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="763c8-121">Verwenden von Kategorien zum Verwalten des Servers für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="763c8-121">Using categories to administer Persistent Chat Server</span></span>](using-categories-to-administer-persistent-chat-server.md)

  - [<span data-ttu-id="763c8-122">Grundlegendes zur Mitgliedschaft im beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="763c8-122">Understanding Persistent Chat membership</span></span>](understanding-persistent-chat-membership.md)

  - [<span data-ttu-id="763c8-123">Bewährte Methoden für beständigen Chat Server</span><span class="sxs-lookup"><span data-stu-id="763c8-123">Persistent Chat Server best practices</span></span>](persistent-chat-server-best-practices.md)

  - [<span data-ttu-id="763c8-124">Verwalten von Kategorien, Räumen und Add-Ins in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="763c8-124">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)

  - [<span data-ttu-id="763c8-125">Verwalten des Benutzerzugriffs für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="763c8-125">Managing Persistent Chat user access in Lync Server 2013</span></span>](lync-server-2013-managing-persistent-chat-user-access.md)

  - [<span data-ttu-id="763c8-126">Betreiben und Verwalten des Systems für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="763c8-126">Operating and maintaining the Persistent Chat system in Lync Server 2013</span></span>](lync-server-2013-operating-and-maintaining-the-persistent-chat-system.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

