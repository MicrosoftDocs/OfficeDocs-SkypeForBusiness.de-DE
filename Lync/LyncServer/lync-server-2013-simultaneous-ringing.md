---
title: 'Lync Server 2013: Gleichzeitiges Klingeln'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e3104da5e7d351bda26698087e97106cafbdff4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a><span data-ttu-id="42a82-102">Gleichzeitiges Klingeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42a82-102">Simultaneous ringing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42a82-103">_**Letztes Änderungsstand des Themas:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="42a82-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="42a82-104">Wenn für den angerufenen das gleichzeitige Klingeln aktiviert ist, analysiert das standortbasierte Routing den Standort des anrufenden Teilnehmers und die Endpunkte der angerufenen Parteien, um zu bestimmen, ob der Anruf weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="42a82-104">When the called party has simultaneous ringing enabled, Location-Based Routing analyzes the location of the calling party and the endpoints of the called parties to determine whether the call should be routed.</span></span>

<span data-ttu-id="42a82-105">Die folgende Tabelle zeigt einen Benutzer, der mit gleichzeitigem Klingeln konfiguriert ist, und das gleichzeitige Klingeln-Ziel ist ein Benutzer am gleichen Netzwerkstandort, an einem anderen Netzwerkstandort oder an einem unbekannten Netzwerkstandort.</span><span class="sxs-lookup"><span data-stu-id="42a82-105">The following table illustrates a user configured with simultaneous ringing, and the simultaneous ringing target is a user in the same network site, in a different network site, or in an unknown network site.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42a82-106">Eingehender PSTN-Anruf für</span><span class="sxs-lookup"><span data-stu-id="42a82-106">Incoming PSTN call for</span></span></th>
<th><span data-ttu-id="42a82-107">Befindet sich am gleichen Netzwerkstandort wie der angerufene</span><span class="sxs-lookup"><span data-stu-id="42a82-107">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="42a82-108">Befindet sich an einem anderen Netzwerkstandort als der angerufene</span><span class="sxs-lookup"><span data-stu-id="42a82-108">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="42a82-109">Befindet sich an einem unbekannten Netzwerkstandort oder ist für standortbasiertes Routing nicht aktiviert</span><span class="sxs-lookup"><span data-stu-id="42a82-109">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42a82-110">Lync-Benutzer</span><span class="sxs-lookup"><span data-stu-id="42a82-110">Lync user</span></span></p></td>
<td><p><span data-ttu-id="42a82-111">Gleichzeitiges Klingeln zulässig</span><span class="sxs-lookup"><span data-stu-id="42a82-111">Simultaneous ring allowed</span></span></p></td>
<td><p><span data-ttu-id="42a82-112">Gleichzeitiges Klingeln nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="42a82-112">Simultaneous ring not allowed</span></span></p></td>
<td><p><span data-ttu-id="42a82-113">Gleichzeitiges Klingeln nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="42a82-113">Simultaneous ring not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="42a82-114">Die folgende Tabelle zeigt einen Aufruf von einem lync-Benutzer (dh lync-Anrufer) am gleichen Netzwerkstandort, an einem anderen Netzwerkstandort oder an einem unbekannten Netzwerkstandort.</span><span class="sxs-lookup"><span data-stu-id="42a82-114">The following table illustrates a call from a Lync user (i.e. Lync caller) in the same network site, in a different network site, or from an unknown network site.</span></span> <span data-ttu-id="42a82-115">Der angerufene verfügt über einen PSTN-Endpunkt (also ein Mobiltelefon), der als gleichzeitiger Ring-Zielwert konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="42a82-115">The callee has a PSTN endpoint (i.e. cellphone) configured as a simultaneous ring target.</span></span> <span data-ttu-id="42a82-116">In diesem Szenario wird durch das standortbasierte Routing ermittelt, ob der Anruf an das Ziel für das gleichzeitige Klingeln (also das Mobiltelefon) des angerufenen weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="42a82-116">In this scenario, Location-Based Routing will determine whether the call should be routed to the simultaneous ring target (i.e. cellphone) of the callee or not.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42a82-117">Gleichzeitiges Klingel Ziel</span><span class="sxs-lookup"><span data-stu-id="42a82-117">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="42a82-118">Befindet sich am gleichen Netzwerkstandort wie der angerufene</span><span class="sxs-lookup"><span data-stu-id="42a82-118">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="42a82-119">Befindet sich an einem anderen Netzwerkstandort als der angerufene</span><span class="sxs-lookup"><span data-stu-id="42a82-119">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="42a82-120">Befindet sich an einem unbekannten Netzwerkstandort oder ist für standortbasiertes Routing nicht aktiviert</span><span class="sxs-lookup"><span data-stu-id="42a82-120">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42a82-121">PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="42a82-121">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="42a82-122">Gleichzeitiges Klingeln über die Website VoIP-Routing Richtlinie des Anrufers zulässig</span><span class="sxs-lookup"><span data-stu-id="42a82-122">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="42a82-123">Gleichzeitiges Klingeln über die Website VoIP-Routing Richtlinie des Anrufers zulässig</span><span class="sxs-lookup"><span data-stu-id="42a82-123">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="42a82-124">Gleichzeitiges Klingeln über die VoIP-Richtlinie des Anrufers in Trunks, die nicht für standortbasiertes Routing aktiviert sind</span><span class="sxs-lookup"><span data-stu-id="42a82-124">Simultaneous ring allowed through the caller’s voice policy to trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="42a82-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42a82-125">See Also</span></span>


[<span data-ttu-id="42a82-126">Szenarien für das standortbasierte Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42a82-126">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

