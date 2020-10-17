---
title: 'Lync Server 2013: von Grant-CsOUPermission vorgenommene Änderungen'
description: 'Lync Server 2013: Änderungen, die von Grant-CsOUPermission vorgenommen wurden.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10d3db0e9dde380628690bc016e2b4bd2ec85b54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543611"
---
# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="10075-103">Von Grant-CsOUPermission in lync Server 2013 vorgenommene Änderungen</span><span class="sxs-lookup"><span data-stu-id="10075-103">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10075-104">_**Letztes Änderungsstand des Themas:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="10075-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="10075-105">Um lync Server 2013 Verwaltung zu delegieren, können Sie Berechtigungen zu bestimmten Organisationseinheiten (Organizational Units, OUs) hinzufügen, sodass Mitglieder der von der Gesamtstrukturvorbereitung erstellten RTC-universellen Gruppen auf die OUs zugreifen können, ohne Mitglieder der Gruppe "Domänen-Admins" zu sein.</span><span class="sxs-lookup"><span data-stu-id="10075-105">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="10075-106">Mit dem **Grant-CsOuPermission**-Cmdlet werden Objekten in der angegebenen Organisationseinheit Berechtigungen gemäß der folgenden Tabellen erteilt.</span><span class="sxs-lookup"><span data-stu-id="10075-106">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="10075-107">Erteilen von Berechtigungen für User-Objekte</span><span class="sxs-lookup"><span data-stu-id="10075-107">Granting Permission for User Objects</span></span>

<span data-ttu-id="10075-108">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Benutzerobjekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="10075-108">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="10075-109">Für User-Objekte erteilte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="10075-109">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10075-110">Gruppe</span><span class="sxs-lookup"><span data-stu-id="10075-110">Group</span></span></th>
<th><span data-ttu-id="10075-111">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="10075-111">Permission</span></span></th>
<th><span data-ttu-id="10075-112">Geltungsbereich</span><span class="sxs-lookup"><span data-stu-id="10075-112">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10075-113">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="10075-113">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="10075-114">Verzeichnisänderungen replizieren</span><span class="sxs-lookup"><span data-stu-id="10075-114">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="10075-115">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="10075-115">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10075-116">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="10075-116">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="10075-117">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="10075-117">List contents</span></span></p>
<p><span data-ttu-id="10075-118">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="10075-118">Read all properties</span></span></p>
<p><span data-ttu-id="10075-119">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="10075-119">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="10075-120">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="10075-120">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10075-121">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="10075-121">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="10075-122">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="10075-122">List contents</span></span></p>
<p><span data-ttu-id="10075-123">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="10075-123">Read all properties</span></span></p>
<p><span data-ttu-id="10075-124">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="10075-124">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="10075-125">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="10075-125">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10075-126">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="10075-126">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="10075-127">Read RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="10075-127">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="10075-128">Read RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="10075-128">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="10075-129">Read RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="10075-129">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="10075-130">Read Public-Information</span><span class="sxs-lookup"><span data-stu-id="10075-130">Read Public-Information</span></span></p>
<p><span data-ttu-id="10075-131">Read General-Information</span><span class="sxs-lookup"><span data-stu-id="10075-131">Read General-Information</span></span></p>
<p><span data-ttu-id="10075-132">Read User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="10075-132">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="10075-133">Untergeordnete User-Objekte</span><span class="sxs-lookup"><span data-stu-id="10075-133">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10075-134">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="10075-134">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="10075-135">Write RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="10075-135">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="10075-136">Write msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="10075-136">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="10075-137">Write RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="10075-137">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="10075-138">Write RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="10075-138">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="10075-139">Write proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="10075-139">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="10075-140">Untergeordnete User-Objekte</span><span class="sxs-lookup"><span data-stu-id="10075-140">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="10075-141">Erteilen von Berechtigungen für Computer-Objekte</span><span class="sxs-lookup"><span data-stu-id="10075-141">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="10075-142">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Computer Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="10075-142">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="10075-143">Für Computer-Objekte erteilte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="10075-143">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10075-144">Gruppe</span><span class="sxs-lookup"><span data-stu-id="10075-144">Group</span></span></th>
<th><span data-ttu-id="10075-145">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="10075-145">Permission</span></span></th>
<th><span data-ttu-id="10075-146">Geltungsbereich</span><span class="sxs-lookup"><span data-stu-id="10075-146">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10075-147">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="10075-147">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="10075-148">Verzeichnisänderungen replizieren</span><span class="sxs-lookup"><span data-stu-id="10075-148">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="10075-149">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="10075-149">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10075-150">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="10075-150">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="10075-151">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="10075-151">List contents</span></span></p>
<p><span data-ttu-id="10075-152">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="10075-152">Read all properties</span></span></p>
<p><span data-ttu-id="10075-153">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="10075-153">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="10075-154">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="10075-154">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10075-155">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="10075-155">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="10075-156">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="10075-156">List contents</span></span></p>
<p><span data-ttu-id="10075-157">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="10075-157">Read all properties</span></span></p>
<p><span data-ttu-id="10075-158">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="10075-158">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="10075-159">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="10075-159">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10075-160">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="10075-160">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="10075-161">Read Public-Information</span><span class="sxs-lookup"><span data-stu-id="10075-161">Read Public-Information</span></span></p>
<p><span data-ttu-id="10075-162">Read Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="10075-162">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="10075-163">Untergeordnete Computer-Objekte</span><span class="sxs-lookup"><span data-stu-id="10075-163">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10075-164">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="10075-164">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="10075-165">Read Public-Information</span><span class="sxs-lookup"><span data-stu-id="10075-165">Read Public-Information</span></span></p>
<p><span data-ttu-id="10075-166">Read Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="10075-166">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="10075-167">Untergeordnete Computer-Objekte</span><span class="sxs-lookup"><span data-stu-id="10075-167">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="10075-168">Erteilen von Berechtigungen für Contact oder AppContact-Objekte</span><span class="sxs-lookup"><span data-stu-id="10075-168">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="10075-169">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Contact-Objekte oder AppContact-Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="10075-169">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="10075-170">Für Contact- oder AppContact-Objekte erteilte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="10075-170">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10075-171">Gruppe</span><span class="sxs-lookup"><span data-stu-id="10075-171">Group</span></span></th>
<th><span data-ttu-id="10075-172">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="10075-172">Permission</span></span></th>
<th><span data-ttu-id="10075-173">Geltungsbereich</span><span class="sxs-lookup"><span data-stu-id="10075-173">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10075-174">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="10075-174">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="10075-175">Verzeichnisänderungen replizieren</span><span class="sxs-lookup"><span data-stu-id="10075-175">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="10075-176">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="10075-176">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10075-177">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="10075-177">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="10075-178">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="10075-178">List contents</span></span></p>
<p><span data-ttu-id="10075-179">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="10075-179">Read all properties</span></span></p>
<p><span data-ttu-id="10075-180">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="10075-180">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="10075-181">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="10075-181">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10075-182">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="10075-182">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="10075-183">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="10075-183">List contents</span></span></p>
<p><span data-ttu-id="10075-184">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="10075-184">Read all properties</span></span></p>
<p><span data-ttu-id="10075-185">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="10075-185">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="10075-186">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="10075-186">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10075-187">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="10075-187">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="10075-188">Read RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="10075-188">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="10075-189">Read RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="10075-189">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="10075-190">Read RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="10075-190">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="10075-191">Read Public-Information</span><span class="sxs-lookup"><span data-stu-id="10075-191">Read Public-Information</span></span></p>
<p><span data-ttu-id="10075-192">Read General-Information</span><span class="sxs-lookup"><span data-stu-id="10075-192">Read General-Information</span></span></p>
<p><span data-ttu-id="10075-193">Read Personal-Information</span><span class="sxs-lookup"><span data-stu-id="10075-193">Read Personal-Information</span></span></p>
<p><span data-ttu-id="10075-194">Read User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="10075-194">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="10075-195">Untergeordnete Contact-Objekte</span><span class="sxs-lookup"><span data-stu-id="10075-195">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10075-196">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="10075-196">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="10075-197">Write RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="10075-197">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="10075-198">Write otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="10075-198">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="10075-199">Write displayName</span><span class="sxs-lookup"><span data-stu-id="10075-199">Write displayName</span></span></p>
<p><span data-ttu-id="10075-200">Write description</span><span class="sxs-lookup"><span data-stu-id="10075-200">Write description</span></span></p>
<p><span data-ttu-id="10075-201">Write telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="10075-201">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="10075-202">Write msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="10075-202">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="10075-203">Write RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="10075-203">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="10075-204">Write RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="10075-204">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="10075-205">Write proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="10075-205">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="10075-206">Untergeordnete Contact-Objekte</span><span class="sxs-lookup"><span data-stu-id="10075-206">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="10075-207">Erteilen von Berechtigungen für Device-Objekte</span><span class="sxs-lookup"><span data-stu-id="10075-207">Granting Permission for Device Objects</span></span>

<span data-ttu-id="10075-208">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Device-Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="10075-208">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="10075-209">Für Device-Objekte erteilte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="10075-209">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10075-210">Gruppe</span><span class="sxs-lookup"><span data-stu-id="10075-210">Group</span></span></th>
<th><span data-ttu-id="10075-211">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="10075-211">Permission</span></span></th>
<th><span data-ttu-id="10075-212">Geltungsbereich</span><span class="sxs-lookup"><span data-stu-id="10075-212">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10075-213">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="10075-213">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="10075-214">Verzeichnisänderungen replizieren</span><span class="sxs-lookup"><span data-stu-id="10075-214">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="10075-215">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="10075-215">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10075-216">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="10075-216">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="10075-217">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="10075-217">List contents</span></span></p>
<p><span data-ttu-id="10075-218">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="10075-218">Read all properties</span></span></p>
<p><span data-ttu-id="10075-219">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="10075-219">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="10075-220">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="10075-220">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10075-221">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="10075-221">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="10075-222">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="10075-222">List contents</span></span></p>
<p><span data-ttu-id="10075-223">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="10075-223">Read all properties</span></span></p>
<p><span data-ttu-id="10075-224">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="10075-224">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="10075-225">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="10075-225">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10075-226">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="10075-226">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="10075-227">Read RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="10075-227">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="10075-228">Read RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="10075-228">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="10075-229">Read RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="10075-229">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="10075-230">Read Public-Information</span><span class="sxs-lookup"><span data-stu-id="10075-230">Read Public-Information</span></span></p>
<p><span data-ttu-id="10075-231">Read Personal-Information</span><span class="sxs-lookup"><span data-stu-id="10075-231">Read Personal-Information</span></span></p>
<p><span data-ttu-id="10075-232">Read General-Information</span><span class="sxs-lookup"><span data-stu-id="10075-232">Read General-Information</span></span></p>
<p><span data-ttu-id="10075-233">Read User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="10075-233">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="10075-234">Untergeordnete Contact-Objekte</span><span class="sxs-lookup"><span data-stu-id="10075-234">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10075-235">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="10075-235">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="10075-236">Untergeordnetes Element erstellen</span><span class="sxs-lookup"><span data-stu-id="10075-236">Create child</span></span></p>
<p><span data-ttu-id="10075-237">Untergeordnetes Element löschen</span><span class="sxs-lookup"><span data-stu-id="10075-237">Delete child</span></span></p>
<p><span data-ttu-id="10075-238">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="10075-238">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="10075-239">Kontakt</span><span class="sxs-lookup"><span data-stu-id="10075-239">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10075-240">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="10075-240">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="10075-241">Write displayName</span><span class="sxs-lookup"><span data-stu-id="10075-241">Write displayName</span></span></p>
<p><span data-ttu-id="10075-242">Write description</span><span class="sxs-lookup"><span data-stu-id="10075-242">Write description</span></span></p>
<p><span data-ttu-id="10075-243">Write telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="10075-243">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="10075-244">Untergeordnete User-Objekte</span><span class="sxs-lookup"><span data-stu-id="10075-244">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10075-245">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="10075-245">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="10075-246">Write RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="10075-246">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="10075-247">Write otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="10075-247">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="10075-248">Write displayName</span><span class="sxs-lookup"><span data-stu-id="10075-248">Write displayName</span></span></p>
<p><span data-ttu-id="10075-249">Write description</span><span class="sxs-lookup"><span data-stu-id="10075-249">Write description</span></span></p>
<p><span data-ttu-id="10075-250">Write telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="10075-250">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="10075-251">Write msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="10075-251">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="10075-252">Write RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="10075-252">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="10075-253">Write RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="10075-253">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="10075-254">Write proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="10075-254">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="10075-255">Untergeordnete Contact-Objekte</span><span class="sxs-lookup"><span data-stu-id="10075-255">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="10075-256">Erteilen von Berechtigungen für InetOrgPerson-Objekte</span><span class="sxs-lookup"><span data-stu-id="10075-256">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="10075-257">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für InetOrgPerson-Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="10075-257">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="10075-258">Für InetOrgPerson-Objekte erteilte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="10075-258">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10075-259">Gruppe</span><span class="sxs-lookup"><span data-stu-id="10075-259">Group</span></span></th>
<th><span data-ttu-id="10075-260">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="10075-260">Permission</span></span></th>
<th><span data-ttu-id="10075-261">Geltungsbereich</span><span class="sxs-lookup"><span data-stu-id="10075-261">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10075-262">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="10075-262">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="10075-263">Verzeichnisänderungen replizieren</span><span class="sxs-lookup"><span data-stu-id="10075-263">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="10075-264">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="10075-264">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10075-265">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="10075-265">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="10075-266">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="10075-266">List contents</span></span></p>
<p><span data-ttu-id="10075-267">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="10075-267">Read all properties</span></span></p>
<p><span data-ttu-id="10075-268">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="10075-268">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="10075-269">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="10075-269">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10075-270">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="10075-270">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="10075-271">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="10075-271">List contents</span></span></p>
<p><span data-ttu-id="10075-272">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="10075-272">Read all properties</span></span></p>
<p><span data-ttu-id="10075-273">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="10075-273">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="10075-274">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="10075-274">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10075-275">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="10075-275">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="10075-276">Read RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="10075-276">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="10075-277">Read RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="10075-277">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="10075-278">Read RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="10075-278">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="10075-279">Read Personal-Information</span><span class="sxs-lookup"><span data-stu-id="10075-279">Read Personal-Information</span></span></p>
<p><span data-ttu-id="10075-280">Read Public-Information</span><span class="sxs-lookup"><span data-stu-id="10075-280">Read Public-Information</span></span></p>
<p><span data-ttu-id="10075-281">Read General-Information</span><span class="sxs-lookup"><span data-stu-id="10075-281">Read General-Information</span></span></p>
<p><span data-ttu-id="10075-282">Read User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="10075-282">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="10075-283">Untergeordnete inetOrgPerson-Objekte</span><span class="sxs-lookup"><span data-stu-id="10075-283">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10075-284">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="10075-284">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="10075-285">Write RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="10075-285">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="10075-286">Write RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="10075-286">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="10075-287">Write RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="10075-287">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="10075-288">Write proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="10075-288">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="10075-289">Untergeordnete inetOrgPerson-Objekte</span><span class="sxs-lookup"><span data-stu-id="10075-289">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

