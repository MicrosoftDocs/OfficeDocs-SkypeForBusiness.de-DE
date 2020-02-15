---
title: 'Lync Server 2013: DNS-Infrastrukturunterstützung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) infrastructure support
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425850(v=OCS.15)
ms:contentKeyID: 48183878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 190e0160532ca0ac26ce4f818f260848ea68f0a1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034807"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="d8c42-102">Unterstützung der DNS-Infrastruktur in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8c42-102">DNS infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8c42-103">_**Letztes Änderungsstand des Themas:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="d8c42-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="d8c42-104">Lync Server 2013 erfordert Domain Name System (DNS) und verwendet es wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d8c42-104">Lync Server 2013 requires Domain Name System (DNS) and uses it in the following ways:</span></span>

  - <span data-ttu-id="d8c42-105">Zum Erkennen interner Server oder Pools für die Kommunikation zwischen Servern.</span><span class="sxs-lookup"><span data-stu-id="d8c42-105">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="d8c42-106">Damit Clients den Front-End-Pool oder den Standard Edition-Server erkennen können, der für verschiedene SIP-Transaktionen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d8c42-106">To enable clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="d8c42-107">Zum Zuordnen der einfachen URLs für Konferenzen zu den Servern, auf denen diese Konferenzen gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="d8c42-107">To associate the simple URLs for conferences with the servers hosting those conferences.</span></span>

  - <span data-ttu-id="d8c42-108">Damit externe Server und Clients für Sofortnachrichten oder für Konferenzen eine Verbindung mit Edgeservern oder dem HTTP-Reverseproxy herstellen können.</span><span class="sxs-lookup"><span data-stu-id="d8c42-108">To enable external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="d8c42-109">Damit nicht angemeldete UC-Geräte (Unified Communications) den Front-End-Pool oder den Standard Edition-Server ermitteln können, auf dem der Geräteaktualisierungswebdienst ausgeführt wird, sowie Updates abrufen und Protokolle senden können.</span><span class="sxs-lookup"><span data-stu-id="d8c42-109">To enable unified communications (UC) devices that are not logged in to discover the Front End pool or Standard Edition server running Device Update Web service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="d8c42-110">Damit mobile Clients automatisch Webdienstressourcen ermitteln können, ohne dass Benutzer in den Geräteeinstellungen manuell URLs eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="d8c42-110">To enable mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

  - <span data-ttu-id="d8c42-111">Zum DNS-Lastenausgleich.</span><span class="sxs-lookup"><span data-stu-id="d8c42-111">For DNS load balancing.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d8c42-112">Lync Server 2013 unterstützt keine internationalen Domänennamen (IDNs).</span><span class="sxs-lookup"><span data-stu-id="d8c42-112">Lync Server 2013 does not support internationalized domain names (IDNs).</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d8c42-113">Der angegebene Name muss mit dem auf dem Server konfigurierten Computernamen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d8c42-113">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="d8c42-114">Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Kurzname.</span><span class="sxs-lookup"><span data-stu-id="d8c42-114">By default, the computer name of a computer that is not joined to a domain is a short name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="d8c42-115">Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs.</span><span class="sxs-lookup"><span data-stu-id="d8c42-115">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="d8c42-116">Daher müssen Sie ein DNS-Suffix für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll und nicht Mitglied einer Domäne ist.</span><span class="sxs-lookup"><span data-stu-id="d8c42-116">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="d8c42-117"><STRONG>Verwenden Sie nur Standardzeichen</STRONG> (also A–Z, a–z, 0–9 und Bindestriche) beim Zuweisen von FQDNs der Server mit Lync Server, Edgeserver und Pools.</span><span class="sxs-lookup"><span data-stu-id="d8c42-117"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="d8c42-118">Verwenden Sie keine Unicode-Zeichen oder Unterstriche.</span><span class="sxs-lookup"><span data-stu-id="d8c42-118">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="d8c42-119">Andere als die genannten Zeichen in einem FQDN werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d8c42-119">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

