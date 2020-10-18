---
title: 'Lync Server 2013: DNS-Zusammenfassung-AutoErmittlung'
description: 'Lync Server 2013: DNS-Zusammenfassung – AutoErmittlung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eef9bd6a2489561145718c7bbf2f710ab0b1f248
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574281"
---
# <a name="dns-summary---autodiscover-in-lync-server-2013"></a>DNS-Zusammenfassung – AutoErmittlung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-13_

Die AutoErmittlung ist ein flexibler Dienst, da Sie die Kommunikation über HTTP oder HTTPS übernimmt. Um dies zu erreichen, müssen das DNS (Domain Name System) und die Zertifikate, die von Servern verwendet werden, die den AutoErmittlungsdienst hosten, ordnungsgemäß konfiguriert werden. Zertifikatanforderungen werden in der [Zertifikatzusammenfassung-AutoErmittlung in lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)behandelt.

<div>


> [!IMPORTANT]  
> Die DNS-Nachschlage Logik für die lync Server Clients verwendet eine bestimmte Lösungsreihenfolge. Sie sollten immer sowohl die "lyncdiscoverinternal"-als auch die. &lt; Domäne &gt; und lyncdiscover. &lt; Domäne &gt; in Ihrem DNS. Ohne "lyncdiscoverinternal". &lt; der Domäneneintrag führt dazu, dass &gt; interne Clients nicht mit den vorgesehenen Diensten verbunden werden oder die falsche Auto Ermittlungs Antwort erhalten.



</div>

### <a name="internal-dns-records"></a>Interne DNS-Einträge

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Eintragstyp</th>
<th>Hostname</th>
<th>Auflösung in</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>"Lyncdiscoverinternal". &lt; Interner Domänenname&gt;</p></td>
<td><p>Interner Webdienste FQDN für Ihren Directorpool, wenn Sie einen haben, oder für Ihre Front-End-Pool, wenn Sie keinen Director haben.</p></td>
</tr>
<tr class="even">
<td><p>A (Host, wenn IPv6, AAAA)</p></td>
<td><p>"lyncdiscoverinternal". &lt; Interner Domänenname&gt;</p></td>
<td><p>Interne Webdienste IP-Adresse (virtuelle IP-Adresse (VIP), wenn Sie einen Lastenausgleich verwenden) Ihres Directorpool, wenn Sie einen haben, oder Ihrer Front-End-Pool, wenn Sie keinen Director haben.</p></td>
</tr>
</tbody>
</table>


Sie müssen einen der folgenden externen DNS-Einträge erstellen:

### <a name="external-dns-records"></a>Externe DNS-Einträge

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Eintragstyp</th>
<th>Hostname</th>
<th>Auflösung in</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover. &lt; sipdomain "&gt;</p></td>
<td><p>Externer Webdienste FQDN für Ihren Directorpool, wenn Sie einen haben, oder für Ihre Front-End-Pool, wenn Sie keinen Director haben.</p></td>
</tr>
<tr class="even">
<td><p>A (Host, wenn IPv6, AAAA)</p></td>
<td><p>lyncdiscover. &lt; sipdomain "&gt;</p></td>
<td><p>Externe oder öffentliche IP-Adresse des Reverse-Proxys.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Externer Datenverkehr wird über den Reverseproxy geleitet.



</div>

<div>


> [!NOTE]  
> Clients mobiler Geräte unterstützen nicht mehrere SSL-Zertifikate (Secure Sockets Layer) von verschiedenen Domänen. Daher wird die CNAME-Umleitung an verschiedene Domänen nicht über HTTPS unterstützt. Beispielsweise wird ein DNS-CNAME-Eintrag für "lyncdiscover.contoso.com", der eine Weiterleitung an eine Adresse von "director.contoso.net" vornimmt, nicht über HTTPS unterstützt. In einer solchen Topologie muss ein Client für ein mobiles Gerät HTTP für die erste Anforderung verwenden, sodass die CNAME-Umleitung über HTTP aufgelöst wird. Für die nachfolgenden Anforderungen wird dann HTTPS verwendet. Um dieses Szenario zu unterstützen, müssen Sie den Reverseproxy mit einer Webveröffentlichungsregel für Port 80 (HTTP) konfigurieren. Ausführliche Informationen finden Sie unter "So erstellen Sie eine Webveröffentlichungsregel für Port 80" unter <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Konfigurieren des Reverseproxys für Mobilität in lync Server 2013</A>. Die CNAME-Umleitung an dieselbe Domäne wird über HTTPS unterstützt. In diesem Fall deckt das Zertifikat der Zieldomäne die ursprüngliche Domäne ab.



</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren des Reverse-Proxys für Mobilität in lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[Zertifikatzusammenfassung-AutoErmittlung in lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

