---
title: 'Lync Server 2013: Konfigurieren von Enterprise-VoIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e46bd64efd8aa2eb6e1aead17083aa8593c8544
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="937c1-102">Konfigurieren von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="937c1-102">Configuring Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="937c1-103">_**Letztes Änderungsdatum des Themas:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="937c1-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="937c1-104">Zur Bereitstellung von Enterprise-VoIP müssen Sie Folgendes konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="937c1-104">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="937c1-105">Erstellen eines Stamms</span><span class="sxs-lookup"><span data-stu-id="937c1-105">Create a Trunk</span></span>

  - <span data-ttu-id="937c1-106">Definieren einer VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="937c1-106">Define a Voice Policy</span></span>

  - <span data-ttu-id="937c1-107">Definieren einer VoIP-Route</span><span class="sxs-lookup"><span data-stu-id="937c1-107">Define a Voice Route</span></span>

  - <span data-ttu-id="937c1-108">Enable Users for Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="937c1-108">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="937c1-109">Erstellen eines Stamms</span><span class="sxs-lookup"><span data-stu-id="937c1-109">Create a Trunk</span></span>

<span data-ttu-id="937c1-110">Sie müssen Trunks in Ihrer Enterprise-VoIP-Bereitstellung definieren.</span><span class="sxs-lookup"><span data-stu-id="937c1-110">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="937c1-111">Für standortbasiertes Routing müssen Sie eine trunk-Konfiguration pro trunk erstellen.</span><span class="sxs-lookup"><span data-stu-id="937c1-111">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="937c1-112">Verwenden Sie den lync Server Topology Builder, um Ihre Trunks zu definieren, und verwenden Sie den lync Server Windows PowerShell-Befehl, New-CsTrunkConfiguration oder die lync Server-Systemsteuerung, um die entsprechenden Trunk-Konfigurationen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="937c1-112">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="937c1-113">Weitere Informationen zum Aktivieren von Standort basiertem Routing auf Trunk-Konfigurationen finden Sie im Abschnitt Aktivieren des standortbasierten Routings für Trunks im Thema Aktivieren des [standortbasierten Routings in lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="937c1-113">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="937c1-114">In diesem Beispiel werden in der folgenden Tabelle die in diesem Szenario verwendeten Trunks veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="937c1-114">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="937c1-115">Weitere Informationen finden Sie unter [Definieren zusätzlicher Trunks im Topologie-Generator in lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="937c1-115">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


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
<th><span data-ttu-id="937c1-116">Trunk-Name</span><span class="sxs-lookup"><span data-stu-id="937c1-116">Trunk name</span></span></th>
<th><span data-ttu-id="937c1-117">Systemtyp</span><span class="sxs-lookup"><span data-stu-id="937c1-117">System type</span></span></th>
<th><span data-ttu-id="937c1-118">Name</span><span class="sxs-lookup"><span data-stu-id="937c1-118">Name</span></span></th>
<th><span data-ttu-id="937c1-119">Ort</span><span class="sxs-lookup"><span data-stu-id="937c1-119">Location</span></span></th>
<th><span data-ttu-id="937c1-120">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="937c1-120">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="937c1-121">Trunk 1 del-GW</span><span class="sxs-lookup"><span data-stu-id="937c1-121">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="937c1-122">PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="937c1-122">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="937c1-123">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="937c1-123">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="937c1-124">Delhi</span><span class="sxs-lookup"><span data-stu-id="937c1-124">Delhi</span></span></p></td>
<td><p><span data-ttu-id="937c1-125">MS1</span><span class="sxs-lookup"><span data-stu-id="937c1-125">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="937c1-126">Trunk 2 Hyd-GW</span><span class="sxs-lookup"><span data-stu-id="937c1-126">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="937c1-127">PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="937c1-127">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="937c1-128">Hyd-GW</span><span class="sxs-lookup"><span data-stu-id="937c1-128">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="937c1-129">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="937c1-129">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="937c1-130">MS1</span><span class="sxs-lookup"><span data-stu-id="937c1-130">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="937c1-131">Trunk 3 del-PBX</span><span class="sxs-lookup"><span data-stu-id="937c1-131">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="937c1-132">PBX</span><span class="sxs-lookup"><span data-stu-id="937c1-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="937c1-133">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="937c1-133">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="937c1-134">Delhi</span><span class="sxs-lookup"><span data-stu-id="937c1-134">Delhi</span></span></p></td>
<td><p><span data-ttu-id="937c1-135">MS1</span><span class="sxs-lookup"><span data-stu-id="937c1-135">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="937c1-136">Trunk 4 Hyd-PBX</span><span class="sxs-lookup"><span data-stu-id="937c1-136">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="937c1-137">PBX</span><span class="sxs-lookup"><span data-stu-id="937c1-137">PBX</span></span></p></td>
<td><p><span data-ttu-id="937c1-138">Hyd-PBX</span><span class="sxs-lookup"><span data-stu-id="937c1-138">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="937c1-139">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="937c1-139">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="937c1-140">MS1</span><span class="sxs-lookup"><span data-stu-id="937c1-140">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="937c1-141">Definiert VoIP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="937c1-141">Defines Voice Policies</span></span>

<span data-ttu-id="937c1-142">Sie müssen VoIP-Richtlinien für Ihre Enterprise-VoIP-Bereitstellung definieren.</span><span class="sxs-lookup"><span data-stu-id="937c1-142">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="937c1-143">Definieren Sie eine VoIP-Richtlinie, um standortbasierte Routing Einschränkungen für eine Teilmenge von Benutzern zu erzwingen, wenn nur eine Teilmenge von Ihnen für die Verwendung von Standort basiertem Routing erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="937c1-143">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="937c1-144">In diesem Beispiel werden in der folgenden Tabelle die in diesem Szenario verwendeten VoIP-Richtlinien veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="937c1-144">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="937c1-145">Nur Einstellungen, die für standortbasierte Routings spezifisch sind, sind in der Tabelle zu Illustrationszwecken enthalten.</span><span class="sxs-lookup"><span data-stu-id="937c1-145">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="937c1-146">Weitere Informationen finden Sie unter [Konfigurieren von VoIP-Richtlinien und PSTN-Verwendungsdatensätzen, um die Anruffunktionen und-Berechtigungen in lync Server 2013 zu autorisieren](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="937c1-146">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="937c1-147">VoIP-Richtlinie 1</span><span class="sxs-lookup"><span data-stu-id="937c1-147">Voice policy 1</span></span></th>
<th><span data-ttu-id="937c1-148">VoIP-Richtlinie 2</span><span class="sxs-lookup"><span data-stu-id="937c1-148">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="937c1-149">VoIP-Richtlinienkennung</span><span class="sxs-lookup"><span data-stu-id="937c1-149">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="937c1-150">VoIP-Richtlinie für Delhi</span><span class="sxs-lookup"><span data-stu-id="937c1-150">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="937c1-151">Hyderabad-VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="937c1-151">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="937c1-152">PSTN-Nutzungen</span><span class="sxs-lookup"><span data-stu-id="937c1-152">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="937c1-153">Nutzung von Delhi, Nutzung von Telefonanlagen, Telefonanlagen Hyd</span><span class="sxs-lookup"><span data-stu-id="937c1-153">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="937c1-154">Hyderabad-Nutzung, Nutzung von Telefonanlagen Hyd, Telefonanlagen Nutzung</span><span class="sxs-lookup"><span data-stu-id="937c1-154">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="937c1-155">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="937c1-155">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="937c1-156">Falsch</span><span class="sxs-lookup"><span data-stu-id="937c1-156">False</span></span></p></td>
<td><p><span data-ttu-id="937c1-157">Falsch</span><span class="sxs-lookup"><span data-stu-id="937c1-157">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="937c1-158">Definieren von VoIP-Routen</span><span class="sxs-lookup"><span data-stu-id="937c1-158">Define Voice Routes</span></span>

<span data-ttu-id="937c1-159">Sie müssen VoIP-Routen für Ihre Enterprise-VoIP-Bereitstellung definieren.</span><span class="sxs-lookup"><span data-stu-id="937c1-159">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="937c1-160">In diesem Beispiel werden in der folgenden Tabelle die in diesem Szenario verwendeten VoIP-Routen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="937c1-160">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="937c1-161">Nur Einstellungen, die für standortbasierte Routings spezifisch sind, sind in der Tabelle zu Illustrationszwecken enthalten.</span><span class="sxs-lookup"><span data-stu-id="937c1-161">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="937c1-162">Weitere Informationen finden Sie unter [Konfigurieren von VoIP-Routen für ausgehende Anrufe in lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="937c1-162">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


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
<th><span data-ttu-id="937c1-163">VoIP-Route 1</span><span class="sxs-lookup"><span data-stu-id="937c1-163">Voice route 1</span></span></th>
<th><span data-ttu-id="937c1-164">VoIP-Route 2</span><span class="sxs-lookup"><span data-stu-id="937c1-164">Voice route 2</span></span></th>
<th><span data-ttu-id="937c1-165">VoIP-Route 3</span><span class="sxs-lookup"><span data-stu-id="937c1-165">Voice route 3</span></span></th>
<th><span data-ttu-id="937c1-166">VoIP-Route 4</span><span class="sxs-lookup"><span data-stu-id="937c1-166">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="937c1-167">Name</span><span class="sxs-lookup"><span data-stu-id="937c1-167">Name</span></span></p></td>
<td><p><span data-ttu-id="937c1-168">Delhi-Route</span><span class="sxs-lookup"><span data-stu-id="937c1-168">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="937c1-169">Hyderabad-Route</span><span class="sxs-lookup"><span data-stu-id="937c1-169">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="937c1-170">PBX del-Route</span><span class="sxs-lookup"><span data-stu-id="937c1-170">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="937c1-171">PBX-Hyd-Route</span><span class="sxs-lookup"><span data-stu-id="937c1-171">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="937c1-172">PSTN-Nutzungen</span><span class="sxs-lookup"><span data-stu-id="937c1-172">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="937c1-173">Delhi-Nutzung</span><span class="sxs-lookup"><span data-stu-id="937c1-173">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="937c1-174">Hyderabad-Nutzung</span><span class="sxs-lookup"><span data-stu-id="937c1-174">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="937c1-175">Telefonanlagen Nutzung</span><span class="sxs-lookup"><span data-stu-id="937c1-175">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="937c1-176">Verwendung von PBX-Hyd</span><span class="sxs-lookup"><span data-stu-id="937c1-176">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="937c1-177">Stamm</span><span class="sxs-lookup"><span data-stu-id="937c1-177">Trunk</span></span></p></td>
<td><p><span data-ttu-id="937c1-178">Trunk 1 del-GW</span><span class="sxs-lookup"><span data-stu-id="937c1-178">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="937c1-179">Trunk 2 Hyd-GW</span><span class="sxs-lookup"><span data-stu-id="937c1-179">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="937c1-180">Trunk 3 del-PBX</span><span class="sxs-lookup"><span data-stu-id="937c1-180">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="937c1-181">Trunk 4 Hyd-PBX</span><span class="sxs-lookup"><span data-stu-id="937c1-181">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="937c1-182">Enable Users for Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="937c1-182">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="937c1-183">Aktivieren Sie Benutzer für Enterprise-VoIP, und weisen Sie Ihnen eine VoIP-Richtlinie zu, die Sie zuvor definiert haben.</span><span class="sxs-lookup"><span data-stu-id="937c1-183">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="937c1-184">In diesem Beispiel wird in der folgenden Tabelle die in diesem Szenario verwendete Aufgabe veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="937c1-184">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="937c1-185">Nur Einstellungen, die für standortbasierte Routings spezifisch sind, sind in der Tabelle zu Illustrationszwecken enthalten.</span><span class="sxs-lookup"><span data-stu-id="937c1-185">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="937c1-186">Weitere Informationen finden Sie unter [Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="937c1-186">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="937c1-187">Benutzer in Delhi</span><span class="sxs-lookup"><span data-stu-id="937c1-187">Users located in Delhi</span></span></th>
<th><span data-ttu-id="937c1-188">Benutzer, die sich in Hyderabad befinden</span><span class="sxs-lookup"><span data-stu-id="937c1-188">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="937c1-189">Zugehörige VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="937c1-189">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="937c1-190">VoIP-Richtlinie für Delhi</span><span class="sxs-lookup"><span data-stu-id="937c1-190">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="937c1-191">Hyderabad-VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="937c1-191">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="937c1-192">Beispiel Benutzer</span><span class="sxs-lookup"><span data-stu-id="937c1-192">Sample users</span></span></p></td>
<td><p><span data-ttu-id="937c1-193">Del-lync-1, del-lync-2, del-lync-3</span><span class="sxs-lookup"><span data-stu-id="937c1-193">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="937c1-194">Hyd-lync-1, Hyd-lync-2, Hyd-lync-3</span><span class="sxs-lookup"><span data-stu-id="937c1-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="937c1-195">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="937c1-195">See Also</span></span>


[<span data-ttu-id="937c1-196">Konfigurieren von standortbasiertem Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="937c1-196">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

