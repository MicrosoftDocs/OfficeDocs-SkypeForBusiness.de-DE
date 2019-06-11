---
title: 'Lync Server 2013: Betriebssystemunterstützung für Server und Tools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server and tools operating system support
ms:assetid: b65a0956-f90d-48d0-ac61-558e67339084
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412883(v=OCS.15)
ms:contentKeyID: 48185214
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a19ae4b69eb261a9d23d767dcd3847d8986847b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-and-tools-operating-system-support-in-lync-server-2013"></a><span data-ttu-id="c9425-102">Betriebssystemunterstützung für Server und Tools in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9425-102">Server and tools operating system support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9425-103">_**Letztes Änderungsdatum des Themas:** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="c9425-103">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="c9425-104">Lync Server 2013 ist nur in 64-Bit verfügbar, was eine 64-Bit-Hardware und 64-Bit-Editionen von Windows Server erfordert.</span><span class="sxs-lookup"><span data-stu-id="c9425-104">Lync Server 2013 is available only in 64-bit, which requires 64-bit hardware and 64-bit editions of Windows Server.</span></span> <span data-ttu-id="c9425-105">Dies bedeutet, dass alle Serverrollen und Computer mit lync Server 2013-Verwaltungstools ein 64-Bit-Edition-Betriebssystem ausführen.</span><span class="sxs-lookup"><span data-stu-id="c9425-105">This means that all server roles and computers running Lync Server 2013 administrative tools run a 64-bit edition operating system.</span></span>

<div>

## <a name="operating-systems-for-server-roles"></a><span data-ttu-id="c9425-106">Betriebssysteme für Server Rollen</span><span class="sxs-lookup"><span data-stu-id="c9425-106">Operating Systems for Server Roles</span></span>

<span data-ttu-id="c9425-107">Lync Server 2013 unterstützt die 64-Bit-Editionen der folgenden Betriebssysteme für alle Server Rollen in lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="c9425-107">Lync Server 2013 supports the 64-bit editions of the following operating systems for all server roles in Lync Server 2013:</span></span>

  - <span data-ttu-id="c9425-108">Windows Server 2008 R2 mit Service Pack 1 (SP1) Standard Betriebssystem (erforderlich) oder neuestes Service Pack (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="c9425-108">The Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="c9425-109">Das Windows Server 2008 R2 mit SP1 Enterprise-Betriebssystem (erforderlich) oder neuestes Service Pack (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="c9425-109">The Windows Server 2008 R2 with SP1 Enterprise operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="c9425-110">Das Windows Server 2008 R2 mit SP1 Datacenter-Betriebssystem (erforderlich) oder neuestes Service Pack (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="c9425-110">The Windows Server 2008 R2 with SP1 Datacenter operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="c9425-111">Das Betriebssystem Windows Server 2012 Standard</span><span class="sxs-lookup"><span data-stu-id="c9425-111">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="c9425-112">Das Betriebssystem Windows Server 2012 Datacenter</span><span class="sxs-lookup"><span data-stu-id="c9425-112">The Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="c9425-113">Die Windows Server 2012 R2-Betriebssysteme werden mit den kumulativen Updates für lync Server 2013: Oktober 2013 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c9425-113">The Windows Server 2012 R2 operating systems are supported with the Cumulative Updates for Lync Server 2013: October 2013.</span></span>

<span data-ttu-id="c9425-114">Lync Server 2013 wird auf der folgenden Grundlage nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="c9425-114">Lync Server 2013 is not supported on the following:</span></span>

  - <span data-ttu-id="c9425-115">Die Server Core-Installationsoption von Windows Server 2008 R2 oder Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="c9425-115">The Server Core installation option of Windows Server 2008 R2 or Windows Server 2012</span></span>

  - <span data-ttu-id="c9425-116">Das BetriebssystemWindows Web Server 2008 R2 oder das BetriebssystemWindows Web Server 2012</span><span class="sxs-lookup"><span data-stu-id="c9425-116">The Windows Web Server 2008 R2 operating system or the Windows Web Server 2012 operating system</span></span>

  - <span data-ttu-id="c9425-117">Windows Server 2008 R2 HPC Edition oder Windows Server 2012 HPC Edition</span><span class="sxs-lookup"><span data-stu-id="c9425-117">Windows Server 2008 R2 HPC Edition or Windows Server 2012 HPC Edition</span></span>

</div>

<div>

## <a name="additional-operating-systems-for-administrative-tools"></a><span data-ttu-id="c9425-118">Zusätzliche Betriebssysteme für Verwaltungs Tools</span><span class="sxs-lookup"><span data-stu-id="c9425-118">Additional Operating Systems for Administrative Tools</span></span>

<span data-ttu-id="c9425-119">Lync Server 2013-Verwaltungstools werden standardmäßig auf Servern mit lync Server 2013 installiert, Sie können jedoch Verwaltungstools separat auf anderen Computern installieren, auf denen Windows-Betriebssysteme ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c9425-119">Lync Server 2013 administrative tools are installed by default on servers running Lync Server 2013, but you can install administrative tools separately on other computers running Windows operating systems.</span></span> <span data-ttu-id="c9425-120">Dazu gehören die folgenden 64-Bit-Versionen der folgenden Betriebssysteme sowie die 64-Bit-Editionen der Betriebssysteme, die für die Bereitstellung von Serverrollen unterstützt werden (wie im vorherigen Abschnitt beschrieben).</span><span class="sxs-lookup"><span data-stu-id="c9425-120">These include the following 64-bit versions of the following operating systems, in addition to the 64-bit editions of the operating systems supported for deployment of server roles (as described in the previous section).</span></span>

  - <span data-ttu-id="c9425-121">Windows 7-Betriebssystem mit SP1-Betriebssystem (erforderlich) oder neuestes Service Pack (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="c9425-121">The Windows 7 operating system with SP1 operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="c9425-122">Das Windows 8-Betriebssystem oder das neueste Service Pack (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="c9425-122">The Windows 8 operating system or latest service pack (recommended)</span></span>

  - <span data-ttu-id="c9425-123">Das Windows 8,1-Betriebssystem oder das neueste Service Pack (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="c9425-123">The Windows 8.1 operating system or latest service pack (recommended)</span></span>

</div>

<div>

## <a name="operating-systems-for-other-servers-in-your-deployment"></a><span data-ttu-id="c9425-124">Betriebssysteme für andere Server in Ihrer Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="c9425-124">Operating Systems for Other Servers in Your Deployment</span></span>

  - <span data-ttu-id="c9425-125">Details zu den Anforderungen für Back-End-Server und andere Datenbankserver finden Sie unter [Unterstützung von Datenbanksoftware in lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="c9425-125">For details about requirements for Back End Servers and other database servers, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

  - <span data-ttu-id="c9425-126">Details zu den Anforderungen für Reverse-Proxy Server (für die Edge-Bereitstellung) finden Sie unter [IIS-Unterstützung in lync Server 2013](lync-server-2013-iis-support.md).</span><span class="sxs-lookup"><span data-stu-id="c9425-126">For details about requirements for reverse proxy servers (for Edge deployment), see [IIS support in Lync Server 2013](lync-server-2013-iis-support.md).</span></span>

  - <span data-ttu-id="c9425-127">Ausführliche Informationen zu anderen Softwareanforderungen, einschließlich Infrastruktur-und Virtualisierungs-Support, finden Sie in den anderen Themen der [Server Software-und-Infrastrukturunterstützung in lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span><span class="sxs-lookup"><span data-stu-id="c9425-127">For details about other software requirements, including infrastructure and virtualization support, see the other topics in the [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

