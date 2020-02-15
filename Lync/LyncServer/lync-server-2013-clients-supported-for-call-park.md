---
title: 'Lync Server 2013: für das Parken von Anrufen unterstützte Clients'
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
ms.openlocfilehash: ee3916e74a68121b027061429bacb44e2dafacdb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clients-supported-for-call-park-in-lync-server-2013"></a><span data-ttu-id="277ec-102">Für das Parken von Anrufen unterstützte Clients in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="277ec-102">Clients supported for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="277ec-103">_**Letztes Änderungsstand des Themas:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="277ec-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="277ec-104">In diesem Abschnitt werden Clients aufgeführt, die für das Parken von Anrufen verwendet werden können, sowie Clients, die zum Wiederaufnehmen geparkter Anrufe eingesetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="277ec-104">This section identifies the clients that can be used to park calls and the clients that can be used to retrieve parked calls.</span></span>

<div>

## <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="277ec-105">Für das Parken von Anrufen unterstützte Clients</span><span class="sxs-lookup"><span data-stu-id="277ec-105">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="277ec-106">Anrufe von IP-, Nebenstellen-, Festnetz- oder Mobiltelefonen können geparkt werden.</span><span class="sxs-lookup"><span data-stu-id="277ec-106">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="277ec-p101">Nur Audioanrufe können geparkt werden. Das Parken von Chatnachrichten und Konferenzen ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="277ec-p101">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span>



</div>

<span data-ttu-id="277ec-109">Die folgenden Clients können Anrufe mit dem Parken von Anrufen Parken:</span><span class="sxs-lookup"><span data-stu-id="277ec-109">The following clients can use Call Park to park calls:</span></span>

  - <span data-ttu-id="277ec-110">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="277ec-110">Lync 2013</span></span>

  - <span data-ttu-id="277ec-111">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="277ec-111">Lync 2010</span></span>

  - <span data-ttu-id="277ec-112">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="277ec-112">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="277ec-113">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="277ec-113">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="277ec-114">Mobiltelefone können Anrufe nicht mit dem Parken von Anrufen abstellen.</span><span class="sxs-lookup"><span data-stu-id="277ec-114">Mobile phones cannot use Call Park to park calls.</span></span>



</div>

</div>

<div>

## <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="277ec-115">Für das Wiederaufnehmen geparkter Anrufe unterstützte Clients</span><span class="sxs-lookup"><span data-stu-id="277ec-115">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="277ec-p102">Orbitbereiche werden als Blöcke virtueller Durchwahlnummern (Durchwahlnummern, denen kein Benutzer oder Telefon zugewiesen ist) konfiguriert. Wenn Sie Orbits als virtuelle Durchwahlnummern konfigurieren, können Mobil- und Festnetztelefone keine geparkten Anrufe wiederaufnehmen.</span><span class="sxs-lookup"><span data-stu-id="277ec-p102">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>

<span data-ttu-id="277ec-118">Das Wiederaufnehmen geparkter Anrufe durch Partnerbenutzer ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="277ec-118">Federated users cannot retrieve parked calls.</span></span>

<span data-ttu-id="277ec-119">Die folgenden Clients können Anrufe abrufen, die im Parken von Anrufen geparkt sind:</span><span class="sxs-lookup"><span data-stu-id="277ec-119">The following clients can retrieve calls that are parked on Call Park:</span></span>

  - <span data-ttu-id="277ec-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="277ec-120">Lync 2013</span></span>

  - <span data-ttu-id="277ec-121">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="277ec-121">Lync 2010</span></span>

  - <span data-ttu-id="277ec-122">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="277ec-122">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="277ec-123">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="277ec-123">Lync Phone Edition</span></span>

  - <span data-ttu-id="277ec-124">IP-Telefone in öffentlichen Bereichen</span><span class="sxs-lookup"><span data-stu-id="277ec-124">IP common area phones</span></span>

  - <span data-ttu-id="277ec-125">Nicht-IP-Telefone, die mit der lync Server 2013-Infrastruktur verbunden sind, einschließlich Telefone für gemeinsame Bereiche und PBX-Telefone (Private Branch Exchange)</span><span class="sxs-lookup"><span data-stu-id="277ec-125">Non-IP phones that are connected to the Lync Server 2013 infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

