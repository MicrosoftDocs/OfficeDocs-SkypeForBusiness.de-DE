---
title: 'Lync Server 2013: tblComplianceData'
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558606(v=OCS.15)
ms:contentKeyID: 49293050
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblComplianceData in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

"tblComplianceData" enthält die Kompatibilitätsereignisse, die noch nicht vom Kompatibilitätsadapter verarbeitet wurden.

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
<td><p>cmplEventID</p></td>
<td><p>bigint, nicht NULL</p></td>
<td><p>Ereignis-ID</p></td>
</tr>
<tr class="even">
<td><p>entryDate</p></td>
<td><p>smalldatetime, nicht NULL</p></td>
<td><p>Zeitpunkt des Einfügevorgangs (kann für &quot;cmplType=9&quot; in ferner Zukunft liegen, da der Eintrag in diesem Fall nur ein Platzhalter ist).</p></td>
</tr>
<tr class="odd">
<td><p>cmplType</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Typ des Kompatibilitätsereignisses:</p>
<ul>
<li><p>1: Chat</p></li>
<li><p>2: Backchat</p></li>
<li><p>3: Dateidownload</p></li>
<li><p>4: Dateiupload</p></li>
<li><p>9: Vorläufige Dateiübertragung</p></li>
<li><p>10: Chatlöschung (mit Ersatz)</p></li>
<li><p>11: Chatbereinigung</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>cmplTime</p></td>
<td><p>bigint, nicht NULL</p></td>
<td><p>Zeitstempel für das Ereignis.</p></td>
</tr>
<tr class="odd">
<td><p>cmplChannelUri</p></td>
<td><p>nvarchar (255), nicht NULL</p></td>
<td><p>Kanal-URI (Uniform Resource Identifier).</p></td>
</tr>
<tr class="even">
<td><p>cmplChatID</p></td>
<td><p>bigint</p></td>
<td><p>Chat-ID (entsprechend der Tabelle &quot;tblChat.chatId&quot;).</p></td>
</tr>
<tr class="odd">
<td><p>cmplUserID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Prinzipal-ID des Bereitstellers (entsprechend der Tabelle &quot;tblPrincipal.prinID&quot;).</p></td>
</tr>
<tr class="even">
<td><p>cmplUserUri</p></td>
<td><p>nvarchar (255), nicht NULL</p></td>
<td><p>Benutzer-URI</p></td>
</tr>
<tr class="odd">
<td><p>cmplMessage</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>Nachricht (Codierung abhängig von &quot;cmplType&quot;).</p></td>
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
<td><p>cmplEventID</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
</tbody>
</table>

