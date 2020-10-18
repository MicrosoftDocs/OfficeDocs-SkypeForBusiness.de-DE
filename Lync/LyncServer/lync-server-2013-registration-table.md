---
title: 'Lync Server 2013: Registration-Tabelle'
description: 'Lync Server 2013: Registrierungstabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 806e1a4e944c9bc04ebdd167c41c80a57fde3f29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578525"
---
# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="e5765-103">Registrierungstabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5765-103">Registration table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5765-104">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e5765-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e5765-105">Jeder Datensatz stellt ein Benutzerregistrierungsereignis dar.</span><span class="sxs-lookup"><span data-stu-id="e5765-105">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5765-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="e5765-106">Column</span></span></th>
<th><span data-ttu-id="e5765-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e5765-107">Data Type</span></span></th>
<th><span data-ttu-id="e5765-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="e5765-108">Key/Index</span></span></th>
<th><span data-ttu-id="e5765-109">Details</span><span class="sxs-lookup"><span data-stu-id="e5765-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5765-110"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="e5765-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e5765-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="e5765-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5765-112">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="e5765-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e5765-113">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="e5765-113">Time of session request.</span></span> <span data-ttu-id="e5765-114">Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e5765-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e5765-115">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e5765-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5765-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e5765-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e5765-117">int</span><span class="sxs-lookup"><span data-stu-id="e5765-117">int</span></span></p></td>
<td><p><span data-ttu-id="e5765-118">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="e5765-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e5765-119">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="e5765-119">ID number to identify the session.</span></span> <span data-ttu-id="e5765-120">Wird zusammen mit <strong>SessionIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e5765-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e5765-121">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e5765-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5765-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="e5765-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5765-123">int</span><span class="sxs-lookup"><span data-stu-id="e5765-123">int</span></span></p></td>
<td><p><span data-ttu-id="e5765-124">Fremd</span><span class="sxs-lookup"><span data-stu-id="e5765-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e5765-125">Die Benutzer-ID.</span><span class="sxs-lookup"><span data-stu-id="e5765-125">The user ID.</span></span> <span data-ttu-id="e5765-126">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e5765-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5765-127"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="e5765-127"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5765-128">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="e5765-128">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5765-p104">Eine GUID (Globally Unique Identifier) zur Kennzeichnung eines Registrierungsendpunkts. In der Regel hat jedes Registrierungsereignis vom gleichen Computer des gleichen Benutzers die gleiche Endpunkt-ID. Verschiedene Computer haben unterschiedliche Endpunkt-IDs.</span><span class="sxs-lookup"><span data-stu-id="e5765-p104">A GUID to identify a registration endpoint. Usually the register event from the same computer of the same user will have the same endpoint ID. Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5765-132"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="e5765-132"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="e5765-133">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="e5765-133">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5765-134">ID zum Unterscheiden von Registrierungen, die denselben Benutzer und denselben Endpunkt betreffen.</span><span class="sxs-lookup"><span data-stu-id="e5765-134">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="e5765-135">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e5765-135">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5765-136"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="e5765-136"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5765-137">int</span><span class="sxs-lookup"><span data-stu-id="e5765-137">int</span></span></p></td>
<td><p><span data-ttu-id="e5765-138">Fremd</span><span class="sxs-lookup"><span data-stu-id="e5765-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e5765-139">Die Clientversion des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="e5765-139">Client version of current user.</span></span> <span data-ttu-id="e5765-140">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der Client Versions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e5765-140">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5765-141"><strong>Registrierungsstelle</strong></span><span class="sxs-lookup"><span data-stu-id="e5765-141"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5765-142">int</span><span class="sxs-lookup"><span data-stu-id="e5765-142">int</span></span></p></td>
<td><p><span data-ttu-id="e5765-143">Fremd</span><span class="sxs-lookup"><span data-stu-id="e5765-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e5765-144">Die ID des Registrierungsservers, der für die Registrierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e5765-144">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="e5765-145">Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e5765-145">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5765-146"><strong>Pool-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="e5765-146"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5765-147">int</span><span class="sxs-lookup"><span data-stu-id="e5765-147">int</span></span></p></td>
<td><p><span data-ttu-id="e5765-148">Fremd</span><span class="sxs-lookup"><span data-stu-id="e5765-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e5765-149">ID des Pools, in dem die Sitzung erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="e5765-149">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="e5765-150">Weitere Informationen finden Sie <a href="lync-server-2013-pools-table.md">in der Tabelle Pools in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e5765-150">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5765-151"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="e5765-151"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5765-152">int</span><span class="sxs-lookup"><span data-stu-id="e5765-152">int</span></span></p></td>
<td><p><span data-ttu-id="e5765-153">Fremd</span><span class="sxs-lookup"><span data-stu-id="e5765-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e5765-154">Der Edgeserver, über den die Registrierung läuft.</span><span class="sxs-lookup"><span data-stu-id="e5765-154">Edge Server the registration is going through.</span></span> <span data-ttu-id="e5765-155">Weitere Informationen finden Sie <a href="lync-server-2013-edgeservers-table.md">in der EdgeServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e5765-155">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5765-156"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="e5765-156"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="e5765-157">Bit</span><span class="sxs-lookup"><span data-stu-id="e5765-157">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5765-158">Ob der Benutzer von innerhalb angemeldet ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="e5765-158">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5765-159"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="e5765-159"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="e5765-160">Bit</span><span class="sxs-lookup"><span data-stu-id="e5765-160">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5765-161">Ob der Benutzerdienst verfügbar ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="e5765-161">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5765-162"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="e5765-162"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="e5765-163">Bit</span><span class="sxs-lookup"><span data-stu-id="e5765-163">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5765-164">Ob die Registrierung bei der primären Registrierung erfolgt oder nicht.</span><span class="sxs-lookup"><span data-stu-id="e5765-164">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5765-165"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="e5765-165"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="e5765-166">Bit</span><span class="sxs-lookup"><span data-stu-id="e5765-166">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5765-167">Gibt an, ob der Benutzer mit einer Survivable Branch Appliance registriert ist.</span><span class="sxs-lookup"><span data-stu-id="e5765-167">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="e5765-168">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e5765-168">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5765-169"><strong>Registerzeit</strong></span><span class="sxs-lookup"><span data-stu-id="e5765-169"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e5765-170">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="e5765-170">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5765-171">Der Zeitpunkt der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="e5765-171">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5765-172"><strong>Deregisterzeit</strong></span><span class="sxs-lookup"><span data-stu-id="e5765-172"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e5765-173">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="e5765-173">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5765-174">Der Zeitpunkt der Aufhebung der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="e5765-174">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5765-175"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="e5765-175"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="e5765-176">int</span><span class="sxs-lookup"><span data-stu-id="e5765-176">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5765-177">Der Antwortcode der Registrierungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="e5765-177">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5765-178"><strong>Diagnose-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="e5765-178"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5765-179">int</span><span class="sxs-lookup"><span data-stu-id="e5765-179">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5765-p109">Die Diagnose-ID der Registrierungsanforderung. Diese gibt den Diagnoseinformationstyp an.</span><span class="sxs-lookup"><span data-stu-id="e5765-p109">Diagnostic ID of the register request. This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5765-182"><strong>DeviceID</strong></span><span class="sxs-lookup"><span data-stu-id="e5765-182"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5765-183">int</span><span class="sxs-lookup"><span data-stu-id="e5765-183">int</span></span></p></td>
<td><p><span data-ttu-id="e5765-184">Fremd</span><span class="sxs-lookup"><span data-stu-id="e5765-184">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e5765-185">Das Gerät, von dem die Registrierungsanforderung stammt.</span><span class="sxs-lookup"><span data-stu-id="e5765-185">The device that the register request is coming from.</span></span> <span data-ttu-id="e5765-186">Weitere Informationen finden Sie <a href="lync-server-2013-devices-table.md">in der Tabelle "Geräte" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e5765-186">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5765-187"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="e5765-187"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5765-188">tinyint</span><span class="sxs-lookup"><span data-stu-id="e5765-188">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e5765-189">Fremd</span><span class="sxs-lookup"><span data-stu-id="e5765-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e5765-190">Der Grund für die Aufhebung der Registrierung, z. B. vom Benutzer initiiert, Registrierung abgelaufen, Fehler beim Client usw.</span><span class="sxs-lookup"><span data-stu-id="e5765-190">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="e5765-191">Weitere Informationen finden Sie <a href="lync-server-2013-deregistertype-table.md">in der deregistertype-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e5765-191">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5765-192"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="e5765-192"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="e5765-193">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e5765-193">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5765-194">IP-Adresse des Endpunkts, mit dem sich der Benutzer registriert hat.</span><span class="sxs-lookup"><span data-stu-id="e5765-194">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="e5765-195">Dies kann eine IPv4- oder eine IPv6-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="e5765-195">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="e5765-196">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e5765-196">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

