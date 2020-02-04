---
title: 'Lync Server 2013: Zertifikatzusammenfassung für Reverseproxy'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42e52fa8522de53404fee3f3b5798f159361dbf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a>Zertifikatzusammenfassung für Reverseproxy in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-14_

Die Zertifikatanforderungen für den Reverse-Proxy sind viel einfacher als die für die Edgeserver. Das bereitgestellte Flussdiagramm stellt die erforderlichen Anforderungen dar. In der zugehörigen Tabelle werden typische Namen für Zertifikats Subjekte und andere Alternative Namen in Bezug auf die Szenarien vorgestellt, die in den Edge-Server-Diskussionen besprochen wurden. Weitere Informationen zu den Edge-Server-Szenarien finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**Flussdiagramm für Zertifikate für den Reverse-Proxy**

![Flussdiagramm für Zertifikate für Edgeserver](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Flussdiagramm für Zertifikate für Edgeserver")

### <a name="reverse-proxy-external-interface"></a>Reverse Proxy: externe Schnittstelle

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
<th>Subject Alternative Name (San)/Order</th>
<th>Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Reverseproxy</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>webext.contoso.com</p>
<p>webdirext.contoso.com</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>officewebapps01.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(Optional):*. contoso.com</p></td>
<td><p>Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle und mit der Server-EKU ausgestellt werden. Zu den Diensten gehören der Adressbuchdienst, die Expansion der Verteilergruppe in Office Web Apps für Konferenzen und die Veröffentlichungsregeln für lync-IP-Geräte. Der Alternative Antragstellername umfasst:</p>
<ul>
<li><p>FQDN für externe Webdienste für Front-End-Server oder Front-End-Pool</p></li>
<li><p>FQDN des externen Webdiensts für Director oder Director-Pool</p></li>
<li><p>Einwahlkonferenzen</p></li>
<li><p>Veröffentlichungsregel für Online Besprechungen</p></li>
<li><p>Office Web Apps für Konferenzen</p></li>
<li><p>Lyncdiscover (AutoErmittlung)</p></li>
</ul>
<p>Der optionale Platzhalter ersetzt sowohl Meet als auch Dialin San</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

