---
title: Lync Server 2013 Unterstützung für große Besprechungen
description: Lync Server 2013 Unterstützung für große Besprechungen.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for large meetings
ms:assetid: 8f0446d5-1ed9-4ea0-bb97-6c062a98a1eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205090(v=OCS.15)
ms:contentKeyID: 48184820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb37cbfb95e36b9a07604eb4fbbc548e4d7ce9a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546261"
---
# <a name="support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="38b85-103">Unterstützung für große Besprechungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38b85-103">Support for large meetings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38b85-104">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="38b85-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="38b85-105">Lync Server 2013 können Besprechungen mit bis zu 1000 Teilnehmern mithilfe von Audio/Video-Konferenzen (A/V) unterstützen, einschließlich der Freigabe von PowerPoint-Präsentationen.</span><span class="sxs-lookup"><span data-stu-id="38b85-105">Lync Server 2013 can support meetings with up to 1000 participants using audio/video (A/V) conferencing, including sharing PowerPoint presentations.</span></span> <span data-ttu-id="38b85-106">Diese Unterstützung erfordert einen dedizierten Pool, der für die Unterstützung großer Besprechungen konfiguriert und so verwaltet wird, dass gleichzeitig nur eine einzige große Besprechung gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="38b85-106">This support requires a dedicated pool configured to support large meetings and managed in a way that ensures hosting of only a single large meeting at a time.</span></span>

<span data-ttu-id="38b85-107">In diesem Abschnitt wird beschrieben, wie Sie große Besprechungen mithilfe eines dedizierten lync Server 2013 Pools unterstützen.</span><span class="sxs-lookup"><span data-stu-id="38b85-107">This section describes how to support large meetings using a dedicated Lync Server 2013 pool.</span></span> <span data-ttu-id="38b85-108">Es werden Skalierbarkeits Überlegungen und die Implementierungsanforderungen für einen dedizierten Pool beschrieben, einschließlich Topologie-, Hardware-, Software-und Konfigurationsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="38b85-108">It describes scalability considerations and the implementation requirements for a dedicated pool, including topology, hardware, software, and configuration requirements.</span></span> <span data-ttu-id="38b85-109">Außerdem werden bewährte Methoden für die Unterstützung von großen Besprechungen, eine Zusammenfassung der Testmethoden und Ergebnisse der Server Skalierbarkeitstests, die vom lync Server Engineering-Team durchgeführt wurden, sowie die Antworten auf häufig gestellte Fragen zur Unterstützung für große Besprechungen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="38b85-109">It also provides a set of best practice recommendations for supporting large meetings, a summary of the test methods and results of server scalability testing conducted by the Lync Server engineering team, and the answers to frequently asked questions about support for large meetings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="38b85-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="38b85-110">In This Section</span></span>

  - [<span data-ttu-id="38b85-111">Übersicht über die Skalierbarkeit von Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38b85-111">Overview of conferencing scalability in Lync Server 2013</span></span>](lync-server-2013-conferencing-scalability-overview.md)

  - [<span data-ttu-id="38b85-112">Unterstützen großer Besprechungen mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38b85-112">Supporting large meetings using Lync Server 2013</span></span>](lync-server-2013-supporting-large-meetings.md)

  - [<span data-ttu-id="38b85-113">FAQ für umfangreiche Besprechungs Unterstützung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38b85-113">Large meeting support FAQ for Lync Server 2013</span></span>](lync-server-2013-large-meeting-support-faq.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

