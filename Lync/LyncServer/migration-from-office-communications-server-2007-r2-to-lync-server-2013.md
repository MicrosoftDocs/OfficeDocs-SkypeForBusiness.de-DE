---
title: Migration von Office Communications Server 2007 R2 zu lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Office Communications Server 2007 R2 to Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48185802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a71ac7e0e1291dedfa45e4e358b5b3495d8a623b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527252"
---
# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a><span data-ttu-id="3e062-102">Migration von Office Communications Server 2007 R2 zu lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e062-102">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e062-103">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="3e062-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="3e062-104">Die Themen in diesem Abschnitt führen Sie durch den Migrationsprozess von Office Communications Server 2007 R2 zu lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e062-104">The topics in this section guide you through the process of migrating from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3e062-p101">In diesem Dokument werden die Schritte beschrieben, die im Allgemeinen zur Durchführung der einzelnen Phasen der Migration erforderlich sind. Es wird darin nicht auf jede mögliche Bereitstellungstopologie der Vorversion oder jedes mögliche Migrationsszenario eingegangen. Deshalb ist es nicht notwendig, dass Sie jeden beschriebenen Schritt ausführen; ggf. müssen Sie auch, abhängig von Ihrer Bereitstellung, zusätzliche Schritte ausführen. Darüber hinaus werden in diesem Dokument auch Beispiele für Überprüfungsschritte aufgeführt. Durch diese Überprüfungsschritte können Sie einfacher erkennen, wie Sie die erfolgreiche Ausführung der einzelnen Phasen der Migration sicherstellen können. Passen Sie diese Überprüfungsschritte an Ihren jeweiligen Migrationsprozess an.</span><span class="sxs-lookup"><span data-stu-id="3e062-p101">This document describes the steps generally required to accomplish each phase of migration. It does not address every possible legacy deployment topology or every possible migration scenario. Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment. This document also provides examples of verification steps. These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration. Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="3e062-p102">Dieses Handbuch enthält Informationen, die speziell auf die Aktualisierung Ihrer vorhandenen Bereitstellung eingehen. Die Änderung Ihrer vorhandenen Topologie wird darin nicht behandelt. In diesem Handbuch wird nicht die Implementierung neuer Funktionen behandelt. Dieses Handbuch enthält entsprechende Verweise auf Verfahren, die in anderen Dokumenten detailliert beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="3e062-p102">This guide provides information specific to upgrading your existing deployment. It does not explain how to change your existing topology. This guide does not cover the implementation of new features. When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="3e062-115">In diesem Dokument werden Begriffe gemäß der Definition in der folgenden Liste verwendet.</span><span class="sxs-lookup"><span data-stu-id="3e062-115">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="3e062-116">*Migration*</span><span class="sxs-lookup"><span data-stu-id="3e062-116">*migration*</span></span>  
    <span data-ttu-id="3e062-117">Verschieben der Produktionsbereitstellung von einer früheren Version von Office Communications Server 2007 R2 auf lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3e062-117">Moving your production deployment from a previous version of Office Communications Server 2007 R2 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="3e062-118">*upgrade*</span><span class="sxs-lookup"><span data-stu-id="3e062-118">*upgrade*</span></span>  
    <span data-ttu-id="3e062-119">Installieren einer neueren Softwareversion auf einem Server oder Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="3e062-119">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="3e062-120">*Koexistenz*</span><span class="sxs-lookup"><span data-stu-id="3e062-120">*coexistence*</span></span>  
    <span data-ttu-id="3e062-121">Die temporäre Umgebung, die während der Migration vorhanden ist, wenn einige Funktionen zu lync Server 2013 migriert wurden und andere Funktionen weiterhin in einer früheren Version von Office Communications Server 2007 R2 verbleiben.</span><span class="sxs-lookup"><span data-stu-id="3e062-121">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Office Communications Server 2007 R2.</span></span>

<!-- end list -->

  - <span data-ttu-id="3e062-122">*Interoperabilität*</span><span class="sxs-lookup"><span data-stu-id="3e062-122">*interoperability*</span></span>  
    <span data-ttu-id="3e062-123">Die Fähigkeit Ihrer Bereitstellung, während der Phase der Koexistenz erfolgreich ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="3e062-123">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3e062-124">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="3e062-124">In This Section</span></span>

  - [<span data-ttu-id="3e062-125">Vorbereiten der Migration</span><span class="sxs-lookup"><span data-stu-id="3e062-125">Before you begin the migration</span></span>](before-you-begin-the-migration_1.md)

  - [<span data-ttu-id="3e062-126">Migrationsphasen</span><span class="sxs-lookup"><span data-stu-id="3e062-126">Migration phases</span></span>](migration-phases_1.md)

  - [<span data-ttu-id="3e062-127">Phase 1: Planen der Migration von Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3e062-127">Phase 1: Plan your migration from Office Communications Server 2007 R2</span></span>](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [<span data-ttu-id="3e062-128">Phase 2: Vorbereitung der Migration</span><span class="sxs-lookup"><span data-stu-id="3e062-128">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration_1.md)

  - [<span data-ttu-id="3e062-129">Phase 3: Bereitstellen lync Server 2013 pilotpools</span><span class="sxs-lookup"><span data-stu-id="3e062-129">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [<span data-ttu-id="3e062-130">Phase 4: Zusammenführen von Topologien</span><span class="sxs-lookup"><span data-stu-id="3e062-130">Phase 4: Merge topologies</span></span>](phase-4-merge-topologies.md)

  - [<span data-ttu-id="3e062-131">Phase 5: Konfigurieren des pilotpools</span><span class="sxs-lookup"><span data-stu-id="3e062-131">Phase 5: Configure the pilot pool</span></span>](phase-5-configure-the-pilot-pool.md)

  - [<span data-ttu-id="3e062-132">Phase 6: Migrieren von Benutzern zum Pilot Pool</span><span class="sxs-lookup"><span data-stu-id="3e062-132">Phase 6: Move users to the pilot pool</span></span>](phase-6-move-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="3e062-133">Phase 7: Hinzufügen von lync Server 2013 Edgeserver zu einem Pilot Pool</span><span class="sxs-lookup"><span data-stu-id="3e062-133">Phase 7: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="3e062-134">Phase 8: Umsteigen von der Pilotbereitstellung in die Produktion</span><span class="sxs-lookup"><span data-stu-id="3e062-134">Phase 8: Move from pilot deployment into production</span></span>](phase-8-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="3e062-135">Phase 9: Ausführen von Aufgaben nach der Migration</span><span class="sxs-lookup"><span data-stu-id="3e062-135">Phase 9: Complete post-migration tasks</span></span>](phase-9-complete-post-migration-tasks.md)

  - [<span data-ttu-id="3e062-136">Phase 10: decommission Legacy Site</span><span class="sxs-lookup"><span data-stu-id="3e062-136">Phase 10: Decommission legacy site</span></span>](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

