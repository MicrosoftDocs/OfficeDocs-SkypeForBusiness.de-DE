---
title: 'Lync Server 2013: DNS-Zusammenfassung-DNS-und HLB-Lastenausgleich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6a3dc04856e1727c3982864995494cee751f457
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532152"
---
# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>DNS-Zusammenfassung-DNS-und HLB-Lastenausgleich in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-20_

Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die zur Unterstützung des Directors für DNS-Lastenausgleich und Hardwarelastenausgleich erforderlich sind. Die Rolle des Directors erfordert ähnliche DNS-Einträge wie die Front-End-Server. Die erforderliche Anzahl von Datensätzen wird in den für das Director-Zertifikat erforderlichen alternativen Antragstellernamen reflektiert. Anders als die Front-End-Server, hostet der Directorpool keine Benutzerkonten oder hostet die Mobilitätsdienste.

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a>Für den Directorpool erforderliche DNS-Einträge bei Verwendung des DNS-Lastenausgleichs und des Hardwarelastenausgleichs

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
<td><p>Internes DNS/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>Directorpool</p></td>
<td><p>Host Eintrag für die Directorpool für den DNS-Lastenausgleich für Server-zu-Server</p></td>
</tr>
<tr class="odd">
<td><p>Interne DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Directorpool</p></td>
<td><p>SIP (Inbound Session Initiation Protocol) von der internen Schnittstelle des Edgeserver</p></td>
</tr>
<tr class="even">
<td><p>Interne DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Directorpool-HLB-VIP</p></td>
<td><p>Hardwaregerät zum Lastenausgleich des veröffentlichten Dialin-Webdiensts vom Reverseproxy</p></td>
</tr>
<tr class="odd">
<td><p>Internes DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Directorpool-HLB-VIP</p></td>
<td><p>Hardwaregerät zum Lastenausgleich des veröffentlichten Besprechungs-Webdiensts vom Reverseproxy</p></td>
</tr>
<tr class="even">
<td><p>Internes DNS/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>Directorpool-HLB-VIP</p></td>
<td><p>Von den externen Webticket-Webdiensten des Reverseproxy mit Hardwarelastenausgleich veröffentlichter und definierter Reverseproxy für den Directorpool</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

