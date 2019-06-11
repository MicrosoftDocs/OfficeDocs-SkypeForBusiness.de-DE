---
title: Verwalten von Lync Server 2013 Persistent Chat Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Lync Server 2013, Persistent Chat Server
ms:assetid: 82befdc6-5d32-45f1-bfd7-aaedffed1ab8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398657(v=OCS.15)
ms:contentKeyID: 48184672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de49e9843c5243457d1c4d736d9bfeda246f042e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-persistent-chat-server"></a><span data-ttu-id="c7110-102">Verwalten von Lync Server 2013 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="c7110-102">Managing Lync Server 2013, Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7110-103">_**Letztes Änderungsdatum des Themas:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="c7110-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="c7110-104">Sie können lync Server 2013, beständiger Chat Server verwenden, um mehreren Benutzern die Teilnahme an Unterhaltungen zu ermöglichen, in denen Sie Inhalte zu bestimmten Themen, einschließlich Text, Links und Dateien, Posten und darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="c7110-104">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="c7110-105">Obwohl Benutzer während einer Sitzung in Echtzeit kommunizieren können, ist der Inhalt jeder Sitzung persistent, was bedeutet, dass Sie nach dem Ende einer Sitzung weiterhin zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="c7110-105">Although users can communicate in real time during a session, the content of each session is persistent, which means that it continues to be available after a session ends.</span></span>

<span data-ttu-id="c7110-106">Der Inhalt beständiger Chatrooms besteht in erster Linie aus kurzen Textnachrichten, kann aber auch längere Nachrichten, die als Text *Abschnitte*bezeichnet werden, sowie Links, Emoticons und hochgeladene Dokumente umfassen.</span><span class="sxs-lookup"><span data-stu-id="c7110-106">The content of Persistent Chat rooms consists primarily of short text messages, although it can include longer messages, referred to as *stories*, and also hyperlinks, emoticons, and uploaded documents.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7110-107">Dateiupload und-Download wird vom lync 2013-Client nicht unterstützt. Sie wird jedoch weiterhin von lync Server 2013, beständiger Chat Server, unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c7110-107">File upload and download is not supported by the Lync 2013 client; however, it is still supported by Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="c7110-108">Der Legacy-Gruppen-Chat-Client kann Dateien Posten und anzeigen, aber wenn auf den gleichen Chatroom über den lync 2013-Client zugegriffen wird, kann er nicht auf die Dateien zugreifen.</span><span class="sxs-lookup"><span data-stu-id="c7110-108">The legacy Group Chat client can post and view files, but if the same chat room is accessed via the Lync 2013 client, it will not be able to access the files.</span></span>



</div>

<span data-ttu-id="c7110-109">Der Zugriff auf einen Chatroom wird durch eine Mitgliedschaftsliste gesteuert.</span><span class="sxs-lookup"><span data-stu-id="c7110-109">Access to a chat room is controlled by a membership list.</span></span> <span data-ttu-id="c7110-110">Der gesamte Verlauf des Chatrooms steht jedem Mitglied zur chronologischen Überprüfung oder Volltextsuche zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="c7110-110">The entire chat room history is available to any member for chronological review or full-text search.</span></span> <span data-ttu-id="c7110-111">Details zur Verwendung des beständigen Chat-Clients finden Sie unter [Planen der Clients in lync Server 2013](lync-server-2013-planning-for-clients.md) in der Planungsdokumentation und [Bereitstellen von Clients und Geräten in lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c7110-111">For details about using the Persistent Chat client, see [Planning for clients in Lync Server 2013](lync-server-2013-planning-for-clients.md) in the Planning documentation, and [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

<span data-ttu-id="c7110-112">Wenn Sie den Server für beständigen Chat für Ihre Organisation einrichten, geben Sie die anfängliche Konfiguration während der Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="c7110-112">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="c7110-113">Es kann jedoch vorkommen, dass Sie ändern möchten, wie Sie die Unterstützung für beständigen Chat Server implementieren.</span><span class="sxs-lookup"><span data-stu-id="c7110-113">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="c7110-114">So können Sie beispielsweise für ein bestimmtes Team oder eine bestimmte Gruppe in Ihrer Organisation die Unterstützung für beständigen Chat Server und die Steuerelemente anders einrichten.</span><span class="sxs-lookup"><span data-stu-id="c7110-114">For example, you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="c7110-115">Dieser Abschnitt enthält Informationen und Verfahren, die Ihnen bei der Anpassung ihrer beständigen Chat Server Bereitstellung helfen.</span><span class="sxs-lookup"><span data-stu-id="c7110-115">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="c7110-116">Ausführliche Informationen zu den Features und Funktionen, die Sie für den Server für beständigen Chat konfigurieren können, finden Sie unter [Definieren der Anforderungen Ihrer Organisation für beständigen Chat Server in lync Server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) in der Planungsdokumentation und [Funktionsweise des beständigen Chats Server funktioniert in lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in der Planning-Dokumentation, Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c7110-116">For details about the features and functionality that you can configure for Persistent Chat Server, see [Defining your organization's requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) in the Planning documentation, and [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="c7110-117">Details zum Bereitstellen des beständigen Chat Servers für lync Server 2013 finden Sie unter [Bereitstellen eines beständigen Chat Servers in lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c7110-117">For details about deploying Persistent Chat Server for Lync Server 2013, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c7110-118">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c7110-118">In This Section</span></span>

  - [<span data-ttu-id="c7110-119">Funktionsweise des beständigen Chat Servers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7110-119">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="c7110-120">Verwenden von Kategorien zur Verwaltung des Servers für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="c7110-120">Using categories to administer Persistent Chat Server</span></span>](using-categories-to-administer-persistent-chat-server.md)

  - [<span data-ttu-id="c7110-121">Grundlegendes zur dauerhaften Chat Mitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="c7110-121">Understanding Persistent Chat membership</span></span>](understanding-persistent-chat-membership.md)

  - [<span data-ttu-id="c7110-122">Bewährte Methoden für den Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="c7110-122">Persistent Chat Server best practices</span></span>](persistent-chat-server-best-practices.md)

  - [<span data-ttu-id="c7110-123">Verwalten von Kategorien, Chatrooms und Add-Ins in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7110-123">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)

  - [<span data-ttu-id="c7110-124">Verwalten des Benutzerzugriffs für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7110-124">Managing Persistent Chat user access in Lync Server 2013</span></span>](lync-server-2013-managing-persistent-chat-user-access.md)

  - [<span data-ttu-id="c7110-125">Betreiben und Verwalten des Systems für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7110-125">Operating and maintaining the Persistent Chat system in Lync Server 2013</span></span>](lync-server-2013-operating-and-maintaining-the-persistent-chat-system.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

