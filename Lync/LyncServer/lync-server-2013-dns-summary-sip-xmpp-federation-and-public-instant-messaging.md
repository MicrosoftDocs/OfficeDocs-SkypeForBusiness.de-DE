---
title: DNS-Zusammenfassung – SIP, XMPP Federation und Public Instant Messaging
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c22b38fdb9e936df8b3fd148022acdbd857cdcfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>DNS-Zusammenfassung – SIP, XMPP Federation und Public Instant Messaging in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2017-03-09_

Die DNS-Einträge (Domain Name System), die erforderlich sind, um einen Verbund mit Office Communications Server-oder lync Server-Partnern zu definieren, werden durch ihre Entscheidung bestimmt, die automatische DNS-Erkennung Ihrer Domäne durch andere Perspective-Partner zu ermöglichen. Wenn Sie die \_sipfederationtls veröffentlichen. \_TCP. *SIP-Domänenname\> \<* SRV-Eintrag, kann jede andere SIP-Verbunddomäne ihren Verbund "entdecken". Sie können steuern, welche Verbunddomänen mit Ihnen kommunizieren können, indem Sie die Einstellungen Domänen und Blockierte Domänen in der lync Server-Systemsteuerung zulassen oder die Konfiguration der zugelassenen oder blockierten Domänen mithilfe der lync Server-Verwaltungsshell und der ** Get**-, **Sets**-, **New**-, **Remove-CsAllowedDomain** -und **-CsBlockedDomain-PowerShell-** Cmdlets. Weitere Informationen zum Konfigurieren dieser Einstellungen und zur Verwendung der PowerShell-Cmdlets finden Sie unter " **Verwandte Themen** " am Ende dieses Themas.

In der Tabelle "Zusammenfassung der DNS-Einträge" werden die erforderlichen Einträge für eine offene oder auffindbare Föderation dargestellt. Wenn Sie die Verbund Ermittlung nicht implementieren möchten, können Sie sich entscheiden, die \_sipfederationtls nicht zu konfigurieren. \_TCP. *SIP-Domänen\> Namen Eintrag. \<*

<div>


> [!IMPORTANT]
> Es gibt bestimmte Szenarien, in denen Sie über die _sipfederationtls. _tcp verfügen müssen. <EM>SIP-Domänenname&gt; &lt;</EM> SRV-Eintrag, aber Sie möchten keinen auffindbaren Verbund haben. In einem solchen Fall haben Sie die Mobilität für Ihre Benutzer bereitgestellt. Das Mobility Push Notification Clearing House (PNCH) ist ein spezieller Föderations, der für Microsoft lync Mobile-Clients auf Apple iPhone oder iPad mit dem lync 2010-Mobilclient oder Windows Phone mit den mobilen lync 2010 Mobile-oder lync 2013-Clients verwendet wird. Die _sipfederationtls. _tcp. <EM>SIP-Domänenname&gt; &lt;</EM> SRV-Eintrag wird im Fall von Mobilität und Push-Benachrichtigung verwendet. Um dieses Problem zu vermeiden und ihre Auffindbarkeit zu kontrollieren, deaktivieren Sie die Einstellung <STRONG>enable Partner Domain Discovery</STRONG> , um Discovery zu deaktivieren.



</div>

Zum Konfigurieren von xmpp (Extensible Messaging and Presence Protocol) für Ihre Bereitstellung erstellen Sie zwei DNS-Einträge (Domain Name System) auf einem externen DNS-Server, die die Datensätze in den Access-Edgedienst Ihres Edge-Servers oder Edge-Pools auflösen.

Wenn Sie DNS (Domain Name System) für die öffentliche Instant Messaging-Konnektivität konfigurieren, werden Sie feststellen, dass die Konfiguration, die externe Benutzer unterstützt, öffentliche Chat Verbindungen unterstützt. Wenn Sie Ihren Edge-Server oder Edge-Pool bereits konfiguriert haben, sollten Sie über die DNS-Einträge verfügen, die für die Unterstützung öffentlicher Chat Verbindungen erforderlich sind.

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a>DNS-Zusammenfassung – SIP-Föderation einschließlich öffentlicher Instant Messaging-Konnektivität


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
<th>FQDN</th>
<th>IP-Adresse/FQDN-Hosteintrag</th>
<th>Karten/Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externer DNS/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Die externe Schnittstelle für den Zugriff auf den Edgedienst ist für die automatische DNS-Erkennung Ihres Verbandes zu anderen potenziellen Verbundpartnern erforderlich und wird als "zugelassene SIP-Domänen" bezeichnet (genannt Enhanced Federation in früheren Versionen). Wiederholen Sie diese Schritte für alle SIP-Domänen mit lync-aktivierten Benutzern.</p>



> [!IMPORTANT]
> Dieser SRV-Eintrag ist für Mobilität und das Clearing House für die Push-Benachrichtigung erforderlich. In Fällen, in denen mehrere SIP-Domänen vorhanden sind, erstellen und veröffentlichen Sie einen SRV-Eintrag für jede Domäne, die lync Mobile-Clients enthält. Der Push-Benachrichtigungsdienst und der Apple Push-Benachrichtigungsdienst funktionieren möglicherweise nicht wie erwartet, wenn kein expliziter SRV-Eintrag für die einzelnen SIP-Domänen vorhanden ist, die die Bereitstellung unterstützt.

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a>DNS Summary – Extensible Messaging and Presence Protocol (XMPP)


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
<th>FQDN</th>
<th>IP-Adresse/FQDN-Hosteintrag</th>
<th>Karten/Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externer DNS/SRV/5269</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>XMPP-Proxy-externe Schnittstelle im Access Edge-Dienst oder Edge-Pool. Wiederholen Sie diese Schritte für alle internen SIP-Domänen mit lync-aktivierten Benutzern, bei denen der Kontakt mit XMPP-Kontakten durch die Konfiguration der Richtlinie für den externen Zugriff über eine globale Richtlinie, eine Website Richtlinie, in der sich der Benutzer befindet, oder auf die Benutzerrichtlinie angewendet wird, die auf die Lync-fähiger Benutzer. Eine zulässige XMPP-Domäne muss auch in der XMPP-Föderationspartner-Richtlinie konfiguriert werden. Weitere Informationen finden Sie in den Themen unter <strong>Siehe auch</strong> .</p></td>
</tr>
<tr class="even">
<td><p>Externer DNS/A</p></td>
<td><p>xmpp.contoso.com (Beispiel)</p></td>
<td><p>IP-Adresse des Zugriffs-Edgedienst auf dem Edgeserver oder Edge-Pool, der XMPP-Proxy hostet</p></td>
<td><p>Verweist auf den Access Edge-Dienst oder den Edge-Pool, der den XMPP-Proxydienst hostet. In der Regel verweist der von Ihnen erstellte SRV-Eintrag auf diesen Host-Eintrag (a oder AAAA).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Siehe auch


[Einrichten eines XMPP-Partnerverbunds in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  
[Konfigurieren von Pushbenachrichtigungen in Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)  
[Aktivieren oder Deaktivieren der Suche von Verbundpartnern in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Ermitteln von DNS-Anforderungen für Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Verwalten von SIP-Partnerdomänen für eine Organisation in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

