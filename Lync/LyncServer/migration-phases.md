---
title: Migrationsphasen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa7226a442d8e41d4ab0e6e3511a35e020decb65
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a>Migrationsphasen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-17_

In lync Server 2013 definieren Sie Websites in Ihrem Netzwerk, die lync Server 2013-Komponenten enthalten. Bei einer Website handelt es sich um eine Gruppe von Computern, die durch ein Hochgeschwindigkeits-Netzwerk mit niedriger Latenz gut verbunden sind, beispielsweise ein einzelnes lokales Netzwerk (LAN) oder zwei Netzwerke, die über ein Hochgeschwindigkeits-Fiberoptik-Netzwerk verbunden sind.

Bei einem *Front-End-Pool* handelt es sich um einen Satz von Front-End-Servern, die identisch konfiguriert sind und zusammenarbeiten, um Dienste für eine gemeinsame Gruppe von Benutzern bereitzustellen. Ein Pool bietet ihren Benutzern Skalierbarkeit und Failover-Funktion. Auf allen Servern innerhalb eines Pools muss dieselbe Serverrolle ausgeführt werden. Ein Standard Edition-Server, der für kleine Organisationen entwickelt wurde, definiert auch einen Pool und wird auf einem einzelnen Server ausgeführt. Dies ermöglicht Ihnen, lync Server 2013-Funktionen zu einem niedrigeren Preis zu nutzen, bietet jedoch keine echte Lösung mit hoher Verfügbarkeit.

In den folgenden Phasen wird der Prozess einer Pool Migration von lync Server 2010 zu lync Server 2013 beschrieben. Für mehrere Websites, die mehrere Pools enthalten, sollte jeder einzelne Pool diesem phasenweisen Ansatz folgen.

1.  [Phase 1: Planen der Migration von lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [Phase 2: Vorbereitung der Migration](phase-2-prepare-for-migration.md)

3.  [Phase 3: Bereitstellen des lync Server 2013-pilotpools](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [Phase 4: Verschieben von Testbenutzern in den Pilot Pool](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [Phase 5: Hinzufügen von lync Server 2013 Edge-Server zu Pilot Pool](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [Phase 6: Migration von der Pilotbereitstellung zur Produktionsbereitstellung](phase-6-move-from-pilot-deployment-into-production.md)

7.  [Phase 7: Aufgaben nach der Migration abschließen](phase-7-complete-post-migration-tasks.md)

8.  [Phase 8: Außerbetriebsetzen der Legacypools](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

