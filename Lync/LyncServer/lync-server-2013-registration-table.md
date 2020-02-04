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
ms.openlocfilehash: 0bc19c35893b12aae7842be5fc474f7831b7f979
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="e6992-102">Registration-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6992-102">Registration table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6992-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e6992-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e6992-104">Jeder Datensatz steht für ein Benutzer Registrierungs Ereignis.</span><span class="sxs-lookup"><span data-stu-id="e6992-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e6992-105">Spalte</span><span class="sxs-lookup"><span data-stu-id="e6992-105">Column</span></span></th>
<th><span data-ttu-id="e6992-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e6992-106">Data Type</span></span></th>
<th><span data-ttu-id="e6992-107">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="e6992-107">Key/Index</span></span></th>
<th><span data-ttu-id="e6992-108">Details</span><span class="sxs-lookup"><span data-stu-id="e6992-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6992-109"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="e6992-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e6992-110">datetime</span><span class="sxs-lookup"><span data-stu-id="e6992-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="e6992-111">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="e6992-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e6992-112">Uhrzeit der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="e6992-112">Time of session request.</span></span> <span data-ttu-id="e6992-113">Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e6992-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e6992-114">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e6992-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6992-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e6992-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e6992-116">int</span><span class="sxs-lookup"><span data-stu-id="e6992-116">int</span></span></p></td>
<td><p><span data-ttu-id="e6992-117">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="e6992-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e6992-118">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e6992-118">ID number to identify the session.</span></span> <span data-ttu-id="e6992-119">Wird in Verbindung mit <strong>SessionID</strong> -Mal verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e6992-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e6992-120">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e6992-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6992-121"><strong>UserID</strong></span><span class="sxs-lookup"><span data-stu-id="e6992-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="e6992-122">int</span><span class="sxs-lookup"><span data-stu-id="e6992-122">int</span></span></p></td>
<td><p><span data-ttu-id="e6992-123">Fremd</span><span class="sxs-lookup"><span data-stu-id="e6992-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e6992-124">Die Benutzer-ID.</span><span class="sxs-lookup"><span data-stu-id="e6992-124">The user ID.</span></span> <span data-ttu-id="e6992-125">Weitere Informationen finden Sie <a href="lync-server-2013-users-table.md">in der Tabelle Benutzer in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e6992-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6992-126"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="e6992-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="e6992-127">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="e6992-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e6992-128">Eine GUID, um einen Registrierungs Endpunkt zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e6992-128">A GUID to identify a registration endpoint.</span></span> <span data-ttu-id="e6992-129">In der Regel verfügt das Register-Ereignis vom gleichen Computer desselben Benutzers über die gleiche Endpunkt-ID.</span><span class="sxs-lookup"><span data-stu-id="e6992-129">Usually the register event from the same computer of the same user will have the same endpoint ID.</span></span> <span data-ttu-id="e6992-130">Unterschiedliche Computer verfügen über eine andere Endpunkt-ID.</span><span class="sxs-lookup"><span data-stu-id="e6992-130">Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6992-131"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="e6992-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="e6992-132">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="e6992-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e6992-133">Die ID, mit der Registrierungen unterschieden werden, die denselben Benutzer und denselben Endpunkt einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="e6992-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="e6992-134">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e6992-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6992-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="e6992-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="e6992-136">int</span><span class="sxs-lookup"><span data-stu-id="e6992-136">int</span></span></p></td>
<td><p><span data-ttu-id="e6992-137">Fremd</span><span class="sxs-lookup"><span data-stu-id="e6992-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e6992-138">Client Version des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="e6992-138">Client version of current user.</span></span> <span data-ttu-id="e6992-139">Weitere Informationen finden Sie <a href="lync-server-2013-clientversions-table.md">in der ClientVersions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e6992-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6992-140"><strong>Registrator</strong></span><span class="sxs-lookup"><span data-stu-id="e6992-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="e6992-141">int</span><span class="sxs-lookup"><span data-stu-id="e6992-141">int</span></span></p></td>
<td><p><span data-ttu-id="e6992-142">Fremd</span><span class="sxs-lookup"><span data-stu-id="e6992-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e6992-143">Die ID des Registrierungsservers, der für die Registrierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e6992-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="e6992-144">Weitere Informationen finden Sie <a href="lync-server-2013-servers-table.md">in der Tabelle Server in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e6992-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6992-145"><strong>Pool-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="e6992-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="e6992-146">int</span><span class="sxs-lookup"><span data-stu-id="e6992-146">int</span></span></p></td>
<td><p><span data-ttu-id="e6992-147">Fremd</span><span class="sxs-lookup"><span data-stu-id="e6992-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e6992-148">Die ID des Pools, in dem die Sitzung erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="e6992-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="e6992-149">Weitere Informationen finden Sie <a href="lync-server-2013-pools-table.md">in der Tabelle Pools in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e6992-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6992-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="e6992-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="e6992-151">int</span><span class="sxs-lookup"><span data-stu-id="e6992-151">int</span></span></p></td>
<td><p><span data-ttu-id="e6992-152">Fremd</span><span class="sxs-lookup"><span data-stu-id="e6992-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e6992-153">Edge-Server die Registrierung wird durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="e6992-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="e6992-154">Weitere Informationen finden Sie <a href="lync-server-2013-edgeservers-table.md">in der EdgeServers-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e6992-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6992-155"><strong>"IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="e6992-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="e6992-156">Bit</span><span class="sxs-lookup"><span data-stu-id="e6992-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e6992-157">Gibt an, ob der Benutzer intern angemeldet ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="e6992-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6992-158"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="e6992-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="e6992-159">bit</span><span class="sxs-lookup"><span data-stu-id="e6992-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e6992-160">Gibt an, ob die UserService verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e6992-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6992-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="e6992-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="e6992-162">bit</span><span class="sxs-lookup"><span data-stu-id="e6992-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e6992-163">Ob Sie sich bei der primären Registrierungsstelle registrieren oder nicht.</span><span class="sxs-lookup"><span data-stu-id="e6992-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6992-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="e6992-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="e6992-165">bit</span><span class="sxs-lookup"><span data-stu-id="e6992-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e6992-166">Gibt an, ob der Benutzer bei einer Survivable Branch-Appliance registriert ist.</span><span class="sxs-lookup"><span data-stu-id="e6992-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="e6992-167">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e6992-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6992-168"><strong>Registrierung</strong></span><span class="sxs-lookup"><span data-stu-id="e6992-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e6992-169">datetime</span><span class="sxs-lookup"><span data-stu-id="e6992-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e6992-170">Registrierungszeit.</span><span class="sxs-lookup"><span data-stu-id="e6992-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6992-171"><strong>Registrierung</strong></span><span class="sxs-lookup"><span data-stu-id="e6992-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e6992-172">datetime</span><span class="sxs-lookup"><span data-stu-id="e6992-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e6992-173">Zeit für die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="e6992-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6992-174"><strong>Response Code</strong></span><span class="sxs-lookup"><span data-stu-id="e6992-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="e6992-175">int</span><span class="sxs-lookup"><span data-stu-id="e6992-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e6992-176">Antwortcode der Registrierungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="e6992-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6992-177"><strong>Diagnose-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="e6992-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="e6992-178">int</span><span class="sxs-lookup"><span data-stu-id="e6992-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e6992-179">Diagnose-ID der Registrierungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="e6992-179">Diagnostic ID of the register request.</span></span> <span data-ttu-id="e6992-180">Dies gibt an, dass der Typ der diagnostischen Informationen.</span><span class="sxs-lookup"><span data-stu-id="e6992-180">This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6992-181"><strong>DeviceID</strong></span><span class="sxs-lookup"><span data-stu-id="e6992-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="e6992-182">int</span><span class="sxs-lookup"><span data-stu-id="e6992-182">int</span></span></p></td>
<td><p><span data-ttu-id="e6992-183">Fremd</span><span class="sxs-lookup"><span data-stu-id="e6992-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e6992-184">Das Gerät, von dem die Registrierungsanforderung stammt.</span><span class="sxs-lookup"><span data-stu-id="e6992-184">The device that the register request is coming from.</span></span> <span data-ttu-id="e6992-185">Weitere Informationen finden Sie <a href="lync-server-2013-devices-table.md">in der Tabelle Devices in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e6992-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6992-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="e6992-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="e6992-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="e6992-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e6992-188">Fremd</span><span class="sxs-lookup"><span data-stu-id="e6992-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e6992-189">Der Grund für die Deregistrierung, wie "Benutzer initiiert", "Registrierung abgelaufen", "Client Fehler" und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="e6992-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="e6992-190">Weitere Informationen finden Sie <a href="lync-server-2013-deregistertype-table.md">in der Tabelle deregistertype in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e6992-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6992-191"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="e6992-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="e6992-192">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e6992-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e6992-193">Die IP-Adresse des Endpunkts, bei dem der Benutzer registriert ist.</span><span class="sxs-lookup"><span data-stu-id="e6992-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="e6992-194">Dies kann eine IPv4-Adresse oder eine IPv6-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="e6992-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="e6992-195">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e6992-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

