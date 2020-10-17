---
title: 'Lync Server 2013: DNS-Zusammenfassung für einen einzelnen Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1eaaebf1fb695bc1ee6ea1b86f980a666cf0a70
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515532"
---
# <a name="dns-summary---single-director-in-lync-server-2013"></a>DNS-Zusammenfassung für einen einzelnen Director in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-20_

Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die zur Unterstützung des einzelnen Directors erforderlich sind. Die Rolle des Directors erfordert ähnliche DNS-Einträge wie die Front-End-Server. Die erforderliche Anzahl von Datensätzen wird in den für das Director-Zertifikat erforderlichen alternativen Antragstellernamen reflektiert. Anders als die Front-End-Server, hostet der Director keine Benutzerkonten oder hostet die Mobilitätsdienste.

### <a name="dns-records-required-for-the-director"></a>Für den Director erforderliche DNS-Einträge

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Standort/Typ/Port</th>
<th>FQDN/DNS-Eintrag</th>
<th>IP-Adresse/FQDN</th>
<th>Zugeordnet zu/Kommentar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interne DNS/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Director</p></td>
<td><p>Director-Hosteintrag für Replikation und Server-zu-Server</p></td>
</tr>
<tr class="even">
<td><p>Interne DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>SIP (Inbound Session Initiation Protocol) von der internen Edge-Schnittstelle des Edgeserver</p></td>
</tr>
<tr class="odd">
<td><p>Interne DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>Veröffentlichte Dialin-Webdienste vom Reverseproxyserver</p></td>
</tr>
<tr class="even">
<td><p>Interne DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>Veröffentlichte Meet-Webdienste vom Reverseproxyserver</p></td>
</tr>
<tr class="odd">
<td><p>Interne DNS/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>Veröffentlicht und definiert durch das Reverse-Proxy-WebTICKET externe Webdienste für den Director</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

