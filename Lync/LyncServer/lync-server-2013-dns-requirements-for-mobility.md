---
title: 'Lync Server 2013: DNS-Anforderungen für Mobilität'
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
ms.openlocfilehash: bc11c79c291f7db7ad9e9e3228644ee27d42e555
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a>DNS-Anforderungen für Mobilität mit lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-13_

Wenn Sie das Mobilitätsfeature von lync Server 2013 bereitstellen, können Sie die neuen URLs verwenden, die für den AutoErmittlungsdienst von Microsoft lync Server 2013 verfügbar sind, oder Sie können Ihre vorhandenen URLs für Webdienste verwenden. Wenn Sie Ihre vorhandenen URLs verwenden, müssen die Benutzer die URLs in Ihren Einstellungen für mobile Geräte manuell eingeben. Diese Option wird in der Regel für die Problembehandlung verwendet. Wenn Sie die neuen URLs verwenden, können mobile Clients die lync Server 2013-Ressourcen automatisch ermitteln. Wenn Sie die automatische Ermittlung unterstützen, müssen Sie neue DNS-Einträge (Domain Name System) hinzufügen. In diesem Abschnitt werden die DNS-Einträge beschrieben, die für die automatische Ermittlung erforderlich sind.

Zur Unterstützung der automatischen Ermittlung müssen Sie die folgenden DNS-Einträge für jede SIP-Domäne erstellen:

  - Ein interner DNS-Eintrag zur Unterstützung von mobilen Benutzern, die innerhalb des Netzwerks Ihrer Organisation eine Verbindung herstellen

  - Ein externer oder öffentlicher DNS-Eintrag zur Unterstützung von mobilen Benutzern, die eine Verbindung mit dem Internet herstellen

Die interne automatische Erkennungs-URL sollte nicht von außerhalb Ihres Netzwerks adressierbar sein. Die URL für die externe automatische Suche sollte in Ihrem Netzwerk nicht adressierbar sein. Wenn Sie diese Voraussetzungen für die externe URL nicht erfüllen können, sollte der Mobile Client jedoch nicht beeinträchtigt werden.

Bei den DNS-Einträgen kann es sich entweder um CNAME-Einträge oder einen (Host-) Eintrag handeln.

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
<td><p>lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
<td><p>Interner Webdienste (Fully Qualified Domain Name, FQDN) für Ihren Director-Pool, falls vorhanden, oder für Ihren Front-End-Pool, wenn Sie keinen Director haben</p></td>
</tr>
<tr class="even">
<td><p>A (Host)</p></td>
<td><p>lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
<td><p>Interne Web Services-IP-Adresse (virtuelle IP-Adresse (VIP-Adresse), wenn Sie ein Lastenausgleichsmodul verwenden) Ihres Director-Pools, falls vorhanden, oder des Front-End-Pools, wenn Sie keinen Director haben</p></td>
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
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>FQDN externer Webdienste für Ihren Director-Pool, falls vorhanden, oder für Ihren Front-End-Pool, wenn Sie keinen Director haben</p></td>
</tr>
<tr class="even">
<td><p>A (Host)</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>Externe oder öffentliche IP-Adresse (VIP-Adresse, wenn Sie ein Lastenausgleichsmodul verwenden) des Reverse-Proxys</p></td>
</tr>
<tr class="odd">
<td><p>SRV</p></td>
<td><p>_sipfederationtls._tcp. &lt;sipdomain&gt;</p>
<p>Behebt einen Host-Eintrag (A oder AAAA) für den Access-Edgedienst</p></td>
<td><p>Um den Push-Benachrichtigungsdienst und den Apple Push-Benachrichtigungsdienst zu unterstützen, erstellen Sie für jede SIP-Domäne mit Microsoft lync Mobile-Clients einen SRV-Eintrag.</p>
<div>

> [!IMPORTANT]  
> Diese Anforderung gilt nur für Microsoft lync Mobile-Clients auf mobilen Apple-oder Microsoft-basierten Geräten. Android und Nokia Symbian-Geräte verwenden keine Push-Benachrichtigung.


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Lyncdiscover, auch als AutoErmittlung bekannt, verkehrt durch den Reverseproxy. Der SRV-Eintrag verweist auf einen Datensatz, der über den Access-Edgedienst aufgelöst wird.



</div>

</div>

<span> </span>

</div>

</div>

</div>

