---
title: 'Lync Server 2013: Schema Änderungen in lync Server 2013'
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
ms.openlocfilehash: d70b090f59c0a0f8510d778ef659def77cfd0747
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a><span data-ttu-id="bb97f-102">Schema Änderungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb97f-102">Schema changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb97f-103">_**Letztes Änderungsstand des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="bb97f-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="bb97f-104">Bevor Sie lync Server 2013 bereitstellen und verwenden, müssen Sie Active Directory-Domänendienste durch Erweitern des Schemas vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="bb97f-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="bb97f-105">Die Schemaerweiterungen fügen die Klassen und Attribute hinzu, die für lync Server 2013 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="bb97f-105">The schema extensions add the classes and attributes that are required by Lync Server 2013.</span></span>

<span data-ttu-id="bb97f-106">Lync Server 2013 erfordert mehrere neue Klassen und Attribute und ändert einige vorhandene Klassen und Attribute.</span><span class="sxs-lookup"><span data-stu-id="bb97f-106">Lync Server 2013 requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="bb97f-107">Darüber hinaus werden viele Konfigurationsinformationen für lync Server 2013 im zentralen Verwaltungsspeicher statt in AD DS wie in früheren Versionen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bb97f-107">In addition, much configuration information for Lync Server 2013 is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="bb97f-108">Die folgenden Informationen werden weiterhin in AD DS in lync Server 2013 gespeichert:</span><span class="sxs-lookup"><span data-stu-id="bb97f-108">The following information is still stored in AD DS in Lync Server 2013:</span></span>

  - <span data-ttu-id="bb97f-109">**Schemaerweiterungen**:</span><span class="sxs-lookup"><span data-stu-id="bb97f-109">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="bb97f-110">Benutzerobjekterweiterungen</span><span class="sxs-lookup"><span data-stu-id="bb97f-110">User object extensions</span></span>
    
      - <span data-ttu-id="bb97f-111">Erweiterungen für Office Communications Server 2007-und Office Communications Server 2007 R2-Klassen zum aufrecht erhalten der Abwärtskompatibilität mit unterstützten Vorgängerversionen</span><span class="sxs-lookup"><span data-stu-id="bb97f-111">Extensions for Office Communications Server 2007 and Office Communications Server 2007 R2 classes to maintain backward compatibility with supported previous versions</span></span>

<!-- end list -->

  - <span data-ttu-id="bb97f-112">**Daten** (in lync Server Extended Schema und in vorhandenen Schemaklassen gespeichert):</span><span class="sxs-lookup"><span data-stu-id="bb97f-112">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="bb97f-113">Benutzer-SIP-URI (Uniform Resource Identifier) und weitere Einstellungen</span><span class="sxs-lookup"><span data-stu-id="bb97f-113">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="bb97f-114">Kontaktobjekte für Anwendungen wie z. B. Reaktionsgruppe und Konferenzzentrale</span><span class="sxs-lookup"><span data-stu-id="bb97f-114">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="bb97f-115">Ein Verweis auf den zentralen Verwaltungsspeicher</span><span class="sxs-lookup"><span data-stu-id="bb97f-115">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="bb97f-116">Das Kerberos-Authentifizierungskonto (ein optionales Computerobjekt)</span><span class="sxs-lookup"><span data-stu-id="bb97f-116">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="bb97f-117">In diesem Thema werden die von lync Server 2013 erforderlichen Active Directory Schemaänderungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bb97f-117">This topic describes the Active Directory schema changes required by Lync Server 2013.</span></span> <span data-ttu-id="bb97f-118">Es werden keine Schemaänderungen beschrieben, die von früheren Versionen von Office Communications Server eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="bb97f-118">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="bb97f-119">Eine Liste der Klassen und deren Beschreibungen finden Sie unter [Schema Klassen und Beschreibungen in lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="bb97f-119">For a list of classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="bb97f-120">Eine Liste der Attribute und deren Beschreibungen finden Sie unter [Schema Attribute and Descriptions in lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="bb97f-120">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="bb97f-121">Eine Liste der Klassen mit den Attributen, die Sie enthalten können, finden Sie unter [Schema Attribute by class in lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="bb97f-121">For a list of classes with the attributes they may contain, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span>

<span data-ttu-id="bb97f-122">Das msRTCSIP-Präfix identifiziert Klassen und Attribute, die spezifisch für lync Server sind.</span><span class="sxs-lookup"><span data-stu-id="bb97f-122">The msRTCSIP prefix identifies classes and attributes that are specific to Lync Server.</span></span>

<div>

## <a name="new-active-directory-attributes"></a><span data-ttu-id="bb97f-123">Neue Active Directory-Attribute</span><span class="sxs-lookup"><span data-stu-id="bb97f-123">New Active Directory Attributes</span></span>

<span data-ttu-id="bb97f-124">In der folgenden Tabelle werden die Active Directory Attribute beschrieben, die von lync Server 2013 hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="bb97f-124">The following table describes the Active Directory attributes that are added by Lync Server 2013.</span></span>

### <a name="attributes-added-by-lync-server-2013"></a><span data-ttu-id="bb97f-125">Von lync Server 2013 hinzugefügte Attribute</span><span class="sxs-lookup"><span data-stu-id="bb97f-125">Attributes Added by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb97f-126">Attribut</span><span class="sxs-lookup"><span data-stu-id="bb97f-126">Attribute</span></span></th>
<th><span data-ttu-id="bb97f-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb97f-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb97f-128">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="bb97f-128">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="bb97f-129">Dieses mehrwertige Attribut enthält Bezeichner für Aufbewahrungsrichtlinien, die für den Benutzer gelten.</span><span class="sxs-lookup"><span data-stu-id="bb97f-129">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="bb97f-130">Mit Aufbewahrungsrichtlinien werden für den Benutzer Postfachelemente für die Dauer der Aufbewahrung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bb97f-130">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="bb97f-131">Dieses Attribut ist für Exchange 2013 freigegeben.</span><span class="sxs-lookup"><span data-stu-id="bb97f-131">This attribute is shared with Exchange 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb97f-132">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="bb97f-132">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="bb97f-p105">Dies ist die SIP-Routinggruppen-ID. Benutzer in derselben Gruppe registrieren sich beim selben Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="bb97f-p105">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb97f-135">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="bb97f-135">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="bb97f-136">Dieses Attribut wird verwendet, um das vom Front-End-Pool verwendete gespiegelte SQL Server-Back-End zu speichern.</span><span class="sxs-lookup"><span data-stu-id="bb97f-136">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a><span data-ttu-id="bb97f-137">Geänderte Active Directory-Klassen</span><span class="sxs-lookup"><span data-stu-id="bb97f-137">Modified Active Directory Classes</span></span>

<span data-ttu-id="bb97f-138">In der folgenden Tabelle werden die Active Directory Klassen beschrieben, die von lync Server 2013 geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="bb97f-138">The following table describes the Active Directory classes that are modified by Lync Server 2013.</span></span>

### <a name="classes-modified-by-lync-server-2013"></a><span data-ttu-id="bb97f-139">Von lync Server 2013 geänderte Klassen</span><span class="sxs-lookup"><span data-stu-id="bb97f-139">Classes Modified by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb97f-140">Klasse</span><span class="sxs-lookup"><span data-stu-id="bb97f-140">Class</span></span></th>
<th><span data-ttu-id="bb97f-141">Änderung</span><span class="sxs-lookup"><span data-stu-id="bb97f-141">Change</span></span></th>
<th><span data-ttu-id="bb97f-142">Klasse oder Attribut</span><span class="sxs-lookup"><span data-stu-id="bb97f-142">Class or Attribute</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb97f-143">Benutzer</span><span class="sxs-lookup"><span data-stu-id="bb97f-143">User</span></span></p></td>
<td><p><span data-ttu-id="bb97f-144">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="bb97f-144">add: mayContain</span></span></p>
<p><span data-ttu-id="bb97f-145">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="bb97f-145">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="bb97f-146">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="bb97f-146">ProxyAddresses</span></span></p>
<p><span data-ttu-id="bb97f-147">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="bb97f-147">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb97f-148">Kontakt</span><span class="sxs-lookup"><span data-stu-id="bb97f-148">Contact</span></span></p></td>
<td><p><span data-ttu-id="bb97f-149">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="bb97f-149">add: mayContain</span></span></p>
<p><span data-ttu-id="bb97f-150">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="bb97f-150">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="bb97f-151">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="bb97f-151">ProxyAddresses</span></span></p>
<p><span data-ttu-id="bb97f-152">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="bb97f-152">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb97f-153">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="bb97f-153">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="bb97f-154">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="bb97f-154">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="bb97f-155">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="bb97f-155">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb97f-156">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="bb97f-156">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="bb97f-157">Hinzugefügt: mayContain</span><span class="sxs-lookup"><span data-stu-id="bb97f-157">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="bb97f-158">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="bb97f-158">msRTCSIP-MirrorBackEndServer</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

