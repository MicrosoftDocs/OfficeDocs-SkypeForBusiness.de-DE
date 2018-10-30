---
title: Registration-Ansicht
TOCTitle: Registration-Ansicht
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49890826
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Registration-Ansicht

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In der Registrierungsansicht werden Informationen zur Benutzerregistrierung gespeichert. Diese Ansicht wurde in Lync Server 2013 eingeführt.


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Zeitpunkt der Sitzungsanforderung. Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie unter <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>ID zur Identifikation der Sitzung. Wird zusammen mit SessionIdTime verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie unter <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegisterTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Zeitpunkt, an dem die Registrierung erfolgt ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI der registrierten Benutzer.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>URI-Typ der registrierten Benutzer. Weitere Informationen finden Sie unter <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Mandant der registrierten Benutzers. Weitere Informationen finden Sie unter <a href="lync-server-2013-tenants-table.md">Tenants-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Eindeutige ID des Endpunkts der Benutzer, bei dem sie registriert sind.</p></td>
</tr>
<tr class="even">
<td><p><strong>EndpointEra</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Eindeutige ID zur Unterscheidung der Registrierungen mit gleichen Benutzern und gleichen Endpunkten.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterType</strong></p></td>
<td><p>datetime</p></td>
<td><p>Zeitpunkt, an dem die Registrierung aufgehoben wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeRegisterReason</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Grund für die Aufhebung der Registrierung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Client-Version der registrierten Benutzer.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Client der registrierten Benutzer. Weitere Informationen finden Sie unter <a href="lync-server-2013-useragentdef-table.md">UserAgentDef-Tabelle</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Client-Kategorie der registrierten Benutzer.</p></td>
</tr>
<tr class="even">
<td><p><strong>IpAddress</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>IP-Adresse, bei dem der Benutzer registriert ist. Dies kann eine IPv4- oder IPv6-Adresse sein.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring(775)</p></td>
<td><p>SIP-Dialog-ID. Das Format:</p>
<p>dialog;from-tag;to-tag</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>SIP-Antwortcode auf die Sitzungseinladung. Dieses Feld wird normalerweise von Daten aufgefüllt, die von der initialen INVITE-Nachricht in der Sitzung generiert wird. Wenn keine INVITE-Nachricht vorhanden ist, wird das Feld mit den Datum der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p>Diagnose-ID, die vom SIP-Header erfasst wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>Registrar</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>FQDN der Registrierung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>FQDN des Pools, der die Daten für diese Sitzung erfasst hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>EdgeServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>FQDN des Edgeservers, der vom registrierten Benutzer verwendet wird.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsInternal</strong></p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob der Benutzer von einem internen Netzwerk angemeldet ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob der Benutzerdienst zum Zeitpunkt der Registrierung verfügbar war.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob die Registrierung mit der primären Registrierung durchgeführt wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceMacAddress</strong></p></td>
<td><p>bigint</p></td>
<td><p>MAC-Adresse des registrierten Geräts.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceManufacturer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Hersteller des registrierten Geräts. Weitere Informationen finden Sie unter <a href="lync-server-2013-manufacturers-table.md">Manufacturers-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHardwareVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Hardwareversion des registrierten Geräts. Weitere Informationen finden Sie unter <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

