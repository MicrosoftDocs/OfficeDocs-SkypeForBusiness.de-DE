---
title: 'Lync Server 2013: Betriebssystemunterstützung für Server und Tools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server and tools operating system support
ms:assetid: b65a0956-f90d-48d0-ac61-558e67339084
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412883(v=OCS.15)
ms:contentKeyID: 48185214
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 757091b8f3c8155134fa1cc3e984e28093d49843
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-and-tools-operating-system-support-in-lync-server-2013"></a><span data-ttu-id="b85af-102">Betriebssystemunterstützung für Server und Tools in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b85af-102">Server and tools operating system support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b85af-103">_**Letztes Änderungsstand des Themas:** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="b85af-103">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="b85af-104">Lync Server 2013 ist nur in 64-Bit verfügbar, was 64-Bit-Hardware und 64-Bit-Editionen von Windows Server erfordert.</span><span class="sxs-lookup"><span data-stu-id="b85af-104">Lync Server 2013 is available only in 64-bit, which requires 64-bit hardware and 64-bit editions of Windows Server.</span></span> <span data-ttu-id="b85af-105">Dies bedeutet, dass alle Serverrollen und Computer, auf denen lync Server 2013 Verwaltungstools ausgeführt werden, ein 64-Bit-Edition-Betriebssystem ausführen.</span><span class="sxs-lookup"><span data-stu-id="b85af-105">This means that all server roles and computers running Lync Server 2013 administrative tools run a 64-bit edition operating system.</span></span>

<div>

## <a name="operating-systems-for-server-roles"></a><span data-ttu-id="b85af-106">Betriebssysteme für Serverrollen</span><span class="sxs-lookup"><span data-stu-id="b85af-106">Operating Systems for Server Roles</span></span>

<span data-ttu-id="b85af-107">Lync Server 2013 unterstützt die 64-Bit-Editionen der folgenden Betriebssysteme für alle Server Rollen in lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="b85af-107">Lync Server 2013 supports the 64-bit editions of the following operating systems for all server roles in Lync Server 2013:</span></span>

  - <span data-ttu-id="b85af-108">Die Windows Server 2008 R2 mit Service Pack 1 (SP1) Standard Betriebssystem (erforderlich) oder mit dem neuesten Service Pack (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="b85af-108">The Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="b85af-109">Das Windows Server 2008 R2 mit SP1 Enterprise-Betriebssystem (erforderlich) oder mit dem neuesten Service Pack (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="b85af-109">The Windows Server 2008 R2 with SP1 Enterprise operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="b85af-110">Das Windows Server 2008 R2 mit SP1 Datacenter-Betriebssystem (erforderlich) oder mit dem neuesten Service Pack (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="b85af-110">The Windows Server 2008 R2 with SP1 Datacenter operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="b85af-111">Das Windows Server 2012 Standard-Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="b85af-111">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="b85af-112">Das Betriebssystem des Windows Server 2012-Rechenzentrums</span><span class="sxs-lookup"><span data-stu-id="b85af-112">The Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="b85af-113">Die Windows Server 2012 R2-Betriebssysteme werden mit den kumulativen Updates für lync Server 2013: Oktober 2013 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b85af-113">The Windows Server 2012 R2 operating systems are supported with the Cumulative Updates for Lync Server 2013: October 2013.</span></span>

<span data-ttu-id="b85af-114">Lync Server 2013 wird für Folgendes nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="b85af-114">Lync Server 2013 is not supported on the following:</span></span>

  - <span data-ttu-id="b85af-115">Die Server Core-Installationsoption von Windows Server 2008 R2 oder Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="b85af-115">The Server Core installation option of Windows Server 2008 R2 or Windows Server 2012</span></span>

  - <span data-ttu-id="b85af-116">Dem Betriebssystem Windows Web Server 2008 R2 oder Windows Web Server 2012</span><span class="sxs-lookup"><span data-stu-id="b85af-116">The Windows Web Server 2008 R2 operating system or the Windows Web Server 2012 operating system</span></span>

  - <span data-ttu-id="b85af-117">Windows Server 2008 R2 HPC-Edition oder Windows Server 2012 HPC-Edition</span><span class="sxs-lookup"><span data-stu-id="b85af-117">Windows Server 2008 R2 HPC Edition or Windows Server 2012 HPC Edition</span></span>

</div>

<div>

## <a name="additional-operating-systems-for-administrative-tools"></a><span data-ttu-id="b85af-118">Weitere Betriebssysteme für Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="b85af-118">Additional Operating Systems for Administrative Tools</span></span>

<span data-ttu-id="b85af-119">Lync Server 2013 Verwaltungstools werden standardmäßig auf Servern mit lync Server 2013 installiert, aber Sie können Verwaltungstools separat auf anderen Computern installieren, auf denen Windows-Betriebssysteme verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b85af-119">Lync Server 2013 administrative tools are installed by default on servers running Lync Server 2013, but you can install administrative tools separately on other computers running Windows operating systems.</span></span> <span data-ttu-id="b85af-120">Dazu gehören die folgenden 64-Bit-Versionen der folgenden Betriebssysteme, zusätzlich zu den 64-Bit-Editionen der Betriebssysteme, die für die Bereitstellung von Serverrollen unterstützt werden (wie im vorherigen Abschnitt beschrieben).</span><span class="sxs-lookup"><span data-stu-id="b85af-120">These include the following 64-bit versions of the following operating systems, in addition to the 64-bit editions of the operating systems supported for deployment of server roles (as described in the previous section).</span></span>

  - <span data-ttu-id="b85af-121">Das Betriebssystem Windows 7 Betriebssystem mit SP1 (erforderlich) oder neuestes Service Pack (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="b85af-121">The Windows 7 operating system with SP1 operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="b85af-122">Das Windows 8 Betriebssystem oder das neueste Service Pack (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="b85af-122">The Windows 8 operating system or latest service pack (recommended)</span></span>

  - <span data-ttu-id="b85af-123">Das Windows 8.1 Betriebssystem oder das neueste Service Pack (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="b85af-123">The Windows 8.1 operating system or latest service pack (recommended)</span></span>

</div>

<div>

## <a name="operating-systems-for-other-servers-in-your-deployment"></a><span data-ttu-id="b85af-124">Betriebssysteme für andere Server in Ihrer Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="b85af-124">Operating Systems for Other Servers in Your Deployment</span></span>

  - <span data-ttu-id="b85af-125">Ausführliche Informationen zu den Anforderungen für Back-End-Server und andere Datenbankserver finden Sie unter [Database Software Support in lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="b85af-125">For details about requirements for Back End Servers and other database servers, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

  - <span data-ttu-id="b85af-126">Ausführliche Informationen zu den Anforderungen für Reverse-Proxy Server (für die Edge-Bereitstellung) finden Sie unter [IIS-Unterstützung in lync Server 2013](lync-server-2013-iis-support.md).</span><span class="sxs-lookup"><span data-stu-id="b85af-126">For details about requirements for reverse proxy servers (for Edge deployment), see [IIS support in Lync Server 2013](lync-server-2013-iis-support.md).</span></span>

  - <span data-ttu-id="b85af-127">Ausführliche Informationen zu anderen Softwareanforderungen, einschließlich Infrastruktur und Unterstützung der Virtualisierung, finden Sie in den anderen Themen unter [Server Software and Infrastructure Support in lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span><span class="sxs-lookup"><span data-stu-id="b85af-127">For details about other software requirements, including infrastructure and virtualization support, see the other topics in the [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

