---
title: 'Lync Server 2013: Zuordnen von Subnetzen zu Netzwerkstandorten für die Anrufsteuerung'
description: 'Lync Server 2013: Zuordnen von Subnetzen zu Netzwerkstandorten für die Anrufsteuerung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for CAC
ms:assetid: a749c9b3-15f3-4e74-9f43-1507d3c2c940
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412786(v=OCS.15)
ms:contentKeyID: 48185017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d68607c1674bb964c27c8408583be7f5e092f4c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560501"
---
# <a name="associate-subnets-with-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="458e9-103">Zuordnen von Subnetzen zu Netzwerkstandorten für die Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="458e9-103">Associate subnets with network sites for CAC in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="458e9-104">_**Letztes Änderungsstand des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="458e9-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="458e9-105">Jedes Subnetz in Ihrem Netzwerk muss einem bestimmten Netzwerkstandort zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="458e9-105">Every subnet in your network must be associated with a specific network site.</span></span> <span data-ttu-id="458e9-106">Anhand dieser Subnetzinformationen wird der Netzwerkstandort ermittelt, an dem sich ein Endpunkt befindet.</span><span class="sxs-lookup"><span data-stu-id="458e9-106">This is because subnet information is used to determine the network site on which an endpoint is located.</span></span> <span data-ttu-id="458e9-107">Wenn die Standorte beider Parteien in einer Sitzung bekannt sind, kann die Anrufsteuerung (Call Admission Control, CAC) ermitteln, ob genügend Bandbreite vorhanden ist, um einen Anruf einzurichten.</span><span class="sxs-lookup"><span data-stu-id="458e9-107">When the locations of both parties in a session are known, call admission control (CAC) can determine if there is sufficient bandwidth to establish a call.</span></span>

<span data-ttu-id="458e9-108">Die Anrufsteuerung hat keine besonderen Anforderungen für das Zuordnen von Subnetzen zu Netzwerkstandorten.</span><span class="sxs-lookup"><span data-stu-id="458e9-108">Call admission control does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="458e9-109">Um eine Zuordnung zwischen den Subnetzen und Netzwerkstandorten in Ihrer Topologie zu erstellen, führen Sie die Verfahren unter Zuordnen eines Subnetzes [mit einem Netzwerkstandort in lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)aus.</span><span class="sxs-lookup"><span data-stu-id="458e9-109">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span> <span data-ttu-id="458e9-110">Informationen zum Anzeigen der Netzwerkstandorte (und der entsprechenden Subnetze) in der Beispiel Netzwerktopologie für die Anrufsteuerung finden Sie unter [Beispiel: Sammeln Ihrer Anforderungen für die Anrufsteuerung in lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="458e9-110">To view the network sites (and their respective subnets) in the example network topology for call admission control, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

