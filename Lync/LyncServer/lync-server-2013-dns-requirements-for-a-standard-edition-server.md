---
title: 'Lync Server 2013: DNS-Anforderungen für eine Standard Edition-Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for a Standard Edition server
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204936(v=OCS.15)
ms:contentKeyID: 48184259
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12a4d87f0ffa1ab7d6e857a40c2440d35d0b38aa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204861"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="c7537-102">DNS-Anforderungen für eine Standard Edition-Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7537-102">DNS requirements for a Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7537-103">_**Letztes Änderungsstand des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="c7537-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="c7537-104">In diesem Abschnitt werden die DNS-Einträge (Domain Name System) beschrieben, die zur Bereitstellung von Standard Edition-Servern erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c7537-104">This section describes the Domain Name System (DNS) records that are required for deployment of Standard Edition servers.</span></span>

<div>

## <a name="dns-records-for-standard-edition-servers"></a><span data-ttu-id="c7537-105">DNS-Einträge für Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="c7537-105">DNS Records for Standard Edition Servers</span></span>

<span data-ttu-id="c7537-106">In der folgenden Tabelle werden die DNS-Anforderungen für lync Server 2013 Standard Edition-Server-Bereitstellung angegeben.</span><span class="sxs-lookup"><span data-stu-id="c7537-106">The following table specifies DNS requirements for Lync Server 2013 Standard Edition server deployment.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7537-107">Bereitstellungsszenario</span><span class="sxs-lookup"><span data-stu-id="c7537-107">Deployment scenario</span></span></th>
<th><span data-ttu-id="c7537-108">DNS-Anforderung</span><span class="sxs-lookup"><span data-stu-id="c7537-108">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7537-109">Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="c7537-109">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="c7537-110">Ein interner A-Eintrag, mit dem der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Servers in die zugehörige IP-Adresse aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="c7537-110">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7537-111">Automatische Clientanmeldung</span><span class="sxs-lookup"><span data-stu-id="c7537-111">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="c7537-112">Für jede unterstützte SIP-Domäne ein SRV-Eintrag für _sipinternaltls. _tcp. &lt;Domäne&gt; über Port 5061, die dem FQDN des Standard Edition-Server zugeordnet ist, der Clientanforderungen für die Anmeldung authentifiziert und umleitet.</span><span class="sxs-lookup"><span data-stu-id="c7537-112">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Standard Edition server that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="c7537-113">Ausführliche Informationen finden Sie unter <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS-Anforderungen für die automatische Clientanmeldung in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="c7537-113">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7537-114">Ermittlung des Geräteaktualisierungswebdiensts über Unified Communications-Geräte (UC)</span><span class="sxs-lookup"><span data-stu-id="c7537-114">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="c7537-115">Ein interner A-Eintrag mit dem Namen ucupdates-r2. &lt;SIP-&gt; Domäne, die in die IP-Adresse des Standard Edition-Server Hosting Device Update-Webdiensts aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="c7537-115">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Standard Edition server hosting Device Update Web service.</span></span> <span data-ttu-id="c7537-116">Wenn ein UC-Gerät eingeschaltet wird, ein Benutzer sich jedoch noch nie am Gerät angemeldet hat, ermöglicht der A-Eintrag, dass das Gerät den Server sucht, auf dem der Geräteaktualisierungs-Webdienst gehostet wird, und Updates abruft.</span><span class="sxs-lookup"><span data-stu-id="c7537-116">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the server hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="c7537-117">Andernfalls rufen Geräte die Serverinformationen über die In-Band-Bereitstellung ab, wenn sich der Benutzer das erste Mal anmeldet.</span><span class="sxs-lookup"><span data-stu-id="c7537-117">Otherwise, devices obtain the server information though in-band provisioning the first time a user logs in.</span></span> <span data-ttu-id="c7537-118">Ausführliche Informationen finden Sie unter <a href="lync-server-2013-device-update-web-service.md">Device Update-Webdienst in lync Server 2013</a> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c7537-118">For details, see <a href="lync-server-2013-device-update-web-service.md">Device Update Web service in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7537-119">Ein Reverseproxy zur Unterstützung von HTTP-Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="c7537-119">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="c7537-120">Ein externer A-Eintrag, der den externen FQDN der Webfarm in die externe IP-Adresse des Reverseproxys auflöst.</span><span class="sxs-lookup"><span data-stu-id="c7537-120">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="c7537-121">Clients und UC-Geräte stellen mit diesem Eintrag eine Verbindung mit dem Reverseproxy her.</span><span class="sxs-lookup"><span data-stu-id="c7537-121">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="c7537-122">Ausführliche Informationen finden Sie unter <a href="lync-server-2013-determine-dns-requirements.md">bestimmen der DNS-Anforderungen für lync Server 2013</a> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c7537-122">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c7537-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7537-123">See Also</span></span>


[<span data-ttu-id="c7537-124">DNS-Anforderungen für die automatische Clientanmeldung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7537-124">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[<span data-ttu-id="c7537-125">Bestimmen der DNS-Anforderungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7537-125">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="c7537-126">Geräteaktualisierungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7537-126">Device Update Web service in Lync Server 2013</span></span>](lync-server-2013-device-update-web-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

