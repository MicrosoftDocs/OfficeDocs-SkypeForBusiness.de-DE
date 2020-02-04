---
title: 'Lync Server 2013: Bereitstellungsberechtigungen für SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 393e293dfc7e20fa1e990d9f87c17c6e72776be3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a>Bereitstellungsberechtigungen für SQL Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Microsoft SQL Server 2012 hat bestimmte Anforderungen beim Installieren und Bereitstellen von lync Server 2013. Da Windows und SQL Server Ihre Sicherheit anders definieren, gewährt die Anmeldung als Administrator in der Active Directory-Domäne implizit keine Berechtigungen für SQL Server. Sie müssen auch ein Mitglied der sysadmin-Entität auf dem SQL Server-basierten Server sein, den Sie konfigurieren.

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a>Für die Installation von Datenbank und lync Server erforderliche Berechtigungen

Die folgenden Optionen erläutern drei Berechtigungen und Gruppen Mitgliedschafts Zuordnungen für die Installation von lync Server 2013-Dateien und SQL Server-Datenbanken. Wählen Sie das Szenario aus, das den Anforderungen Ihrer Organisation am besten entspricht.

### <a name="permissions-and-group-membership-associations"></a>Berechtigungen und Gruppen Mitgliedschafts Zuordnungen

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>SQL Server-oder lync Server 2013-Rolle</th>
<th>Rollen typische SQL Server-Berechtigungen und Gruppenmitgliedschaft</th>
<th>Rollen typische lync Server 2013-Berechtigungen und Gruppenmitgliedschaft</th>
<th>Berechtigungs Ergebnis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013-Administrator</p></td>
<td><p>Es muss eine Mitgliedschaft in der SQL Server-Sicherheitsgruppe SysAdmins und Mitglied der Gruppe der lokalen Administratoren von SQL Server gewährt werden.</p></td>
<td><p>Muss ein Mitglied der RTCUniversalServerAdmins-Gruppe sein</p></td>
<td><p>Der lync Server 2013-Administrator verfügt über die erforderlichen Berechtigungen zum Installieren von lync Server 2013-und SQL Server-Datenbanken.</p></td>
</tr>
<tr class="even">
<td><p>SQL Server-Administrator</p></td>
<td><p>SQL Server sysadmin-Gruppenmitglied (oder Äquivalent) und Mitglied der Gruppe der lokalen SQL Server-Administratoren</p></td>
<td><p>Muss ein Mitglied der RTCUniversalServerReadOnly-Gruppe sein</p></td>
<td><p>Der SQL Server-Administrator verfügt über die erforderlichen Berechtigungen zum Installieren von lync Server 2013-und SQL Server-Datenbanken.</p></td>
</tr>
<tr class="odd">
<td><p>Beide Administratoren Teilen Installationsaufgaben</p></td>
<td><p>Der SQL Server-Administrator ist Mitglied der Gruppe Sysadmins (oder Äquivalent) und Mitglied der Gruppe der lokalen Administratoren von SQL Server.</p></td>
<td><p>Lync Server 2013-Administrator ist Mitglied von RTCUniversalServerAdmins</p></td>
<td><p>Der lync Server 2013-Administrator kann lync Server 2013 installieren, die Datenbankenkönnen aber nicht installiert werden. Der SQL Server-Administrator verwendet die lync Server-Verwaltungsshell und die Windows PowerShell-Cmdlets, die vom lync Server 2013-Administrator bereitgestellt werden, um die Datenbanken zu installieren. Die vom SQL Server-Administrator verwendete lync Server 2013-Verwaltungsshell ist auf dem Front-End-Server installiert. Dadurch entfällt die Notwendigkeit, die lync Server 2013-Verwaltungstools auf dem SQL Server-basierten Server zu installieren.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

