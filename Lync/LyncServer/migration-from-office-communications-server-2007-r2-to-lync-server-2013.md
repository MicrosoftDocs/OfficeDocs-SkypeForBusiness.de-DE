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
ms.openlocfilehash: 39aef26271594ed57d113bed4c3bb3702df41fac
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a>Migration von Office Communications Server 2007 R2 zu lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-19_

Die Themen in diesem Abschnitt führen Sie durch den Migrationsprozess von Office Communications Server 2007 R2 zu lync Server 2013

<div>


> [!IMPORTANT]  
> In diesem Dokument werden die Schritte beschrieben, die im Allgemeinen zur Durchführung der einzelnen Phasen der Migration erforderlich sind. Es wird darin nicht auf jede mögliche Bereitstellungstopologie der Vorversion oder jedes mögliche Migrationsszenario eingegangen. Deshalb ist es nicht notwendig, dass Sie jeden beschriebenen Schritt ausführen; ggf. müssen Sie auch, abhängig von Ihrer Bereitstellung, zusätzliche Schritte ausführen. Darüber hinaus werden in diesem Dokument auch Beispiele für Überprüfungsschritte aufgeführt. Durch diese Überprüfungsschritte können Sie einfacher erkennen, wie Sie die erfolgreiche Ausführung der einzelnen Phasen der Migration sicherstellen können. Passen Sie diese Überprüfungsschritte an Ihren jeweiligen Migrationsprozess an.



</div>

Dieses Handbuch enthält Informationen, die speziell auf die Aktualisierung Ihrer vorhandenen Bereitstellung eingehen. Die Änderung Ihrer vorhandenen Topologie wird darin nicht behandelt. In diesem Handbuch wird nicht die Implementierung neuer Funktionen behandelt. Dieses Handbuch enthält entsprechende Verweise auf Verfahren, die in anderen Dokumenten detailliert beschrieben sind.

In diesem Dokument werden Begriffe gemäß der Definition in der folgenden Liste verwendet.

  - *Migration*  
    Verschieben der Produktionsbereitstellung von einer früheren Version von Office Communications Server 2007 R2 auf lync Server 2013.

<!-- end list -->

  - *upgrade*  
    Installieren einer neueren Softwareversion auf einem Server oder Clientcomputer.

<!-- end list -->

  - *Koexistenz*  
    Die temporäre Umgebung, die während der Migration vorhanden ist, wenn einige Funktionen zu lync Server 2013 migriert wurden und andere Funktionen weiterhin in einer früheren Version von Office Communications Server 2007 R2 verbleiben.

<!-- end list -->

  - *Interoperabilität*  
    Die Fähigkeit Ihrer Bereitstellung, während der Phase der Koexistenz erfolgreich ausgeführt zu werden.

<div>

## <a name="in-this-section"></a>Inhalt dieses Abschnitts

  - [Bevor Sie mit der Migration beginnen](before-you-begin-the-migration_1.md)

  - [Migrationsphasen](migration-phases_1.md)

  - [Phase 1: Planen der Migration von Office Communications Server 2007 R2](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [Phase 2: Vorbereiten der Migration](phase-2-prepare-for-migration_1.md)

  - [Phase 3: Bereitstellen lync Server 2013 pilotpools](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [Phase 4: Zusammenführen von Topologien](phase-4-merge-topologies.md)

  - [Phase 5: Konfigurieren des pilotpools](phase-5-configure-the-pilot-pool.md)

  - [Phase 6: Migrieren von Benutzern zum Pilot Pool](phase-6-move-users-to-the-pilot-pool.md)

  - [Phase 7: Hinzufügen von lync Server 2013 Edgeserver zu einem Pilot Pool](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Phase 8: Umsteigen von der Pilotbereitstellung in die Produktion](phase-8-move-from-pilot-deployment-into-production.md)

  - [Phase 9: Ausführen von Aufgaben nach der Migration](phase-9-complete-post-migration-tasks.md)

  - [Phase 10: decommission Legacy Site](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

