---
title: 'Lync Server 2013: Durchführen eines Failovers des ABC-Front-End-Pools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing an ABC Front End pool failover
ms:assetid: 81ecd26d-49e3-4c72-a66e-02748efb513b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945637(v=OCS.15)
ms:contentKeyID: 51541489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 155d8224b80e614ac8609c007a16072e9d3a5c60
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755275"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-an-abc-front-end-pool-failover-in-lync-server-2013"></a><span data-ttu-id="d376c-102">Durchführen eines ABC-Front-End-Pool-Failovers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d376c-102">Performing an ABC Front End pool failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d376c-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d376c-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d376c-104">In den beiden Themen in diesem Abschnitt wird das Verfahren für die Durchführung eines ABC-Pool-Failovers in lync Server 2013 beschrieben, in dem zwei lync Server-Front-End-Pools a und B vorhanden sind und Pool a nicht mehr wiederhergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d376c-104">The two topics in this section describe the procedure for performing an ABC pool failover in Lync Server 2013, where there are paired Lync Server Front End pools A and B, and pool A becomes unrecoverable.</span></span> <span data-ttu-id="d376c-105">Mit diesem Verfahren erstellen Sie einen neuen Front-End-Pool C mit einem neuen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN).</span><span class="sxs-lookup"><span data-stu-id="d376c-105">Using this procedure, you create a new Front End pool C with a new fully qualified domain name (FQDN).</span></span> <span data-ttu-id="d376c-106">Pool C wird aus den Informationen aus einem fehlerhaften Pool A erstellt. Das Verfahren umfasst auch die Kopplung von Pools B und C.</span><span class="sxs-lookup"><span data-stu-id="d376c-106">Pool C is constructed from the information from failed pool A. The procedure also includes pairing together pools B and C.</span></span>

  - [<span data-ttu-id="d376c-107">Backup-Voraussetzungen für ABC-Pool-Failover in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d376c-107">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>](lync-server-2013-backup-prerequisites-for-abc-pool-failover.md)

  - [<span data-ttu-id="d376c-108">ABC-Failover-Verfahren im Front-End-Pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d376c-108">Front End pool ABC failover procedure in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-abc-failover-procedure.md)

</div>

<span> </span>

</div>

</div>

</div>

