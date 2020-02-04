---
title: 'Lync Server 2013: Szenarien für den Director'
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
ms.openlocfilehash: ac7c5a262f5323f28ff089766cab1f4d65e30757
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-the-director-in-lync-server-2013"></a><span data-ttu-id="a16bc-102">Szenarien für den Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a16bc-102">Scenarios for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a16bc-103">_**Letztes Änderungsdatum des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="a16bc-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="a16bc-104">Bei einem Director handelt es sich um einen Server mit Microsoft lync Server 2013-Kommunikationssoftware, der Benutzeranforderungen authentifizieren kann, jedoch keine Benutzerkonten aufweist.</span><span class="sxs-lookup"><span data-stu-id="a16bc-104">A Director is a server running Microsoft Lync Server 2013 communications software that can authenticate user requests, but does not home any user accounts.</span></span> <span data-ttu-id="a16bc-105">Der Direktor hostet auch Webdienste, die dem Front-End-Server ähnlich sind, und authentifiziert Web-Ticket-Anfragen und stellt andere Dienste bereit.</span><span class="sxs-lookup"><span data-stu-id="a16bc-105">The Director also hosts web services similar to the Front End Server and will authenticate web ticket requests and provide other services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a16bc-106">Wenn Sie Directors bereitstellen, müssen Sie die Director-Webdienste extern über den Reverse-Proxy und die Webdienste des Front-End-Servers veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="a16bc-106">If you deploy Directors, you must publish the Director web services externally through the reverse proxy as well as the web services of the Front End Server.</span></span> <span data-ttu-id="a16bc-107">In den folgenden Themen wird der Planungsprozess für die möglichen Director-Topologien beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a16bc-107">The topics following describe the planning process for the possible Director topologies.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a16bc-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a16bc-108">In This Section</span></span>

  - [<span data-ttu-id="a16bc-109">Übersicht über den Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a16bc-109">Overview of the Director in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-director.md)

  - [<span data-ttu-id="a16bc-110">Für den Director erforderliche Komponenten in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a16bc-110">Components required for the Director in Lync Server 2013</span></span>](lync-server-2013-components-required-for-the-director.md)

  - [<span data-ttu-id="a16bc-111">Hardware- und Softwareanforderungen für den Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a16bc-111">Hardware and software requirements for the Director in Lync Server 2013</span></span>](lync-server-2013-hardware-and-software-requirements-for-the-director.md)

  - [<span data-ttu-id="a16bc-112">Einzelner Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a16bc-112">Single Director in Lync Server 2013</span></span>](lync-server-2013-single-director.md)

  - [<span data-ttu-id="a16bc-113">Skalierter Directorpool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a16bc-113">Scaled Director pool in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a16bc-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a16bc-114">See Also</span></span>


[<span data-ttu-id="a16bc-115">Unterstützte Topologien in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a16bc-115">Supported topologies in Lync Server 2013</span></span>](lync-server-2013-supported-topologies.md)  
[<span data-ttu-id="a16bc-116">Serverhardwareplattformen für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a16bc-116">Server hardware platforms for Lync Server 2013</span></span>](lync-server-2013-server-hardware-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

