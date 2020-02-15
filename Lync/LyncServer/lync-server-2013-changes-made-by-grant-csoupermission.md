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
ms.openlocfilehash: dfad0cf4b8b863cd19d4d4113241477de1a50aaf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043927"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="149c5-102">Von Grant-CsOUPermission vorgenommene Änderungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="149c5-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="149c5-103">_**Letztes Änderungsstand des Themas:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="149c5-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="149c5-104">Um lync Server 2013 Verwaltung zu delegieren, können Sie Berechtigungen zu bestimmten Organisationseinheiten (Organizational Units, OUs) hinzufügen, sodass Mitglieder der von der Gesamtstrukturvorbereitung erstellten RTC-universellen Gruppen auf die OUs zugreifen können, ohne Mitglieder der Gruppe "Domänen-Admins" zu sein.</span><span class="sxs-lookup"><span data-stu-id="149c5-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="149c5-105">Mit dem **Grant-CsOuPermission**-Cmdlet werden Objekten in der angegebenen Organisationseinheit Berechtigungen gemäß der folgenden Tabellen erteilt.</span><span class="sxs-lookup"><span data-stu-id="149c5-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="149c5-106">Erteilen von Berechtigungen für User-Objekte</span><span class="sxs-lookup"><span data-stu-id="149c5-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="149c5-107">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Benutzerobjekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="149c5-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="149c5-108">Für User-Objekte erteilte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="149c5-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="149c5-109">Group</span><span class="sxs-lookup"><span data-stu-id="149c5-109">Group</span></span></th>
<th><span data-ttu-id="149c5-110">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="149c5-110">Permission</span></span></th>
<th><span data-ttu-id="149c5-111">Geltungsbereich</span><span class="sxs-lookup"><span data-stu-id="149c5-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="149c5-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="149c5-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="149c5-113">Verzeichnisänderungen replizieren</span><span class="sxs-lookup"><span data-stu-id="149c5-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="149c5-114">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="149c5-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="149c5-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="149c5-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="149c5-116">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="149c5-116">List contents</span></span></p>
<p><span data-ttu-id="149c5-117">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="149c5-117">Read all properties</span></span></p>
<p><span data-ttu-id="149c5-118">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="149c5-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="149c5-119">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="149c5-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="149c5-120">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="149c5-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="149c5-121">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="149c5-121">List contents</span></span></p>
<p><span data-ttu-id="149c5-122">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="149c5-122">Read all properties</span></span></p>
<p><span data-ttu-id="149c5-123">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="149c5-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="149c5-124">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="149c5-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="149c5-125">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="149c5-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="149c5-126">Read RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="149c5-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="149c5-127">Read RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="149c5-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="149c5-128">Read RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="149c5-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="149c5-129">Read Public-Information</span><span class="sxs-lookup"><span data-stu-id="149c5-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="149c5-130">Read General-Information</span><span class="sxs-lookup"><span data-stu-id="149c5-130">Read General-Information</span></span></p>
<p><span data-ttu-id="149c5-131">Read User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="149c5-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="149c5-132">Untergeordnete User-Objekte</span><span class="sxs-lookup"><span data-stu-id="149c5-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="149c5-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="149c5-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="149c5-134">Write RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="149c5-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="149c5-135">Write msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="149c5-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="149c5-136">Write RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="149c5-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="149c5-137">Write RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="149c5-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="149c5-138">Write proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="149c5-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="149c5-139">Untergeordnete User-Objekte</span><span class="sxs-lookup"><span data-stu-id="149c5-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="149c5-140">Erteilen von Berechtigungen für Computer-Objekte</span><span class="sxs-lookup"><span data-stu-id="149c5-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="149c5-141">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Computer Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="149c5-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="149c5-142">Für Computer-Objekte erteilte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="149c5-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="149c5-143">Group</span><span class="sxs-lookup"><span data-stu-id="149c5-143">Group</span></span></th>
<th><span data-ttu-id="149c5-144">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="149c5-144">Permission</span></span></th>
<th><span data-ttu-id="149c5-145">Geltungsbereich</span><span class="sxs-lookup"><span data-stu-id="149c5-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="149c5-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="149c5-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="149c5-147">Verzeichnisänderungen replizieren</span><span class="sxs-lookup"><span data-stu-id="149c5-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="149c5-148">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="149c5-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="149c5-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="149c5-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="149c5-150">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="149c5-150">List contents</span></span></p>
<p><span data-ttu-id="149c5-151">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="149c5-151">Read all properties</span></span></p>
<p><span data-ttu-id="149c5-152">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="149c5-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="149c5-153">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="149c5-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="149c5-154">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="149c5-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="149c5-155">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="149c5-155">List contents</span></span></p>
<p><span data-ttu-id="149c5-156">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="149c5-156">Read all properties</span></span></p>
<p><span data-ttu-id="149c5-157">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="149c5-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="149c5-158">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="149c5-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="149c5-159">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="149c5-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="149c5-160">Read Public-Information</span><span class="sxs-lookup"><span data-stu-id="149c5-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="149c5-161">Read Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="149c5-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="149c5-162">Untergeordnete Computer-Objekte</span><span class="sxs-lookup"><span data-stu-id="149c5-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="149c5-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="149c5-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="149c5-164">Read Public-Information</span><span class="sxs-lookup"><span data-stu-id="149c5-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="149c5-165">Read Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="149c5-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="149c5-166">Untergeordnete Computer-Objekte</span><span class="sxs-lookup"><span data-stu-id="149c5-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="149c5-167">Erteilen von Berechtigungen für Contact oder AppContact-Objekte</span><span class="sxs-lookup"><span data-stu-id="149c5-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="149c5-168">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Contact-Objekte oder AppContact-Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="149c5-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="149c5-169">Für Contact- oder AppContact-Objekte erteilte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="149c5-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="149c5-170">Group</span><span class="sxs-lookup"><span data-stu-id="149c5-170">Group</span></span></th>
<th><span data-ttu-id="149c5-171">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="149c5-171">Permission</span></span></th>
<th><span data-ttu-id="149c5-172">Geltungsbereich</span><span class="sxs-lookup"><span data-stu-id="149c5-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="149c5-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="149c5-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="149c5-174">Verzeichnisänderungen replizieren</span><span class="sxs-lookup"><span data-stu-id="149c5-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="149c5-175">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="149c5-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="149c5-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="149c5-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="149c5-177">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="149c5-177">List contents</span></span></p>
<p><span data-ttu-id="149c5-178">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="149c5-178">Read all properties</span></span></p>
<p><span data-ttu-id="149c5-179">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="149c5-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="149c5-180">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="149c5-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="149c5-181">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="149c5-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="149c5-182">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="149c5-182">List contents</span></span></p>
<p><span data-ttu-id="149c5-183">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="149c5-183">Read all properties</span></span></p>
<p><span data-ttu-id="149c5-184">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="149c5-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="149c5-185">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="149c5-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="149c5-186">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="149c5-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="149c5-187">Read RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="149c5-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="149c5-188">Read RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="149c5-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="149c5-189">Read RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="149c5-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="149c5-190">Read Public-Information</span><span class="sxs-lookup"><span data-stu-id="149c5-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="149c5-191">Read General-Information</span><span class="sxs-lookup"><span data-stu-id="149c5-191">Read General-Information</span></span></p>
<p><span data-ttu-id="149c5-192">Read Personal-Information</span><span class="sxs-lookup"><span data-stu-id="149c5-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="149c5-193">Read User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="149c5-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="149c5-194">Untergeordnete Contact-Objekte</span><span class="sxs-lookup"><span data-stu-id="149c5-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="149c5-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="149c5-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="149c5-196">Write RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="149c5-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="149c5-197">Write otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="149c5-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="149c5-198">Write displayName</span><span class="sxs-lookup"><span data-stu-id="149c5-198">Write displayName</span></span></p>
<p><span data-ttu-id="149c5-199">Write description</span><span class="sxs-lookup"><span data-stu-id="149c5-199">Write description</span></span></p>
<p><span data-ttu-id="149c5-200">Write telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="149c5-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="149c5-201">Write msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="149c5-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="149c5-202">Write RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="149c5-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="149c5-203">Write RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="149c5-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="149c5-204">Write proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="149c5-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="149c5-205">Untergeordnete Contact-Objekte</span><span class="sxs-lookup"><span data-stu-id="149c5-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="149c5-206">Erteilen von Berechtigungen für Device-Objekte</span><span class="sxs-lookup"><span data-stu-id="149c5-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="149c5-207">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Device-Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="149c5-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="149c5-208">Für Device-Objekte erteilte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="149c5-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="149c5-209">Group</span><span class="sxs-lookup"><span data-stu-id="149c5-209">Group</span></span></th>
<th><span data-ttu-id="149c5-210">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="149c5-210">Permission</span></span></th>
<th><span data-ttu-id="149c5-211">Geltungsbereich</span><span class="sxs-lookup"><span data-stu-id="149c5-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="149c5-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="149c5-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="149c5-213">Verzeichnisänderungen replizieren</span><span class="sxs-lookup"><span data-stu-id="149c5-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="149c5-214">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="149c5-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="149c5-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="149c5-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="149c5-216">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="149c5-216">List contents</span></span></p>
<p><span data-ttu-id="149c5-217">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="149c5-217">Read all properties</span></span></p>
<p><span data-ttu-id="149c5-218">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="149c5-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="149c5-219">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="149c5-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="149c5-220">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="149c5-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="149c5-221">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="149c5-221">List contents</span></span></p>
<p><span data-ttu-id="149c5-222">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="149c5-222">Read all properties</span></span></p>
<p><span data-ttu-id="149c5-223">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="149c5-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="149c5-224">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="149c5-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="149c5-225">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="149c5-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="149c5-226">Read RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="149c5-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="149c5-227">Read RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="149c5-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="149c5-228">Read RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="149c5-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="149c5-229">Read Public-Information</span><span class="sxs-lookup"><span data-stu-id="149c5-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="149c5-230">Read Personal-Information</span><span class="sxs-lookup"><span data-stu-id="149c5-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="149c5-231">Read General-Information</span><span class="sxs-lookup"><span data-stu-id="149c5-231">Read General-Information</span></span></p>
<p><span data-ttu-id="149c5-232">Read User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="149c5-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="149c5-233">Untergeordnete Contact-Objekte</span><span class="sxs-lookup"><span data-stu-id="149c5-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="149c5-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="149c5-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="149c5-235">Untergeordnetes Element erstellen</span><span class="sxs-lookup"><span data-stu-id="149c5-235">Create child</span></span></p>
<p><span data-ttu-id="149c5-236">Untergeordnetes Element löschen</span><span class="sxs-lookup"><span data-stu-id="149c5-236">Delete child</span></span></p>
<p><span data-ttu-id="149c5-237">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="149c5-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="149c5-238">Kontakt</span><span class="sxs-lookup"><span data-stu-id="149c5-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="149c5-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="149c5-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="149c5-240">Write displayName</span><span class="sxs-lookup"><span data-stu-id="149c5-240">Write displayName</span></span></p>
<p><span data-ttu-id="149c5-241">Write description</span><span class="sxs-lookup"><span data-stu-id="149c5-241">Write description</span></span></p>
<p><span data-ttu-id="149c5-242">Write telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="149c5-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="149c5-243">Untergeordnete User-Objekte</span><span class="sxs-lookup"><span data-stu-id="149c5-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="149c5-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="149c5-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="149c5-245">Write RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="149c5-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="149c5-246">Write otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="149c5-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="149c5-247">Write displayName</span><span class="sxs-lookup"><span data-stu-id="149c5-247">Write displayName</span></span></p>
<p><span data-ttu-id="149c5-248">Write description</span><span class="sxs-lookup"><span data-stu-id="149c5-248">Write description</span></span></p>
<p><span data-ttu-id="149c5-249">Write telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="149c5-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="149c5-250">Write msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="149c5-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="149c5-251">Write RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="149c5-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="149c5-252">Write RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="149c5-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="149c5-253">Write proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="149c5-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="149c5-254">Untergeordnete Contact-Objekte</span><span class="sxs-lookup"><span data-stu-id="149c5-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="149c5-255">Erteilen von Berechtigungen für InetOrgPerson-Objekte</span><span class="sxs-lookup"><span data-stu-id="149c5-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="149c5-256">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für InetOrgPerson-Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen erteilt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="149c5-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="149c5-257">Für InetOrgPerson-Objekte erteilte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="149c5-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="149c5-258">Group</span><span class="sxs-lookup"><span data-stu-id="149c5-258">Group</span></span></th>
<th><span data-ttu-id="149c5-259">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="149c5-259">Permission</span></span></th>
<th><span data-ttu-id="149c5-260">Geltungsbereich</span><span class="sxs-lookup"><span data-stu-id="149c5-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="149c5-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="149c5-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="149c5-262">Verzeichnisänderungen replizieren</span><span class="sxs-lookup"><span data-stu-id="149c5-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="149c5-263">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="149c5-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="149c5-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="149c5-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="149c5-265">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="149c5-265">List contents</span></span></p>
<p><span data-ttu-id="149c5-266">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="149c5-266">Read all properties</span></span></p>
<p><span data-ttu-id="149c5-267">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="149c5-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="149c5-268">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="149c5-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="149c5-269">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="149c5-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="149c5-270">Inhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="149c5-270">List contents</span></span></p>
<p><span data-ttu-id="149c5-271">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="149c5-271">Read all properties</span></span></p>
<p><span data-ttu-id="149c5-272">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="149c5-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="149c5-273">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="149c5-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="149c5-274">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="149c5-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="149c5-275">Read RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="149c5-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="149c5-276">Read RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="149c5-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="149c5-277">Read RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="149c5-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="149c5-278">Read Personal-Information</span><span class="sxs-lookup"><span data-stu-id="149c5-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="149c5-279">Read Public-Information</span><span class="sxs-lookup"><span data-stu-id="149c5-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="149c5-280">Read General-Information</span><span class="sxs-lookup"><span data-stu-id="149c5-280">Read General-Information</span></span></p>
<p><span data-ttu-id="149c5-281">Read User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="149c5-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="149c5-282">Untergeordnete inetOrgPerson-Objekte</span><span class="sxs-lookup"><span data-stu-id="149c5-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="149c5-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="149c5-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="149c5-284">Write RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="149c5-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="149c5-285">Write RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="149c5-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="149c5-286">Write RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="149c5-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="149c5-287">Write proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="149c5-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="149c5-288">Untergeordnete inetOrgPerson-Objekte</span><span class="sxs-lookup"><span data-stu-id="149c5-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

