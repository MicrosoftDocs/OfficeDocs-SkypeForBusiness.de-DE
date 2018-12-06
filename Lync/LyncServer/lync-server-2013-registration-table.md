---
title: 'Lync Server 2013: Registration-Tabelle'
TOCTitle: Registration-Tabelle
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398114(v=OCS.15)
ms:contentKeyID: 49293058
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Registration-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Jeder Datensatz stellt ein Benutzerregistrierungsereignis dar.


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
<td><p>Primär, Fremd</p></td>
<td><p>Zeitpunkt der Sitzungsanforderung. Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>ID zur Kennzeichnung der Sitzung. Gibt in Verbindung mit <strong>SessionIdTime</strong> eine Sitzung eindeutig an. Weitere Informationen finden Sie unter <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die Benutzer-ID. Weitere Informationen finden Sie unter <a href="lync-server-2013-users-table.md">Users-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>EndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p></p></td>
<td><p>Eine GUID (Globally Unique Identifier) zur Kennzeichnung eines Registrierungsendpunkts. In der Regel hat jedes Registrierungsereignis vom gleichen Computer des gleichen Benutzers die gleiche Endpunkt-ID. Verschiedene Computer haben unterschiedliche Endpunkt-IDs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndpointEra</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>ID zum Unterscheiden von Registrierungen, die denselben Benutzer und denselben Endpunkt betreffen.</p>
<p>Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die Clientversion des aktuellen Benutzers. Weitere Informationen finden Sie unter <a href="lync-server-2013-clientversions-table.md">ClientVersions-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegistrarId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die ID des Registrierungsservers, der für die Registrierung verwendet wird. Weitere Informationen finden Sie unter <a href="lync-server-2013-servers-table.md">Servers-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID des Pools, in dem die Sitzung erfasst wurde. Weitere Informationen finden Sie in der <a href="lync-server-2013-pools-table.md">Pools-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Edgeserver, über den die Registrierung läuft. Weitere Informationen finden Sie unter <a href="lync-server-2013-edgeservers-table.md">EdgeServers-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsInternal</strong></p></td>
<td><p>Bit</p></td>
<td><p></p></td>
<td><p>Ob der Benutzer von innerhalb angemeldet ist oder nicht.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Ob der Benutzerdienst verfügbar ist oder nicht.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Ob die Registrierung bei der primären Registrierung erfolgt oder nicht.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrarCentral</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Gibt an, ob der Benutzer mit einer Survivable Branch Appliance registriert ist.</p>
<p>Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>RegisterTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Der Zeitpunkt der Registrierung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Der Zeitpunkt der Aufhebung der Registrierung.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Der Antwortcode der Registrierungsanforderung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Die Diagnose-ID der Registrierungsanforderung. Diese gibt den Diagnoseinformationstyp an.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Das Gerät, von dem die Registrierungsanforderung stammt. Weitere Informationen finden Sie unter <a href="lync-server-2013-devices-table.md">Devices-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Fremd</p></td>
<td><p>Der Grund für die Aufhebung der Registrierung, z. B. vom Benutzer initiiert, Registrierung abgelaufen, Fehler beim Client usw. Weitere Informationen finden Sie unter <a href="lync-server-2013-deregistertype-table.md">DeRegisterType-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddress</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>IP-Adresse des Endpunkts, mit dem sich der Benutzer registriert hat. Dies kann eine IPv4- oder eine IPv6-Adresse sein.</p>
<p>Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>

