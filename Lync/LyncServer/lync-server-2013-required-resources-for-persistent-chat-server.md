---
title: 'Lync Server 2013: erforderliche Ressourcen für den Server für beständigen Chat'
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
ms.openlocfilehash: 3c925a695fd856c4e9c2d272d39f18a7c3d1f78c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="b855f-102">Erforderliche Ressourcen für den Server für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b855f-102">Required resources for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b855f-103">_**Letztes Änderungsstand des Themas:** 2016-02-05_</span><span class="sxs-lookup"><span data-stu-id="b855f-103">_**Topic Last Modified:** 2016-02-05_</span></span>

<span data-ttu-id="b855f-104">Hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat erfordern zusätzliche Ressourcen, die in der Regel für den vollständigen Betrieb erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b855f-104">High availability and disaster recovery for Persistent Chat Server requires additional resources beyond what is typically needed for full operation.</span></span> <span data-ttu-id="b855f-105">Stellen Sie vor dem Konfigurieren des Servers für beständigen Chat für hohe Verfügbarkeit und Notfallwiederherstellung sicher, dass Sie über die folgenden Ressourcen verfügen, zusätzlich zu den Anforderungen für den Servervorgang für den standardmäßigen beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="b855f-105">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following resources in addition to what is required for standard Persistent Chat Server operation.</span></span> <span data-ttu-id="b855f-106">Weitere Konfigurationsinformationen finden Sie unter [Configuring persistent Chat Server in lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="b855f-106">For additional configuration information, see [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span></span>

  - <span data-ttu-id="b855f-107">Eine dedizierte Datenbankinstanz, die sich im selben physischen Rechenzentrum befindet, in dem sich das Hauptfront-End des Server Diensts für beständigen Chat befindet.</span><span class="sxs-lookup"><span data-stu-id="b855f-107">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="b855f-108">Diese Datenbank wird als SQL Server Spiegel für die primäre Datenbank für beständigen Chat fungieren.</span><span class="sxs-lookup"><span data-stu-id="b855f-108">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="b855f-109">Legen Sie optional eine zusätzliche SQL Server fest, die als Spiegelungs Zeuge fungieren soll, wenn Sie ein automatisches Failover für die Spiegeldatenbank wünschen.</span><span class="sxs-lookup"><span data-stu-id="b855f-109">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>

  - <span data-ttu-id="b855f-110">Eine dedizierte Datenbankinstanz im anderen physischen Rechenzentrum.</span><span class="sxs-lookup"><span data-stu-id="b855f-110">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="b855f-111">Diese Datenbank dient als SQL Server Protokollversand sekundäre Datenbank für die Datenbank im primären Rechenzentrum.</span><span class="sxs-lookup"><span data-stu-id="b855f-111">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>

  - <span data-ttu-id="b855f-112">Eine dedizierte Datenbankinstanz, die als SQL Server Spiegel für die sekundäre Datenbank dient.</span><span class="sxs-lookup"><span data-stu-id="b855f-112">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="b855f-113">Optional können Sie einen zusätzlichen SQL Server als Spiegelungs Zeugen für Server festlegen.</span><span class="sxs-lookup"><span data-stu-id="b855f-113">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="b855f-114">Beide Instanzen müssen sich im selben physischen Rechenzentrum wie die sekundäre Datenbank befinden.</span><span class="sxs-lookup"><span data-stu-id="b855f-114">Both of these must be located in the same physical data center as the secondary database.</span></span>

  - <span data-ttu-id="b855f-115">Wenn die Kompatibilität für den beständigen Chat Server aktiviert ist, sind weitere drei dedizierte Datenbankinstanzen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b855f-115">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="b855f-116">Die Verteilung entspricht denen, die zuvor für die Datenbank für beständigen Chat beschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="b855f-116">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="b855f-117">Es ist zwar möglich, dass die Kompatibilitätsdatenbank dieselbe SQL Server Instanz wie die Datenbank für beständigen Chat hat, es wird jedoch empfohlen, eigenständige Instanzen für hohe Verfügbarkeit und Notfallwiederherstellung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b855f-117">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, we recommend standalone instances for high availability and disaster recovery.</span></span>

  - <span data-ttu-id="b855f-118">Eine Dateifreigabe muss für die SQL Server Protokollversand-Transaktionsprotokolle erstellt und festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b855f-118">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="b855f-119">Alle SQL-Server in beiden Rechenzentren, auf denen persistente Chat Datenbanken ausgeführt werden, müssen über Lese-/Schreibzugriff auf diese Dateifreigabe verfügen.</span><span class="sxs-lookup"><span data-stu-id="b855f-119">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="b855f-120">Diese Freigabe ist nicht als Teil einer Filestore-Rolle definiert.</span><span class="sxs-lookup"><span data-stu-id="b855f-120">This share is not defined as part of a FileStore role.</span></span>

  - <span data-ttu-id="b855f-121">Eine Dateifreigabe auf dem sekundären Datenbankserver, die als Zielordner für die SQL Server Transaktionsprotokolle dient, die von der Dateifreigabe des primären Servers kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="b855f-121">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b855f-122">Aktive persistent Chat-Server in einem Serverpool für beständigen Chat müssen sich in derselben Zeitzone befinden wie der lync-Pool für den nächsten Hop, der in der Topologie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b855f-122">Active Persistent Chat servers in a Persistent Chat Server pool MUST reside in the same time zone as the next hop Lync Pool defined in the topology.</span></span>



</div>

<span data-ttu-id="b855f-123">Die folgenden Abbildungen bieten Beispiele dafür, wie der gesamte Server Pool für beständigen Chat in den beiden unterschiedlichen Topologien mit gestreckten Pools konfiguriert werden kann:</span><span class="sxs-lookup"><span data-stu-id="b855f-123">The following figures provide examples about how the entire Persistent Chat Server pool can be configured in the two different stretched pool topologies:</span></span>

  - <span data-ttu-id="b855f-124">Erweiterter Pool mit Servern für beständigten Chat, bei dem die Geolocation der Rechenzentren eine hohe Bandbreite bzw. eine geringe Wartezeit aufweist.</span><span class="sxs-lookup"><span data-stu-id="b855f-124">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>

  - <span data-ttu-id="b855f-125">Erweiterter Pool mit Servern für beständigen Chat, bei dem die Geolocation der Rechenzentren eine geringe Bandbreite bzw. eine lange Wartezeit aufweist.</span><span class="sxs-lookup"><span data-stu-id="b855f-125">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="b855f-126">In der folgenden Abbildung ist eine gestreckte Server Pooltopologie mit beständigem Chat dargestellt, in der sich Rechenzentren mit hoher Bandbreite und niedriger Latenz geografischer Standorte befinden.</span><span class="sxs-lookup"><span data-stu-id="b855f-126">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span>

<span data-ttu-id="b855f-127">**Erweiterter Pool mit Servern für beständigten Chat, bei dem die Geolocation der Rechenzentren eine hohe Bandbreite bzw. eine geringe Wartezeit aufweist.**</span><span class="sxs-lookup"><span data-stu-id="b855f-127">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.**</span></span>

<span data-ttu-id="b855f-128">![Server Pool für beständigen Chat HBW-Konfigurationsprüfung](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Server Pool für beständigen Chat HBW-Konfigurationsprüfung")</span><span class="sxs-lookup"><span data-stu-id="b855f-128">![Persistent Chat Server pool HBW configuration exam](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Persistent Chat Server pool HBW configuration exam")</span></span>

<span data-ttu-id="b855f-129">In der folgenden Abbildung ist eine gestreckte Server Pooltopologie mit beständigem Chat dargestellt, in der sich Rechenzentren mit geringer Bandbreite und hoher Latenz befinden.</span><span class="sxs-lookup"><span data-stu-id="b855f-129">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="b855f-130">**Erweiterter Pool mit Servern für beständigen Chat, bei dem die Geolocation der Rechenzentren eine geringe Bandbreite bzw. eine lange Wartezeit aufweist.**</span><span class="sxs-lookup"><span data-stu-id="b855f-130">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.**</span></span>

<span data-ttu-id="b855f-131">![Server Pool für beständigen Chat LBW-Konfigurationsprüfung](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Server Pool für beständigen Chat LBW-Konfigurationsprüfung")</span><span class="sxs-lookup"><span data-stu-id="b855f-131">![Persistent Chat Server pool LBW configuration exam](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Persistent Chat Server pool LBW configuration exam")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

