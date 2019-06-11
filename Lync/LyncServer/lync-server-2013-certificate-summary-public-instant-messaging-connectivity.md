---
title: 'Lync Server 2013: Zertifikats Zusammenfassung – öffentliche Instant Messaging-Konnektivität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31988207403ef1ccb5ea366da6e1ec6b3d448b4e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>Zertifikats Zusammenfassung – öffentliche Instant Messaging-Konnektivität in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-19_

Wenn Sie Zertifikate für die öffentliche Instant Messaging-Konnektivität konfigurieren möchten, sollten Sie zuerst feststellen, dass sich nichts von anderen SIP Federation-Typen oder sogar Standard-Edgeserver-Zertifikaten unterscheidet, es sei denn, dass America Online (AOL) eine eindeutige Zertifikatkonfiguration. Neben der üblichen Server-Erweiterte Schlüsselverwendung (EKU) erfordert America Online, dass das Zertifikat oder die Zertifikate (im Fall eines Edge-Pools) auch die Client-EKU enthalten. Die Client-EKU ist eine Ergänzung zum Zertifikat und Teil des externen öffentlichen Zertifikats, das Ihrem Edgeserver zugewiesen ist.

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a>Zusammenfassung des Zertifikats – öffentliche Instant Messaging-Konnektivität


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
<th>Name des Antragstellers</th>
<th>Subject Alternative Names (San)/Order</th>
<th>Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Extern/Access-Edge</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle sein und über die Server-EKU und den Client-EKU verfügen, wenn öffentliche Chat Verbindungen mit AOL bereitgestellt werden sollen. Das Zertifikat wird den externen Edgeserver-Schnittstellen für Folgendes zugewiesen:</p>
<ul>
<li><p>Zugriffs-Edgedienst</p></li>
<li><p>Webkonferenz-Edgedienst</p></li>
<li><p>A/V-Edgedienst</p></li>
</ul>
<p>Beachten Sie, dass Sans automatisch dem Zertifikat basierend auf ihren Definitionen im Topologie-Generator hinzugefügt werden. Für zusätzliche SIP-Domänen und andere Einträge, die Sie unterstützen müssen, fügen Sie nach Bedarf San-Einträge hinzu. Der Antragstellername wird im San repliziert und muss für den korrekten Betrieb vorhanden sein.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Siehe auch


[Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

