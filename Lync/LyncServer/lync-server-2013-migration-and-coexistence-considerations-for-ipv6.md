---
title: 'Lync Server 2013: Überlegungen zu Migration und Koexistenz für IPv6'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration and coexistence considerations for IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48184751
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f091b12b12913af107991c86b87d1d738bf88bb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513612"
---
# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="e8515-102">Überlegungen zu Migration und Koexistenz für IPv6 in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8515-102">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8515-103">_**Letztes Änderungsstand des Themas:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="e8515-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="e8515-104">IP Version 6 (IPv6) wird auf lync Server 2010 oder Office Communications Server nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e8515-104">IP version 6 (IPv6) is not supported on Lync Server 2010 or Office Communications Server.</span></span> <span data-ttu-id="e8515-105">Für Pilot Zwecke können Sie lync Server 2010 und lync Server 2013 Dual-Stack-Koexistenz testen.</span><span class="sxs-lookup"><span data-stu-id="e8515-105">For piloting purposes, you can test Lync Server 2010 and Lync Server 2013 dual-stack coexistence.</span></span> <span data-ttu-id="e8515-106">Es wird empfohlen, alle Pools für einen bestimmten zentralen Standort auf lync Server 2013 zu aktualisieren, bevor Sie IPv6 (Dual-Stack-Netzwerk) für einen der Pools aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e8515-106">We recommend that all pools for a given central site are upgraded to Lync Server 2013 before you enable IPv6 (dual-stack network) for any of the pools.</span></span> <span data-ttu-id="e8515-107">Wenn Sie einen Pool nur für IPv6 konfigurieren müssen, wird empfohlen, dass Sie einen Pool nur mit IPv6 in Ihrer Testumgebung zum Testen einrichten.</span><span class="sxs-lookup"><span data-stu-id="e8515-107">If you need to configure a pool for IPv6 only, we recommend that you set up an IPv6-only pool in your lab environment for testing.</span></span>

<span data-ttu-id="e8515-108">Die folgenden Szenarien werden bei der Migration und Koexistenz unterstützt:</span><span class="sxs-lookup"><span data-stu-id="e8515-108">The following scenarios are supported during migration and coexistence:</span></span>

  - <span data-ttu-id="e8515-109">Lync Server 2013-, lync Server 2010-und Office Communications Server 2007 R2 Pools im IPv4-Modus, die mit lync Server 2013 im Dual-Stack-Modus nebeneinander stehen.</span><span class="sxs-lookup"><span data-stu-id="e8515-109">Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2 pools in IPv4 mode, coexisting with Lync Server 2013 in dual-stack mode.</span></span>

  - <span data-ttu-id="e8515-110">Lync Server 2013 Pool im reinen IPv6-Modus, wenn der nur-IPv6-Pool isoliert ist.</span><span class="sxs-lookup"><span data-stu-id="e8515-110">Lync Server 2013 pool in IPv6-only mode, if the IPv6-only pool is siloed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

