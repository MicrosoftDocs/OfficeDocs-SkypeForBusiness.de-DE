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
# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a>Migration von Lync Server 2010 zu Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-17_

Die Themen in diesem Abschnitt führen Sie durch den Migrationsprozess von lync Server 2010 zu lync Server 2013.

<div>


> [!IMPORTANT]  
> In diesem Dokument werden die Schritte beschrieben, die im Allgemeinen zur Durchführung der einzelnen Phasen der Migration erforderlich sind. Es wird darin nicht auf jede mögliche Bereitstellungstopologie der Vorversion oder jedes mögliche Migrationsszenario eingegangen. Deshalb ist es nicht notwendig, dass Sie jeden beschriebenen Schritt ausführen; ggf. müssen Sie auch, abhängig von Ihrer Bereitstellung, zusätzliche Schritte ausführen. Darüber hinaus werden in diesem Dokument auch Beispiele für Überprüfungsschritte aufgeführt. Durch diese Überprüfungsschritte können Sie einfacher erkennen, wie Sie die erfolgreiche Ausführung der einzelnen Phasen der Migration sicherstellen können. Passen Sie diese Überprüfungsschritte an Ihren jeweiligen Migrationsprozess an.



</div>

Dieses Handbuch enthält Informationen, die speziell auf die Aktualisierung Ihrer vorhandenen Bereitstellung eingehen. Die Änderung Ihrer vorhandenen Topologie wird darin nicht behandelt. In diesem Handbuch wird nicht die Implementierung neuer Funktionen behandelt. Dieses Handbuch enthält entsprechende Verweise auf Verfahren, die in anderen Dokumenten detailliert beschrieben sind.

In diesem Dokument werden Begriffe gemäß der Definition in der folgenden Liste verwendet.

  - *Migration*  
    Verschieben der Produktionsbereitstellung von einer früheren Version von lync Server 2010 auf lync Server 2013.

<!-- end list -->

  - *upgrade*  
    Installieren einer neueren Softwareversion auf einem Server oder Clientcomputer.

<!-- end list -->

  - *Koexistenz*  
    Die temporäre Umgebung, die während der Migration vorhanden ist, wenn einige Funktionen zu lync Server 2013 migriert wurden und andere Funktionen weiterhin in einer früheren Version von lync Server 2010 verbleiben.

<!-- end list -->

  - *Interoperabilität*  
    Die Fähigkeit Ihrer Bereitstellung, während der Phase der Koexistenz erfolgreich ausgeführt zu werden.

<div>

## <a name="in-this-section"></a>Inhalt dieses Abschnitts

  - [Vorbereiten der Migration](before-you-begin-the-migration.md)

  - [Phase 1: Planen der Migration von lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [Phase 2: Vorbereitung der Migration](phase-2-prepare-for-migration.md)

  - [Phase 3: Bereitstellen lync Server 2013 pilotpools](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [Phase 4: verlagern von Testbenutzern in den Pilot Pool](phase-4-move-test-users-to-the-pilot-pool.md)

  - [Phase 5: Hinzufügen von lync Server 2013 Edgeserver zu einem Pilot Pool](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Phase 6: Migration von der Pilotbereitstellung zur Produktionsbereitstellung](phase-6-move-from-pilot-deployment-into-production.md)

  - [Phase 7: Aufgaben nach der Migration abschließen](phase-7-complete-post-migration-tasks.md)

  - [Phase 8: Außerbetriebsetzen der Legacypools](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

