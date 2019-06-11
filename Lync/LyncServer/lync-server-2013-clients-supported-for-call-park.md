---
title: 'Lync Server 2013: Unterstützte Clients für das Parken von Anrufen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Clients supported for Call Park
ms:assetid: c236d2ba-9d83-418c-9cbc-92541f115fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412958(v=OCS.15)
ms:contentKeyID: 48185320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46b9ac77a82cf8d833c3f06a8fe3c738e2501937
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clients-supported-for-call-park-in-lync-server-2013"></a><span data-ttu-id="89c0c-102">Unterstützte Clients für das Parken von Anrufen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89c0c-102">Clients supported for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89c0c-103">_**Letztes Änderungsdatum des Themas:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="89c0c-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="89c0c-104">In diesem Abschnitt werden die Clients identifiziert, die zum Parken von Anrufen und der Clients verwendet werden können, die zum Abrufen von geparkten Anrufen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="89c0c-104">This section identifies the clients that can be used to park calls and the clients that can be used to retrieve parked calls.</span></span>

<div>

## <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="89c0c-105">Für das Parken von Anrufen unterstützte Clients</span><span class="sxs-lookup"><span data-stu-id="89c0c-105">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="89c0c-106">Anrufe von IP-, Nebenstellen-, Festnetz- oder Mobiltelefonen können geparkt werden.</span><span class="sxs-lookup"><span data-stu-id="89c0c-106">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="89c0c-p101">Nur Audioanrufe können geparkt werden. Das Parken von Chatnachrichten und Konferenzen ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="89c0c-p101">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span>



</div>

<span data-ttu-id="89c0c-109">Die folgenden Clients können den Anruf Park zum Parken von Anrufen verwenden:</span><span class="sxs-lookup"><span data-stu-id="89c0c-109">The following clients can use Call Park to park calls:</span></span>

  - <span data-ttu-id="89c0c-110">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="89c0c-110">Lync 2013</span></span>

  - <span data-ttu-id="89c0c-111">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="89c0c-111">Lync 2010</span></span>

  - <span data-ttu-id="89c0c-112">Lync 2010-Vermittlung</span><span class="sxs-lookup"><span data-stu-id="89c0c-112">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="89c0c-113">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="89c0c-113">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="89c0c-114">Mobiltelefone können den Anruf Park nicht zum Parken von Anrufen verwenden.</span><span class="sxs-lookup"><span data-stu-id="89c0c-114">Mobile phones cannot use Call Park to park calls.</span></span>



</div>

</div>

<div>

## <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="89c0c-115">Für das Wiederaufnehmen geparkter Anrufe unterstützte Clients</span><span class="sxs-lookup"><span data-stu-id="89c0c-115">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="89c0c-p102">Orbitbereiche werden als Blöcke virtueller Durchwahlnummern (Durchwahlnummern, denen kein Benutzer oder Telefon zugewiesen ist) konfiguriert. Wenn Sie Orbits als virtuelle Durchwahlnummern konfigurieren, können Mobil- und Festnetztelefone keine geparkten Anrufe wiederaufnehmen.</span><span class="sxs-lookup"><span data-stu-id="89c0c-p102">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>

<span data-ttu-id="89c0c-118">Das Wiederaufnehmen geparkter Anrufe durch Partnerbenutzer ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="89c0c-118">Federated users cannot retrieve parked calls.</span></span>

<span data-ttu-id="89c0c-119">Die folgenden Clients können Anrufe abrufen, die im Park des Anrufs abgestellt sind:</span><span class="sxs-lookup"><span data-stu-id="89c0c-119">The following clients can retrieve calls that are parked on Call Park:</span></span>

  - <span data-ttu-id="89c0c-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="89c0c-120">Lync 2013</span></span>

  - <span data-ttu-id="89c0c-121">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="89c0c-121">Lync 2010</span></span>

  - <span data-ttu-id="89c0c-122">Lync 2010-Vermittlung</span><span class="sxs-lookup"><span data-stu-id="89c0c-122">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="89c0c-123">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="89c0c-123">Lync Phone Edition</span></span>

  - <span data-ttu-id="89c0c-124">IP-Telefone in öffentlichen Bereichen</span><span class="sxs-lookup"><span data-stu-id="89c0c-124">IP common area phones</span></span>

  - <span data-ttu-id="89c0c-125">Nicht-IP-Telefone, die mit der lync Server 2013-Infrastruktur verbunden sind, einschließlich Telefone im öffentlichen Bereich und Private Branch Exchange (PBX)-Telefone</span><span class="sxs-lookup"><span data-stu-id="89c0c-125">Non-IP phones that are connected to the Lync Server 2013 infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

