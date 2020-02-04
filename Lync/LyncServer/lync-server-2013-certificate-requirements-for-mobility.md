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
ms.openlocfilehash: 680eaf205959b67d8fef93ff56d379ae8cd293bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a>Zertifikatanforderungen für die Mobilität in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-24_

Wenn Sie das Mobilitätsfeature bereitstellen und die automatische Ermittlung für mobile Clients unterstützen, müssen Sie bestimmte Einträge für alternative Namen in Zertifikate einbeziehen, um sichere Verbindungen von den mobilen Clients zu unterstützen.

Sie müssen die Einträge für den alternativen Antragstellernamen für die automatische Ermittlung für die folgenden Zertifikate einbeziehen:

  - Directorpool

  - Front-End-Pool

  - Reverseproxy

In diesem Abschnitt werden die Einträge für Alternativen Betreff-Namen beschrieben, die für Ihre Zertifikate für die automatische Erkennung erforderlich sind.

<div>


> [!NOTE]  
> Das erneute Ausstellen von Zertifikaten mithilfe einer internen Zertifizierungsstelle ist in der Regel ein einfacher Vorgang, aber das Hinzufügen von mehreren alternativen Subjektnamen Einträgen zu öffentlichen Zertifikaten, die vom Reverse-Proxy verwendet werden, kann kostspielig sein. Wenn Sie über zahlreiche SIP-Domänen verfügen, die das Hinzufügen von alternativen Subjektnamen sehr teuer machen, können Sie den Reverseproxy so konfigurieren, dass er http für die anfängliche AutoErmittlungsdienst Anforderung verwendet, anstatt HTTPS (die Standardkonfiguration) zu verwenden. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-technical-requirements-for-mobility.md">Technische Voraussetzungen für Mobilität in lync Server 2013</A>.



</div>

### <a name="director-pool-certificate-requirements"></a>Anforderungen des Director-Pool Zertifikats

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Beschreibung</th>
<th>Eintrag für den alternativen Antragstellernamen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL des internen AutoErmittlungsdiensts</p></td>
<td><p>San = lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL des externen AutoErmittlungsdiensts</p></td>
<td><p>San = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Sie können auch San = * verwenden. &lt;sipdomain&gt;



</div>

### <a name="front-end-pool-certificate-requirements"></a>Anforderungen für das Front-End-Pool Zertifikat

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Beschreibung</th>
<th>Eintrag für den alternativen Antragstellernamen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL des internen AutoErmittlungsdiensts</p></td>
<td><p>San = lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL des externen AutoErmittlungsdiensts</p></td>
<td><p>San = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Sie können auch San = * verwenden. &lt;sipdomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>Zertifikatanforderungen für Reverse Proxy (öffentliche Zertifizierungsstelle)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Beschreibung</th>
<th>Eintrag für den alternativen Antragstellernamen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL des externen AutoErmittlungsdiensts</p></td>
<td><p>San = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Sie weisen dieses San dem Zertifikat zu, das dem SSL-Listener auf dem Reverse-Proxy zugewiesen ist.



</div>

<div>


> [!NOTE]  
> Ihr Reverse Proxy-Listener weist Alternative Namen für die externen Webdienste-URLs auf (Beispiel: San = lyncwebextpool01. contoso. com und dirwebexternal.contoso.com, wenn Sie den optionalen Director bereitgestellt haben).



</div>

</div>

<span> </span>

</div>

</div>

</div>

