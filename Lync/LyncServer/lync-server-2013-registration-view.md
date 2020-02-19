---
title: 'Lync Server 2013: Registrierungs Ansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f6a48780535960a71a06f2edfcb6c2b8a95d999
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="54260-102">Registrierungs Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54260-102">Registration view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54260-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="54260-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="54260-104">In der Registrierungs Ansicht werden Informationen zur Benutzerregistrierung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="54260-104">The Registration view stores information about user registration.</span></span> <span data-ttu-id="54260-105">Diese Ansicht wurde in lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="54260-105">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54260-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="54260-106">Column</span></span></th>
<th><span data-ttu-id="54260-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="54260-107">Data Type</span></span></th>
<th><span data-ttu-id="54260-108">Details</span><span class="sxs-lookup"><span data-stu-id="54260-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54260-109"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="54260-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-110">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="54260-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="54260-111">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="54260-111">Time of session request.</span></span> <span data-ttu-id="54260-112">Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren..</span><span class="sxs-lookup"><span data-stu-id="54260-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="54260-113">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="54260-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54260-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="54260-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-115">int</span><span class="sxs-lookup"><span data-stu-id="54260-115">int</span></span></p></td>
<td><p><span data-ttu-id="54260-116">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="54260-116">ID number to identify the session.</span></span> <span data-ttu-id="54260-117">Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="54260-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="54260-118">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="54260-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54260-119"><strong>Registerzeit</strong></span><span class="sxs-lookup"><span data-stu-id="54260-119"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-120">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="54260-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="54260-121">Zeitpunkt, zu dem die Registrierung erfolgte.</span><span class="sxs-lookup"><span data-stu-id="54260-121">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54260-122"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="54260-122"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="54260-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="54260-124">URI des registrierten Benutzers.</span><span class="sxs-lookup"><span data-stu-id="54260-124">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54260-125"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="54260-125"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="54260-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54260-127">URI-Typ des registrierten Benutzers.</span><span class="sxs-lookup"><span data-stu-id="54260-127">Type of URI of the user who registered.</span></span> <span data-ttu-id="54260-128">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="54260-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54260-129"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="54260-129"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="54260-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54260-131">Mandant des registrierten Benutzers.</span><span class="sxs-lookup"><span data-stu-id="54260-131">Tenant of the user who registered.</span></span> <span data-ttu-id="54260-132">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="54260-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54260-133"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="54260-133"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-134">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="54260-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="54260-135">Eindeutiger Bezeichner des Endpunkts des Benutzers, der registriert ist.</span><span class="sxs-lookup"><span data-stu-id="54260-135">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54260-136"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="54260-136"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-137">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="54260-137">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="54260-138">Eindeutiger Bezeichner zum unterscheiden von Registrierungen, bei denen derselbe Benutzer und derselbe Endpunkt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="54260-138">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54260-139"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="54260-139"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-140">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="54260-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="54260-141">Zeitpunkt, zu dem die Registrierung aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="54260-141">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54260-142"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="54260-142"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="54260-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54260-144">Grund für die Aufhebung der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="54260-144">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54260-145"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="54260-145"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-146">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="54260-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54260-147">Version des Clients, die von dem Benutzer verwendet wird, der registriert ist.</span><span class="sxs-lookup"><span data-stu-id="54260-147">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54260-148"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="54260-148"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-149">int</span><span class="sxs-lookup"><span data-stu-id="54260-149">int</span></span></p></td>
<td><p><span data-ttu-id="54260-150">Client, der vom registrierten Benutzer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="54260-150">Client used by the user who registered.</span></span> <span data-ttu-id="54260-151">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="54260-151">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54260-152"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="54260-152"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-153">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="54260-153">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="54260-154">Die Kategorie des Clients, der von dem Benutzer verwendet wird, der registriert ist.</span><span class="sxs-lookup"><span data-stu-id="54260-154">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54260-155"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="54260-155"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-156">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="54260-156">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54260-157">IP-Adresse, mit der der Benutzer registriert hat.</span><span class="sxs-lookup"><span data-stu-id="54260-157">IP Address the user registered with.</span></span> <span data-ttu-id="54260-158">Hierbei kann es sich um eine IPv4-oder IPv6-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="54260-158">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54260-159"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="54260-159"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-160">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="54260-160">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="54260-161">SIP-Dialog-ID.</span><span class="sxs-lookup"><span data-stu-id="54260-161">SIP dialog ID.</span></span> <span data-ttu-id="54260-162">Das Format von ist:</span><span class="sxs-lookup"><span data-stu-id="54260-162">The format of the is:</span></span></p>
<p><span data-ttu-id="54260-163">Dialogfeld; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="54260-163">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54260-164"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="54260-164"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-165">int</span><span class="sxs-lookup"><span data-stu-id="54260-165">int</span></span></p></td>
<td><p><span data-ttu-id="54260-p109">SIP-Antwortcode auf die Sitzungseinladung. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="54260-p109">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54260-169"><strong>Diagnose-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="54260-169"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-170">int</span><span class="sxs-lookup"><span data-stu-id="54260-170">int</span></span></p></td>
<td><p><span data-ttu-id="54260-171">Vom SIP-Header erfasste Diagnose-ID.</span><span class="sxs-lookup"><span data-stu-id="54260-171">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54260-172"><strong>Registrierungsstelle</strong></span><span class="sxs-lookup"><span data-stu-id="54260-172"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="54260-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54260-174">FQDN der Registrierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="54260-174">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54260-175"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="54260-175"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="54260-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54260-177">Vollqualifizierter Domänenname des Pools, der die Daten für die Sitzung erfasst hat.</span><span class="sxs-lookup"><span data-stu-id="54260-177">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54260-178"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="54260-178"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-179">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="54260-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54260-180">Der FQDN des Edgeserver, der von dem Benutzer verwendet wird, der registriert ist.</span><span class="sxs-lookup"><span data-stu-id="54260-180">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54260-181"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="54260-181"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-182">Bit</span><span class="sxs-lookup"><span data-stu-id="54260-182">bit</span></span></p></td>
<td><p><span data-ttu-id="54260-183">Gibt an, ob sich der Benutzer aus dem internen Netzwerk angemeldet hat.</span><span class="sxs-lookup"><span data-stu-id="54260-183">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54260-184"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="54260-184"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-185">Bit</span><span class="sxs-lookup"><span data-stu-id="54260-185">bit</span></span></p></td>
<td><p><span data-ttu-id="54260-186">Gibt an, ob das UserService zum Zeitpunkt der Registrierung verfügbar war.</span><span class="sxs-lookup"><span data-stu-id="54260-186">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54260-187"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="54260-187"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-188">Bit</span><span class="sxs-lookup"><span data-stu-id="54260-188">bit</span></span></p></td>
<td><p><span data-ttu-id="54260-189">Gibt an, ob die Registrierung bei der primären Registrierungsstelle erfolgte.</span><span class="sxs-lookup"><span data-stu-id="54260-189">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54260-190"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="54260-190"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-191">bigint</span><span class="sxs-lookup"><span data-stu-id="54260-191">bigint</span></span></p></td>
<td><p><span data-ttu-id="54260-192">Mac-Adresse des registrierten Geräts.</span><span class="sxs-lookup"><span data-stu-id="54260-192">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54260-193"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="54260-193"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="54260-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54260-195">Hersteller des registrierten Geräts.</span><span class="sxs-lookup"><span data-stu-id="54260-195">Manufacturer of the device registered.</span></span> <span data-ttu-id="54260-196">Weitere Informationen finden Sie <a href="lync-server-2013-manufacturers-table.md">in der Tabelle Hersteller in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="54260-196">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54260-197"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="54260-197"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="54260-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="54260-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54260-199">Hardware Version des registrierten Geräts.</span><span class="sxs-lookup"><span data-stu-id="54260-199">Hardware version of the device registered.</span></span> <span data-ttu-id="54260-200">Weitere Informationen finden Sie <a href="lync-server-2013-hardwareversions-table.md">in der Hardware Versions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="54260-200">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

