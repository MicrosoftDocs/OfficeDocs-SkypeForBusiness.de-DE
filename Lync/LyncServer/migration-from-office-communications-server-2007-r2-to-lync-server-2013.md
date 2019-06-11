---
title: Migration von Office Communications Server 2007 R2 zu Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration from Office Communications Server 2007 R2 to Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48185802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43064d265bc08cab3721d0f19fd7f89184871f0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847098"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a><span data-ttu-id="5f253-102">Migration von Office Communications Server 2007 R2 zu Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f253-102">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f253-103">_**Letztes Änderungsdatum des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="5f253-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="5f253-104">Die Themen in diesem Abschnitt führen Sie durch den Prozess der Migration von Office Communications Server 2007 R2 zu lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f253-104">The topics in this section guide you through the process of migrating from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5f253-105">In diesem Dokument werden die Schritte beschrieben, die in der Regel für die einzelnen Migrationsphasen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5f253-105">This document describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="5f253-106">Sie bezieht sich nicht auf jede mögliche Legacy Bereitstellungstopologie oder alle möglichen Migrationsszenarien.</span><span class="sxs-lookup"><span data-stu-id="5f253-106">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="5f253-107">Daher müssen Sie möglicherweise nicht alle beschriebenen Schritte ausführen, oder Sie müssen abhängig von Ihrer Bereitstellung möglicherweise zusätzliche Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="5f253-107">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="5f253-108">Dieses Dokument enthält auch Beispiele für Überprüfungsschritte.</span><span class="sxs-lookup"><span data-stu-id="5f253-108">This document also provides examples of verification steps.</span></span> <span data-ttu-id="5f253-109">Diese Überprüfungsschritte werden bereitgestellt, um Ihnen zu verdeutlichen, was Sie suchen müssen, um sicherzustellen, dass jede Phase erfolgreich abgeschlossen wird, während Sie Ihre Migration fortführen.</span><span class="sxs-lookup"><span data-stu-id="5f253-109">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="5f253-110">Passen Sie diese Überprüfungsschritte an den jeweiligen Migrationsprozess an.</span><span class="sxs-lookup"><span data-stu-id="5f253-110">Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="5f253-111">Dieses Handbuch enthält Informationen, die speziell für das Upgrade Ihrer vorhandenen Bereitstellung gelten.</span><span class="sxs-lookup"><span data-stu-id="5f253-111">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="5f253-112">Es wird nicht erläutert, wie Sie Ihre vorhandene Topologie ändern.</span><span class="sxs-lookup"><span data-stu-id="5f253-112">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="5f253-113">In diesem Leitfaden wird die Implementierung neuer Features nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="5f253-113">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="5f253-114">Wenn eine detaillierte Prozedur an anderer Stelle dokumentiert wird, werden Sie in diesem Leitfaden zu dem entsprechenden Dokument-oder Dokumentabschnitt weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="5f253-114">When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="5f253-115">In diesem Dokument werden die in der folgenden Liste angegebenen Ausdrücke definiert.</span><span class="sxs-lookup"><span data-stu-id="5f253-115">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="5f253-116">*Migrations*</span><span class="sxs-lookup"><span data-stu-id="5f253-116">*migration*</span></span>  
    <span data-ttu-id="5f253-117">Verschieben der Produktionsbereitstellung aus einer früheren Version von Office Communications Server 2007 R2 auf lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f253-117">Moving your production deployment from a previous version of Office Communications Server 2007 R2 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="5f253-118">*Upgrade*</span><span class="sxs-lookup"><span data-stu-id="5f253-118">*upgrade*</span></span>  
    <span data-ttu-id="5f253-119">Installieren einer neueren Software Version auf einem Server oder Clientcomputer</span><span class="sxs-lookup"><span data-stu-id="5f253-119">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="5f253-120">*Koexistenz*</span><span class="sxs-lookup"><span data-stu-id="5f253-120">*coexistence*</span></span>  
    <span data-ttu-id="5f253-121">Die temporäre Umgebung, die während der Migration vorhanden ist, wenn einige Funktionen zu lync Server 2013 migriert wurden und andere Funktionen weiterhin auf einer früheren Version von Office Communications Server 2007 R2 verbleiben.</span><span class="sxs-lookup"><span data-stu-id="5f253-121">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Office Communications Server 2007 R2.</span></span>

<!-- end list -->

  - <span data-ttu-id="5f253-122">*Interoperabilität*</span><span class="sxs-lookup"><span data-stu-id="5f253-122">*interoperability*</span></span>  
    <span data-ttu-id="5f253-123">Die Möglichkeit, dass Ihre Bereitstellung während des Zeitraums der Koexistenz erfolgreich ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="5f253-123">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5f253-124">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5f253-124">In This Section</span></span>

  - [<span data-ttu-id="5f253-125">Vorbereiten der Migration</span><span class="sxs-lookup"><span data-stu-id="5f253-125">Before you begin the migration</span></span>](before-you-begin-the-migration_1.md)

  - [<span data-ttu-id="5f253-126">Migrationsphasen</span><span class="sxs-lookup"><span data-stu-id="5f253-126">Migration phases</span></span>](migration-phases_1.md)

  - [<span data-ttu-id="5f253-127">Phase 1: Planen der Migration von Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="5f253-127">Phase 1: Plan your migration from Office Communications Server 2007 R2</span></span>](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [<span data-ttu-id="5f253-128">Phase 2: Vorbereitung der Migration</span><span class="sxs-lookup"><span data-stu-id="5f253-128">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration_1.md)

  - [<span data-ttu-id="5f253-129">Phase 3: Bereitstellen des lync Server 2013-pilotpools</span><span class="sxs-lookup"><span data-stu-id="5f253-129">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [<span data-ttu-id="5f253-130">Phase 4: Zusammenführen von Topologien</span><span class="sxs-lookup"><span data-stu-id="5f253-130">Phase 4: Merge topologies</span></span>](phase-4-merge-topologies.md)

  - [<span data-ttu-id="5f253-131">Phase 5: Konfigurieren des pilotpools</span><span class="sxs-lookup"><span data-stu-id="5f253-131">Phase 5: Configure the pilot pool</span></span>](phase-5-configure-the-pilot-pool.md)

  - [<span data-ttu-id="5f253-132">Phase 6: Verschieben von Benutzern in den Pilot Pool</span><span class="sxs-lookup"><span data-stu-id="5f253-132">Phase 6: Move users to the pilot pool</span></span>](phase-6-move-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="5f253-133">Phase 7: Hinzufügen von lync Server 2013 Edge-Server zu Pilot Pool</span><span class="sxs-lookup"><span data-stu-id="5f253-133">Phase 7: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="5f253-134">Phase 8: Wechseln von der Pilotbereitstellung in die Produktionsumgebung</span><span class="sxs-lookup"><span data-stu-id="5f253-134">Phase 8: Move from pilot deployment into production</span></span>](phase-8-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="5f253-135">Phase 9: Ausführen von Aufgaben nach der Migration</span><span class="sxs-lookup"><span data-stu-id="5f253-135">Phase 9: Complete post-migration tasks</span></span>](phase-9-complete-post-migration-tasks.md)

  - [<span data-ttu-id="5f253-136">Phase 10: Legacy Website der decommission</span><span class="sxs-lookup"><span data-stu-id="5f253-136">Phase 10: Decommission legacy site</span></span>](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

