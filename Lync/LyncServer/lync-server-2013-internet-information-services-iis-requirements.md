---
title: 'Lync Server 2013: IIS-Anforderungen (Internetinformationsdienste)'
TOCTitle: IIS-Anforderungen (Internetinformationsdienste)
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398321(v=OCS.15)
ms:contentKeyID: 49293973
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# IIS-Anforderungen (Internetinformationsdienste) in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Verschiedene Lync Server 2013-Komponenten erfordern die Internetinformationsdienste (Internet Information Services, IIS). In diesem Thema werden die spezifischen IIS-Funktionen beschrieben, die zur Unterstützung von Lync Server erforderlich sind. In den Abschnitten dieses Themas werden die Anforderungen spezifischer Komponenten in Bezug auf IIS erläutert.

Wenn die Webserverrolle (IIS) auf Windows Server 2008 aktiviert wird, werden standardmäßig verschiedene Rollendienste installiert. In der folgenden Tabelle werden die zusätzlichen Rollendienste beschrieben, die bei Aktivierung der Webserverrolle (IIS) auf Windows Server 2008 installiert werden müssen.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Rollendienst</th>
<th>Funktion</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Allgemeine HTTP-Funktionen</p></td>
<td><p>HTTP-Umleitung</p></td>
</tr>
<tr class="even">
<td><p>Anwendungsentwicklung</p></td>
<td><p>ASP.NET</p></td>
</tr>
<tr class="odd">
<td><p>Anwendungsentwicklung</p></td>
<td><p>.NET-Erweiterbarkeit</p></td>
</tr>
<tr class="even">
<td><p>Anwendungsentwicklung</p></td>
<td><p>ISAPI-Erweiterungen</p></td>
</tr>
<tr class="odd">
<td><p>Anwendungsentwicklung</p></td>
<td><p>ISAPI-Filter</p></td>
</tr>
<tr class="even">
<td><p>Integrität und Diagnose</p></td>
<td><p>Protokollierungstools</p></td>
</tr>
<tr class="odd">
<td><p>Integrität und Diagnose</p></td>
<td><p>Ablaufverfolgung</p></td>
</tr>
<tr class="even">
<td><p>Sicherheit</p></td>
<td><p>Standardauthentifizierung</p></td>
</tr>
<tr class="odd">
<td><p>Sicherheit</p></td>
<td><p>Windows-Authentifizierung</p></td>
</tr>
<tr class="even">
<td><p>Verwaltungstools</p></td>
<td><p>IIS-Verwaltungsskripts und -tools</p></td>
</tr>
<tr class="odd">
<td><p>Verwaltungstools</p></td>
<td><p>IIS 6-Verwaltungskompatibilität</p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg399038.security(OCS.15).gif" title="security" alt="security" />Sicherheit Hinweis:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Wenn Sie IIS 7.0 auf einem Windows Server 2008-Betriebssystem verwenden, wird die Kernelmodusauthentifizierung in IIS durch das Lync Server-Setup deaktiviert.</td>
</tr>
</tbody>
</table>


## In diesem Abschnitt

  - [IIS-Anforderungen für Front-End-Pools und Standard Edition-Server in Lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

