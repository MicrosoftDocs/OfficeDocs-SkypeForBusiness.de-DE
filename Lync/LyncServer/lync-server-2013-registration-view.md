---
title: 'Lync Server 2013: Registrierungs Ansicht'
description: 'Lync Server 2013: Registrierungs Ansicht.'
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
ms.openlocfilehash: be169cafc324f89cacedda154ca49a8ff1ff39aa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578526"
---
# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="c7606-103">Registrierungs Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7606-103">Registration view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7606-104">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c7606-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c7606-105">In der Registrierungs Ansicht werden Informationen zur Benutzerregistrierung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c7606-105">The Registration view stores information about user registration.</span></span> <span data-ttu-id="c7606-106">Diese Ansicht wurde in lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c7606-106">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7606-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="c7606-107">Column</span></span></th>
<th><span data-ttu-id="c7606-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="c7606-108">Data Type</span></span></th>
<th><span data-ttu-id="c7606-109">Details</span><span class="sxs-lookup"><span data-stu-id="c7606-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7606-110"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="c7606-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="c7606-112">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="c7606-112">Time of session request.</span></span> <span data-ttu-id="c7606-113">Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren..</span><span class="sxs-lookup"><span data-stu-id="c7606-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="c7606-114">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c7606-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7606-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-116">int</span><span class="sxs-lookup"><span data-stu-id="c7606-116">int</span></span></p></td>
<td><p><span data-ttu-id="c7606-117">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="c7606-117">ID number to identify the session.</span></span> <span data-ttu-id="c7606-118">Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c7606-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="c7606-119">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c7606-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7606-120"><strong>Registerzeit</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-120"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-121">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="c7606-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="c7606-122">Zeitpunkt, zu dem die Registrierung erfolgte.</span><span class="sxs-lookup"><span data-stu-id="c7606-122">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7606-123"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-123"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-124">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c7606-124">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c7606-125">URI des registrierten Benutzers.</span><span class="sxs-lookup"><span data-stu-id="c7606-125">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7606-126"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-126"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c7606-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c7606-128">URI-Typ des registrierten Benutzers.</span><span class="sxs-lookup"><span data-stu-id="c7606-128">Type of URI of the user who registered.</span></span> <span data-ttu-id="c7606-129">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c7606-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7606-130"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-130"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c7606-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c7606-132">Mandant des registrierten Benutzers.</span><span class="sxs-lookup"><span data-stu-id="c7606-132">Tenant of the user who registered.</span></span> <span data-ttu-id="c7606-133">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c7606-133">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7606-134"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-134"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-135">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="c7606-135">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="c7606-136">Eindeutiger Bezeichner des Endpunkts des Benutzers, der registriert ist.</span><span class="sxs-lookup"><span data-stu-id="c7606-136">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7606-137"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-137"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-138">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="c7606-138">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="c7606-139">Eindeutiger Bezeichner zum unterscheiden von Registrierungen, bei denen derselbe Benutzer und derselbe Endpunkt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c7606-139">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7606-140"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-140"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-141">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="c7606-141">datetime</span></span></p></td>
<td><p><span data-ttu-id="c7606-142">Zeitpunkt, zu dem die Registrierung aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="c7606-142">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7606-143"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-143"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c7606-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c7606-145">Grund für die Aufhebung der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="c7606-145">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7606-146"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-146"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-147">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c7606-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c7606-148">Version des Clients, die von dem Benutzer verwendet wird, der registriert ist.</span><span class="sxs-lookup"><span data-stu-id="c7606-148">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7606-149"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-149"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-150">int</span><span class="sxs-lookup"><span data-stu-id="c7606-150">int</span></span></p></td>
<td><p><span data-ttu-id="c7606-151">Client, der vom registrierten Benutzer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c7606-151">Client used by the user who registered.</span></span> <span data-ttu-id="c7606-152">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c7606-152">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7606-153"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-153"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-154">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="c7606-154">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="c7606-155">Die Kategorie des Clients, der von dem Benutzer verwendet wird, der registriert ist.</span><span class="sxs-lookup"><span data-stu-id="c7606-155">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7606-156"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-156"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-157">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c7606-157">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c7606-158">IP-Adresse, mit der der Benutzer registriert hat.</span><span class="sxs-lookup"><span data-stu-id="c7606-158">IP Address the user registered with.</span></span> <span data-ttu-id="c7606-159">Hierbei kann es sich um eine IPv4-oder IPv6-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="c7606-159">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7606-160"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-160"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-161">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="c7606-161">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="c7606-162">SIP-Dialog-ID.</span><span class="sxs-lookup"><span data-stu-id="c7606-162">SIP dialog ID.</span></span> <span data-ttu-id="c7606-163">Das Format von ist:</span><span class="sxs-lookup"><span data-stu-id="c7606-163">The format of the is:</span></span></p>
<p><span data-ttu-id="c7606-164">Dialogfeld; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="c7606-164">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7606-165"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-165"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-166">int</span><span class="sxs-lookup"><span data-stu-id="c7606-166">int</span></span></p></td>
<td><p><span data-ttu-id="c7606-p109">SIP-Antwortcode auf die Sitzungseinladung. Dieses Feld wird typischerweise mit Daten aufgefüllt, die von der ersten INVITE-Nachricht in der Sitzung generiert werden. Ist keine INVITE-Nachricht vorhanden, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht (BYE, CANCEL, MESSAGE oder INFO) aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="c7606-p109">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7606-170"><strong>Diagnose-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-170"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-171">int</span><span class="sxs-lookup"><span data-stu-id="c7606-171">int</span></span></p></td>
<td><p><span data-ttu-id="c7606-172">Vom SIP-Header erfasste Diagnose-ID.</span><span class="sxs-lookup"><span data-stu-id="c7606-172">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7606-173"><strong>Registrierungsstelle</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-173"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c7606-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c7606-175">FQDN der Registrierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="c7606-175">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7606-176"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-176"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-177">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c7606-177">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c7606-178">Vollqualifizierter Domänenname des Pools, der die Daten für die Sitzung erfasst hat.</span><span class="sxs-lookup"><span data-stu-id="c7606-178">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7606-179"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-179"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-180">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c7606-180">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c7606-181">Der FQDN des Edgeserver, der von dem Benutzer verwendet wird, der registriert ist.</span><span class="sxs-lookup"><span data-stu-id="c7606-181">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7606-182"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-182"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-183">Bit</span><span class="sxs-lookup"><span data-stu-id="c7606-183">bit</span></span></p></td>
<td><p><span data-ttu-id="c7606-184">Gibt an, ob sich der Benutzer aus dem internen Netzwerk angemeldet hat.</span><span class="sxs-lookup"><span data-stu-id="c7606-184">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7606-185"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-185"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-186">Bit</span><span class="sxs-lookup"><span data-stu-id="c7606-186">bit</span></span></p></td>
<td><p><span data-ttu-id="c7606-187">Gibt an, ob das UserService zum Zeitpunkt der Registrierung verfügbar war.</span><span class="sxs-lookup"><span data-stu-id="c7606-187">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7606-188"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-188"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-189">Bit</span><span class="sxs-lookup"><span data-stu-id="c7606-189">bit</span></span></p></td>
<td><p><span data-ttu-id="c7606-190">Gibt an, ob die Registrierung bei der primären Registrierungsstelle erfolgte.</span><span class="sxs-lookup"><span data-stu-id="c7606-190">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7606-191"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-191"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-192">bigint</span><span class="sxs-lookup"><span data-stu-id="c7606-192">bigint</span></span></p></td>
<td><p><span data-ttu-id="c7606-193">Mac-Adresse des registrierten Geräts.</span><span class="sxs-lookup"><span data-stu-id="c7606-193">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7606-194"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-194"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c7606-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c7606-196">Hersteller des registrierten Geräts.</span><span class="sxs-lookup"><span data-stu-id="c7606-196">Manufacturer of the device registered.</span></span> <span data-ttu-id="c7606-197">Weitere Informationen finden Sie <a href="lync-server-2013-manufacturers-table.md">in der Tabelle Hersteller in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c7606-197">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7606-198"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="c7606-198"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="c7606-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c7606-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c7606-200">Hardware Version des registrierten Geräts.</span><span class="sxs-lookup"><span data-stu-id="c7606-200">Hardware version of the device registered.</span></span> <span data-ttu-id="c7606-201">Weitere Informationen finden Sie <a href="lync-server-2013-hardwareversions-table.md">in der Hardware Versions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c7606-201">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

