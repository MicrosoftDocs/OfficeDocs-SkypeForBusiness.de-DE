---
title: 'Lync Server 2013: Bereitstellungsberechtigungen für SQL Server'
TOCTitle: Bereitstellungsberechtigungen für SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398375(v=OCS.15)
ms:contentKeyID: 49294054
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellungsberechtigungen für SQL Server in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Für Microsoft SQL Server 2012 gelten bei der Installation und Bereitstellung von Lync Server 2013 spezifische Anforderungen. Da die Sicherheitseinstellungen in Windows und SQL Server unterschiedlich definiert sind, werden bei der Anmeldung an der Active Directory-Domäne keine impliziten Berechtigungen für SQL Server erteilt. Sie müssen zudem ein Mitglied der sysadmin-Entität auf dem SQL Server-basierten Server sein, den Sie konfigurieren.

## Erforderliche Berechtigungen für die Installation von Datenbank und Lync Server

Die folgenden Optionen zeigen drei Berechtigungsstufen und Gruppenmitgliedschaftszuordnungen für die Installation von Lync Server 2013-Dateien und SQL Server-Datenbanken. Wählen Sie das Szenario, das den Anforderungen Ihrer Organisation am ehesten entspricht.

### Berechtigungen und Gruppenmitgliedschaftszuordnungen

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>SQL Server- oder Lync Server 2013-Rolle</th>
<th>Für die Rolle typische SQL Server-Berechtigungen und Gruppenmitgliedschaft</th>
<th>Für die Rolle typische Lync Server 2013-Berechtigungen und Gruppenmitgliedschaft</th>
<th>Resultierende Berechtigungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013-Administrator</p></td>
<td><p>Mitgliedschaft in der SQL Server-Sicherheitsgruppe &quot;sysadmins&quot; und lokalen Administratorgruppe in SQL Server erforderlich</p></td>
<td><p>Mitgliedschaft in der Gruppe &quot;RTCUniversalServerAdmins&quot; erforderlich</p></td>
<td><p>Der Lync Server 2013-Administrator verfügt über die erforderlichen Berechtigungen für die Installation von Lync Server 2013- und SQL Server-Datenbanken.</p></td>
</tr>
<tr class="even">
<td><p>SQL Server-Administrator</p></td>
<td><p>Mitgliedschaft in der SQL Server-Gruppe &quot;sysadmin&quot; (oder äquivalente Berechtigungen) und Mitgliedschaft in der lokalen Administratorgruppe von SQL Server erforderlich</p></td>
<td><p>Mitgliedschaft in der Gruppe &quot;RTCUniversalServerReadOnly&quot; erforderlich</p></td>
<td><p>Der SQL Server-Administrator verfügt über die erforderlichen Berechtigungen für die Installation von Lync Server 2013- und SQL Server-Datenbanken.</p></td>
</tr>
<tr class="odd">
<td><p>Beide Administratoren sind für Installationsaufgaben verantwortlich</p></td>
<td><p>Der SQL Server-Administrator ist Mitglied der Gruppe &quot;sysadmin&quot; (oder verfügt über äquivalente Berechtigungen) und Mitglied der lokalen Administratorgruppe von SQL Server</p></td>
<td><p>Der Lync Server 2013-Administrator ist Mitglied der Gruppe &quot;RTCUniversalServerAdmins&quot;</p></td>
<td><p>Der Lync Server 2013-Administrator kann Lync Server 2013, jedoch keine Datenbanken installieren. Der SQL Server-Administrator verwendet die vom Lync Server 2013-Administrator bereitgestellten Cmdlets der Lync Server-Verwaltungsshell und der Windows PowerShell, um die Datenbanken zu installieren. Die vom SQL Server-Administrator verwendete Verwaltungsshell für Lync Server 2013 wird auf dem Front-End-Server installiert. Folglich müssen die Lync Server 2013-Verwaltungstools nicht auf dem SQL Server-basierten Server installiert werden.</p></td>
</tr>
</tbody>
</table>

