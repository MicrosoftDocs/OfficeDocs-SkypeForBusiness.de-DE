---
title: 'Lync Server 2013: ConferenceUris-Tabelle'
TOCTitle: ConferenceUris-Tabelle
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412854(v=OCS.15)
ms:contentKeyID: 49295123
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ConferenceUris-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **ConferenceUris** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Darin wird eine Liste der verschiedenen Konferenz-URIs gespeichert, die an in der Datenbank aufgezeichneten Konferenzsitzungen beteiligt waren. Jeder Datensatz in der Tabelle steht für einen Konferenz-URI.


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
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Zeitstempel; zu internen Zwecken.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die diesen Konferenz-URI identifiziert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p></p></td>
<td><p>Der Konferenz-URI.</p></td>
</tr>
<tr class="even">
<td><p><strong>Checksum</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Prüfsumme von <strong>ConferenceUri</strong> . Wird verwendet, um die Geschwindigkeit von Datenbanksuchvorgängen zu steigern.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>URI-Typ, wie etwa <strong>conf:chat</strong> für Sofortnachrichtenkonferenzen oder <strong>conf:audio-video</strong> für Audio-/Video-Konferenzen. Weitere Informationen sind der Tabelle <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in Lync Server 2013</a> zu entnehmen.</p></td>
</tr>
</tbody>
</table>

