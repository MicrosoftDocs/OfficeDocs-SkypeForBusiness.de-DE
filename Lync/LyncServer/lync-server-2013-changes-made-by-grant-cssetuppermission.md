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
ms.openlocfilehash: 9d82b896f1d6d1da1184bfa61d7352c9b4803a03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="9f952-102">Von Grant-CsSetupPermission in lync Server 2013 vorgenommene Änderungen</span><span class="sxs-lookup"><span data-stu-id="9f952-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f952-103">_**Letztes Änderungsdatum des Themas:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="9f952-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="9f952-104">Zum Delegieren von Setup können Sie der universellen RTCUniversalServerAdmins-Gruppe Berechtigungen für eine bestimmte Active Directory-Organisationseinheit erteilen, sodass Mitglieder der RTCUniversalServerAdmins-Gruppe in dieser OU lync Server 2013 im angegebenen Domäne, ohne Mitglieder der Gruppe "Domänen-Admins" zu sein.</span><span class="sxs-lookup"><span data-stu-id="9f952-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="9f952-105">Das Cmdlet **Grant-CsSetupPermission** gewährt der RTCUniversalServerAdmins-Gruppe Berechtigungen für eine OU, wie in der folgenden Tabelle angegeben:</span><span class="sxs-lookup"><span data-stu-id="9f952-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="9f952-106">Berechtigungen, die Objekten in der Organisationseinheit gewährt werden</span><span class="sxs-lookup"><span data-stu-id="9f952-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f952-107">Berechtigungen gelten für:</span><span class="sxs-lookup"><span data-stu-id="9f952-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="9f952-108">Gewährte Berechtigungen sind:</span><span class="sxs-lookup"><span data-stu-id="9f952-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f952-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9f952-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="9f952-110">Spezieller Zugriff:</span><span class="sxs-lookup"><span data-stu-id="9f952-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="9f952-111">Lesen von servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="9f952-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="9f952-112">Schreiben von servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="9f952-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="9f952-113">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="9f952-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="9f952-114">Replizieren von Verzeichnisänderungen</span><span class="sxs-lookup"><span data-stu-id="9f952-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f952-115">Nachfolger serviceConnectionPoint-Objekte</span><span class="sxs-lookup"><span data-stu-id="9f952-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="9f952-116">Spezieller Zugriff:</span><span class="sxs-lookup"><span data-stu-id="9f952-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="9f952-117">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="9f952-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="9f952-118">Schreibberechtigungen</span><span class="sxs-lookup"><span data-stu-id="9f952-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="9f952-119">Erstellen eines untergeordneten Elements</span><span class="sxs-lookup"><span data-stu-id="9f952-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="9f952-120">Untergeordnetes Element löschen</span><span class="sxs-lookup"><span data-stu-id="9f952-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="9f952-121">Listeninhalt</span><span class="sxs-lookup"><span data-stu-id="9f952-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="9f952-122">Write-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9f952-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="9f952-123">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9f952-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="9f952-124">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="9f952-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f952-125">NachfolgerAttribut msRTCSIP-Server Objekte</span><span class="sxs-lookup"><span data-stu-id="9f952-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="9f952-126">Spezieller Zugriff:</span><span class="sxs-lookup"><span data-stu-id="9f952-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="9f952-127">Write-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9f952-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="9f952-128">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9f952-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="9f952-129">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="9f952-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f952-130">NachfolgerAttribut msRTCSIP – Webkomponenten Objekte</span><span class="sxs-lookup"><span data-stu-id="9f952-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="9f952-131">Spezieller Zugriff:</span><span class="sxs-lookup"><span data-stu-id="9f952-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="9f952-132">Write-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9f952-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="9f952-133">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9f952-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="9f952-134">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="9f952-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f952-135">NachfolgerAttribut msRTCSIP-MCU-Objekte</span><span class="sxs-lookup"><span data-stu-id="9f952-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="9f952-136">Spezieller Zugriff:</span><span class="sxs-lookup"><span data-stu-id="9f952-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="9f952-137">Write-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9f952-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="9f952-138">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9f952-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="9f952-139">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="9f952-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f952-140">NachfolgerAttribut msRTCSIP-MediationServer-Objekte</span><span class="sxs-lookup"><span data-stu-id="9f952-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="9f952-141">Spezieller Zugriff:</span><span class="sxs-lookup"><span data-stu-id="9f952-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="9f952-142">Write-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9f952-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="9f952-143">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9f952-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="9f952-144">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="9f952-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f952-145">NachfolgerAttribut msRTCSIP-ApplicationServer-Objekte</span><span class="sxs-lookup"><span data-stu-id="9f952-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="9f952-146">Spezieller Zugriff:</span><span class="sxs-lookup"><span data-stu-id="9f952-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="9f952-147">Write-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9f952-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="9f952-148">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9f952-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="9f952-149">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="9f952-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f952-150">NachfolgerAttribut msRTCSIP-ConnectionPoint-Objekte</span><span class="sxs-lookup"><span data-stu-id="9f952-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="9f952-151">Spezieller Zugriff:</span><span class="sxs-lookup"><span data-stu-id="9f952-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="9f952-152">Write-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9f952-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="9f952-153">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9f952-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="9f952-154">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="9f952-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f952-155">Nachfolger Computer Objekte</span><span class="sxs-lookup"><span data-stu-id="9f952-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="9f952-156">Spezieller Zugriff für serviceConnectionPoint:</span><span class="sxs-lookup"><span data-stu-id="9f952-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="9f952-157">Erstellen von untergeordneten Objekten</span><span class="sxs-lookup"><span data-stu-id="9f952-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="9f952-158">Löschen von untergeordneten Objekten</span><span class="sxs-lookup"><span data-stu-id="9f952-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="9f952-159">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="9f952-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="9f952-160">Spezieller Zugriff für öffentliche Informationen:</span><span class="sxs-lookup"><span data-stu-id="9f952-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="9f952-161">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9f952-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="9f952-162">Spezieller Zugriff auf den DNS-Hostname:</span><span class="sxs-lookup"><span data-stu-id="9f952-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="9f952-163">Read-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9f952-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

