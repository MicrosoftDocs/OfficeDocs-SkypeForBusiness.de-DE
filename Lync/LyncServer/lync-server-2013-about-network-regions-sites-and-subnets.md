---
title: 'Lync Server 2013: Informationen zu netzwerkregionen, Standorten und Subnetzen'
description: 'Lync Server 2013: Informationen zu netzwerkregionen, Standorten und Subnetzen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3c7f660f3c72003527e0721c3f9702865e9b9b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568931"
---
# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="ccc38-103">Informationen zu netzwerkregionen, Standorten und Subnetzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc38-103">About network regions, sites, and subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccc38-104">_**Letztes Änderungsstand des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="ccc38-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="ccc38-p101">Für die in diesem Abschnitt beschriebenen erweiterten Enterprise-VoIP-Funktionen gelten einige gemeinsame Konfigurationsanforderungen für Netzwerkregionen, Netzwerkstandorte und Subnetze. Beispielsweise ist es für alle drei erweiterten Funktionen erforderlich, dass jedes Subnetz in Ihrer Topologie einem bestimmten *Netzwerkstandort* und jeder Netzwerkstandort einer *Netzwerkregion* zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="ccc38-p101">The advanced Enterprise Voice features described in this section share certain configuration requirements for network regions, network sites, and subnets. For example, all three advanced features require that each subnet in your topology be associated with a specific *network site*, and each network site must be associated with a *network region*.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ccc38-107">Bevor Sie mit der Netzwerkkonfiguration für die Anrufsteuerung, mit E9-1-1 oder mit der medienumgehung beginnen, stellen Sie sicher, dass Sie in der Planungsdokumentation zusätzliche Informationen zu den Netzwerkeinstellungen im Thema <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Features in lync Server 2013</A> überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="ccc38-107">Before you begin network configuration for call admission control, E9-1-1, or media bypass, make sure that you reviewed additional information about network settings in the <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A> topic in the Planning documentation.</span></span> <span data-ttu-id="ccc38-108">Ausführliche Informationen zur Netzwerkkonfiguration in erster Linie zur Anrufsteuerung finden Sie auch unter <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definieren der Anforderungen für die Anrufsteuerung in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="ccc38-108">For details about network configuration primarily about call admission control, also see <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="ccc38-109">Für die Anrufsteuerung und E9-1-1 gelten bei den Netzwerkstandorten zusätzliche Konfigurationsanforderungen:</span><span class="sxs-lookup"><span data-stu-id="ccc38-109">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

  - <span data-ttu-id="ccc38-110">Die Anrufsteuerung erfordert, dass ein *Bandbreitenrichtlinienprofil* für jeden Standort angegeben wird, für den WAN-Bandbreiteneinschränkungen gelten.</span><span class="sxs-lookup"><span data-stu-id="ccc38-110">Call admission control requires that a *bandwidth policy profile* be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="ccc38-111">Wenn Sie die Bereitstellung der Anrufsteuerung planen, müssen Sie [bandbreitenrichtlinienprofile in lync Server 2013 erstellen](lync-server-2013-create-bandwidth-policy-profiles.md) , bevor Sie Ihre Netzwerkstandorte konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ccc38-111">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

  - <span data-ttu-id="ccc38-112">Für E9-1-1 ist es erforderlich, dass für jeden Standort eine *Standortrichtlinie* angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="ccc38-112">E9-1-1 requires that a *location policy* be specified for each site.</span></span> <span data-ttu-id="ccc38-113">Wenn Sie die Bereitstellung von E9-1-1 planen, müssen Sie [Standortrichtlinien in lync Server 2013 erstellen](lync-server-2013-create-location-policies.md) , bevor Sie Ihre Netzwerkstandorte konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ccc38-113">If you plan to deploy E9-1-1, you must [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) before you configure your network sites.</span></span>

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a><span data-ttu-id="ccc38-114">Erstellen oder Ändern von Netzwerkregionen, Netzwerkstandorten und Subnetzen</span><span class="sxs-lookup"><span data-stu-id="ccc38-114">Create or Modify Network Regions, Network Sites, and Subnets</span></span>

<span data-ttu-id="ccc38-p105">In den folgenden Themen werden die Schritte zum Erstellen oder Ändern von Netzwerkregionen und Netzwerkstandorten sowie zum Zuordnen von Subnetzen zu Netzwerkstandorten beschrieben. Diese Themen sind nicht auf eine bestimmte erweiterte Enterprise-VoIP-Funktion beschränkt.</span><span class="sxs-lookup"><span data-stu-id="ccc38-p105">The following topics provide steps to create or modify network regions and network sites, and to associate subnets with network sites. These topics are not specific to any particular advanced Enterprise Voice feature.</span></span>

  - [<span data-ttu-id="ccc38-117">Erstellen oder Ändern einer netzwerkregion in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc38-117">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)

  - [<span data-ttu-id="ccc38-118">Erstellen oder Ändern eines Netzwerkstandorts in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc38-118">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)

  - [<span data-ttu-id="ccc38-119">Zuordnen eines Subnetzes zu einem Netzwerkstandort in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc38-119">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

