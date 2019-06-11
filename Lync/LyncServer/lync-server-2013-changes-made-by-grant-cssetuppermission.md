---
title: 'Lync Server 2013: von Grant-CsSetupPermission vorgenommene Änderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc63cf814f2bd901ab9753fe0f4501e7f44e2189
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a>Von Grant-CsSetupPermission in lync Server 2013 vorgenommene Änderungen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-20_

Zum Delegieren von Setup können Sie der universellen RTCUniversalServerAdmins-Gruppe Berechtigungen für eine bestimmte Active Directory-Organisationseinheit erteilen, sodass Mitglieder der RTCUniversalServerAdmins-Gruppe in dieser OU lync Server 2013 im angegebenen Domäne, ohne Mitglieder der Gruppe "Domänen-Admins" zu sein.

Das Cmdlet **Grant-CsSetupPermission** gewährt der RTCUniversalServerAdmins-Gruppe Berechtigungen für eine OU, wie in der folgenden Tabelle angegeben:

### <a name="permissions-granted-to-objects-in-the-ou"></a>Berechtigungen, die Objekten in der Organisationseinheit gewährt werden

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Berechtigungen gelten für:</th>
<th>Gewährte Berechtigungen sind:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>Spezieller Zugriff:</p>
<ul>
<li><p>Lesen von servicePrincipalName</p></li>
<li><p>Schreiben von servicePrincipalName</p></li>
<li><p>Struktur löschen</p></li>
<li><p>Replizieren von Verzeichnisänderungen</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Nachfolger serviceConnectionPoint-Objekte</p></td>
<td><p>Spezieller Zugriff:</p>
<ul>
<li><p>Leseberechtigungen</p></li>
<li><p>Schreibberechtigungen</p></li>
<li><p>Erstellen eines untergeordneten Elements</p></li>
<li><p>Untergeordnetes Element löschen</p></li>
<li><p>Listeninhalt</p></li>
<li><p>Write-Eigenschaft</p></li>
<li><p>Read-Eigenschaft</p></li>
<li><p>Struktur löschen</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>NachfolgerAttribut msRTCSIP-Server Objekte</p></td>
<td><p>Spezieller Zugriff:</p>
<ul>
<li><p>Write-Eigenschaft</p></li>
<li><p>Read-Eigenschaft</p></li>
<li><p>Struktur löschen</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>NachfolgerAttribut msRTCSIP – Webkomponenten Objekte</p></td>
<td><p>Spezieller Zugriff:</p>
<ul>
<li><p>Write-Eigenschaft</p></li>
<li><p>Read-Eigenschaft</p></li>
<li><p>Struktur löschen</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>NachfolgerAttribut msRTCSIP-MCU-Objekte</p></td>
<td><p>Spezieller Zugriff:</p>
<ul>
<li><p>Write-Eigenschaft</p></li>
<li><p>Read-Eigenschaft</p></li>
<li><p>Struktur löschen</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>NachfolgerAttribut msRTCSIP-MediationServer-Objekte</p></td>
<td><p>Spezieller Zugriff:</p>
<ul>
<li><p>Write-Eigenschaft</p></li>
<li><p>Read-Eigenschaft</p></li>
<li><p>Struktur löschen</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>NachfolgerAttribut msRTCSIP-ApplicationServer-Objekte</p></td>
<td><p>Spezieller Zugriff:</p>
<ul>
<li><p>Write-Eigenschaft</p></li>
<li><p>Read-Eigenschaft</p></li>
<li><p>Struktur löschen</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>NachfolgerAttribut msRTCSIP-ConnectionPoint-Objekte</p></td>
<td><p>Spezieller Zugriff:</p>
<ul>
<li><p>Write-Eigenschaft</p></li>
<li><p>Read-Eigenschaft</p></li>
<li><p>Struktur löschen</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Nachfolger Computer Objekte</p></td>
<td><p>Spezieller Zugriff für serviceConnectionPoint:</p>
<ul>
<li><p>Erstellen von untergeordneten Objekten</p></li>
<li><p>Löschen von untergeordneten Objekten</p></li>
<li><p>Struktur löschen</p></li>
</ul>
<p>Spezieller Zugriff für öffentliche Informationen:</p>
<ul>
<li><p>Read-Eigenschaft</p></li>
</ul>
<p>Spezieller Zugriff auf den DNS-Hostname:</p>
<ul>
<li><p>Read-Eigenschaft</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

