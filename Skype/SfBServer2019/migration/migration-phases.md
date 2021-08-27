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
ms.localizationpriority: medium
description: In Skype for Business Server 2019 definieren Sie Standorte in Ihrem Netzwerk, die Skype for Business Server 2019-Komponenten enthalten. Ein Standort ist eine Gruppe von Computern, die über ein Netzwerk mit hoher Geschwindigkeit und geringer Latenz gut verbunden sind, z. B. ein einzelnes Lan (Local Area Network) oder zwei Netzwerke, die über ein Hochgeschwindigkeit-Glasfasernetzwerk verbunden sind.
ms.openlocfilehash: 8066e9ed7e46c54e6a6eac89bcf65dca1447aa57
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587987"
---
# <a name="migration-phases"></a>Migrationsphasen

In Skype for Business Server 2019 definieren Sie Standorte in Ihrem Netzwerk, die Skype for Business Server 2019-Komponenten enthalten. Ein Standort ist eine Gruppe von Computern, die über ein Netzwerk mit hoher Geschwindigkeit und geringer Latenz gut verbunden sind, z. B. ein einzelnes Lan (Local Area Network) oder zwei Netzwerke, die über ein Hochgeschwindigkeit-Glasfasernetzwerk verbunden sind. 
  
Ein Front-End-Pool ist eine Gruppe von Front-End-Servern, die identisch konfiguriert sind und zusammenarbeiten, um Dienste für eine gemeinsame Gruppe von Benutzern bereitzustellen. Ein Pool bietet Skalierbarkeit und Failoverfunktionen für Benutzer. Auf allen Servern innerhalb eines Pools muss dieselbe Serverrolle ausgeführt werden. Ein Standard Edition-Server, der für kleine Organisationen entwickelt wurde, definiert auch einen Pool und wird auf einem einzelnen Server ausgeführt. Auf diese Weise können Sie Skype for Business Server 2019-Funktionalität für geringere Kosten verwenden, bietet jedoch keine echte Hochverfügbarkeitslösung. 
  
In den folgenden Phasen wird der Prozess einer Poolmigration zu Skype for Business Server 2019 beschrieben. Bei mehreren Standorten, die mehrere Pools enthalten, sollte jeder einzelne Pool diesen phasenweisen Ansatz durchlaufen.
  
1. [Phase 1: Planen der Migration](phase-1-plan-your-migration.md)
    
2. [Phase 2: Vorbereitung der Migration](phase-2-prepare-for-migration.md)
    
3. [Phase 3: Bereitstellen Skype for Business Server 2019-Pilotpools](phase-3-deploy-pilot-pool.md)
    
4. [Phase 4: Verschieben von Testbenutzern in den Pilotpool](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [Phase 5: Hinzufügen Skype for Business Server 2019-Edgeservers zum Pilotpool](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [Phase 6: Migration von der Pilotbereitstellung zur Produktionsbereitstellung](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [Phase 7: Aufgaben nach der Migration abschließen](phase-7-complete-post-migration-tasks.md)
    
8. [Phase 8: Außerbetriebsetzen der Legacypools](phase-8-decommission-legacy-pools.md)
    

