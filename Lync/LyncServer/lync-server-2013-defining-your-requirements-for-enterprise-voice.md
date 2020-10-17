---
title: 'Lync Server 2013: Definieren der Anforderungen für Enterprise-VoIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eeadb699c12b3f0ece883484ea8c935bfb795256
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504342"
---
# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="28eba-102">Definieren der Anforderungen für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28eba-102">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28eba-103">_**Letztes Änderungsstand des Themas:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="28eba-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="28eba-104">Dieses Thema enthält eine Übersicht über die Überlegungen, die Sie bei der Bereitstellung von Enterprise-VoIP für die Regionen, Websites und die Verknüpfungen zwischen Websites in Ihrer Topologie vornehmen müssen und wie diese wichtig sind.</span><span class="sxs-lookup"><span data-stu-id="28eba-104">This topic provides an overview of the considerations you need to make about the regions, sites, and the links between sites in your topology and how those are important when you deploy Enterprise Voice.</span></span> <span data-ttu-id="28eba-105">Ausführliche Informationen, die Sie bei diesen Entscheidungen unterstützen, finden Sie unter [Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Features in lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="28eba-105">For details to help you make these decisions, see [Network settings for the advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) in the Planning documentation.</span></span>

<div>

## <a name="sites-and-regions"></a><span data-ttu-id="28eba-106">Standorte und Regionen</span><span class="sxs-lookup"><span data-stu-id="28eba-106">Sites and Regions</span></span>

<span data-ttu-id="28eba-107">Geben Sie zunächst die Standorte in Ihrer Topologie an, in denen Sie Enterprise-VoIP und die netzwerkregionen bereitstellen, zu denen diese Websites gehören.</span><span class="sxs-lookup"><span data-stu-id="28eba-107">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="28eba-108">Insbesondere müssen Sie überlegen, wie die PSTN-Anbindung (Public Switched Telephone Network) für jeden Standort implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="28eba-108">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="28eba-109">Die Zuweisung von Standorten zu Regionen kann aus verwaltungstechnischer und logistischer Sicht ein entscheidender Faktor sein.</span><span class="sxs-lookup"><span data-stu-id="28eba-109">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="28eba-110">Entscheiden Sie, wo Gateways lokal bereitgestellt werden, wo Survivable Branch Appliances (SBAS) bereitgestellt werden und wo Sie SIP-Trunks (lokal oder am zentralen Standort) an einen Internet Telefonie-Dienstanbieter (ITSP) konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="28eba-110">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>

</div>

<div>

## <a name="network-links-between-sites"></a><span data-ttu-id="28eba-111">Netzwerkverbindungen zwischen Standorten</span><span class="sxs-lookup"><span data-stu-id="28eba-111">Network Links Between Sites</span></span>

<span data-ttu-id="28eba-112">Sie müssen auch die Bandbreitenauslastung in Anspruch nehmen, die Sie von den Netzwerkverbindungen zwischen dem zentralen Standort und den Zweigstellenstandorten erwarten.</span><span class="sxs-lookup"><span data-stu-id="28eba-112">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="28eba-113">Wenn Sie stabile WAN-Verbindungen Zwischenstand Orten bereitstellen möchten, empfehlen wir, an jedem Zweigstellenstandort ein Gateway bereitzustellen, um Benutzern an diesen Standorten eine lokale direkte Inward-Wählverbindung (DID) zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="28eba-113">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="28eba-114">Wenn Sie über ausfallsichere WAN-Verbindungen verfügen, die Bandbreite einer WAN-Verbindung jedoch wahrscheinlich eingeschränkt ist, konfigurieren Sie die Anrufsteuerung für diese Verbindung.</span><span class="sxs-lookup"><span data-stu-id="28eba-114">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="28eba-115">Wenn Sie über keine elastischen WAN-Verbindungen verfügen, weniger als 1000-Benutzer an Ihrem Zweigstellenstandort hosten und nicht über lokal geschulte lync Server Administratoren verfügen, wird empfohlen, eine Survivable Branch Appliance am Zweigstellenstandort bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="28eba-115">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="28eba-116">Wenn Sie zwischen 1000-und 5000-Benutzern an Ihrem Zweigstellenstandort hosten, keine stabile WAN-Verbindung haben und lync Server Administratoren verfügbar gemacht haben, wird empfohlen, eine Survivable Branch Server mit einem kleinen Gateway am Zweigstellenstandort bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="28eba-116">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="28eba-117">Erwägen Sie auch die Aktivierung der Medienumgehung für Verbindungen mit eingeschränkter Bandbreite, wenn Sie über ein Gatewaypeer mit Unterstützung der Medienumgehung verfügen.</span><span class="sxs-lookup"><span data-stu-id="28eba-117">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="28eba-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28eba-118">See Also</span></span>


[<span data-ttu-id="28eba-119">Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Funktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28eba-119">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

