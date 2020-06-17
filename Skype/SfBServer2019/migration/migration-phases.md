---
title: Migrationsphasen
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: In Skype for Business Server 2019 definieren Sie Websites in Ihrem Netzwerk, die Skype for Business Server 2019-Komponenten enthalten. Bei einer Website handelt es sich um eine Gruppe von Computern, die über ein Hochgeschwindigkeitsnetzwerk mit niedriger Latenz gut verbunden sind, beispielsweise ein einzelnes lokales Netzwerk (LAN) oder zwei Netzwerke, die über ein Hochgeschwindigkeits-Fiberoptik Netz verbunden sind.
ms.openlocfilehash: d05fc0c4eb7d12a6d96b638fe7f59acc830fbcd1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752627"
---
# <a name="migration-phases"></a>Migrationsphasen

In Skype for Business Server 2019 definieren Sie Websites in Ihrem Netzwerk, die Skype for Business Server 2019-Komponenten enthalten. Bei einer Website handelt es sich um eine Gruppe von Computern, die über ein Hochgeschwindigkeitsnetzwerk mit niedriger Latenz gut verbunden sind, beispielsweise ein einzelnes lokales Netzwerk (LAN) oder zwei Netzwerke, die über ein Hochgeschwindigkeits-Fiberoptik Netz verbunden sind. 
  
Ein Front-End-Pool ist eine Gruppe von Front-End-Servern, die identisch konfiguriert sind und zusammenarbeiten, um Dienste für eine gemeinsame Gruppe von Benutzern bereitzustellen. Ein Pool bietet Skalierbarkeit und Failoverfunktionen für Benutzer. Auf allen Servern innerhalb eines Pools muss dieselbe Serverrolle ausgeführt werden. Eine Standard Edition-Server, die für kleine Organisationen entwickelt wurde, definiert auch einen Pool und wird auf einem einzelnen Server ausgeführt. Auf diese Weise können Sie Skype for Business Server 2019-Funktionalität zu geringeren Kosten Nutzen, jedoch keine echte Hochverfügbarkeitslösung anbieten. 
  
In den folgenden Phasen wird der Prozess einer Pool Migration zu Skype for Business Server 2019 beschrieben. Bei mehreren Standorten, die mehrere Pools enthalten, sollte jeder einzelne Pool diesen phasenweisen Ansatz durchlaufen.
  
1. [Phase 1: Planen der Migration](phase-1-plan-your-migration.md)
    
2. [Phase 2: Vorbereitung der Migration](phase-2-prepare-for-migration.md)
    
3. [Phase 3: Bereitstellen des pilotpools für Skype for Business Server 2019](phase-3-deploy-pilot-pool.md)
    
4. [Phase 4: verlagern von Testbenutzern in den Pilot Pool](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [Phase 5: Hinzufügen von Skype for Business Server 2019 Edgeserver zu einem Pilot Pool](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [Phase 6: Migration von der Pilotbereitstellung zur Produktionsbereitstellung](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [Phase 7: Aufgaben nach der Migration abschließen](phase-7-complete-post-migration-tasks.md)
    
8. [Phase 8: Außerbetriebsetzen der Legacypools](phase-8-decommission-legacy-pools.md)
    

