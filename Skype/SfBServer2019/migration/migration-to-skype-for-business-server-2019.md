---
title: Migration zu Skype für Business Server 2019
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In den Themen in diesem Abschnitt begleiten Sie bei der Migration zu Skype für Business Server 2019.
ms.openlocfilehash: 32babd6fedd5defc756f73bbf001716c7c0b8a72
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231609"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="e6a0b-103">Migration zu Skype für Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="e6a0b-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="e6a0b-104">In den Themen in diesem Abschnitt begleiten Sie bei der Migration zu Skype für Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e6a0b-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="e6a0b-105">Dieser Artikel behandelt Migrieren von Lync Server 2013 oder Skype für Business Server 2015 zu Skype für Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e6a0b-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6a0b-106">Im gesamten Inhalt verwenden wir den Begriff *legacy* auf der Vorgängerversion Lync Server 2013 oder Skype für Business Server 2015 verweisen möchten, die Sie zu Skype für Business Server 2019 migrieren.</span><span class="sxs-lookup"><span data-stu-id="e6a0b-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e6a0b-107">Dieses Handbuch beschreibt die Schritte im Allgemeinen erforderlich, um die einzelnen Phasen der Migration zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="e6a0b-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="e6a0b-108">Es werden nicht alle möglichen legacy Bereitstellungstopologie oder jede mögliche Migrationsszenario behandelt.</span><span class="sxs-lookup"><span data-stu-id="e6a0b-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="e6a0b-109">Aus diesem Grund möglicherweise nicht müssen Sie jeden Schritt beschrieben ausführen, oder Sie müssen zusätzliche Schritte, abhängig von Ihrer Bereitstellung ausführen.</span><span class="sxs-lookup"><span data-stu-id="e6a0b-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="e6a0b-110">Dieses Handbuch enthält auch Beispiele Überprüfungsschritte.</span><span class="sxs-lookup"><span data-stu-id="e6a0b-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="e6a0b-111">Diese Schritte werden bereitgestellt, um Ihnen zu verdeutlichen, was Sie benötigen, um sicherzustellen, dass die, die jeder Phase als Bearbeitung über die Migration erfolgreich abgeschlossen wird gesucht.</span><span class="sxs-lookup"><span data-stu-id="e6a0b-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="e6a0b-112">Passen Sie diese Schritte für Ihre spezifische Migrationsprozess.</span><span class="sxs-lookup"><span data-stu-id="e6a0b-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="e6a0b-113">Dieses Handbuch enthält Informationen, die speziell für Ihre vorhandene Bereitstellung aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e6a0b-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="e6a0b-114">Es wird nicht zum Ändern Ihrer vorhandenen Topologie erläutert.</span><span class="sxs-lookup"><span data-stu-id="e6a0b-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="e6a0b-115">Die Implementierung der neuen Features behandelt in diesem Handbuch nicht.</span><span class="sxs-lookup"><span data-stu-id="e6a0b-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="e6a0b-116">Wenn Sie eine detaillierte Vorgehensweise detailliert beschrieben sind, weist Sie dieses Handbuch zum Artikel oder Artikel-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="e6a0b-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="e6a0b-117">In diesem Artikel werden Begriffe definiert, wie in der folgenden Liste angegeben.</span><span class="sxs-lookup"><span data-stu-id="e6a0b-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="e6a0b-118">**Migration:** Verschieben der produktionsbereitstellung von Lync Server 2013 oder Skype für Business Server 2015 zu Skype für Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e6a0b-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="e6a0b-119">**Koexistenz:** Die temporäre Umgebung, die während der Migration vorhanden ist, wenn einige Funktionen zu Skype für Business Server 2019 und andere Funktionen migriert wurde, ist weiterhin auf einer früheren Version.</span><span class="sxs-lookup"><span data-stu-id="e6a0b-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="e6a0b-120">**Interoperabilität:** Die Fähigkeit Ihrer Bereitstellung während der Phase der Koexistenz erfolgreich ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e6a0b-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="e6a0b-121">**legacy:** Das System schrittargumente, migrieren Sie die Lync Server 2013 oder Skype für Business Server 2015 ist.</span><span class="sxs-lookup"><span data-stu-id="e6a0b-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="e6a0b-122">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="e6a0b-122">In this section</span></span>

- [<span data-ttu-id="e6a0b-123">Vorbereiten der Migration</span><span class="sxs-lookup"><span data-stu-id="e6a0b-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="e6a0b-124">Phase 1: Planen der Migration</span><span class="sxs-lookup"><span data-stu-id="e6a0b-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="e6a0b-125">Phase 2: Vorbereitung der Migration</span><span class="sxs-lookup"><span data-stu-id="e6a0b-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="e6a0b-126">Phase 3: Bereitstellen des Pilotpools</span><span class="sxs-lookup"><span data-stu-id="e6a0b-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="e6a0b-127">Phase 4: Verschieben von Testbenutzern in den pilotpool</span><span class="sxs-lookup"><span data-stu-id="e6a0b-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="e6a0b-128">Phase 5: Hinzufügen von Edgeservern zum Pilotpool</span><span class="sxs-lookup"><span data-stu-id="e6a0b-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="e6a0b-129">Phase 6: Migration von der Pilotbereitstellung zur Produktionsbereitstellung</span><span class="sxs-lookup"><span data-stu-id="e6a0b-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="e6a0b-130">Phase 7: Aufgaben nach der Migration abschließen</span><span class="sxs-lookup"><span data-stu-id="e6a0b-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="e6a0b-131">Phase 8: Außerbetriebsetzen der Legacypools</span><span class="sxs-lookup"><span data-stu-id="e6a0b-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

