---
title: 'Lync Server 2013: DNS-Anforderungen für Standard Edition-Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Standard Edition servers
ms:assetid: 3d6bbe65-e7ce-491b-a0bd-d2f7197f240d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425900(v=OCS.15)
ms:contentKeyID: 48183920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 903243e846fee2a0b874a50fb529b533c1658fc2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-standard-edition-servers-in-lync-server-2013"></a>DNS-Anforderungen für Standard Edition-Server in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-19_

In diesem Abschnitt werden die DNS-Einträge (Domain Name System) beschrieben, die zur Bereitstellung von Standard Edition-Servern erforderlich sind.

<div>

## <a name="dns-records-for-standard-edition-servers"></a>DNS-Einträge für Standard Edition-Server

In der folgenden Tabelle werden die DNS-Anforderungen für lync Server 2013 Standard Edition-Server-Bereitstellung angegeben.

### <a name="dns-requirements-for-a-standard-edition-server"></a>DNS-Anforderungen für einen Standard Edition-Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Bereitstellungsszenario</th>
<th>DNS-Anforderung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard Edition-Server</p></td>
<td><p>Ein interner A-Eintrag, mit dem der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Servers in die zugehörige IP-Adresse aufgelöst wird.</p></td>
</tr>
<tr class="even">
<td><p>Automatische Clientanmeldung</p></td>
<td><p>Für jede unterstützte SIP-Domäne ein SRV-Eintrag für _sipinternaltls. _tcp. &lt;Domäne&gt; über Port 5061, die dem FQDN des Standard Edition-Server zugeordnet ist, der Clientanforderungen für die Anmeldung authentifiziert und umleitet. Ausführliche Informationen finden Sie unter <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS-Anforderungen für die automatische Clientanmeldung in lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Ermittlung des Geräteaktualisierungswebdiensts über Unified Communications-Geräte (UC)</p></td>
<td><p>Ein interner A-Eintrag mit dem Namen ucupdates-r2. &lt;SIP-&gt; Domäne, die in die IP-Adresse des Standard Edition-Server Hosting Device Update-Webdiensts aufgelöst wird. Wenn ein UC-Gerät eingeschaltet wird, ein Benutzer sich jedoch noch nie am Gerät angemeldet hat, ermöglicht der A-Eintrag, dass das Gerät den Server sucht, auf dem der Geräteaktualisierungs-Webdienst gehostet wird, und Updates abruft. Andernfalls rufen Geräte die Serverinformationen über die In-Band-Bereitstellung ab, wenn sich der Benutzer das erste Mal anmeldet.</p></td>
</tr>
<tr class="even">
<td><p>Ein Reverseproxy zur Unterstützung von HTTP-Datenverkehr</p></td>
<td><p>Ein externer A-Eintrag, der den externen FQDN der Webfarm in die externe IP-Adresse des Reverseproxys auflöst. Clients und UC-Geräte stellen mit diesem Eintrag eine Verbindung mit dem Reverseproxy her. Ausführliche Informationen finden Sie unter <a href="lync-server-2013-determine-dns-requirements.md">bestimmen der DNS-Anforderungen für lync Server 2013</a> in der Planungsdokumentation.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

