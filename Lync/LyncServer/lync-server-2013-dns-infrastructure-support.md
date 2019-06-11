---
title: 'Lync Server 2013: DNS-Infrastrukturunterstützung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Domain Name System (DNS) infrastructure support
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425850(v=OCS.15)
ms:contentKeyID: 48183878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9aa9670761e16032abf0c205bbb740cbe1f43c4a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="97664-102">DNS-Infrastrukturunterstützung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97664-102">DNS infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97664-103">_**Letztes Änderungsdatum des Themas:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="97664-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="97664-104">Lync Server 2013 erfordert DNS (Domain Name System) und verwendet es wie folgt:</span><span class="sxs-lookup"><span data-stu-id="97664-104">Lync Server 2013 requires Domain Name System (DNS) and uses it in the following ways:</span></span>

  - <span data-ttu-id="97664-105">Ermitteln interner Server oder Pools für die Server-zu-Server-Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="97664-105">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="97664-106">Damit Clients den Front-End-Pool oder Standard Edition-Server ermitteln können, der für verschiedene SIP-Transaktionen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="97664-106">To enable clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="97664-107">Zuordnen der einfachen URLs für Konferenzen zu den Servern, die diese Konferenzen hosten</span><span class="sxs-lookup"><span data-stu-id="97664-107">To associate the simple URLs for conferences with the servers hosting those conferences.</span></span>

  - <span data-ttu-id="97664-108">So aktivieren Sie externe Server und Clients zum Herstellen einer Verbindung mit Edgeserver oder dem HTTP-Reverseproxy für Instant Messaging (im) oder Konferenzen</span><span class="sxs-lookup"><span data-stu-id="97664-108">To enable external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="97664-109">Wenn Sie Unified Communications (UC)-Geräte aktivieren möchten, die nicht angemeldet sind, um den Front-End-Pool oder den Standard Edition-Server mit dem Geräte Update-Webdienst zu entdecken, beziehen Sie Updates, und senden Sie Protokolle.</span><span class="sxs-lookup"><span data-stu-id="97664-109">To enable unified communications (UC) devices that are not logged in to discover the Front End pool or Standard Edition server running Device Update Web service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="97664-110">Damit Mobile Clients automatisch Webdienste-Ressourcen ermitteln können, ohne dass die Benutzer URLs in den Geräteeinstellungen manuell eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="97664-110">To enable mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

  - <span data-ttu-id="97664-111">Für den DNS-Lastenausgleich.</span><span class="sxs-lookup"><span data-stu-id="97664-111">For DNS load balancing.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="97664-112">Lync Server 2013 unterstützt keine Internationalisierungs Domänennamen (IDNs).</span><span class="sxs-lookup"><span data-stu-id="97664-112">Lync Server 2013 does not support internationalized domain names (IDNs).</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="97664-113">Der angegebene Name muss mit dem auf dem Server konfigurierten Computernamen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="97664-113">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="97664-114">Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Kurzname.</span><span class="sxs-lookup"><span data-stu-id="97664-114">By default, the computer name of a computer that is not joined to a domain is a short name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="97664-115">Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs.</span><span class="sxs-lookup"><span data-stu-id="97664-115">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="97664-116">Daher müssen Sie ein DNS-Suffix für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll und nicht Mitglied einer Domäne ist.</span><span class="sxs-lookup"><span data-stu-id="97664-116">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="97664-117"><STRONG>Verwenden Sie nur Standardzeichen</STRONG> (also A – Z, a – z, 0 – 9 und Bindestriche) beim Zuweisen von FQDNs der Server mit Lync Server, Edgeserver und Pools.</span><span class="sxs-lookup"><span data-stu-id="97664-117"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="97664-118">Verwenden Sie keine Unicode-Zeichen oder Unterstriche.</span><span class="sxs-lookup"><span data-stu-id="97664-118">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="97664-119">Andere als die genannten Zeichen in einem FQDN werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="97664-119">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

