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
ms.openlocfilehash: 71fb3052de36a92afb4ed9076820f7fcb2b54997
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a>DNS-Zusammenfassung für einen einzelnen Director in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-20_

Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die für die Unterstützung des einzelnen Directors erforderlich sind. Die Rolle des Directors erfordert ähnliche DNS-Einträge wie der Front-End-Server. Die Anzahl der benötigten Datensätze wird in den für das Director-Zertifikat erforderlichen Alternativen Betreff-Namen widergespiegelt. Anders als der Front-End-Server hostet der Director keine Benutzerkonten oder hostet die Mobilitätsdienste.

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
<th>Ort/Typ/Port</th>
<th>FQDN/DNS-Eintrag</th>
<th>IP-Adresse/FQDN</th>
<th>Karten/Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Internes DNS/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Director</p></td>
<td><p>Director-Hosteintrag für Replikation und Server-zu-Server</p></td>
</tr>
<tr class="even">
<td><p>Internes DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>SIP (Inbound Session Initiation Protocol) von der Schnittstelle des Edge-Servers</p></td>
</tr>
<tr class="odd">
<td><p>Internes DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>Veröffentlichte Dialin-Webdienste vom Reverse-Proxy</p></td>
</tr>
<tr class="even">
<td><p>Internes DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>Veröffentlicht Meet Web Services from Reverse Proxy</p></td>
</tr>
<tr class="odd">
<td><p>Internes DNS/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>Veröffentlicht und definiert vom Reverse Proxy Web-Ticket externe Webdienste für den Director</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

