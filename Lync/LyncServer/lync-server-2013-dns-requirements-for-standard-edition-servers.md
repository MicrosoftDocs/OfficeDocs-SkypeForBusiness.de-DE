---
title: 'Lync Server 2013: DNS-Anforderungen für Standard Edition-Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Standard Edition servers
ms:assetid: 3d6bbe65-e7ce-491b-a0bd-d2f7197f240d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425900(v=OCS.15)
ms:contentKeyID: 48183920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19c5e04f23428b073e544b040ed07dc852f1da4c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="5a2ea-102">DNS-Anforderungen für Standard Edition-Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a2ea-102">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a2ea-103">_**Letztes Änderungsdatum des Themas:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="5a2ea-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="5a2ea-104">In diesem Abschnitt werden die DNS-Einträge (Domain Name System) beschrieben, die für die Bereitstellung von Standard Edition-Servern erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5a2ea-104">This section describes the Domain Name System (DNS) records that are required for deployment of Standard Edition servers.</span></span>

<div>

## <a name="dns-records-for-standard-edition-servers"></a><span data-ttu-id="5a2ea-105">DNS-Einträge für Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="5a2ea-105">DNS Records for Standard Edition Servers</span></span>

<span data-ttu-id="5a2ea-106">In der folgenden Tabelle sind die DNS-Anforderungen für die lync Server 2013 Standard Edition-Server Bereitstellung angegeben.</span><span class="sxs-lookup"><span data-stu-id="5a2ea-106">The following table specifies DNS requirements for Lync Server 2013 Standard Edition server deployment.</span></span>

### <a name="dns-requirements-for-a-standard-edition-server"></a><span data-ttu-id="5a2ea-107">DNS-Anforderungen für einen Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="5a2ea-107">DNS Requirements for a Standard Edition Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5a2ea-108">Bereitstellungsszenario</span><span class="sxs-lookup"><span data-stu-id="5a2ea-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="5a2ea-109">DNS-Anforderung</span><span class="sxs-lookup"><span data-stu-id="5a2ea-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a2ea-110">Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="5a2ea-110">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="5a2ea-111">Ein interner A-Eintrag, mit dem der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Servers in die zugehörige IP-Adresse aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="5a2ea-111">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a2ea-112">Automatische Clientanmeldung</span><span class="sxs-lookup"><span data-stu-id="5a2ea-112">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="5a2ea-113">Für jede unterstützte SIP-Domäne einen SRV-Eintrag für _sipinternaltls. _tcp. &lt;Domäne&gt; über Port 5061, die dem FQDN des Standard Edition-Servers zugeordnet ist, der Clientanforderungen für die Anmeldung authentifiziert und umleitet.</span><span class="sxs-lookup"><span data-stu-id="5a2ea-113">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Standard Edition server that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="5a2ea-114">Ausführliche Informationen finden Sie unter <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS-Anforderungen für die automatische Clientanmeldung in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5a2ea-114">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a2ea-115">Device Update-Webdienst Ermittlung durch Unified Communications (UC)-Geräte</span><span class="sxs-lookup"><span data-stu-id="5a2ea-115">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="5a2ea-116">Ein interner A-Eintrag mit dem Namen ucupdates-r2. &lt;SIP-&gt; Domäne, die in die IP-Adresse des Standard Edition-Servers für die Aktualisierung des Geräte Update-Webdiensts aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="5a2ea-116">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Standard Edition server hosting Device Update Web service.</span></span> <span data-ttu-id="5a2ea-117">In der Situation, in der ein UC-Gerät aktiviert ist, sich ein Benutzer aber noch nie beim Gerät angemeldet hat, ermöglicht der a-Eintrag dem Gerät das Erkennen des Server-Hosting-Geräte Update-Webdiensts und das Abrufen von Updates.</span><span class="sxs-lookup"><span data-stu-id="5a2ea-117">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the server hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="5a2ea-118">Andernfalls rufen Geräte die Serverinformationen über die In-Band-Bereitstellung ab, wenn sich der Benutzer das erste Mal anmeldet.</span><span class="sxs-lookup"><span data-stu-id="5a2ea-118">Otherwise, devices obtain the server information though in-band provisioning the first time a user logs in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a2ea-119">Ein Reverse-Proxy zur Unterstützung des HTTP-Datenverkehrs</span><span class="sxs-lookup"><span data-stu-id="5a2ea-119">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="5a2ea-120">Ein externer A-Eintrag, der den FQDN der externen Webfarm in die externe IP-Adresse des Reverse-Proxys auflöst.</span><span class="sxs-lookup"><span data-stu-id="5a2ea-120">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="5a2ea-121">Clients und UC-Geräte verwenden diesen Eintrag, um eine Verbindung mit dem Reverse-Proxy herzustellen.</span><span class="sxs-lookup"><span data-stu-id="5a2ea-121">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="5a2ea-122">Ausführliche Informationen finden Sie unter <a href="lync-server-2013-determine-dns-requirements.md">Ermitteln der DNS-Anforderungen für lync Server 2013</a> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="5a2ea-122">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

