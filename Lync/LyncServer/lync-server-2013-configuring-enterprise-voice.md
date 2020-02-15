---
title: 'Lync Server 2013: Konfigurieren von Enterprise-VoIP'
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
ms.openlocfilehash: 76105b9bee5ce35801196b5a4cd20b2a1feed3e7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="edb1a-102">Konfigurieren von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="edb1a-102">Configuring Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edb1a-103">_**Letztes Änderungsstand des Themas:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="edb1a-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="edb1a-104">Um Enterprise-VoIP bereitzustellen, müssen Sie Folgendes konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="edb1a-104">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="edb1a-105">Erstellen eines Trunks</span><span class="sxs-lookup"><span data-stu-id="edb1a-105">Create a Trunk</span></span>

  - <span data-ttu-id="edb1a-106">Definieren einer VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="edb1a-106">Define a Voice Policy</span></span>

  - <span data-ttu-id="edb1a-107">Definieren einer VoIP-Route</span><span class="sxs-lookup"><span data-stu-id="edb1a-107">Define a Voice Route</span></span>

  - <span data-ttu-id="edb1a-108">Aktivieren von Benutzern für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="edb1a-108">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="edb1a-109">Erstellen eines Trunks</span><span class="sxs-lookup"><span data-stu-id="edb1a-109">Create a Trunk</span></span>

<span data-ttu-id="edb1a-110">Sie müssen Trunks in Ihrer Enterprise-VoIP-Bereitstellung definieren.</span><span class="sxs-lookup"><span data-stu-id="edb1a-110">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="edb1a-111">Für das standortbasierte Routing müssen Sie eine trunkkonfiguration pro trunk erstellen.</span><span class="sxs-lookup"><span data-stu-id="edb1a-111">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="edb1a-112">Verwenden Sie den lync Server Topologie-Generator, um Ihre Trunks zu definieren, und verwenden Sie den lync Server Windows PowerShell-Befehl, New-CsTrunkConfiguration oder den lync Server-Systemsteuerung, um die entsprechenden Trunk Konfigurationen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="edb1a-112">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="edb1a-113">Weitere Informationen zum Aktivieren des standortbasierten Routings auf Trunk Konfigurationen finden Sie im Abschnitt Aktivieren des standortbasierten Routings für Trunks, im Thema Aktivieren des [standortbasierten Routings in lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="edb1a-113">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="edb1a-114">In diesem Beispiel werden in der folgenden Tabelle die Trunks dargestellt, die in diesem Szenario verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="edb1a-114">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="edb1a-115">Weitere Informationen finden Sie unter [Definieren zusätzlicher Trunks im Topologie-Generator in lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="edb1a-115">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


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
<th><span data-ttu-id="edb1a-116">Trunk Name</span><span class="sxs-lookup"><span data-stu-id="edb1a-116">Trunk name</span></span></th>
<th><span data-ttu-id="edb1a-117">Systemtyp</span><span class="sxs-lookup"><span data-stu-id="edb1a-117">System type</span></span></th>
<th><span data-ttu-id="edb1a-118">Name</span><span class="sxs-lookup"><span data-stu-id="edb1a-118">Name</span></span></th>
<th><span data-ttu-id="edb1a-119">Ort</span><span class="sxs-lookup"><span data-stu-id="edb1a-119">Location</span></span></th>
<th><span data-ttu-id="edb1a-120">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="edb1a-120">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edb1a-121">Trunk 1 del-GW</span><span class="sxs-lookup"><span data-stu-id="edb1a-121">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="edb1a-122">PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="edb1a-122">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="edb1a-123">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="edb1a-123">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="edb1a-124">Delhi</span><span class="sxs-lookup"><span data-stu-id="edb1a-124">Delhi</span></span></p></td>
<td><p><span data-ttu-id="edb1a-125">MS1</span><span class="sxs-lookup"><span data-stu-id="edb1a-125">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edb1a-126">Trunk 2 Hyd-GW</span><span class="sxs-lookup"><span data-stu-id="edb1a-126">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="edb1a-127">PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="edb1a-127">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="edb1a-128">Hyd-GW</span><span class="sxs-lookup"><span data-stu-id="edb1a-128">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="edb1a-129">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="edb1a-129">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="edb1a-130">MS1</span><span class="sxs-lookup"><span data-stu-id="edb1a-130">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edb1a-131">Trunk 3 del-Nebenstellenanlage</span><span class="sxs-lookup"><span data-stu-id="edb1a-131">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="edb1a-132">PBX</span><span class="sxs-lookup"><span data-stu-id="edb1a-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="edb1a-133">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="edb1a-133">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="edb1a-134">Delhi</span><span class="sxs-lookup"><span data-stu-id="edb1a-134">Delhi</span></span></p></td>
<td><p><span data-ttu-id="edb1a-135">MS1</span><span class="sxs-lookup"><span data-stu-id="edb1a-135">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edb1a-136">Trunk 4 Hyd-Nebenstellenanlage</span><span class="sxs-lookup"><span data-stu-id="edb1a-136">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="edb1a-137">PBX</span><span class="sxs-lookup"><span data-stu-id="edb1a-137">PBX</span></span></p></td>
<td><p><span data-ttu-id="edb1a-138">Hyd-PBX</span><span class="sxs-lookup"><span data-stu-id="edb1a-138">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="edb1a-139">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="edb1a-139">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="edb1a-140">MS1</span><span class="sxs-lookup"><span data-stu-id="edb1a-140">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="edb1a-141">Definiert VoIP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="edb1a-141">Defines Voice Policies</span></span>

<span data-ttu-id="edb1a-142">Sie müssen VoIP-Richtlinien für Ihre Enterprise-VoIP-Bereitstellung definieren.</span><span class="sxs-lookup"><span data-stu-id="edb1a-142">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="edb1a-143">Definieren Sie eine VoIP-Richtlinie zum Erzwingen von standortbasierten Routing Einschränkungen für eine Teilmenge von Benutzern, wenn nur eine Teilmenge davon für die Verwendung des standortbasierten Routings erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="edb1a-143">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="edb1a-144">In diesem Beispiel werden in der folgenden Tabelle die in diesem Szenario verwendeten VoIP-Richtlinien erläutert.</span><span class="sxs-lookup"><span data-stu-id="edb1a-144">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="edb1a-145">Zur Veranschaulichung werden nur Einstellungen, die für das standortbasierte Routing spezifisch sind, in der Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="edb1a-145">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="edb1a-146">Weitere Informationen finden Sie unter [Konfigurieren von VoIP-Richtlinien und PSTN-Verwendungsdatensätzen zum Autorisieren von Anruffunktionen und-Berechtigungen in lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="edb1a-146">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="edb1a-147">VoIP-Richtlinie 1</span><span class="sxs-lookup"><span data-stu-id="edb1a-147">Voice policy 1</span></span></th>
<th><span data-ttu-id="edb1a-148">VoIP-Richtlinie 2</span><span class="sxs-lookup"><span data-stu-id="edb1a-148">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edb1a-149">VoIP-Richtlinien-ID</span><span class="sxs-lookup"><span data-stu-id="edb1a-149">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="edb1a-150">VoIP-Richtlinie für Delhi</span><span class="sxs-lookup"><span data-stu-id="edb1a-150">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="edb1a-151">Hyderabad-VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="edb1a-151">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edb1a-152">PSTN-Verwendungen</span><span class="sxs-lookup"><span data-stu-id="edb1a-152">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="edb1a-153">Verwendung von Delhi, PBX del Usage, PBX Hyd</span><span class="sxs-lookup"><span data-stu-id="edb1a-153">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="edb1a-154">Verwendung von Hyderabad, Nebenstellenanlagen Hyd, PBX del Usage</span><span class="sxs-lookup"><span data-stu-id="edb1a-154">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edb1a-155">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="edb1a-155">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="edb1a-156">False</span><span class="sxs-lookup"><span data-stu-id="edb1a-156">False</span></span></p></td>
<td><p><span data-ttu-id="edb1a-157">False</span><span class="sxs-lookup"><span data-stu-id="edb1a-157">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="edb1a-158">Definieren von VoIP-Routen</span><span class="sxs-lookup"><span data-stu-id="edb1a-158">Define Voice Routes</span></span>

<span data-ttu-id="edb1a-159">Sie müssen VoIP-Routen für Ihre Enterprise-VoIP-Bereitstellung definieren.</span><span class="sxs-lookup"><span data-stu-id="edb1a-159">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="edb1a-160">In diesem Beispiel werden in der folgenden Tabelle die in diesem Szenario verwendeten VoIP-Routen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="edb1a-160">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="edb1a-161">Zur Veranschaulichung werden nur Einstellungen, die für das standortbasierte Routing spezifisch sind, in der Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="edb1a-161">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="edb1a-162">Weitere Informationen finden Sie unter [Konfigurieren von VoIP-Routen für ausgehende Anrufe in lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="edb1a-162">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


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
<th><span data-ttu-id="edb1a-163">VoIP-Route 1</span><span class="sxs-lookup"><span data-stu-id="edb1a-163">Voice route 1</span></span></th>
<th><span data-ttu-id="edb1a-164">VoIP-Route 2</span><span class="sxs-lookup"><span data-stu-id="edb1a-164">Voice route 2</span></span></th>
<th><span data-ttu-id="edb1a-165">VoIP-Route 3</span><span class="sxs-lookup"><span data-stu-id="edb1a-165">Voice route 3</span></span></th>
<th><span data-ttu-id="edb1a-166">VoIP-Route 4</span><span class="sxs-lookup"><span data-stu-id="edb1a-166">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edb1a-167">Name</span><span class="sxs-lookup"><span data-stu-id="edb1a-167">Name</span></span></p></td>
<td><p><span data-ttu-id="edb1a-168">Delhi-Route</span><span class="sxs-lookup"><span data-stu-id="edb1a-168">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="edb1a-169">Hyderabad-Route</span><span class="sxs-lookup"><span data-stu-id="edb1a-169">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="edb1a-170">Nebenstellenanlage del Route</span><span class="sxs-lookup"><span data-stu-id="edb1a-170">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="edb1a-171">PBX-Hyd-Route</span><span class="sxs-lookup"><span data-stu-id="edb1a-171">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edb1a-172">PSTN-Verwendungen</span><span class="sxs-lookup"><span data-stu-id="edb1a-172">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="edb1a-173">Delhi-Nutzung</span><span class="sxs-lookup"><span data-stu-id="edb1a-173">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="edb1a-174">Hyderabad-Nutzung</span><span class="sxs-lookup"><span data-stu-id="edb1a-174">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="edb1a-175">PBX del-Nutzung</span><span class="sxs-lookup"><span data-stu-id="edb1a-175">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="edb1a-176">PBX-Hyd-Verwendung</span><span class="sxs-lookup"><span data-stu-id="edb1a-176">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edb1a-177">Stamm</span><span class="sxs-lookup"><span data-stu-id="edb1a-177">Trunk</span></span></p></td>
<td><p><span data-ttu-id="edb1a-178">Trunk 1 del-GW</span><span class="sxs-lookup"><span data-stu-id="edb1a-178">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="edb1a-179">Trunk 2 Hyd-GW</span><span class="sxs-lookup"><span data-stu-id="edb1a-179">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="edb1a-180">Trunk 3 del-Nebenstellenanlage</span><span class="sxs-lookup"><span data-stu-id="edb1a-180">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="edb1a-181">Trunk 4 Hyd-Nebenstellenanlage</span><span class="sxs-lookup"><span data-stu-id="edb1a-181">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="edb1a-182">Aktivieren von Benutzern für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="edb1a-182">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="edb1a-183">Aktivieren Sie Benutzer für Enterprise-VoIP, und weisen Sie Ihnen eine VoIP-Richtlinie zu, die Sie zuvor definiert haben.</span><span class="sxs-lookup"><span data-stu-id="edb1a-183">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="edb1a-184">In diesem Beispiel wird in der folgenden Tabelle die in diesem Szenario verwendete Zuweisung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="edb1a-184">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="edb1a-185">Zur Veranschaulichung werden nur Einstellungen, die für das standortbasierte Routing spezifisch sind, in der Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="edb1a-185">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="edb1a-186">Weitere Informationen finden Sie unter [Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="edb1a-186">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="edb1a-187">Benutzer, die sich in Delhi befinden</span><span class="sxs-lookup"><span data-stu-id="edb1a-187">Users located in Delhi</span></span></th>
<th><span data-ttu-id="edb1a-188">Benutzer, die sich in Hyderabad befinden</span><span class="sxs-lookup"><span data-stu-id="edb1a-188">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edb1a-189">Zugeordnete VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="edb1a-189">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="edb1a-190">VoIP-Richtlinie für Delhi</span><span class="sxs-lookup"><span data-stu-id="edb1a-190">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="edb1a-191">Hyderabad-VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="edb1a-191">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edb1a-192">Beispiel Benutzer</span><span class="sxs-lookup"><span data-stu-id="edb1a-192">Sample users</span></span></p></td>
<td><p><span data-ttu-id="edb1a-193">Del-lync-1, del-lync-2, del-lync-3</span><span class="sxs-lookup"><span data-stu-id="edb1a-193">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="edb1a-194">Hyd-lync-1, Hyd-lync-2, Hyd-lync-3</span><span class="sxs-lookup"><span data-stu-id="edb1a-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="edb1a-195">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="edb1a-195">See Also</span></span>


[<span data-ttu-id="edb1a-196">Konfigurieren des standortbasierten Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="edb1a-196">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

