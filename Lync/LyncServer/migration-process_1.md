---
title: Migrationsprozess
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2da65ead79d33ff03a66f4ec5ef54fa4e2167890
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="48cdf-102">Migrationsprozess</span><span class="sxs-lookup"><span data-stu-id="48cdf-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48cdf-103">_**Letztes Änderungsstand des Themas:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="48cdf-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="48cdf-104">Das empfohlene und unterstützte Migrationsverfahren für lync Server 2013 ist die parallele Migrationsprozedur.</span><span class="sxs-lookup"><span data-stu-id="48cdf-104">The recommended and supported migration procedure for Lync Server 2013 is the side-by-side migration procedure.</span></span> <span data-ttu-id="48cdf-105">In diesem Thema wird beschrieben, weshalb Sie die parallele Migration verwenden sollten, und es enthält zudem Informationen über die Koexistenz.</span><span class="sxs-lookup"><span data-stu-id="48cdf-105">This topic describes why you should use side-by-side migration and also includes information about coexistence.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="48cdf-106">Parallele Migration</span><span class="sxs-lookup"><span data-stu-id="48cdf-106">Side-by-Side Migration</span></span>

<span data-ttu-id="48cdf-107">Am besten wenden Sie für nahezu jede Migration das Verfahren der parallelen Migration an.</span><span class="sxs-lookup"><span data-stu-id="48cdf-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="48cdf-108">Bei einer parallelen Migration stellen Sie einen neuen Server mit lync Server 2013 neben einem entsprechenden Server bereit, auf dem Office Communications Server 2007 R2 ausgeführt wird, und Sie können dann Vorgänge auf den neuen Server übertragen.</span><span class="sxs-lookup"><span data-stu-id="48cdf-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Office Communications Server 2007 R2, and then you transfer operations to the new server.</span></span> <span data-ttu-id="48cdf-109">Wenn ein Rollback auf Office Communications Server 2007 R2 erforderlich ist, müssen Sie nur die Vorgänge zurück auf die ursprünglichen Server verschieben.</span><span class="sxs-lookup"><span data-stu-id="48cdf-109">If it becomes necessary to roll back to Office Communications Server 2007 R2, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="48cdf-110">Bedenken Sie, dass in diesem Fall neue Besprechungen, die mit aktualisierten Clients geplant wurden, nicht funktionieren und dass auch für die Clients ein Downgrade erforderlich wäre.</span><span class="sxs-lookup"><span data-stu-id="48cdf-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="48cdf-111">Koexistenztest</span><span class="sxs-lookup"><span data-stu-id="48cdf-111">Coexistence Testing</span></span>

<span data-ttu-id="48cdf-112">Nachdem Sie lync Server 2013 parallel mit Office Communications Server 2007 R2 bereitgestellt haben, stellt die Topologie einen Testzustand der Koexistenz von lync Server 2013 und Office Communications Server 2007 R2 dar.</span><span class="sxs-lookup"><span data-stu-id="48cdf-112">After you have deployed Lync Server 2013 in parallel with Office Communications Server 2007 R2, the topology represents a coexistence testing state of Lync Server 2013 and Office Communications Server 2007 R2.</span></span> <span data-ttu-id="48cdf-113">In diesem Zustand ist es wichtig zu testen und sicherzustellen, dass Dienste gestartet werden, jeder Standort verwaltet werden kann und Clients mit aktuellen und älteren Benutzern kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="48cdf-113">While in this state, it is important to test and ensure services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="48cdf-114">Vor dem Migrieren aller Benutzer sollten Sie unbedingt den Status jeder Bereitstellung festgestellt und sich vergewissert haben, dass jede Bereitstellung ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="48cdf-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="48cdf-115">In der Regel besteht die Testphase der Koexistenz während der Pilottests von lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48cdf-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="48cdf-116">Ältere Benutzer werden für einen bestimmten Zeitraum in lync Server 2013 verschoben, um sicherzustellen, dass Anwendungskompatibilität und Features und Funktionen ordnungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="48cdf-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="48cdf-117">Nach Pilottests werden Benutzer und Anwendungen in die Produktionsversion von lync Server 2013 verschoben, und die Legacy Pools und-Anwendungen von Office Communications Server 2007 R2 werden zurückgezogen.</span><span class="sxs-lookup"><span data-stu-id="48cdf-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Office Communications Server 2007 R2 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

