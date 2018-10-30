---
title: 'Lync Server 2013: Kapazitätsplanung für das Parken von Anrufen'
TOCTitle: Kapazitätsplanung für das Parken von Anrufen
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg416493(v=OCS.15)
ms:contentKeyID: 49294424
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Kapazitätsplanung für das Parken von Anrufen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In der folgenden Tabelle wird das Benutzermodell der Parken von Anrufen beschrieben, das Sie als Grundlage für die Anforderungen bei der Kapazitätsplanung verwenden können.


> [!IMPORTANT]
> Beachten Sie bei der Kapazitätsplanung für die Notfallwiederherstellung, dass jeder Pool eines gekoppelten Pools die Arbeitsauslastungen für Parken von Anrufen-Dienste in beiden Pools unterstützen muss.



### Benutzermodell der Funktion zum Parken von Anrufen

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Metrik</th>
<th>Pro Front-End-Pool (mit 8 Front-End-Servern)</th>
<th>Per Standard Edition-Server</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Rate für das Parken von Anrufen</p></td>
<td><p>8 pro Minute</p></td>
<td><p>1 pro Minute</p></td>
</tr>
<tr class="even">
<td><p>Rate für das Abrufen geparkter Anrufe</p></td>
<td><p>8 pro Minute</p></td>
<td><p>1 pro Minute</p></td>
</tr>
<tr class="odd">
<td><p>Durchschnittliche Parkdauer</p></td>
<td><p>60 Sekunden</p></td>
<td><p>60 Sekunden</p></td>
</tr>
</tbody>
</table>

