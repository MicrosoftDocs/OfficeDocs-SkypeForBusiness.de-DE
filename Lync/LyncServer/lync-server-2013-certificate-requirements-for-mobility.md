---
title: 'Lync Server 2013: Zertifikatanforderungen für die Mobilität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c3bf95f87fa663331f05861f91cd7f7f19a2728
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a>Zertifikatanforderungen für die Mobilität in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-24_

Wenn Sie das Mobilitätsfeature bereitstellen und die automatische Ermittlung für mobile Clients unterstützten, müssen Sie für Zertifikate bestimmte Einträge für alternative Antragstellernamen einfügen, um sichere Verbindungen von den mobilen Clients aus zu unterstützen.

Zur Unterstützung der automatischen Ermittlung müssen Sie für folgende Zertifikate Einträge für alternative Antragstellernamen einfügen:

  - Directorpool

  - Front-End-Pool

  - Reverseproxy

In diesem Abschnitt werden die Einträge für alternative Antragstellernamen beschrieben, die zur Unterstützung der automatischen Ermittlung für Zertifikate erforderlich sind.

<div>


> [!NOTE]  
> Das erneute Ausstellen von Zertifikaten mithilfe einer internen Zertifizierungsstelle ist normalerweise ein einfacher Vorgang, aber das Hinzufügen von Einträgen für mehrere alternative Antragstellernamen zu öffentlichen Zertifikaten, die vom Reverseproxy verwendet werden, kann kostspielig sein. Wenn Sie über zahlreiche SIP-Domänen verfügen und das Hinzufügen von alternativen Antragstellernamen sehr kostspielig ist, können Sie den Reverseproxy so konfigurieren, dass er http für die anfängliche AutoErmittlungsdienst Anforderung verwendet, anstatt HTTPS zu verwenden (Standardkonfiguration). Ausführliche Informationen finden Sie unter <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical Requirements for Mobility in lync Server 2013</A>.



</div>

### <a name="director-pool-certificate-requirements"></a>Directorpool-Zertifikatanforderungen

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Beschreibung</th>
<th>Eintrag für alternativen Antragstellernamen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interne URL des AutoErmittlungsdiensts</p></td>
<td><p>San = "lyncdiscoverinternal". &lt;sipdomain "&gt;</p></td>
</tr>
<tr class="even">
<td><p>Externe URL des AutoErmittlungsdiensts</p></td>
<td><p>San = lyncdiscover. &lt;sipdomain "&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Alternativ können Sie San = * verwenden. &lt;sipdomain "&gt;



</div>

### <a name="front-end-pool-certificate-requirements"></a>Front-End-Pool-Zertifikatanforderungen

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Beschreibung</th>
<th>Eintrag für alternativen Antragstellernamen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interne URL des AutoErmittlungsdiensts</p></td>
<td><p>San = "lyncdiscoverinternal". &lt;sipdomain "&gt;</p></td>
</tr>
<tr class="even">
<td><p>Externe URL des AutoErmittlungsdiensts</p></td>
<td><p>San = lyncdiscover. &lt;sipdomain "&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Alternativ können Sie San = * verwenden. &lt;sipdomain "&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>Reverseproxy-Zertifikatanforderungen (öffentliche ZS)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Beschreibung</th>
<th>Eintrag für alternativen Antragstellernamen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externe URL des AutoErmittlungsdiensts</p></td>
<td><p>San = lyncdiscover. &lt;sipdomain "&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Sie weisen dieses SAN dem Zertifikat zu, das dem SSL-Listener auf dem Reverseproxy zugewiesen ist.



</div>

<div>


> [!NOTE]  
> Ihr Reverse Proxy Listener weist alternative Antragstellernamen für Ihre externen Webdienste-URLs auf (beispielsweise "San = lyncwebextpool01. contoso. com" und "dirwebexternal.contoso.com", wenn Sie den optionalen Director bereitgestellt haben).



</div>

</div>

<span> </span>

</div>

</div>

</div>

