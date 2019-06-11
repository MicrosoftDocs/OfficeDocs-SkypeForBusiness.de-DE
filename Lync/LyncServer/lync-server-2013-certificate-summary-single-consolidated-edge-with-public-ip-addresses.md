---
title: Zertifikatzusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Single consolidated edge with public IP addresses
ms:assetid: 25b8ae7a-e5a0-43c0-92ae-7e144d5e4a36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204747(v=OCS.15)
ms:contentKeyID: 48183653
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07c5bce784c6d05393b38b68c2558362bcb9525f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Zertifikatzusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Microsoft lync Server 2013 verwendet Zertifikate zur gegenseitigen Authentifizierung anderer Server und zum Verschlüsseln von Daten von Server zu Server und Server auf dem Client. Für Zertifikate ist eine Namensübereinstimmung der DNS-Einträge (Domain Name System) erforderlich, die den Servern zugeordnet sind, sowie der Antragstellername (SN) und der Alternative Name (Subject Alternative Name, San) auf dem Zertifikat. Damit Server, DNS-Einträge und Zertifikat Einträge erfolgreich zugeordnet werden können, müssen Sie die vollqualifizierten Domänennamen für den vorgesehenen Server sorgfältig planen, wie Sie in DNS und den Einträgen SN und San auf dem Zertifikat registriert sind.

Das Zertifikat, das den externen Schnittstellen des Edge-Servers zugewiesen ist, wird von einer öffentlichen Zertifizierungsstelle angefordert. Öffentliche Zertifizierungsstellen, die den Erfolg bei der Bereitstellung von Zertifikaten für die Zwecke der Unified Communications bewiesen haben, [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395) sind im folgenden Artikel aufgeführt: Wenn Sie das Zertifikat anfordern, können Sie die vom lync-Server generierte Zertifikatanforderung verwenden. Bereitstellungs-Assistent oder erstellen Sie die Anforderung manuell oder durch einen Prozess, der von der öffentlichen Zertifizierungsstelle bereitgestellt wird. Beim Zuweisen des Zertifikats wird das Zertifikat der Access-Edgedienst-Schnittstelle, der Webkonferenz-Edgedienst-Schnittstelle und dem Audio/Video-Authentifizierungsdienst zugewiesen. Der Audio-und Video Authentifizierungsdienst sollte nicht mit dem a/V-Edgedienst verwechselt werden, der kein Zertifikat zum Verschlüsseln der Audio-und Videodatenströme verwendet. Die Schnittstelle für den internen Edgeserver kann ein Zertifikat von einer internen Zertifizierungsstelle (in Ihrer Organisation) oder einem Zertifikat einer öffentlichen Zertifizierungsstelle verwenden. Das interne Schnittstellen Zertifikat verwendet nur SN und benötigt keine San-Einträge.

<div>


> [!NOTE]
> Die folgende Tabelle zeigt einen zweiten SIP-Eintrag (SIP.fabrikam.com) in der Liste Betreff-alternativer Name als Referenz. Für jede SIP-Domäne in Ihrer Organisation müssen Sie einen entsprechenden FQDN hinzufügen, der in der Liste Zertifikat Antragsteller-alternativer Name aufgeführt ist.



</div>

<div>

## <a name="certificates-required-for-single-consolidated-edge-with-public-ip-addresses"></a>Für einzelne konsolidierte Edges erforderliche Zertifikate mit öffentlichen IP-Adressen


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
<th>Subject Alternative Names (San)/Order</th>
<th>Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Einzelner konsolidierter Rand (externer Rand)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle sein und muss über die Server-EKU und den Client-EKU verfügen, wenn öffentliche Chat Verbindungen mit AOL bereitgestellt werden sollen. Das Zertifikat wird den externen Edge-Schnittstellen für Folgendes zugewiesen:</p>
<ul>
<li><p>Zugriffs-Edge</p></li>
<li><p>Konferenz Kante</p></li>
<li><p>A/V-Edge</p></li>
</ul>
<p>Beachten Sie, dass Sans automatisch dem Zertifikat basierend auf ihren Definitionen im Topologie-Generator hinzugefügt werden. Für zusätzliche SIP-Domänen und andere Einträge, die Sie unterstützen müssen, fügen Sie nach Bedarf San-Einträge hinzu. Der Antragstellername wird im San repliziert und muss für den korrekten Betrieb vorhanden sein.</p></td>
</tr>
<tr class="even">
<td><p>Einzelner konsolidierter Rand (interner Rand)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>Kein San erforderlich</p></td>
<td><p>Das Zertifikat kann von einer öffentlichen oder privaten Zertifizierungsstelle ausgestellt werden und muss die Server-EKU enthalten. Das Zertifikat wird der Schnittstelle für den internen Rand zugewiesen.</p></td>
</tr>
</tbody>
</table>


</div>

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
<td><p>Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle sein und muss über die Server-EKU und den Client-EKU verfügen, wenn öffentliche Chat Verbindungen mit AOL bereitgestellt werden sollen. Das Zertifikat wird den externen Edge-Schnittstellen für Folgendes zugewiesen:</p>
<ul>
<li><p>Zugriffs-Edge</p></li>
<li><p>Konferenz Kante</p></li>
<li><p>A/V-Edge</p></li>
</ul>
<p>Beachten Sie, dass Sans automatisch dem Zertifikat basierend auf ihren Definitionen im Topologie-Generator hinzugefügt werden. Für zusätzliche SIP-Domänen und andere Einträge, die Sie unterstützen müssen, fügen Sie nach Bedarf San-Einträge hinzu. Der Antragstellername wird im San repliziert und muss für den korrekten Betrieb vorhanden sein.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>Zertifikatzusammenfassung für erweiterbares Messaging und Anwesenheits Protokoll


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
<td><p>Zuweisen des Zugriffs-Edgedienst des Edge-Servers oder Edge-Pools</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>xmpp.contoso.com</p>
<p><strong>*.contoso.com</strong></p></td>
<td><p>Die ersten drei San-Einträge sind die normalen San-Einträge für einen Full Edge-Server. Der contoso.com ist der Eintrag, der für den Verbund mit dem XMPP-Partner auf der Stammdomänen Ebene erforderlich ist. Dieser Eintrag ermöglicht XMPP für alle Domänen mit dem Suffix *. contoso.com.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

