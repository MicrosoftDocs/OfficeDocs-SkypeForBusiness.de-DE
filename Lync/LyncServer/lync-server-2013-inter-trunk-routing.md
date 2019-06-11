---
title: 'Lync Server 2013: zwischen trunk-Routing'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Inter-trunk routing
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49733877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 204402ba6620fa75b64bb9710ce979b44b63f412
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="inter-trunk-routing-in-lync-server-2013"></a><span data-ttu-id="0b094-102">Zwischen trunk-Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b094-102">Inter-trunk routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b094-103">_**Letztes Änderungsdatum des Themas:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="0b094-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="0b094-104">Lync Server 2013 bietet grundlegende Sitzungsverwaltung durch die Unterstützung von intertrunk-Routing.</span><span class="sxs-lookup"><span data-stu-id="0b094-104">Lync Server 2013 provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="0b094-105">Mit dieser neuen Funktion kann lync Server Funktionen zur Anrufsteuerung für Downstream-Telefoniesysteme bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0b094-105">This new capability enables Lync Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="0b094-106">Durch das Routing zwischen Trunks kann eine IP-Nebenstellenanlage mit einem PSTN-Gateway (Public Switched Telephone Network, Festnetz) verbunden werden, sodass Anrufe von einem Nebenstellentelefon an das Festnetz und eingehende Festnetzanrufe an ein Nebenstellentelefon weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="0b094-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="0b094-107">In ähnlicher Weise kann lync Server zwei oder mehr IP-PBX-Systeme verbinden, damit Anrufe zwischen PBX-Telefonen von den verschiedenen IP-PBX-Systemen getätigt und empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="0b094-107">Similarly, Lync Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="0b094-108">Die folgende Abbildung zeigt, wie lync Server 2013 die Interkonnektivität zwischen einem PSTN-Gateway und einer IP-Telefonanlage bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="0b094-108">The following figure illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="0b094-109">![Lync Server-Verbindung zwischen PSTN-Gateway/IP-PBX-Diagramm] (images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server-Verbindung zwischen PSTN-Gateway/IP-PBX-Diagramm")</span><span class="sxs-lookup"><span data-stu-id="0b094-109">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="0b094-110">Die nächste Abbildung zeigt die lync Server 2013-Verbindung zwischen zwei IP-PBX-Systemen.</span><span class="sxs-lookup"><span data-stu-id="0b094-110">The next figure illustrates Lync Server 2013 connecting two IP-PBX systems.</span></span>

<span data-ttu-id="0b094-111">![Lync Server-Verbindung zwischen IP-Pax-Systemen (Diagramm] ) (images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server-Verbindung zwischen IP-Pax-Systemen (Diagramm") )</span><span class="sxs-lookup"><span data-stu-id="0b094-111">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

