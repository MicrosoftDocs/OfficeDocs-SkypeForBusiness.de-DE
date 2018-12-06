---
title: 'Lync Server 2013: Kapazitätsplanung für Reaktionsgruppen'
TOCTitle: Kapazitätsplanung für Reaktionsgruppen
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412754(v=OCS.15)
ms:contentKeyID: 49294951
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Kapazitätsplanung für Reaktionsgruppen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In der folgenden Tabelle wird das Benutzermodell der Reaktionsgruppe beschrieben, das Sie als Grundlage für die Anforderungen bei der Kapazitätsplanung verwenden können.


> [!NOTE]
> Bei den Zahlen in der folgenden Tabelle wird davon ausgegangen, dass Sie 16-kHz-, Mono-, 16-Bit-WAV-Dateien für alle Audiodateien für Reaktionsgruppen verwenden. Wenn Sie andere Dateiformate, z.&nbsp;B. Windows Media Audio (WMA), einsetzen, können die Zahlen abweichen.




> [!IMPORTANT]
> Bedenken Sie bei der Kapazitätsplanung für die Notfallwiederherstellung, dass jeder Pool eines Poolpaars in der Lage sein sollte, die Arbeitslasten für alle Reaktionsgruppen in beiden Pools zu verarbeiten.



### Benutzermodell für Reaktionsgruppen

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Metrik</th>
<th>Pro Enterprise Edition-Pool (mit 8 Front-End-Servern)</th>
<th>Pro Standard Edition-Server</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Eingehende Anrufe pro Sekunde</p></td>
<td><p>16</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>Gleichzeitige mit interaktiver Sprachantwort (IVR) oder Wartemusik (MoH) verbundene Anrufe</p></td>
<td><p>480</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Gleichzeitige anonyme Sitzungen (ohne Instant Messaging)</p></td>
<td><p>224</p></td>
<td><p>28</p></td>
</tr>
<tr class="even">
<td><p>Gleichzeitige anonyme Sitzungen (mit Instant Messaging)</p></td>
<td><p>64</p></td>
<td><p>8</p></td>
</tr>
<tr class="odd">
<td><p>Aktive Agents (formell und informell)</p></td>
<td><p>1200</p></td>
<td><p>1200</p></td>
</tr>
<tr class="even">
<td><p>Anzahl der Sammelanschlüsse</p></td>
<td><p>400</p></td>
<td><p>400</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl der IVR-Gruppen (Verwendung der Spracherkennung)</p></td>
<td><p>200</p></td>
<td><p>200</p></td>
</tr>
</tbody>
</table>

