---
title: Migration von Lync Server 2010 zu Lync Server 2013
description: Migration von lync Server 2010 zu lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbe1bc1b7745c5ddc89a7f8fb64295a82f52c9bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543201"
---
# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a><span data-ttu-id="da386-103">Migration von Lync Server 2010 zu Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da386-103">Migration from Lync Server 2010 to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da386-104">_**Letztes Änderungsstand des Themas:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="da386-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="da386-105">Die Themen in diesem Abschnitt führen Sie durch den Migrationsprozess von lync Server 2010 zu lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="da386-105">The topics in this section guide you through the process of migrating from Lync Server 2010 to Lync Server 2013.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="da386-p101">In diesem Dokument werden die Schritte beschrieben, die im Allgemeinen zur Durchführung der einzelnen Phasen der Migration erforderlich sind. Es wird darin nicht auf jede mögliche Bereitstellungstopologie der Vorversion oder jedes mögliche Migrationsszenario eingegangen. Deshalb ist es nicht notwendig, dass Sie jeden beschriebenen Schritt ausführen; ggf. müssen Sie auch, abhängig von Ihrer Bereitstellung, zusätzliche Schritte ausführen. Darüber hinaus werden in diesem Dokument auch Beispiele für Überprüfungsschritte aufgeführt. Durch diese Überprüfungsschritte können Sie einfacher erkennen, wie Sie die erfolgreiche Ausführung der einzelnen Phasen der Migration sicherstellen können. Passen Sie diese Überprüfungsschritte an Ihren jeweiligen Migrationsprozess an.</span><span class="sxs-lookup"><span data-stu-id="da386-p101">This document describes the steps generally required to accomplish each phase of migration. It does not address every possible legacy deployment topology or every possible migration scenario. Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment. This document also provides examples of verification steps. These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration. Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="da386-p102">Dieses Handbuch enthält Informationen, die speziell auf die Aktualisierung Ihrer vorhandenen Bereitstellung eingehen. Die Änderung Ihrer vorhandenen Topologie wird darin nicht behandelt. In diesem Handbuch wird nicht die Implementierung neuer Funktionen behandelt. Dieses Handbuch enthält entsprechende Verweise auf Verfahren, die in anderen Dokumenten detailliert beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="da386-p102">This guide provides information specific to upgrading your existing deployment. It does not explain how to change your existing topology. This guide does not cover the implementation of new features. When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="da386-116">In diesem Dokument werden Begriffe gemäß der Definition in der folgenden Liste verwendet.</span><span class="sxs-lookup"><span data-stu-id="da386-116">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="da386-117">*Migration*</span><span class="sxs-lookup"><span data-stu-id="da386-117">*migration*</span></span>  
    <span data-ttu-id="da386-118">Verschieben der Produktionsbereitstellung von einer früheren Version von lync Server 2010 auf lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="da386-118">Moving your production deployment from a previous version of Lync Server 2010 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="da386-119">*upgrade*</span><span class="sxs-lookup"><span data-stu-id="da386-119">*upgrade*</span></span>  
    <span data-ttu-id="da386-120">Installieren einer neueren Softwareversion auf einem Server oder Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="da386-120">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="da386-121">*Koexistenz*</span><span class="sxs-lookup"><span data-stu-id="da386-121">*coexistence*</span></span>  
    <span data-ttu-id="da386-122">Die temporäre Umgebung, die während der Migration vorhanden ist, wenn einige Funktionen zu lync Server 2013 migriert wurden und andere Funktionen weiterhin in einer früheren Version von lync Server 2010 verbleiben.</span><span class="sxs-lookup"><span data-stu-id="da386-122">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Lync Server 2010.</span></span>

<!-- end list -->

  - <span data-ttu-id="da386-123">*Interoperabilität*</span><span class="sxs-lookup"><span data-stu-id="da386-123">*interoperability*</span></span>  
    <span data-ttu-id="da386-124">Die Fähigkeit Ihrer Bereitstellung, während der Phase der Koexistenz erfolgreich ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="da386-124">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="da386-125">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="da386-125">In This Section</span></span>

  - [<span data-ttu-id="da386-126">Vorbereiten der Migration</span><span class="sxs-lookup"><span data-stu-id="da386-126">Before you begin the migration</span></span>](before-you-begin-the-migration.md)

  - [<span data-ttu-id="da386-127">Phase 1: Planen der Migration von lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="da386-127">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [<span data-ttu-id="da386-128">Phase 2: Vorbereitung der Migration</span><span class="sxs-lookup"><span data-stu-id="da386-128">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

  - [<span data-ttu-id="da386-129">Phase 3: Bereitstellen lync Server 2013 pilotpools</span><span class="sxs-lookup"><span data-stu-id="da386-129">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="da386-130">Phase 4: verlagern von Testbenutzern in den Pilot Pool</span><span class="sxs-lookup"><span data-stu-id="da386-130">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="da386-131">Phase 5: Hinzufügen von lync Server 2013 Edgeserver zu einem Pilot Pool</span><span class="sxs-lookup"><span data-stu-id="da386-131">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="da386-132">Phase 6: Migration von der Pilotbereitstellung zur Produktionsbereitstellung</span><span class="sxs-lookup"><span data-stu-id="da386-132">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="da386-133">Phase 7: Aufgaben nach der Migration abschließen</span><span class="sxs-lookup"><span data-stu-id="da386-133">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

  - [<span data-ttu-id="da386-134">Phase 8: Außerbetriebsetzen der Legacypools</span><span class="sxs-lookup"><span data-stu-id="da386-134">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

