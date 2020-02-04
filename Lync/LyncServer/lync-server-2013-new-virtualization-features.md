---
title: 'Lync Server 2013: Neue Virtualisierungsfunktionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New virtualization features
ms:assetid: edeb2c41-765e-47b8-8a2b-7a7ce09de2ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721926(v=OCS.15)
ms:contentKeyID: 49733861
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 687e1c77cec18dc9ad4372fd911db32c537c61c9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755859"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-virtualization-features-in-lync-server-2013"></a><span data-ttu-id="01e22-102">Neue Virtualisierungsfunktionen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01e22-102">New virtualization features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01e22-103">_**Letztes Änderungsdatum des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="01e22-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="01e22-104">Lync Server 2013 unterstützt die Virtualisierung sowohl auf Windows Server 2012, Windows Server 2012 R2 und Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="01e22-104">Lync Server 2013 supports virtualization on both Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span> <span data-ttu-id="01e22-105">Unterstützung für Windows Server 2012 und Windows Server 2012 R2 bietet Unterstützung für die einzelnen root I/O Virtualization-Funktionen (SR-IOV).</span><span class="sxs-lookup"><span data-stu-id="01e22-105">Support on Windows Server 2012 and Windows Server 2012 R2 includes support for the Single Root I/O Virtualization (SR-IOV) capabilities.</span></span> <span data-ttu-id="01e22-106">Bei SR-IOV wird die virtuelle Funktion eines physikalischen Netzwerkadapters direkt einem virtuellen Computer zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="01e22-106">With SR-IOV, the virtual function of a physical network adapter is assigned directly to a virtual machine.</span></span> <span data-ttu-id="01e22-107">Dadurch wird der Netzwerkdurchsatz erhöht und die Netzwerklatenz verringert, während gleichzeitig der für die Verarbeitung des Netzwerkdatenverkehrs erforderliche Host-CPU-Overhead verringert wird.</span><span class="sxs-lookup"><span data-stu-id="01e22-107">This increases network throughput and reduces network latency while also reducing the host CPU overhead that is required for processing network traffic.</span></span> <span data-ttu-id="01e22-108">Um die Vorteile von SR-IOV zu nutzen, müssen Sie einen Hostserver verwenden, der über ein BIOS verfügt, das SR-IOV unterstützt, sowie Netzwerkadapter verwenden, die SR-IOV unterstützen.</span><span class="sxs-lookup"><span data-stu-id="01e22-108">To take advantage of SR-IOV, you must use a host server which has BIOS which supports SR-IOV, as well as use network adapters that support SR-IOV.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

