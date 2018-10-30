---
title: 'Lync Server 2013: tblChat'
TOCTitle: tblChat
ms:assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615031(v=OCS.15)
ms:contentKeyID: 49295188
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblChat in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

tblChat enthält alle Chatnachrichten.

### Spalten

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Typ</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>channelId</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Knoten-ID</p></td>
</tr>
<tr class="even">
<td><p>chatId</p></td>
<td><p>bigint, nicht NULL</p></td>
<td><p>Eindeutige fortlaufende Zahl (pro Knoten-ID), die die Reihenfolge der Chatrooms identifiziert, generiert von der tblLastChatId-Tabelle.</p></td>
</tr>
<tr class="odd">
<td><p>chatDate</p></td>
<td><p>bigint, nicht NULL</p></td>
<td><p>Zeitstempel für die Chatnachricht.</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Prinzipal-ID des Bereitstellers.</p></td>
</tr>
<tr class="odd">
<td><p>isAlert</p></td>
<td><p>bit, nicht NULL</p></td>
<td><p>TRUE, wenn es sich bei der Nachricht um eine Fehlermeldung handelt, andernfalls FALSE.</p></td>
</tr>
<tr class="even">
<td><p>content</p></td>
<td><p>nvarchar (max), nicht NULL</p></td>
<td><p>Chatinhalt (Nur-Text-Version). Der Inhalt ist normalerweise einfacher Text mit den folgenden Ausnahmen:</p>
<ul>
<li><p>Dateien sind als Links vom Typ <strong>ma-filelink:</strong> dargestellt.</p></li>
<li><p>Links sind als HTML-Elemente dargestellt (obwohl der Inhaltstyp nicht als HTML betrachtet werden kann).</p></li>
<li><p>Textabschnitte sind in einem Format wie &quot;[STORY]....&quot; verschlüsselt.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtf</p></td>
<td><p>varchar(max)</p></td>
<td><p>Chatinhalt (RTF-Version). Kann NULL sein, wenn vom Client nicht bereitgestellt.</p></td>
</tr>
</tbody>
</table>


### Schlüssel

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;channelID, chatD&gt;</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
</tbody>
</table>

