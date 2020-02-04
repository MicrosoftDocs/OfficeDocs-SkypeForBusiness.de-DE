---
title: 'Lync Server 2013: Paralleles Anrufen'
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
ms.openlocfilehash: 1bcdb0d30bccfe628fd02861d257d79268046b77
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a><span data-ttu-id="e8d7c-102">Paralleles Anrufen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8d7c-102">Simultaneous ringing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8d7c-103">_**Letztes Änderungsdatum des Themas:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="e8d7c-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="e8d7c-104">Wenn der angerufene Teilnehmer das gleichzeitige Klingeln aktiviert hat, analysiert standortbasiertes Routing den Standort des anrufenden und die Endpunkte der angerufenen Parteien, um zu ermitteln, ob der Anruf weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e8d7c-104">When the called party has simultaneous ringing enabled, Location-Based Routing analyzes the location of the calling party and the endpoints of the called parties to determine whether the call should be routed.</span></span>

<span data-ttu-id="e8d7c-105">Die folgende Tabelle zeigt einen Benutzer, für den paralleles Anrufen konfiguriert ist, und das Ziel des parallelen Anrufs ist ein Benutzer am gleichen oder einem unbekannten Netzwerkstandort.</span><span class="sxs-lookup"><span data-stu-id="e8d7c-105">The following table illustrates a user configured with simultaneous ringing, and the simultaneous ringing target is a user in the same network site, in a different network site, or in an unknown network site.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8d7c-106">Eingehender Anruf aus dem öffentlichen Telefonnetz für</span><span class="sxs-lookup"><span data-stu-id="e8d7c-106">Incoming PSTN call for</span></span></th>
<th><span data-ttu-id="e8d7c-107">Am gleichen Netzwerkstandort wie der Angerufene</span><span class="sxs-lookup"><span data-stu-id="e8d7c-107">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="e8d7c-108">An einem anderen Netzwerkstandort als der Angerufene</span><span class="sxs-lookup"><span data-stu-id="e8d7c-108">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="e8d7c-109">Befindet sich auf der unbekannten Netzwerk Website oder ist für standortbasiertes Routing nicht aktiviert</span><span class="sxs-lookup"><span data-stu-id="e8d7c-109">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8d7c-110">Lync-Benutzer</span><span class="sxs-lookup"><span data-stu-id="e8d7c-110">Lync user</span></span></p></td>
<td><p><span data-ttu-id="e8d7c-111">Paralleles Anrufen zugelassen</span><span class="sxs-lookup"><span data-stu-id="e8d7c-111">Simultaneous ring allowed</span></span></p></td>
<td><p><span data-ttu-id="e8d7c-112">Paralleles Anrufen nicht zugelassen</span><span class="sxs-lookup"><span data-stu-id="e8d7c-112">Simultaneous ring not allowed</span></span></p></td>
<td><p><span data-ttu-id="e8d7c-113">Paralleles Anrufen nicht zugelassen</span><span class="sxs-lookup"><span data-stu-id="e8d7c-113">Simultaneous ring not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="e8d7c-114">In der folgenden Tabelle wird ein Anruf eines lync-Benutzers (also lync-Anrufers) auf derselben Netzwerk Website, in einer anderen Netzwerk Website oder auf einer unbekannten Netzwerk Website veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e8d7c-114">The following table illustrates a call from a Lync user (i.e. Lync caller) in the same network site, in a different network site, or from an unknown network site.</span></span> <span data-ttu-id="e8d7c-115">Der Angerufene hat einen Endpunkt im öffentlichen Telefonfestnetz (z. B. ein Mobiltelefon), der als Ziel für paralleles Anrufen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="e8d7c-115">The callee has a PSTN endpoint (i.e. cellphone) configured as a simultaneous ring target.</span></span> <span data-ttu-id="e8d7c-116">In diesem Szenario bestimmt standortbasiertes Routing, ob der Anruf an das Ziel für das gleichzeitige Klingeln (also das Mobiltelefon) des angerufenen weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e8d7c-116">In this scenario, Location-Based Routing will determine whether the call should be routed to the simultaneous ring target (i.e. cellphone) of the callee or not.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8d7c-117">Ziel für paralleles Anrufen</span><span class="sxs-lookup"><span data-stu-id="e8d7c-117">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="e8d7c-118">Am gleichen Netzwerkstandort wie der Angerufene</span><span class="sxs-lookup"><span data-stu-id="e8d7c-118">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="e8d7c-119">An einem anderen Netzwerkstandort als der Angerufene</span><span class="sxs-lookup"><span data-stu-id="e8d7c-119">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="e8d7c-120">Befindet sich auf der unbekannten Netzwerk Website oder ist für standortbasiertes Routing nicht aktiviert</span><span class="sxs-lookup"><span data-stu-id="e8d7c-120">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8d7c-121">Endpunkt im öffentlichen Telefonnetz</span><span class="sxs-lookup"><span data-stu-id="e8d7c-121">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="e8d7c-122">Paralleles Anrufen durch die VoIP-Weiterleitungsrichtline am Standort des Anrufers zugelassen</span><span class="sxs-lookup"><span data-stu-id="e8d7c-122">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="e8d7c-123">Paralleles Anrufen durch die VoIP-Weiterleitungsrichtline am Standort des Anrufers zugelassen</span><span class="sxs-lookup"><span data-stu-id="e8d7c-123">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="e8d7c-124">Paralleles Anrufen durch die VoIP-Weiterleitungsrichtlinie an Trunks, die nicht für standortbasiertes Routing aktiviert sind, zugelassen</span><span class="sxs-lookup"><span data-stu-id="e8d7c-124">Simultaneous ring allowed through the caller’s voice policy to trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="e8d7c-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8d7c-125">See Also</span></span>


[<span data-ttu-id="e8d7c-126">Szenarien für das standortbasierte Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8d7c-126">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

