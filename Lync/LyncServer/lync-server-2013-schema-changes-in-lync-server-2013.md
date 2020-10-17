---
title: 'Lync Server 2013: Schema Änderungen in lync Server 2013'
description: 'Lync Server 2013: Schema Änderungen in lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e914de48ace80fd2611f2d05b092894b11c534a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557151"
---
# <a name="schema-changes-in-lync-server-2013"></a><span data-ttu-id="a1e0a-103">Schema Änderungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e0a-103">Schema changes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1e0a-104">_**Letztes Änderungsstand des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="a1e0a-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="a1e0a-105">Bevor Sie lync Server 2013 bereitstellen und verwenden, müssen Sie Active Directory-Domänendienste durch Erweitern des Schemas vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="a1e0a-105">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="a1e0a-106">Die Schemaerweiterungen fügen die Klassen und Attribute hinzu, die für lync Server 2013 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a1e0a-106">The schema extensions add the classes and attributes that are required by Lync Server 2013.</span></span>

<span data-ttu-id="a1e0a-107">Lync Server 2013 erfordert mehrere neue Klassen und Attribute und ändert einige vorhandene Klassen und Attribute.</span><span class="sxs-lookup"><span data-stu-id="a1e0a-107">Lync Server 2013 requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="a1e0a-108">Darüber hinaus werden viele Konfigurationsinformationen für lync Server 2013 im zentralen Verwaltungsspeicher statt in AD DS wie in früheren Versionen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a1e0a-108">In addition, much configuration information for Lync Server 2013 is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="a1e0a-109">Die folgenden Informationen werden weiterhin in AD DS in lync Server 2013 gespeichert:</span><span class="sxs-lookup"><span data-stu-id="a1e0a-109">The following information is still stored in AD DS in Lync Server 2013:</span></span>

  - <span data-ttu-id="a1e0a-110">**Schemaerweiterungen**:</span><span class="sxs-lookup"><span data-stu-id="a1e0a-110">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="a1e0a-111">Benutzerobjekterweiterungen</span><span class="sxs-lookup"><span data-stu-id="a1e0a-111">User object extensions</span></span>
    
      - <span data-ttu-id="a1e0a-112">Erweiterungen für Office Communications Server 2007-und Office Communications Server 2007 R2-Klassen zum aufrecht erhalten der Abwärtskompatibilität mit unterstützten Vorgängerversionen</span><span class="sxs-lookup"><span data-stu-id="a1e0a-112">Extensions for Office Communications Server 2007 and Office Communications Server 2007 R2 classes to maintain backward compatibility with supported previous versions</span></span>

<!-- end list -->

  - <span data-ttu-id="a1e0a-113">**Daten** (in lync Server Extended Schema und in vorhandenen Schemaklassen gespeichert):</span><span class="sxs-lookup"><span data-stu-id="a1e0a-113">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="a1e0a-114">Benutzer-SIP-URI (Uniform Resource Identifier) und weitere Einstellungen</span><span class="sxs-lookup"><span data-stu-id="a1e0a-114">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="a1e0a-115">Kontaktobjekte für Anwendungen wie z. B. Reaktionsgruppe und Konferenzzentrale</span><span class="sxs-lookup"><span data-stu-id="a1e0a-115">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="a1e0a-116">Ein Verweis auf den zentralen Verwaltungsspeicher</span><span class="sxs-lookup"><span data-stu-id="a1e0a-116">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="a1e0a-117">Das Kerberos-Authentifizierungskonto (ein optionales Computerobjekt)</span><span class="sxs-lookup"><span data-stu-id="a1e0a-117">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="a1e0a-118">In diesem Thema werden die von lync Server 2013 erforderlichen Active Directory Schemaänderungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a1e0a-118">This topic describes the Active Directory schema changes required by Lync Server 2013.</span></span> <span data-ttu-id="a1e0a-119">Es werden keine Schemaänderungen beschrieben, die von früheren Versionen von Office Communications Server eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="a1e0a-119">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="a1e0a-120">Eine Liste der Klassen und deren Beschreibungen finden Sie unter [Schema Klassen und Beschreibungen in lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="a1e0a-120">For a list of classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="a1e0a-121">Eine Liste der Attribute und deren Beschreibungen finden Sie unter [Schema Attribute and Descriptions in lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="a1e0a-121">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="a1e0a-122">Eine Liste der Klassen mit den Attributen, die Sie enthalten können, finden Sie unter [Schema Attribute by class in lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="a1e0a-122">For a list of classes with the attributes they may contain, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span>

<span data-ttu-id="a1e0a-123">Das msRTCSIP-Präfix identifiziert Klassen und Attribute, die spezifisch für lync Server sind.</span><span class="sxs-lookup"><span data-stu-id="a1e0a-123">The msRTCSIP prefix identifies classes and attributes that are specific to Lync Server.</span></span>

<div>

## <a name="new-active-directory-attributes"></a><span data-ttu-id="a1e0a-124">Neue Active Directory-Attribute</span><span class="sxs-lookup"><span data-stu-id="a1e0a-124">New Active Directory Attributes</span></span>

<span data-ttu-id="a1e0a-125">In der folgenden Tabelle werden die Active Directory Attribute beschrieben, die von lync Server 2013 hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a1e0a-125">The following table describes the Active Directory attributes that are added by Lync Server 2013.</span></span>

### <a name="attributes-added-by-lync-server-2013"></a><span data-ttu-id="a1e0a-126">Von lync Server 2013 hinzugefügte Attribute</span><span class="sxs-lookup"><span data-stu-id="a1e0a-126">Attributes Added by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1e0a-127">Attribut</span><span class="sxs-lookup"><span data-stu-id="a1e0a-127">Attribute</span></span></th>
<th><span data-ttu-id="a1e0a-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1e0a-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1e0a-129">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="a1e0a-129">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="a1e0a-130">Dieses mehrwertige Attribut enthält Bezeichner für Aufbewahrungsrichtlinien, die für den Benutzer gelten.</span><span class="sxs-lookup"><span data-stu-id="a1e0a-130">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="a1e0a-131">Mit Aufbewahrungsrichtlinien werden für den Benutzer Postfachelemente für die Dauer der Aufbewahrung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a1e0a-131">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="a1e0a-132">Dieses Attribut ist für Exchange 2013 freigegeben.</span><span class="sxs-lookup"><span data-stu-id="a1e0a-132">This attribute is shared with Exchange 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1e0a-133">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="a1e0a-133">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="a1e0a-p105">Dies ist die SIP-Routinggruppen-ID. Benutzer in derselben Gruppe registrieren sich beim selben Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="a1e0a-p105">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1e0a-136">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="a1e0a-136">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="a1e0a-137">Dieses Attribut wird verwendet, um das vom Front-End-Pool verwendete gespiegelte SQL Server-Back-End zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a1e0a-137">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a><span data-ttu-id="a1e0a-138">Geänderte Active Directory-Klassen</span><span class="sxs-lookup"><span data-stu-id="a1e0a-138">Modified Active Directory Classes</span></span>

<span data-ttu-id="a1e0a-139">In der folgenden Tabelle werden die Active Directory Klassen beschrieben, die von lync Server 2013 geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="a1e0a-139">The following table describes the Active Directory classes that are modified by Lync Server 2013.</span></span>

### <a name="classes-modified-by-lync-server-2013"></a><span data-ttu-id="a1e0a-140">Von lync Server 2013 geänderte Klassen</span><span class="sxs-lookup"><span data-stu-id="a1e0a-140">Classes Modified by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1e0a-141">Klasse</span><span class="sxs-lookup"><span data-stu-id="a1e0a-141">Class</span></span></th>
<th><span data-ttu-id="a1e0a-142">Änderung</span><span class="sxs-lookup"><span data-stu-id="a1e0a-142">Change</span></span></th>
<th><span data-ttu-id="a1e0a-143">Klasse oder Attribut</span><span class="sxs-lookup"><span data-stu-id="a1e0a-143">Class or Attribute</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1e0a-144">Benutzer</span><span class="sxs-lookup"><span data-stu-id="a1e0a-144">User</span></span></p></td>
<td><p><span data-ttu-id="a1e0a-145">Hinzugefügt: mayContain</span><span class="sxs-lookup"><span data-stu-id="a1e0a-145">add: mayContain</span></span></p>
<p><span data-ttu-id="a1e0a-146">Hinzugefügt: mayContain</span><span class="sxs-lookup"><span data-stu-id="a1e0a-146">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="a1e0a-147">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="a1e0a-147">ProxyAddresses</span></span></p>
<p><span data-ttu-id="a1e0a-148">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="a1e0a-148">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1e0a-149">Kontakt</span><span class="sxs-lookup"><span data-stu-id="a1e0a-149">Contact</span></span></p></td>
<td><p><span data-ttu-id="a1e0a-150">Hinzugefügt: mayContain</span><span class="sxs-lookup"><span data-stu-id="a1e0a-150">add: mayContain</span></span></p>
<p><span data-ttu-id="a1e0a-151">Hinzugefügt: mayContain</span><span class="sxs-lookup"><span data-stu-id="a1e0a-151">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="a1e0a-152">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="a1e0a-152">ProxyAddresses</span></span></p>
<p><span data-ttu-id="a1e0a-153">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="a1e0a-153">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1e0a-154">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="a1e0a-154">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="a1e0a-155">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="a1e0a-155">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="a1e0a-156">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="a1e0a-156">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1e0a-157">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="a1e0a-157">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="a1e0a-158">Hinzugefügt: mayContain</span><span class="sxs-lookup"><span data-stu-id="a1e0a-158">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="a1e0a-159">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="a1e0a-159">msRTCSIP-MirrorBackEndServer</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

