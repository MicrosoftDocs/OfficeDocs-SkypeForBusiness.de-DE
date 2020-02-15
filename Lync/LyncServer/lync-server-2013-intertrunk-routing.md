---
title: 'Lync Server 2013: intertrunk-Routing'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23aab6df352b162f7f389ef56fb2300f01654edb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a><span data-ttu-id="89943-102">Intertrunk-Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89943-102">Intertrunk routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89943-103">_**Letztes Änderungsstand des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="89943-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="89943-104">Lync Server 2013 können eine IP-Nebenstellenanlage mit einem PSTN-Gateway (Public Switched Telephone Network) verbinden, sodass Anrufe von einem PBX-Telefon an das PSTN weitergeleitet werden können und eingehende PSTN-Anrufe an ein PBX-Telefon (Private Branch Exchange) weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="89943-104">Lync Server 2013 can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a PBX phone can be routed to the PSTN, and incoming PSTN calls can be routed to a private branch exchange (PBX) phone.</span></span> <span data-ttu-id="89943-105">Auf ähnliche Weise können lync Server 2013 zwei oder mehr IP-PBX-Systeme miteinander verbinden, sodass Anrufe zwischen Nebenstellen Geräten von den verschiedenen IP-PBX-Systemen getätigt und empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="89943-105">Similarly, Lync Server 2013 can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="89943-106">Dieses intertrunk-Routing Feature kann mithilfe des lync Server-Verwaltungsshell-Cmdlets, " **CsTrunkConfiguration**", mit dem neuen Parameter "PstnUsages" konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="89943-106">This intertrunk routing feature can be configured by using the Lync Server Management Shell cmdlet, **Set-CsTrunkConfiguration**, with the new parameter, PstnUsages.</span></span> <span data-ttu-id="89943-107">Dieser Parameter gibt die Gruppe der zu verwendenden PSTN-Verwendungsdaten Sätze an.</span><span class="sxs-lookup"><span data-stu-id="89943-107">This parameter specifies the set of PSTN usage records to use.</span></span> <span data-ttu-id="89943-108">Ein trunk verwendet diese PSTN-Verwendung, um eine Route zu bestimmen und alle eingehenden Anrufe entsprechend weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="89943-108">A trunk uses this PSTN usage to determine a route and to route all incoming calls accordingly.</span></span>

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

<span data-ttu-id="89943-109">Das folgende Diagramm zeigt lync Server 2013 die Bereitstellung von Verbindungen zwischen einem PSTN-Gateway und einer IP-Nebenstellenanlage.</span><span class="sxs-lookup"><span data-stu-id="89943-109">The following diagram illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="89943-110">**Intertrunk-Routing zwischen Gateway und IP-Nebenstellenanlage**</span><span class="sxs-lookup"><span data-stu-id="89943-110">**Intertrunk routing between gateway and IP PBX**</span></span>

<span data-ttu-id="89943-111">![Lync Server verbinden des PSTN-Gateways/IP-PBX-Diagramms](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server verbinden des PSTN-Gateways/IP-PBX-Diagramms")</span><span class="sxs-lookup"><span data-stu-id="89943-111">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="89943-112">Das folgende Diagramm veranschaulicht lync Server 2013 Verbinden von zwei IP-PBX-Systemen.</span><span class="sxs-lookup"><span data-stu-id="89943-112">The following diagram illustrates Lync Server 2013 interconnecting two IP-PBX systems.</span></span>

<span data-ttu-id="89943-113">**Intertrunk-Routing zwischen zwei IP-Nebenstellenanlagen**</span><span class="sxs-lookup"><span data-stu-id="89943-113">**Intertrunk routing between two IP PBXs**</span></span>

<span data-ttu-id="89943-114">![Diagramm für lync Server Verbindung zwischen IP-Pax-Systemen](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Diagramm für lync Server Verbindung zwischen IP-Pax-Systemen")</span><span class="sxs-lookup"><span data-stu-id="89943-114">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

