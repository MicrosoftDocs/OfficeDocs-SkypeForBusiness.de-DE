---
title: Lync Server 2013 von Topologie-Änderungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3979aa0725b632a1b5910c5f7e27b9a6a28245d8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530392"
---
# <a name="topology-changes-in-lync-server-2013"></a><span data-ttu-id="ed87b-102">Topologie-Änderungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed87b-102">Topology changes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed87b-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ed87b-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ed87b-104">Topologie-Anforderungen und Überlegungen für lync Server 2013 unterscheiden sich von denen für frühere Versionen, wie in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ed87b-104">Topology requirements and considerations for Lync Server 2013 are different from those for earlier releases, as described in this section.</span></span>

<div>

## <a name="new-front-end-pools-architecture"></a><span data-ttu-id="ed87b-105">Neue Architektur der Front-End-Pools.</span><span class="sxs-lookup"><span data-stu-id="ed87b-105">New Front End Pools Architecture</span></span>

<span data-ttu-id="ed87b-106">In lync Server 2013 wurde die Architektur von Enterprise Edition-Front-End-Pools in eine verteilte Systemarchitektur geändert.</span><span class="sxs-lookup"><span data-stu-id="ed87b-106">In Lync Server 2013, the architecture of Enterprise Edition Front End pools has changed to a distributed systems architecture.</span></span>

<span data-ttu-id="ed87b-p101">Mit dieser neuen Architektur bildet die Back-End-Datenbank nicht mehr den Echtzeit-Datenspeicher in einem Pool. Die Informationen zu einem bestimmten Benutzer befinden sich auf drei Front-End-Servern im Pool. Für jeden Benutzer agiert ein Front-End-Server als Master für die Informationen des jeweiligen Benutzers und zwei weitere Front-End-Server dienen als Replikate. Wenn ein Front-End-Server ausfällt, wird ein anderer Front-End-Server, der als Replikat gedient hat, automatisch zum Master hochgestuft.</span><span class="sxs-lookup"><span data-stu-id="ed87b-p101">With this new architecture, the Back End database is no longer the real-time data store in a pool. Information about a particular user is kept on three Front End Servers in the pool. For each user, one Front End Server acts as the master for that user’s information, and two other Front End Servers serve as replicas. If a Front End Server goes down, another Front End Server which served as a replica is automatically promoted to master.</span></span>

<span data-ttu-id="ed87b-111">Dies passiert im Hintergrund und es ist nicht erforderlich, dass Administratoren wissen, welche Front-End-Server als Master für welche Benutzer agieren.</span><span class="sxs-lookup"><span data-stu-id="ed87b-111">This happens behind the scenes, and administrators do not need to know which Front End Servers are the masters for which users.</span></span> <span data-ttu-id="ed87b-112">Diese Verteilung der Datenspeicherung verbessert die Leistung und Skalierbarkeit innerhalb des Pools und eliminiert den einzelnen Ausfallpunkt eines einzelnen Back-End-Servers.</span><span class="sxs-lookup"><span data-stu-id="ed87b-112">This distribution of data storage improves performance and scalability within the pool, and eliminates the single point of failure of a single Back End Server.</span></span>

<span data-ttu-id="ed87b-113">Der Back-End-Server dient als Sicherungsspeicher für Benutzer- und Konferenzdaten und stellt außerdem den primären Speicher für andere Datenbanken, wie die Reaktionsgruppendatenbank.</span><span class="sxs-lookup"><span data-stu-id="ed87b-113">The Back End Server serves as backup storage for user and conference data, and is also the primary storage for other databases such as the Response Group database.</span></span>

<span data-ttu-id="ed87b-114">Diese Verbesserungen ziehen auch Änderungen bei der Planung und Wartung der Pools nach sich.</span><span class="sxs-lookup"><span data-stu-id="ed87b-114">These improvements also mean there are changes in how you plan and maintain your pools.</span></span> <span data-ttu-id="ed87b-115">Es wird empfohlen, dass alle Ihre Enterprise Edition-Front-End-Pools mindestens drei Front-End-Server enthalten, um die vollständige Anzahl von Replikaten bereitzustellen, für die die Front-End-Pool Architektur ausgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ed87b-115">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers, to provide the full number of replicas that the Front End pool architecture is designed for.</span></span> <span data-ttu-id="ed87b-116">Darüber hinaus müssen Sie beim Hinzufügen von Servern zu einer Front-End-Pool, beim Entfernen von Servern oder beim Aktualisieren von Servern bestimmte Verfahren befolgen.</span><span class="sxs-lookup"><span data-stu-id="ed87b-116">Additionally, you must follow certain procedures when adding servers to a Front End pool, removing servers from it, or upgrading servers.</span></span> <span data-ttu-id="ed87b-117">Weitere Informationen finden Sie unter [Topologien und Komponenten für Front-End-Server, Instant Messaging und Anwesenheit in lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="ed87b-117">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<div>

## <a name="server-role-topology-changes"></a><span data-ttu-id="ed87b-118">Änderungen der Topologie der Serverrolle</span><span class="sxs-lookup"><span data-stu-id="ed87b-118">Server Role Topology Changes</span></span>

<span data-ttu-id="ed87b-119">Einige Serverrollen, die zuvor auf separaten Servern ausgeführt wurden, sind jetzt in der Front-End-Serverrolle zusammengefasst, was die Hardwarekosten senkt</span><span class="sxs-lookup"><span data-stu-id="ed87b-119">Some server roles that previously ran on separate servers are now consolidated into the Front End Server role, enabling you to save on hardware costs</span></span>

  - <span data-ttu-id="ed87b-120">In lync Server 2013 ist A/V-Konferenzserver immer mit Front-End-Server verbunden.</span><span class="sxs-lookup"><span data-stu-id="ed87b-120">In Lync Server 2013, A/V Conferencing Server is always collocated with Front End Server.</span></span>

  - <span data-ttu-id="ed87b-p104">Die Front-Ends für die Überwachung und für die Archivierung sind jetzt mit dem Front-End-Server verbunden. Für die Überwachung und die Archivierung ist weiterhin eine separate Back-End-Datenbank erforderlich, die auf demselben Server wie die Back-End-Datenbank des Front-End-Pools verbunden oder auf separaten Back-End-Servern gehostet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ed87b-p104">The front ends for both Monitoring and Archiving are now always collocated with Front End Server. Monitoring and Archiving each still require a separate Back-End Database, which can be collocated on the same server as the Front End Pool’s back-end database, or can be hosted on separate Back-End Servers.</span></span>

  - <span data-ttu-id="ed87b-123">Der Server für beständigen Chat ist jetzt eine Serverrolle.</span><span class="sxs-lookup"><span data-stu-id="ed87b-123">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="ed87b-124">In Microsoft lync Server 2010 war der Gruppen Chat Server eine vertrauenswürdige Drittanbieteranwendung für Microsoft lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="ed87b-124">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="ed87b-125">In lync Server 2013 wird die Server Funktionalität für beständigen Chat mit drei neuen Serverrollen implementiert:</span><span class="sxs-lookup"><span data-stu-id="ed87b-125">In Lync Server 2013, Persistent Chat Server functionality is implemented using three new server roles:</span></span>
    
      - <span data-ttu-id="ed87b-126">**PersistentChatService:** Haupt Server Dienste für beständigen Chat, die als Front-End-Rolle implementiert sind</span><span class="sxs-lookup"><span data-stu-id="ed87b-126">**PersistentChatService:** Main Persistent Chat Server services implemented as a front end role</span></span>
    
      - <span data-ttu-id="ed87b-127">**PersistentChatStore:** Back-End-Server Rolle</span><span class="sxs-lookup"><span data-stu-id="ed87b-127">**PersistentChatStore:** Back End Server role</span></span>
    
      - <span data-ttu-id="ed87b-128">**PersistentChatComplianceStore:** Back-End-Server Rolle für die Compliance für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="ed87b-128">**PersistentChatComplianceStore:** Back End Server role for Persistent Chat Compliance</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

