---
title: ConferenceJoinTimeThresholds-Tabelle
TOCTitle: ConferenceJoinTimeThresholds-Tabelle
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204809(v=OCS.15)
ms:contentKeyID: 49293708
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ConferenceJoinTimeThresholds-Tabelle

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die Tabelle **ConferenceJoinTimeThresholds** enthält die Klassifizierungsgrenzwerte, die vom zusammenfassenden Bericht über den Zeitpunkt des Konferenzbeitritts verwendet werden. Der Bericht über den Zeitpunkt des Konferenzbeitritts enthält eine Zusammenfassung der Zeit, die Benutzer benötigen, um einer Konferenz erfolgreich beizutreten. Diese Zeitwerte werden sowohl als Durchschnitt als auch in einer der folgenden Kategorien gemeldet:

  - Weniger als 2 Sekunden.

  - Zwischen 2 Sekunden und 5 Sekunden.

  - Zwischen 5 Sekunden und 10 Sekunden.

  - Mehr als 10 Sekunden.

Die Tabelle **ConferenceJoinTimeThresholds** enthält die Klassifizierungswerte 2 Sekunden, 5 Sekunden und 10 Sekunden.

Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Datentyp</th>
<th>Schlüssel/Index</th>
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ThresholdId</strong></p></td>
<td><p>int</p></td>
<td><p>Primär</p></td>
<td><p>Eindeutige ID für die Klassifizierung.</p></td>
</tr>
<tr class="even">
<td><p><strong>ThresholdValue</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Oberer Grenzwert für die Klassifizierung. Gültige Werte sind:</p>
<ol>
<li><p>2</p></li>
<li><p>5</p></li>
<li><p>10</p></li>
</ol></td>
</tr>
</tbody>
</table>

