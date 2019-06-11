---
title: 'Lync Server 2013: von Grant-CsOUPermission vorgenommene Änderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ce6b16dff48afeeec848024d763655695905008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="35802-102">Von Grant-CsOUPermission in lync Server 2013 vorgenommene Änderungen</span><span class="sxs-lookup"><span data-stu-id="35802-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35802-103">_**Letztes Änderungsdatum des Themas:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="35802-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="35802-104">Wenn Sie die Verwaltung von lync Server 2013 delegieren möchten, können Sie den angegebenen Organisationseinheiten Berechtigungen hinzufügen, sodass Mitglieder der von der Gesamtstrukturvorbereitung erstellten RTC universelle Gruppen auf die OUs zugreifen können, ohne Mitglieder der Gruppe der Domänenadministratoren zu sein.</span><span class="sxs-lookup"><span data-stu-id="35802-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="35802-105">Das Cmdlet **Grant-CsOuPermission** gewährt den Objekten in der angegebenen OU Berechtigungen, wie in den folgenden Tabellen angegeben.</span><span class="sxs-lookup"><span data-stu-id="35802-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="35802-106">Erteilen der Berechtigung für Benutzerobjekte</span><span class="sxs-lookup"><span data-stu-id="35802-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="35802-107">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Benutzerobjekte in einer OU ausführen, werden Gruppen Berechtigungen gewährt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="35802-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="35802-108">Für Benutzerobjekte gewährte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="35802-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35802-109">Gruppe</span><span class="sxs-lookup"><span data-stu-id="35802-109">Group</span></span></th>
<th><span data-ttu-id="35802-110">Berechtigungs</span><span class="sxs-lookup"><span data-stu-id="35802-110">Permission</span></span></th>
<th><span data-ttu-id="35802-111">Gilt für</span><span class="sxs-lookup"><span data-stu-id="35802-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35802-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="35802-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="35802-113">Replizieren von Verzeichnisänderungen</span><span class="sxs-lookup"><span data-stu-id="35802-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="35802-114">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="35802-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35802-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="35802-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="35802-116">Listeninhalt</span><span class="sxs-lookup"><span data-stu-id="35802-116">List contents</span></span></p>
<p><span data-ttu-id="35802-117">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="35802-117">Read all properties</span></span></p>
<p><span data-ttu-id="35802-118">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="35802-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="35802-119">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="35802-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35802-120">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="35802-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="35802-121">Listeninhalt</span><span class="sxs-lookup"><span data-stu-id="35802-121">List contents</span></span></p>
<p><span data-ttu-id="35802-122">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="35802-122">Read all properties</span></span></p>
<p><span data-ttu-id="35802-123">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="35802-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="35802-124">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="35802-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35802-125">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="35802-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="35802-126">Lesen von RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="35802-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="35802-127">Lesen von RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="35802-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="35802-128">Lesen von RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="35802-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="35802-129">Lesen öffentlicher Informationen</span><span class="sxs-lookup"><span data-stu-id="35802-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="35802-130">Allgemeine Informationen lesen</span><span class="sxs-lookup"><span data-stu-id="35802-130">Read General-Information</span></span></p>
<p><span data-ttu-id="35802-131">Lesen von Benutzerkonto Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="35802-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="35802-132">Nachfolger Benutzerobjekte</span><span class="sxs-lookup"><span data-stu-id="35802-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35802-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="35802-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="35802-134">Schreiben von RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="35802-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="35802-135">Schreiben von msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="35802-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="35802-136">Schreiben von RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="35802-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="35802-137">Schreiben von RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="35802-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="35802-138">Schreiben von proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="35802-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="35802-139">Nachfolger Benutzerobjekte</span><span class="sxs-lookup"><span data-stu-id="35802-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="35802-140">Erteilen der Berechtigung für Computer Objekte</span><span class="sxs-lookup"><span data-stu-id="35802-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="35802-141">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Computer Objekte in einer OU ausführen, werden Gruppen Berechtigungen gewährt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="35802-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="35802-142">Für Computer Objekte gewährte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="35802-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35802-143">Gruppe</span><span class="sxs-lookup"><span data-stu-id="35802-143">Group</span></span></th>
<th><span data-ttu-id="35802-144">Berechtigungs</span><span class="sxs-lookup"><span data-stu-id="35802-144">Permission</span></span></th>
<th><span data-ttu-id="35802-145">Gilt für</span><span class="sxs-lookup"><span data-stu-id="35802-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35802-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="35802-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="35802-147">Replizieren von Verzeichnisänderungen</span><span class="sxs-lookup"><span data-stu-id="35802-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="35802-148">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="35802-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35802-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="35802-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="35802-150">Listeninhalt</span><span class="sxs-lookup"><span data-stu-id="35802-150">List contents</span></span></p>
<p><span data-ttu-id="35802-151">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="35802-151">Read all properties</span></span></p>
<p><span data-ttu-id="35802-152">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="35802-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="35802-153">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="35802-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35802-154">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="35802-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="35802-155">Listeninhalt</span><span class="sxs-lookup"><span data-stu-id="35802-155">List contents</span></span></p>
<p><span data-ttu-id="35802-156">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="35802-156">Read all properties</span></span></p>
<p><span data-ttu-id="35802-157">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="35802-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="35802-158">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="35802-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35802-159">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="35802-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="35802-160">Lesen öffentlicher Informationen</span><span class="sxs-lookup"><span data-stu-id="35802-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="35802-161">Read validiert-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="35802-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="35802-162">Nachfolger Computer Objekte</span><span class="sxs-lookup"><span data-stu-id="35802-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35802-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="35802-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="35802-164">Lesen öffentlicher Informationen</span><span class="sxs-lookup"><span data-stu-id="35802-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="35802-165">Read validiert-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="35802-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="35802-166">Nachfolger Computer Objekte</span><span class="sxs-lookup"><span data-stu-id="35802-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="35802-167">Erteilen der Berechtigung für Kontakt-oder AppContact-Objekte</span><span class="sxs-lookup"><span data-stu-id="35802-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="35802-168">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Contact-Objekte oder AppContact-Objekte in einer OU ausführen, werden Gruppen Berechtigungen gewährt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="35802-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="35802-169">Für Contact-oder AppContact-Objekte gewährte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="35802-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35802-170">Gruppe</span><span class="sxs-lookup"><span data-stu-id="35802-170">Group</span></span></th>
<th><span data-ttu-id="35802-171">Berechtigungs</span><span class="sxs-lookup"><span data-stu-id="35802-171">Permission</span></span></th>
<th><span data-ttu-id="35802-172">Gilt für</span><span class="sxs-lookup"><span data-stu-id="35802-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35802-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="35802-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="35802-174">Replizieren von Verzeichnisänderungen</span><span class="sxs-lookup"><span data-stu-id="35802-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="35802-175">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="35802-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35802-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="35802-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="35802-177">Listeninhalt</span><span class="sxs-lookup"><span data-stu-id="35802-177">List contents</span></span></p>
<p><span data-ttu-id="35802-178">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="35802-178">Read all properties</span></span></p>
<p><span data-ttu-id="35802-179">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="35802-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="35802-180">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="35802-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35802-181">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="35802-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="35802-182">Listeninhalt</span><span class="sxs-lookup"><span data-stu-id="35802-182">List contents</span></span></p>
<p><span data-ttu-id="35802-183">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="35802-183">Read all properties</span></span></p>
<p><span data-ttu-id="35802-184">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="35802-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="35802-185">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="35802-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35802-186">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="35802-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="35802-187">Lesen von RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="35802-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="35802-188">Lesen von RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="35802-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="35802-189">Lesen von RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="35802-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="35802-190">Lesen öffentlicher Informationen</span><span class="sxs-lookup"><span data-stu-id="35802-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="35802-191">Allgemeine Informationen lesen</span><span class="sxs-lookup"><span data-stu-id="35802-191">Read General-Information</span></span></p>
<p><span data-ttu-id="35802-192">Lesen persönlicher Informationen</span><span class="sxs-lookup"><span data-stu-id="35802-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="35802-193">Lesen von Benutzerkonto Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="35802-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="35802-194">Nachfolger-Kontaktobjekte</span><span class="sxs-lookup"><span data-stu-id="35802-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35802-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="35802-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="35802-196">Schreiben von RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="35802-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="35802-197">Schreiben von otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="35802-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="35802-198">Schreiben von DisplayName</span><span class="sxs-lookup"><span data-stu-id="35802-198">Write displayName</span></span></p>
<p><span data-ttu-id="35802-199">Beschreibung schreiben</span><span class="sxs-lookup"><span data-stu-id="35802-199">Write description</span></span></p>
<p><span data-ttu-id="35802-200">Schreiben von telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="35802-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="35802-201">Schreiben von msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="35802-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="35802-202">Schreiben von RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="35802-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="35802-203">Schreiben von RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="35802-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="35802-204">Schreiben von proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="35802-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="35802-205">Nachfolger-Kontaktobjekte</span><span class="sxs-lookup"><span data-stu-id="35802-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="35802-206">Erteilen der Berechtigung für Geräteobjekte</span><span class="sxs-lookup"><span data-stu-id="35802-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="35802-207">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Geräteobjekte in einer OU ausführen, werden Gruppen Berechtigungen gewährt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="35802-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="35802-208">Für Geräteobjekte gewährte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="35802-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35802-209">Gruppe</span><span class="sxs-lookup"><span data-stu-id="35802-209">Group</span></span></th>
<th><span data-ttu-id="35802-210">Berechtigungs</span><span class="sxs-lookup"><span data-stu-id="35802-210">Permission</span></span></th>
<th><span data-ttu-id="35802-211">Gilt für</span><span class="sxs-lookup"><span data-stu-id="35802-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35802-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="35802-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="35802-213">Replizieren von Verzeichnisänderungen</span><span class="sxs-lookup"><span data-stu-id="35802-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="35802-214">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="35802-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35802-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="35802-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="35802-216">Listeninhalt</span><span class="sxs-lookup"><span data-stu-id="35802-216">List contents</span></span></p>
<p><span data-ttu-id="35802-217">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="35802-217">Read all properties</span></span></p>
<p><span data-ttu-id="35802-218">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="35802-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="35802-219">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="35802-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35802-220">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="35802-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="35802-221">Listeninhalt</span><span class="sxs-lookup"><span data-stu-id="35802-221">List contents</span></span></p>
<p><span data-ttu-id="35802-222">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="35802-222">Read all properties</span></span></p>
<p><span data-ttu-id="35802-223">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="35802-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="35802-224">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="35802-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35802-225">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="35802-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="35802-226">Lesen von RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="35802-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="35802-227">Lesen von RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="35802-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="35802-228">Lesen von RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="35802-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="35802-229">Lesen öffentlicher Informationen</span><span class="sxs-lookup"><span data-stu-id="35802-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="35802-230">Lesen persönlicher Informationen</span><span class="sxs-lookup"><span data-stu-id="35802-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="35802-231">Allgemeine Informationen lesen</span><span class="sxs-lookup"><span data-stu-id="35802-231">Read General-Information</span></span></p>
<p><span data-ttu-id="35802-232">Lesen von Benutzerkonto Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="35802-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="35802-233">Nachfolger-Kontaktobjekte</span><span class="sxs-lookup"><span data-stu-id="35802-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35802-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="35802-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="35802-235">Erstellen eines untergeordneten Elements</span><span class="sxs-lookup"><span data-stu-id="35802-235">Create child</span></span></p>
<p><span data-ttu-id="35802-236">Untergeordnetes Element löschen</span><span class="sxs-lookup"><span data-stu-id="35802-236">Delete child</span></span></p>
<p><span data-ttu-id="35802-237">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="35802-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="35802-238">Kontakt</span><span class="sxs-lookup"><span data-stu-id="35802-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35802-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="35802-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="35802-240">Schreiben von DisplayName</span><span class="sxs-lookup"><span data-stu-id="35802-240">Write displayName</span></span></p>
<p><span data-ttu-id="35802-241">Beschreibung schreiben</span><span class="sxs-lookup"><span data-stu-id="35802-241">Write description</span></span></p>
<p><span data-ttu-id="35802-242">Schreiben von telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="35802-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="35802-243">Nachfolger Benutzerobjekte</span><span class="sxs-lookup"><span data-stu-id="35802-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35802-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="35802-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="35802-245">Schreiben von RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="35802-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="35802-246">Schreiben von otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="35802-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="35802-247">Schreiben von DisplayName</span><span class="sxs-lookup"><span data-stu-id="35802-247">Write displayName</span></span></p>
<p><span data-ttu-id="35802-248">Beschreibung schreiben</span><span class="sxs-lookup"><span data-stu-id="35802-248">Write description</span></span></p>
<p><span data-ttu-id="35802-249">Schreiben von telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="35802-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="35802-250">Schreiben von msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="35802-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="35802-251">Schreiben von RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="35802-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="35802-252">Schreiben von RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="35802-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="35802-253">Schreiben von proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="35802-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="35802-254">Nachfolger-Kontaktobjekte</span><span class="sxs-lookup"><span data-stu-id="35802-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="35802-255">Erteilen der Berechtigung für InetOrgPerson-Objekte</span><span class="sxs-lookup"><span data-stu-id="35802-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="35802-256">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für InetOrgPerson-Objekte in einer OU ausführen, werden Gruppen Berechtigungen gewährt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="35802-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="35802-257">Für InetOrgPerson-Objekte gewährte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="35802-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35802-258">Gruppe</span><span class="sxs-lookup"><span data-stu-id="35802-258">Group</span></span></th>
<th><span data-ttu-id="35802-259">Berechtigungs</span><span class="sxs-lookup"><span data-stu-id="35802-259">Permission</span></span></th>
<th><span data-ttu-id="35802-260">Gilt für</span><span class="sxs-lookup"><span data-stu-id="35802-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35802-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="35802-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="35802-262">Replizieren von Verzeichnisänderungen</span><span class="sxs-lookup"><span data-stu-id="35802-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="35802-263">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="35802-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35802-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="35802-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="35802-265">Listeninhalt</span><span class="sxs-lookup"><span data-stu-id="35802-265">List contents</span></span></p>
<p><span data-ttu-id="35802-266">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="35802-266">Read all properties</span></span></p>
<p><span data-ttu-id="35802-267">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="35802-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="35802-268">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="35802-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35802-269">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="35802-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="35802-270">Listeninhalt</span><span class="sxs-lookup"><span data-stu-id="35802-270">List contents</span></span></p>
<p><span data-ttu-id="35802-271">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="35802-271">Read all properties</span></span></p>
<p><span data-ttu-id="35802-272">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="35802-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="35802-273">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="35802-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35802-274">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="35802-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="35802-275">Lesen von RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="35802-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="35802-276">Lesen von RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="35802-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="35802-277">Lesen von RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="35802-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="35802-278">Lesen persönlicher Informationen</span><span class="sxs-lookup"><span data-stu-id="35802-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="35802-279">Lesen öffentlicher Informationen</span><span class="sxs-lookup"><span data-stu-id="35802-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="35802-280">Allgemeine Informationen lesen</span><span class="sxs-lookup"><span data-stu-id="35802-280">Read General-Information</span></span></p>
<p><span data-ttu-id="35802-281">Lesen von Benutzerkonto Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="35802-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="35802-282">Nachgeordnete InetOrgPerson-Objekte</span><span class="sxs-lookup"><span data-stu-id="35802-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35802-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="35802-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="35802-284">Schreiben von RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="35802-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="35802-285">Schreiben von RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="35802-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="35802-286">Schreiben von RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="35802-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="35802-287">Schreiben von proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="35802-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="35802-288">Nachgeordnete InetOrgPerson-Objekte</span><span class="sxs-lookup"><span data-stu-id="35802-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

