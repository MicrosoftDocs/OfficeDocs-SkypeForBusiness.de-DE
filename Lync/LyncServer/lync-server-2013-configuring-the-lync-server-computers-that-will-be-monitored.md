---
title: Konfigurieren der zu überwachenden Lync Server-Computer
TOCTitle: Konfigurieren der zu überwachenden Lync Server-Computer
ms:assetid: 9f1b2b91-d5af-42ad-a27d-b0815f762ad8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205118(v=OCS.15)
ms:contentKeyID: 49294920
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der zu überwachenden Lync Server-Computer

 

_**Letztes Änderungsdatum des Themas:** 2012-10-20_

Da Lync Server 2013 den in Microsoft Lync Server 2010 verwendeten zentralen Suchvorgang nicht verwendet, muss jeder Lync Server 2013-Computer, den Sie überwachen möchten, seine Existenz per Selbstauskunft an den Verwaltungsserver melden können. Um dies zu ermöglichen, müssen Sie die Operations Manager-Agent-Dateien auf allen zu überwachenden Computern installieren. Nach dem Installieren der Agent-Dateien müssen Sie die Computer für die Funktion als System Center-Proxy konfigurieren. Beachten Sie, dass Sie diese Vorgänge ausführen sollten, nachdem Sie Lync Server auf diesen Computern installiert und konfiguriert haben.

