---
title: 'Lync Server 2013: Registration-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfee81d83fb58b2fbeccff68a672da47e6770bd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823798"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a>Registration-Tabelle in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Jeder Datensatz steht für ein Benutzer Registrierungs Ereignis.


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
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionID</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primär, fremd</p></td>
<td><p>Uhrzeit der Sitzungsanforderung. Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, fremd</p></td>
<td><p>Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit <strong>SessionID</strong> -Mal verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserID</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die Benutzer-ID. Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>EndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td></td>
<td><p>Eine GUID, um einen Registrierungs Endpunkt zu identifizieren. In der Regel verfügt das Register-Ereignis vom gleichen Computer desselben Benutzers über die gleiche Endpunkt-ID. Unterschiedliche Computer verfügen über eine andere Endpunkt-ID.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndpointEra</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>Die ID, mit der Registrierungen unterschieden werden, die denselben Benutzer und denselben Endpunkt einbeziehen.</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Client Version des aktuellen Benutzers. Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der ClientVersions-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Registrator</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die ID des Registrierungsservers, der für die Registrierung verwendet wird. Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool-Nr</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die ID des Pools, in dem die Sitzung erfasst wurde. Weitere Informationen finden Sie <a href="lync-server-2013-pools-table.md">in der Tabelle Pools in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Edge-Server die Registrierung wird durchlaufen. Weitere Informationen finden Sie <a href="lync-server-2013-edgeservers-table.md">in der EdgeServers-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>"IsInternal</strong></p></td>
<td><p>Bit</p></td>
<td></td>
<td><p>Gibt an, ob der Benutzer intern angemeldet ist oder nicht.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Gibt an, ob die UserService verfügbar ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Ob Sie sich bei der primären Registrierungsstelle registrieren oder nicht.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrarCentral</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Gibt an, ob der Benutzer bei einer Survivable Branch-Appliance registriert ist.</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Registrierung</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Registrierungszeit.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Registrierung</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Zeit für die Registrierung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Response Code</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Antwortcode der Registrierungsanforderung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Diagnose-Nr</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Diagnose-ID der Registrierungsanforderung. Dies gibt an, dass der Typ der diagnostischen Informationen.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceID</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Das Gerät, von dem die Registrierungsanforderung stammt. Weitere Informationen finden Sie <a href="lync-server-2013-devices-table.md">in der Tabelle Devices in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Fremd</p></td>
<td><p>Der Grund für die Deregistrierung, wie "Benutzer initiiert", "Registrierung abgelaufen", "Client Fehler" und vieles mehr. Weitere Informationen finden Sie <a href="lync-server-2013-deregistertype-table.md">in der Tabelle deregistertype in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddress</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>Die IP-Adresse des Endpunkts, bei dem der Benutzer registriert ist. Dies kann eine IPv4-Adresse oder eine IPv6-Adresse sein.</p>
<p>Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

