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
ms.openlocfilehash: 9056753e57f57b131a05d13eb2862611ba34f966
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="1436d-102">Von Grant-CsOUPermission in lync Server 2013 vorgenommene Änderungen</span><span class="sxs-lookup"><span data-stu-id="1436d-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1436d-103">_**Letztes Änderungsdatum des Themas:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="1436d-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="1436d-104">Wenn Sie die Verwaltung von lync Server 2013 delegieren möchten, können Sie den angegebenen Organisationseinheiten Berechtigungen hinzufügen, sodass Mitglieder der von der Gesamtstrukturvorbereitung erstellten RTC universelle Gruppen auf die OUs zugreifen können, ohne Mitglieder der Gruppe der Domänenadministratoren zu sein.</span><span class="sxs-lookup"><span data-stu-id="1436d-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="1436d-105">Das Cmdlet **Grant-CsOuPermission** gewährt den Objekten in der angegebenen OU Berechtigungen, wie in den folgenden Tabellen angegeben.</span><span class="sxs-lookup"><span data-stu-id="1436d-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="1436d-106">Erteilen der Berechtigung für Benutzerobjekte</span><span class="sxs-lookup"><span data-stu-id="1436d-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="1436d-107">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Benutzerobjekte in einer OU ausführen, werden Gruppen Berechtigungen gewährt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1436d-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="1436d-108">Für Benutzerobjekte gewährte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1436d-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1436d-109">Gruppe</span><span class="sxs-lookup"><span data-stu-id="1436d-109">Group</span></span></th>
<th><span data-ttu-id="1436d-110">Berechtigungs</span><span class="sxs-lookup"><span data-stu-id="1436d-110">Permission</span></span></th>
<th><span data-ttu-id="1436d-111">Gilt für</span><span class="sxs-lookup"><span data-stu-id="1436d-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1436d-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="1436d-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="1436d-113">Replizieren von Verzeichnisänderungen</span><span class="sxs-lookup"><span data-stu-id="1436d-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="1436d-114">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="1436d-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1436d-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1436d-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1436d-116">Listeninhalt</span><span class="sxs-lookup"><span data-stu-id="1436d-116">List contents</span></span></p>
<p><span data-ttu-id="1436d-117">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="1436d-117">Read all properties</span></span></p>
<p><span data-ttu-id="1436d-118">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="1436d-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1436d-119">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="1436d-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1436d-120">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="1436d-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1436d-121">Listeninhalt</span><span class="sxs-lookup"><span data-stu-id="1436d-121">List contents</span></span></p>
<p><span data-ttu-id="1436d-122">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="1436d-122">Read all properties</span></span></p>
<p><span data-ttu-id="1436d-123">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="1436d-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1436d-124">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="1436d-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1436d-125">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="1436d-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1436d-126">Lesen von RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="1436d-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1436d-127">Lesen von RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="1436d-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1436d-128">Lesen von RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="1436d-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="1436d-129">Lesen öffentlicher Informationen</span><span class="sxs-lookup"><span data-stu-id="1436d-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="1436d-130">Allgemeine Informationen lesen</span><span class="sxs-lookup"><span data-stu-id="1436d-130">Read General-Information</span></span></p>
<p><span data-ttu-id="1436d-131">Lesen von Benutzerkonto Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1436d-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="1436d-132">Nachfolger Benutzerobjekte</span><span class="sxs-lookup"><span data-stu-id="1436d-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1436d-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1436d-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1436d-134">Schreiben von RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="1436d-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1436d-135">Schreiben von msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="1436d-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="1436d-136">Schreiben von RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="1436d-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1436d-137">Schreiben von RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="1436d-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="1436d-138">Schreiben von proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="1436d-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="1436d-139">Nachfolger Benutzerobjekte</span><span class="sxs-lookup"><span data-stu-id="1436d-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="1436d-140">Erteilen der Berechtigung für Computer Objekte</span><span class="sxs-lookup"><span data-stu-id="1436d-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="1436d-141">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Computer Objekte in einer OU ausführen, werden Gruppen Berechtigungen gewährt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1436d-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="1436d-142">Für Computer Objekte gewährte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1436d-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1436d-143">Gruppe</span><span class="sxs-lookup"><span data-stu-id="1436d-143">Group</span></span></th>
<th><span data-ttu-id="1436d-144">Berechtigungs</span><span class="sxs-lookup"><span data-stu-id="1436d-144">Permission</span></span></th>
<th><span data-ttu-id="1436d-145">Gilt für</span><span class="sxs-lookup"><span data-stu-id="1436d-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1436d-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="1436d-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="1436d-147">Replizieren von Verzeichnisänderungen</span><span class="sxs-lookup"><span data-stu-id="1436d-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="1436d-148">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="1436d-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1436d-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1436d-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1436d-150">Listeninhalt</span><span class="sxs-lookup"><span data-stu-id="1436d-150">List contents</span></span></p>
<p><span data-ttu-id="1436d-151">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="1436d-151">Read all properties</span></span></p>
<p><span data-ttu-id="1436d-152">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="1436d-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1436d-153">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="1436d-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1436d-154">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="1436d-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1436d-155">Listeninhalt</span><span class="sxs-lookup"><span data-stu-id="1436d-155">List contents</span></span></p>
<p><span data-ttu-id="1436d-156">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="1436d-156">Read all properties</span></span></p>
<p><span data-ttu-id="1436d-157">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="1436d-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1436d-158">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="1436d-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1436d-159">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="1436d-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1436d-160">Lesen öffentlicher Informationen</span><span class="sxs-lookup"><span data-stu-id="1436d-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="1436d-161">Read validiert-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="1436d-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="1436d-162">Nachfolger Computer Objekte</span><span class="sxs-lookup"><span data-stu-id="1436d-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1436d-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1436d-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1436d-164">Lesen öffentlicher Informationen</span><span class="sxs-lookup"><span data-stu-id="1436d-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="1436d-165">Read validiert-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="1436d-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="1436d-166">Nachfolger Computer Objekte</span><span class="sxs-lookup"><span data-stu-id="1436d-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="1436d-167">Erteilen der Berechtigung für Kontakt-oder AppContact-Objekte</span><span class="sxs-lookup"><span data-stu-id="1436d-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="1436d-168">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Contact-Objekte oder AppContact-Objekte in einer OU ausführen, werden Gruppen Berechtigungen gewährt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1436d-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="1436d-169">Für Contact-oder AppContact-Objekte gewährte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1436d-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1436d-170">Gruppe</span><span class="sxs-lookup"><span data-stu-id="1436d-170">Group</span></span></th>
<th><span data-ttu-id="1436d-171">Berechtigungs</span><span class="sxs-lookup"><span data-stu-id="1436d-171">Permission</span></span></th>
<th><span data-ttu-id="1436d-172">Gilt für</span><span class="sxs-lookup"><span data-stu-id="1436d-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1436d-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="1436d-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="1436d-174">Replizieren von Verzeichnisänderungen</span><span class="sxs-lookup"><span data-stu-id="1436d-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="1436d-175">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="1436d-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1436d-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1436d-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1436d-177">Listeninhalt</span><span class="sxs-lookup"><span data-stu-id="1436d-177">List contents</span></span></p>
<p><span data-ttu-id="1436d-178">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="1436d-178">Read all properties</span></span></p>
<p><span data-ttu-id="1436d-179">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="1436d-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1436d-180">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="1436d-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1436d-181">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="1436d-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1436d-182">Listeninhalt</span><span class="sxs-lookup"><span data-stu-id="1436d-182">List contents</span></span></p>
<p><span data-ttu-id="1436d-183">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="1436d-183">Read all properties</span></span></p>
<p><span data-ttu-id="1436d-184">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="1436d-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1436d-185">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="1436d-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1436d-186">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="1436d-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1436d-187">Lesen von RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="1436d-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1436d-188">Lesen von RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="1436d-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1436d-189">Lesen von RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="1436d-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="1436d-190">Lesen öffentlicher Informationen</span><span class="sxs-lookup"><span data-stu-id="1436d-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="1436d-191">Allgemeine Informationen lesen</span><span class="sxs-lookup"><span data-stu-id="1436d-191">Read General-Information</span></span></p>
<p><span data-ttu-id="1436d-192">Lesen persönlicher Informationen</span><span class="sxs-lookup"><span data-stu-id="1436d-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="1436d-193">Lesen von Benutzerkonto Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1436d-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="1436d-194">Nachfolger-Kontaktobjekte</span><span class="sxs-lookup"><span data-stu-id="1436d-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1436d-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1436d-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1436d-196">Schreiben von RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="1436d-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1436d-197">Schreiben von otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="1436d-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="1436d-198">Schreiben von DisplayName</span><span class="sxs-lookup"><span data-stu-id="1436d-198">Write displayName</span></span></p>
<p><span data-ttu-id="1436d-199">Beschreibung schreiben</span><span class="sxs-lookup"><span data-stu-id="1436d-199">Write description</span></span></p>
<p><span data-ttu-id="1436d-200">Schreiben von telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="1436d-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="1436d-201">Schreiben von msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="1436d-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="1436d-202">Schreiben von RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="1436d-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1436d-203">Schreiben von RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="1436d-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="1436d-204">Schreiben von proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="1436d-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="1436d-205">Nachfolger-Kontaktobjekte</span><span class="sxs-lookup"><span data-stu-id="1436d-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="1436d-206">Erteilen der Berechtigung für Geräteobjekte</span><span class="sxs-lookup"><span data-stu-id="1436d-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="1436d-207">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Geräteobjekte in einer OU ausführen, werden Gruppen Berechtigungen gewährt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1436d-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="1436d-208">Für Geräteobjekte gewährte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1436d-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1436d-209">Gruppe</span><span class="sxs-lookup"><span data-stu-id="1436d-209">Group</span></span></th>
<th><span data-ttu-id="1436d-210">Berechtigungs</span><span class="sxs-lookup"><span data-stu-id="1436d-210">Permission</span></span></th>
<th><span data-ttu-id="1436d-211">Gilt für</span><span class="sxs-lookup"><span data-stu-id="1436d-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1436d-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="1436d-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="1436d-213">Replizieren von Verzeichnisänderungen</span><span class="sxs-lookup"><span data-stu-id="1436d-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="1436d-214">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="1436d-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1436d-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1436d-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1436d-216">Listeninhalt</span><span class="sxs-lookup"><span data-stu-id="1436d-216">List contents</span></span></p>
<p><span data-ttu-id="1436d-217">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="1436d-217">Read all properties</span></span></p>
<p><span data-ttu-id="1436d-218">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="1436d-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1436d-219">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="1436d-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1436d-220">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="1436d-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1436d-221">Listeninhalt</span><span class="sxs-lookup"><span data-stu-id="1436d-221">List contents</span></span></p>
<p><span data-ttu-id="1436d-222">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="1436d-222">Read all properties</span></span></p>
<p><span data-ttu-id="1436d-223">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="1436d-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1436d-224">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="1436d-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1436d-225">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="1436d-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1436d-226">Lesen von RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="1436d-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1436d-227">Lesen von RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="1436d-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1436d-228">Lesen von RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="1436d-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="1436d-229">Lesen öffentlicher Informationen</span><span class="sxs-lookup"><span data-stu-id="1436d-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="1436d-230">Lesen persönlicher Informationen</span><span class="sxs-lookup"><span data-stu-id="1436d-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="1436d-231">Allgemeine Informationen lesen</span><span class="sxs-lookup"><span data-stu-id="1436d-231">Read General-Information</span></span></p>
<p><span data-ttu-id="1436d-232">Lesen von Benutzerkonto Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1436d-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="1436d-233">Nachfolger-Kontaktobjekte</span><span class="sxs-lookup"><span data-stu-id="1436d-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1436d-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1436d-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1436d-235">Erstellen eines untergeordneten Elements</span><span class="sxs-lookup"><span data-stu-id="1436d-235">Create child</span></span></p>
<p><span data-ttu-id="1436d-236">Untergeordnetes Element löschen</span><span class="sxs-lookup"><span data-stu-id="1436d-236">Delete child</span></span></p>
<p><span data-ttu-id="1436d-237">Struktur löschen</span><span class="sxs-lookup"><span data-stu-id="1436d-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="1436d-238">Kontakt</span><span class="sxs-lookup"><span data-stu-id="1436d-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1436d-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1436d-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1436d-240">Schreiben von DisplayName</span><span class="sxs-lookup"><span data-stu-id="1436d-240">Write displayName</span></span></p>
<p><span data-ttu-id="1436d-241">Beschreibung schreiben</span><span class="sxs-lookup"><span data-stu-id="1436d-241">Write description</span></span></p>
<p><span data-ttu-id="1436d-242">Schreiben von telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="1436d-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="1436d-243">Nachfolger Benutzerobjekte</span><span class="sxs-lookup"><span data-stu-id="1436d-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1436d-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1436d-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1436d-245">Schreiben von RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="1436d-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1436d-246">Schreiben von otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="1436d-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="1436d-247">Schreiben von DisplayName</span><span class="sxs-lookup"><span data-stu-id="1436d-247">Write displayName</span></span></p>
<p><span data-ttu-id="1436d-248">Beschreibung schreiben</span><span class="sxs-lookup"><span data-stu-id="1436d-248">Write description</span></span></p>
<p><span data-ttu-id="1436d-249">Schreiben von telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="1436d-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="1436d-250">Schreiben von msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="1436d-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="1436d-251">Schreiben von RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="1436d-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1436d-252">Schreiben von RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="1436d-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="1436d-253">Schreiben von proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="1436d-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="1436d-254">Nachfolger-Kontaktobjekte</span><span class="sxs-lookup"><span data-stu-id="1436d-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="1436d-255">Erteilen der Berechtigung für InetOrgPerson-Objekte</span><span class="sxs-lookup"><span data-stu-id="1436d-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="1436d-256">Wenn Sie das **Grant-CsOuPermission-** Cmdlet für InetOrgPerson-Objekte in einer OU ausführen, werden Gruppen Berechtigungen gewährt, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1436d-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="1436d-257">Für InetOrgPerson-Objekte gewährte Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1436d-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1436d-258">Gruppe</span><span class="sxs-lookup"><span data-stu-id="1436d-258">Group</span></span></th>
<th><span data-ttu-id="1436d-259">Berechtigungs</span><span class="sxs-lookup"><span data-stu-id="1436d-259">Permission</span></span></th>
<th><span data-ttu-id="1436d-260">Gilt für</span><span class="sxs-lookup"><span data-stu-id="1436d-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1436d-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="1436d-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="1436d-262">Replizieren von Verzeichnisänderungen</span><span class="sxs-lookup"><span data-stu-id="1436d-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="1436d-263">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="1436d-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1436d-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1436d-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1436d-265">Listeninhalt</span><span class="sxs-lookup"><span data-stu-id="1436d-265">List contents</span></span></p>
<p><span data-ttu-id="1436d-266">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="1436d-266">Read all properties</span></span></p>
<p><span data-ttu-id="1436d-267">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="1436d-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1436d-268">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="1436d-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1436d-269">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="1436d-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1436d-270">Listeninhalt</span><span class="sxs-lookup"><span data-stu-id="1436d-270">List contents</span></span></p>
<p><span data-ttu-id="1436d-271">Alle Eigenschaften lesen</span><span class="sxs-lookup"><span data-stu-id="1436d-271">Read all properties</span></span></p>
<p><span data-ttu-id="1436d-272">Leseberechtigungen</span><span class="sxs-lookup"><span data-stu-id="1436d-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1436d-273">Nur dieses Objekt</span><span class="sxs-lookup"><span data-stu-id="1436d-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1436d-274">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="1436d-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1436d-275">Lesen von RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="1436d-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1436d-276">Lesen von RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="1436d-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1436d-277">Lesen von RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="1436d-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="1436d-278">Lesen persönlicher Informationen</span><span class="sxs-lookup"><span data-stu-id="1436d-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="1436d-279">Lesen öffentlicher Informationen</span><span class="sxs-lookup"><span data-stu-id="1436d-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="1436d-280">Allgemeine Informationen lesen</span><span class="sxs-lookup"><span data-stu-id="1436d-280">Read General-Information</span></span></p>
<p><span data-ttu-id="1436d-281">Lesen von Benutzerkonto Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1436d-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="1436d-282">Nachgeordnete InetOrgPerson-Objekte</span><span class="sxs-lookup"><span data-stu-id="1436d-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1436d-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1436d-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1436d-284">Schreiben von RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="1436d-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1436d-285">Schreiben von RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="1436d-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1436d-286">Schreiben von RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="1436d-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="1436d-287">Schreiben von proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="1436d-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="1436d-288">Nachgeordnete InetOrgPerson-Objekte</span><span class="sxs-lookup"><span data-stu-id="1436d-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

