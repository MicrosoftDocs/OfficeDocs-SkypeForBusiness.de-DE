---
title: Lync Server 2013 Server-Hardwareplattformen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server hardware platforms
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48185395
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ddcfc08ff983ec080bd2382394bfc4b8c3bae3a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-hardware-platforms-for-lync-server-2013"></a><span data-ttu-id="08c4d-102">Server Hardwareplattformen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08c4d-102">Server hardware platforms for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08c4d-103">_**Letztes Änderungsstand des Themas:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="08c4d-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="08c4d-104">Lync Server 2013 Server Rollen und Computer, auf denen lync Server Verwaltungstools betrieben werden, benötigen 64-Bit-Hardware.</span><span class="sxs-lookup"><span data-stu-id="08c4d-104">Lync Server 2013 server roles and computers running Lync Server administrative tools require 64-bit hardware.</span></span>

<span data-ttu-id="08c4d-105">Die für lync Server 2013 Bereitstellung verwendete spezifische Hardware kann je nach Größe und Verwendungsanforderungen variieren.</span><span class="sxs-lookup"><span data-stu-id="08c4d-105">The specific hardware used for Lync Server 2013 deployment can vary, depending on size and usage requirements.</span></span> <span data-ttu-id="08c4d-106">In diesem Abschnitt wird die empfohlene Hardware beschrieben.</span><span class="sxs-lookup"><span data-stu-id="08c4d-106">This section describes the recommended hardware.</span></span> <span data-ttu-id="08c4d-107">Obwohl es sich hierbei um Empfehlungen handelt, nicht um Anforderungen, kann die Verwendung von Hardware, die diese Empfehlungen nicht erfüllt, zu erheblichen Leistungsproblemen und anderen Problemen führen.</span><span class="sxs-lookup"><span data-stu-id="08c4d-107">Although these are recommendations, not requirements, using hardware that does not meet these recommendations may result in significant performance issues and other issues.</span></span>

<div>

## <a name="recommended-hardware-platform"></a><span data-ttu-id="08c4d-108">Empfohlene Hardware Plattform</span><span class="sxs-lookup"><span data-stu-id="08c4d-108">Recommended Hardware Platform</span></span>

<span data-ttu-id="08c4d-109">Um eine optimale Leistung zu erzielen, sollten Sie lync Server auf Servern mit Hardware ausführen, die die Anforderungen in der folgenden Tabelle erfüllen.</span><span class="sxs-lookup"><span data-stu-id="08c4d-109">For best performance, we recommend that you run Lync Server on servers with hardware that meets the requirements in the following table.</span></span> <span data-ttu-id="08c4d-110">Wenn Sie weniger leistungsfähige Hardware verwenden, können Funktionsprobleme oder eine schlechte Leistung auftreten.</span><span class="sxs-lookup"><span data-stu-id="08c4d-110">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="08c4d-111">Beachten Sie, dass diese Hardwareanforderungen höher sind als bei früheren Versionen von lync Server, vor allem, weil in lync Server 2013 alle Front-End-Server SQL Server ausführen.</span><span class="sxs-lookup"><span data-stu-id="08c4d-111">Note that these hardware requirements are higher than those of previous versions of Lync Server, primarily because in Lync Server 2013, all Front End Servers run SQL Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="08c4d-112">NIC-Teaming wird unterstützt und sollte für lync Server transparent sein.</span><span class="sxs-lookup"><span data-stu-id="08c4d-112">NIC teaming is supported and should be transparent to Lync Server.</span></span> <span data-ttu-id="08c4d-113">Ausführliche Informationen finden Sie unter <A href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server oder lync Server und Netzwerkadapter-Teaming</A>.</span><span class="sxs-lookup"><span data-stu-id="08c4d-113">For details, see <A href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and network adapter teaming</A>.</span></span>



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a><span data-ttu-id="08c4d-114">Empfohlene Hardware für Front-End-Server, Back-End-Server, Standard Edition-Server, persistent Chat-Server und persistent Chat Store und Compliance Store für beständigen Chat (Back-End-Serverrollen für den Server für beständigen Chat)</span><span class="sxs-lookup"><span data-stu-id="08c4d-114">Recommended Hardware for Front End Servers, Back End Servers, Standard Edition Servers, Persistent Chat Servers, and Persistent Chat Store and Persistent Chat Compliance Store (Back End Server Roles for Persistent Chat Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08c4d-115">Hardwarekomponente</span><span class="sxs-lookup"><span data-stu-id="08c4d-115">Hardware component</span></span></th>
<th><span data-ttu-id="08c4d-116">Empfohlen</span><span class="sxs-lookup"><span data-stu-id="08c4d-116">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08c4d-117">CPU</span><span class="sxs-lookup"><span data-stu-id="08c4d-117">CPU</span></span></p></td>
<td><p><span data-ttu-id="08c4d-118">64-Bit Dualprozessor, Hex-Core, 2,26 Gigahertz (GHz) oder höher.</span><span class="sxs-lookup"><span data-stu-id="08c4d-118">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="08c4d-119">Intel Itanium-Prozessoren werden für lync Server-Server Rollen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="08c4d-119">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08c4d-120">Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="08c4d-120">Memory</span></span></p></td>
<td><p><span data-ttu-id="08c4d-121">32 Gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="08c4d-121">32 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08c4d-122">Datenträger</span><span class="sxs-lookup"><span data-stu-id="08c4d-122">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="08c4d-123">8 oder mehr 10.000 RPM-Festplatten mit mindestens 72 GB freiem Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="08c4d-123">8 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="08c4d-124">Zwei der Datenträger sollten RAID 1 verwenden, und sechs sollten RAID 10 verwenden.</span><span class="sxs-lookup"><span data-stu-id="08c4d-124">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="08c4d-125">-Oder</span><span class="sxs-lookup"><span data-stu-id="08c4d-125">- OR -</span></span></p></li>
<li><p><span data-ttu-id="08c4d-126">Solid State Drives (SSDs), die ähnliche Leistung wie mechanische Festplattenlaufwerke mit 8 10.000-rpm bieten.</span><span class="sxs-lookup"><span data-stu-id="08c4d-126">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08c4d-127">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="08c4d-127">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="08c4d-128">1 Dual-Port-Netzwerkadapter, 1 Gbit/s oder höher (2 wird empfohlen, für die ein Teaming mit einer einzelnen Mac-Adresse und einer einzelnen IP-Adresse erforderlich ist).</span><span class="sxs-lookup"><span data-stu-id="08c4d-128">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="08c4d-129">Duale oder Multi-Homed-Konfigurationen werden für Front-End-Server, Back-End-Server, Standard Edition-Server und Server für beständigen Chat nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="08c4d-129">Dual or multi-homed configurations are not supported for Front End Servers, Back End Servers, Standard Edition servers, and Persistent Chat Servers.</span></span><BR><span data-ttu-id="08c4d-130">ILO/DRAC/etc. Verbindungen, die nicht dem Betriebs System ausgesetzt sind und zum Überwachen und Verwalten der Server Hardware verwendet werden, stellen keinen Multi-Homed-Server dar und werden daher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="08c4d-130">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a><span data-ttu-id="08c4d-131">Empfohlene Hardware für Edgeserver, eigenständige Vermittlungsserver und Directors</span><span class="sxs-lookup"><span data-stu-id="08c4d-131">Recommended Hardware for Edge Servers, Standalone Mediation Servers, and Directors</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08c4d-132">Hardwarekomponente</span><span class="sxs-lookup"><span data-stu-id="08c4d-132">Hardware component</span></span></th>
<th><span data-ttu-id="08c4d-133">Empfohlen</span><span class="sxs-lookup"><span data-stu-id="08c4d-133">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08c4d-134">CPU</span><span class="sxs-lookup"><span data-stu-id="08c4d-134">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="08c4d-135">Dualprozessor mit 64 Bit, Quad-Core, 2,0 Gigahertz (GHz) oder höher.</span><span class="sxs-lookup"><span data-stu-id="08c4d-135">64-bit dual processor, quad-core, 2.0 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="08c4d-136">-Oder</span><span class="sxs-lookup"><span data-stu-id="08c4d-136">- OR -</span></span></p></li>
<li><p><span data-ttu-id="08c4d-137">64-Bit-4-Wege-Prozessor, Dual-Core, 2,0 GHz oder höher.</span><span class="sxs-lookup"><span data-stu-id="08c4d-137">64-bit 4-way processor, dual-core, 2.0 GHz or higher.</span></span></p></li>
</ul>
<p><span data-ttu-id="08c4d-138">Intel Itanium-Prozessoren werden für lync Server-Server Rollen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="08c4d-138">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08c4d-139">Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="08c4d-139">Memory</span></span></p></td>
<td><p><span data-ttu-id="08c4d-140">16 Gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="08c4d-140">16 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08c4d-141">Datenträger</span><span class="sxs-lookup"><span data-stu-id="08c4d-141">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="08c4d-142">4 oder mehr 10.000 RPM-Festplatten mit mindestens 72 GB freiem Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="08c4d-142">4 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="08c4d-143">Die Datenträger sollten sich in einer 2X-RAID-1-Konfiguration befinden.</span><span class="sxs-lookup"><span data-stu-id="08c4d-143">The disks should be in a 2x RAID 1 configuration.</span></span></p>
<p><span data-ttu-id="08c4d-144">-Oder</span><span class="sxs-lookup"><span data-stu-id="08c4d-144">- OR -</span></span></p></li>
<li><p><span data-ttu-id="08c4d-145">Solid State Drives (SSDs), die ähnliche Leistung wie mechanische Festplattenlaufwerke mit 4 10.000-rpm bieten.</span><span class="sxs-lookup"><span data-stu-id="08c4d-145">Solid state drives (SSDs) which provide performance similar to 4 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08c4d-146">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="08c4d-146">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="08c4d-147">1 Dual-Port-Netzwerkadapter, 1 Gbit/s oder höher (2 wird empfohlen, für die ein Teaming mit einer einzelnen Mac-Adresse und einer einzelnen IP-Adresse erforderlich ist).</span><span class="sxs-lookup"><span data-stu-id="08c4d-147">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span> <span data-ttu-id="08c4d-148">2 Netzwerkschnittstellen sind auf Edge-Servern erforderlich und werden auf eigenständigen Vermittlungsservern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="08c4d-148">2 network interfaces are required on Edge Servers, and are supported on standalone Mediation Servers.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="08c4d-149">Duale oder Multi-Homed-Konfigurationen werden für Directors nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="08c4d-149">Dual or multi-homed configurations are not supported for Directors.</span></span><BR><span data-ttu-id="08c4d-150">ILO/DRAC/etc. Verbindungen, die nicht dem Betriebs System ausgesetzt sind und zum Überwachen und Verwalten der Server Hardware verwendet werden, stellen keinen Multi-Homed-Server dar und werden daher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="08c4d-150">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div>
<p><span data-ttu-id="08c4d-151">Edgeserver benötigen zwei Netzwerkschnittstellen mit zwei Netzwerkadaptern, 1 Gbit/s oder höher (oder zwei gekoppelte Netzwerkadapter für insgesamt vier, wobei jedes Paar mit einer einzelnen Mac-Adresse und einer einzelnen IP-Adresse zusammenarbeitet, wobei insgesamt zwei Paare verwendet werden).</span><span class="sxs-lookup"><span data-stu-id="08c4d-151">Edge Servers will require two network interfaces that are dual-port network adapters, 1 Gbps or higher (or two paired network adapters, for a total of four, each pair being teamed with a single MAC address and a single IP address, for a total of two pairs).</span></span></p>
<p><span data-ttu-id="08c4d-152">Die Installation zusätzlicher Netzwerkschnittstellenkarten (NICs), um die Konfiguration einer bestimmten PSTN-IP-Adresse zuzulassen, wird auf eigenständigen Vermittlungsservern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="08c4d-152">Installation of additional network interface cards (NICs) to allow the configuration of a specific PSTN IP address is supported on standalone Mediation Servers.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

