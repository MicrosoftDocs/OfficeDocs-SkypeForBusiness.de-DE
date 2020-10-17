---
title: 'Lync Server 2013: Wiederherstellen eines lync Server Pools'
description: 'Lync Server 2013: Wiederherstellen eines lync Server-Pools.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Lync Server pool
ms:assetid: 6fe80fb3-38ad-4931-a07b-1763b61aa448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202176(v=OCS.15)
ms:contentKeyID: 51541488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02e92b4e7af9cf782d49c265425006e0118b9161
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543811"
---
# <a name="restoring-a-lync-server-pool-in-lync-server-2013"></a><span data-ttu-id="27212-103">Wiederherstellen eines lync Server Pools in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27212-103">Restoring a Lync Server pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27212-104">_**Letztes Änderungsstand des Themas:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="27212-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="27212-105">Die lync Server-Bereitstellung kann einen der folgenden Typen von Pools umfassen:</span><span class="sxs-lookup"><span data-stu-id="27212-105">Your Lync Server deployment may include any of the following types of pools:</span></span>

  - <span data-ttu-id="27212-106">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="27212-106">Front End Server</span></span>

  - <span data-ttu-id="27212-107">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="27212-107">Mediation Server</span></span>

  - <span data-ttu-id="27212-108">Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="27212-108">Persistent Chat Server</span></span>

  - <span data-ttu-id="27212-109">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="27212-109">Edge Server</span></span>

<span data-ttu-id="27212-110">Wenn für einen gesamten Pool ein Ausfall auftritt, führen Sie die folgenden Schritte für jeden Mitgliedsserver im Pool aus.</span><span class="sxs-lookup"><span data-stu-id="27212-110">If an entire pool experiences an outage, follow these procedures for each member server in the pool.</span></span>

  - <span data-ttu-id="27212-111">Stellen Sie für ein Front-End-Pool den Back-End-Server zuerst wieder her, und stellen Sie dann jeden Front-End-Server wieder her.</span><span class="sxs-lookup"><span data-stu-id="27212-111">For a Front End pool, restore the Back End Server first, and then restore each Front End Server.</span></span> <span data-ttu-id="27212-112">Ausführliche Informationen finden Sie unter [Wiederherstellen eines Enterprise Edition-Back-End-Servers in lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) und [Wiederherstellen eines Enterprise Edition-Mitgliedsservers in lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="27212-112">For details, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) and [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

  - <span data-ttu-id="27212-113">Stellen Sie für alle anderen Typen von Pools jeden Mitgliedsserver wieder her.</span><span class="sxs-lookup"><span data-stu-id="27212-113">For all other types of pools, restore each member server.</span></span> <span data-ttu-id="27212-114">Ausführliche Informationen finden Sie unter [Wiederherstellen eines Enterprise Edition-Mitgliedsservers in lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="27212-114">For details, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

