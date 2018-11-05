---
title: VoIPDetails-Ansicht
TOCTitle: VoIPDetails-Ansicht
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49890634
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# VoIPDetails-Ansicht

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die VoIPDetails-Ansicht speichert Informationen zu Peer-zu-Peer-Sitzungen, an denen mindestens ein VoIP-Benutzer teilnimmt. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.


> [!NOTE]
> Neben den unten aufgeführten Spalten enthält die VoIPDetails-Ansicht alle Spalten in der <A href="lync-server-2013-sessiondetails-view.md">SessionDetails-Ansicht</A>.




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
<td><p><strong>FromPhone</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Telefon-URI des Benutzers, der die Sitzung gestartet hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToPhone</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Telefon-URI des Benutzers, der der Sitzung beigetreten ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI des Benutzers, der die Verbindung zur Sitzung unterbrochen hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>URI-Typ des Benutzers, der die Verbindung zur Sitzung unterbrochen hat. Weitere Informationen finden Sie in der <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Mandant des Benutzers, der die Sitzung gestartet hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByPhone</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Telefon-URI des Benutzers, der die Verbindung zur Sitzung unterbrochen hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Vom Benutzer, der die Sitzung gestartet hat, verwendeter Vermittlungsserver.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Vom Benutzer, der der Sitzung beigetreten ist, verwendeter Vermittlungsserver.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGateway</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Vom Benutzer, der die Sitzung gestartet hat, verwendetes Gateway.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToGateway</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Vom Benutzer, der der Sitzung beigetreten ist, verwendetes Gateway.</p></td>
</tr>
</tbody>
</table>

