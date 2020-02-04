---
title: Migration von Office Communications Server 2007 R2 zu Lync Server 2013
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
ms.openlocfilehash: e32d43e8052de454647cd9f69b4572d178a0cecb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a>Migration von Office Communications Server 2007 R2 zu Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Die Themen in diesem Abschnitt führen Sie durch den Prozess der Migration von Office Communications Server 2007 R2 zu lync Server 2013.

<div>


> [!IMPORTANT]  
> In diesem Dokument werden die Schritte beschrieben, die in der Regel für die einzelnen Migrationsphasen erforderlich sind. Sie bezieht sich nicht auf jede mögliche Legacy Bereitstellungstopologie oder alle möglichen Migrationsszenarien. Daher müssen Sie möglicherweise nicht alle beschriebenen Schritte ausführen, oder Sie müssen abhängig von Ihrer Bereitstellung möglicherweise zusätzliche Schritte ausführen. Dieses Dokument enthält auch Beispiele für Überprüfungsschritte. Diese Überprüfungsschritte werden bereitgestellt, um Ihnen zu verdeutlichen, was Sie suchen müssen, um sicherzustellen, dass jede Phase erfolgreich abgeschlossen wird, während Sie Ihre Migration fortführen. Passen Sie diese Überprüfungsschritte an den jeweiligen Migrationsprozess an.



</div>

Dieses Handbuch enthält Informationen, die speziell für das Upgrade Ihrer vorhandenen Bereitstellung gelten. Es wird nicht erläutert, wie Sie Ihre vorhandene Topologie ändern. In diesem Leitfaden wird die Implementierung neuer Features nicht behandelt. Wenn eine detaillierte Prozedur an anderer Stelle dokumentiert wird, werden Sie in diesem Leitfaden zu dem entsprechenden Dokument-oder Dokumentabschnitt weitergeleitet.

In diesem Dokument werden die in der folgenden Liste angegebenen Ausdrücke definiert.

  - *Migrations*  
    Verschieben der Produktionsbereitstellung aus einer früheren Version von Office Communications Server 2007 R2 auf lync Server 2013

<!-- end list -->

  - *Upgrade*  
    Installieren einer neueren Software Version auf einem Server oder Clientcomputer

<!-- end list -->

  - *Koexistenz*  
    Die temporäre Umgebung, die während der Migration vorhanden ist, wenn einige Funktionen zu lync Server 2013 migriert wurden und andere Funktionen weiterhin auf einer früheren Version von Office Communications Server 2007 R2 verbleiben.

<!-- end list -->

  - *Interoperabilität*  
    Die Möglichkeit, dass Ihre Bereitstellung während des Zeitraums der Koexistenz erfolgreich ausgeführt werden kann.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Vorbereiten der Migration](before-you-begin-the-migration_1.md)

  - [Migrationsphasen](migration-phases_1.md)

  - [Phase 1: Planen der Migration von Office Communications Server 2007 R2](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [Phase 2: Vorbereitung der Migration](phase-2-prepare-for-migration_1.md)

  - [Phase 3: Bereitstellen des lync Server 2013-pilotpools](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [Phase 4: Zusammenführen von Topologien](phase-4-merge-topologies.md)

  - [Phase 5: Konfigurieren des pilotpools](phase-5-configure-the-pilot-pool.md)

  - [Phase 6: Verschieben von Benutzern in den Pilot Pool](phase-6-move-users-to-the-pilot-pool.md)

  - [Phase 7: Hinzufügen von lync Server 2013 Edge-Server zu Pilot Pool](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Phase 8: Wechseln von der Pilotbereitstellung in die Produktionsumgebung](phase-8-move-from-pilot-deployment-into-production.md)

  - [Phase 9: Ausführen von Aufgaben nach der Migration](phase-9-complete-post-migration-tasks.md)

  - [Phase 10: Legacy Website der decommission](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

