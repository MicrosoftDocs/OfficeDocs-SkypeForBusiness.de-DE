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
ms.openlocfilehash: 2a6697fdb4910b16592ace53e08dcc754cdb2446
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a>Bereitstellungsberechtigungen für SQL Server in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

Microsoft SQL Server 2012 hat bestimmte Anforderungen beim Installieren und Bereitstellen von lync Server 2013. Da Windows und SQL Server Ihre Sicherheit anders definieren, gewährt die Anmeldung als Administrator in der Active Directory Domäne nicht implizit Berechtigungen für SQL Server. Sie müssen zudem ein Mitglied der sysadmin-Entität auf dem SQL Server-basierten Server sein, den Sie konfigurieren.

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a>Erforderliche Berechtigungen für die Installation von Datenbank und Lync Server

Die folgenden Optionen beschreiben drei Berechtigungen und Gruppen Mitgliedschafts Zuordnungen für die Installation von lync Server 2013 Dateien und SQL Server Datenbanken. Wählen Sie das Szenario, das den Anforderungen Ihrer Organisation am ehesten entspricht.

### <a name="permissions-and-group-membership-associations"></a>Berechtigungen und Gruppenmitgliedschaftszuordnungen

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>SQL Server oder lync Server 2013 Rolle</th>
<th>Für die Rolle typische SQL Server-Berechtigungen und Gruppenmitgliedschaft</th>
<th>Rollen typische lync Server 2013 Berechtigungen und Gruppenmitgliedschaft</th>
<th>Resultierende Berechtigungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 Administrator</p></td>
<td><p>Mitgliedschaft in der SQL Server-Sicherheitsgruppe "sysadmins" und lokalen Administratorgruppe in SQL Server erforderlich</p></td>
<td><p>Mitgliedschaft in der Gruppe "RTCUniversalServerAdmins" erforderlich</p></td>
<td><p>Lync Server 2013 Administrator verfügt über die erforderlichen Berechtigungen zum Installieren von lync Server 2013-und SQL Server Datenbanken.</p></td>
</tr>
<tr class="even">
<td><p>SQL Server-Administrator</p></td>
<td><p>Mitgliedschaft in der SQL Server-Gruppe "sysadmin" (oder äquivalente Berechtigungen) und Mitgliedschaft in der lokalen Administratorgruppe von SQL Server erforderlich</p></td>
<td><p>Mitgliedschaft in der Gruppe "RTCUniversalServerReadOnly" erforderlich</p></td>
<td><p>SQL Server Administrator verfügt über die erforderlichen Berechtigungen zum Installieren von lync Server 2013-und SQL Server Datenbanken.</p></td>
</tr>
<tr class="odd">
<td><p>Beide Administratoren sind für Installationsaufgaben verantwortlich</p></td>
<td><p>Der SQL Server-Administrator ist Mitglied der Gruppe "sysadmin" (oder verfügt über äquivalente Berechtigungen) und Mitglied der lokalen Administratorgruppe von SQL Server</p></td>
<td><p>Lync Server 2013 Administrator ist Mitglied von RTCUniversalServerAdmins</p></td>
<td><p>Der lync Server 2013 Administrator kann lync Server 2013 installieren, aber die Datenbanken nicht installieren. Der SQL Server Administrator verwendet die vom lync Server 2013-Administrator bereitgestellten lync Server-Verwaltungsshell-und Windows PowerShell-Cmdlets zum Installieren der Datenbanken. Die lync Server 2013 Verwaltungsshell, die vom SQL Server-Administrator verwendet wird, wird auf der Front-End-Server installiert. Dadurch entfällt die Notwendigkeit, die lync Server 2013 Verwaltungstools auf dem SQL Server basierten Server zu installieren.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

