---
title: 'Lync Server 2013: Topologieänderungen'
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
ms.openlocfilehash: c4453a9b5b8a5fcd60eaad1e437fd4800caddfba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a><span data-ttu-id="5fd81-102">Topologieänderungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fd81-102">Topology changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fd81-103">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5fd81-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5fd81-104">Topologie-Anforderungen und-Überlegungen für lync Server 2013 unterscheiden sich von denen für frühere Versionen, wie in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5fd81-104">Topology requirements and considerations for Lync Server 2013 are different from those for earlier releases, as described in this section.</span></span>

<div>

## <a name="new-front-end-pools-architecture"></a><span data-ttu-id="5fd81-105">Neue Front-End-Pools-Architektur</span><span class="sxs-lookup"><span data-stu-id="5fd81-105">New Front End Pools Architecture</span></span>

<span data-ttu-id="5fd81-106">In lync Server 2013 wurde die Architektur von Enterprise Edition-Front-End-Pools in eine verteilte Systemarchitektur geändert.</span><span class="sxs-lookup"><span data-stu-id="5fd81-106">In Lync Server 2013, the architecture of Enterprise Edition Front End pools has changed to a distributed systems architecture.</span></span>

<span data-ttu-id="5fd81-107">Mit dieser neuen Architektur ist die Back-End-Datenbank nicht mehr der Echtzeitdaten Speicher in einem Pool.</span><span class="sxs-lookup"><span data-stu-id="5fd81-107">With this new architecture, the Back End database is no longer the real-time data store in a pool.</span></span> <span data-ttu-id="5fd81-108">Informationen zu einem bestimmten Benutzer werden auf drei Front-End-Servern im Pool aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="5fd81-108">Information about a particular user is kept on three Front End Servers in the pool.</span></span> <span data-ttu-id="5fd81-109">Für jeden Benutzer fungiert ein Front-End-Server als Master für die Informationen dieses Benutzers, und zwei weitere Front-End-Server dienen als Replikate.</span><span class="sxs-lookup"><span data-stu-id="5fd81-109">For each user, one Front End Server acts as the master for that user’s information, and two other Front End Servers serve as replicas.</span></span> <span data-ttu-id="5fd81-110">Wenn ein Front-End-Server ausfällt, wird ein anderer Front-End-Server, der als Replikat fungiert, automatisch zum Master heraufgestuft.</span><span class="sxs-lookup"><span data-stu-id="5fd81-110">If a Front End Server goes down, another Front End Server which served as a replica is automatically promoted to master.</span></span>

<span data-ttu-id="5fd81-111">Dies geschieht hinter den Kulissen, und Administratoren müssen nicht wissen, welche Front-End-Server die Master für welche Benutzer sind.</span><span class="sxs-lookup"><span data-stu-id="5fd81-111">This happens behind the scenes, and administrators do not need to know which Front End Servers are the masters for which users.</span></span> <span data-ttu-id="5fd81-112">Diese Verteilung der Datenspeicherung verbessert die Leistung und Skalierbarkeit innerhalb des Pools und beseitigt den einzelnen Fehlerpunkt eines einzelnen Back-End-Servers.</span><span class="sxs-lookup"><span data-stu-id="5fd81-112">This distribution of data storage improves performance and scalability within the pool, and eliminates the single point of failure of a single Back End Server.</span></span>

<span data-ttu-id="5fd81-113">Der Back-End-Server dient als Sicherungsspeicher für Benutzer-und Konferenzdaten und ist auch der primäre Speicher für andere Datenbanken wie die Datenbank der Reaktionsgruppe.</span><span class="sxs-lookup"><span data-stu-id="5fd81-113">The Back End Server serves as backup storage for user and conference data, and is also the primary storage for other databases such as the Response Group database.</span></span>

<span data-ttu-id="5fd81-114">Diese Verbesserungen besagen auch, dass es Änderungen bei der Planung und Verwaltung Ihrer Pools gibt.</span><span class="sxs-lookup"><span data-stu-id="5fd81-114">These improvements also mean there are changes in how you plan and maintain your pools.</span></span> <span data-ttu-id="5fd81-115">Wir empfehlen, dass alle Ihre Enterprise Edition-Front-End-Pools mindestens drei Front-End-Server umfassen, um die vollständige Anzahl von Replikaten bereitzustellen, für die die Front-End-Pool-Architektur konzipiert ist.</span><span class="sxs-lookup"><span data-stu-id="5fd81-115">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers, to provide the full number of replicas that the Front End pool architecture is designed for.</span></span> <span data-ttu-id="5fd81-116">Darüber hinaus müssen Sie bestimmte Verfahren ausführen, wenn Sie einem Front-End-Pool Server hinzufügen, Server davon entfernen oder Server aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="5fd81-116">Additionally, you must follow certain procedures when adding servers to a Front End pool, removing servers from it, or upgrading servers.</span></span> <span data-ttu-id="5fd81-117">Weitere Informationen finden Sie unter [Topologien und Komponenten für Front-End-Server, Instant Messaging und Anwesenheitsinformationen in lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="5fd81-117">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<div>

## <a name="server-role-topology-changes"></a><span data-ttu-id="5fd81-118">Änderungen der Server Rollen Topologie</span><span class="sxs-lookup"><span data-stu-id="5fd81-118">Server Role Topology Changes</span></span>

<span data-ttu-id="5fd81-119">Einige Serverrollen, die zuvor auf separaten Servern ausgeführt wurden, werden jetzt in der Front-End-Serverrolle konsolidiert, sodass Sie die Hardwarekosten sparen können.</span><span class="sxs-lookup"><span data-stu-id="5fd81-119">Some server roles that previously ran on separate servers are now consolidated into the Front End Server role, enabling you to save on hardware costs</span></span>

  - <span data-ttu-id="5fd81-120">In lync Server 2013 ist der A/V-Konferenzserver immer mit dem Front-End-Server verbunden.</span><span class="sxs-lookup"><span data-stu-id="5fd81-120">In Lync Server 2013, A/V Conferencing Server is always collocated with Front End Server.</span></span>

  - <span data-ttu-id="5fd81-121">Die Front-Ends für Überwachung und Archivierung sind jetzt immer mit dem Front-End-Server verbunden.</span><span class="sxs-lookup"><span data-stu-id="5fd81-121">The front ends for both Monitoring and Archiving are now always collocated with Front End Server.</span></span> <span data-ttu-id="5fd81-122">Für die Überwachung und Archivierung ist immer noch eine separate Back-End-Datenbank erforderlich, die sich auf demselben Server wie die Back-End-Datenbank des Front-End-Pools befindet oder auf separaten Back-End-Servern gehostet werden kann.</span><span class="sxs-lookup"><span data-stu-id="5fd81-122">Monitoring and Archiving each still require a separate Back-End Database, which can be collocated on the same server as the Front End Pool’s back-end database, or can be hosted on separate Back-End Servers.</span></span>

  - <span data-ttu-id="5fd81-123">Der beständige Chat Server ist nun eine Serverrolle.</span><span class="sxs-lookup"><span data-stu-id="5fd81-123">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="5fd81-124">In Microsoft lync Server 2010 war der Gruppen-Chat Server eine vertrauenswürdige Anwendung eines Drittanbieters für Microsoft lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5fd81-124">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="5fd81-125">In lync Server 2013 wird die Funktion des beständigen Chat Servers mit drei neuen Serverrollen implementiert:</span><span class="sxs-lookup"><span data-stu-id="5fd81-125">In Lync Server 2013, Persistent Chat Server functionality is implemented using three new server roles:</span></span>
    
      - <span data-ttu-id="5fd81-126">**PersistentChatService:** Die wichtigsten Server Dienste für beständigen Chat, die als Front-End-Rolle implementiert sind</span><span class="sxs-lookup"><span data-stu-id="5fd81-126">**PersistentChatService:** Main Persistent Chat Server services implemented as a front end role</span></span>
    
      - <span data-ttu-id="5fd81-127">**PersistentChatStore:** Back-End-Server Rolle</span><span class="sxs-lookup"><span data-stu-id="5fd81-127">**PersistentChatStore:** Back End Server role</span></span>
    
      - <span data-ttu-id="5fd81-128">**PersistentChatComplianceStore:** Back-End-Server Rolle für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="5fd81-128">**PersistentChatComplianceStore:** Back End Server role for Persistent Chat Compliance</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

