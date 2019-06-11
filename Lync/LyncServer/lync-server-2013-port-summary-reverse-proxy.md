---
title: 'Lync Server 2013: Portzusammenfassung für Reverseproxy'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a86b993a35210934f5ebef61464c11a153bf297
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824176"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="e8415-102">Portzusammenfassung für Reverseproxy in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8415-102">Port summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8415-103">_**Letztes Änderungsdatum des Themas:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="e8415-103">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="e8415-104">Der Reverse-Proxy bietet minimale Anforderungen für Firewall und Port/Protokoll.</span><span class="sxs-lookup"><span data-stu-id="e8415-104">The reverse proxy has minimal requirements for firewall and port/protocol.</span></span>

  - <span data-ttu-id="e8415-105">Die Anforderungen externer Firewalls lauten HTTPS/TCP/443 und die optionale http/TCP/80-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="e8415-105">External firewall requirements are the HTTPS/TCP/443 and the optional HTTP/TCP/80.</span></span> <span data-ttu-id="e8415-106">HTTPS wird für SSL-und TLS-sichere Kommunikation über den Reverse-Proxy verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8415-106">HTTPS is used for SSL and TLS secure communications through the reverse proxy.</span></span> <span data-ttu-id="e8415-107">HTTP wird verwendet, wenn Sie den Zugriff auf den AutoErmittlungsdienst zulassen möchten, wenn sich das Ändern von Zertifikaten als schwierig oder nicht gerechtfertigt erweisen kann.</span><span class="sxs-lookup"><span data-stu-id="e8415-107">HTTP is used if you choose to allow access to the Autodiscover Service when modifying certificates might prove difficult or not cost justified.</span></span>

  - <span data-ttu-id="e8415-108">Clients erwarten, dass Sie sich mit dem Office Web Apps-Server auf HTTPS in Verbindung setzen.</span><span class="sxs-lookup"><span data-stu-id="e8415-108">Clients expect to contact the Office Web Apps Server on HTTPS.</span></span> <span data-ttu-id="e8415-109">Der Office Web Apps-Server erwartet die Kommunikation von internen Clients auf HTTPS/TCP/443.</span><span class="sxs-lookup"><span data-stu-id="e8415-109">The Office Web Apps Server expects communication from internal clients on HTTPS/TCP/443.</span></span> <span data-ttu-id="e8415-110">Die empfohlene Konfiguration ist das Zulassen von HTTPS/TCP/443 vom Reverse-Proxy zum Office Web Apps-Server.</span><span class="sxs-lookup"><span data-stu-id="e8415-110">The recommended configuration is to allow HTTPS/TCP/443 from the reverse proxy to the Office Web Apps Server.</span></span>

  - <span data-ttu-id="e8415-111">Port 8080 wird verwendet, um den Datenverkehr von der internen Schnittstelle des Reverse Proxys an den Front-End-Server, Virtual IP-Front-End-Pool (VIP) oder den optionalen Director oder Director Pool VIP weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="e8415-111">Port 8080 is used to route traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP.</span></span> <span data-ttu-id="e8415-112">Port TCP 8080 ist für mobile Geräte erforderlich, auf denen lync ausgeführt wird, um den AutoErmittlungsdienst in Situationen zu finden, in denen die Änderung des Zertifikats für die Veröffentlichung von externen Webdiensten unerwünscht ist (beispielsweise, wenn Sie über eine große Anzahl von SIP-Domänen verfügen).</span><span class="sxs-lookup"><span data-stu-id="e8415-112">Port TCP 8080 is required for mobile devices running Lync to locate the Autodiscover Service in situations where modifying the external web service publishing rule certificate is undesirable (for example, if you have a large number of SIP domains).</span></span> <span data-ttu-id="e8415-113">Wenn Sie sich entscheiden, neue Zertifikate mit den erforderlichen San-Einträgen zu erwerben, wird der Port TCP 8080 nicht benötigt und ist optional.</span><span class="sxs-lookup"><span data-stu-id="e8415-113">If you choose to acquire new certificates with the necessary SAN entries, the port TCP 8080 is not needed and is optional.</span></span>

  - <span data-ttu-id="e8415-114">Port 4443 wird für den Datenverkehr von der internen Reverse Proxy-Schnittstelle zum Front-End-Server, Virtual IP-Front-End-Pool (VIP) oder dem optionalen Director oder Director Pool VIP verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8415-114">Port 4443 is used for traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP</span></span>
    
    <span data-ttu-id="e8415-115">![13142405-d5c9-45b7-a8b7-a8c89f09c97c] (images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="e8415-115">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>  
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="e8415-116">Verwechseln Sie die 4443 nicht über TCP vom Reverse-Proxy zur internen Bereitstellung für den Port 4443 über TCP-Datenverkehr vom Standard Edition-Server oder dem Front-End-Pool, der die Rolle des zentralen Verwaltungsspeichers verwaltet.</span><span class="sxs-lookup"><span data-stu-id="e8415-116">Do not confuse the 4443 over TCP from the reverse proxy to the internal deployment for the port 4443 over TCP traffic from the Standard Edition server or the Front End pool that manages the Central Management store role.</span></span>

    
    </div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="e8415-117">Port- und Protokolldetails</span><span class="sxs-lookup"><span data-stu-id="e8415-117">Port and Protocol Details</span></span>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="e8415-118">Firewall-Details für Reverse Proxy Server: externe Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8415-118">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8415-119">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="e8415-119">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e8415-120">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e8415-120">Source IP Address</span></span></th>
<th><span data-ttu-id="e8415-121">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e8415-121">Destination IP Address</span></span></th>
<th><span data-ttu-id="e8415-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e8415-122">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8415-123">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="e8415-123">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="e8415-124">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e8415-124">Any</span></span></p></td>
<td><p><span data-ttu-id="e8415-125">Reverse Proxy-Listener</span><span class="sxs-lookup"><span data-stu-id="e8415-125">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="e8415-126">Optional Umleitung zu HTTPS, wenn der Benutzer http://&lt;publishedSiteFQDN&gt;eingibt.</span><span class="sxs-lookup"><span data-stu-id="e8415-126">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span></p>
<p><span data-ttu-id="e8415-127">Dies ist auch bei Verwendung von Office Web Apps für Conferencing und dem AutoErmittlungsdienst für mobile Geräte, die lync ausführen, in Situationen erforderlich, in denen die Organisation das Zertifikat des externen Webdienst-Veröffentlichungsregel nicht ändern möchte.</span><span class="sxs-lookup"><span data-stu-id="e8415-127">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8415-128">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e8415-128">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e8415-129">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e8415-129">Any</span></span></p></td>
<td><p><span data-ttu-id="e8415-130">Reverse Proxy-Listener</span><span class="sxs-lookup"><span data-stu-id="e8415-130">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="e8415-131">Adressbuch Downloads, Adressbuch-Webabfrage Dienst, AutoErmittlung, Clientupdates, Besprechungsinhalte, Geräte Updates, Gruppenerweiterung, Office Web Apps für Konferenzen, Einwahlkonferenzen und Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="e8415-131">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="e8415-132">Firewall-Details für Reverse Proxy Server: interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8415-132">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8415-133">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="e8415-133">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e8415-134">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e8415-134">Source IP Address</span></span></th>
<th><span data-ttu-id="e8415-135">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e8415-135">Destination IP Address</span></span></th>
<th><span data-ttu-id="e8415-136">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e8415-136">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8415-137">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="e8415-137">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="e8415-138">Interne Reverse-Proxy-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8415-138">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="e8415-139">Front-End-Server, Front-End-Pool, Director, Director-Pool</span><span class="sxs-lookup"><span data-stu-id="e8415-139">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="e8415-140">Erforderlich, wenn der AutoErmittlungsdienst für mobile Geräte mit lync in Situationen verwendet wird, in denen die Organisation das Zertifikat für die Veröffentlichungsregel für externe Webdienste nicht ändern möchte.</span><span class="sxs-lookup"><span data-stu-id="e8415-140">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p>
<p><span data-ttu-id="e8415-141">Datenverkehr, der an Port 80 auf der externen Schnittstelle des Reverse Proxys gesendet wird, wird von der internen Schnittstelle des Reverse-Proxys an einen Pool auf Port 8080 umgeleitet, sodass die Pool-Webdienste Sie vom internen Webverkehr unterscheiden können.</span><span class="sxs-lookup"><span data-stu-id="e8415-141">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8415-142">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="e8415-142">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="e8415-143">Interne Reverse-Proxy-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8415-143">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="e8415-144">Front-End-Server, Front-End-Pool, Director, Director-Pool</span><span class="sxs-lookup"><span data-stu-id="e8415-144">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="e8415-145">Datenverkehr, der an Port 443 auf der externen Schnittstelle des Reverse Proxys gesendet wird, wird von der internen Schnittstelle des Reverse-Proxys an einen Pool auf Port 4443 umgeleitet, sodass die Pool-Webdienste Sie vom internen Webverkehr unterscheiden können.</span><span class="sxs-lookup"><span data-stu-id="e8415-145">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8415-146">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e8415-146">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e8415-147">Interne Reverse-Proxy-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8415-147">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="e8415-148">Office Web Apps für Konferenzen</span><span class="sxs-lookup"><span data-stu-id="e8415-148">Office Web Apps for conferencing</span></span></p></td>
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

