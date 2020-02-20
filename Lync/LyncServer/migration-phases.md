---
title: Migrationsphasen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e877afc67e5dea1bc2feada22e5bbbbe81e15139
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a>Migrationsphasen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-17_

In lync Server 2013 definieren Sie Websites in Ihrem Netzwerk, die lync Server 2013 Komponenten enthalten. Bei einer Website handelt es sich um eine Gruppe von Computern, die über ein Hochgeschwindigkeitsnetzwerk mit niedriger Latenz gut verbunden sind, beispielsweise ein einzelnes lokales Netzwerk (LAN) oder zwei Netzwerke, die über ein Hochgeschwindigkeits-Fiberoptik Netz verbunden sind.

Ein *Front-End-Pool* ist eine Gruppe von Front-End-Servern, die identisch konfiguriert sind und zusammenarbeiten, um Dienste für eine gemeinsame Gruppe von Benutzern bereitzustellen. Ein Pool bietet Skalierbarkeit und Failoverfunktionen für Benutzer. Auf allen Servern innerhalb eines Pools muss dieselbe Serverrolle ausgeführt werden. Eine Standard Edition-Server, die für kleine Organisationen entwickelt wurde, definiert auch einen Pool und wird auf einem einzelnen Server ausgeführt. Auf diese Weise können Sie lync Server 2013 Funktionalität zu geringeren Kosten Nutzen, jedoch keine echte Hochverfügbarkeitslösung anbieten.

In den folgenden Phasen wird der Prozess einer Pool Migration von lync Server 2010 auf lync Server 2013 beschrieben. Bei mehreren Standorten, die mehrere Pools enthalten, sollte jeder einzelne Pool diesen phasenweisen Ansatz durchlaufen.

1.  [Phase 1: Planen der Migration von lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [Phase 2: Vorbereiten der Migration](phase-2-prepare-for-migration.md)

3.  [Phase 3: Bereitstellen lync Server 2013 pilotpools](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [Phase 4: verlagern von Testbenutzern in den Pilot Pool](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [Phase 5: Hinzufügen von lync Server 2013 Edgeserver zu einem Pilot Pool](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [Phase 6: Umsteigen von der Pilotbereitstellung in die Produktion](phase-6-move-from-pilot-deployment-into-production.md)

7.  [Phase 7: Ausführen von Aufgaben nach der Migration](phase-7-complete-post-migration-tasks.md)

8.  [Phase 8: Außerbetriebnahme von Legacy Pools](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

