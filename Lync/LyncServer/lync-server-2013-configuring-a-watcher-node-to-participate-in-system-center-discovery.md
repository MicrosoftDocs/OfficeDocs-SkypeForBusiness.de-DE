---
title: Konfigurieren eines Watcher-Knotens für die Teilnahme an der System Center-Ermittlung
TOCTitle: Konfigurieren eines Watcher-Knotens für die Teilnahme an der System Center-Ermittlung
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204704(v=OCS.15)
ms:contentKeyID: 49293282
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren eines Watcher-Knotens für die Teilnahme an der System Center-Ermittlung

 

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Um sicherzustellen, dass der Watcher-Knoten am Erkennungsprozess für System Center Operations Manager teilnimmt, müssen Sie auf jedem Computer, auf dem die System Center Operations Manager-Konsole installiert ist, das folgende Verfahren ausführen:

1.  Klicken Sie auf die Registerkarte **Verwaltung** auf **Mit Agents verwaltet**.

2.  Klicken Sie mit der rechten Maustaste auf den Namen des Watcher-Knoten-Computers, und klicken Sie dann auf **Eigenschaften**. Wählen Sie im Dialogfeld **Eigenschaften** auf der Registerkarte **Sicherheit** die Option **Dieser Agent soll als Proxyagent fungieren und verwaltete Objekte auf anderen Computern erkennen** aus, und klicken Sie dann auf **OK**.

Starten Sie den Watcher-Knoten-Computer neu, nachdem Sie Watcher-Knoten so konfiguriert haben, dass er als Proxy fungiert. Überprüfen Sie nach dem Neustart des Computers, dass im Operations Manager-Ereignisprotokoll auf diesem Computer keine Fehlerereignisse aufgezeichnet werden. Überprüfen Sie ca. 15 Minuten nach dem Hochfahren des Computers mithilfe der Operations Manager-Konsole, dass Ihre Lync Server-Computer in der Kategorie **Lync** aufgeführt sind.

