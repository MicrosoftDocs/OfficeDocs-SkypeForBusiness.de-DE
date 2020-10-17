---
title: 'Lync Server 2013: Konfigurieren einer Failover-Route'
description: 'Lync Server 2013: Konfigurieren einer Failover-Route.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7cfc45276931685a2d42103b1b7f1d5015dcd7e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560491"
---
# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="0a574-103">Konfigurieren einer Failover-Route in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a574-103">Configuring a failover route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a574-104">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="0a574-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="0a574-p101">Im folgenden Beispiel wird gezeigt, wie ein Administrator eine Failoverroute definieren kann, die bei geplanten Wartungsausfällen oder anderen Ausfällen des Gateways „Dallas-GW1“ verwendet wird. In den folgenden Tabellen wird die erforderliche Konfigurationsänderung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0a574-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="0a574-p102">Tabelle 1. Benutzerrichtlinie</span><span class="sxs-lookup"><span data-stu-id="0a574-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0a574-109">Benutzerrichtlinie</span><span class="sxs-lookup"><span data-stu-id="0a574-109">User policy</span></span></th>
<th><span data-ttu-id="0a574-110">Telefonverwendung</span><span class="sxs-lookup"><span data-stu-id="0a574-110">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a574-111">Standardanrufrichtlinie</span><span class="sxs-lookup"><span data-stu-id="0a574-111">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="0a574-112">Lokal</span><span class="sxs-lookup"><span data-stu-id="0a574-112">Local</span></span></p>
<p><span data-ttu-id="0a574-113">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="0a574-113">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a574-114">Richtlinie für Ortsgespräche am Standort Redmond</span><span class="sxs-lookup"><span data-stu-id="0a574-114">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="0a574-115">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="0a574-115">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a574-116">Anrufrichtlinie für Dallas</span><span class="sxs-lookup"><span data-stu-id="0a574-116">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="0a574-117">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="0a574-117">DallasUsers</span></span></p>
<p><span data-ttu-id="0a574-118">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="0a574-118">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="0a574-p103">Tabelle 2. Routen</span><span class="sxs-lookup"><span data-stu-id="0a574-p103">Table 2. Routes</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0a574-121">Name der Route</span><span class="sxs-lookup"><span data-stu-id="0a574-121">Route name</span></span></th>
<th><span data-ttu-id="0a574-122">Nummernmuster</span><span class="sxs-lookup"><span data-stu-id="0a574-122">Number pattern</span></span></th>
<th><span data-ttu-id="0a574-123">Telefonverwendung</span><span class="sxs-lookup"><span data-stu-id="0a574-123">Phone usage</span></span></th>
<th><span data-ttu-id="0a574-124">Stamm</span><span class="sxs-lookup"><span data-stu-id="0a574-124">Trunk</span></span></th>
<th><span data-ttu-id="0a574-125">Gateway</span><span class="sxs-lookup"><span data-stu-id="0a574-125">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a574-126">Route für Ortsgespräche am Standort Redmond</span><span class="sxs-lookup"><span data-stu-id="0a574-126">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="0a574-127">^\+1 (425 | 206 | 253) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="0a574-127">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="0a574-128">Lokal</span><span class="sxs-lookup"><span data-stu-id="0a574-128">Local</span></span></p>
<p><span data-ttu-id="0a574-129">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="0a574-129">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="0a574-130">Trunk1</span><span class="sxs-lookup"><span data-stu-id="0a574-130">Trunk1</span></span></p>
<p><span data-ttu-id="0a574-131">Trunk2</span><span class="sxs-lookup"><span data-stu-id="0a574-131">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="0a574-132">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="0a574-132">Red-GW1</span></span></p>
<p><span data-ttu-id="0a574-133">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="0a574-133">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a574-134">Route für Ortsgespräche am Standort Dallas</span><span class="sxs-lookup"><span data-stu-id="0a574-134">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="0a574-135">^\+1 (972 | 214 | 469) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="0a574-135">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="0a574-136">Lokal</span><span class="sxs-lookup"><span data-stu-id="0a574-136">Local</span></span></p></td>
<td><p><span data-ttu-id="0a574-137">Trunk3</span><span class="sxs-lookup"><span data-stu-id="0a574-137">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="0a574-138">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="0a574-138">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a574-139">Universalroute</span><span class="sxs-lookup"><span data-stu-id="0a574-139">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="0a574-140">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="0a574-140">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="0a574-141">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="0a574-141">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="0a574-142">Trunk1</span><span class="sxs-lookup"><span data-stu-id="0a574-142">Trunk1</span></span></p>
<p><span data-ttu-id="0a574-143">Trunk2</span><span class="sxs-lookup"><span data-stu-id="0a574-143">Trunk2</span></span></p>
<p><span data-ttu-id="0a574-144">Trunk3</span><span class="sxs-lookup"><span data-stu-id="0a574-144">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="0a574-145">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="0a574-145">Red-GW1</span></span></p>
<p><span data-ttu-id="0a574-146">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="0a574-146">Red-GW2</span></span></p>
<p><span data-ttu-id="0a574-147">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="0a574-147">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a574-148">Route für Benutzer in Dallas</span><span class="sxs-lookup"><span data-stu-id="0a574-148">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="0a574-149">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="0a574-149">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="0a574-150">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="0a574-150">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="0a574-151">Trunk3</span><span class="sxs-lookup"><span data-stu-id="0a574-151">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="0a574-152">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="0a574-152">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0a574-p104">In Tabelle 1 wird die Telefonverwendung „GlobalPSTNHopoff“ nach der Telefonverwendung „DallasUsers“ zur Anrufrichtlinie für Dallas hinzugefügt. Daher können für Anrufe, für die die Anrufrichtlinie für Dallas gilt, Routen verwendet werden, die für „GlobalPSTNHopoff“ konfiguriert sind, wenn eine Route für die Telefonverwendung „DallasUsers“ nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="0a574-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

