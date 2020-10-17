---
title: 'Lync Server 2013: Port Summary-Reverse Proxy'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfe8a797fa926899774386101ff57fa5733b9918
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534152"
---
# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="f8f73-102">Port Zusammenfassung-Reverseproxy in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8f73-102">Port summary - Reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8f73-103">_**Letztes Änderungsstand des Themas:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="f8f73-103">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="f8f73-104">Die Firewall- und die Port- bzw. Protokollanforderungen des Reverseproxys sind minimal.</span><span class="sxs-lookup"><span data-stu-id="f8f73-104">The reverse proxy has minimal requirements for firewall and port/protocol.</span></span>

  - <span data-ttu-id="f8f73-105">Externe Firewall-Anforderungen sind die HTTPS/TCP/443 und die optionale http/TCP/80.</span><span class="sxs-lookup"><span data-stu-id="f8f73-105">External firewall requirements are the HTTPS/TCP/443 and the optional HTTP/TCP/80.</span></span> <span data-ttu-id="f8f73-106">HTTPS wird für die sichere SSL-und TLS-Kommunikation über den Reverseproxy verwendet.</span><span class="sxs-lookup"><span data-stu-id="f8f73-106">HTTPS is used for SSL and TLS secure communications through the reverse proxy.</span></span> <span data-ttu-id="f8f73-107">HTTP wird verwendet, wenn Sie den Zugriff auf den AutoErmittlungsdienst gewähren möchten, wenn sich das Ändern von Zertifikaten als schwierig oder nicht Kosten berechtigt erweisen kann.</span><span class="sxs-lookup"><span data-stu-id="f8f73-107">HTTP is used if you choose to allow access to the Autodiscover Service when modifying certificates might prove difficult or not cost justified.</span></span>

  - <span data-ttu-id="f8f73-108">Clients erwarten, dass Sie den Office-webapps-Server unter https kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="f8f73-108">Clients expect to contact the Office Web Apps Server on HTTPS.</span></span> <span data-ttu-id="f8f73-109">Der Office-webapps-Server erwartet die Kommunikation von internen Clients unter https/TCP/443.</span><span class="sxs-lookup"><span data-stu-id="f8f73-109">The Office Web Apps Server expects communication from internal clients on HTTPS/TCP/443.</span></span> <span data-ttu-id="f8f73-110">Die empfohlene Konfiguration besteht darin, HTTPS/TCP/443 vom Reverseproxy zum Office-webapps-Server zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="f8f73-110">The recommended configuration is to allow HTTPS/TCP/443 from the reverse proxy to the Office Web Apps Server.</span></span>

  - <span data-ttu-id="f8f73-111">Port 8080 wird verwendet, um Datenverkehr von der internen Reverse Proxy-Schnittstelle an den Front-End-Server, Front-End-Pool virtuelle IP (VIP) oder den optionalen Director oder Directorpool VIP weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="f8f73-111">Port 8080 is used to route traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP.</span></span> <span data-ttu-id="f8f73-112">Port TCP 8080 ist erforderlich, damit Mobile Geräte, auf denen lync ausgeführt wird, den AutoErmittlungsdienst in Situationen finden, in denen das Ändern des Veröffentlichungsregel Zertifikats für externe Webdienste nicht erwünscht ist (beispielsweise, wenn Sie eine große Anzahl von SIP-Domänen haben).</span><span class="sxs-lookup"><span data-stu-id="f8f73-112">Port TCP 8080 is required for mobile devices running Lync to locate the Autodiscover Service in situations where modifying the external web service publishing rule certificate is undesirable (for example, if you have a large number of SIP domains).</span></span> <span data-ttu-id="f8f73-113">Wenn Sie neue Zertifikate mit den erforderlichen San-Einträgen erwerben möchten, ist der Port TCP 8080 nicht erforderlich und ist optional.</span><span class="sxs-lookup"><span data-stu-id="f8f73-113">If you choose to acquire new certificates with the necessary SAN entries, the port TCP 8080 is not needed and is optional.</span></span>

  - <span data-ttu-id="f8f73-114">Port 4443 wird für Datenverkehr von der internen Reverseproxy-Schnittstelle zum Front-End-Server, Front-End-Pool Virtual IP (VIP) oder dem optionalen Director oder Directorpool VIP verwendet.</span><span class="sxs-lookup"><span data-stu-id="f8f73-114">Port 4443 is used for traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP</span></span>
    
    <span data-ttu-id="f8f73-115">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="f8f73-115">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>  
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="f8f73-116">Verwechseln Sie nicht die 4443 über TCP vom Reverseproxy zur internen Bereitstellung für den Port 4443 über TCP-Datenverkehr von der Standard Edition-Server oder der Front-End-Pool, die die Rolle des zentralen Verwaltungsspeichers verwaltet.</span><span class="sxs-lookup"><span data-stu-id="f8f73-116">Do not confuse the 4443 over TCP from the reverse proxy to the internal deployment for the port 4443 over TCP traffic from the Standard Edition server or the Front End pool that manages the Central Management store role.</span></span>

    
    </div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="f8f73-117">Port-und Protokoll Details</span><span class="sxs-lookup"><span data-stu-id="f8f73-117">Port and Protocol Details</span></span>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="f8f73-118">Firewalldetails für Reverseproxyserver: externe Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8f73-118">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8f73-119">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="f8f73-119">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="f8f73-120">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="f8f73-120">Source IP Address</span></span></th>
<th><span data-ttu-id="f8f73-121">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="f8f73-121">Destination IP Address</span></span></th>
<th><span data-ttu-id="f8f73-122">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="f8f73-122">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8f73-123">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="f8f73-123">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="f8f73-124">Beliebig</span><span class="sxs-lookup"><span data-stu-id="f8f73-124">Any</span></span></p></td>
<td><p><span data-ttu-id="f8f73-125">Reverseproxylistener</span><span class="sxs-lookup"><span data-stu-id="f8f73-125">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="f8f73-126">Optional Umleitung zu HTTPS, wenn der Benutzer http://publishedSiteFQDN eingibt &lt; &gt; .</span><span class="sxs-lookup"><span data-stu-id="f8f73-126">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span></p>
<p><span data-ttu-id="f8f73-127">Auch erforderlich, wenn Office-webapps für Konferenzen und der AutoErmittlungsdienst für mobile Geräte, auf denen lync ausgeführt wird, in Situationen verwendet werden, in denen die Organisation das Zertifikat für die Veröffentlichungsregel für externe Webdienste nicht ändern möchte.</span><span class="sxs-lookup"><span data-stu-id="f8f73-127">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8f73-128">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="f8f73-128">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="f8f73-129">Beliebig</span><span class="sxs-lookup"><span data-stu-id="f8f73-129">Any</span></span></p></td>
<td><p><span data-ttu-id="f8f73-130">Reverseproxylistener</span><span class="sxs-lookup"><span data-stu-id="f8f73-130">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="f8f73-131">Adressbuch Downloads, Adressbuch-Webabfragedienst, AutoErmittlung, Clientupdates, Besprechungsinhalte, Geräteaktualisierungen, Gruppenerweiterung, Office-Webanwendungen für Konferenzen, Einwahlkonferenzen und Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="f8f73-131">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="f8f73-132">Firewalldetails für Reverseproxyserver: interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8f73-132">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8f73-133">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="f8f73-133">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="f8f73-134">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="f8f73-134">Source IP Address</span></span></th>
<th><span data-ttu-id="f8f73-135">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="f8f73-135">Destination IP Address</span></span></th>
<th><span data-ttu-id="f8f73-136">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="f8f73-136">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8f73-137">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="f8f73-137">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="f8f73-138">Interne Reverseproxyschnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8f73-138">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="f8f73-139">Front-End-Server, Front-End-Pool, Director Directorpool</span><span class="sxs-lookup"><span data-stu-id="f8f73-139">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="f8f73-140">Erforderlich, wenn der AutoErmittlungsdienst für mobile Geräte, auf denen lync ausgeführt wird, in Situationen verwendet wird, in denen die Organisation das Zertifikat für die Veröffentlichungsregel für externe Webdienste nicht ändern möchte.</span><span class="sxs-lookup"><span data-stu-id="f8f73-140">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p>
<p><span data-ttu-id="f8f73-141">Datenverkehr, der an Port 80 der externen Reverseproxyschnittstelle gesendet wird, wird an einen Pool an Port 8080 der internen Reverseproxyschnittstelle umgeleitet, sodass die Poolwebdienste diesen vom internen Webdatenverkehr unterscheiden können.</span><span class="sxs-lookup"><span data-stu-id="f8f73-141">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8f73-142">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="f8f73-142">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="f8f73-143">Interne Reverseproxyschnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8f73-143">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="f8f73-144">Front-End-Server, Front-End-Pool, Director Directorpool</span><span class="sxs-lookup"><span data-stu-id="f8f73-144">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="f8f73-145">Datenverkehr, der an Port 80 der externen Reverseproxyschnittstelle gesendet wird, wird an einen Pool an Port 8080 der internen Reverseproxyschnittstelle umgeleitet, sodass die Poolwebdienste diesen vom internen Webdatenverkehr unterscheiden können.</span><span class="sxs-lookup"><span data-stu-id="f8f73-145">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8f73-146">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="f8f73-146">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="f8f73-147">Interne Reverseproxyschnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8f73-147">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="f8f73-148">Office-Webanwendungen für Konferenzen</span><span class="sxs-lookup"><span data-stu-id="f8f73-148">Office Web Apps for conferencing</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

