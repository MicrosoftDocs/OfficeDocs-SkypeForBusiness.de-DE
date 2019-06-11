---
title: 'Lync Server 2013: DNS-Zusammenfassung – AutoErmittlung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64e303ebecc42f03197f6502296c8a2708e97ebf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---autodiscover-in-lync-server-2013"></a>DNS-Zusammenfassung – AutoErmittlung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-13_

Die AutoErmittlung ist ein flexibler Dienst, da Sie die Kommunikation über HTTP oder HTTPS akzeptiert. Um dies zu erreichen, müssen das Domain Name System (DNS) und die von Servern, die den AutoErmittlungsdienst hosten, verwendeten Zertifikate ordnungsgemäß konfiguriert sein. Die Zertifikatanforderungen werden in der [Zertifikats Zusammenfassung-AutoErmittlung in lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)behandelt.

<div>


> [!IMPORTANT]  
> Die DNS-Nachschlage Logik für die lync Server-Clients verwendet eine bestimmte Reihenfolge der Auflösung. Sie sollten immer die beiden lyncdiscoverinternal-Elemente angeben. &lt;Domäne&gt; und die lyncdiscover. &lt;Domäne&gt; in Ihrem DNS. Mit Ausnahme des lyncdiscoverinternal. &lt;der&gt; Domäneneintrag führt dazu, dass interne Clients keine Verbindung mit den vorgesehenen Diensten herstellen oder die falsche Antwort auf die AutoErmittlung erhalten.



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
<td><p>Lyncdiscoverinternal. &lt;Interner Domänenname&gt;</p></td>
<td><p>Interner FQDN des Webdiensts für Ihren Director-Pool, falls vorhanden, oder für Ihren Front-End-Pool, wenn Sie keinen Director haben.</p></td>
</tr>
<tr class="even">
<td><p>A (Host, wenn IPv6; AAAA)</p></td>
<td><p>lyncdiscoverinternal. &lt;Interner Domänenname&gt;</p></td>
<td><p>Interne Webdienste-IP-Adresse (virtuelle IP-Adresse (VIP-Adresse), wenn Sie ein Lastenausgleichsmodul verwenden) Ihres Director-Pools, falls vorhanden, oder des Front-End-Pools, wenn Sie keinen Director haben.</p></td>
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
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>Externer Webdienst-FQDN für Ihren Director-Pool, falls vorhanden, oder für Ihren Front-End-Pool, wenn Sie keinen Director haben.</p></td>
</tr>
<tr class="even">
<td><p>A (Host, wenn IPv6; AAAA)</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>Externe oder öffentliche IP-Adresse des Reverse-Proxys.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Externer Datenverkehr führt den Reverse-Proxy durch.



</div>

<div>


> [!NOTE]  
> Clients für mobile Geräte unterstützen nicht mehrere SSL-Zertifikate (Secure Sockets Layer) aus verschiedenen Domänen. Daher wird die CNAME-Umleitung zu verschiedenen Domänen nicht über HTTPS unterstützt. Ein DNS-CNAME-Eintrag für lyncdiscover.contoso.com, der an eine Adresse von Director.contoso.net umgeleitet wird, wird beispielsweise nicht über HTTPS unterstützt. In einer solchen Topologie muss ein Client für mobile Geräte http für die erste Anforderung verwenden, damit die CNAME-Umleitung über HTTP aufgelöst wird. Nachfolgende Anforderungen verwenden dann HTTPS. Zur Unterstützung dieses Szenarios müssen Sie den Reverse-Proxy mit einer Webveröffentlichungsregel für Port 80 (http) konfigurieren. Ausführliche Informationen finden Sie unter "So erstellen Sie eine Webveröffentlichungsregel für Port 80" unter <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Konfigurieren des Reverse-Proxys für Mobilität in lync Server 2013</A>. Die CNAME-Umleitung zur gleichen Domäne wird über HTTPS unterstützt. In diesem Fall umfasst das Zertifikat der Zieldomäne die ursprüngliche Domäne.



</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren des Reverseproxys für Mobilität in Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[Zertifikatzusammenfassung – AutoErmittlung in lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

