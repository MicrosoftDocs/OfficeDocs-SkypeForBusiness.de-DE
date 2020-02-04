---
title: Migrationsvorgang
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2771a7a8b29cf410f9da5155e8f379bd7efe0e4e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="7d044-102">Migrationsvorgang</span><span class="sxs-lookup"><span data-stu-id="7d044-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d044-103">_**Letztes Änderungsdatum des Themas:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="7d044-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="7d044-104">Das empfohlene und unterstützte Migrationsverfahren für lync Server 2013 ist das parallele Migrationsverfahren.</span><span class="sxs-lookup"><span data-stu-id="7d044-104">The recommended and supported migration procedure for Lync Server 2013 is the side-by-side migration procedure.</span></span> <span data-ttu-id="7d044-105">In diesem Thema wird beschrieben, warum Sie eine parallele Migration verwenden sollten, und Sie enthält auch Informationen zur Koexistenz.</span><span class="sxs-lookup"><span data-stu-id="7d044-105">This topic describes why you should use side-by-side migration and also includes information about coexistence.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="7d044-106">Parallele Migration</span><span class="sxs-lookup"><span data-stu-id="7d044-106">Side-by-Side Migration</span></span>

<span data-ttu-id="7d044-107">In fast jeder Migration sollten Sie den parallelen Migrationspfad verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d044-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="7d044-108">Bei einer parallelen Migration stellen Sie einen neuen Server mit lync Server 2013 zusammen mit einem entsprechenden Server bereit, auf dem Office Communications Server 2007 R2 ausgeführt wird, und Sie können dann Vorgänge auf den neuen Server übertragen.</span><span class="sxs-lookup"><span data-stu-id="7d044-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Office Communications Server 2007 R2, and then you transfer operations to the new server.</span></span> <span data-ttu-id="7d044-109">Wenn ein Rollback zu Office Communications Server 2007 R2 erforderlich ist, müssen Sie die Vorgänge nur zurück zu den ursprünglichen Servern verschieben.</span><span class="sxs-lookup"><span data-stu-id="7d044-109">If it becomes necessary to roll back to Office Communications Server 2007 R2, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="7d044-110">Beachten Sie, dass in dieser Situation alle neuen Besprechungen, die mit aktualisierten Clients geplant sind, nicht funktionieren, und die Clients müssten ebenfalls heruntergestuft werden.</span><span class="sxs-lookup"><span data-stu-id="7d044-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="7d044-111">Koexistenz testen</span><span class="sxs-lookup"><span data-stu-id="7d044-111">Coexistence Testing</span></span>

<span data-ttu-id="7d044-112">Nachdem Sie lync Server 2013 parallel zu Office Communications Server 2007 R2 bereitgestellt haben, stellt die Topologie einen Teststatus für die Koexistenz von lync Server 2013 und Office Communications Server 2007 R2 dar.</span><span class="sxs-lookup"><span data-stu-id="7d044-112">After you have deployed Lync Server 2013 in parallel with Office Communications Server 2007 R2, the topology represents a coexistence testing state of Lync Server 2013 and Office Communications Server 2007 R2.</span></span> <span data-ttu-id="7d044-113">In diesem Zustand ist es wichtig, zu testen und sicherzustellen, dass Dienste gestartet werden, jeder Standort verwaltet werden kann und Clients mit aktuellen und älteren Benutzern kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="7d044-113">While in this state, it is important to test and ensure services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="7d044-114">Vor der Migration aller Benutzer ist es sehr wichtig, dass Sie den Zustand jeder Bereitstellung verstehen und sicherstellen, dass jede Bereitstellung funktionsfähig ist und ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="7d044-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="7d044-115">In der Regel ist die Koexistenz Testphase während des Pilottests von lync Server 2013 vorhanden.</span><span class="sxs-lookup"><span data-stu-id="7d044-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="7d044-116">Ältere Benutzer werden für einen bestimmten Zeitraum nach lync Server 2013 verschoben, um sicherzustellen, dass die Anwendungskompatibilität und die Features und Funktionen ordnungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="7d044-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="7d044-117">Nach Pilottests werden Benutzer und Anwendungen in die Produktionsversion von lync Server 2013 verschoben, und die Legacy Pools und-Anwendungen von Office Communications Server 2007 R2 werden eingestellt.</span><span class="sxs-lookup"><span data-stu-id="7d044-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Office Communications Server 2007 R2 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

