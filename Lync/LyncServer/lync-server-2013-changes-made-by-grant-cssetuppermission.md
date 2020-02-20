---
title: 'Lync Server 2013: von Grant-CsSetupPermission vorgenommene Änderungen'
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
ms.openlocfilehash: 12c9431e413428080f72d34510cdb3879e26e7cf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="bd9c0-102">Von Grant-CsSetupPermission vorgenommene Änderungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd9c0-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd9c0-103">_**Letztes Änderungsstand des Themas:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="bd9c0-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="bd9c0-104">Um Setup zu delegieren, können Sie der universellen Gruppe RTCUniversalServerAdmins Berechtigungen für eine bestimmte Active Directory Organisationseinheit (Organizational Unit, OU) erteilen, sodass Mitglieder der Gruppe RTCUniversalServerAdmins in dieser Organisationseinheit lync Server 2013 in der angegebenen Domäne ohne Mitglied der Gruppe "Domänen-Admins" zu sein.</span><span class="sxs-lookup"><span data-stu-id="bd9c0-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="bd9c0-105">Das **Grant-CsSetupPermission-** Cmdlet erteilt den RTCUniversalServerAdmins-Gruppen Berechtigungen für eine OU, wie in der folgenden Tabelle angegeben:</span><span class="sxs-lookup"><span data-stu-id="bd9c0-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="bd9c0-106">Berechtigungen, die Objekten in der Organisationseinheit erteilt werden</span><span class="sxs-lookup"><span data-stu-id="bd9c0-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd9c0-107">Berechtigungen gelten für:</span><span class="sxs-lookup"><span data-stu-id="bd9c0-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="bd9c0-108">Gewährte Berechtigungen sind:</span><span class="sxs-lookup"><span data-stu-id="bd9c0-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd9c0-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="bd9c0-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="bd9c0-110">Spezieller Zugriff:</span><span class="sxs-lookup"><span data-stu-id="bd9c0-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="bd9c0-111">ServicePrincipalName lesen</span><span class="sxs-lookup"><span data-stu-id="bd9c0-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="bd9c0-112">ServicePrincipalName schreiben</span><span class="sxs-lookup"><span data-stu-id="bd9c0-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="bd9c0-113">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="bd9c0-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="bd9c0-114">Verzeichnisänderungen replizieren</span><span class="sxs-lookup"><span data-stu-id="bd9c0-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd9c0-115">Untergeordnete serviceConnectionPoint-Objekte</span><span class="sxs-lookup"><span data-stu-id="bd9c0-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="bd9c0-116">Spezieller Zugriff:</span><span class="sxs-lookup"><span data-stu-id="bd9c0-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="bd9c0-117">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="bd9c0-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="bd9c0-118">Schreibberechtigungen</span><span class="sxs-lookup"><span data-stu-id="bd9c0-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="bd9c0-119">Untergeordnetes Element erstellen</span><span class="sxs-lookup"><span data-stu-id="bd9c0-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="bd9c0-120">Untergeordnetes Element löschen</span><span class="sxs-lookup"><span data-stu-id="bd9c0-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="bd9c0-121">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="bd9c0-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="bd9c0-122">Write-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bd9c0-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="bd9c0-123">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bd9c0-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="bd9c0-124">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="bd9c0-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd9c0-125">Untergeordnete msRTCSIP-Server Objekte</span><span class="sxs-lookup"><span data-stu-id="bd9c0-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="bd9c0-126">Spezieller Zugriff:</span><span class="sxs-lookup"><span data-stu-id="bd9c0-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="bd9c0-127">Write-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bd9c0-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="bd9c0-128">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bd9c0-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="bd9c0-129">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="bd9c0-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd9c0-130">Untergeordnete msRTCSIP-WebComponents-Objekte</span><span class="sxs-lookup"><span data-stu-id="bd9c0-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="bd9c0-131">Spezieller Zugriff:</span><span class="sxs-lookup"><span data-stu-id="bd9c0-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="bd9c0-132">Write-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bd9c0-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="bd9c0-133">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bd9c0-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="bd9c0-134">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="bd9c0-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd9c0-135">Untergeordnete msRTCSIP-MCU-Objekte</span><span class="sxs-lookup"><span data-stu-id="bd9c0-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="bd9c0-136">Spezieller Zugriff:</span><span class="sxs-lookup"><span data-stu-id="bd9c0-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="bd9c0-137">Write-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bd9c0-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="bd9c0-138">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bd9c0-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="bd9c0-139">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="bd9c0-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd9c0-140">Untergeordnete msRTCSIP-MediationServer-Objekte</span><span class="sxs-lookup"><span data-stu-id="bd9c0-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="bd9c0-141">Spezieller Zugriff:</span><span class="sxs-lookup"><span data-stu-id="bd9c0-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="bd9c0-142">Write-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bd9c0-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="bd9c0-143">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bd9c0-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="bd9c0-144">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="bd9c0-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd9c0-145">Untergeordnete msRTCSIP-ApplicationServer-Objekte</span><span class="sxs-lookup"><span data-stu-id="bd9c0-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="bd9c0-146">Spezieller Zugriff:</span><span class="sxs-lookup"><span data-stu-id="bd9c0-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="bd9c0-147">Write-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bd9c0-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="bd9c0-148">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bd9c0-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="bd9c0-149">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="bd9c0-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd9c0-150">Untergeordnete msRTCSIP-ConnectionPoint-Objekte</span><span class="sxs-lookup"><span data-stu-id="bd9c0-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="bd9c0-151">Spezieller Zugriff:</span><span class="sxs-lookup"><span data-stu-id="bd9c0-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="bd9c0-152">Write-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bd9c0-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="bd9c0-153">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bd9c0-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="bd9c0-154">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="bd9c0-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd9c0-155">Untergeordnete Computer-Objekte</span><span class="sxs-lookup"><span data-stu-id="bd9c0-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="bd9c0-156">Spezieller Zugriff für serviceConnectionPoint:</span><span class="sxs-lookup"><span data-stu-id="bd9c0-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="bd9c0-157">Untergeordnete Objekte erstellen</span><span class="sxs-lookup"><span data-stu-id="bd9c0-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="bd9c0-158">Untergeordnete Objekte löschen</span><span class="sxs-lookup"><span data-stu-id="bd9c0-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="bd9c0-159">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="bd9c0-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="bd9c0-160">Spezieller Zugriff für öffentliche Informationen:</span><span class="sxs-lookup"><span data-stu-id="bd9c0-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="bd9c0-161">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bd9c0-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="bd9c0-162">Spezieller Zugriff für den DNS-Hostnamen:</span><span class="sxs-lookup"><span data-stu-id="bd9c0-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="bd9c0-163">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bd9c0-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

