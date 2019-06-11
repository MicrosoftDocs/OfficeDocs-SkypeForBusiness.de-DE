---
title: Migration von Lync Server 2010 zu Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4be42da09e14f91d82310258c728de4ed7976be2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a><span data-ttu-id="78a14-102">Migration von Lync Server 2010 zu Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78a14-102">Migration from Lync Server 2010 to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78a14-103">_**Letztes Änderungsdatum des Themas:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="78a14-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="78a14-104">Die Themen in diesem Abschnitt führen Sie durch den Vorgang der Migration von lync Server 2010 zu lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="78a14-104">The topics in this section guide you through the process of migrating from Lync Server 2010 to Lync Server 2013.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="78a14-105">In diesem Dokument werden die Schritte beschrieben, die in der Regel für die einzelnen Migrationsphasen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="78a14-105">This document describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="78a14-106">Sie bezieht sich nicht auf jede mögliche Legacy Bereitstellungstopologie oder alle möglichen Migrationsszenarien.</span><span class="sxs-lookup"><span data-stu-id="78a14-106">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="78a14-107">Daher müssen Sie möglicherweise nicht alle beschriebenen Schritte ausführen, oder Sie müssen abhängig von Ihrer Bereitstellung möglicherweise zusätzliche Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="78a14-107">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="78a14-108">Dieses Dokument enthält auch Beispiele für Überprüfungsschritte.</span><span class="sxs-lookup"><span data-stu-id="78a14-108">This document also provides examples of verification steps.</span></span> <span data-ttu-id="78a14-109">Diese Überprüfungsschritte werden bereitgestellt, um Ihnen zu verdeutlichen, was Sie suchen müssen, um sicherzustellen, dass jede Phase erfolgreich abgeschlossen wird, während Sie Ihre Migration fortführen.</span><span class="sxs-lookup"><span data-stu-id="78a14-109">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="78a14-110">Passen Sie diese Überprüfungsschritte an den jeweiligen Migrationsprozess an.</span><span class="sxs-lookup"><span data-stu-id="78a14-110">Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="78a14-111">Dieses Handbuch enthält Informationen, die speziell für das Upgrade Ihrer vorhandenen Bereitstellung gelten.</span><span class="sxs-lookup"><span data-stu-id="78a14-111">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="78a14-112">Es wird nicht erläutert, wie Sie Ihre vorhandene Topologie ändern.</span><span class="sxs-lookup"><span data-stu-id="78a14-112">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="78a14-113">In diesem Leitfaden wird die Implementierung neuer Features nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="78a14-113">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="78a14-114">Wenn eine detaillierte Prozedur an anderer Stelle dokumentiert wird, werden Sie in diesem Leitfaden zu dem entsprechenden Dokument-oder Dokumentabschnitt weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="78a14-114">When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="78a14-115">In diesem Dokument werden die in der folgenden Liste angegebenen Ausdrücke definiert.</span><span class="sxs-lookup"><span data-stu-id="78a14-115">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="78a14-116">*Migrations*</span><span class="sxs-lookup"><span data-stu-id="78a14-116">*migration*</span></span>  
    <span data-ttu-id="78a14-117">Verschieben der Produktionsbereitstellung aus einer früheren Version von lync Server 2010 auf lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78a14-117">Moving your production deployment from a previous version of Lync Server 2010 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="78a14-118">*Upgrade*</span><span class="sxs-lookup"><span data-stu-id="78a14-118">*upgrade*</span></span>  
    <span data-ttu-id="78a14-119">Installieren einer neueren Software Version auf einem Server oder Clientcomputer</span><span class="sxs-lookup"><span data-stu-id="78a14-119">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="78a14-120">*Koexistenz*</span><span class="sxs-lookup"><span data-stu-id="78a14-120">*coexistence*</span></span>  
    <span data-ttu-id="78a14-121">Die temporäre Umgebung, die während der Migration vorhanden ist, wenn einige Funktionen zu lync Server 2013 migriert wurden und andere Funktionen weiterhin in einer früheren Version von lync Server 2010 verbleiben.</span><span class="sxs-lookup"><span data-stu-id="78a14-121">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Lync Server 2010.</span></span>

<!-- end list -->

  - <span data-ttu-id="78a14-122">*Interoperabilität*</span><span class="sxs-lookup"><span data-stu-id="78a14-122">*interoperability*</span></span>  
    <span data-ttu-id="78a14-123">Die Möglichkeit, dass Ihre Bereitstellung während des Zeitraums der Koexistenz erfolgreich ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="78a14-123">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="78a14-124">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="78a14-124">In This Section</span></span>

  - [<span data-ttu-id="78a14-125">Vorbereiten der Migration</span><span class="sxs-lookup"><span data-stu-id="78a14-125">Before you begin the migration</span></span>](before-you-begin-the-migration.md)

  - [<span data-ttu-id="78a14-126">Phase 1: Planen der Migration von lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="78a14-126">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [<span data-ttu-id="78a14-127">Phase 2: Vorbereitung der Migration</span><span class="sxs-lookup"><span data-stu-id="78a14-127">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

  - [<span data-ttu-id="78a14-128">Phase 3: Bereitstellen des lync Server 2013-pilotpools</span><span class="sxs-lookup"><span data-stu-id="78a14-128">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="78a14-129">Phase 4: Verschieben von Testbenutzern in den Pilot Pool</span><span class="sxs-lookup"><span data-stu-id="78a14-129">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="78a14-130">Phase 5: Hinzufügen von lync Server 2013 Edge-Server zu Pilot Pool</span><span class="sxs-lookup"><span data-stu-id="78a14-130">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="78a14-131">Phase 6: Migration von der Pilotbereitstellung zur Produktionsbereitstellung</span><span class="sxs-lookup"><span data-stu-id="78a14-131">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="78a14-132">Phase 7: Aufgaben nach der Migration abschließen</span><span class="sxs-lookup"><span data-stu-id="78a14-132">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

  - [<span data-ttu-id="78a14-133">Phase 8: Außerbetriebsetzen der Legacypools</span><span class="sxs-lookup"><span data-stu-id="78a14-133">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

