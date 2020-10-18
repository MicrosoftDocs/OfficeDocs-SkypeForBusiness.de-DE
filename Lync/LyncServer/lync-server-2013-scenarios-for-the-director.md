---
title: 'Lync Server 2013: Szenarien für den Director'
description: 'Lync Server 2013: Szenarien für den Director.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for the Director
ms:assetid: d2cf384a-0860-4779-80ce-cba2543be322
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398908(v=OCS.15)
ms:contentKeyID: 48185419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45c611fbe680ba55fb148c08fed26d96a848507e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579001"
---
# <a name="scenarios-for-the-director-in-lync-server-2013"></a><span data-ttu-id="3ff1a-103">Szenarien für den Director in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ff1a-103">Scenarios for the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ff1a-104">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="3ff1a-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="3ff1a-105">Bei einem Director handelt es sich um einen Server mit Microsoft lync Server 2013 Kommunikationssoftware, der Benutzeranforderungen authentifizieren kann, jedoch keine Benutzerkonten aufweist.</span><span class="sxs-lookup"><span data-stu-id="3ff1a-105">A Director is a server running Microsoft Lync Server 2013 communications software that can authenticate user requests, but does not home any user accounts.</span></span> <span data-ttu-id="3ff1a-106">Der Director hostet außerdem Webdienste, die dem Front-End-Server ähneln und WebTICKET-Anforderungen authentifizieren und andere Dienste bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="3ff1a-106">The Director also hosts web services similar to the Front End Server and will authenticate web ticket requests and provide other services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3ff1a-107">Wenn Sie Directors bereitstellen, müssen Sie die Director-Webdienste extern über den Reverseproxy und die Webdienste des Front-End-Server veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="3ff1a-107">If you deploy Directors, you must publish the Director web services externally through the reverse proxy as well as the web services of the Front End Server.</span></span> <span data-ttu-id="3ff1a-108">In den folgenden Themen wird der Planungsprozess für die möglichen Director-Topologien beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3ff1a-108">The topics following describe the planning process for the possible Director topologies.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3ff1a-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="3ff1a-109">In This Section</span></span>

  - [<span data-ttu-id="3ff1a-110">Übersicht über den Director in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ff1a-110">Overview of the Director in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-director.md)

  - [<span data-ttu-id="3ff1a-111">Erforderliche Komponenten für den Director in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ff1a-111">Components required for the Director in Lync Server 2013</span></span>](lync-server-2013-components-required-for-the-director.md)

  - [<span data-ttu-id="3ff1a-112">Hardware-und Softwareanforderungen für den Director in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ff1a-112">Hardware and software requirements for the Director in Lync Server 2013</span></span>](lync-server-2013-hardware-and-software-requirements-for-the-director.md)

  - [<span data-ttu-id="3ff1a-113">Einzelner Director in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ff1a-113">Single Director in Lync Server 2013</span></span>](lync-server-2013-single-director.md)

  - [<span data-ttu-id="3ff1a-114">Skalierte Directorpool in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ff1a-114">Scaled Director pool in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3ff1a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ff1a-115">See Also</span></span>


[<span data-ttu-id="3ff1a-116">Unterstützte Topologien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ff1a-116">Supported topologies in Lync Server 2013</span></span>](lync-server-2013-supported-topologies.md)  
[<span data-ttu-id="3ff1a-117">Server Hardwareplattformen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ff1a-117">Server hardware platforms for Lync Server 2013</span></span>](lync-server-2013-server-hardware-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

