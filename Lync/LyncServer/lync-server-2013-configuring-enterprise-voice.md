---
title: 'Lync Server 2013: Konfigurieren von Enterprise-VoIP'
description: 'Lync Server 2013: Konfigurieren von Enterprise-VoIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49a231b92bf7b04aa3466927a79258f0cbad4e3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548431"
---
# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="cc793-103">Konfigurieren von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc793-103">Configuring Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc793-104">_**Letztes Änderungsstand des Themas:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="cc793-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="cc793-105">Um Enterprise-VoIP bereitzustellen, müssen Sie Folgendes konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="cc793-105">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="cc793-106">Erstellen eines Trunks</span><span class="sxs-lookup"><span data-stu-id="cc793-106">Create a Trunk</span></span>

  - <span data-ttu-id="cc793-107">Definieren einer VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="cc793-107">Define a Voice Policy</span></span>

  - <span data-ttu-id="cc793-108">Definieren einer VoIP-Route</span><span class="sxs-lookup"><span data-stu-id="cc793-108">Define a Voice Route</span></span>

  - <span data-ttu-id="cc793-109">Aktivieren von Benutzern für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="cc793-109">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="cc793-110">Erstellen eines Trunks</span><span class="sxs-lookup"><span data-stu-id="cc793-110">Create a Trunk</span></span>

<span data-ttu-id="cc793-111">Sie müssen Trunks in Ihrer Enterprise-VoIP-Bereitstellung definieren.</span><span class="sxs-lookup"><span data-stu-id="cc793-111">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="cc793-112">Für Location-Based Routing müssen Sie eine trunkkonfiguration pro trunk erstellen.</span><span class="sxs-lookup"><span data-stu-id="cc793-112">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="cc793-113">Verwenden Sie den lync Server Topologie-Generator, um Ihre Trunks zu definieren, und verwenden Sie den lync Server Windows PowerShell-Befehl, New-CsTrunkConfiguration oder den lync Server-Systemsteuerung, um die entsprechenden Trunk Konfigurationen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="cc793-113">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="cc793-114">Weitere Informationen zum Aktivieren des Location-Based Routings auf Trunk Konfigurationen finden Sie im Abschnitt enable Location-Based Routing to Trunks, in dem Thema Aktivieren von [Location-Based Routing in lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="cc793-114">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="cc793-115">In diesem Beispiel werden in der folgenden Tabelle die Trunks dargestellt, die in diesem Szenario verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cc793-115">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="cc793-116">Weitere Informationen finden Sie unter [Definieren zusätzlicher Trunks im Topologie-Generator in lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="cc793-116">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


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
<th><span data-ttu-id="cc793-117">Trunk Name</span><span class="sxs-lookup"><span data-stu-id="cc793-117">Trunk name</span></span></th>
<th><span data-ttu-id="cc793-118">Systemtyp</span><span class="sxs-lookup"><span data-stu-id="cc793-118">System type</span></span></th>
<th><span data-ttu-id="cc793-119">Name</span><span class="sxs-lookup"><span data-stu-id="cc793-119">Name</span></span></th>
<th><span data-ttu-id="cc793-120">Standort</span><span class="sxs-lookup"><span data-stu-id="cc793-120">Location</span></span></th>
<th><span data-ttu-id="cc793-121">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="cc793-121">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc793-122">Trunk 1 del-GW</span><span class="sxs-lookup"><span data-stu-id="cc793-122">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="cc793-123">PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="cc793-123">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="cc793-124">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="cc793-124">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="cc793-125">Delhi</span><span class="sxs-lookup"><span data-stu-id="cc793-125">Delhi</span></span></p></td>
<td><p><span data-ttu-id="cc793-126">MS1</span><span class="sxs-lookup"><span data-stu-id="cc793-126">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc793-127">Trunk 2 Hyd-GW</span><span class="sxs-lookup"><span data-stu-id="cc793-127">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="cc793-128">PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="cc793-128">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="cc793-129">Hyd-GW</span><span class="sxs-lookup"><span data-stu-id="cc793-129">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="cc793-130">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="cc793-130">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="cc793-131">MS1</span><span class="sxs-lookup"><span data-stu-id="cc793-131">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc793-132">Trunk 3 del-Nebenstellenanlage</span><span class="sxs-lookup"><span data-stu-id="cc793-132">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="cc793-133">PBX</span><span class="sxs-lookup"><span data-stu-id="cc793-133">PBX</span></span></p></td>
<td><p><span data-ttu-id="cc793-134">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="cc793-134">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="cc793-135">Delhi</span><span class="sxs-lookup"><span data-stu-id="cc793-135">Delhi</span></span></p></td>
<td><p><span data-ttu-id="cc793-136">MS1</span><span class="sxs-lookup"><span data-stu-id="cc793-136">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc793-137">Trunk 4 Hyd-Nebenstellenanlage</span><span class="sxs-lookup"><span data-stu-id="cc793-137">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="cc793-138">PBX</span><span class="sxs-lookup"><span data-stu-id="cc793-138">PBX</span></span></p></td>
<td><p><span data-ttu-id="cc793-139">Hyd-PBX</span><span class="sxs-lookup"><span data-stu-id="cc793-139">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="cc793-140">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="cc793-140">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="cc793-141">MS1</span><span class="sxs-lookup"><span data-stu-id="cc793-141">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="cc793-142">Definiert VoIP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="cc793-142">Defines Voice Policies</span></span>

<span data-ttu-id="cc793-143">Sie müssen VoIP-Richtlinien für Ihre Enterprise-VoIP-Bereitstellung definieren.</span><span class="sxs-lookup"><span data-stu-id="cc793-143">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="cc793-144">Definieren Sie eine VoIP-Richtlinie, um Location-Based Routing Einschränkungen für eine Teilmenge von Benutzern zu erzwingen, wenn nur eine Teilmenge von Ihnen für die Verwendung Location-Based Routings erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="cc793-144">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="cc793-145">In diesem Beispiel werden in der folgenden Tabelle die in diesem Szenario verwendeten VoIP-Richtlinien erläutert.</span><span class="sxs-lookup"><span data-stu-id="cc793-145">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="cc793-146">Zur Veranschaulichung werden nur Einstellungen, die für Location-Based Routing spezifisch sind, in die Tabelle einbezogen.</span><span class="sxs-lookup"><span data-stu-id="cc793-146">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="cc793-147">Weitere Informationen finden Sie unter [Konfigurieren von VoIP-Richtlinien und PSTN-Verwendungsdatensätzen zum Autorisieren von Anruffunktionen und-Berechtigungen in lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="cc793-147">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="cc793-148">VoIP-Richtlinie 1</span><span class="sxs-lookup"><span data-stu-id="cc793-148">Voice policy 1</span></span></th>
<th><span data-ttu-id="cc793-149">VoIP-Richtlinie 2</span><span class="sxs-lookup"><span data-stu-id="cc793-149">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc793-150">VoIP-Richtlinien-ID</span><span class="sxs-lookup"><span data-stu-id="cc793-150">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="cc793-151">VoIP-Richtlinie für Delhi</span><span class="sxs-lookup"><span data-stu-id="cc793-151">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="cc793-152">Hyderabad-VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="cc793-152">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc793-153">PSTN-Verwendungen</span><span class="sxs-lookup"><span data-stu-id="cc793-153">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="cc793-154">Verwendung von Delhi, PBX del Usage, PBX Hyd</span><span class="sxs-lookup"><span data-stu-id="cc793-154">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="cc793-155">Verwendung von Hyderabad, Nebenstellenanlagen Hyd, PBX del Usage</span><span class="sxs-lookup"><span data-stu-id="cc793-155">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc793-156">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="cc793-156">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="cc793-157">False</span><span class="sxs-lookup"><span data-stu-id="cc793-157">False</span></span></p></td>
<td><p><span data-ttu-id="cc793-158">False</span><span class="sxs-lookup"><span data-stu-id="cc793-158">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="cc793-159">Definieren von VoIP-Routen</span><span class="sxs-lookup"><span data-stu-id="cc793-159">Define Voice Routes</span></span>

<span data-ttu-id="cc793-160">Sie müssen VoIP-Routen für Ihre Enterprise-VoIP-Bereitstellung definieren.</span><span class="sxs-lookup"><span data-stu-id="cc793-160">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="cc793-161">In diesem Beispiel werden in der folgenden Tabelle die in diesem Szenario verwendeten VoIP-Routen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cc793-161">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="cc793-162">Zur Veranschaulichung werden nur Einstellungen, die für Location-Based Routing spezifisch sind, in die Tabelle einbezogen.</span><span class="sxs-lookup"><span data-stu-id="cc793-162">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="cc793-163">Weitere Informationen finden Sie unter [Konfigurieren von VoIP-Routen für ausgehende Anrufe in lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="cc793-163">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


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
<th></th>
<th><span data-ttu-id="cc793-164">VoIP-Route 1</span><span class="sxs-lookup"><span data-stu-id="cc793-164">Voice route 1</span></span></th>
<th><span data-ttu-id="cc793-165">VoIP-Route 2</span><span class="sxs-lookup"><span data-stu-id="cc793-165">Voice route 2</span></span></th>
<th><span data-ttu-id="cc793-166">VoIP-Route 3</span><span class="sxs-lookup"><span data-stu-id="cc793-166">Voice route 3</span></span></th>
<th><span data-ttu-id="cc793-167">VoIP-Route 4</span><span class="sxs-lookup"><span data-stu-id="cc793-167">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc793-168">Name</span><span class="sxs-lookup"><span data-stu-id="cc793-168">Name</span></span></p></td>
<td><p><span data-ttu-id="cc793-169">Delhi-Route</span><span class="sxs-lookup"><span data-stu-id="cc793-169">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="cc793-170">Hyderabad-Route</span><span class="sxs-lookup"><span data-stu-id="cc793-170">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="cc793-171">Nebenstellenanlage del Route</span><span class="sxs-lookup"><span data-stu-id="cc793-171">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="cc793-172">PBX-Hyd-Route</span><span class="sxs-lookup"><span data-stu-id="cc793-172">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc793-173">PSTN-Verwendungen</span><span class="sxs-lookup"><span data-stu-id="cc793-173">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="cc793-174">Delhi-Nutzung</span><span class="sxs-lookup"><span data-stu-id="cc793-174">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="cc793-175">Hyderabad-Nutzung</span><span class="sxs-lookup"><span data-stu-id="cc793-175">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="cc793-176">PBX del-Nutzung</span><span class="sxs-lookup"><span data-stu-id="cc793-176">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="cc793-177">PBX-Hyd-Verwendung</span><span class="sxs-lookup"><span data-stu-id="cc793-177">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc793-178">Stamm</span><span class="sxs-lookup"><span data-stu-id="cc793-178">Trunk</span></span></p></td>
<td><p><span data-ttu-id="cc793-179">Trunk 1 del-GW</span><span class="sxs-lookup"><span data-stu-id="cc793-179">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="cc793-180">Trunk 2 Hyd-GW</span><span class="sxs-lookup"><span data-stu-id="cc793-180">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="cc793-181">Trunk 3 del-Nebenstellenanlage</span><span class="sxs-lookup"><span data-stu-id="cc793-181">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="cc793-182">Trunk 4 Hyd-Nebenstellenanlage</span><span class="sxs-lookup"><span data-stu-id="cc793-182">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="cc793-183">Aktivieren von Benutzern für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="cc793-183">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="cc793-184">Aktivieren Sie Benutzer für Enterprise-VoIP, und weisen Sie Ihnen eine VoIP-Richtlinie zu, die Sie zuvor definiert haben.</span><span class="sxs-lookup"><span data-stu-id="cc793-184">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="cc793-185">In diesem Beispiel wird in der folgenden Tabelle die in diesem Szenario verwendete Zuweisung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cc793-185">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="cc793-186">Zur Veranschaulichung werden nur Einstellungen, die für Location-Based Routing spezifisch sind, in die Tabelle einbezogen.</span><span class="sxs-lookup"><span data-stu-id="cc793-186">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="cc793-187">Weitere Informationen finden Sie unter [Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="cc793-187">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="cc793-188">Benutzer, die sich in Delhi befinden</span><span class="sxs-lookup"><span data-stu-id="cc793-188">Users located in Delhi</span></span></th>
<th><span data-ttu-id="cc793-189">Benutzer, die sich in Hyderabad befinden</span><span class="sxs-lookup"><span data-stu-id="cc793-189">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc793-190">Zugeordnete VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="cc793-190">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="cc793-191">VoIP-Richtlinie für Delhi</span><span class="sxs-lookup"><span data-stu-id="cc793-191">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="cc793-192">Hyderabad-VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="cc793-192">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc793-193">Beispiel Benutzer</span><span class="sxs-lookup"><span data-stu-id="cc793-193">Sample users</span></span></p></td>
<td><p><span data-ttu-id="cc793-194">Del-lync-1, del-lync-2, del-lync-3</span><span class="sxs-lookup"><span data-stu-id="cc793-194">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="cc793-195">Hyd-lync-1, Hyd-lync-2, Hyd-lync-3</span><span class="sxs-lookup"><span data-stu-id="cc793-195">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cc793-196">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc793-196">See Also</span></span>


[<span data-ttu-id="cc793-197">Konfigurieren Location-Based Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc793-197">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

