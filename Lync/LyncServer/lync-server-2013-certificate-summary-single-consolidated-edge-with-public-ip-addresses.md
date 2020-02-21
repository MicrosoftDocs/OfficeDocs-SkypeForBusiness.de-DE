---
title: Zertifikatzusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Single consolidated edge with public IP addresses
ms:assetid: 25b8ae7a-e5a0-43c0-92ae-7e144d5e4a36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204747(v=OCS.15)
ms:contentKeyID: 48183653
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11f1658ed907018e71590ad2ff60120fb6336ccd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Zertifikatzusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-08_

Microsoft lync Server 2013 verwendet Zertifikate, um andere Server gegenseitig zu authentifizieren und Daten von Server zu Server und Server auf dem Client zu verschlüsseln. Zertifikate erfordern einen Namensabgleich der Datensätze des Domain Name System (DNS), die den Servern und dem Antragstellernamen (SN) und dem alternativen Antragstellernamen (SAN) auf dem Zertifikat zugewiesen sind. Um Serverpfade, DNS-Datensätze und Zertifikateinträge erfolgreich zuzuordnen, müssen Sie die vorgesehenen vollständig qualifizierten Domänennamen Ihrer Server sorgfältig so planen, wie sie im DNS sowie den SN- und SAN-Einträgen im Zertifikat registriert sind.

Das Zertifikat, das den externen Schnittstellen des Edgeserver zugewiesen ist, wird von einer öffentlichen Zertifizierungsstelle angefordert. Öffentliche Zertifizierungsstellen, die den Erfolg bei der Bereitstellung von Zertifikaten für Unified Communications bewiesen haben, sind im folgenden [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395) Artikel aufgeführt: Wenn Sie das Zertifikat anfordern, können Sie die vom lync Server-Bereitstellungs-Assistenten generierte Zertifikatanforderung verwenden oder die Anforderung manuell oder durch einen Prozess erstellen, der von der öffentlichen Zertifizierungsstelle bereitgestellt wird. Beim Zuweisen des Zertifikats wird das Zertifikat der Zugriffs-Edgedienst-Schnittstelle, der Webkonferenz-Edgedienst-Schnittstelle und dem Audio/Video-Authentifizierungsdienst zugewiesen. Der Audio/Video-Authentifizierungsdienst sollte nicht mit dem A/V-Edgedienst verwechselt werden, der kein Zertifikat zum Verschlüsseln der Audio-und Videodatenströme verwendet. Die interne Edgeserver Schnittstelle kann ein Zertifikat von einer internen Zertifizierungsstelle (in Ihrer Organisation) oder ein Zertifikat von einer öffentlichen Zertifizierungsstelle verwenden. Das Zertifikat für die interne Schnittstelle verwendet nur den Antragstellernamen und benötigt und verwendet keine Einträge für alternative Antragstellernamen.

<div>


> [!NOTE]
> Die folgende Tabelle zeigt zu Referenzzwecken einen sekundären SIP-Eintrag (sip.fabrikam.com) in der Liste für alternative Antragstellernamen. Für jede SIP-Domäne in Ihrer Organisation muss ein entsprechender FQDN in der Liste der alternativen Antragstellernamen des Zertifikats hinzugefügt werden.



</div>

<div>

## <a name="certificates-required-for-single-consolidated-edge-with-public-ip-addresses"></a>Erforderliche Zertifikate für eine Umgebung mit einem einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen


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
<th>Antragstellername (SN)</th>
<th>Alternative Antragstellernamen (SAN)/Reihenfolge</th>
<th>Anmerkungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Einzelner konsolidierter Edgeserver (externer Edge)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle stammen und über die Server-EKU und die Client-EKU verfügen, wenn eine Verbindung mit öffentlichen Instant Messaging-Diensten von AOL bereitgestellt werden soll. Das Zertifikat ist den externen Edgeschnittstellen für Folgendes zugewiesen:</p>
<ul>
<li><p>Zugriffs-Edgeserver</p></li>
<li><p>Konferenz-Edgeserver</p></li>
<li><p>A/V-Edgeserver</p></li>
</ul>
<p>Beachten Sie, dass SANs dem Zertifikat automatisch hinzugefügt werden, basierend auf Ihren Definitionen im Topologie-Generator. Sie können SAN-Einträge für zusätzliche SIP-Domänen und andere Einträge, die Sie unterstützen müssen, nach Bedarf hinzufügen. Der Antragstellername wird im SAN repliziert und muss zum korrekten Betrieb vorhanden sein.</p></td>
</tr>
<tr class="even">
<td><p>Einzelner konsolidierter Edgeserver (interner Edge)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>Kein SAN erforderlich</p></td>
<td><p>Ein Zertifikat kann von einer öffentlichen oder privaten Zertifizierungsstelle ausgegeben werden und muss die Server-EKU enthalten. Das Zertifikat ist der internen Edgeschnittstelle zugewiesen.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a>Zertifikatzusammenfassung – Verbindung mit öffentlichen Instant Messaging-Diensten


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
<td><p>Externer Edgeserver/Zugriffsedge</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle stammen und über die Server-EKU und die Client-EKU verfügen, wenn eine Verbindung mit öffentlichen Instant Messaging-Diensten von AOL bereitgestellt werden soll. Das Zertifikat ist den externen Edgeschnittstellen für Folgendes zugewiesen:</p>
<ul>
<li><p>Zugriffs-Edgeserver</p></li>
<li><p>Konferenz-Edgeserver</p></li>
<li><p>A/V-Edgeserver</p></li>
</ul>
<p>Beachten Sie, dass SANs dem Zertifikat automatisch hinzugefügt werden, basierend auf Ihren Definitionen im Topologie-Generator. Sie können SAN-Einträge für zusätzliche SIP-Domänen und andere Einträge, die Sie unterstützen müssen, nach Bedarf hinzufügen. Der Antragstellername wird im SAN repliziert und muss zum korrekten Betrieb vorhanden sein.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>Zertifikatzusammenfassung für Extensible Messaging and Presence Protocol


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
<p>xmpp.contoso.com</p>
<p><strong>*. contoso.com</strong></p></td>
<td><p>Die ersten drei San-Einträge sind die normalen San-Einträge für eine vollständige Edgeserver. "contoso.com" ist der erforderliche Eintrag für den Partnerverbund mit dem XMPP-Partner auf Stammdomänenebene. Dieser Eintrag ermöglicht die Verwendung von XMPP für alle Domänen mit dem Suffix *.contoso.com.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

