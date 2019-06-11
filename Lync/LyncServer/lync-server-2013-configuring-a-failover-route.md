---
title: 'Lync Server 2013: Konfigurieren einer Failoverroute'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e65070326c82e3a30977b3512bd2785d6bb4bd2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="44cd1-102">Konfigurieren einer Failoverroute in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44cd1-102">Configuring a failover route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44cd1-103">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="44cd1-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="44cd1-104">Im folgenden Beispiel wird gezeigt, wie ein Administrator eine Failover-Route für die Verwendung definieren kann, wenn der Dallas-GW1 für die Wartung ausgefallen ist oder anderweitig nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="44cd1-104">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable.</span></span> <span data-ttu-id="44cd1-105">Die folgenden Tabellen veranschaulichen die erforderliche Konfigurationsänderung.</span><span class="sxs-lookup"><span data-stu-id="44cd1-105">The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="44cd1-106">Tabelle 1</span><span class="sxs-lookup"><span data-stu-id="44cd1-106">Table 1.</span></span> <span data-ttu-id="44cd1-107">Benutzerrichtlinien</span><span class="sxs-lookup"><span data-stu-id="44cd1-107">User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44cd1-108">Benutzerrichtlinie</span><span class="sxs-lookup"><span data-stu-id="44cd1-108">User policy</span></span></th>
<th><span data-ttu-id="44cd1-109">Telefonnutzung</span><span class="sxs-lookup"><span data-stu-id="44cd1-109">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44cd1-110">Standardanrufrichtlinie</span><span class="sxs-lookup"><span data-stu-id="44cd1-110">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="44cd1-111">Local</span><span class="sxs-lookup"><span data-stu-id="44cd1-111">Local</span></span></p>
<p><span data-ttu-id="44cd1-112">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="44cd1-112">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44cd1-113">Lokale Redmond-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="44cd1-113">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="44cd1-114">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="44cd1-114">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44cd1-115">Dallas-Anrufrichtlinie</span><span class="sxs-lookup"><span data-stu-id="44cd1-115">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="44cd1-116">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="44cd1-116">DallasUsers</span></span></p>
<p><span data-ttu-id="44cd1-117">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="44cd1-117">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="44cd1-118">Tabelle 2.</span><span class="sxs-lookup"><span data-stu-id="44cd1-118">Table 2.</span></span> <span data-ttu-id="44cd1-119">Routen</span><span class="sxs-lookup"><span data-stu-id="44cd1-119">Routes</span></span>

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
<th><span data-ttu-id="44cd1-120">Routenname</span><span class="sxs-lookup"><span data-stu-id="44cd1-120">Route name</span></span></th>
<th><span data-ttu-id="44cd1-121">Nummernmuster</span><span class="sxs-lookup"><span data-stu-id="44cd1-121">Number pattern</span></span></th>
<th><span data-ttu-id="44cd1-122">Telefonnutzung</span><span class="sxs-lookup"><span data-stu-id="44cd1-122">Phone usage</span></span></th>
<th><span data-ttu-id="44cd1-123">Stamm</span><span class="sxs-lookup"><span data-stu-id="44cd1-123">Trunk</span></span></th>
<th><span data-ttu-id="44cd1-124">Gateway</span><span class="sxs-lookup"><span data-stu-id="44cd1-124">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44cd1-125">Lokale Redmond-Route</span><span class="sxs-lookup"><span data-stu-id="44cd1-125">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="44cd1-126">^\+1 (425 | 206 | 253) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="44cd1-126">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="44cd1-127">Local</span><span class="sxs-lookup"><span data-stu-id="44cd1-127">Local</span></span></p>
<p><span data-ttu-id="44cd1-128">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="44cd1-128">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="44cd1-129">Trunk1</span><span class="sxs-lookup"><span data-stu-id="44cd1-129">Trunk1</span></span></p>
<p><span data-ttu-id="44cd1-130">Trunk2</span><span class="sxs-lookup"><span data-stu-id="44cd1-130">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="44cd1-131">Rot-GW1</span><span class="sxs-lookup"><span data-stu-id="44cd1-131">Red-GW1</span></span></p>
<p><span data-ttu-id="44cd1-132">Rot-GW2</span><span class="sxs-lookup"><span data-stu-id="44cd1-132">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44cd1-133">Lokale Route für Dallas</span><span class="sxs-lookup"><span data-stu-id="44cd1-133">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="44cd1-134">^\+1 (972 | 214 | 469) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="44cd1-134">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="44cd1-135">Local</span><span class="sxs-lookup"><span data-stu-id="44cd1-135">Local</span></span></p></td>
<td><p><span data-ttu-id="44cd1-136">Trunk3</span><span class="sxs-lookup"><span data-stu-id="44cd1-136">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="44cd1-137">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="44cd1-137">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44cd1-138">Universelle Route</span><span class="sxs-lookup"><span data-stu-id="44cd1-138">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="44cd1-139">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="44cd1-139">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="44cd1-140">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="44cd1-140">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="44cd1-141">Trunk1</span><span class="sxs-lookup"><span data-stu-id="44cd1-141">Trunk1</span></span></p>
<p><span data-ttu-id="44cd1-142">Trunk2</span><span class="sxs-lookup"><span data-stu-id="44cd1-142">Trunk2</span></span></p>
<p><span data-ttu-id="44cd1-143">Trunk3</span><span class="sxs-lookup"><span data-stu-id="44cd1-143">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="44cd1-144">Rot-GW1</span><span class="sxs-lookup"><span data-stu-id="44cd1-144">Red-GW1</span></span></p>
<p><span data-ttu-id="44cd1-145">Rot-GW2</span><span class="sxs-lookup"><span data-stu-id="44cd1-145">Red-GW2</span></span></p>
<p><span data-ttu-id="44cd1-146">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="44cd1-146">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44cd1-147">Route für Dallas-Benutzer</span><span class="sxs-lookup"><span data-stu-id="44cd1-147">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="44cd1-148">^\+? (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="44cd1-148">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="44cd1-149">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="44cd1-149">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="44cd1-150">Trunk3</span><span class="sxs-lookup"><span data-stu-id="44cd1-150">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="44cd1-151">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="44cd1-151">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="44cd1-152">In Tabelle 1 wird nach der DallasUsers-Telefonnutzung in der Dallas-Anrufrichtlinie eine Telefonverwendung von GlobalPSTNHopoff hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="44cd1-152">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy.</span></span> <span data-ttu-id="44cd1-153">Dies ermöglicht es anrufen mit der Dallas-Anrufrichtlinie, Routen zu verwenden, die für die GlobalPSTNHopoff-Telefonverwendung konfiguriert sind, wenn eine Route für die DallasUsers-Telefonnutzung nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="44cd1-153">This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

