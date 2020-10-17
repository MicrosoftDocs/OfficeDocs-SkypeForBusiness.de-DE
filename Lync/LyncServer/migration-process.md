---
title: Migrationsvorgang
description: Migrationsprozess.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f363bd79a3d3be709d731d2ca4bffb4f83fe89ea
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569561"
---
# <a name="migration-process"></a><span data-ttu-id="139d8-103">Migrationsvorgang</span><span class="sxs-lookup"><span data-stu-id="139d8-103">Migration process</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="139d8-104">_**Letztes Änderungsstand des Themas:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="139d8-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="139d8-105">Das empfohlene und unterstützte Migrationsverfahren für lync Server 2013 ist die parallele Migration.</span><span class="sxs-lookup"><span data-stu-id="139d8-105">The recommended and supported migration procedure for Lync Server 2013 is side-by-side migration.</span></span> <span data-ttu-id="139d8-106">In diesem Thema wird beschrieben, warum Sie die parallele Migration verwenden sollten und auch Informationen zum Testen der Koexistenz enthält.</span><span class="sxs-lookup"><span data-stu-id="139d8-106">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="139d8-107">Parallele Migration</span><span class="sxs-lookup"><span data-stu-id="139d8-107">Side-By-Side Migration</span></span>

<span data-ttu-id="139d8-108">Am besten wenden Sie für jede Migration das Verfahren der parallelen Migration an.</span><span class="sxs-lookup"><span data-stu-id="139d8-108">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="139d8-109">Bei einer parallelen Migration stellen Sie einen neuen Server mit lync Server 2013 neben einem entsprechenden Server bereit, auf dem lync Server 2010 ausgeführt wird, und übertragen anschließend Vorgänge auf den neuen Server.</span><span class="sxs-lookup"><span data-stu-id="139d8-109">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Lync Server 2010, and then transfer operations to the new server.</span></span> <span data-ttu-id="139d8-110">Wenn ein Rollback auf lync Server 2010 erforderlich ist, müssen Sie nur die Vorgänge zurück auf die ursprünglichen Server verschieben.</span><span class="sxs-lookup"><span data-stu-id="139d8-110">If it becomes necessary to roll back to Lync Server 2010, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="139d8-111">Bedenken Sie, dass in diesem Fall neue Besprechungen, die mit aktualisierten Clients geplant wurden, nicht funktionieren und dass auch für die Clients ein Downgrade erforderlich wäre.</span><span class="sxs-lookup"><span data-stu-id="139d8-111">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="139d8-112">Koexistenztest</span><span class="sxs-lookup"><span data-stu-id="139d8-112">Coexistence Testing</span></span>

<span data-ttu-id="139d8-113">Nachdem Sie lync Server 2013 parallel mit lync Server 2010 bereitgestellt haben, stellt die Bereitstellung einen Testzustand der Koexistenz von lync Server 2013 und lync Server 2010 dar.</span><span class="sxs-lookup"><span data-stu-id="139d8-113">After you have deployed Lync Server 2013 in parallel with Lync Server 2010, the deployment represents a coexistence testing state of Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="139d8-114">In diesem Status ist es wichtig, zu testen und sicherzustellen, dass Dienste gestartet werden können, jeder Standort verwalten werden kann und die Clients mit Benutzern der aktuellen und der Vorgängerversion kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="139d8-114">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="139d8-115">Vor dem Migrieren aller Benutzer sollten Sie unbedingt den Status jeder Bereitstellung festgestellt und sich vergewissert haben, dass jede Bereitstellung ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="139d8-115">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="139d8-116">In der Regel besteht die Testphase der Koexistenz während der Pilottests von lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="139d8-116">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="139d8-117">Ältere Benutzer werden für einen bestimmten Zeitraum in lync Server 2013 verschoben, um sicherzustellen, dass Anwendungskompatibilität und Features und Funktionen ordnungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="139d8-117">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="139d8-118">Nach Pilottests werden Benutzer und Anwendungen in die Produktionsversion von lync Server 2013 verschoben, und die Legacy Pools und-Anwendungen von lync Server 2010 werden zurückgezogen.</span><span class="sxs-lookup"><span data-stu-id="139d8-118">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Lync Server 2010 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

