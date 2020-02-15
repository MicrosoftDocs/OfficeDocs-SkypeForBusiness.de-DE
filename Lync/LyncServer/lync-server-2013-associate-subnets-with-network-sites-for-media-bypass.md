---
title: 'Lync Server 2013: Zuordnen von Subnetzen zu Netzwerkstandorten für die medienumgehung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbe244426b6c2b7f83ef8070f995305a2a02ef31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="2a705-102">Zuordnen von Subnetzen zu Netzwerkstandorten für die medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a705-102">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a705-103">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="2a705-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2a705-104">In diesem Thema wird davon ausgegangen, dass Sie die globalen Einstellungen für die Medienumgehung sowie die Netzwerkregion und Netzwerkstandorte für die Medienumgehung konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="2a705-104">This topic assumes that you have configured media bypass global settings and that you have configured network region and network sites for media bypass.</span></span>



</div>

<span data-ttu-id="2a705-p101">Jedes Subnetz in Ihrem Netzwerk muss einem bestimmten Netzwerkstandort zugeordnet sein. Anhand dieser Subnetzinformationen wird der Netzwerkstandort ermittelt, an dem sich ein Endpunkt befindet. Wenn die Standorte beider Teilnehmer einer Sitzung bekannt sind, kann die Medienumgehung das Ziel ermitteln, an das die Mediendaten zur Verarbeitung gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2a705-p101">Every subnet in your network must be associated with a specific network site. This is because subnet information is used to determine the network site on which an endpoint is located. When the locations of both parties in a session are known, media bypass can determine where to send media for processing.</span></span>

<span data-ttu-id="2a705-108">Für die Medienumgehung gelten keine speziellen Anforderungen für die Zuordnung von Subnetzen zu Netzwerkstandorten.</span><span class="sxs-lookup"><span data-stu-id="2a705-108">Media bypass does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="2a705-109">Um eine Zuordnung zwischen den Subnetzen und Netzwerkstandorten in Ihrer Topologie zu erstellen, führen Sie die Verfahren unter Zuordnen eines Subnetzes [mit einem Netzwerkstandort in lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)aus.</span><span class="sxs-lookup"><span data-stu-id="2a705-109">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a><span data-ttu-id="2a705-110">Nächste Schritte: Erstellen von Bandbreitenrichtlinienprofilen</span><span class="sxs-lookup"><span data-stu-id="2a705-110">Next Steps: Create Bandwidth Policy Profiles</span></span>

<span data-ttu-id="2a705-p103">Nachdem Sie die Subnetze und Netzwerkstandorte für die Medienumgehung zugeordnet haben, müssen Sie mindestens ein Bandbreitenrichtlinienprofil erstellen, mit dem Subnetze für die Medienumgehung in Subnetze mit und ohne gute Konnektivität unterteilt werden. Alle Subnetze innerhalb einer Netzwerkregion mit Netzwerkstandorten, für die keine Bandbreiteneinschränkungen gelten, verfügen über eine gute Konnektivität. Für diese Subnetze kann daher die Medienumgehung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2a705-p103">After you associate subnets with network sites for media bypass, you must create one or more bandwidth policy profiles that will partition subnets into those with good connectivity and those without, for the purposes of media bypass. All subnets within a network region with network sites that do not have bandwidth constraints have good connectivity, and, therefore, those subnets can use media bypass.</span></span>

<span data-ttu-id="2a705-113">Verfahren zum Konfigurieren von Bandbreitenrichtlinien Profilen finden Sie unter [Create Bandwidth Policy Profiles in lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="2a705-113">For procedures to configure bandwidth policy profiles, see [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

