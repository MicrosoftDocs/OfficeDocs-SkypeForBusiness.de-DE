---
title: 'Lync Server 2013: Zertifikatzusammenfassung – XMPP-Partnerverbund (Extensible Messaging and Presence Protocol)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49105661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45758175a04bad0cc673242087c0a4751c1b01bc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Zertifikatzusammenfassung – XMPP-Partnerverbund (Extensible Messaging and Presence Protocol) in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-12-23_

Zertifikatsanforderungen für das Aktivieren und Einrichten von Kommunikationen mit XMPP-Partnern (Extensible Messaging and Presence Protocol) erfordern den zusätzlichen Eintrag in Ihren XMPP-Domänen. Der Eintrag, der auf dem Zertifikat als alternativer Antragstellername (SAN) enthalten ist, ist die Domäne, die an XMPP-Kommunikationen teilnehmen kann. Die Domäne kann die Domäne auf Stammebene sein (beispielsweise contoso.com), wenn Sie XMPP für die gesamte Domäne aktivieren möchten, oder sie kann als untergeordnete Domäne (beispielsweise corp.contoso.com, finance.contoso.com) verwendet werden, wenn Sie XMPP für eine Teilmenge an Benutzern aktivieren.

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>Zertifikatzusammenfassung für XMPP


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
<th>Alternative Antragstellernamen (SAN)/Reihenfolge</th>
<th>Anmerkungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Zuweisen zu Zugriffs-Edgedienst von Edgeserver oder Edgepool</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>contoso.com</p></td>
<td><p>Die ersten drei San-Einträge sind die normalen San-Einträge für eine vollständige Edgeserver. "contoso.com" ist der erforderliche Eintrag für den Partnerverbund mit dem XMPP-Partner auf Stammdomänenebene. In diesem Eintrag wird XMPP für alle Domänen mit dem Suffix contoso.com zugelassen.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Siehe auch


[Beispiel für eine XMPP-Konfiguration in lync Server 2013 – XMPP-Partnerverbund mit Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Planen von Edgeserver Zertifikaten in lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  


[Einrichten von Edge-Zertifikaten für lync Server 2013](lync-server-2013-set-up-edge-certificates.md)  
[Request-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[Gruppe-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

