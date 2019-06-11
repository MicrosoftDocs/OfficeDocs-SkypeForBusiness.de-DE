---
title: 'Lync Server 2013: Routing zwischen Trunks'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c1b66ea04ed72bab6d33114f52fa9fe96364b48
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a><span data-ttu-id="5e072-102">Routing zwischen Trunks in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e072-102">Intertrunk routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e072-103">_**Letztes Änderungsdatum des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="5e072-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="5e072-104">Lync Server 2013 kann eine IP-Telefonanlage mit einem PSTN-Gateway (Public Switched Telephone Network) verbinden, damit Anrufe von einem PBX-Telefon an das PSTN weitergeleitet werden können, und eingehende PSTN-Anrufe können an ein PBX-Telefon (Private Branch Exchange) weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="5e072-104">Lync Server 2013 can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a PBX phone can be routed to the PSTN, and incoming PSTN calls can be routed to a private branch exchange (PBX) phone.</span></span> <span data-ttu-id="5e072-105">In ähnlicher Weise kann lync Server 2013 zwei oder mehr IP-PBX-Systeme verbinden, damit Anrufe zwischen PBX-Telefonen von den verschiedenen IP-PBX-Systemen getätigt und empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="5e072-105">Similarly, Lync Server 2013 can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="5e072-106">Dieses intertrunk-Routing Feature kann mithilfe des Cmdlets "lync Server-Verwaltungsshell", " **Satz-CsTrunkConfiguration**", mit dem neuen Parameter PstnUsages konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="5e072-106">This intertrunk routing feature can be configured by using the Lync Server Management Shell cmdlet, **Set-CsTrunkConfiguration**, with the new parameter, PstnUsages.</span></span> <span data-ttu-id="5e072-107">Dieser Parameter gibt den Satz der zu verwendenden PSTN-Verwendungsdaten Sätze an.</span><span class="sxs-lookup"><span data-stu-id="5e072-107">This parameter specifies the set of PSTN usage records to use.</span></span> <span data-ttu-id="5e072-108">Ein trunk verwendet diese PSTN-Nutzung, um eine Route zu ermitteln und alle eingehenden Anrufe entsprechend weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="5e072-108">A trunk uses this PSTN usage to determine a route and to route all incoming calls accordingly.</span></span>

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

<span data-ttu-id="5e072-109">Das folgende Diagramm veranschaulicht, wie lync Server 2013 die Zusammenschaltung zwischen einem PSTN-Gateway und einer IP-Telefonanlage bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="5e072-109">The following diagram illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="5e072-110">**Intertrunk-Routing zwischen Gateway und IP-PBX**</span><span class="sxs-lookup"><span data-stu-id="5e072-110">**Intertrunk routing between gateway and IP PBX**</span></span>

<span data-ttu-id="5e072-111">![Lync Server-Verbindung zwischen PSTN-Gateway/IP-PBX-Diagramm] (images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server-Verbindung zwischen PSTN-Gateway/IP-PBX-Diagramm")</span><span class="sxs-lookup"><span data-stu-id="5e072-111">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="5e072-112">Das folgende Diagramm zeigt die Verbindung zwischen zwei IP-PBX-Systemen durch lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e072-112">The following diagram illustrates Lync Server 2013 interconnecting two IP-PBX systems.</span></span>

<span data-ttu-id="5e072-113">**Intertrunk-Routing zwischen zwei IP-PBX-Anlagen**</span><span class="sxs-lookup"><span data-stu-id="5e072-113">**Intertrunk routing between two IP PBXs**</span></span>

<span data-ttu-id="5e072-114">![Lync Server-Verbindung zwischen IP-Pax-Systemen (Diagramm] ) (images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server-Verbindung zwischen IP-Pax-Systemen (Diagramm") )</span><span class="sxs-lookup"><span data-stu-id="5e072-114">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

