---
title: 'Lync Server 2013: Zertifikatzusammenfassung-Reverseproxy'
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
ms.openlocfilehash: 460d36723cd084ad4593318cdd04f5e05b90d08a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a>Zertifikatzusammenfassung-Reverseproxy in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-14_

Die Zertifikatanforderungen für den Reverseproxy sind wesentlich einfacher als für die Edgeserver. Das bereitgestellte Flussdiagramm stellt die erforderlichen Anforderungen dar. In der begleitenden Tabelle werden typische Zertifikatsantrags Teller Namen und alternative Antragstellernamen im Zusammenhang mit den Szenarien dargestellt, die wir in den Edgeserver Diskussionen überprüft haben. Weitere Informationen zu den Edgeserver Szenarien finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**Flussdiagramm für Zertifikate für Reverse-Proxy**

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
<th>Antragstellername</th>
<th>Alternativer Antragstellername (San)/Order</th>
<th>Anmerkungen</th>
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
<td><p>Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle und mit der Server-EKU ausgestellt werden. Zu den Diensten gehören Adressbuchdienst, Expansion von Verteilergruppen für Office-Webanwendungen für Konferenzen und Veröffentlichungsregeln für lync-IP-Geräte. Alternative Antragstellernamen:</p>
<ul>
<li><p>Externer Webdienste FQDN für Front-End-Server oder Front-End-Pool</p></li>
<li><p>Externer Webdienste FQDN für Director oder Directorpool</p></li>
<li><p>Einwahlkonferenz</p></li>
<li><p>Veröffentlichungsregel für Online Besprechungen</p></li>
<li><p>Office-Webanwendungen für Konferenzen</p></li>
<li><p>Lyncdiscover (AutoErmittlung)</p></li>
</ul>
<p>Der optionale Platzhalter ersetzt "Meet" und "Dialin San".</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

