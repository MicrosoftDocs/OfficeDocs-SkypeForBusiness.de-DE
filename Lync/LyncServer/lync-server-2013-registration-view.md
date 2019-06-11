---
title: 'Lync Server 2013: Registrierungs Ansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe1b01b748204d3d4365b6f28ae4480d3632b35a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="277dc-102">Registrierungs Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="277dc-102">Registration view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="277dc-103">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="277dc-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="277dc-104">In der Registrierungs Ansicht werden Informationen zur Benutzerregistrierung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="277dc-104">The Registration view stores information about user registration.</span></span> <span data-ttu-id="277dc-105">Diese Ansicht wurde in lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="277dc-105">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="277dc-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="277dc-106">Column</span></span></th>
<th><span data-ttu-id="277dc-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="277dc-107">Data Type</span></span></th>
<th><span data-ttu-id="277dc-108">Details</span><span class="sxs-lookup"><span data-stu-id="277dc-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="277dc-109"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-110">datetime</span><span class="sxs-lookup"><span data-stu-id="277dc-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="277dc-111">Uhrzeit der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="277dc-111">Time of session request.</span></span> <span data-ttu-id="277dc-112">Wird in Verbindung mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="277dc-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="277dc-113">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="277dc-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277dc-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-115">int</span><span class="sxs-lookup"><span data-stu-id="277dc-115">int</span></span></p></td>
<td><p><span data-ttu-id="277dc-116">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="277dc-116">ID number to identify the session.</span></span> <span data-ttu-id="277dc-117">Wird in Verbindung mit SessionID-Mal verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="277dc-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="277dc-118">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="277dc-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277dc-119"><strong>Registrierung</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-119"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-120">datetime</span><span class="sxs-lookup"><span data-stu-id="277dc-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="277dc-121">Zeitpunkt, zu dem die Registrierung erfolgte.</span><span class="sxs-lookup"><span data-stu-id="277dc-121">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277dc-122"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-122"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="277dc-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="277dc-124">URI des registrierten Benutzers.</span><span class="sxs-lookup"><span data-stu-id="277dc-124">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277dc-125"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-125"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="277dc-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="277dc-127">Der Typ des URIs des registrierten Benutzers.</span><span class="sxs-lookup"><span data-stu-id="277dc-127">Type of URI of the user who registered.</span></span> <span data-ttu-id="277dc-128">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="277dc-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277dc-129"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-129"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="277dc-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="277dc-131">Der Mandant des registrierten Benutzers.</span><span class="sxs-lookup"><span data-stu-id="277dc-131">Tenant of the user who registered.</span></span> <span data-ttu-id="277dc-132">Weitere Informationen finden Sie <a href="lync-server-2013-tenants-table.md">in der Tabelle Mandanten in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="277dc-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277dc-133"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-133"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-134">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="277dc-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="277dc-135">Eindeutiger Bezeichner des Endpunkts des Benutzers, bei dem registriert ist.</span><span class="sxs-lookup"><span data-stu-id="277dc-135">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277dc-136"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-136"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-137">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="277dc-137">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="277dc-138">Eindeutiger Bezeichner, der zur Unterscheidung von Registrierungen verwendet wird, die denselben Benutzer und denselben Endpunkt einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="277dc-138">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277dc-139"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-139"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-140">datetime</span><span class="sxs-lookup"><span data-stu-id="277dc-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="277dc-141">Zeitpunkt, zu dem die Registrierung erfolgte.</span><span class="sxs-lookup"><span data-stu-id="277dc-141">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277dc-142"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-142"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-143">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="277dc-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="277dc-144">Grund für die Deregistrierung.</span><span class="sxs-lookup"><span data-stu-id="277dc-144">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277dc-145"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-145"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-146">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="277dc-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="277dc-147">Die Version des Clients, die von dem registrierten Benutzer verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="277dc-147">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277dc-148"><strong>Clienttyp</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-148"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-149">int</span><span class="sxs-lookup"><span data-stu-id="277dc-149">int</span></span></p></td>
<td><p><span data-ttu-id="277dc-150">Der Client, der von dem registrierten Benutzer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="277dc-150">Client used by the user who registered.</span></span> <span data-ttu-id="277dc-151">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="277dc-151">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277dc-152"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-152"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-153">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="277dc-153">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="277dc-154">Die Kategorie des Clients, der von dem registrierten Benutzer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="277dc-154">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277dc-155"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-155"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-156">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="277dc-156">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="277dc-157">Die IP-Adresse, bei der der Benutzer registriert ist.</span><span class="sxs-lookup"><span data-stu-id="277dc-157">IP Address the user registered with.</span></span> <span data-ttu-id="277dc-158">Dies kann eine IPv4-oder IPv6-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="277dc-158">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277dc-159"><strong>Dialogfeld-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-159"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-160">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="277dc-160">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="277dc-161">SIP-Dialogfeld-ID.</span><span class="sxs-lookup"><span data-stu-id="277dc-161">SIP dialog ID.</span></span> <span data-ttu-id="277dc-162">Das Format des is:</span><span class="sxs-lookup"><span data-stu-id="277dc-162">The format of the is:</span></span></p>
<p><span data-ttu-id="277dc-163">Dialogfeld; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="277dc-163">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277dc-164"><strong>Response Code</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-164"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-165">int</span><span class="sxs-lookup"><span data-stu-id="277dc-165">int</span></span></p></td>
<td><p><span data-ttu-id="277dc-166">SIP-Antwortcode für die Sitzungseinladung</span><span class="sxs-lookup"><span data-stu-id="277dc-166">SIP response code to the session invitation.</span></span> <span data-ttu-id="277dc-167">Dieses Feld wird in der Regel von Daten ausgefüllt, die aus der anfänglichen Einladungsnachricht in der Sitzung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="277dc-167">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="277dc-168">Wenn keine Einladungsnachricht vorhanden ist, wird das Feld mit dem Datum und der Uhrzeit der ersten relevanten SIP-Nachricht gefüllt (Bye, Cancel, Nachricht oder info).</span><span class="sxs-lookup"><span data-stu-id="277dc-168">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277dc-169"><strong>Diagnose-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-169"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-170">int</span><span class="sxs-lookup"><span data-stu-id="277dc-170">int</span></span></p></td>
<td><p><span data-ttu-id="277dc-171">Vom SIP-Header erfasste Diagnose-ID.</span><span class="sxs-lookup"><span data-stu-id="277dc-171">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277dc-172"><strong>Registrierungsstelle</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-172"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-173">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="277dc-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="277dc-174">FQDN der Registrierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="277dc-174">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277dc-175"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-175"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-176">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="277dc-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="277dc-177">Der FQDN des Pools, in dem die Daten für die Sitzung erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="277dc-177">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277dc-178"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-178"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-179">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="277dc-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="277dc-180">Der FQDN des Edge-Servers, der von dem registrierten Benutzer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="277dc-180">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277dc-181"><strong>"IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-181"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-182">bit</span><span class="sxs-lookup"><span data-stu-id="277dc-182">bit</span></span></p></td>
<td><p><span data-ttu-id="277dc-183">Gibt an, ob sich der Benutzer vom internen Netzwerk anmeldet.</span><span class="sxs-lookup"><span data-stu-id="277dc-183">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277dc-184"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-184"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-185">bit</span><span class="sxs-lookup"><span data-stu-id="277dc-185">bit</span></span></p></td>
<td><p><span data-ttu-id="277dc-186">Gibt an, ob die UserService zur Registrierungszeit verfügbar war.</span><span class="sxs-lookup"><span data-stu-id="277dc-186">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277dc-187"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-187"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-188">bit</span><span class="sxs-lookup"><span data-stu-id="277dc-188">bit</span></span></p></td>
<td><p><span data-ttu-id="277dc-189">Gibt an, ob die Registrierung bei der primären Registrierungsstelle erfolgte.</span><span class="sxs-lookup"><span data-stu-id="277dc-189">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277dc-190"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-190"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-191">bigint</span><span class="sxs-lookup"><span data-stu-id="277dc-191">bigint</span></span></p></td>
<td><p><span data-ttu-id="277dc-192">Mac-Adresse des registrierten Geräts.</span><span class="sxs-lookup"><span data-stu-id="277dc-192">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="277dc-193"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-193"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="277dc-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="277dc-195">Hersteller des registrierten Geräts.</span><span class="sxs-lookup"><span data-stu-id="277dc-195">Manufacturer of the device registered.</span></span> <span data-ttu-id="277dc-196">Weitere Informationen finden Sie <a href="lync-server-2013-manufacturers-table.md">in der Tabelle "Hersteller" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="277dc-196">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="277dc-197"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="277dc-197"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="277dc-198">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="277dc-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="277dc-199">Hardware Version des registrierten Geräts.</span><span class="sxs-lookup"><span data-stu-id="277dc-199">Hardware version of the device registered.</span></span> <span data-ttu-id="277dc-200">Weitere Informationen finden Sie <a href="lync-server-2013-hardwareversions-table.md">in der HardwareVersions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="277dc-200">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

