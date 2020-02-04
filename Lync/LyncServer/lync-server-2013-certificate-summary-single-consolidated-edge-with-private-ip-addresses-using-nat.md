---
title: 'Lync Server 2013: Zertifikatzusammenfassung für einen einzelnen konsolidierten Edgeserver mit privaten IP-Adressen und NAT'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 6de6680e-5f47-48e6-8e06-4994d710ea6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398519(v=OCS.15)
ms:contentKeyID: 48184433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b76ba1e92c6c396b81e0a815a9b1368f90b8b85d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Zertifikatzusammenfassung für einen einzelnen konsolidierten Edgeserver mit privaten IP-Adressen und NAT in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Microsoft lync Server 2013 verwendet Zertifikate zur gegenseitigen Authentifizierung anderer Server und zum Verschlüsseln von Daten von Server zu Server und Server auf dem Client. Für Zertifikate ist eine Namensübereinstimmung der DNS-Einträge (Domain Name System) erforderlich, die den Servern zugeordnet sind, sowie der Antragstellername (SN) und der Alternative Name (Subject Alternative Name, San) auf dem Zertifikat. Damit Server, DNS-Einträge und Zertifikat Einträge erfolgreich zugeordnet werden können, müssen Sie die vollqualifizierten Domänennamen für den vorgesehenen Server sorgfältig planen, wie Sie in DNS und den Einträgen SN und San auf dem Zertifikat registriert sind.

Das Zertifikat, das den externen Schnittstellen des Edge-Servers zugewiesen ist, wird von einer öffentlichen Zertifizierungsstelle angefordert. Öffentliche CAS, die bei der Bereitstellung von Zertifikaten für die Zwecke der Unified Communications erfolgreich sind, sind im folgenden Artikel [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395)aufgeführt:. Wenn Sie das Zertifikat anfordern, können Sie die vom lync Server-Bereitstellungs-Assistenten generierte Zertifikatanforderung verwenden oder die Anforderung manuell mithilfe der lync Server-Verwaltungsshell-Cmdlets oder durch einen Prozess erstellen, der von einer öffentlichen Zertifizierungsstelle bereitgestellt wird. Ausführliche Informationen zu Cmdlets der lync Server-Verwaltungsshell für die Zertifikatverwaltung finden Sie unter [Zertifikats-und Authentifizierungs-Cmdlets in lync Server 2013](https://docs.microsoft.com/powershell/module/skype/) bei der Zuweisung des Zertifikats wird das Zertifikat der Access-Edgedienst-Schnittstelle, der Edgedienst-Schnittstelle für Webkonferenzen und dem Audio/Video-Authentifizierungsdienst zugewiesen. Der Audio-und Video Authentifizierungsdienst sollte nicht mit dem a/V-Edgedienst verwechselt werden, der kein Zertifikat zum Verschlüsseln der Audio-und Videodatenströme verwendet. Die Schnittstelle für den internen Edgeserver kann ein Zertifikat von einer internen Zertifizierungsstelle (in Ihrer Organisation) oder einem Zertifikat einer öffentlichen Zertifizierungsstelle verwenden. Das interne Schnittstellen Zertifikat verwendet nur SN und benötigt keine San-Einträge.

<div>


> [!NOTE]  
> Die folgende Tabelle zeigt einen zweiten SIP-Eintrag (SIP.fabrikam.com) in der Liste Betreff-alternativer Name als Referenz. Für jede SIP-Domäne in Ihrer Organisation müssen Sie einen entsprechenden FQDN hinzufügen, der in der Liste Zertifikat Antragsteller-alternativer Name aufgeführt ist.



</div>

<div>

## <a name="certificates-required-for-single-consolidated-edge-with-private-ip-addresses-using-nat"></a>Zertifikate, die für einen einzelnen konsolidierten Edge mit privaten IP-Adressen mithilfe von NAT erforderlich sind


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

