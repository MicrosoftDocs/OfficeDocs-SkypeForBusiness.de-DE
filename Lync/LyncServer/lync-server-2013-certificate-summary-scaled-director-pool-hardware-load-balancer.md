---
title: Zertifikatzusammenfassung für skalierte Directorpool, Hardwaregerät zum Lastenausgleich
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Scaled Director pool, hardware load balancer
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48183992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79f0ed7eea237c459ec3d42526f25a2b02429906
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Zertifikatzusammenfassung für skalierte Directorpool, Hardwaregerät zum Lastenausgleich in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-20_

Zertifikatanforderungen für einen Director mit einem Hardwaregerät zum Lastenausgleich verwenden ein Standardzertifikat, das über einen Antragstellernamen und alternative Antragstellernamen für Dienste verfügt, die der Directorpool empfangen kann. Ein Zertifikat wird für jeden Director im Pool angefordert. Darüber hinaus ist ein OAuth-Tokenzertifikat für die Authentifizierung zwischen Servern verfügbar, das auf jedem Server installiert wird.

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a>Zertifikate für einen skalierten Director mit einem Hardwaregerät zum Lastenausgleich

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Komponente</th>
<th>Antragstellername</th>
<th>Alternative Antragstellernamen</th>
<th>Anmerkungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>dirpool01.contoso.net</p>
<p>dir01.contoso.net</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>lyncdiscoverinternal.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(Optional) *.contoso.com</p></td>
<td><p>Director-Zertifikate können von einer intern verwalteten Zertifizierungsstelle (Certification Authority, ca) oder von einer öffentlichen Zertifizierungsstelle angefordert werden.</p>
<p>Der Director antwortet auf Anfragen vom Reverseproxy im Umkreis oder von der Edgeserver.</p>
<p>Oder ein Platzhaltereintrag für die einfachen URLs</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Kein Eintrag</p></td>
<td>


> [!IMPORTANT]
> Beachten Sie, dass die minimale Schlüssellänge 1024 Bit beträgt. Dennoch ist es möglich, dass Sie eine Warnmeldung erhalten, die besagt, dass die empfohlene Mindestlänge 2048 Bit beträgt.


<p>Das OAuthTokenIssuer-Zertifikat dient ausschließlich zum Authentifizieren von Servern in einer großen Umgebung und kann von einer internen oder öffentlichen Zertifizierungsstelle angefordert werden. Das Zertifikat ist erforderlich.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

