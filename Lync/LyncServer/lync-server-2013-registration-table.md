---
title: 'Lync Server 2013: Registration-Tabelle'
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
ms.openlocfilehash: 0679915e73061e550e01c0809fd5c5b20b566ff6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="fe3d0-102">Registrierungstabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe3d0-102">Registration table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe3d0-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="fe3d0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="fe3d0-104">Jeder Datensatz stellt ein Benutzerregistrierungsereignis dar.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe3d0-105">Spalte</span><span class="sxs-lookup"><span data-stu-id="fe3d0-105">Column</span></span></th>
<th><span data-ttu-id="fe3d0-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="fe3d0-106">Data Type</span></span></th>
<th><span data-ttu-id="fe3d0-107">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="fe3d0-107">Key/Index</span></span></th>
<th><span data-ttu-id="fe3d0-108">Details</span><span class="sxs-lookup"><span data-stu-id="fe3d0-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe3d0-109"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="fe3d0-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe3d0-110">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="fe3d0-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="fe3d0-111">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="fe3d0-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe3d0-112">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-112">Time of session request.</span></span> <span data-ttu-id="fe3d0-113">Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="fe3d0-114">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe3d0-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe3d0-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fe3d0-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fe3d0-116">int</span><span class="sxs-lookup"><span data-stu-id="fe3d0-116">int</span></span></p></td>
<td><p><span data-ttu-id="fe3d0-117">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="fe3d0-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe3d0-118">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-118">ID number to identify the session.</span></span> <span data-ttu-id="fe3d0-119">Wird zusammen mit <strong>SessionIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="fe3d0-120">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe3d0-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe3d0-121"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="fe3d0-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe3d0-122">int</span><span class="sxs-lookup"><span data-stu-id="fe3d0-122">int</span></span></p></td>
<td><p><span data-ttu-id="fe3d0-123">Fremd</span><span class="sxs-lookup"><span data-stu-id="fe3d0-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe3d0-124">Die Benutzer-ID.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-124">The user ID.</span></span> <span data-ttu-id="fe3d0-125">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe3d0-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe3d0-126"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="fe3d0-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe3d0-127">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="fe3d0-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe3d0-p104">Eine GUID (Globally Unique Identifier) zur Kennzeichnung eines Registrierungsendpunkts. In der Regel hat jedes Registrierungsereignis vom gleichen Computer des gleichen Benutzers die gleiche Endpunkt-ID. Verschiedene Computer haben unterschiedliche Endpunkt-IDs.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-p104">A GUID to identify a registration endpoint. Usually the register event from the same computer of the same user will have the same endpoint ID. Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe3d0-131"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="fe3d0-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="fe3d0-132">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="fe3d0-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe3d0-133">ID zum Unterscheiden von Registrierungen, die denselben Benutzer und denselben Endpunkt betreffen.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="fe3d0-134">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe3d0-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="fe3d0-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe3d0-136">int</span><span class="sxs-lookup"><span data-stu-id="fe3d0-136">int</span></span></p></td>
<td><p><span data-ttu-id="fe3d0-137">Fremd</span><span class="sxs-lookup"><span data-stu-id="fe3d0-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe3d0-138">Die Clientversion des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-138">Client version of current user.</span></span> <span data-ttu-id="fe3d0-139">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der Client Versions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe3d0-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe3d0-140"><strong>Registrierungsstelle</strong></span><span class="sxs-lookup"><span data-stu-id="fe3d0-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe3d0-141">int</span><span class="sxs-lookup"><span data-stu-id="fe3d0-141">int</span></span></p></td>
<td><p><span data-ttu-id="fe3d0-142">Fremd</span><span class="sxs-lookup"><span data-stu-id="fe3d0-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe3d0-143">Die ID des Registrierungsservers, der für die Registrierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="fe3d0-144">Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe3d0-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe3d0-145"><strong>Pool-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="fe3d0-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe3d0-146">int</span><span class="sxs-lookup"><span data-stu-id="fe3d0-146">int</span></span></p></td>
<td><p><span data-ttu-id="fe3d0-147">Fremd</span><span class="sxs-lookup"><span data-stu-id="fe3d0-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe3d0-148">ID des Pools, in dem die Sitzung erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="fe3d0-149">Weitere Informationen finden Sie <a href="lync-server-2013-pools-table.md">in der Tabelle Pools in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe3d0-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe3d0-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="fe3d0-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe3d0-151">int</span><span class="sxs-lookup"><span data-stu-id="fe3d0-151">int</span></span></p></td>
<td><p><span data-ttu-id="fe3d0-152">Fremd</span><span class="sxs-lookup"><span data-stu-id="fe3d0-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe3d0-153">Der Edgeserver, über den die Registrierung läuft.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="fe3d0-154">Weitere Informationen finden Sie <a href="lync-server-2013-edgeservers-table.md">in der EdgeServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe3d0-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe3d0-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="fe3d0-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="fe3d0-156">Bit</span><span class="sxs-lookup"><span data-stu-id="fe3d0-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe3d0-157">Ob der Benutzer von innerhalb angemeldet ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe3d0-158"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="fe3d0-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="fe3d0-159">Bit</span><span class="sxs-lookup"><span data-stu-id="fe3d0-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe3d0-160">Ob der Benutzerdienst verfügbar ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe3d0-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="fe3d0-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="fe3d0-162">Bit</span><span class="sxs-lookup"><span data-stu-id="fe3d0-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe3d0-163">Ob die Registrierung bei der primären Registrierung erfolgt oder nicht.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe3d0-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="fe3d0-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="fe3d0-165">Bit</span><span class="sxs-lookup"><span data-stu-id="fe3d0-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe3d0-166">Gibt an, ob der Benutzer mit einer Survivable Branch Appliance registriert ist.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="fe3d0-167">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe3d0-168"><strong>Registerzeit</strong></span><span class="sxs-lookup"><span data-stu-id="fe3d0-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe3d0-169">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="fe3d0-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe3d0-170">Der Zeitpunkt der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe3d0-171"><strong>Deregisterzeit</strong></span><span class="sxs-lookup"><span data-stu-id="fe3d0-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe3d0-172">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="fe3d0-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe3d0-173">Der Zeitpunkt der Aufhebung der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe3d0-174"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="fe3d0-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="fe3d0-175">int</span><span class="sxs-lookup"><span data-stu-id="fe3d0-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe3d0-176">Der Antwortcode der Registrierungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe3d0-177"><strong>Diagnose-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="fe3d0-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe3d0-178">int</span><span class="sxs-lookup"><span data-stu-id="fe3d0-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe3d0-p109">Die Diagnose-ID der Registrierungsanforderung. Diese gibt den Diagnoseinformationstyp an.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-p109">Diagnostic ID of the register request. This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe3d0-181"><strong>DeviceID</strong></span><span class="sxs-lookup"><span data-stu-id="fe3d0-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe3d0-182">int</span><span class="sxs-lookup"><span data-stu-id="fe3d0-182">int</span></span></p></td>
<td><p><span data-ttu-id="fe3d0-183">Fremd</span><span class="sxs-lookup"><span data-stu-id="fe3d0-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe3d0-184">Das Gerät, von dem die Registrierungsanforderung stammt.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-184">The device that the register request is coming from.</span></span> <span data-ttu-id="fe3d0-185">Weitere Informationen finden Sie <a href="lync-server-2013-devices-table.md">in der Tabelle "Geräte" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe3d0-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe3d0-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="fe3d0-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe3d0-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="fe3d0-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fe3d0-188">Fremd</span><span class="sxs-lookup"><span data-stu-id="fe3d0-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe3d0-189">Der Grund für die Aufhebung der Registrierung, z. B. vom Benutzer initiiert, Registrierung abgelaufen, Fehler beim Client usw.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="fe3d0-190">Weitere Informationen finden Sie <a href="lync-server-2013-deregistertype-table.md">in der deregistertype-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe3d0-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe3d0-191"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="fe3d0-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="fe3d0-192">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fe3d0-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe3d0-193">IP-Adresse des Endpunkts, mit dem sich der Benutzer registriert hat.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="fe3d0-194">Dies kann eine IPv4- oder eine IPv6-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="fe3d0-195">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fe3d0-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

