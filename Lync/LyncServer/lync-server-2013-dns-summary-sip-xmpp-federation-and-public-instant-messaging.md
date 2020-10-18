---
title: DNS-Zusammenfassung-SIP, XMPP-Partnerverbund und öffentliche Sofortnachrichten
description: DNS-Zusammenfassung-SIP, XMPP-Partnerverbund und öffentliche Sofortnachrichten.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f40013b8346cc049f844a827b21bef81a66f6950
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572761"
---
# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>DNS-Zusammenfassung – SIP, XMPP-Partnerverbund und öffentliche Chatnachrichten in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2017-03-09_

Die Domain Name System (DNS) Datensätze, die zum Definieren eines Verbunds mit Office Communications Server oder lync Server Partnern erforderlich sind, werden durch ihre Entscheidung bestimmt, die automatische DNS-Ermittlung Ihrer Domäne durch andere Perspective-Partner zuzulassen. Wenn Sie die \_ sipfederationtls veröffentlichen. \_ TCP. *\<SIP domain name\>* SRV-Eintrag, kann jede andere SIP-Verbunddomäne ihren Partnerverbund "ermitteln". Sie können steuern, welche Verbunddomänen mit Ihnen kommunizieren können, indem Sie die Einstellungen für Domänen und Blockierte Domänen in der lync Server-Systemsteuerung zulassen oder die Konfiguration der zugelassenen oder blockierten Domänen mithilfe der lync Server-Verwaltungsshell und der Cmdlets **Get**, **Sets**, **New**, **Remove-CsAllowedDomain** und **-CsBlockedDomain** festlegen. Weitere Informationen zum Konfigurieren dieser Einstellungen und zur Verwendung der PowerShell-Cmdlets finden Sie unter " **Verwandte Themen** " am Ende dieses Themas.

In der Zusammenfassungstabelle für DNS-Einträge werden die erforderlichen Einträge für einen geöffneten oder auffindbaren Partnerverbund dargestellt. Wenn Sie die Verbund Ermittlung nicht implementieren möchten, können Sie sich dafür entscheiden, die sipfederationtls nicht zu konfigurieren \_ . \_ TCP. *\<SIP domain name\>* Datensatz.

<div>


> [!IMPORTANT]
> Es gibt bestimmte Szenarien, in denen Sie über das _sipfederationtls. _tcp verfügen müssen. <EM> &lt; SIP-Domänen &gt; Namen</EM> -SRV-Eintrag, aber Sie möchten keinen auffindbaren Partnerverbund haben. Eine solche Instanz ist der Ort, an dem Sie die Mobilität für Ihre Benutzer bereitgestellt haben. Das Mobility Push Notification Clearing House (PNCH) ist ein spezieller Verbundtyp, der für Microsoft lync Mobile-Clients auf Apple iPhone oder iPad mit dem lync 2010 Mobile-Client oder Windows Phone mit dem lync 2010 Mobile oder lync 2013 mobilen Clients verwendet wird. Die _sipfederationtls. _tcp. <EM> &lt; SIP-Domänen &gt; Namen</EM> -SRV-Eintrag wird im Fall von Mobilität und Push-Benachrichtigung verwendet. Um dieses Problem zu beheben und die Auffindbarkeit zu kontrollieren, deaktivieren Sie die Einstellung <STRONG>Aktivieren der Partnerdomänen Suche</STRONG> , um die Ermittlung zu deaktivieren.



</div>

Zum Konfigurieren von xmpp (Extensible Messaging and Presence Protocol) für Ihre Bereitstellung erstellen Sie zwei DNS-Einträge (Domain Name System) auf einem externen DNS-Server, mit dem die Datensätze in die Zugriffs-Edgedienst ihrer Edgeserver oder Edgepool aufgelöst werden.

Wenn Sie DNS (Domain Name System) für die Verbindung mit öffentlichen Instant Messaging-Diensten konfigurieren, werden Sie feststellen, dass die Konfiguration, die externe Benutzer unterstützt, öffentliche Chat Verbindungen unterstützt. Wenn Sie Ihre Edgeserver oder Edgepool bereits konfiguriert haben, sollten Sie über die erforderlichen DNS-Einträge für die Unterstützung von Verbindungen mit öffentlichen Instant Messaging-Diensten verfügen.

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a>DNS-Zusammenfassung-SIP-Partnerverbund einschließlich der Verbindung mit öffentlichen Instant Messaging-Diensten


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
<th>FQDN</th>
<th>IP-Adresse/FQDN-Hosteintrag</th>
<th>Zugeordnet zu/Kommentar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externe DNS/SRV/5061</p></td>
<td><p>_sipfederationtls _sipfederationtls._tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Zugriffs-Edgedienst externe Schnittstelle, die für die automatische DNS-Ermittlung ihres Verbunds für andere potenzielle Verbundpartner erforderlich ist, und wird als "zugelassene SIP-Domänen" bezeichnet ("Enhanced Federation" in früheren Versionen genannt). Wiederholen bei Bedarf für alle SIP-Domänen mit lync-aktivierten Benutzern</p>



> [!IMPORTANT]
> Dieser SRV-Eintrag ist für die Mobilität und das Push Notification Clearing House erforderlich. Wenn es mehr als eine SIP-Domäne gibt, erstellen und veröffentlichen Sie einen SRV-Eintrag für jede Domäne, die lync Mobile-Clients haben wird. Der Push-Benachrichtigungsdienst und der Apple Push Notification-Dienst funktionieren möglicherweise nicht wie erwartet, wenn kein expliziter SRV-Eintrag für jede SIP-Domäne vorhanden ist, die von der Bereitstellung unterstützt wird.

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a>DNS-Zusammenfassung – xmpp (Extensible Messaging and Presence Protocol)


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
<th>FQDN</th>
<th>IP-Adresse/FQDN-Hosteintrag</th>
<th>Zugeordnet zu/Kommentar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externe DNS/SRV/5269</p></td>
<td><p>_xmpp-Server._tcp. contoso. com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Externe XMPP-Proxyschnittstelle im Zugriffs-Edgedienst oder Edgepool. Wiederholen Sie den Vorgang bei Bedarf für alle internen SIP-Domänen mit lync-aktivierten Benutzern, bei denen Kontakt mit XMPP-Kontakten über die Konfiguration der Richtlinie für den externen Zugriff über eine globale Richtlinie, eine Standortrichtlinie, in der sich der Benutzer befindet, oder eine auf den lync-aktivierten Benutzer angewendete Benutzerrichtlinie zulässig ist. Eine zulässige XMPP-Domäne muss auch in der XMPP-Verbundpartner Richtlinie konfiguriert werden. Weitere Informationen finden Sie Unterthemen in <strong>Siehe auch</strong> .</p></td>
</tr>
<tr class="even">
<td><p>Externe DNS/A</p></td>
<td><p>xmpp.contoso.com (Beispiel)</p></td>
<td><p>IP-Adresse Zugriffs-Edgedienst auf Ihrem Edgeserver oder Edgepool Hosting XMPP-Proxy</p></td>
<td><p>Verweist auf die Zugriffs-Edgedienst oder Edgepool, die den XMPP-Proxydienst hosten. Der SRV-Eintrag, den Sie erstellen, verweist normalerweise auf diesen Hosteintrag (A oder AAAA).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Siehe auch


[Einrichten des XMPP-Verbunds in lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  
[Konfigurieren von Push-Benachrichtigungen in lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)  
[Aktivieren oder Deaktivieren der Ermittlung von Partnerverbund Partnern in lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Verwalten von SIP-Verbunddomänen für Ihre Organisation in lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

