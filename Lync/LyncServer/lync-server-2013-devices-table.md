---
title: 'Lync Server 2013: Devices-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Devices table
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48184169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8906519253445ea67f3fa674a9a1315f8f6cf18b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a>Devices-Tabelle in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-05-25_

Bei der Devices-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz speichert Informationen über ein Gerät (Telefonapparat).


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
<td><p><strong>DeviceID</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die diese Hardwareversion identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>ManufacturerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Hersteller dieses Geräts. Weitere Informationen finden Sie <a href="lync-server-2013-manufacturers-table.md">in der Tabelle Hersteller in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>HardwareVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Hardwareversion dieses Geräts. Weitere Informationen finden Sie <a href="lync-server-2013-hardwareversions-table.md">in der Hardware Versions-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>MACAddress</strong></p></td>
<td><p>bigint</p></td>
<td></td>
<td><p>MAC-Adresse</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

