---
title: 'Lync Server 2013: Definieren der Enterprise-VoIP-bezogenen Anforderungen für Ihr Unternehmen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0ce05c39e3433ff949d82f583207aebfba871fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="1d66c-102">Definieren der Enterprise-VoIP-bezogenen Anforderungen für Ihr Unternehmen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d66c-102">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d66c-103">_**Letztes Änderungsdatum des Themas:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="1d66c-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="1d66c-104">Dieses Thema enthält eine Übersicht über die Überlegungen, die Sie zu den Regionen, Websites und den Verknüpfungen zwischen Websites in Ihrer Topologie vornehmen müssen, und wie diese wichtig sind, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1d66c-104">This topic provides an overview of the considerations you need to make about the regions, sites, and the links between sites in your topology and how those are important when you deploy Enterprise Voice.</span></span> <span data-ttu-id="1d66c-105">Details, die Ihnen bei diesen Entscheidungen helfen, finden Sie unter [Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Features in lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="1d66c-105">For details to help you make these decisions, see [Network settings for the advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) in the Planning documentation.</span></span>

<div>

## <a name="sites-and-regions"></a><span data-ttu-id="1d66c-106">Websites und Regionen</span><span class="sxs-lookup"><span data-stu-id="1d66c-106">Sites and Regions</span></span>

<span data-ttu-id="1d66c-107">Identifizieren Sie zunächst die Websites in Ihrer Topologie, in denen Sie Enterprise-VoIP und die netzwerkregionen bereitstellen, denen diese Websites angehören.</span><span class="sxs-lookup"><span data-stu-id="1d66c-107">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="1d66c-108">Insbesondere müssen Sie überlegen, wie die PSTN-Anbindung (Public Switched Telephone Network) für jeden Standort implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="1d66c-108">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="1d66c-109">Die Zuweisung von Standorten zu Regionen kann aus verwaltungstechnischer und logistischer Sicht ein entscheidender Faktor sein.</span><span class="sxs-lookup"><span data-stu-id="1d66c-109">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="1d66c-110">Entscheiden Sie, wo Gateways lokal bereitgestellt werden sollen, wo Survival Branch Appliances (SBAS) bereitgestellt werden und wo Sie SIP-Trunks (lokal oder am zentralen Standort) an einen Internet-Telefoniedienst (ITSP) konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="1d66c-110">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>

</div>

<div>

## <a name="network-links-between-sites"></a><span data-ttu-id="1d66c-111">Netzwerkverknüpfungen zwischen Websites</span><span class="sxs-lookup"><span data-stu-id="1d66c-111">Network Links Between Sites</span></span>

<span data-ttu-id="1d66c-112">Sie müssen auch die Bandbreitennutzung in Frage stellen, die Sie bei den Netzwerkverbindungen zwischen ihrer zentralen Website und ihren Zweigstellen erwarten.</span><span class="sxs-lookup"><span data-stu-id="1d66c-112">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="1d66c-113">Wenn Sie über eine stabile WAN-Verbindung zwischen Websites verfügen oder diese bereitstellen möchten, empfiehlt es sich, ein Gateway an jeder Verzweigungs Website bereitzustellen, um den Benutzern an diesen Standorten eine direkte Durchwahl (DID)-Kündigung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="1d66c-113">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="1d66c-114">Wenn Sie über ausfallsichere WAN-Verbindungen verfügen, aber die Bandbreite einer WAN-Verbindung wahrscheinlich eingeschränkt ist, konfigurieren Sie die Anrufsteuerung für diese Verbindung.</span><span class="sxs-lookup"><span data-stu-id="1d66c-114">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="1d66c-115">Wenn Sie nicht über belastbare WAN-Links verfügen, weniger als 1000-Benutzer an ihrer Zweigstelle hosten und keine lokal ausgebildeten lync Server-Administratoren verfügbar sind, empfehlen wir, dass Sie eine Survivable Branch-Appliance an der Zweigstelle bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1d66c-115">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="1d66c-116">Wenn Sie zwischen 1000-und 5000-Benutzern an ihrer Zweigstelle hosten, keine robuste WAN-Verbindung haben und die lync Server-Administratoren zur Verfügung stehen, empfehlen wir, dass Sie einen überlebensfähigen Verzweigungs Server mit einem kleinen Gateway auf der Zweigstelle bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1d66c-116">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="1d66c-117">Erwägen Sie auch die Aktivierung der Medienumgehung für Verbindungen mit eingeschränkter Bandbreite, wenn Sie über ein Gatewaypeer mit Unterstützung der Medienumgehung verfügen.</span><span class="sxs-lookup"><span data-stu-id="1d66c-117">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1d66c-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d66c-118">See Also</span></span>


[<span data-ttu-id="1d66c-119">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d66c-119">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

