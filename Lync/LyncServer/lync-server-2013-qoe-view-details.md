---
title: Details zur QoE-Ansicht in Lync Server 2013
TOCTitle: Details zur QoE-Ansicht in Lync Server 2013
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49890780
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Details zur QoE-Ansicht in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Ansichten gibt es für die gebräuchlichsten Szenarien zur Rückgabe von Daten aus der QoE-SQL-Datenbank. Es wird empfohlen, zum Erstellen von benutzerdefinierten Berichten Ansichten zu verwenden, anstatt direkt auf die Datenbanktabellen zuzugreifen, um auch in zukünftigen Versionen abwärtskompatibel zu bleiben.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Ansichtsname</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-audiostreamdetail-view.md">AudioStreamDetail-Ansicht</a></p></td>
<td><p>Speichert Informationen zu jedem Audiostream in der Datenbank.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialine-view.md">MediaLine-Ansicht</a></p></td>
<td><p>Speichert Informationen zu jeder Medienzeile in der Datenbank. Eine Audiositzung enthält für gewöhnlich eine Audiomedienzeile. Eine A/V-Sitzung (Audio und Video) enthält meist eine Audiomedienzeile und eine Videomedienzeile, kann jedoch auch zwei Medienzeilen enthalten, wenn ein Konferenzgerät oder eine Galerieansicht verwendet wird.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-networkconfigurationsettings-view.md">NetworkConfigurationSettings-Ansicht</a></p></td>
<td><p>Speichert Informationen über die Netzwerkkonfiguration.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-view.md">Session-Ansicht</a></p></td>
<td><p>Speichert Informationen über Sitzungen, zu denen in der Datenbank Datensätze vorhanden sind.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-view.md">UserAgent-Ansicht</a></p></td>
<td><p>Speichert Informationen über die Benutzeragents, die an Sitzungen beteiligt waren, zu denen es in der Datenbank Datensätze gibt.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostreamdetail-view.md">VideoStreamDetail-Ansicht</a></p></td>
<td><p>Speichert Informationen zu jedem Videostream in der Datenbank.</p></td>
</tr>
</tbody>
</table>

