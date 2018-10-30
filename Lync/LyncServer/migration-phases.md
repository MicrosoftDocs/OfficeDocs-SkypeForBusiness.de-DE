---
title: Migrationsphasen
TOCTitle: Migrationsphasen
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205336(v=OCS.15)
ms:contentKeyID: 49295418
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrationsphasen

 

_**Letztes Änderungsdatum des Themas:** 2012-09-17_

In Lync Server 2013 werden Standorte in Ihrem Netzwerk definiert, die Lync Server 2013-Komponenten umfassen. Bei einem Standort handelt es sich um eine Gruppe von Computern, die durch ein Hochgeschwindigkeitsnetzwerk mit niedriger Latenz miteinander verbunden sind, beispielsweise durch ein einziges lokales Netzwerk (Local Area Network, LAN) oder zwei Netzwerke, die über ein Hochgeschwindigkeits-Glasfasernetzwerk verbunden sind.

Bei einem *Front-End-Pool* handelt es sich um eine Gruppe von Front-End-Servern mit identischer Konfiguration, die gemeinsam zur Bereitstellung von Diensten für eine gemeinsame Benutzergruppe eingesetzt werden. Ein Pool bietet Skalierbarkeit und Failoverfunktionen für Benutzer. Auf allen Servern innerhalb eines Pools muss dieselbe Serverrolle ausgeführt werden. Ein Standard Edition-Server, entwickelt für kleine Organisationen, definiert auch einen Pool und wird auf einem einzelnen Server ausgeführt. Sie haben so die Möglichkeit Lync Server 2013-Funktionen zu einem deutlich geringeren Preis zu nutzen, erhalten jedoch keine wirklich hochverfügbare Lösung.

In den folgenden Phasen wird der Vorgang der Migration eines Pools von Lync Server 2010 zu Lync Server 2013 beschrieben. Bei mehreren Standorten, die mehrere Pools enthalten, sollte jeder einzelne Pool diesen phasenweisen Ansatz durchlaufen.

1.  [Phase 1: Planen der Migration von Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [Phase 2: Vorbereiten der Migration](phase-2-prepare-for-migration.md)

3.  [Phase 3: Bereitstellen des Lync Server 2013-Pilotpools](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [Phase 4: Verschieben von Testbenutzern in den Pilotpool](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [Phase 5: Hinzufügen des Lync Server 2013-Edgeservers zum Pilotpool](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [Phase 6: Migration von der Pilotbereitstellung zur Produktionsbereitstellung](phase-6-move-from-pilot-deployment-into-production.md)

7.  [Phase 7: Ausführen von Aufgaben nach der Migration](phase-7-complete-post-migration-tasks.md)

8.  [Phase 8: Außerbetriebsetzen der Legacypools](phase-8-decommission-legacy-pools.md)

