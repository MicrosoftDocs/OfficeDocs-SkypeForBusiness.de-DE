---
title: Migrieren von mehreren Standorten und Pools
TOCTitle: Migrieren von mehreren Standorten und Pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49890709
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrieren von mehreren Standorten und Pools

 

_**Letztes Änderungsdatum des Themas:** 2012-08-26_

In Lync Server 2013 werden Bereitstellungen mit mehreren Standorten und Pools unterstützt. Bei der Migration mehrerer Pools von Office Communications Server 2007 R2 zu Lync Server 2013 müssen die folgenden Aspekte berücksichtigt werden:

1.  Nach dem Bereitstellen eines Lync Server 2013-Pilotpools müssen Sie eine Teilmenge mit Pilotbenutzern, die in den Lync Server 2013-Pool verschoben werden, und eine Methodik zum Validieren der Funktionalität der Benutzer definieren.

2.  Nach der Bereitstellung eines Edgeservers im Pilotpool müssen Sie überprüfen, ob externe Benutzer mit dem Lync Server 2013-Pool kommunizieren können.

3.  Nach dem Übergang der Partnerrouten von Office Communications Server 2007 R2-Edgeservern zu Lync Server 2013-Edgeservern der Partnerbereitstellung müssen Sie überprüfen, ob die Partnerbenutzer mit dem Lync Server 2013-Pool kommunizieren können.

4.  Nach dem Verschieben von allen Benutzern und Kontaktobjekten, die keine Benutzer sind, müssen Sie sicherstellen, dass der Office Communications Server 2007 R2-Pool leer ist.

5.  Nachdem Sie sichergestellt haben, dass der Office Communications Server 2007 R2-Pool leer ist, können Sie den Pool deaktivieren.
    
    Ausführliche Informationen über die Deaktivierung von Office Communications Server 2007 R2-Pools und -Servern aus der Vorversionsumgebung finden Sie unter [Phase 10: Außerbetriebnahme des Vorversionsstandorts](phase-10-decommission-legacy-site.md).

