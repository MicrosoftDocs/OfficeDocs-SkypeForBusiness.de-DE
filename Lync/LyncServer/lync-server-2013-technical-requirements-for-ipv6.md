---
title: Lync Server 2013 technische Anforderungen für IPv6
description: Lync Server 2013 technischen Anforderungen für IPv6.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48185465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c54dfbdba56c45f19e7664db075331591c8e87cc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559461"
---
# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="38a2a-103">Technische Anforderungen für IPv6 in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38a2a-103">Technical requirements for IPv6 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38a2a-104">_**Letztes Änderungsstand des Themas:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="38a2a-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="38a2a-105">Wenn Sie lync Server 2013 für IPv6 konfigurieren möchten, sollten Sie die folgenden Anforderungen berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="38a2a-105">If you plan to configure Lync Server 2013 for IPv6, keep the following requirements in mind:</span></span>

  - <span data-ttu-id="38a2a-106">Um IPv6-Adressen mit lync Server zu verwenden, müssen Sie DNS-Einträge (Domain Name System) für Datensätze erstellen, die ermittelt und in eine IPv6-Adresse aufgelöst werden müssen.</span><span class="sxs-lookup"><span data-stu-id="38a2a-106">To use IPv6 addresses with Lync Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="38a2a-107">IPv6-DNS verwendet Host-AAAA-Einträge (Quad-A).</span><span class="sxs-lookup"><span data-stu-id="38a2a-107">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="38a2a-108">Wenn Sie sowohl IPv4 als auch IPv6 in Ihrer Bereitstellung verwenden, empfiehlt es sich, sowohl Host A-Einträge für IPv4 als auch Host-AAAA-Einträge für IPv6 zu konfigurieren und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="38a2a-108">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="38a2a-109">Selbst wenn Sie Ihre Bereitstellung vollständig auf IPv6 umstellen, benötigen Sie möglicherweise weiterhin IPv4-DNS-Hosteinträge für externe Benutzer, die weiterhin IPv4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="38a2a-109">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="38a2a-110">Sie können IPv6-DNS-Hosteinträge bereitstellen, bevor Sie mit der Verwendung von IPv6 beginnen.</span><span class="sxs-lookup"><span data-stu-id="38a2a-110">You can deploy IPv6 DNS host records before you start using IPv6.</span></span> <span data-ttu-id="38a2a-111">Wenn der Client oder Server IPv6 nicht verwendet, wird auf den Datensatz nicht verwiesen.</span><span class="sxs-lookup"><span data-stu-id="38a2a-111">If the client or server doesn't use IPv6, the record will not be referenced.</span></span> <span data-ttu-id="38a2a-112">Übergangstechnologien entscheiden über den zu verwendenden Datensatz basierend auf der Konfiguration und den Richtlinien für die Übergangstechnologie.</span><span class="sxs-lookup"><span data-stu-id="38a2a-112">Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>

  - <span data-ttu-id="38a2a-113">Jede IPv6-Adresse verfügt über einen Bereich.</span><span class="sxs-lookup"><span data-stu-id="38a2a-113">Each IPv6 address has a scope.</span></span> <span data-ttu-id="38a2a-114">Die drei Bereiche, die Sie für die IPv6-Adressierung verwenden können, sind globale IPv6-Adressen (vergleichbar mit öffentlichen IPv4-Adressen), eindeutige lokale IPv6-Adressen (vergleichbar mit den privaten IPv4-Adressbereichen) und lokale IPv6-Linkadressen (ähnlich wie bei automatischen privaten IP-Adressen in Windows Server für IPv4).</span><span class="sxs-lookup"><span data-stu-id="38a2a-114">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="38a2a-115">Alle Server in einem Pool sollten über IPv6-Adressen mit demselben Bereich verfügen.</span><span class="sxs-lookup"><span data-stu-id="38a2a-115">All the servers within a pool should have IPv6 addresses with the same scope.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="38a2a-116">IPv6 ist ein komplexes Thema und erfordert eine sorgfältige Planung mit Ihrem Netzwerkteam und Ihrem Internet Anbieter, um sicherzustellen, dass die Adressen, die Sie auf der Windows Server-Ebene und auf der lync Server 2013 Ebene zuweisen, erwartungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="38a2a-116">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Lync Server 2013 level work as expected.</span></span> <span data-ttu-id="38a2a-117">Zusätzliche Ressourcen zur IPv6-Adressierung und -Planung finden Sie unter den Links am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="38a2a-117">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="38a2a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38a2a-118">See Also</span></span>


[<span data-ttu-id="38a2a-119">IP-Adressierungs Architektur der Version 6</span><span class="sxs-lookup"><span data-stu-id="38a2a-119">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="38a2a-120">Globales Unicast-Adress Format in IPv6</span><span class="sxs-lookup"><span data-stu-id="38a2a-120">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="38a2a-121">Eindeutige lokale IPv6-Unicast-Adressen</span><span class="sxs-lookup"><span data-stu-id="38a2a-121">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

