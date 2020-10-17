---
title: 'Lync Server 2013: von Grant-CsSetupPermission vorgenommene Änderungen'
description: 'Lync Server 2013: Änderungen, die von Grant-CsSetupPermission vorgenommen wurden.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2a9156c977c993dd32e38fc6816bd08d3f65c1f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543601"
---
# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="5ee66-103">Von Grant-CsSetupPermission in lync Server 2013 vorgenommene Änderungen</span><span class="sxs-lookup"><span data-stu-id="5ee66-103">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ee66-104">_**Letztes Änderungsstand des Themas:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="5ee66-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="5ee66-105">Um Setup zu delegieren, können Sie der universellen Gruppe RTCUniversalServerAdmins Berechtigungen für eine bestimmte Active Directory Organisationseinheit (Organizational Unit, OU) erteilen, sodass Mitglieder der Gruppe RTCUniversalServerAdmins in dieser Organisationseinheit lync Server 2013 in der angegebenen Domäne ohne Mitgliedschaft in der Gruppe "Domänen-Admins" installieren können.</span><span class="sxs-lookup"><span data-stu-id="5ee66-105">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="5ee66-106">Das **Grant-CsSetupPermission-** Cmdlet erteilt den RTCUniversalServerAdmins-Gruppen Berechtigungen für eine OU, wie in der folgenden Tabelle angegeben:</span><span class="sxs-lookup"><span data-stu-id="5ee66-106">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="5ee66-107">Berechtigungen, die Objekten in der Organisationseinheit erteilt werden</span><span class="sxs-lookup"><span data-stu-id="5ee66-107">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ee66-108">Berechtigungen gelten für:</span><span class="sxs-lookup"><span data-stu-id="5ee66-108">Permissions apply to:</span></span></th>
<th><span data-ttu-id="5ee66-109">Gewährte Berechtigungen sind:</span><span class="sxs-lookup"><span data-stu-id="5ee66-109">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ee66-110">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5ee66-110">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="5ee66-111">Spezieller Zugriff:</span><span class="sxs-lookup"><span data-stu-id="5ee66-111">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="5ee66-112">ServicePrincipalName lesen</span><span class="sxs-lookup"><span data-stu-id="5ee66-112">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="5ee66-113">ServicePrincipalName schreiben</span><span class="sxs-lookup"><span data-stu-id="5ee66-113">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="5ee66-114">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="5ee66-114">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="5ee66-115">Verzeichnisänderungen replizieren</span><span class="sxs-lookup"><span data-stu-id="5ee66-115">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ee66-116">Untergeordnete serviceConnectionPoint-Objekte</span><span class="sxs-lookup"><span data-stu-id="5ee66-116">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="5ee66-117">Spezieller Zugriff:</span><span class="sxs-lookup"><span data-stu-id="5ee66-117">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="5ee66-118">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="5ee66-118">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="5ee66-119">Schreibberechtigungen</span><span class="sxs-lookup"><span data-stu-id="5ee66-119">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="5ee66-120">Untergeordnetes Element erstellen</span><span class="sxs-lookup"><span data-stu-id="5ee66-120">Create child</span></span></p></li>
<li><p><span data-ttu-id="5ee66-121">Untergeordnetes Element löschen</span><span class="sxs-lookup"><span data-stu-id="5ee66-121">Delete child</span></span></p></li>
<li><p><span data-ttu-id="5ee66-122">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="5ee66-122">List contents</span></span></p></li>
<li><p><span data-ttu-id="5ee66-123">Write-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5ee66-123">Write property</span></span></p></li>
<li><p><span data-ttu-id="5ee66-124">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5ee66-124">Read property</span></span></p></li>
<li><p><span data-ttu-id="5ee66-125">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="5ee66-125">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ee66-126">Untergeordnete msRTCSIP-Server Objekte</span><span class="sxs-lookup"><span data-stu-id="5ee66-126">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="5ee66-127">Spezieller Zugriff:</span><span class="sxs-lookup"><span data-stu-id="5ee66-127">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="5ee66-128">Write-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5ee66-128">Write property</span></span></p></li>
<li><p><span data-ttu-id="5ee66-129">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5ee66-129">Read property</span></span></p></li>
<li><p><span data-ttu-id="5ee66-130">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="5ee66-130">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ee66-131">Untergeordnete msRTCSIP-WebComponents-Objekte</span><span class="sxs-lookup"><span data-stu-id="5ee66-131">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="5ee66-132">Spezieller Zugriff:</span><span class="sxs-lookup"><span data-stu-id="5ee66-132">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="5ee66-133">Write-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5ee66-133">Write property</span></span></p></li>
<li><p><span data-ttu-id="5ee66-134">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5ee66-134">Read property</span></span></p></li>
<li><p><span data-ttu-id="5ee66-135">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="5ee66-135">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ee66-136">Untergeordnete msRTCSIP-MCU-Objekte</span><span class="sxs-lookup"><span data-stu-id="5ee66-136">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="5ee66-137">Spezieller Zugriff:</span><span class="sxs-lookup"><span data-stu-id="5ee66-137">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="5ee66-138">Write-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5ee66-138">Write property</span></span></p></li>
<li><p><span data-ttu-id="5ee66-139">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5ee66-139">Read property</span></span></p></li>
<li><p><span data-ttu-id="5ee66-140">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="5ee66-140">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ee66-141">Untergeordnete msRTCSIP-MediationServer-Objekte</span><span class="sxs-lookup"><span data-stu-id="5ee66-141">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="5ee66-142">Spezieller Zugriff:</span><span class="sxs-lookup"><span data-stu-id="5ee66-142">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="5ee66-143">Write-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5ee66-143">Write property</span></span></p></li>
<li><p><span data-ttu-id="5ee66-144">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5ee66-144">Read property</span></span></p></li>
<li><p><span data-ttu-id="5ee66-145">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="5ee66-145">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ee66-146">Untergeordnete msRTCSIP-ApplicationServer-Objekte</span><span class="sxs-lookup"><span data-stu-id="5ee66-146">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="5ee66-147">Spezieller Zugriff:</span><span class="sxs-lookup"><span data-stu-id="5ee66-147">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="5ee66-148">Write-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5ee66-148">Write property</span></span></p></li>
<li><p><span data-ttu-id="5ee66-149">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5ee66-149">Read property</span></span></p></li>
<li><p><span data-ttu-id="5ee66-150">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="5ee66-150">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ee66-151">Untergeordnete msRTCSIP-ConnectionPoint-Objekte</span><span class="sxs-lookup"><span data-stu-id="5ee66-151">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="5ee66-152">Spezieller Zugriff:</span><span class="sxs-lookup"><span data-stu-id="5ee66-152">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="5ee66-153">Write-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5ee66-153">Write property</span></span></p></li>
<li><p><span data-ttu-id="5ee66-154">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5ee66-154">Read property</span></span></p></li>
<li><p><span data-ttu-id="5ee66-155">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="5ee66-155">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ee66-156">Untergeordnete Computer-Objekte</span><span class="sxs-lookup"><span data-stu-id="5ee66-156">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="5ee66-157">Spezieller Zugriff für serviceConnectionPoint:</span><span class="sxs-lookup"><span data-stu-id="5ee66-157">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="5ee66-158">Untergeordnete Objekte erstellen</span><span class="sxs-lookup"><span data-stu-id="5ee66-158">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="5ee66-159">Untergeordnete Objekte löschen</span><span class="sxs-lookup"><span data-stu-id="5ee66-159">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="5ee66-160">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="5ee66-160">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="5ee66-161">Spezieller Zugriff für öffentliche Informationen:</span><span class="sxs-lookup"><span data-stu-id="5ee66-161">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="5ee66-162">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5ee66-162">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="5ee66-163">Spezieller Zugriff für den DNS-Hostnamen:</span><span class="sxs-lookup"><span data-stu-id="5ee66-163">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="5ee66-164">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5ee66-164">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

