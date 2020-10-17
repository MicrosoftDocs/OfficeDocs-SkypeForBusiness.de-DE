---
title: 'Lync Server 2013: Hardware-und Softwareanforderungen für den Director'
description: 'Lync Server 2013: Hardware-und Softwareanforderungen für den Director.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dd868a3a566f1d89b4ada5a16695f8eb02b3b21
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552931"
---
# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a><span data-ttu-id="bc9f9-103">Hardware-und Softwareanforderungen für den Director in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc9f9-103">Hardware and software requirements for the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc9f9-104">_**Letztes Änderungsstand des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="bc9f9-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="bc9f9-105">In diesem Abschnitt werden die Hardware-und Softwareanforderungen für den Director sowie die unterstützten Zusammenstellungs Szenarien für den Director erläutert.</span><span class="sxs-lookup"><span data-stu-id="bc9f9-105">This section details the hardware and software requirements for the Director, and the supported collocation scenarios for the Director.</span></span>

<div>

## <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="bc9f9-106">Hardwareanforderungen für Director-Server</span><span class="sxs-lookup"><span data-stu-id="bc9f9-106">Hardware Requirements for the Director</span></span>

<span data-ttu-id="bc9f9-107">In der folgenden Tabelle sind die Hardwareanforderungen für den Director aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="bc9f9-107">The following table lists the hardware requirements for the Director:</span></span>

### <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="bc9f9-108">Hardwareanforderungen für Director-Server</span><span class="sxs-lookup"><span data-stu-id="bc9f9-108">Hardware Requirements for the Director</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc9f9-109">Hardwarekomponente</span><span class="sxs-lookup"><span data-stu-id="bc9f9-109">Hardware component</span></span></th>
<th><span data-ttu-id="bc9f9-110">Mindestanforderung</span><span class="sxs-lookup"><span data-stu-id="bc9f9-110">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc9f9-111">CPU</span><span class="sxs-lookup"><span data-stu-id="bc9f9-111">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="bc9f9-112">64-Bit-Prozessor, Vierkern, mindestens 2,0 GHz</span><span class="sxs-lookup"><span data-stu-id="bc9f9-112">64-bit processor, quad-core, 2.0 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="bc9f9-113">64-Bit-Dualprozessor, Doppelkern, mindestens 2,0 GHz</span><span class="sxs-lookup"><span data-stu-id="bc9f9-113">64-bit dual processor, dual-core, 2.0 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc9f9-114">Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="bc9f9-114">Memory</span></span></p></td>
<td><p><span data-ttu-id="bc9f9-115">4 GB</span><span class="sxs-lookup"><span data-stu-id="bc9f9-115">4 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc9f9-116">Datenträger</span><span class="sxs-lookup"><span data-stu-id="bc9f9-116">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="bc9f9-117">HDD-Festplattenlaufwerk mit 10.000 U/min</span><span class="sxs-lookup"><span data-stu-id="bc9f9-117">10K RPM hard disk drive (HDD)</span></span></p></li>
<li><p><span data-ttu-id="bc9f9-118">SSD-Hochleistungslaufwerk mit gleicher oder höherer Leistung als eine HDD-Festplatte mit 10.000 U/min</span><span class="sxs-lookup"><span data-stu-id="bc9f9-118">High-performance solid state drive (SSD) with performance equal to or better than 10K RPM HDD</span></span></p></li>
<li><p><span data-ttu-id="bc9f9-119">2 RAID 10-Datenträger (Stripeset und gespiegelt), 15.000 U/min, für Datenbankdatendateien</span><span class="sxs-lookup"><span data-stu-id="bc9f9-119">2x RAID 10 (striped and mirrored) 15K RPM disks for database data files</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc9f9-120">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="bc9f9-120">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="bc9f9-121">Dual-Port-Netzwerkkarten mit 1 GBit/s (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="bc9f9-121">Dual 1 gigabit per second (Gbps) network adapters (recommended)</span></span></p></li>
<li><p><span data-ttu-id="bc9f9-122">Single-Port-Netzwerkkarte mit 1 GBit/s (unterstützt)</span><span class="sxs-lookup"><span data-stu-id="bc9f9-122">Single 1 Gbps network adapter (supported)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a><span data-ttu-id="bc9f9-123">Software Anforderungen für den Director</span><span class="sxs-lookup"><span data-stu-id="bc9f9-123">Software Requirements for the Director</span></span>

<span data-ttu-id="bc9f9-124">Die Director-Rolle kann nur auf Servern bereitgestellt werden, die lync Server 2013 Enterprise Edition ausführt.</span><span class="sxs-lookup"><span data-stu-id="bc9f9-124">The Director role can be deployed only on servers running Lync Server 2013 Enterprise Edition.</span></span>

<span data-ttu-id="bc9f9-125">Eines der folgenden 64-Bit-Betriebssysteme ist für die Directors erforderlich:</span><span class="sxs-lookup"><span data-stu-id="bc9f9-125">One of the following 64-bit operating systems is required for the Directors:</span></span>

  - <span data-ttu-id="bc9f9-126">Das Windows Server 2008 R2 Standard Betriebssystem mit Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="bc9f9-126">The Windows Server 2008 R2 Standard operating system with Service Pack 1</span></span>

  - <span data-ttu-id="bc9f9-127">Das Windows Server 2008 R2 Enterprise-Betriebssystem mit Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="bc9f9-127">The Windows Server 2008 R2 Enterprise operating system with Service Pack 1</span></span>

  - <span data-ttu-id="bc9f9-128">Das Windows Server 2008 R2 Datacenter-Betriebssystem mit Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="bc9f9-128">The Windows Server 2008 R2 Datacenter operating system with Service Pack 1</span></span>

  - <span data-ttu-id="bc9f9-129">Das Windows Server 2012 Standard-Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="bc9f9-129">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="bc9f9-130">Das Betriebssystem des Windows Server 2012-Rechenzentrums</span><span class="sxs-lookup"><span data-stu-id="bc9f9-130">The Windows Server 2012 Datacenter operating system</span></span>

<span data-ttu-id="bc9f9-131">Lync Server 2013 erfordert auch die Installation der folgenden Programme und Updates, die im Thema [zusätzliche Server Unterstützung und-Anforderungen in lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md)erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="bc9f9-131">Lync Server 2013 also requires installation of the following programs and updates detailed in the topic [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="bc9f9-132">Unterstützte Zusammenstellungen</span><span class="sxs-lookup"><span data-stu-id="bc9f9-132">Supported Collocation</span></span>

<span data-ttu-id="bc9f9-133">Die Director-Serverrolle kann nicht mit einer anderen Serverrolle in lync Server 2013 zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="bc9f9-133">The Director server role cannot be collocated with any other server role in Lync Server 2013.</span></span> <span data-ttu-id="bc9f9-134">Wenn Sie jedoch keinen Director bereitstellen, wird die Rolle von den Front-End-Servern übernommen.</span><span class="sxs-lookup"><span data-stu-id="bc9f9-134">However, if you do not deploy a Director, the Front End Servers will assume the role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

