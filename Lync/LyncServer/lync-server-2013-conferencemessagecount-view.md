---
title: ConferenceMessageCount-Ansicht
TOCTitle: ConferenceMessageCount-Ansicht
ms:assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688129(v=OCS.15)
ms:contentKeyID: 49890836
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ConferenceMessageCount-Ansicht

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die ConferenceMessageCount-Ansicht speichert Informationen darüber, wie viele Nachrichten durch einen Benutzer an eine Konferenz gesendet wurden. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.


> [!NOTE]
> Die ConferenceMessageCount-Ansicht enthält neben den unten aufgeführten Spalten alle Spalten der <A href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails-Ansicht</A>.




<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Datentyp</th>
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI des Benutzers, der die Nachricht gesendet hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Geben Sie den URI des Benutzers ein, der die Nachrichten gesendet hat. Weitere Informationen finden Sie in der <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Tenant des Benutzers, der die Nachrichten gesendet hat. Weitere Informationen finden Sie in der <a href="lync-server-2013-tenants-table.md">Tenants-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserMessageCount</strong></p></td>
<td><p>smallint</p></td>
<td><p>Anzahl der vom Benutzer während der Sitzung gesendeten Nachrichten.</p></td>
</tr>
</tbody>
</table>

