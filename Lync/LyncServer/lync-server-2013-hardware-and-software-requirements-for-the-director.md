---
title: 'Lync Server 2013: Hardware- und Softwareanforderungen für den Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3b1b2a3f642c01d3a4743281554834e9ddda55f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a><span data-ttu-id="58a39-102">Hardware- und Softwareanforderungen für den Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58a39-102">Hardware and software requirements for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58a39-103">_**Letztes Änderungsdatum des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="58a39-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="58a39-104">In diesem Abschnitt werden die Hardware-und Softwareanforderungen für den Director sowie die unterstützten Zusammensetzungs Szenarien für den Director erläutert.</span><span class="sxs-lookup"><span data-stu-id="58a39-104">This section details the hardware and software requirements for the Director, and the supported collocation scenarios for the Director.</span></span>

<div>

## <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="58a39-105">Hardware Anforderungen für den Director</span><span class="sxs-lookup"><span data-stu-id="58a39-105">Hardware Requirements for the Director</span></span>

<span data-ttu-id="58a39-106">In der folgenden Tabelle sind die Hardwareanforderungen für den Director aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="58a39-106">The following table lists the hardware requirements for the Director:</span></span>

### <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="58a39-107">Hardware Anforderungen für den Director</span><span class="sxs-lookup"><span data-stu-id="58a39-107">Hardware Requirements for the Director</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58a39-108">Hardwarekomponente</span><span class="sxs-lookup"><span data-stu-id="58a39-108">Hardware component</span></span></th>
<th><span data-ttu-id="58a39-109">Mindestanforderung</span><span class="sxs-lookup"><span data-stu-id="58a39-109">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58a39-110">CPU</span><span class="sxs-lookup"><span data-stu-id="58a39-110">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="58a39-111">64-Bit-Prozessor, Quad-Core, 2,0 GHz oder höher</span><span class="sxs-lookup"><span data-stu-id="58a39-111">64-bit processor, quad-core, 2.0 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="58a39-112">64-Bit-Dualprozessor, Dual-Core, 2,0 GHz oder höher</span><span class="sxs-lookup"><span data-stu-id="58a39-112">64-bit dual processor, dual-core, 2.0 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58a39-113">Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="58a39-113">Memory</span></span></p></td>
<td><p><span data-ttu-id="58a39-114">4 Gigabyte (GB)</span><span class="sxs-lookup"><span data-stu-id="58a39-114">4 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58a39-115">Festplatte</span><span class="sxs-lookup"><span data-stu-id="58a39-115">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="58a39-116">10K RPM-Festplattenlaufwerk (HDD)</span><span class="sxs-lookup"><span data-stu-id="58a39-116">10K RPM hard disk drive (HDD)</span></span></p></li>
<li><p><span data-ttu-id="58a39-117">Hochleistungs-Solid-State-Laufwerk (SSD) mit gleicher oder besserer Leistung als 10.000-RPM-HDD</span><span class="sxs-lookup"><span data-stu-id="58a39-117">High-performance solid state drive (SSD) with performance equal to or better than 10K RPM HDD</span></span></p></li>
<li><p><span data-ttu-id="58a39-118">2X RAID 10 (gestreifte und gespiegelte) 15K-RPM-Datenträger für Datenbankdateien</span><span class="sxs-lookup"><span data-stu-id="58a39-118">2x RAID 10 (striped and mirrored) 15K RPM disks for database data files</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58a39-119">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="58a39-119">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="58a39-120">Dual 1 Gigabit pro Sekunde (Gbit/s)-Netzwerkadapter (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="58a39-120">Dual 1 gigabit per second (Gbps) network adapters (recommended)</span></span></p></li>
<li><p><span data-ttu-id="58a39-121">Einzelner 1 Gbit/s-Netzwerkadapter (unterstützt)</span><span class="sxs-lookup"><span data-stu-id="58a39-121">Single 1 Gbps network adapter (supported)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a><span data-ttu-id="58a39-122">Software Anforderungen für den Director</span><span class="sxs-lookup"><span data-stu-id="58a39-122">Software Requirements for the Director</span></span>

<span data-ttu-id="58a39-123">Die Director-Rolle kann nur auf Servern bereitgestellt werden, auf denen lync Server 2013 Enterprise Edition ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="58a39-123">The Director role can be deployed only on servers running Lync Server 2013 Enterprise Edition.</span></span>

<span data-ttu-id="58a39-124">Für die Directors ist eines der folgenden 64-Bit-Betriebssysteme erforderlich:</span><span class="sxs-lookup"><span data-stu-id="58a39-124">One of the following 64-bit operating systems is required for the Directors:</span></span>

  - <span data-ttu-id="58a39-125">Das Betriebssystem Windows Server 2008 R2 mit Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="58a39-125">The Windows Server 2008 R2 Standard operating system with Service Pack 1</span></span>

  - <span data-ttu-id="58a39-126">Das Windows Server 2008 R2 Enterprise-Betriebssystem mit Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="58a39-126">The Windows Server 2008 R2 Enterprise operating system with Service Pack 1</span></span>

  - <span data-ttu-id="58a39-127">Das Windows Server 2008 R2 Datacenter-Betriebssystem mit Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="58a39-127">The Windows Server 2008 R2 Datacenter operating system with Service Pack 1</span></span>

  - <span data-ttu-id="58a39-128">Das Betriebssystem Windows Server 2012 Standard</span><span class="sxs-lookup"><span data-stu-id="58a39-128">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="58a39-129">Das Betriebssystem Windows Server 2012 Datacenter</span><span class="sxs-lookup"><span data-stu-id="58a39-129">The Windows Server 2012 Datacenter operating system</span></span>

<span data-ttu-id="58a39-130">Lync Server 2013 erfordert auch die Installation der folgenden Programme und Updates, die im Thema [zusätzliche Server Unterstützung und-Anforderungen in lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md)ausführlich beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="58a39-130">Lync Server 2013 also requires installation of the following programs and updates detailed in the topic [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="58a39-131">Unterstützte Anordnung</span><span class="sxs-lookup"><span data-stu-id="58a39-131">Supported Collocation</span></span>

<span data-ttu-id="58a39-132">Die Director-Serverrolle kann nicht mit einer anderen Serverrolle in lync Server 2013 kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="58a39-132">The Director server role cannot be collocated with any other server role in Lync Server 2013.</span></span> <span data-ttu-id="58a39-133">Wenn Sie jedoch keinen Director bereitstellen, übernimmt der Front-End-Server die Rolle.</span><span class="sxs-lookup"><span data-stu-id="58a39-133">However, if you do not deploy a Director, the Front End Servers will assume the role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

