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
ms.openlocfilehash: c64c11ba999763a44105a68502e53fc4889af305
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="06997-102">Von Grant-CsOUPermission vorgenommene Änderungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06997-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06997-103">_**Letztes Änderungsstand des Themas:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="06997-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="06997-104">Um lync Server 2013 Verwaltung zu delegieren, können Sie Berechtigungen zu bestimmten Organisationseinheiten (Organizational Units, OUs) hinzufügen, sodass Mitglieder der von der Gesamtstrukturvorbereitung erstellten RTC-universellen Gruppen auf die OUs zugreifen können, ohne Mitglieder der Gruppe "Domänen-Admins" zu sein.</span><span class="sxs-lookup"><span data-stu-id="06997-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="06997-105">Mit dem **Grant-CsOuPermission**-Cmdlet werden Objekten in der angegebenen Organisationseinheit Berechtigungen gemäß der folgenden Tabellen erteilt.</span><span class="sxs-lookup"><span data-stu-id="06997-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="06997-106">Erteilen von Berechtigungen für User-Objekte</span><span class="sxs-lookup"><span data-stu-id="06997-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="06997-107">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Benutzerobjekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="06997-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="06997-108">Für User-Objekte erteilte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="06997-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06997-109">Group</span><span class="sxs-lookup"><span data-stu-id="06997-109">Group</span></span></th>
<th><span data-ttu-id="06997-110">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="06997-110">Permission</span></span></th>
<th><span data-ttu-id="06997-111">Geltungsbereich</span><span class="sxs-lookup"><span data-stu-id="06997-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06997-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="06997-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="06997-113">Verzeichnisänderungen replizieren</span><span class="sxs-lookup"><span data-stu-id="06997-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="06997-114">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="06997-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06997-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="06997-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="06997-116">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="06997-116">List contents</span></span></p>
<p><span data-ttu-id="06997-117">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="06997-117">Read all properties</span></span></p>
<p><span data-ttu-id="06997-118">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="06997-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="06997-119">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="06997-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06997-120">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="06997-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="06997-121">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="06997-121">List contents</span></span></p>
<p><span data-ttu-id="06997-122">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="06997-122">Read all properties</span></span></p>
<p><span data-ttu-id="06997-123">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="06997-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="06997-124">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="06997-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06997-125">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="06997-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="06997-126">Read RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="06997-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="06997-127">Read RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="06997-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="06997-128">Read RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="06997-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="06997-129">Read Public-Information</span><span class="sxs-lookup"><span data-stu-id="06997-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="06997-130">Read General-Information</span><span class="sxs-lookup"><span data-stu-id="06997-130">Read General-Information</span></span></p>
<p><span data-ttu-id="06997-131">Read User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="06997-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="06997-132">Untergeordnete User-Objekte</span><span class="sxs-lookup"><span data-stu-id="06997-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06997-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="06997-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="06997-134">Write RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="06997-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="06997-135">Write msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="06997-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="06997-136">Write RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="06997-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="06997-137">Write RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="06997-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="06997-138">Write proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="06997-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="06997-139">Untergeordnete User-Objekte</span><span class="sxs-lookup"><span data-stu-id="06997-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="06997-140">Erteilen von Berechtigungen für Computer-Objekte</span><span class="sxs-lookup"><span data-stu-id="06997-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="06997-141">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Computer Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="06997-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="06997-142">Für Computer-Objekte erteilte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="06997-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06997-143">Group</span><span class="sxs-lookup"><span data-stu-id="06997-143">Group</span></span></th>
<th><span data-ttu-id="06997-144">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="06997-144">Permission</span></span></th>
<th><span data-ttu-id="06997-145">Geltungsbereich</span><span class="sxs-lookup"><span data-stu-id="06997-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06997-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="06997-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="06997-147">Verzeichnisänderungen replizieren</span><span class="sxs-lookup"><span data-stu-id="06997-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="06997-148">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="06997-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06997-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="06997-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="06997-150">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="06997-150">List contents</span></span></p>
<p><span data-ttu-id="06997-151">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="06997-151">Read all properties</span></span></p>
<p><span data-ttu-id="06997-152">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="06997-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="06997-153">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="06997-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06997-154">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="06997-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="06997-155">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="06997-155">List contents</span></span></p>
<p><span data-ttu-id="06997-156">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="06997-156">Read all properties</span></span></p>
<p><span data-ttu-id="06997-157">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="06997-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="06997-158">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="06997-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06997-159">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="06997-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="06997-160">Read Public-Information</span><span class="sxs-lookup"><span data-stu-id="06997-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="06997-161">Read Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="06997-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="06997-162">Untergeordnete Computer-Objekte</span><span class="sxs-lookup"><span data-stu-id="06997-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06997-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="06997-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="06997-164">Read Public-Information</span><span class="sxs-lookup"><span data-stu-id="06997-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="06997-165">Read Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="06997-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="06997-166">Untergeordnete Computer-Objekte</span><span class="sxs-lookup"><span data-stu-id="06997-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="06997-167">Erteilen von Berechtigungen für Contact oder AppContact-Objekte</span><span class="sxs-lookup"><span data-stu-id="06997-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="06997-168">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Contact-Objekte oder AppContact-Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="06997-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="06997-169">Für Contact- oder AppContact-Objekte erteilte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="06997-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06997-170">Group</span><span class="sxs-lookup"><span data-stu-id="06997-170">Group</span></span></th>
<th><span data-ttu-id="06997-171">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="06997-171">Permission</span></span></th>
<th><span data-ttu-id="06997-172">Geltungsbereich</span><span class="sxs-lookup"><span data-stu-id="06997-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06997-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="06997-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="06997-174">Verzeichnisänderungen replizieren</span><span class="sxs-lookup"><span data-stu-id="06997-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="06997-175">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="06997-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06997-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="06997-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="06997-177">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="06997-177">List contents</span></span></p>
<p><span data-ttu-id="06997-178">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="06997-178">Read all properties</span></span></p>
<p><span data-ttu-id="06997-179">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="06997-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="06997-180">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="06997-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06997-181">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="06997-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="06997-182">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="06997-182">List contents</span></span></p>
<p><span data-ttu-id="06997-183">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="06997-183">Read all properties</span></span></p>
<p><span data-ttu-id="06997-184">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="06997-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="06997-185">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="06997-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06997-186">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="06997-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="06997-187">Read RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="06997-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="06997-188">Read RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="06997-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="06997-189">Read RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="06997-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="06997-190">Read Public-Information</span><span class="sxs-lookup"><span data-stu-id="06997-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="06997-191">Read General-Information</span><span class="sxs-lookup"><span data-stu-id="06997-191">Read General-Information</span></span></p>
<p><span data-ttu-id="06997-192">Read Personal-Information</span><span class="sxs-lookup"><span data-stu-id="06997-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="06997-193">Read User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="06997-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="06997-194">Untergeordnete Contact-Objekte</span><span class="sxs-lookup"><span data-stu-id="06997-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06997-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="06997-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="06997-196">Write RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="06997-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="06997-197">Write otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="06997-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="06997-198">Write displayName</span><span class="sxs-lookup"><span data-stu-id="06997-198">Write displayName</span></span></p>
<p><span data-ttu-id="06997-199">Write description</span><span class="sxs-lookup"><span data-stu-id="06997-199">Write description</span></span></p>
<p><span data-ttu-id="06997-200">Write telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="06997-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="06997-201">Write msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="06997-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="06997-202">Write RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="06997-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="06997-203">Write RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="06997-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="06997-204">Write proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="06997-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="06997-205">Untergeordnete Contact-Objekte</span><span class="sxs-lookup"><span data-stu-id="06997-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="06997-206">Erteilen von Berechtigungen für Device-Objekte</span><span class="sxs-lookup"><span data-stu-id="06997-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="06997-207">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Device-Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="06997-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="06997-208">Für Device-Objekte erteilte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="06997-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06997-209">Group</span><span class="sxs-lookup"><span data-stu-id="06997-209">Group</span></span></th>
<th><span data-ttu-id="06997-210">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="06997-210">Permission</span></span></th>
<th><span data-ttu-id="06997-211">Geltungsbereich</span><span class="sxs-lookup"><span data-stu-id="06997-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06997-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="06997-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="06997-213">Verzeichnisänderungen replizieren</span><span class="sxs-lookup"><span data-stu-id="06997-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="06997-214">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="06997-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06997-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="06997-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="06997-216">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="06997-216">List contents</span></span></p>
<p><span data-ttu-id="06997-217">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="06997-217">Read all properties</span></span></p>
<p><span data-ttu-id="06997-218">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="06997-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="06997-219">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="06997-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06997-220">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="06997-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="06997-221">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="06997-221">List contents</span></span></p>
<p><span data-ttu-id="06997-222">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="06997-222">Read all properties</span></span></p>
<p><span data-ttu-id="06997-223">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="06997-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="06997-224">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="06997-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06997-225">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="06997-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="06997-226">Read RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="06997-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="06997-227">Read RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="06997-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="06997-228">Read RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="06997-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="06997-229">Read Public-Information</span><span class="sxs-lookup"><span data-stu-id="06997-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="06997-230">Read Personal-Information</span><span class="sxs-lookup"><span data-stu-id="06997-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="06997-231">Read General-Information</span><span class="sxs-lookup"><span data-stu-id="06997-231">Read General-Information</span></span></p>
<p><span data-ttu-id="06997-232">Read User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="06997-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="06997-233">Untergeordnete Contact-Objekte</span><span class="sxs-lookup"><span data-stu-id="06997-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06997-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="06997-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="06997-235">Untergeordnetes Element erstellen</span><span class="sxs-lookup"><span data-stu-id="06997-235">Create child</span></span></p>
<p><span data-ttu-id="06997-236">Untergeordnetes Element löschen</span><span class="sxs-lookup"><span data-stu-id="06997-236">Delete child</span></span></p>
<p><span data-ttu-id="06997-237">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="06997-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="06997-238">Kontakt</span><span class="sxs-lookup"><span data-stu-id="06997-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06997-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="06997-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="06997-240">Write displayName</span><span class="sxs-lookup"><span data-stu-id="06997-240">Write displayName</span></span></p>
<p><span data-ttu-id="06997-241">Write description</span><span class="sxs-lookup"><span data-stu-id="06997-241">Write description</span></span></p>
<p><span data-ttu-id="06997-242">Write telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="06997-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="06997-243">Untergeordnete User-Objekte</span><span class="sxs-lookup"><span data-stu-id="06997-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06997-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="06997-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="06997-245">Write RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="06997-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="06997-246">Write otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="06997-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="06997-247">Write displayName</span><span class="sxs-lookup"><span data-stu-id="06997-247">Write displayName</span></span></p>
<p><span data-ttu-id="06997-248">Write description</span><span class="sxs-lookup"><span data-stu-id="06997-248">Write description</span></span></p>
<p><span data-ttu-id="06997-249">Write telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="06997-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="06997-250">Write msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="06997-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="06997-251">Write RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="06997-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="06997-252">Write RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="06997-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="06997-253">Write proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="06997-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="06997-254">Untergeordnete Contact-Objekte</span><span class="sxs-lookup"><span data-stu-id="06997-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="06997-255">Erteilen von Berechtigungen für InetOrgPerson-Objekte</span><span class="sxs-lookup"><span data-stu-id="06997-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="06997-256">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für InetOrgPerson-Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="06997-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="06997-257">Für InetOrgPerson-Objekte erteilte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="06997-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06997-258">Group</span><span class="sxs-lookup"><span data-stu-id="06997-258">Group</span></span></th>
<th><span data-ttu-id="06997-259">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="06997-259">Permission</span></span></th>
<th><span data-ttu-id="06997-260">Geltungsbereich</span><span class="sxs-lookup"><span data-stu-id="06997-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06997-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="06997-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="06997-262">Verzeichnisänderungen replizieren</span><span class="sxs-lookup"><span data-stu-id="06997-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="06997-263">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="06997-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06997-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="06997-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="06997-265">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="06997-265">List contents</span></span></p>
<p><span data-ttu-id="06997-266">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="06997-266">Read all properties</span></span></p>
<p><span data-ttu-id="06997-267">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="06997-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="06997-268">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="06997-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06997-269">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="06997-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="06997-270">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="06997-270">List contents</span></span></p>
<p><span data-ttu-id="06997-271">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="06997-271">Read all properties</span></span></p>
<p><span data-ttu-id="06997-272">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="06997-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="06997-273">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="06997-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06997-274">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="06997-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="06997-275">Read RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="06997-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="06997-276">Read RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="06997-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="06997-277">Read RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="06997-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="06997-278">Read Personal-Information</span><span class="sxs-lookup"><span data-stu-id="06997-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="06997-279">Read Public-Information</span><span class="sxs-lookup"><span data-stu-id="06997-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="06997-280">Read General-Information</span><span class="sxs-lookup"><span data-stu-id="06997-280">Read General-Information</span></span></p>
<p><span data-ttu-id="06997-281">Read User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="06997-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="06997-282">Untergeordnete inetOrgPerson-Objekte</span><span class="sxs-lookup"><span data-stu-id="06997-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06997-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="06997-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="06997-284">Write RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="06997-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="06997-285">Write RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="06997-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="06997-286">Write RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="06997-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="06997-287">Write proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="06997-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="06997-288">Untergeordnete inetOrgPerson-Objekte</span><span class="sxs-lookup"><span data-stu-id="06997-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

