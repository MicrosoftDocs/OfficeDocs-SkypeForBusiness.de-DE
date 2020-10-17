---
title: 'Lync Server 2013: erforderliche Ressourcen für den Server für beständigen Chat'
description: 'Lync Server 2013: erforderliche Ressourcen für den Server für beständigen Chat.'
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
ms.openlocfilehash: 18c81f0017428e4305e46fbcf5580a83af38accf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542551"
---
# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="1ca55-103">Erforderliche Ressourcen für den Server für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ca55-103">Required resources for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ca55-104">_**Letztes Änderungsstand des Themas:** 2016-02-05_</span><span class="sxs-lookup"><span data-stu-id="1ca55-104">_**Topic Last Modified:** 2016-02-05_</span></span>

<span data-ttu-id="1ca55-105">Hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat erfordern zusätzliche Ressourcen, die in der Regel für den vollständigen Betrieb erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="1ca55-105">High availability and disaster recovery for Persistent Chat Server requires additional resources beyond what is typically needed for full operation.</span></span> <span data-ttu-id="1ca55-106">Stellen Sie vor dem Konfigurieren des Servers für beständigen Chat für hohe Verfügbarkeit und Notfallwiederherstellung sicher, dass Sie über die folgenden Ressourcen verfügen, zusätzlich zu den Anforderungen für den Servervorgang für den standardmäßigen beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="1ca55-106">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following resources in addition to what is required for standard Persistent Chat Server operation.</span></span> <span data-ttu-id="1ca55-107">Weitere Konfigurationsinformationen finden Sie unter [Configuring persistent Chat Server in lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="1ca55-107">For additional configuration information, see [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span></span>

  - <span data-ttu-id="1ca55-108">Eine dedizierte Datenbankinstanz, die sich im selben physischen Rechenzentrum befindet, in dem sich das Hauptfront-End des Server Diensts für beständigen Chat befindet.</span><span class="sxs-lookup"><span data-stu-id="1ca55-108">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="1ca55-109">Diese Datenbank wird als SQL Server Spiegel für die primäre Datenbank für beständigen Chat fungieren.</span><span class="sxs-lookup"><span data-stu-id="1ca55-109">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="1ca55-110">Legen Sie optional eine zusätzliche SQL Server fest, die als Spiegelungs Zeuge fungieren soll, wenn Sie ein automatisches Failover für die Spiegeldatenbank wünschen.</span><span class="sxs-lookup"><span data-stu-id="1ca55-110">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>

  - <span data-ttu-id="1ca55-111">Eine dedizierte Datenbankinstanz im anderen physischen Rechenzentrum.</span><span class="sxs-lookup"><span data-stu-id="1ca55-111">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="1ca55-112">Diese Datenbank dient als SQL Server Protokollversand sekundäre Datenbank für die Datenbank im primären Rechenzentrum.</span><span class="sxs-lookup"><span data-stu-id="1ca55-112">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>

  - <span data-ttu-id="1ca55-113">Eine dedizierte Datenbankinstanz, die als SQL Server Spiegel für die sekundäre Datenbank dient.</span><span class="sxs-lookup"><span data-stu-id="1ca55-113">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="1ca55-114">Optional können Sie einen zusätzlichen SQL Server als Spiegelungs Zeugen für Server festlegen.</span><span class="sxs-lookup"><span data-stu-id="1ca55-114">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="1ca55-115">Beide Instanzen müssen sich im selben physischen Rechenzentrum wie die sekundäre Datenbank befinden.</span><span class="sxs-lookup"><span data-stu-id="1ca55-115">Both of these must be located in the same physical data center as the secondary database.</span></span>

  - <span data-ttu-id="1ca55-116">Wenn die Kompatibilität für den beständigen Chat Server aktiviert ist, sind weitere drei dedizierte Datenbankinstanzen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1ca55-116">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="1ca55-117">Die Verteilung entspricht denen, die zuvor für die Datenbank für beständigen Chat beschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="1ca55-117">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="1ca55-118">Es ist zwar möglich, dass die Kompatibilitätsdatenbank dieselbe SQL Server Instanz wie die Datenbank für beständigen Chat hat, es wird jedoch empfohlen, eigenständige Instanzen für hohe Verfügbarkeit und Notfallwiederherstellung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1ca55-118">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, we recommend standalone instances for high availability and disaster recovery.</span></span>

  - <span data-ttu-id="1ca55-119">Eine Dateifreigabe muss für die SQL Server Protokollversand-Transaktionsprotokolle erstellt und festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="1ca55-119">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="1ca55-120">Alle SQL-Server in beiden Rechenzentren, auf denen persistente Chat Datenbanken ausgeführt werden, müssen über Lese-/Schreibzugriff auf diese Dateifreigabe verfügen.</span><span class="sxs-lookup"><span data-stu-id="1ca55-120">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="1ca55-121">Diese Freigabe ist nicht als Teil einer Filestore-Rolle definiert.</span><span class="sxs-lookup"><span data-stu-id="1ca55-121">This share is not defined as part of a FileStore role.</span></span>

  - <span data-ttu-id="1ca55-122">Eine Dateifreigabe auf dem sekundären Datenbankserver, die als Zielordner für die SQL Server Transaktionsprotokolle dient, die von der Dateifreigabe des primären Servers kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="1ca55-122">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ca55-123">Aktive persistent Chat-Server in einem Serverpool für beständigen Chat müssen sich in derselben Zeitzone befinden wie der lync-Pool für den nächsten Hop, der in der Topologie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="1ca55-123">Active Persistent Chat servers in a Persistent Chat Server pool MUST reside in the same time zone as the next hop Lync Pool defined in the topology.</span></span>



</div>

<span data-ttu-id="1ca55-124">Die folgenden Abbildungen bieten Beispiele dafür, wie der gesamte Server Pool für beständigen Chat in den beiden unterschiedlichen Topologien mit gestreckten Pools konfiguriert werden kann:</span><span class="sxs-lookup"><span data-stu-id="1ca55-124">The following figures provide examples about how the entire Persistent Chat Server pool can be configured in the two different stretched pool topologies:</span></span>

  - <span data-ttu-id="1ca55-125">Erweiterter Pool mit Servern für beständigten Chat, bei dem die Geolocation der Rechenzentren eine hohe Bandbreite bzw. eine geringe Wartezeit aufweist.</span><span class="sxs-lookup"><span data-stu-id="1ca55-125">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>

  - <span data-ttu-id="1ca55-126">Erweiterter Pool mit Servern für beständigen Chat, bei dem die Geolocation der Rechenzentren eine geringe Bandbreite bzw. eine lange Wartezeit aufweist.</span><span class="sxs-lookup"><span data-stu-id="1ca55-126">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="1ca55-127">In der folgenden Abbildung ist eine gestreckte Server Pooltopologie mit beständigem Chat dargestellt, in der sich Rechenzentren mit hoher Bandbreite und niedriger Latenz geografischer Standorte befinden.</span><span class="sxs-lookup"><span data-stu-id="1ca55-127">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span>

<span data-ttu-id="1ca55-128">**Erweiterter Pool mit Servern für beständigten Chat, bei dem die Geolocation der Rechenzentren eine hohe Bandbreite bzw. eine geringe Wartezeit aufweist.**</span><span class="sxs-lookup"><span data-stu-id="1ca55-128">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.**</span></span>

<span data-ttu-id="1ca55-129">![Server Pool für beständigen Chat HBW-Konfigurationsprüfung](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Server Pool für beständigen Chat HBW-Konfigurationsprüfung")</span><span class="sxs-lookup"><span data-stu-id="1ca55-129">![Persistent Chat Server pool HBW configuration exam](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Persistent Chat Server pool HBW configuration exam")</span></span>

<span data-ttu-id="1ca55-130">In der folgenden Abbildung ist eine gestreckte Server Pooltopologie mit beständigem Chat dargestellt, in der sich Rechenzentren mit geringer Bandbreite und hoher Latenz befinden.</span><span class="sxs-lookup"><span data-stu-id="1ca55-130">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="1ca55-131">**Erweiterter Pool mit Servern für beständigen Chat, bei dem die Geolocation der Rechenzentren eine geringe Bandbreite bzw. eine lange Wartezeit aufweist.**</span><span class="sxs-lookup"><span data-stu-id="1ca55-131">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.**</span></span>

<span data-ttu-id="1ca55-132">![Server Pool für beständigen Chat LBW-Konfigurationsprüfung](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Server Pool für beständigen Chat LBW-Konfigurationsprüfung")</span><span class="sxs-lookup"><span data-stu-id="1ca55-132">![Persistent Chat Server pool LBW configuration exam](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Persistent Chat Server pool LBW configuration exam")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

