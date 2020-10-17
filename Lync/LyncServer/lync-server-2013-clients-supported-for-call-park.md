---
title: 'Lync Server 2013: für das Parken von Anrufen unterstützte Clients'
description: 'Lync Server 2013: für das Parken von Anrufen unterstützte Clients.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Clients supported for Call Park
ms:assetid: c236d2ba-9d83-418c-9cbc-92541f115fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412958(v=OCS.15)
ms:contentKeyID: 48185320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a923f0e62c246a12b811628d578ab571f4f13e36
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543491"
---
# <a name="clients-supported-for-call-park-in-lync-server-2013"></a><span data-ttu-id="3c8d6-103">Für das Parken von Anrufen unterstützte Clients in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c8d6-103">Clients supported for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c8d6-104">_**Letztes Änderungsstand des Themas:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="3c8d6-104">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="3c8d6-105">In diesem Abschnitt werden Clients aufgeführt, die für das Parken von Anrufen verwendet werden können, sowie Clients, die zum Wiederaufnehmen geparkter Anrufe eingesetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="3c8d6-105">This section identifies the clients that can be used to park calls and the clients that can be used to retrieve parked calls.</span></span>

<div>

## <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="3c8d6-106">Für das Parken von Anrufen unterstützte Clients</span><span class="sxs-lookup"><span data-stu-id="3c8d6-106">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="3c8d6-107">Anrufe von IP-, Nebenstellen-, Festnetz- oder Mobiltelefonen können geparkt werden.</span><span class="sxs-lookup"><span data-stu-id="3c8d6-107">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3c8d6-p101">Nur Audioanrufe können geparkt werden. Das Parken von Chatnachrichten und Konferenzen ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="3c8d6-p101">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span>



</div>

<span data-ttu-id="3c8d6-110">Die folgenden Clients können Anrufe mit dem Parken von Anrufen Parken:</span><span class="sxs-lookup"><span data-stu-id="3c8d6-110">The following clients can use Call Park to park calls:</span></span>

  - <span data-ttu-id="3c8d6-111">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="3c8d6-111">Lync 2013</span></span>

  - <span data-ttu-id="3c8d6-112">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="3c8d6-112">Lync 2010</span></span>

  - <span data-ttu-id="3c8d6-113">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="3c8d6-113">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="3c8d6-114">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="3c8d6-114">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3c8d6-115">Mobiltelefone können Anrufe nicht mit dem Parken von Anrufen abstellen.</span><span class="sxs-lookup"><span data-stu-id="3c8d6-115">Mobile phones cannot use Call Park to park calls.</span></span>



</div>

</div>

<div>

## <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="3c8d6-116">Für das Wiederaufnehmen geparkter Anrufe unterstützte Clients</span><span class="sxs-lookup"><span data-stu-id="3c8d6-116">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="3c8d6-p102">Orbitbereiche werden als Blöcke virtueller Durchwahlnummern (Durchwahlnummern, denen kein Benutzer oder Telefon zugewiesen ist) konfiguriert. Wenn Sie Orbits als virtuelle Durchwahlnummern konfigurieren, können Mobil- und Festnetztelefone keine geparkten Anrufe wiederaufnehmen.</span><span class="sxs-lookup"><span data-stu-id="3c8d6-p102">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>

<span data-ttu-id="3c8d6-119">Das Wiederaufnehmen geparkter Anrufe durch Partnerbenutzer ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="3c8d6-119">Federated users cannot retrieve parked calls.</span></span>

<span data-ttu-id="3c8d6-120">Die folgenden Clients können Anrufe abrufen, die im Parken von Anrufen geparkt sind:</span><span class="sxs-lookup"><span data-stu-id="3c8d6-120">The following clients can retrieve calls that are parked on Call Park:</span></span>

  - <span data-ttu-id="3c8d6-121">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="3c8d6-121">Lync 2013</span></span>

  - <span data-ttu-id="3c8d6-122">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="3c8d6-122">Lync 2010</span></span>

  - <span data-ttu-id="3c8d6-123">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="3c8d6-123">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="3c8d6-124">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="3c8d6-124">Lync Phone Edition</span></span>

  - <span data-ttu-id="3c8d6-125">IP-Telefone in öffentlichen Bereichen</span><span class="sxs-lookup"><span data-stu-id="3c8d6-125">IP common area phones</span></span>

  - <span data-ttu-id="3c8d6-126">Nicht-IP-Telefone, die mit der lync Server 2013-Infrastruktur verbunden sind, einschließlich Telefone für gemeinsame Bereiche und PBX-Telefone (Private Branch Exchange)</span><span class="sxs-lookup"><span data-stu-id="3c8d6-126">Non-IP phones that are connected to the Lync Server 2013 infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

