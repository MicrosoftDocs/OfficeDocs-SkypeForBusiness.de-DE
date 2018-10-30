---
title: Konfigurieren des Lync Server-Computers für die Teilnahme an der System Center-Ermittlung
TOCTitle: Konfigurieren des Lync Server-Computers für die Teilnahme an der System Center-Ermittlung
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204776(v=OCS.15)
ms:contentKeyID: 49293565
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren des Lync Server-Computers für die Teilnahme an der System Center-Ermittlung

 

_**Letztes Änderungsdatum des Themas:** 2012-10-20_

Um sicherzustellen, dass der neue Lync Server-Agent am Erkennungsprozess für System Center Operations Manager teilnimmt, müssen Sie auf jedem Computer, auf dem die System Center Operations Manager-Konsole installiert ist, das folgende Verfahren ausführen:

1.  Klicken Sie auf die Registerkarte **Verwaltung** auf **Mit Agents verwaltet**.

2.  Klicken Sie mit der rechten Maustaste auf den Namen des Computers, und klicken Sie dann auf **Eigenschaften**. Wählen Sie im Dialogfeld **Eigenschaften** auf der Registerkarte **Sicherheit** die Option **Dieser Agent soll als Proxyagent fungieren und verwaltete Objekte auf anderen Computern erkennen** aus, und klicken Sie dann auf **OK**.

Starten Sie den Systemintegritäts-Agent-Dienst neu, nachdem Sie Schritt 2 abgeschlossen haben. (Durch den Neustart des Diensts wird die Erkennung des neuen Computers "erzwungen". Wenn Sie den Dienst nicht neu starten, kann es bis zu 4 Stunden dauern, bis der neue Computer vom System Center Operations Manager erkannt wird.). Stellen Sie nach dem Neustart des Diensts sicher, dass im System Center Operations Manager-Ereignisprotokoll keine Fehlerereignisse aufgezeichnet werden.

