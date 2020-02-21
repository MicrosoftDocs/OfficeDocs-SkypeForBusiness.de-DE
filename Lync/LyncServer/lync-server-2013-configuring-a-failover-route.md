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
ms.openlocfilehash: 50917bffe3c6294b554edc7f9c3f620721e04737
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="0b5a1-102">Konfigurieren einer Failover-Route in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b5a1-102">Configuring a failover route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b5a1-103">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="0b5a1-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="0b5a1-p101">Im folgenden Beispiel wird gezeigt, wie ein Administrator eine Failoverroute definieren kann, die bei geplanten Wartungsausfällen oder anderen Ausfällen des Gateways „Dallas-GW1“ verwendet wird. In den folgenden Tabellen wird die erforderliche Konfigurationsänderung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0b5a1-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="0b5a1-p102">Tabelle 1. Benutzerrichtlinie</span><span class="sxs-lookup"><span data-stu-id="0b5a1-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b5a1-108">Benutzerrichtlinie</span><span class="sxs-lookup"><span data-stu-id="0b5a1-108">User policy</span></span></th>
<th><span data-ttu-id="0b5a1-109">Telefonverwendung</span><span class="sxs-lookup"><span data-stu-id="0b5a1-109">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b5a1-110">Standardanrufrichtlinie</span><span class="sxs-lookup"><span data-stu-id="0b5a1-110">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="0b5a1-111">Local</span><span class="sxs-lookup"><span data-stu-id="0b5a1-111">Local</span></span></p>
<p><span data-ttu-id="0b5a1-112">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="0b5a1-112">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b5a1-113">Richtlinie für Ortsgespräche am Standort Redmond</span><span class="sxs-lookup"><span data-stu-id="0b5a1-113">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="0b5a1-114">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="0b5a1-114">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b5a1-115">Anrufrichtlinie für Dallas</span><span class="sxs-lookup"><span data-stu-id="0b5a1-115">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="0b5a1-116">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="0b5a1-116">DallasUsers</span></span></p>
<p><span data-ttu-id="0b5a1-117">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="0b5a1-117">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="0b5a1-p103">Tabelle 2. Routen</span><span class="sxs-lookup"><span data-stu-id="0b5a1-p103">Table 2. Routes</span></span>

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
<th><span data-ttu-id="0b5a1-120">Name der Route</span><span class="sxs-lookup"><span data-stu-id="0b5a1-120">Route name</span></span></th>
<th><span data-ttu-id="0b5a1-121">Nummernmuster</span><span class="sxs-lookup"><span data-stu-id="0b5a1-121">Number pattern</span></span></th>
<th><span data-ttu-id="0b5a1-122">Telefonverwendung</span><span class="sxs-lookup"><span data-stu-id="0b5a1-122">Phone usage</span></span></th>
<th><span data-ttu-id="0b5a1-123">Stamm</span><span class="sxs-lookup"><span data-stu-id="0b5a1-123">Trunk</span></span></th>
<th><span data-ttu-id="0b5a1-124">Gateway</span><span class="sxs-lookup"><span data-stu-id="0b5a1-124">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b5a1-125">Route für Ortsgespräche am Standort Redmond</span><span class="sxs-lookup"><span data-stu-id="0b5a1-125">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="0b5a1-126">^\+1 (425 | 206 | 253) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="0b5a1-126">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="0b5a1-127">Local</span><span class="sxs-lookup"><span data-stu-id="0b5a1-127">Local</span></span></p>
<p><span data-ttu-id="0b5a1-128">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="0b5a1-128">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="0b5a1-129">Trunk1</span><span class="sxs-lookup"><span data-stu-id="0b5a1-129">Trunk1</span></span></p>
<p><span data-ttu-id="0b5a1-130">Trunk2</span><span class="sxs-lookup"><span data-stu-id="0b5a1-130">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="0b5a1-131">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="0b5a1-131">Red-GW1</span></span></p>
<p><span data-ttu-id="0b5a1-132">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="0b5a1-132">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b5a1-133">Route für Ortsgespräche am Standort Dallas</span><span class="sxs-lookup"><span data-stu-id="0b5a1-133">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="0b5a1-134">^\+1 (972 | 214 | 469) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="0b5a1-134">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="0b5a1-135">Local</span><span class="sxs-lookup"><span data-stu-id="0b5a1-135">Local</span></span></p></td>
<td><p><span data-ttu-id="0b5a1-136">Trunk3</span><span class="sxs-lookup"><span data-stu-id="0b5a1-136">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="0b5a1-137">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="0b5a1-137">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b5a1-138">Universalroute</span><span class="sxs-lookup"><span data-stu-id="0b5a1-138">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="0b5a1-139">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="0b5a1-139">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="0b5a1-140">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="0b5a1-140">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="0b5a1-141">Trunk1</span><span class="sxs-lookup"><span data-stu-id="0b5a1-141">Trunk1</span></span></p>
<p><span data-ttu-id="0b5a1-142">Trunk2</span><span class="sxs-lookup"><span data-stu-id="0b5a1-142">Trunk2</span></span></p>
<p><span data-ttu-id="0b5a1-143">Trunk3</span><span class="sxs-lookup"><span data-stu-id="0b5a1-143">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="0b5a1-144">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="0b5a1-144">Red-GW1</span></span></p>
<p><span data-ttu-id="0b5a1-145">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="0b5a1-145">Red-GW2</span></span></p>
<p><span data-ttu-id="0b5a1-146">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="0b5a1-146">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b5a1-147">Route für Benutzer in Dallas</span><span class="sxs-lookup"><span data-stu-id="0b5a1-147">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="0b5a1-148">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="0b5a1-148">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="0b5a1-149">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="0b5a1-149">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="0b5a1-150">Trunk3</span><span class="sxs-lookup"><span data-stu-id="0b5a1-150">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="0b5a1-151">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="0b5a1-151">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0b5a1-p104">In Tabelle 1 wird die Telefonverwendung „GlobalPSTNHopoff“ nach der Telefonverwendung „DallasUsers“ zur Anrufrichtlinie für Dallas hinzugefügt. Daher können für Anrufe, für die die Anrufrichtlinie für Dallas gilt, Routen verwendet werden, die für „GlobalPSTNHopoff“ konfiguriert sind, wenn eine Route für die Telefonverwendung „DallasUsers“ nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="0b5a1-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

