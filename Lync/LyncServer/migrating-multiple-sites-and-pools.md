---
title: Migrieren von mehreren Standorten und Pools
TOCTitle: Migrieren von mehreren Standorten und Pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205165(v=OCS.15)
ms:contentKeyID: 49295004
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrieren von mehreren Standorten und Pools

 

_**Letztes Änderungsdatum des Themas:** 2012-09-17_

In Lync Server 2013 werden Bereitstellungen mit mehreren Standorten und Pools unterstützt. Bei der Migration mehrerer Pools von Lync Server 2010 zu Lync Server 2013 müssen die folgenden Aspekte berücksichtigt werden:

1.  Nach dem Bereitstellen eines Lync Server 2013-Pilotpools müssen Sie eine Teilmenge mit Pilotbenutzern, die in den Lync Server 2013-Pool verschoben werden, und eine Methodik zum Validieren der Funktionalität der Benutzer definieren. Stellen Sie beispielsweise nach dem Verschieben eines Benutzers in den Pilotpool sicher, dass die Konferenzrichtlinie des Benutzers nach Lync Server 2013 verschoben wurde.

2.  Nach der Bereitstellung eines Edgeservers im Pilotpool müssen Sie überprüfen, ob externe Benutzer mit dem Lync Server 2013-Pool kommunizieren können.

3.  Nach dem Übergang der Partnerrouten von Lync Server 2010-Edgeservern zu Lync Server 2013-Edgeservern der Partnerbereitstellung müssen Sie überprüfen, ob die Partnerbenutzer mit dem Lync Server 2013-Pool kommunizieren können.

4.  Nach dem Verschieben von allen Benutzern und Kontaktobjekten, die keine Benutzer sind, müssen Sie sicherstellen, dass der Lync Server 2010-Pool leer ist.

5.  Nachdem Sie sichergestellt haben, dass der Lync Server 2010-Pool leer ist, können Sie den Pool deaktivieren.
    
    Ausführliche Informationen über die Deaktivierung von Lync Server 2010-Pools und -Servern aus der Vorversionsumgebung finden Sie unter [Phase 8: Außerbetriebsetzen der Legacypools](phase-8-decommission-legacy-pools.md).

