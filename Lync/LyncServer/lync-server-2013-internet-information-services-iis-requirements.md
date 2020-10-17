---
title: 'Lync Server 2013: Internet Information Services (IIS) Anforderungen'
description: 'Lync Server 2013: Internet Information Services (IIS) Anforderungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd8de55fa4611c3ab29eac7d7c28c522b418e77d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543991"
---
# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a>Internet Information Services (IIS) Anforderungen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-19_

Mehrere lync Server 2013 Komponenten erfordern Internet Information Services (IIS). In diesem Thema werden die spezifischen IIS-Features beschrieben, die zur Unterstützung von lync Server erforderlich sind. In den Abschnitten dieses Themas werden die Anforderungen spezifischer Komponenten in Bezug auf IIS erläutert.

Wenn die Webserverrolle (IIS) auf Windows Server 2008 aktiviert wird, werden standardmäßig verschiedene Rollendienste installiert. In der folgenden Tabelle werden die zusätzlichen Rollendienste beschrieben, die bei Aktivierung der Webserverrolle (IIS) auf Windows Server 2008 installiert werden müssen.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Rollendienst</th>
<th>Feature</th>
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
<td><p>Tracing</p></td>
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


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="Sicherheits" alt="security" />Sicherheitshinweis:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Wenn Sie IIS 7,0 auf einem Windows Server 2008 Betriebssystem verwenden, deaktiviert lync Server Setup die Kernelmodus-Authentifizierung in IIS.</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [IIS-Anforderungen für Front-End-Pools und Standard Edition-Server in lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

