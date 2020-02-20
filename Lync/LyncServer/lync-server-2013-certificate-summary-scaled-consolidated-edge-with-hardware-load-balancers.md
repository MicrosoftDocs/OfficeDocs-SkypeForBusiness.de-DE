---
title: Zertifikatzusammenfassung für einen skalierten konsolidierten Edgeserver mit Hardwaregerät zum Lastenausgleich
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 894a9f3e-7cba-4915-8fdf-e52f2f25126f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398692(v=OCS.15)
ms:contentKeyID: 48184729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 922853c7fe3ce41d969d6a0af5428a4c1a13f8c3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Zertifikatzusammenfassung für einen skalierten konsolidierten Edgeserver mit Hardwarelastenausgleichs für den Lastenausgleich in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-22_

Microsoft lync Server 2013 verwendet Zertifikate, um andere Server gegenseitig zu authentifizieren und Daten von Server zu Server und Server auf dem Client zu verschlüsseln. Zertifikate erfordern einen Namensabgleich der Datensätze des Domain Name System (DNS), die den Servern und dem Antragstellernamen (SN) und dem alternativen Antragstellernamen (SAN) auf dem Zertifikat zugewiesen sind. Um Serverpfade, DNS-Datensätze und Zertifikateinträge erfolgreich zuzuordnen, müssen Sie die vorgesehenen vollständig qualifizierten Domänennamen Ihrer Server sorgfältig so planen, wie sie im DNS sowie den SN- und SAN-Einträgen im Zertifikat registriert sind.

Das Zertifikat, das den externen Schnittstellen des Edgeserver zugewiesen ist, wird von einer öffentlichen Zertifizierungsstelle angefordert. Öffentliche Zertifizierungsstellen, die den Erfolg bei der Bereitstellung von Zertifikaten für Unified Communications bewiesen haben, sind im folgenden [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395)Artikel aufgeführt:. Wenn Sie das Zertifikat anfordern, können Sie die vom lync Server-Bereitstellungs-Assistenten generierte Zertifikatanforderung verwenden oder die Anforderung manuell oder durch einen Prozess erstellen, der von der öffentlichen Zertifizierungsstelle bereitgestellt wird. Beim Zuweisen des Zertifikats wird das Zertifikat der Zugriffs-Edgedienst-Schnittstelle, der Webkonferenz-Edgedienst-Schnittstelle und dem Audio/Video-Authentifizierungsdienst zugewiesen. Der Audio/Video-Authentifizierungsdienst sollte nicht mit dem A/V-Edgedienst verwechselt werden, der kein Zertifikat zum Verschlüsseln der Audio-und Videodatenströme verwendet. Die interne Edgeserver Schnittstelle kann ein Zertifikat von einer internen Zertifizierungsstelle (in Ihrer Organisation) oder ein Zertifikat von einer öffentlichen Zertifizierungsstelle verwenden. Das Zertifikat für die interne Schnittstelle verwendet nur den Antragstellernamen und benötigt und verwendet keine Einträge für alternative Antragstellernamen.

<div>


> [!NOTE]
> Die folgende Tabelle zeigt zu Referenzzwecken einen sekundären SIP-Eintrag (sip.fabrikam.com) in der Liste für alternative Antragstellernamen. Für jede SIP-Domäne in Ihrer Organisation müssen Sie einen entsprechenden FQDN aus der Liste der alternativen Antragstellernamen des Zertifikats hinzufügen.



</div>

<div>

## <a name="certificates-required-for-scaled-consolidated-edge-with-hardware-load-balancers"></a>Für einen skalierten konsolidierten Edgeserver erforderliche Zertifikate mit Hardware-Lastenausgleich


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
<td><p>Einzelne konsolidierte Edgeserver (externer Edge)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle stammen und über die Server-EKU und die Client-EKU verfügen, wenn eine Verbindung mit öffentlichen Instant Messaging-Diensten von AOL bereitgestellt werden soll. Darüber hinaus muss für skalierte Edgeserver der private Zertifikatschlüssel exportierbar sein, und das Zertifikat und der private Schlüssel werden in jede Edgeserver kopiert. das Zertifikat wird den externen Edge-Schnittstellen für Folgendes zugewiesen:</p>
<ul>
<li><p>Zugriffs-Edgedienst</p></li>
<li><p>Webkonferenz-Edgedienst</p></li>
<li><p>A/V-Edgedienst</p></li>
</ul>
<p>Beachten Sie, dass SANs dem Zertifikat automatisch hinzugefügt werden, basierend auf Ihren Definitionen im Topologie-Generator. Sie können SAN-Einträge für zusätzliche SIP-Domänen und andere Einträge, die Sie unterstützen müssen, nach Bedarf hinzufügen. Der Antragstellername wird im SAN repliziert und muss zum korrekten Betrieb vorhanden sein.</p></td>
</tr>
<tr class="even">
<td><p>Einzelner konsolidierter Edgeserver (interner Edge)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>Kein SAN erforderlich</p></td>
<td><p>Ein Zertifikat kann von einer öffentlichen oder privaten Zertifizierungsstelle ausgegeben werden und muss die Server-EKU enthalten. Das Zertifikat wird der internen Edgeserver-Schnittstelle zugewiesen.</p></td>
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
<td><p>Extern/Zugriffs-Edgedienst</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle stammen und über die Server-EKU und die Client-EKU verfügen, wenn eine Verbindung mit öffentlichen Instant Messaging-Diensten von AOL bereitgestellt werden soll. Das Zertifikat ist den externen Edgeschnittstellen für Folgendes zugewiesen:</p>
<ul>
<li><p>Zugriffs-Edgedienst</p></li>
<li><p>Webkonferenz-Edgedienst</p></li>
<li><p>A/V-Edgedienst</p></li>
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

