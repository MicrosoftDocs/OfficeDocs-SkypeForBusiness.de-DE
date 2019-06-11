---
title: 'Lync Server 2013: DNS-Anforderungen für einen Standard Edition-Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for a Standard Edition server
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204936(v=OCS.15)
ms:contentKeyID: 48184259
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7508fea0fa6640546bda4f1ecb559821d468803d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-a-standard-edition-server-in-lync-server-2013"></a>DNS-Anforderungen für einen Standard Edition-Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

In diesem Abschnitt werden die DNS-Einträge (Domain Name System) beschrieben, die für die Bereitstellung von Standard Edition-Servern erforderlich sind.

<div>

## <a name="dns-records-for-standard-edition-servers"></a>DNS-Einträge für Standard Edition-Server

In der folgenden Tabelle sind die DNS-Anforderungen für die lync Server 2013 Standard Edition-Server Bereitstellung angegeben.


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
<td><p>Für jede unterstützte SIP-Domäne einen SRV-Eintrag für _sipinternaltls. _tcp. &lt;Domäne&gt; über Port 5061, die dem FQDN des Standard Edition-Servers zugeordnet ist, der Clientanforderungen für die Anmeldung authentifiziert und umleitet. Ausführliche Informationen finden Sie unter <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS-Anforderungen für die automatische Clientanmeldung in lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Device Update-Webdienst Ermittlung durch Unified Communications (UC)-Geräte</p></td>
<td><p>Ein interner A-Eintrag mit dem Namen ucupdates-r2. &lt;SIP-&gt; Domäne, die in die IP-Adresse des Standard Edition-Servers für die Aktualisierung des Geräte Update-Webdiensts aufgelöst wird. In der Situation, in der ein UC-Gerät aktiviert ist, sich ein Benutzer aber noch nie beim Gerät angemeldet hat, ermöglicht der a-Eintrag dem Gerät das Erkennen des Server-Hosting-Geräte Update-Webdiensts und das Abrufen von Updates. Andernfalls rufen Geräte die Serverinformationen über die In-Band-Bereitstellung ab, wenn sich der Benutzer das erste Mal anmeldet. Ausführliche Informationen finden Sie unter <a href="lync-server-2013-device-update-web-service.md">Device Update Web Service in lync Server 2013</a> in der Betriebsdokumentation.</p></td>
</tr>
<tr class="even">
<td><p>Ein Reverse-Proxy zur Unterstützung des HTTP-Datenverkehrs</p></td>
<td><p>Ein externer A-Eintrag, der den FQDN der externen Webfarm in die externe IP-Adresse des Reverse-Proxys auflöst. Clients und UC-Geräte verwenden diesen Eintrag, um eine Verbindung mit dem Reverse-Proxy herzustellen. Ausführliche Informationen finden Sie unter <a href="lync-server-2013-determine-dns-requirements.md">Ermitteln der DNS-Anforderungen für lync Server 2013</a> in der Planungsdokumentation.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Siehe auch


[DNS-Anforderungen für die automatische Clientanmeldung in lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[Ermitteln von DNS-Anforderungen für Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Geräteaktualisierungs-Webdienst in Lync Server 2013](lync-server-2013-device-update-web-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

