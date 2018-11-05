---
title: 'Lync Server 2013: Konfigurieren der Orbittabelle für das Parken von Anrufen'
TOCTitle: Konfigurieren der Orbittabelle für das Parken von Anrufen
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg399020(v=OCS.15)
ms:contentKeyID: 49295718
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der Orbittabelle für das Parken von Anrufen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-10_

Die Funktion zum Parken von Anrufen verwendet Orbits für das Parken von Anrufen. Bevor die Benutzer Anrufe parken und wiederaufnehmen können, müssen Sie die Orbittabelle zum Parken von Anrufen konfigurieren. Sie müssen die Bereiche der Durchwahlnummern (Orbits), die Ihr Unternehmen für das Parken von Anrufen reserviert, festlegen und das Routing für diese Bereiche definieren. Ordnen Sie dazu jedem Pool zum Parken von Anrufen einen Bereich zu. Wenn Sie Orbitbereiche definieren, besteht das Ziel darin, über so viele Orbits zu verfügen, dass ein bestimmter Orbit nicht zu schnell wiederverwendet wird. Allerdings sollte die Zahl der Orbits auch nicht so hoch liegen, dass die Anzahl der für die Benutzer oder andere Dienste verfügbaren Durchwahlnummern eingeschränkt wird. Sie können mehrere Orbitbereiche zum Parken von Anrufen für jeden Lync Server-Pool festlegen, in dem die Funktion zum Anwendung zum Parken von Anrufen bereitgestellt wird. Jeder Orbitbereich für das Parken von Anrufen muss über einen global eindeutigen Namen und einen eindeutigen Satz an Durchwahlnummern verfügen.


> [!IMPORTANT]
> Ein Orbitbereich umfasst normalerweise 100 oder weniger Orbits. Jeder Bereich kann deutlich größer sein, solange der Höchstwert von 10.000&nbsp;Orbits pro Bereich nicht überschritten wird und Sie über weniger als 50.000&nbsp;Orbits pro Pool verfügen. Ist ein Bereich zu klein, werden die Orbits zu schnell wiederverwendet.



Verwenden Sie für Ihre Orbitbereiche Blöcke virtueller Durchwahlnummern (Durchwahlnummern, denen kein Benutzer oder Telefon zugewiesen ist).


> [!NOTE]
> Das Zuweisen von DID-Nummern (Direct Inward Dialing) als Orbitnummern in der Orbittabelle für das Parken von Anrufen wird nicht unterstützt.



## In diesem Abschnitt

[Erstellen oder Ändern eines Orbitbereichs für das Parken von Anrufen in Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

