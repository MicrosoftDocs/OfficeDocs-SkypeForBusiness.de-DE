---
title: 'Lync Server 2013: Erforderliche Ressourcen für den Server für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31683641e50a3e3bc898841b0cf4b0911e046262
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723825"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="b7900-102">Erforderliche Ressourcen für den Server für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7900-102">Required resources for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7900-103">_**Letztes Änderungsdatum des Themas:** 2016-02-05_</span><span class="sxs-lookup"><span data-stu-id="b7900-103">_**Topic Last Modified:** 2016-02-05_</span></span>

<span data-ttu-id="b7900-104">Hochverfügbarkeit und Disaster Recovery für beständigen Chat Server erfordern zusätzliche Ressourcen, die über das hinausgehen, was in der Regel für den vollständigen Betrieb benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="b7900-104">High availability and disaster recovery for Persistent Chat Server requires additional resources beyond what is typically needed for full operation.</span></span> <span data-ttu-id="b7900-105">Bevor Sie den beständigen Chat Server für Hochverfügbarkeit und Disaster Recovery konfigurieren, stellen Sie sicher, dass Sie über die folgenden Ressourcen verfügen, die für den standardmäßigen Serverbetrieb des beständigen Chats erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b7900-105">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following resources in addition to what is required for standard Persistent Chat Server operation.</span></span> <span data-ttu-id="b7900-106">Weitere Konfigurationsinformationen finden Sie unter [Konfigurieren des beständigen Chat Servers in lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="b7900-106">For additional configuration information, see [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span></span>

  - <span data-ttu-id="b7900-107">Eine dedizierte Datenbankinstanz, die sich im gleichen physikalischen Rechenzentrum befindet, in dem sich das Home-Front-End des Server Diensts für beständigen Chat befindet.</span><span class="sxs-lookup"><span data-stu-id="b7900-107">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="b7900-108">Diese Datenbank dient als SQL Server-Spiegelung für die primäre Datenbank für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="b7900-108">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="b7900-109">Optional können Sie einen zusätzlichen SQL-Server als Spiegelungs Zeuge festlegen, wenn Sie ein automatisches Failover zur Spiegeldatenbank durch stellen möchten.</span><span class="sxs-lookup"><span data-stu-id="b7900-109">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>

  - <span data-ttu-id="b7900-110">Eine dedizierte Datenbankinstanz in dem anderen physischen Rechenzentrum.</span><span class="sxs-lookup"><span data-stu-id="b7900-110">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="b7900-111">Diese Datenbank dient als SQL Server-Protokollversand-sekundäre Datenbank für die Datenbank im primären Rechenzentrum.</span><span class="sxs-lookup"><span data-stu-id="b7900-111">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>

  - <span data-ttu-id="b7900-112">Eine dedizierte Datenbankinstanz, die als SQL Server-Spiegelung für die sekundäre Datenbank fungieren soll.</span><span class="sxs-lookup"><span data-stu-id="b7900-112">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="b7900-113">Optional können Sie einen zusätzlichen SQL Server als Spiegelungs Zeuge auf dem Server angeben.</span><span class="sxs-lookup"><span data-stu-id="b7900-113">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="b7900-114">Beide Instanzen müssen sich im selben physischen Rechenzentrum wie die sekundäre Datenbank befinden.</span><span class="sxs-lookup"><span data-stu-id="b7900-114">Both of these must be located in the same physical data center as the secondary database.</span></span>

  - <span data-ttu-id="b7900-115">Wenn die Kompatibilität des beständigen Chat Servers aktiviert ist, sind zusätzliche drei dedizierte Datenbankinstanzen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b7900-115">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="b7900-116">Ihre Verteilung ist mit denen identisch, die zuvor für die persistente Chat-Datenbank beschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="b7900-116">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="b7900-117">Es ist zwar möglich, dass die Compliance-Datenbank dieselbe SQL Server-Instanz wie die persistente Chat-Datenbank hat, wir empfehlen jedoch eigenständige Instanzen für eine höhere Verfügbarkeit und Disaster Recovery.</span><span class="sxs-lookup"><span data-stu-id="b7900-117">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, we recommend standalone instances for high availability and disaster recovery.</span></span>

  - <span data-ttu-id="b7900-118">Es muss eine Dateifreigabe erstellt und für die Transaktionsprotokolle des SQL Server-Protokollversands festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b7900-118">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="b7900-119">Alle SQL-Server in beiden Rechenzentren, in denen persistente Chat Datenbanken ausgeführt werden, müssen über Lese-/Schreibzugriff auf diese Dateifreigabe verfügen.</span><span class="sxs-lookup"><span data-stu-id="b7900-119">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="b7900-120">Diese Freigabe wird nicht als Teil einer FileStore-Rolle definiert.</span><span class="sxs-lookup"><span data-stu-id="b7900-120">This share is not defined as part of a FileStore role.</span></span>

  - <span data-ttu-id="b7900-121">Eine Dateifreigabe auf dem sekundären Datenbankserver, die als Zielordner für die SQL Server-Transaktionsprotokolle fungieren soll, die aus der Dateifreigabe des primären Servers kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="b7900-121">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b7900-122">Aktive beständige Chat Server in einem beständigen Chat Serverpool müssen sich in derselben Zeitzone befinden wie der lync-Pool für den nächsten Hop, der in der Topologie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b7900-122">Active Persistent Chat servers in a Persistent Chat Server pool MUST reside in the same time zone as the next hop Lync Pool defined in the topology.</span></span>



</div>

<span data-ttu-id="b7900-123">Die folgenden Abbildungen enthalten Beispiele dafür, wie der gesamte Server Pool für beständigen Chat in den beiden unterschiedlichen gedehnten Pool Topologien konfiguriert werden kann:</span><span class="sxs-lookup"><span data-stu-id="b7900-123">The following figures provide examples about how the entire Persistent Chat Server pool can be configured in the two different stretched pool topologies:</span></span>

  - <span data-ttu-id="b7900-124">Gedehnter beständiger Chat Server Pool, wenn Rechenzentren mit hoher Bandbreite/geringer Latenz geographisch lokalisiert sind.</span><span class="sxs-lookup"><span data-stu-id="b7900-124">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>

  - <span data-ttu-id="b7900-125">Gedehnter beständiger Chat Server Pool, wenn Rechenzentren mit niedriger Bandbreite/hoher Latenz geografischer Standort sind.</span><span class="sxs-lookup"><span data-stu-id="b7900-125">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="b7900-126">Die folgende Abbildung zeigt eine gedehnte Server Pooltopologie mit beständigem Chat, in der Rechenzentren mit hoher Bandbreite/geringer Latenz geographisch lokalisiert sind.</span><span class="sxs-lookup"><span data-stu-id="b7900-126">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span>

<span data-ttu-id="b7900-127">**Gedehnter beständiger Chat Server Pool, wenn Rechenzentren mit hoher Bandbreite/geringer Latenz geographisch lokalisiert sind.**</span><span class="sxs-lookup"><span data-stu-id="b7900-127">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.**</span></span>

<span data-ttu-id="b7900-128">![Beständiger Chat Server Pool HBW-Konfigurationsprüfung](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Beständiger Chat Server Pool HBW-Konfigurationsprüfung")</span><span class="sxs-lookup"><span data-stu-id="b7900-128">![Persistent Chat Server pool HBW configuration exam](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Persistent Chat Server pool HBW configuration exam")</span></span>

<span data-ttu-id="b7900-129">Die folgende Abbildung zeigt eine gedehnte Server Pooltopologie mit beständigem Chat, in der Rechenzentren mit niedriger Bandbreite/hoher Latenz geografisch lokalisiert sind.</span><span class="sxs-lookup"><span data-stu-id="b7900-129">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="b7900-130">**Gedehnter beständiger Chat Server Pool, wenn Rechenzentren mit niedriger Bandbreite/hoher Latenz geografischer Standort sind.**</span><span class="sxs-lookup"><span data-stu-id="b7900-130">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.**</span></span>

<span data-ttu-id="b7900-131">![Beständiger Chat Server Pool LBW-Konfigurationsprüfung](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Beständiger Chat Server Pool LBW-Konfigurationsprüfung")</span><span class="sxs-lookup"><span data-stu-id="b7900-131">![Persistent Chat Server pool LBW configuration exam](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Persistent Chat Server pool LBW configuration exam")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

