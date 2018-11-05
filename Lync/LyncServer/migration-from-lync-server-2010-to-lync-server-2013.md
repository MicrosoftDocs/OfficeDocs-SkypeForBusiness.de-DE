---
title: Migration von Lync Server 2010 zu Lync Server 2013
TOCTitle: Migration von Lync Server 2010 zu Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205369(v=OCS.15)
ms:contentKeyID: 49295838
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration von Lync Server 2010 zu Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-17_

Die Themen in diesem Abschnitt begleiten Sie bei der Migration von Lync Server 2010 zu Lync Server 2013.


> [!IMPORTANT]
> In diesem Dokument werden die Schritte beschrieben, die im Allgemeinen zur Durchführung der einzelnen Phasen der Migration erforderlich sind. Es wird darin nicht auf jede mögliche Bereitstellungstopologie der Vorversion oder jedes mögliche Migrationsszenario eingegangen. Deshalb ist es nicht notwendig, dass Sie jeden beschriebenen Schritt ausführen; ggf. müssen Sie auch, abhängig von Ihrer Bereitstellung, zusätzliche Schritte ausführen. Darüber hinaus werden in diesem Dokument auch Beispiele für Überprüfungsschritte aufgeführt. Durch diese Überprüfungsschritte können Sie einfacher erkennen, wie Sie die erfolgreiche Ausführung der einzelnen Phasen der Migration sicherstellen können. Passen Sie diese Überprüfungsschritte an Ihren jeweiligen Migrationsprozess an.



Dieses Handbuch enthält Informationen, die speziell auf die Aktualisierung Ihrer vorhandenen Bereitstellung eingehen. Die Änderung Ihrer vorhandenen Topologie wird darin nicht behandelt. In diesem Handbuch wird nicht die Implementierung neuer Funktionen behandelt. Dieses Handbuch enthält entsprechende Verweise auf Verfahren, die in anderen Dokumenten detailliert beschrieben sind.

In diesem Dokument werden Begriffe gemäß der Definition in der folgenden Liste verwendet.

  - *Migration*   
    Verschieben der Produktionsbereitstellung aus einer Vorgängerversion von Lync Server 2010 zu Lync Server 2013.

<!-- end list -->

  - *Upgrade*   
    Installieren einer neueren Softwareversion auf einem Server oder Clientcomputer.

<!-- end list -->

  - *Koexistenz*   
    Die temporäre Umgebung während der Migration, wenn einige Funktionen zu Lync Server 2013 migriert wurden, während andere Funktionen noch von einer Vorversion von Lync Server 2010 bereitgestellt werden.

<!-- end list -->

  - *Interoperabilität*   
    Die Fähigkeit Ihrer Bereitstellung, während der Phase der Koexistenz erfolgreich ausgeführt zu werden.

## In diesem Abschnitt

  - [Vorbereiten der Migration](before-you-begin-the-migration.md)

  - [Phase 1: Planen der Migration von Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [Phase 2: Vorbereiten der Migration](phase-2-prepare-for-migration.md)

  - [Phase 3: Bereitstellen des Lync Server 2013-Pilotpools](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [Phase 4: Verschieben von Testbenutzern in den Pilotpool](phase-4-move-test-users-to-the-pilot-pool.md)

  - [Phase 5: Hinzufügen des Lync Server 2013-Edgeservers zum Pilotpool](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Phase 6: Migration von der Pilotbereitstellung zur Produktionsbereitstellung](phase-6-move-from-pilot-deployment-into-production.md)

  - [Phase 7: Ausführen von Aufgaben nach der Migration](phase-7-complete-post-migration-tasks.md)

  - [Phase 8: Außerbetriebsetzen der Legacypools](phase-8-decommission-legacy-pools.md)

