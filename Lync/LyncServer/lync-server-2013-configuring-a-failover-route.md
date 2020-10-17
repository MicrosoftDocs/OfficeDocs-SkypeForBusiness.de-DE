---
title: 'Lync Server 2013: Konfigurieren einer Failover-Route'
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
ms.openlocfilehash: e0a3a0d3b2eb2d505ff345af66ae8ccbcc551ee8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520062"
---
# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="136bf-102">Konfigurieren einer Failover-Route in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="136bf-102">Configuring a failover route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="136bf-103">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="136bf-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="136bf-p101">Im folgenden Beispiel wird gezeigt, wie ein Administrator eine Failoverroute definieren kann, die bei geplanten Wartungsausfällen oder anderen Ausfällen des Gateways „Dallas-GW1“ verwendet wird. In den folgenden Tabellen wird die erforderliche Konfigurationsänderung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="136bf-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="136bf-p102">Tabelle 1. Benutzerrichtlinie</span><span class="sxs-lookup"><span data-stu-id="136bf-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="136bf-108">Benutzerrichtlinie</span><span class="sxs-lookup"><span data-stu-id="136bf-108">User policy</span></span></th>
<th><span data-ttu-id="136bf-109">Telefonverwendung</span><span class="sxs-lookup"><span data-stu-id="136bf-109">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="136bf-110">Standardanrufrichtlinie</span><span class="sxs-lookup"><span data-stu-id="136bf-110">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="136bf-111">Lokal</span><span class="sxs-lookup"><span data-stu-id="136bf-111">Local</span></span></p>
<p><span data-ttu-id="136bf-112">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="136bf-112">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="136bf-113">Richtlinie für Ortsgespräche am Standort Redmond</span><span class="sxs-lookup"><span data-stu-id="136bf-113">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="136bf-114">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="136bf-114">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="136bf-115">Anrufrichtlinie für Dallas</span><span class="sxs-lookup"><span data-stu-id="136bf-115">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="136bf-116">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="136bf-116">DallasUsers</span></span></p>
<p><span data-ttu-id="136bf-117">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="136bf-117">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="136bf-p103">Tabelle 2. Routen</span><span class="sxs-lookup"><span data-stu-id="136bf-p103">Table 2. Routes</span></span>

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
<th><span data-ttu-id="136bf-120">Name der Route</span><span class="sxs-lookup"><span data-stu-id="136bf-120">Route name</span></span></th>
<th><span data-ttu-id="136bf-121">Nummernmuster</span><span class="sxs-lookup"><span data-stu-id="136bf-121">Number pattern</span></span></th>
<th><span data-ttu-id="136bf-122">Telefonverwendung</span><span class="sxs-lookup"><span data-stu-id="136bf-122">Phone usage</span></span></th>
<th><span data-ttu-id="136bf-123">Stamm</span><span class="sxs-lookup"><span data-stu-id="136bf-123">Trunk</span></span></th>
<th><span data-ttu-id="136bf-124">Gateway</span><span class="sxs-lookup"><span data-stu-id="136bf-124">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="136bf-125">Route für Ortsgespräche am Standort Redmond</span><span class="sxs-lookup"><span data-stu-id="136bf-125">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="136bf-126">^\+1 (425 | 206 | 253) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="136bf-126">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="136bf-127">Lokal</span><span class="sxs-lookup"><span data-stu-id="136bf-127">Local</span></span></p>
<p><span data-ttu-id="136bf-128">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="136bf-128">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="136bf-129">Trunk1</span><span class="sxs-lookup"><span data-stu-id="136bf-129">Trunk1</span></span></p>
<p><span data-ttu-id="136bf-130">Trunk2</span><span class="sxs-lookup"><span data-stu-id="136bf-130">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="136bf-131">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="136bf-131">Red-GW1</span></span></p>
<p><span data-ttu-id="136bf-132">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="136bf-132">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="136bf-133">Route für Ortsgespräche am Standort Dallas</span><span class="sxs-lookup"><span data-stu-id="136bf-133">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="136bf-134">^\+1 (972 | 214 | 469) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="136bf-134">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="136bf-135">Lokal</span><span class="sxs-lookup"><span data-stu-id="136bf-135">Local</span></span></p></td>
<td><p><span data-ttu-id="136bf-136">Trunk3</span><span class="sxs-lookup"><span data-stu-id="136bf-136">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="136bf-137">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="136bf-137">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="136bf-138">Universalroute</span><span class="sxs-lookup"><span data-stu-id="136bf-138">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="136bf-139">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="136bf-139">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="136bf-140">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="136bf-140">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="136bf-141">Trunk1</span><span class="sxs-lookup"><span data-stu-id="136bf-141">Trunk1</span></span></p>
<p><span data-ttu-id="136bf-142">Trunk2</span><span class="sxs-lookup"><span data-stu-id="136bf-142">Trunk2</span></span></p>
<p><span data-ttu-id="136bf-143">Trunk3</span><span class="sxs-lookup"><span data-stu-id="136bf-143">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="136bf-144">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="136bf-144">Red-GW1</span></span></p>
<p><span data-ttu-id="136bf-145">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="136bf-145">Red-GW2</span></span></p>
<p><span data-ttu-id="136bf-146">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="136bf-146">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="136bf-147">Route für Benutzer in Dallas</span><span class="sxs-lookup"><span data-stu-id="136bf-147">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="136bf-148">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="136bf-148">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="136bf-149">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="136bf-149">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="136bf-150">Trunk3</span><span class="sxs-lookup"><span data-stu-id="136bf-150">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="136bf-151">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="136bf-151">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="136bf-p104">In Tabelle 1 wird die Telefonverwendung „GlobalPSTNHopoff“ nach der Telefonverwendung „DallasUsers“ zur Anrufrichtlinie für Dallas hinzugefügt. Daher können für Anrufe, für die die Anrufrichtlinie für Dallas gilt, Routen verwendet werden, die für „GlobalPSTNHopoff“ konfiguriert sind, wenn eine Route für die Telefonverwendung „DallasUsers“ nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="136bf-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

