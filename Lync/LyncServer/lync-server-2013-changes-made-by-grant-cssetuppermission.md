---
title: 'Lync Server 2013: von Grant-CsSetupPermission vorgenommene Änderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12c9431e413428080f72d34510cdb3879e26e7cf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a>Von Grant-CsSetupPermission vorgenommene Änderungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-20_

Um Setup zu delegieren, können Sie der universellen Gruppe RTCUniversalServerAdmins Berechtigungen für eine bestimmte Active Directory Organisationseinheit (Organizational Unit, OU) erteilen, sodass Mitglieder der Gruppe RTCUniversalServerAdmins in dieser Organisationseinheit lync Server 2013 in der angegebenen Domäne ohne Mitglied der Gruppe "Domänen-Admins" zu sein.

Das **Grant-CsSetupPermission-** Cmdlet erteilt den RTCUniversalServerAdmins-Gruppen Berechtigungen für eine OU, wie in der folgenden Tabelle angegeben:

### <a name="permissions-granted-to-objects-in-the-ou"></a>Berechtigungen, die Objekten in der Organisationseinheit erteilt werden

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
<li><p>ServicePrincipalName lesen</p></li>
<li><p>ServicePrincipalName schreiben</p></li>
<li><p>Struktur löschen</p></li>
<li><p>Verzeichnisänderungen replizieren</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Untergeordnete serviceConnectionPoint-Objekte</p></td>
<td><p>Spezieller Zugriff:</p>
<ul>
<li><p>Leseberechtigungen</p></li>
<li><p>Schreibberechtigungen</p></li>
<li><p>Untergeordnetes Element erstellen</p></li>
<li><p>Untergeordnetes Element löschen</p></li>
<li><p>Inhalt auflisten</p></li>
<li><p>Write-Eigenschaft</p></li>
<li><p>Read-Eigenschaft</p></li>
<li><p>Struktur löschen</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Untergeordnete msRTCSIP-Server Objekte</p></td>
<td><p>Spezieller Zugriff:</p>
<ul>
<li><p>Write-Eigenschaft</p></li>
<li><p>Read-Eigenschaft</p></li>
<li><p>Struktur löschen</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Untergeordnete msRTCSIP-WebComponents-Objekte</p></td>
<td><p>Spezieller Zugriff:</p>
<ul>
<li><p>Write-Eigenschaft</p></li>
<li><p>Read-Eigenschaft</p></li>
<li><p>Struktur löschen</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Untergeordnete msRTCSIP-MCU-Objekte</p></td>
<td><p>Spezieller Zugriff:</p>
<ul>
<li><p>Write-Eigenschaft</p></li>
<li><p>Read-Eigenschaft</p></li>
<li><p>Struktur löschen</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Untergeordnete msRTCSIP-MediationServer-Objekte</p></td>
<td><p>Spezieller Zugriff:</p>
<ul>
<li><p>Write-Eigenschaft</p></li>
<li><p>Read-Eigenschaft</p></li>
<li><p>Struktur löschen</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Untergeordnete msRTCSIP-ApplicationServer-Objekte</p></td>
<td><p>Spezieller Zugriff:</p>
<ul>
<li><p>Write-Eigenschaft</p></li>
<li><p>Read-Eigenschaft</p></li>
<li><p>Struktur löschen</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Untergeordnete msRTCSIP-ConnectionPoint-Objekte</p></td>
<td><p>Spezieller Zugriff:</p>
<ul>
<li><p>Write-Eigenschaft</p></li>
<li><p>Read-Eigenschaft</p></li>
<li><p>Struktur löschen</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Untergeordnete Computer-Objekte</p></td>
<td><p>Spezieller Zugriff für serviceConnectionPoint:</p>
<ul>
<li><p>Untergeordnete Objekte erstellen</p></li>
<li><p>Untergeordnete Objekte löschen</p></li>
<li><p>Struktur löschen</p></li>
</ul>
<p>Spezieller Zugriff für öffentliche Informationen:</p>
<ul>
<li><p>Read-Eigenschaft</p></li>
</ul>
<p>Spezieller Zugriff für den DNS-Hostnamen:</p>
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

