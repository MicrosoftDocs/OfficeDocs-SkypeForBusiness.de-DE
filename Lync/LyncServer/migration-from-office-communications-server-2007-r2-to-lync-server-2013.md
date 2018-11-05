---
title: Migration von Office Communications Server 2007 R2 zu Lync Server 2013
TOCTitle: Migration von Office Communications Server 2007 R2 zu Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205375(v=OCS.15)
ms:contentKeyID: 49295894
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration von Office Communications Server 2007 R2 zu Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

In den Themen in diesem Abschnitt finden Sie Anleitungen zum Migrieren von Office Communications Server 2007 R2 zu Lync Server 2013.


> [!IMPORTANT]
> In diesem Dokument werden die Schritte beschrieben, die im Allgemeinen zur Durchführung der einzelnen Phasen der Migration erforderlich sind. Es wird darin nicht auf jede mögliche Bereitstellungstopologie der Vorversion oder jedes mögliche Migrationsszenario eingegangen. Deshalb ist es nicht notwendig, dass Sie jeden beschriebenen Schritt ausführen; ggf. müssen Sie auch, abhängig von Ihrer Bereitstellung, zusätzliche Schritte ausführen. Darüber hinaus werden in diesem Dokument auch Beispiele für Überprüfungsschritte aufgeführt. Durch diese Überprüfungsschritte können Sie einfacher erkennen, wie Sie die erfolgreiche Ausführung der einzelnen Phasen der Migration sicherstellen können. Passen Sie diese Überprüfungsschritte an Ihren jeweiligen Migrationsprozess an.



Dieses Handbuch enthält Informationen, die speziell auf die Aktualisierung Ihrer vorhandenen Bereitstellung eingehen. Die Änderung Ihrer vorhandenen Topologie wird darin nicht behandelt. In diesem Handbuch wird nicht die Implementierung neuer Funktionen behandelt. Dieses Handbuch enthält entsprechende Verweise auf Verfahren, die in anderen Dokumenten detailliert beschrieben sind.

In diesem Dokument werden Begriffe gemäß der Definition in der folgenden Liste verwendet.

  - *Migration*   
    Verschieben der Produktionsbereitstellung aus einer Vorgängerversion von Office Communications Server 2007 R2 zu Lync Server 2013.

<!-- end list -->

  - *Upgrade*   
    Installieren einer neueren Softwareversion auf einem Server oder Clientcomputer.

<!-- end list -->

  - *Koexistenz*   
    Die temporäre Umgebung während der Migration, wenn einige Funktionen zu Lync Server 2013 migriert wurden, während andere Funktionen noch von einer Vorversion von Office Communications Server 2007 R2 bereitgestellt werden.

<!-- end list -->

  - *Interoperabilität*   
    Die Fähigkeit Ihrer Bereitstellung, während der Phase der Koexistenz erfolgreich ausgeführt zu werden.

## In diesem Abschnitt

  - [Vorbereiten der Migration](before-you-begin-the-migration_1.md)

  - [Migrationsphasen](migration-phases_1.md)

  - [Phase 1: Planen der Migration von Office Communications Server 2007 R2](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [Phase 2: Vorbereiten der Migration](phase-2-prepare-for-migration_1.md)

  - [Phase 3: Bereitstellen des Lync Server 2013-Pilotpools](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [Phase 4: Zusammenführen von Topologien](phase-4-merge-topologies.md)

  - [Phase 5: Konfigurieren des Pilotpools](phase-5-configure-the-pilot-pool.md)

  - [Phase 6: Verschieben von Benutzern in den Pilotpool](phase-6-move-users-to-the-pilot-pool.md)

  - [Phase 7: Hinzufügen des Lync Server 2013-Edgeservers zum Pilotpool](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Phase 8: Migration von der Pilotbereitstellung zur Produktionsbereitstellung](phase-8-move-from-pilot-deployment-into-production.md)

  - [Phase 9: Ausführen von Aufgaben nach der Migration](phase-9-complete-post-migration-tasks.md)

  - [Phase 10: Außerbetriebnahme des Vorversionsstandorts](phase-10-decommission-legacy-site.md)

