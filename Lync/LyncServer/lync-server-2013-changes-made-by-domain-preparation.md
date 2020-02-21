---
title: 'Lync Server 2013: von der Domänenvorbereitung vorgenommene Änderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74fe383cf773e1cdfa645a3f8513167fd7472958
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a>Von der Domänenvorbereitung in lync Server 2013 vorgenommene Änderungen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2010-10-18_

In der folgenden Tabelle sind die ACEs (Access Control Entries, Zugriffssteuerungseinträge) aufgeführt, die während der Domänenvorbereitung im Domänenstamm erstellt werden. Alle ACEs werden vererbt, sofern nicht anders angegeben.

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a>Zum Domänenstamm hinzugefügte ACEs

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversal-UserReadOnly-Gruppe</th>
<th>RTCUniversal-ServerReadOnly-Gruppe</th>
<th>RTCUniversal-UserAdmins</th>
<th>RTCHSUniversal-Dienste</th>
<th>Authentifizierte Benutzer</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Read Container (nicht vererbt)</p></td>
<td><p><strong>Ja</strong></p></td>
<td><p><strong>Ja</strong></p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p>Read User PropertySet User-Account-Restrictions</p></td>
<td><p><strong>Ja</strong></p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="odd">
<td><p>Read User PropertySet Personal-Information</p></td>
<td><p><strong>Ja</strong></p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p>Read User PropertySet General-Information</p></td>
<td><p><strong>Ja</strong></p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="odd">
<td><p>Read User PropertySet Public-Information</p></td>
<td><p><strong>Ja</strong></p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p>Read User PropertySet RTCUserSearchProperty-Set</p></td>
<td><p><strong>Ja</strong></p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p><strong>Ja</strong></p></td>
</tr>
<tr class="odd">
<td><p>Read User PropertySet RTCPropertySet</p></td>
<td><p><strong>Ja</strong></p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p>Write User Property Proxy-Addresses</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p><strong>Ja</strong></p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="odd">
<td><p>Write User PropertySet RTCUserSearchProperty-Set</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p><strong>Ja</strong></p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p>Write User PropertySet RTCPropertySet</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p><strong>Ja</strong></p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="odd">
<td><p>Read PropertySet DS-Replication-Get-Changes für alle Active Directory-Objekte</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p><strong>Ja</strong></p></td>
<td><p>Nein</p></td>
</tr>
</tbody>
</table>


In der folgenden Tabelle sind die ACEs (Access Control Entries, Zugriffssteuerungseinträge) aufgeführt, die während der Domänenvorbereitung in den drei integrierten Containern erstellt werden: für Benutzer, Computer und Domänencontroller. Alle ACEs werden vererbt, sofern nicht anders angegeben.

### <a name="aces-added-to-built-in-containers"></a>Zu integrierten Containern hinzugefügte ACEs

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversal-UserReadOnly-Gruppe</th>
<th>RTCUniversal-ServerReadOnly-Gruppe</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Read Container (nicht vererbt)</p></td>
<td><p><strong>Ja</strong></p></td>
<td><p><strong>Ja</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

