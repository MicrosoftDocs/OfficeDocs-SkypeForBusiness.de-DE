---
title: 'Lync Server 2013: Zuordnen von Subnetzen zu Netzwerk Websites für die medienumgehung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c0f2d6461264ff8b54609e280c59986e1a923c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839910"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="3d65e-102">Zuordnen von Subnetzen zu Netzwerk Websites zur medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d65e-102">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d65e-103">_**Letztes Änderungsdatum des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="3d65e-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3d65e-104">In diesem Thema wird davon ausgegangen, dass Sie die globalen Einstellungen für die medienumgehung konfiguriert haben und dass Sie die netzwerkregion und Netzwerk Websites für die medienumgehung konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="3d65e-104">This topic assumes that you have configured media bypass global settings and that you have configured network region and network sites for media bypass.</span></span>



</div>

<span data-ttu-id="3d65e-105">Jedes Subnetz in Ihrem Netzwerk muss einer bestimmten Netzwerk Website zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="3d65e-105">Every subnet in your network must be associated with a specific network site.</span></span> <span data-ttu-id="3d65e-106">Dies liegt daran, dass die Netzwerk Website, auf der sich ein Endpunkt befindet, mithilfe von Subnetinformationen ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="3d65e-106">This is because subnet information is used to determine the network site on which an endpoint is located.</span></span> <span data-ttu-id="3d65e-107">Wenn die Speicherorte beider Parteien in einer Sitzung bekannt sind, kann die medienumgehung bestimmen, wohin Medien zur Verarbeitung gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3d65e-107">When the locations of both parties in a session are known, media bypass can determine where to send media for processing.</span></span>

<span data-ttu-id="3d65e-108">Die medienumgehung hat keine besonderen Anforderungen für das Zuordnen von Subnetzen zu Netzwerkstandorten.</span><span class="sxs-lookup"><span data-stu-id="3d65e-108">Media bypass does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="3d65e-109">Wenn Sie eine Zuordnung zwischen den Subnetzen und Netzwerkstandorten in Ihrer Topologie erstellen möchten, führen Sie die Verfahren unter Zuordnen eines Subnetzes [zu einer Netzwerk Website in lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)aus.</span><span class="sxs-lookup"><span data-stu-id="3d65e-109">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a><span data-ttu-id="3d65e-110">Nächste Schritte: Erstellen von Bandbreitenrichtlinien Profilen</span><span class="sxs-lookup"><span data-stu-id="3d65e-110">Next Steps: Create Bandwidth Policy Profiles</span></span>

<span data-ttu-id="3d65e-111">Nachdem Sie Subnetze mit Netzwerk Websites für die medienumgehung verknüpft haben, müssen Sie mindestens ein bandbreitenrichtlinienprofil erstellen, mit dem Subnetze in Personen mit guter Konnektivität und ohne zum Zweck der medienumgehung partitioniert werden.</span><span class="sxs-lookup"><span data-stu-id="3d65e-111">After you associate subnets with network sites for media bypass, you must create one or more bandwidth policy profiles that will partition subnets into those with good connectivity and those without, for the purposes of media bypass.</span></span> <span data-ttu-id="3d65e-112">Alle Subnetze in einem Netzwerkbereich mit Netzwerk Websites, die keine Bandbreiteneinschränkungen aufweisen, verfügen über eine gute Konnektivität, und daher können diese Subnetze die medienumgehung verwenden.</span><span class="sxs-lookup"><span data-stu-id="3d65e-112">All subnets within a network region with network sites that do not have bandwidth constraints have good connectivity, and, therefore, those subnets can use media bypass.</span></span>

<span data-ttu-id="3d65e-113">Verfahren zum Konfigurieren von Profilen für Bandbreitenrichtlinien finden Sie unter [Erstellen von Bandbreitenrichtlinien Profilen in lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3d65e-113">For procedures to configure bandwidth policy profiles, see [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

