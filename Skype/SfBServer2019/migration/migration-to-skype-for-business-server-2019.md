---
title: Migration zu Skype for Business Server 2019
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Die Themen in diesem Abschnitt führen Sie durch den Prozess der Migration zu Skype for Business Server 2019.
ms.openlocfilehash: 51c3be10b90198e1abe24172aa35ab167e871739
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813403"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="5b4bf-103">Migration zu Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="5b4bf-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="5b4bf-104">Die Themen in diesem Abschnitt führen Sie durch den Prozess der Migration zu Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5b4bf-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="5b4bf-105">Dieser Artikel behandelt die Migration von lync Server 2013 oder Skype for Business Server 2015 zu Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5b4bf-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5b4bf-106">Im gesamten Inhalt verwenden wir den Begriff *Legacy* , um auf den Legacy-lync Server 2013 oder Skype for Business Server 2015 zu verweisen, den Sie zu Skype for Business Server 2019 migrieren.</span><span class="sxs-lookup"><span data-stu-id="5b4bf-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5b4bf-107">In diesem Leitfaden werden die Schritte beschrieben, die in der Regel für die einzelnen Migrationsphasen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5b4bf-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="5b4bf-108">Sie bezieht sich nicht auf jede mögliche Legacy Bereitstellungstopologie oder alle möglichen Migrationsszenarien.</span><span class="sxs-lookup"><span data-stu-id="5b4bf-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="5b4bf-109">Daher müssen Sie möglicherweise nicht alle beschriebenen Schritte ausführen, oder Sie müssen abhängig von Ihrer Bereitstellung möglicherweise zusätzliche Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="5b4bf-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="5b4bf-110">Dieses Handbuch enthält auch Beispiele für Überprüfungsschritte.</span><span class="sxs-lookup"><span data-stu-id="5b4bf-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="5b4bf-111">Diese Überprüfungsschritte werden bereitgestellt, um Ihnen zu verdeutlichen, was Sie suchen müssen, um sicherzustellen, dass jede Phase erfolgreich abgeschlossen wird, während Sie Ihre Migration fortführen.</span><span class="sxs-lookup"><span data-stu-id="5b4bf-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="5b4bf-112">Passen Sie diese Überprüfungsschritte an den jeweiligen Migrationsprozess an.</span><span class="sxs-lookup"><span data-stu-id="5b4bf-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="5b4bf-113">Dieses Handbuch enthält Informationen, die speziell für das Upgrade Ihrer vorhandenen Bereitstellung gelten.</span><span class="sxs-lookup"><span data-stu-id="5b4bf-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="5b4bf-114">Es wird nicht erläutert, wie Sie Ihre vorhandene Topologie ändern.</span><span class="sxs-lookup"><span data-stu-id="5b4bf-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="5b4bf-115">In diesem Leitfaden wird die Implementierung neuer Features nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="5b4bf-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="5b4bf-116">Wenn eine detaillierte Prozedur an anderer Stelle dokumentiert wird, werden Sie in diesem Leitfaden zum Artikel-oder Artikel Abschnitt weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="5b4bf-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="5b4bf-117">In diesem Artikel werden die in der folgenden Liste angegebenen Ausdrücke definiert.</span><span class="sxs-lookup"><span data-stu-id="5b4bf-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="5b4bf-118">**Migration:** Verschieben der Produktionsbereitstellung von lync Server 2013 oder Skype for Business Server 2015 auf Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5b4bf-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="5b4bf-119">**Koexistenz:** Die temporäre Umgebung, die während der Migration vorhanden ist, wenn einige Funktionen in Skype for Business Server 2019 migriert wurden und andere Funktionen weiterhin auf einer früheren Version verbleiben.</span><span class="sxs-lookup"><span data-stu-id="5b4bf-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="5b4bf-120">**Interoperabilität:** Die Möglichkeit, dass Ihre Bereitstellung während des Zeitraums der Koexistenz erfolgreich ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="5b4bf-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="5b4bf-121">**Legacy:** Das System, von dem Sie die Migration fortführen, also entweder lync Server 2013 oder Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5b4bf-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="5b4bf-122">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="5b4bf-122">In this section</span></span>

- [<span data-ttu-id="5b4bf-123">Vorbereiten der Migration</span><span class="sxs-lookup"><span data-stu-id="5b4bf-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="5b4bf-124">Phase 1: Planen der Migration</span><span class="sxs-lookup"><span data-stu-id="5b4bf-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="5b4bf-125">Phase 2: Vorbereitung der Migration</span><span class="sxs-lookup"><span data-stu-id="5b4bf-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="5b4bf-126">Phase 3: Bereitstellen des Pilotpools</span><span class="sxs-lookup"><span data-stu-id="5b4bf-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="5b4bf-127">Phase 4: Verschieben von Testbenutzern in den Pilot Pool</span><span class="sxs-lookup"><span data-stu-id="5b4bf-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="5b4bf-128">Phase 5: Hinzufügen von Edgeservern zum Pilotpool</span><span class="sxs-lookup"><span data-stu-id="5b4bf-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="5b4bf-129">Phase 6: Migration von der Pilotbereitstellung zur Produktionsbereitstellung</span><span class="sxs-lookup"><span data-stu-id="5b4bf-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="5b4bf-130">Phase 7: Aufgaben nach der Migration abschließen</span><span class="sxs-lookup"><span data-stu-id="5b4bf-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="5b4bf-131">Phase 8: Außerbetriebsetzen der Legacypools</span><span class="sxs-lookup"><span data-stu-id="5b4bf-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

