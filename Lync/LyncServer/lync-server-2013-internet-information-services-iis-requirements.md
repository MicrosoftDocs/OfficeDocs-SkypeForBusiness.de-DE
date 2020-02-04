---
title: 'Lync Server 2013: IIS-Anforderungen (Internetinformationsdienste)'
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
ms.openlocfilehash: 3f4b51ac4996e2556ced3ad91e15a6cc58a1623c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725805"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a>IIS-Anforderungen (Internetinformationsdienste) in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-19_

Mehrere lync Server 2013-Komponenten erfordern Internet Informationsdienste (IIS). In diesem Thema werden die speziellen IIS-Features beschrieben, die für die Unterstützung von lync Server erforderlich sind. In den Themen in diesem Abschnitt werden die Anforderungen bestimmter Komponenten für IIS beschrieben.

Wenn die Rolle des Webservers (IIS) unter Windows Server 2008 aktiviert ist, werden standardmäßig verschiedene Rollendienste installiert. In der folgenden Tabelle werden die zusätzlichen Rollendienste beschrieben, die installiert werden müssen, wenn die Webserver (IIS)-Rolle unter Windows Server 2008 aktiviert ist.


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


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="Sicherheits" alt="security" />Sicherheitshinweis:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Wenn Sie IIS 7,0 unter einem Windows Server 2008-Betriebssystem verwenden, deaktiviert das lync Server-Setup die Kernelmodus-Authentifizierung in IIS.</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [IIS-Anforderungen für Front-End-Pools und Standard Edition-Server in Lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

