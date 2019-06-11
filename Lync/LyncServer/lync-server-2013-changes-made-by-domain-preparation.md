---
title: 'Lync Server 2013: von der Domänenvorbereitung vorgenommene Änderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b674e2c3d65aeda22838dca08ac5b016fa83359
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a>Von der Domänenvorbereitung in lync Server 2013 vorgenommene Änderungen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2010-10-18_

In der folgenden Tabelle sind die Zugriffssteuerungseinträge (ACEs) aufgeführt, die von der Domänenvorbereitung für den Domänenstamm erstellt werden. Alle ACEs werden geerbt, sofern nicht anders angegeben.

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a>ACEs, die dem Domänenstamm hinzugefügt wurden

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
<td><p>Read-Container (nicht geerbt)</p></td>
<td><p><strong>Ja</strong></p></td>
<td><p><strong>Ja</strong></p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p>Lesen der Benutzer-PropertySet-Benutzerkonto Einschränkungen</p></td>
<td><p><strong>Ja</strong></p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="odd">
<td><p>Lesen der Benutzer-PropertySet Personal-Informationen</p></td>
<td><p><strong>Ja</strong></p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p>Lesen der Benutzer-PropertySet-allgemeine Informationen</p></td>
<td><p><strong>Ja</strong></p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="odd">
<td><p>Lesen der Benutzer-PropertySet-öffentlichen Informationen</p></td>
<td><p><strong>Ja</strong></p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p>Read User PropertySet RTCUserSearchProperty-Satz</p></td>
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
<td><p>Schreiben von Benutzer Eigenschafts Proxy-Adressen</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p><strong>Ja</strong></p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="odd">
<td><p>Schreiben von Benutzer-Eigenschaftssatz-RTCUserSearchProperty</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p><strong>Ja</strong></p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p>Schreiben von Benutzer-PropertySet-RTCPropertySet</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p><strong>Ja</strong></p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="odd">
<td><p>Lesen von PropertySet DS-Replikation-abrufen – Änderungen aller Active Directory-Objekte</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p><strong>Ja</strong></p></td>
<td><p>Nein</p></td>
</tr>
</tbody>
</table>


In der folgenden Tabelle sind die ACEs aufgeführt, die von der Domänenvorbereitung in den drei integrierten Containern erstellt werden: Benutzer, Computer und Domänencontroller. Alle ACEs werden geerbt, sofern nicht anders angegeben.

### <a name="aces-added-to-built-in-containers"></a>ACEs, die zu integrierten Containern hinzugefügt wurden

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
<td><p>Read-Container (nicht geerbt)</p></td>
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

