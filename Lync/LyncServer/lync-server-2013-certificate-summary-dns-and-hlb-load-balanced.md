---
title: 'Lync Server 2013: Zertifikatzusammenfassung für DNS- und Hardwarelastenausgleich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - DNS and HLB load balanced
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48184676
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e145e2f1ac3d331906713584b365adf7cd48aec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>Zertifikatzusammenfassung für DNS- und Hardwarelastenausgleich in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Die Zertifikatanforderungen für einen Director mit DNS-Lastenausgleich und einem Hardware Lastenausgleichsmodul verwenden ein Standardzertifikat, das einen Antragstellernamen und einen alternativen Betreff für Dienste enthält, die der Director empfangen kann. Für jeden Director im Pool wird ein Zertifikat angefordert. Beachten Sie, dass der Hardwarelastenausgleich nur den Datenverkehr vom Reverseproxy abgleicht. Darüber hinaus gibt es ein OAuth-Token Zertifikat für Server-zu-Server-Authentifizierungszwecke, das auf jedem Server installiert ist.

### <a name="certificates-for-director"></a>Zertifikate für Director

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
<th>Subject Alternative Names (San)</th>
<th>Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>dirpool01.contoso.net</p>
<p>dir01.contoso.net</p>
<p>dialin.contoso.com</p>
<p>Meet.contoso.com</p>
<p>lyncdiscoverinternal.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(Optional) *. contoso.com</p></td>
<td><p>Director-Zertifikate können entweder von einer intern verwalteten Zertifizierungsstelle (Certification Authority, ca) oder von einer öffentlichen Zertifizierungsstelle angefordert werden.</p>
<p>Der Director antwortet auf Anforderungen vom Reverse-Proxy im Umkreis oder vom Edgeserver. Interne Clients verwenden den Director nicht.</p>
<p>Oder ein Platzhaltereintrag für die einfachen URLs</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Kein Eintrag</p></td>
<td><div>

> [!IMPORTANT]  
> Beachten Sie, dass die minimale Schlüssellänge 1024 ist, aber möglicherweise eine Warnung angezeigt wird, dass die empfohlene Mindestlänge von 2048 Bits beträgt.


</div>
<p>Das OAuthTokenIssuer-Zertifikat ist ein Single-Purpose-Zertifikat zum Zweck der Authentifizierung von Servern in einer großen Umgebung und kann von einer internen Zertifizierungsstelle oder von einer öffentlichen Zertifizierungsstelle angefordert werden. Das Zertifikat ist erforderlich.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

