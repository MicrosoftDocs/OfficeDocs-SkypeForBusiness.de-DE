---
title: 'Lync Server 2013: Schema Änderungen in lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bbe1c08b7d03042be2c03511103bfa4e43d39d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a><span data-ttu-id="8d009-102">Schema Änderungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d009-102">Schema changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d009-103">_**Letztes Änderungsdatum des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="8d009-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="8d009-104">Vor der Bereitstellung und dem Betrieb von lync Server 2013 müssen Sie die Active Directory-Domänendienste vorbereiten, indem Sie das Schema erweitern.</span><span class="sxs-lookup"><span data-stu-id="8d009-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="8d009-105">Die Schemaerweiterungen fügen die Klassen und Attribute hinzu, die für lync Server 2013 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="8d009-105">The schema extensions add the classes and attributes that are required by Lync Server 2013.</span></span>

<span data-ttu-id="8d009-106">Lync Server 2013 erfordert mehrere neue Klassen und Attribute und ändert einige vorhandene Klassen und Attribute.</span><span class="sxs-lookup"><span data-stu-id="8d009-106">Lync Server 2013 requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="8d009-107">Darüber hinaus werden viele Konfigurationsinformationen für lync Server 2013 im zentralen Verwaltungsspeicher statt in AD DS gespeichert, wie in früheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="8d009-107">In addition, much configuration information for Lync Server 2013 is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="8d009-108">Die folgenden Informationen werden weiterhin in AD DS in lync Server 2013 gespeichert:</span><span class="sxs-lookup"><span data-stu-id="8d009-108">The following information is still stored in AD DS in Lync Server 2013:</span></span>

  - <span data-ttu-id="8d009-109">**Schema Erweiterungen**:</span><span class="sxs-lookup"><span data-stu-id="8d009-109">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="8d009-110">Benutzerobjekterweiterungen</span><span class="sxs-lookup"><span data-stu-id="8d009-110">User object extensions</span></span>
    
      - <span data-ttu-id="8d009-111">Erweiterungen für Office Communications Server 2007 und Office Communications Server 2007 R2-Klassen zum aufrecht erhalten der Abwärtskompatibilität mit unterstützten vorherigen Versionen</span><span class="sxs-lookup"><span data-stu-id="8d009-111">Extensions for Office Communications Server 2007 and Office Communications Server 2007 R2 classes to maintain backward compatibility with supported previous versions</span></span>

<!-- end list -->

  - <span data-ttu-id="8d009-112">**Daten** (im erweiterten lync Server-Schema und in vorhandenen Schemaklassen gespeichert):</span><span class="sxs-lookup"><span data-stu-id="8d009-112">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="8d009-113">Benutzer SIP Uniform Resource Identifier (URI) und andere Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="8d009-113">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="8d009-114">Kontaktobjekte für Anwendungen wie Reaktionsgruppe und Konferenzzentrale</span><span class="sxs-lookup"><span data-stu-id="8d009-114">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="8d009-115">Ein Zeiger auf den zentralen Verwaltungsspeicher</span><span class="sxs-lookup"><span data-stu-id="8d009-115">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="8d009-116">Kerberos-Authentifizierungs Konto (ein optionales Computerobjekt)</span><span class="sxs-lookup"><span data-stu-id="8d009-116">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="8d009-117">In diesem Thema werden die Active Directory-Schemaänderungen beschrieben, die von lync Server 2013 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="8d009-117">This topic describes the Active Directory schema changes required by Lync Server 2013.</span></span> <span data-ttu-id="8d009-118">Es werden keine Schemaänderungen beschrieben, die in früheren Versionen von Office Communications Server eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="8d009-118">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="8d009-119">Eine Liste der Klassen und deren Beschreibungen finden Sie unter [Schema Klassen und Beschreibungen in lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="8d009-119">For a list of classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="8d009-120">Eine Liste der Attribute und deren Beschreibungen finden Sie unter [Schema Attribute und Beschreibungen in lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="8d009-120">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="8d009-121">Eine Liste der Klassen mit den Attributen, die Sie enthalten können, finden Sie unter [Schema Attribute nach Klasse in lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="8d009-121">For a list of classes with the attributes they may contain, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span>

<span data-ttu-id="8d009-122">Das Attribut msRTCSIP-Präfix identifiziert Klassen und Attribute, die für lync Server spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="8d009-122">The msRTCSIP prefix identifies classes and attributes that are specific to Lync Server.</span></span>

<div>

## <a name="new-active-directory-attributes"></a><span data-ttu-id="8d009-123">Neue Active Directory-Attribute</span><span class="sxs-lookup"><span data-stu-id="8d009-123">New Active Directory Attributes</span></span>

<span data-ttu-id="8d009-124">In der folgenden Tabelle werden die Active Directory-Attribute beschrieben, die von lync Server 2013 hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="8d009-124">The following table describes the Active Directory attributes that are added by Lync Server 2013.</span></span>

### <a name="attributes-added-by-lync-server-2013"></a><span data-ttu-id="8d009-125">Von lync Server 2013 hinzugefügte Attribute</span><span class="sxs-lookup"><span data-stu-id="8d009-125">Attributes Added by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d009-126">Attribut</span><span class="sxs-lookup"><span data-stu-id="8d009-126">Attribute</span></span></th>
<th><span data-ttu-id="8d009-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8d009-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d009-128">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="8d009-128">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="8d009-129">Dieses mehrwertige Attribut enthält Bezeichner für für den Benutzer geltende Aufbewahrungsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="8d009-129">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="8d009-130">Aufbewahrungsrichtlinien behalten Postfachelemente für den Benutzer für die Dauer des haltebereichs bei.</span><span class="sxs-lookup"><span data-stu-id="8d009-130">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="8d009-131">Dieses Attribut wird für Exchange 2013 freigegeben.</span><span class="sxs-lookup"><span data-stu-id="8d009-131">This attribute is shared with Exchange 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d009-132">Attribut msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="8d009-132">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="8d009-133">Hierbei handelt es sich um die SIP-Routinggruppen-ID.</span><span class="sxs-lookup"><span data-stu-id="8d009-133">This is the SIP routing group ID.</span></span> <span data-ttu-id="8d009-134">Benutzer in der gleichen Gruppe werden für denselben Front-End-Server registriert.</span><span class="sxs-lookup"><span data-stu-id="8d009-134">Users in the same group will register to the same Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d009-135">Attribut msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="8d009-135">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="8d009-136">Dieses Attribut wird zum Speichern des vom Front-End-Pool verwendeten gespiegelten SQL Server-Back-Ends verwendet.</span><span class="sxs-lookup"><span data-stu-id="8d009-136">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a><span data-ttu-id="8d009-137">Geänderte Active Directory-Klassen</span><span class="sxs-lookup"><span data-stu-id="8d009-137">Modified Active Directory Classes</span></span>

<span data-ttu-id="8d009-138">In der folgenden Tabelle werden die Active Directory-Klassen beschrieben, die von lync Server 2013 geändert werden.</span><span class="sxs-lookup"><span data-stu-id="8d009-138">The following table describes the Active Directory classes that are modified by Lync Server 2013.</span></span>

### <a name="classes-modified-by-lync-server-2013"></a><span data-ttu-id="8d009-139">Von lync Server 2013 geänderte Klassen</span><span class="sxs-lookup"><span data-stu-id="8d009-139">Classes Modified by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d009-140">Klasse</span><span class="sxs-lookup"><span data-stu-id="8d009-140">Class</span></span></th>
<th><span data-ttu-id="8d009-141">Änderung</span><span class="sxs-lookup"><span data-stu-id="8d009-141">Change</span></span></th>
<th><span data-ttu-id="8d009-142">Klasse oder Attribut</span><span class="sxs-lookup"><span data-stu-id="8d009-142">Class or Attribute</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d009-143">User</span><span class="sxs-lookup"><span data-stu-id="8d009-143">User</span></span></p></td>
<td><p><span data-ttu-id="8d009-144">Add: mayContain</span><span class="sxs-lookup"><span data-stu-id="8d009-144">add: mayContain</span></span></p>
<p><span data-ttu-id="8d009-145">Add: mayContain</span><span class="sxs-lookup"><span data-stu-id="8d009-145">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="8d009-146">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="8d009-146">ProxyAddresses</span></span></p>
<p><span data-ttu-id="8d009-147">Attribut msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="8d009-147">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d009-148">Kontakt</span><span class="sxs-lookup"><span data-stu-id="8d009-148">Contact</span></span></p></td>
<td><p><span data-ttu-id="8d009-149">Add: mayContain</span><span class="sxs-lookup"><span data-stu-id="8d009-149">add: mayContain</span></span></p>
<p><span data-ttu-id="8d009-150">Add: mayContain</span><span class="sxs-lookup"><span data-stu-id="8d009-150">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="8d009-151">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="8d009-151">ProxyAddresses</span></span></p>
<p><span data-ttu-id="8d009-152">Attribut msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="8d009-152">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d009-153">E-Mail-Empfänger</span><span class="sxs-lookup"><span data-stu-id="8d009-153">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="8d009-154">Add: mayContain</span><span class="sxs-lookup"><span data-stu-id="8d009-154">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="8d009-155">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="8d009-155">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d009-156">Attribut msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="8d009-156">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="8d009-157">Add: mayContain</span><span class="sxs-lookup"><span data-stu-id="8d009-157">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="8d009-158">Attribut msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="8d009-158">msRTCSIP-MirrorBackEndServer</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

