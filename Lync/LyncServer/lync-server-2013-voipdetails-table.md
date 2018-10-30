---
title: 'Lync Server 2013: VoipDetails-Tabelle'
TOCTitle: VoipDetails-Tabelle
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398566(v=OCS.15)
ms:contentKeyID: 49294410
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# VoipDetails-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Jeder Datensatz steht für einen Anruf mit zwei Teilnehmern, wovon mindestens einer ein VoIP-Benutzer ist.


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Zeitpunkt der Sitzungsanforderung. Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>ID zur Kennzeichnung der Sitzung. Gibt in Verbindung mit <strong>SessionIdTime</strong> eine Sitzung eindeutig an. Weitere Informationen finden Sie unter <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromNumberId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p><strong>PhoneId</strong> des Anrufers. Weitere Informationen finden Sie unter <a href="lync-server-2013-phones-table.md">Phones-Tabelle in Lync Server 2013</a>. Wenn nicht NULL und <strong>FromGatewayId</strong> ist nicht NULL, handelt es sich beim Anrufer um einen PSTN-Benutzer.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectedNumberId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p><strong>PhoneId</strong> des Anrufempfängers. Weitere Informationen finden Sie unter <a href="lync-server-2013-phones-table.md">Phones-Tabelle in Lync Server 2013</a>. Wenn nicht NULL und <strong>FromGatewayId</strong> ist nicht NULL, handelt es sich beim Anrufempfänger um einen PSTN-Benutzer.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Vermittlungsserver, von dem der Anruf kommt. Weitere Informationen finden Sie unter <a href="lync-server-2013-mediationservers-table.md">MediationServers-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Vermittlungsserver, an den der Anruf geht. Weitere Informationen finden Sie unter <a href="lync-server-2013-mediationservers-table.md">MediationServers-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Das Gateway, von dem der Anruf kommt. Weitere Informationen finden Sie unter <a href="lync-server-2013-gateways-table.md">Gateways-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Das Gateway, an das der Anruf geht. Weitere Informationen finden Sie unter <a href="lync-server-2013-gateways-table.md">Gateways-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedbyURIId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>URI des Benutzers, der den Anruf unterbrochen hat, sofern der Benutzer über einen URI verfügt. Weitere Informationen finden Sie unter <a href="lync-server-2013-users-table.md">Users-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedbyPhoneId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID des Telefons, das den Anruf unterbrochen hat, sofern der Anruf von einem Telefon unterbrochen wurde. Weitere Informationen finden Sie unter <a href="lync-server-2013-phones-table.md">Phones-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

