---
title: 'Lync Server 2013: DNS-Anforderungen für die Mobilität'
description: 'Lync Server 2013: DNS-Anforderungen für die Mobilität.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2a8377dc7c856bb7250817cb3b8b66ed7789d3b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574301"
---
# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a>DNS-Anforderungen für die Mobilität mit lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-13_

Wenn Sie das lync Server 2013 Mobilitätsfeature bereitstellen, können Sie die neuen URLs verwenden, die mit dem Microsoft lync Server 2013 AutoErmittlungsdienst zur Verfügung stehen, oder Sie können Ihre vorhandenen Webdienste-URLs verwenden. Wenn Sie vorhandene URLs verwenden, müssen Benutzer in den Einstellungen des mobilen Geräts die URLs manuell eingeben. Diese Option wird normalerweise zur Problembehandlung verwendet. Wenn Sie die neuen URLs verwenden, können mobile Clients lync Server 2013 Ressourcen automatisch ermitteln. Wenn Sie die automatische Ermittlung unterstützen möchten, müssen Sie neue DNS-Einträge (Domain Name System) hinzufügen. In diesem Abschnitt werden die DNS-Einträge beschrieben, die für die automatische Ermittlung erforderlich sind.

Zur Unterstützung der AutoErmittlung müssen Sie für jede SIP-Domäne die folgenden DNS-Einträge erstellen:

  - Einen internen DNS-Eintrag zur Unterstützung mobiler Benutzer, die über das Netzwerk Ihrer Organisation eine Verbindung herstellen

  - Einen externen oder öffentlichen DNS-Eintrag zur Unterstützung mobiler Benutzer, die eine Verbindung über das Internet herstellen

Die interne AutoErmittlung-URL sollte nicht von außerhalb des Netzwerks adressierbar sein. Die externe AutoErmittlung-URL sollte nicht von innerhalb des Netzwerks adressierbar sein. Wenn Sie diese Anforderung für die externe URL nicht erfüllen können, sollte dies allerdings nicht die Funktionen des mobilen Clients beeinträchtigen.

Bei den DNS-Einträgen kann es sich entweder um A-Einträge (Host) oder um CNAME-Einträge handeln.

**Interne DNS-Einträge**

Sie müssen einen der folgenden internen DNS-Einträge erstellen:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Eintragstyp</th>
<th>Hostname oder SRV-Definition</th>
<th>Auflösung in</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>"lyncdiscoverinternal". &lt; sipdomain "&gt;</p></td>
<td><p>Interner Webdienste vollqualifizierter Domänenname (Fully Qualified Domain Name, FQDN) für Ihren Directorpool, wenn Sie einen haben, oder für Ihre Front-End-Pool, wenn Sie keinen Director haben</p></td>
</tr>
<tr class="even">
<td><p>A (Host)</p></td>
<td><p>"lyncdiscoverinternal". &lt; sipdomain "&gt;</p></td>
<td><p>Interne Webdienste IP-Adresse (virtuelle IP-Adresse (VIP), wenn Sie einen Lastenausgleich verwenden) Ihres Directorpool, wenn Sie einen haben, oder Ihrer Front-End-Pool, wenn Sie keinen Director haben</p></td>
</tr>
</tbody>
</table>


**Externe DNS-Einträge**

Sie müssen einen der folgenden externen DNS-Einträge erstellen:


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
<td><p>lyncdiscover. &lt;sipdomain "&gt;</p></td>
<td><p>Externer Webdienste FQDN für Ihren Directorpool, wenn Sie einen haben, oder für Ihre Front-End-Pool, wenn Sie keinen Director haben</p></td>
</tr>
<tr class="even">
<td><p>A (Host)</p></td>
<td><p>lyncdiscover. &lt;sipdomain "&gt;</p></td>
<td><p>Externe oder öffentliche IP-Adresse (VIP-Adresse bei Verwendung eines Lastenausgleichs) des Reverseproxys</p></td>
</tr>
<tr class="odd">
<td><p>SRV</p></td>
<td><p>_sipfederationtls _sipfederationtls._tcp. &lt;sipdomain "&gt;</p>
<p>Aufgelöst in Hosteintrag (a oder AAAA) für den Zugriffs-Edgedienst</p></td>
<td><p>Zur Unterstützung von Push Notification Service und Apple Push Notification Service erstellen Sie einen SRV-Eintrag für jede SIP-Domäne mit Microsoft lync Mobile-Clients.</p>
<div>

> [!IMPORTANT]  
> Diese Anforderung gilt nur für Microsoft lync Mobile-Clients auf Apple-oder Microsoft-basierten mobilen Geräten. Android- und Nokia Symbian-Geräte verwenden die Pushbenachrichtigung nicht.


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Lyncdiscover, auch bekannt als AutoErmittlung, Verkehr durchläuft den Reverseproxy. Der SRV-Eintrag verweist auf einen Datensatz, der durch den Zugriffs-Edgedienst aufgelöst wird.



</div>

</div>

<span> </span>

</div>

</div>

</div>

