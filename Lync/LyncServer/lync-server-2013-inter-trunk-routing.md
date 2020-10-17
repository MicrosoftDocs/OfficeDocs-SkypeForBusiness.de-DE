---
title: 'Lync Server 2013: Routing zwischen Trunks'
description: 'Lync Server 2013: Inter-trunk Routing.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Inter-trunk routing
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49733877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e023956f28183423c04e94948acdec0df2c1284
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543971"
---
# <a name="inter-trunk-routing-in-lync-server-2013"></a><span data-ttu-id="7d33f-103">Zwischen trunk Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d33f-103">Inter-trunk routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d33f-104">_**Letztes Änderungsstand des Themas:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="7d33f-104">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="7d33f-105">Lync Server 2013 bietet grundlegende Sitzungsverwaltung über die Unterstützung des intertrunk-Routings.</span><span class="sxs-lookup"><span data-stu-id="7d33f-105">Lync Server 2013 provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="7d33f-106">Diese neue Funktion ermöglicht lync Server das Bereitstellen von Funktionen für die Anrufsteuerung für nachgeschaltete Telefoniesysteme.</span><span class="sxs-lookup"><span data-stu-id="7d33f-106">This new capability enables Lync Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="7d33f-107">Das intertrunk-Routing kann eine IP-Nebenstellenanlage mit einem PSTN-Gateway (Public Switched Telephone Network) verbinden, sodass Anrufe von einem PBX-Telefon (Private Branch Exchange) an das PSTN weitergeleitet werden können und eingehende PSTN-Anrufe an ein PBX-Telefon weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="7d33f-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="7d33f-108">Auf ähnliche Weise können lync Server zwei oder mehr IP-PBX-Systeme miteinander verbinden, sodass Anrufe zwischen Nebenstellen Geräten von den verschiedenen IP-PBX-Systemen getätigt und empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="7d33f-108">Similarly, Lync Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="7d33f-109">In der folgenden Abbildung wird veranschaulicht, lync Server 2013 die Zusammenschaltung zwischen einem PSTN-Gateway und einer IP-Nebenstellenanlage bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="7d33f-109">The following figure illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="7d33f-110">![Lync Server verbinden des PSTN-Gateways/IP-PBX-Diagramms](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server verbinden des PSTN-Gateways/IP-PBX-Diagramms")</span><span class="sxs-lookup"><span data-stu-id="7d33f-110">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="7d33f-111">In der nächsten Abbildung wird lync Server 2013 Verbinden von zwei IP-PBX-Systemen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7d33f-111">The next figure illustrates Lync Server 2013 connecting two IP-PBX systems.</span></span>

<span data-ttu-id="7d33f-112">![Diagramm für lync Server Verbindung zwischen IP-Pax-Systemen](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Diagramm für lync Server Verbindung zwischen IP-Pax-Systemen")</span><span class="sxs-lookup"><span data-stu-id="7d33f-112">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

