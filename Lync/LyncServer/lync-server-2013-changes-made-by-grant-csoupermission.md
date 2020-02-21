---
title: 'Lync Server 2013: von Grant-CsOUPermission vorgenommene Änderungen'
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
ms.openlocfilehash: 6143310797c7372a30665cd380d7fb07340ebaf9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="39287-102">Von Grant-CsOUPermission vorgenommene Änderungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39287-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39287-103">_**Letztes Änderungsstand des Themas:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="39287-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="39287-104">Um lync Server 2013 Verwaltung zu delegieren, können Sie Berechtigungen zu bestimmten Organisationseinheiten (Organizational Units, OUs) hinzufügen, sodass Mitglieder der von der Gesamtstrukturvorbereitung erstellten RTC-universellen Gruppen auf die OUs zugreifen können, ohne Mitglieder der Gruppe "Domänen-Admins" zu sein.</span><span class="sxs-lookup"><span data-stu-id="39287-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="39287-105">Mit dem **Grant-CsOuPermission**-Cmdlet werden Objekten in der angegebenen Organisationseinheit Berechtigungen gemäß der folgenden Tabellen erteilt.</span><span class="sxs-lookup"><span data-stu-id="39287-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="39287-106">Erteilen von Berechtigungen für User-Objekte</span><span class="sxs-lookup"><span data-stu-id="39287-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="39287-107">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Benutzerobjekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="39287-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="39287-108">Für User-Objekte erteilte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="39287-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39287-109">Group</span><span class="sxs-lookup"><span data-stu-id="39287-109">Group</span></span></th>
<th><span data-ttu-id="39287-110">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="39287-110">Permission</span></span></th>
<th><span data-ttu-id="39287-111">Geltungsbereich</span><span class="sxs-lookup"><span data-stu-id="39287-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39287-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="39287-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="39287-113">Verzeichnisänderungen replizieren</span><span class="sxs-lookup"><span data-stu-id="39287-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="39287-114">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="39287-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39287-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="39287-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="39287-116">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="39287-116">List contents</span></span></p>
<p><span data-ttu-id="39287-117">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="39287-117">Read all properties</span></span></p>
<p><span data-ttu-id="39287-118">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="39287-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="39287-119">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="39287-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39287-120">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="39287-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="39287-121">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="39287-121">List contents</span></span></p>
<p><span data-ttu-id="39287-122">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="39287-122">Read all properties</span></span></p>
<p><span data-ttu-id="39287-123">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="39287-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="39287-124">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="39287-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39287-125">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="39287-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="39287-126">Read RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="39287-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="39287-127">Read RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="39287-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="39287-128">Read RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="39287-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="39287-129">Read Public-Information</span><span class="sxs-lookup"><span data-stu-id="39287-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="39287-130">Read General-Information</span><span class="sxs-lookup"><span data-stu-id="39287-130">Read General-Information</span></span></p>
<p><span data-ttu-id="39287-131">Read User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="39287-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="39287-132">Untergeordnete User-Objekte</span><span class="sxs-lookup"><span data-stu-id="39287-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39287-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="39287-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="39287-134">Write RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="39287-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="39287-135">Write msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="39287-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="39287-136">Write RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="39287-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="39287-137">Write RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="39287-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="39287-138">Write proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="39287-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="39287-139">Untergeordnete User-Objekte</span><span class="sxs-lookup"><span data-stu-id="39287-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="39287-140">Erteilen von Berechtigungen für Computer-Objekte</span><span class="sxs-lookup"><span data-stu-id="39287-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="39287-141">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Computer Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="39287-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="39287-142">Für Computer-Objekte erteilte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="39287-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39287-143">Group</span><span class="sxs-lookup"><span data-stu-id="39287-143">Group</span></span></th>
<th><span data-ttu-id="39287-144">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="39287-144">Permission</span></span></th>
<th><span data-ttu-id="39287-145">Geltungsbereich</span><span class="sxs-lookup"><span data-stu-id="39287-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39287-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="39287-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="39287-147">Verzeichnisänderungen replizieren</span><span class="sxs-lookup"><span data-stu-id="39287-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="39287-148">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="39287-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39287-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="39287-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="39287-150">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="39287-150">List contents</span></span></p>
<p><span data-ttu-id="39287-151">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="39287-151">Read all properties</span></span></p>
<p><span data-ttu-id="39287-152">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="39287-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="39287-153">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="39287-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39287-154">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="39287-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="39287-155">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="39287-155">List contents</span></span></p>
<p><span data-ttu-id="39287-156">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="39287-156">Read all properties</span></span></p>
<p><span data-ttu-id="39287-157">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="39287-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="39287-158">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="39287-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39287-159">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="39287-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="39287-160">Read Public-Information</span><span class="sxs-lookup"><span data-stu-id="39287-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="39287-161">Read Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="39287-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="39287-162">Untergeordnete Computer-Objekte</span><span class="sxs-lookup"><span data-stu-id="39287-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39287-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="39287-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="39287-164">Read Public-Information</span><span class="sxs-lookup"><span data-stu-id="39287-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="39287-165">Read Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="39287-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="39287-166">Untergeordnete Computer-Objekte</span><span class="sxs-lookup"><span data-stu-id="39287-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="39287-167">Erteilen von Berechtigungen für Contact oder AppContact-Objekte</span><span class="sxs-lookup"><span data-stu-id="39287-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="39287-168">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Contact-Objekte oder AppContact-Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="39287-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="39287-169">Für Contact- oder AppContact-Objekte erteilte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="39287-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39287-170">Group</span><span class="sxs-lookup"><span data-stu-id="39287-170">Group</span></span></th>
<th><span data-ttu-id="39287-171">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="39287-171">Permission</span></span></th>
<th><span data-ttu-id="39287-172">Geltungsbereich</span><span class="sxs-lookup"><span data-stu-id="39287-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39287-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="39287-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="39287-174">Verzeichnisänderungen replizieren</span><span class="sxs-lookup"><span data-stu-id="39287-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="39287-175">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="39287-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39287-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="39287-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="39287-177">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="39287-177">List contents</span></span></p>
<p><span data-ttu-id="39287-178">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="39287-178">Read all properties</span></span></p>
<p><span data-ttu-id="39287-179">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="39287-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="39287-180">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="39287-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39287-181">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="39287-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="39287-182">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="39287-182">List contents</span></span></p>
<p><span data-ttu-id="39287-183">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="39287-183">Read all properties</span></span></p>
<p><span data-ttu-id="39287-184">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="39287-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="39287-185">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="39287-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39287-186">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="39287-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="39287-187">Read RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="39287-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="39287-188">Read RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="39287-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="39287-189">Read RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="39287-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="39287-190">Read Public-Information</span><span class="sxs-lookup"><span data-stu-id="39287-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="39287-191">Read General-Information</span><span class="sxs-lookup"><span data-stu-id="39287-191">Read General-Information</span></span></p>
<p><span data-ttu-id="39287-192">Read Personal-Information</span><span class="sxs-lookup"><span data-stu-id="39287-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="39287-193">Read User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="39287-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="39287-194">Untergeordnete Contact-Objekte</span><span class="sxs-lookup"><span data-stu-id="39287-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39287-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="39287-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="39287-196">Write RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="39287-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="39287-197">Write otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="39287-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="39287-198">Write displayName</span><span class="sxs-lookup"><span data-stu-id="39287-198">Write displayName</span></span></p>
<p><span data-ttu-id="39287-199">Write description</span><span class="sxs-lookup"><span data-stu-id="39287-199">Write description</span></span></p>
<p><span data-ttu-id="39287-200">Write telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="39287-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="39287-201">Write msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="39287-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="39287-202">Write RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="39287-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="39287-203">Write RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="39287-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="39287-204">Write proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="39287-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="39287-205">Untergeordnete Contact-Objekte</span><span class="sxs-lookup"><span data-stu-id="39287-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="39287-206">Erteilen von Berechtigungen für Device-Objekte</span><span class="sxs-lookup"><span data-stu-id="39287-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="39287-207">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Device-Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="39287-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="39287-208">Für Device-Objekte erteilte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="39287-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39287-209">Group</span><span class="sxs-lookup"><span data-stu-id="39287-209">Group</span></span></th>
<th><span data-ttu-id="39287-210">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="39287-210">Permission</span></span></th>
<th><span data-ttu-id="39287-211">Geltungsbereich</span><span class="sxs-lookup"><span data-stu-id="39287-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39287-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="39287-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="39287-213">Verzeichnisänderungen replizieren</span><span class="sxs-lookup"><span data-stu-id="39287-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="39287-214">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="39287-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39287-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="39287-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="39287-216">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="39287-216">List contents</span></span></p>
<p><span data-ttu-id="39287-217">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="39287-217">Read all properties</span></span></p>
<p><span data-ttu-id="39287-218">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="39287-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="39287-219">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="39287-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39287-220">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="39287-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="39287-221">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="39287-221">List contents</span></span></p>
<p><span data-ttu-id="39287-222">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="39287-222">Read all properties</span></span></p>
<p><span data-ttu-id="39287-223">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="39287-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="39287-224">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="39287-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39287-225">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="39287-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="39287-226">Read RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="39287-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="39287-227">Read RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="39287-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="39287-228">Read RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="39287-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="39287-229">Read Public-Information</span><span class="sxs-lookup"><span data-stu-id="39287-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="39287-230">Read Personal-Information</span><span class="sxs-lookup"><span data-stu-id="39287-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="39287-231">Read General-Information</span><span class="sxs-lookup"><span data-stu-id="39287-231">Read General-Information</span></span></p>
<p><span data-ttu-id="39287-232">Read User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="39287-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="39287-233">Untergeordnete Contact-Objekte</span><span class="sxs-lookup"><span data-stu-id="39287-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39287-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="39287-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="39287-235">Untergeordnetes Element erstellen</span><span class="sxs-lookup"><span data-stu-id="39287-235">Create child</span></span></p>
<p><span data-ttu-id="39287-236">Untergeordnetes Element löschen</span><span class="sxs-lookup"><span data-stu-id="39287-236">Delete child</span></span></p>
<p><span data-ttu-id="39287-237">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="39287-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="39287-238">Kontakt</span><span class="sxs-lookup"><span data-stu-id="39287-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39287-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="39287-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="39287-240">Write displayName</span><span class="sxs-lookup"><span data-stu-id="39287-240">Write displayName</span></span></p>
<p><span data-ttu-id="39287-241">Write description</span><span class="sxs-lookup"><span data-stu-id="39287-241">Write description</span></span></p>
<p><span data-ttu-id="39287-242">Write telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="39287-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="39287-243">Untergeordnete User-Objekte</span><span class="sxs-lookup"><span data-stu-id="39287-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39287-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="39287-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="39287-245">Write RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="39287-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="39287-246">Write otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="39287-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="39287-247">Write displayName</span><span class="sxs-lookup"><span data-stu-id="39287-247">Write displayName</span></span></p>
<p><span data-ttu-id="39287-248">Write description</span><span class="sxs-lookup"><span data-stu-id="39287-248">Write description</span></span></p>
<p><span data-ttu-id="39287-249">Write telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="39287-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="39287-250">Write msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="39287-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="39287-251">Write RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="39287-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="39287-252">Write RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="39287-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="39287-253">Write proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="39287-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="39287-254">Untergeordnete Contact-Objekte</span><span class="sxs-lookup"><span data-stu-id="39287-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="39287-255">Erteilen von Berechtigungen für InetOrgPerson-Objekte</span><span class="sxs-lookup"><span data-stu-id="39287-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="39287-256">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für InetOrgPerson-Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="39287-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="39287-257">Für InetOrgPerson-Objekte erteilte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="39287-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39287-258">Group</span><span class="sxs-lookup"><span data-stu-id="39287-258">Group</span></span></th>
<th><span data-ttu-id="39287-259">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="39287-259">Permission</span></span></th>
<th><span data-ttu-id="39287-260">Geltungsbereich</span><span class="sxs-lookup"><span data-stu-id="39287-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39287-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="39287-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="39287-262">Verzeichnisänderungen replizieren</span><span class="sxs-lookup"><span data-stu-id="39287-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="39287-263">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="39287-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39287-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="39287-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="39287-265">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="39287-265">List contents</span></span></p>
<p><span data-ttu-id="39287-266">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="39287-266">Read all properties</span></span></p>
<p><span data-ttu-id="39287-267">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="39287-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="39287-268">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="39287-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39287-269">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="39287-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="39287-270">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="39287-270">List contents</span></span></p>
<p><span data-ttu-id="39287-271">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="39287-271">Read all properties</span></span></p>
<p><span data-ttu-id="39287-272">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="39287-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="39287-273">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="39287-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39287-274">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="39287-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="39287-275">Read RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="39287-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="39287-276">Read RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="39287-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="39287-277">Read RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="39287-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="39287-278">Read Personal-Information</span><span class="sxs-lookup"><span data-stu-id="39287-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="39287-279">Read Public-Information</span><span class="sxs-lookup"><span data-stu-id="39287-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="39287-280">Read General-Information</span><span class="sxs-lookup"><span data-stu-id="39287-280">Read General-Information</span></span></p>
<p><span data-ttu-id="39287-281">Read User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="39287-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="39287-282">Untergeordnete inetOrgPerson-Objekte</span><span class="sxs-lookup"><span data-stu-id="39287-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39287-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="39287-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="39287-284">Write RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="39287-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="39287-285">Write RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="39287-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="39287-286">Write RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="39287-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="39287-287">Write proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="39287-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="39287-288">Untergeordnete inetOrgPerson-Objekte</span><span class="sxs-lookup"><span data-stu-id="39287-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

