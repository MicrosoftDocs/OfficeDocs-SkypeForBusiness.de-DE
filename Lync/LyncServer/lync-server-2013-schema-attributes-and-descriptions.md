---
title: 'Lync Server 2013: Schema Attribute und-Beschreibungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcd4c3f3da44be2721d1c6bfc1c1ceece47b6232
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510872"
---
# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="e2c9a-102">Schema Attribute und-Beschreibungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2c9a-102">Schema attributes and descriptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2c9a-103">_**Letztes Änderungsstand des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="e2c9a-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="e2c9a-104">In diesem Abschnitt werden alle Schema Attribute beschrieben, die von lync Server 2013 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-104">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="e2c9a-105">Informationen zu den Klassen, die Attributen zugeordnet sind, finden Sie unter [Schema Attribute by class in lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="e2c9a-105">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="e2c9a-106">Eine Liste der Klassen und Attribute, die neu in lync Server 2013 sind, finden Sie unter [Schema Changes in lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="e2c9a-106">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="e2c9a-107">Attribute, bei denen es sich um verknüpfte Paare handelt, werden als Weiterleitungslinks oder als Backlinks angegeben.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-107">Attributes that are linked pairs are specified as forward links or back links.</span></span> <span data-ttu-id="e2c9a-108">Ein Attribut, das auf ein anderes Objekt verweist, ist eine Weiterleitungsverbindung; das Attribut des anderen Objekts, das auf das erste Objekt zurückverweist, ist eine Rückverknüpfung.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-108">An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link.</span></span> <span data-ttu-id="e2c9a-109">Weiterleitungslinks sind aktualisierbar, während Rück Verknüpfungen schreibgeschützt sind.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-109">Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="e2c9a-110">Einige Attribute weisen einen Bitmaskenwert auf.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-110">Some attributes have a bit-mask value.</span></span> <span data-ttu-id="e2c9a-111">Für diese Attribute wird jede Einstellung durch ein Bit dargestellt, und der angezeigte Dezimalwert stellt die Bit-Position dar.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-111">For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position.</span></span> <span data-ttu-id="e2c9a-112">Bit-Positionen beginnen mit Bit 0.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-112">Bit positions start with bit 0.</span></span> <span data-ttu-id="e2c9a-113">Beispiel: 1 (binär) ist Bit 0 und 10000 (binär) ist Bit 4 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-113">For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set.</span></span> <span data-ttu-id="e2c9a-114">Jedes Bit stellt eine Eigenschaft dar.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-114">Each bit represents a property.</span></span> <span data-ttu-id="e2c9a-115">Im Folgenden finden Sie einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-115">The following are some examples:</span></span>

  - <span data-ttu-id="e2c9a-116">10000 (Binary) hat den Dezimalwert 16 (das heißt, Bit 4 ist festgelegt).</span><span class="sxs-lookup"><span data-stu-id="e2c9a-116">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="e2c9a-117">100 Millionen (binär) hat den Dezimalwert 256 (das heißt, Bit 8 ist festgelegt).</span><span class="sxs-lookup"><span data-stu-id="e2c9a-117">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="e2c9a-118">1100 (Binary) hat den Dezimalwert 12 (d. r., Bits 2 und 3 sind festgelegt; die durch beide Bits dargestellten Eigenschaften sind aktiviert).</span><span class="sxs-lookup"><span data-stu-id="e2c9a-118">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="e2c9a-119">1111000001 (Binary) hat den Dezimalwert 961 (d. r., Bits 0, 6, 7, 8 und 9 sind festgelegt; Eigenschaften für jedes dieser Bits sind aktiviert).</span><span class="sxs-lookup"><span data-stu-id="e2c9a-119">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="e2c9a-120">Schema Attribute für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2c9a-120">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e2c9a-121">Attribut</span><span class="sxs-lookup"><span data-stu-id="e2c9a-121">Attribute</span></span></th>
<th><span data-ttu-id="e2c9a-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2c9a-122">Description</span></span></th>
<th><span data-ttu-id="e2c9a-123">Kommentare</span><span class="sxs-lookup"><span data-stu-id="e2c9a-123">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-124">DNSHostName</span><span class="sxs-lookup"><span data-stu-id="e2c9a-124">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-125">Ein vorhandenes Attribut in Active Directory-Domänendienste, das nun den Klassen <strong>msRTCSIP-Pool</strong> und <strong>msRTCSIP-MonitoringServer</strong> zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-125">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="e2c9a-126">Dieses Attribut gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) eines Pools oder Monitoring Server an.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-126">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="e2c9a-127">Ein gültiger Wert für jedes Segment ist 63 Zeichen; ein gültiger Wert für den gesamten FQDN ist 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-127">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-128">Neu in Microsoft Office Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-128">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-129">MSDS-SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="e2c9a-129">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-130">Dieses Attribut enthält die Zeichenfolgendarstellung des Distinguished Name (DN) des Objekts in einer anderen Gesamtstruktur, die diesem Objekt entspricht.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-130">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object.</span></span> <span data-ttu-id="e2c9a-131">Dieses Attribut wird für die Expansion von Verteilergruppen und die automatische Teilnahme verwendet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-131">This attribute is used for distribution group expansion and auto attendance.</span></span> <span data-ttu-id="e2c9a-132">Dieses Attribut ist im Standard Active Directory Schema für Windows Server 2003 R2 definiert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-132">This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="e2c9a-133">Um zu vermeiden, dass ein Upgrade von AD DS auf Windows Server 2003 R2 erforderlich ist, erweitert Active Directory Schemavorbereitung das Windows Server 2003 Schema mit dieser Attributdefinition.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-133">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-134">Neu in Microsoft Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-134">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-135">"msexchucvoicemailsettings"</span><span class="sxs-lookup"><span data-stu-id="e2c9a-135">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-136">Dieses mehrwertige Attribut umfasst Einstellungen für Voicemail.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-136">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="e2c9a-137">Dieses Attribut ist für Exchange Unified Messaging (um) freigegeben.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-137">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-138">Neu in Microsoft lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-138">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-139">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="e2c9a-139">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-140">Dieses mehrwertige Attribut enthält Bezeichner für Aufbewahrungsrichtlinien, die für den Benutzer gelten.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-140">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="e2c9a-141">Mit Aufbewahrungsrichtlinien werden für den Benutzer Postfachelemente für die Dauer der Aufbewahrung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-141">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="e2c9a-142">Dieses Attribut ist für Exchange 2013 freigegeben.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-142">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-143">Neu in lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-143">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-144">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="e2c9a-144">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-145">Dieses Attribut speichert Informationen zu Audiokonferenz-Anbietern für einen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-145">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-146">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-146">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-147">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="e2c9a-147">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-148">Dieses Attribut verweist auf den vertrauenswürdigen Diensteintrag für den Anwendungs Kontakt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-148">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-149">Neu in Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-149">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-150">msRTCSIP-applicationlist</span><span class="sxs-lookup"><span data-stu-id="e2c9a-150">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-151">Dieses Attribut enthält eine Liste der gehosteten Anwendungen auf dem Anwendungsserver.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-151">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-152">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-152">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-153">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="e2c9a-153">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-154">Dieses Attribut gibt die Optionen für den Anwendungs Kontakt an.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-154">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-155">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-155">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-156">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="e2c9a-156">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-157">Dieses Attribut enthält die primäre Sprache für den Anwendungs Kontakt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-157">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-158">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-158">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-159">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="e2c9a-159">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-160">Dieses Attribut mit mehreren Werten enthält die sekundären Sprachen für den Anwendungs Kontakt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-160">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-161">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-161">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-162">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="e2c9a-162">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-163">Dieses Attribut enthält eine Liste der Anwendungsserver, die zu diesem Pool gehören.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-163">This attribute contains a list of application servers that belong to this pool.</span></span> <span data-ttu-id="e2c9a-164">Der entsprechende Weiterleitungslink zu diesem Backlink <strong>-Attribut lautet msRTCSIP-ApplicationServerPoolLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-164">The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-165">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-165">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-166">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="e2c9a-166">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-167">Dieses Attribut verweist auf den Pool, zu dem dieser Anwendungsserver gehört.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-167">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="e2c9a-168">Dies ist der Weiterleitungslink.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-168">This is the forward link.</span></span> <span data-ttu-id="e2c9a-169">Der entsprechende abwärts Link ist <strong>msRTCSIP-ApplicationServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-169">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-170">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-170">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-171">msRTCSIP-ArchiveDefault (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-171">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e2c9a-172">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-172">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e2c9a-173">In Office Communications Server 2007 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-173">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-174">msRTCSIP-ArchiveDefaultFlags (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-174">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-175">Dieses Attribut gibt den globalen Standardwert innerhalb der Gesamtstrukturgrenze für die Archivierung der gesamten Benutzerkommunikation an.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-175">This attribute specifies the global default within the forest boundary for archiving all user communications.</span></span> <span data-ttu-id="e2c9a-176">Dies wird durch die Archivierungs-Agent-Schicht erzwungen.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-176">This is enforced by the archiving agent layer.</span></span> <span data-ttu-id="e2c9a-177">Der Wertebereich für dieses Attribut lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-177">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-178"><strong>True</strong>: Archivieren aller Benutzer</span><span class="sxs-lookup"><span data-stu-id="e2c9a-178"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-179"><strong>False</strong>: nicht alle Benutzer archivieren</span><span class="sxs-lookup"><span data-stu-id="e2c9a-179"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="e2c9a-180">Dieses Attribut steuert Global innerhalb der Gesamtstruktur Begrenzung, wie die Benutzerkommunikation innerhalb eines internen Netzwerks archiviert wird.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-180">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="e2c9a-181"><strong>Live Communications Server 2005 Verhalten (jetzt veraltet)</strong></span><span class="sxs-lookup"><span data-stu-id="e2c9a-181"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="e2c9a-182">Der Wertebereich für dieses Attribut lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-182">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-183">0: Nachrichtentext archivieren [Bit 0]</span><span class="sxs-lookup"><span data-stu-id="e2c9a-183">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-184">1: Nachrichtentext nicht archivieren [Bit 0]</span><span class="sxs-lookup"><span data-stu-id="e2c9a-184">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="e2c9a-185"><strong>Office Communications Server 2007 Verhalten</strong></span><span class="sxs-lookup"><span data-stu-id="e2c9a-185"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="e2c9a-186">Der Wertebereich für dieses Attribut lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-186">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-187">0: ArchiveFederationDefaultWithoutBody (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-187">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-188">1-2: ArchiveInternalCommunications</span><span class="sxs-lookup"><span data-stu-id="e2c9a-188">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-189">3-4: ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="e2c9a-189">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-190">5: RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="e2c9a-190">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-191">6: RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="e2c9a-191">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-192">7: RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="e2c9a-192">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-193">8: RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="e2c9a-193">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-194">9: RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="e2c9a-194">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-195">10: RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="e2c9a-195">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-196">11: RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="e2c9a-196">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-197">12: RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="e2c9a-197">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-198">13: RecordMeetingInstantiations</span><span class="sxs-lookup"><span data-stu-id="e2c9a-198">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-199">14: RecordMeetingJoins</span><span class="sxs-lookup"><span data-stu-id="e2c9a-199">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-200">15: RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="e2c9a-200">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-201">16: RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="e2c9a-201">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e2c9a-202">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-202">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e2c9a-203">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-203">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-204">msRTCSIP-ArchiveFederationDefault (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-204">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e2c9a-205">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-205">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e2c9a-206">In Office Communications Server 2007 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-206">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-207">msRTCSIP-ArchiveFederationDefaultFlags (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-207">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e2c9a-208">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-208">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e2c9a-209">In Office Communications Server 2007 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-209">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-210">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="e2c9a-210">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-211">Dieses Attribut ist eine ganze Zahl, die als Bit-Feld verwendet wird, um zu steuern, ob die Kommunikation eines einzelnen Benutzers archiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-211">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived.</span></span> <span data-ttu-id="e2c9a-212">Dieses Steuerelement wird von der Archivierungs-Agent-Schicht erzwungen.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-212">This control is enforced by the archiving agent layer.</span></span> <span data-ttu-id="e2c9a-213">Sie ist für die Replikation des globalen Katalogs markiert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-213">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="e2c9a-214">Der Bereich dieses Attributs ist für einen einzelnen Benutzer oder Kontakt spezifisch.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-214">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="e2c9a-215">Die gültigen Werte (und zugeordneten Bit-Positionen) in lync Server lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-215">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-216">0: nicht archivieren (keine Bit-Festlegung)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-216">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-217">1: zurückgezogen (Bit-Position 0)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-217">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-218">2: zurückgezogen (Bit-Position 1)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-218">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-219">4: Archivieren der internen Kommunikation (Bit-Position 2)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-219">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-220">8: Archivieren der Verbundkommunikation (Bit-Position 3)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-220">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="e2c9a-221">Zuvor gültige Werte in Live Communications Server 2005 lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-221">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-222">0: Verwenden Sie den von <strong>msRTCSIP-ArchiveDefault</strong> und <strong>msRTCSIP-ArchiveFederation</strong> in dieser Rangfolge definierten Standardwert:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-222">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-223">1: Archiv</span><span class="sxs-lookup"><span data-stu-id="e2c9a-223">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-224">2: nicht archivieren</span><span class="sxs-lookup"><span data-stu-id="e2c9a-224">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-225">3: Archivieren ohne Nachrichtentext</span><span class="sxs-lookup"><span data-stu-id="e2c9a-225">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="e2c9a-226">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-226">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-227">msRTCSIP-ArchivingServerData (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-227">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-228">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-228">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-229">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-229">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-230">msRTCSIP-ArchivingServerVersion (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-230">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-231">Dieses Attribut definiert die Version des Archivierungsdiensts.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-231">This attribute defines the version of the Archiving service.</span></span> <span data-ttu-id="e2c9a-232">Dieses Attribut ist ein monoton zunehmender ganzzahliger Typ, der mit jeder offiziellen Produktversion inkrementiert wird.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-232">This attribute is a monotonously increasing integer type that increments with each official product release.</span></span> <span data-ttu-id="e2c9a-233">Die zulässigen Werte sind:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-233">The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-234">Undefined: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="e2c9a-234">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="e2c9a-235">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="e2c9a-235">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="e2c9a-236">                 Live Communications Server 2005 mit SP1</span><span class="sxs-lookup"><span data-stu-id="e2c9a-236">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-237">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="e2c9a-237">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-238">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="e2c9a-238">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e2c9a-239">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-239">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e2c9a-240">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-241">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="e2c9a-241">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-242">Dieses Attribut gibt den FQDN des Back-End-Servers des Pools an.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-242">This attribute specifies the FQDN of the Back End Server of the pool.</span></span> <span data-ttu-id="e2c9a-243">Da es nur einen einzelnen Back-End-Server pro Pool geben kann, handelt es sich um ein einwertiges Attribut.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-243">Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="e2c9a-244">Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN beträgt 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-244">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-245">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-245">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-246">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="e2c9a-246">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-247">Dieses Attribut enthält den Bezeichner des Pools, der das Konferenzverzeichnis hostet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-247">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-248">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-248">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-249">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="e2c9a-249">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-250">Dieses Attribut enthält den Bezeichner eines Konferenz Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-250">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-251">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-251">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-252">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="e2c9a-252">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-253">Dieses Attribut enthält den Bezeichner des Pools, in den das Konferenzverzeichnis verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-253">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-254">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-254">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-255">msRTCSIP – Standard</span><span class="sxs-lookup"><span data-stu-id="e2c9a-255">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-256">Dieses boolesche Attribut legt fest, ob es sich bei der Telefonverwendung um eine Standardverwendung handelt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-256">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="e2c9a-257">Wenn dieses Attribut auf <strong>true</strong>festgelegt ist, ist die Telefonverwendung eine standardmäßige Verwendung und kann vom Administrator nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-257">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="e2c9a-258">Wenn dieses Attribut auf <strong>false</strong>festgelegt ist, kann die Verwendung gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-258">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-259">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-259">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-260">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="e2c9a-260">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-261">Dieses Attribut identifiziert die Communicator-Webzugriffs-URL für Benutzer außerhalb der Organisation.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-261">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-262">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-262">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-263">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="e2c9a-263">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-264">Dieses Attribut identifiziert die Communicator-Webzugriffs-URL für Benutzer, die sich innerhalb der Organisation befinden.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-264">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-265">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-265">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-266">msRTCSIP-DefaultLocationProfileLink (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-266">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-267">Dieses einwertige Attribut enthält den Distinguished Name (DN) eines Standortprofil-Klassenobjekts, das ihm zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-267">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="e2c9a-268">Link weiterleiten: <strong>Link ID 11036</strong></span><span class="sxs-lookup"><span data-stu-id="e2c9a-268">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="e2c9a-269">Der entsprechende abwärts Link ist <strong>msRTCSIP-ServerReferenceBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-269">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-270">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-270">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-271">msRTCSIP-DefaultPolicy (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-271">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-272">Dieses boolesche Attribut gibt an, ob es sich bei der Richtlinie um eine Standardrichtlinie handelt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-272">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="e2c9a-273">Die Richtlinie ist eine Standardrichtlinie, wenn Sie auf <strong>true</strong>festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-273">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-274">Neu in Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="e2c9a-274">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="e2c9a-275">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-275">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-276">msRTCSIP-DefaultRouteToEdgeProxy (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-276">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-277">Dieses Attribut gibt den FQDN der Edgeserver an, auf die der Zugriffs-Edgedienst, auf den direkt zugegriffen werden kann, oder das Hardwaregerät zum Lastenausgleich für einen Serverpool mit Zugriffs-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-277">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="e2c9a-278">Wenn auf den Servern mit Zugriffs-Edgedienst nur über einen oder mehrere Directors zugegriffen werden kann, gibt dieses Attribut den FQDN und optional die Portnummer des Directors oder des Hardware-Lastenausgleichs an, der eine Directorpool bedient.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-278">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="e2c9a-279">Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN beträgt 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-279">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-280">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-280">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e2c9a-281">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-281">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-282">msRTCSIP-DefaultRouteToEdgeProxyPort (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-283">Dieses Attribut stellt die Portnummer dar, die zum Herstellen einer Verbindung mit dem Server mit Zugriffs-Edgedienst verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-283">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="e2c9a-284">Der gültige Wert ist ein ganzzahliger Wert, der den zu verwendenden Port angibt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-284">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="e2c9a-285">Der Standardwert lautet 5061.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-285">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-286">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-286">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e2c9a-287">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-287">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-288">msRTCSIP-DefPresenceSubscriptionTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-289">Dieses Attribut stellt den Standardtimeout Zeitraum für Anwesenheitsabonnements dar.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-289">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-290">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-290">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-291">msRTCSIP-DefRegistrationTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-291">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-292">Dieses Attribut stellt das standardmäßige Registrierungstimeout Fenster dar.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-292">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-293">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-293">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-295">Dieses Attribut stellt das Standardtimeout Fenster für das Roaming-Datenabonnement dar.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-295">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-296">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-296">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-297">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="e2c9a-297">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-298">Dieses Attribut wird in einer geteilten Domänentopologie verwendet und enthält einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN).</span><span class="sxs-lookup"><span data-stu-id="e2c9a-298">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-299">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-299">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-300">msRTCSIP-Description (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-300">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-301">Dieses einwertige UNICODE-Zeichenfolgenattribut enthält eine benutzerfreundliche Beschreibung dieser Telefonroute oder Normalisierungsregel.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-301">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-302">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-302">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e2c9a-303">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-303">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-304">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="e2c9a-304">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-305">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-305">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-306">msRTCSIP-Domänenname</span><span class="sxs-lookup"><span data-stu-id="e2c9a-306">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-307">Dieses Attribut stellt eine für die Registrierungsstelle konfigurierte Domäne dar.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-307">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-308">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="e2c9a-308">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-309">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-309">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-310">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-310">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-311">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="e2c9a-311">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-312">Dieses Attribut gibt den FQDN des Servers an, auf dem Zugriffs-Edgedienst ausführt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-312">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="e2c9a-313">Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN beträgt 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-313">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-314">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-314">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-315">msRTCSIP-EnableBestEffortNotify (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-315">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-316">Dieses Attribut steuert, ob ein Server eine Benachrichtigungsanforderung (Best Effort notify, BENOTIFY) anstelle einer Notify-Anforderung als Antwort auf eine subscribe-Anforderung eines Clients generiert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-316">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client.</span></span> <span data-ttu-id="e2c9a-317">BENOTIFY ist eine leistungssteigernde Erweiterung des Subscribe-Benachrichtigungs Handshakes, bei dem der Server BENOTIFY-Anforderungen anstelle von regulären NOTIFY-Anforderungen generiert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-317">BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests.</span></span> <span data-ttu-id="e2c9a-318">Der Leistungsvorteil besteht darin, dass für eine BENOTIFY-Anforderung keine 200 OK-Antwort vom Client erforderlich ist, wenn die Notify-Anforderung dies tut.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-318">The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="e2c9a-319">Gültige Werte sind <strong>true</strong> oder <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-319">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e2c9a-320">BENOTIFY-Anforderungen werden von Live Communications Server 2003 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-320">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="e2c9a-321">Zur Zusammenarbeit mit Serveranwendungen, die mit der Live Communications Server 2003 Server-API geschrieben werden, die auf Live Communications Server 2005-und Drittanbieterservern ausgeführt wird, können BENOTIFY-Anforderungen deaktiviert werden, indem der Wert auf <STRONG>false</STRONG>festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-321">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="e2c9a-322">BENOTIFY ist derzeit nicht Teil des IETF-Standardisierungsprozesses (Internet Engineering Task Force).</span><span class="sxs-lookup"><span data-stu-id="e2c9a-322">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="e2c9a-323">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-323">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e2c9a-324">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-324">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-325">msRTCSIP-EnableFederation (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-325">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-326">Dieses Attribut ist ein globaler Switch, mit dem IT-Administratoren konfigurieren können, ob Benutzer mit Benutzern aus anderen Organisationen kommunizieren dürfen.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-326">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations.</span></span> <span data-ttu-id="e2c9a-327">Es ermöglicht einem Administrator das Überschreiben des <strong>FederationEnabled</strong> -Attributs eines einzelnen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-327">It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute.</span></span> <span data-ttu-id="e2c9a-328">Dieses Attribut kann hilfreich sein, um das interne Netzwerk vor Internet Angriffen zu schützen, die möglicherweise durch Würmer, Viren oder gezielte Angriffe auf das Unternehmen verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-328">This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="e2c9a-329">Die gültigen Werte (und zugeordneten Bit-Positionen) lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-329">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-330">1: für öffentliche Chat Verbindungen aktiviert (Bit-Position 0)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-330">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-331">2: reserviert (Bit-Position 1)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-331">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-332">4: reserviert (Bit-Position 2)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-332">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-333">8: reserviert (Bit-Position 3)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-333">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-334">16: Remote Anrufsteuerung aktiviert [Telefonie] (Bit-Position 4)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-334">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-335">64: AllowOrganizeMeetingWithAnonymousParticipants lautet (Benutzer können anonyme Benutzer zu Besprechungen einladen (Bit-Position 6)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-335">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-336">128: UCEnabled (Benutzer für Unified Communications aktivieren) (Bit-Position 7)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-336">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-337">256: EnabledForEnhancedPresence (Benutzer für öffentliche Chat Verbindungen aktivieren) (Bit-Position 8)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-337">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-338">512: RemoteCallControlDualMode (Bit-Position 9)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-338">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e2c9a-339">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-339">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e2c9a-340">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-340">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-341">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="e2c9a-341">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-342">Dieses Attribut gibt an, ob die Enterprise-Dienste auf dem angegebenen Server geladen werden.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-342">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-343">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="e2c9a-343">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-344">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-344">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-345">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="e2c9a-345">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-346">Dieses Attribut enthält die Wählnummer für den externen Zugriff.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-346">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-347">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-347">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-348">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="e2c9a-348">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-349">Mit diesem Attribut wird gesteuert, ob ein einzelner Benutzer für den Partnerverbund aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-349">This attribute controls whether a single user is enabled for federation.</span></span> <span data-ttu-id="e2c9a-350">Sie wird von der Enterprise Services-Schicht erzwungen.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-350">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="e2c9a-351">Sie ist für die Replikation des globalen Katalogs markiert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-351">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="e2c9a-352">Gültige Werte sind <strong>true</strong> oder <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-352">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-353">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-353">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-354">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="e2c9a-354">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-355">Dieses Attribut ist eine mehrwertige Liste der Domänennamen aller Enterprise Edition-Server, die einem Pool zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-355">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="e2c9a-356">Link zurück: <strong>Link ID 11023</strong></span><span class="sxs-lookup"><span data-stu-id="e2c9a-356">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="e2c9a-357">Der entsprechende Weiterleitungslink zu diesem Rück Link ist <strong>msRTCSIP-PoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-357">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-358">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-358">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-359">msRTCSIP-Gateways (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-359">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-360">Dieses mehrwertige Zeichenfolgenattribut enthält eine Liste von Gateways und Ports (pro Gateway).</span><span class="sxs-lookup"><span data-stu-id="e2c9a-360">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-361">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-361">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-362">msRTCSIP-GlobalSettingsData (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-362">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-363">Dieses Attribut speichert Name: Wert-Paare.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-363">This attribute stores name:value pairs.</span></span> <span data-ttu-id="e2c9a-364">Das bereits definierte Name: Value-Paar ist für die Einstellung <strong>Abruf für Anwesenheit zulassen</strong> .</span><span class="sxs-lookup"><span data-stu-id="e2c9a-364">The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-365">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-365">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-366">msRTCSIP-Gruppierung</span><span class="sxs-lookup"><span data-stu-id="e2c9a-366">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-367">Dieses Attribut ist ein eindeutiger Bezeichner einer Gruppe, die zum Gruppieren von Adressbucheinträgen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-367">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-368">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-368">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-369">msRTCSIP-Homeserver (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-369">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e2c9a-370">Neu in Live Communications Server 2003 (nicht verwendet).</span><span class="sxs-lookup"><span data-stu-id="e2c9a-370">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="e2c9a-371">In Live Communications Server 2005 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-371">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-372">msRTCSIP-HomeServerString (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-372">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e2c9a-373">Neu in Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-373">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="e2c9a-374">In Live Communications Server 2005 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-374">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-375">msRTCSIP-Heimuser (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-375">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e2c9a-376">Neu in Live Communications Server 2003 (nicht verwendet).</span><span class="sxs-lookup"><span data-stu-id="e2c9a-376">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="e2c9a-377">In Live Communications Server 2005 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-377">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-378">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="e2c9a-378">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-379">Mit diesem Attribut wird gesteuert, ob ein einzelner Benutzer für den Zugriff durch externe Benutzer aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-379">This attribute controls whether a single user is enabled for outside user access.</span></span> <span data-ttu-id="e2c9a-380">Sie wird von der Enterprise Services-Schicht erzwungen.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-380">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="e2c9a-381">Sie ist für die Replikation des globalen Katalogs markiert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-381">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="e2c9a-382">Gültige Werte sind <strong>true</strong> oder <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-382">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-383">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-383">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-384">msRTCSIP-IsMaster (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-384">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e2c9a-385">Neu in Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="e2c9a-385">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="e2c9a-386">In Live Communications Server 2005 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-386">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-387">msRTCSIP-Line</span><span class="sxs-lookup"><span data-stu-id="e2c9a-387">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-388">Dieses einwertige Attribut enthält die Geräte-ID (entweder den SIP-URI oder den Tel-URI des Telefons, den der Benutzer steuert), der von lync für die Telefonie verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-388">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="e2c9a-389">Dieses Attribut ist für die Replikation des globalen Katalogs gekennzeichnet und wird indiziert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-389">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="e2c9a-390">Wenn ein Benutzer für Enterprise-VoIP aktiviert ist, wird in diesem Attribut die normalisierte E. 164-Version der Telefonnummer des Benutzers gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-390">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-391">Neu in Microsoft Office Live Communications Server 2005 mit SP1</span><span class="sxs-lookup"><span data-stu-id="e2c9a-391">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-392">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="e2c9a-392">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-393">Dieses Attribut mit einem Wert enthält den SIP-URI des CSTA-SIP-Gatewayservers.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-393">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server.</span></span> <span data-ttu-id="e2c9a-394">Dieses Attribut ist für die Replikation des globalen Katalogs gekennzeichnet, jedoch nicht indiziert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-394">This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-395">Neu in Microsoft Office Live Communications Server 2005 mit SP1</span><span class="sxs-lookup"><span data-stu-id="e2c9a-395">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-396">msRTCSIP-LocalNormalizationData (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-396">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-397">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-397">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-398">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-398">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e2c9a-399">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-399">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-400">msRTCSIP-LocalNormalizationLinks (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-400">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-401">Dieses mehrwertige Attribut enthält eine Liste der lokalen normalisierungs Namen (Distinguished Names, DN), die diesem Standortprofil zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-401">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile.</span></span> <span data-ttu-id="e2c9a-402">Der Typ dieses Attributs ist eine DN-Binärdatei.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-402">The type of this attribute is a DN binary.</span></span> <span data-ttu-id="e2c9a-403">Es gibt eine 1: n-Beziehung zwischen Standortprofil und lokalen Normalisierungsregeln.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-403">There is a one-to-many relationship between location profile and local normalization rules.</span></span> <span data-ttu-id="e2c9a-404">Die Sortierung der Liste der lokalen normalisierungs-DNS muss in der vom Administrator angegebenen Reihenfolge aufrecht erhalten werden.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-404">The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator.</span></span> <span data-ttu-id="e2c9a-405">Die Beibehaltung der Reihenfolge wird durch den binären Teil der DN-Binärdatei verwaltet, der den Reihenfolgeindex angibt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-405">The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="e2c9a-406">Link weiterleiten: <strong>Link ID 11034</strong></span><span class="sxs-lookup"><span data-stu-id="e2c9a-406">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="e2c9a-407">Die entsprechende Backlink to this Forward Link-Attribut ist <strong>msRTCSIP-LocationProfileBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-407">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-408">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-408">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e2c9a-409">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-409">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-410">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="e2c9a-410">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-411">Dieses Attribut enthält eine Liste von Optionen für die Normalisierungsregel.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-411">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-412">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-412">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-413">msRTCSIP-LocationName (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-413">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-414">Dieses einwertige Attribut enthält einen Anzeigenamen für das Standortprofil, das angibt, welche Position dieses Profil darstellt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-414">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents.</span></span> <span data-ttu-id="e2c9a-415">Da es mehrere Standortprofile geben kann, benötigt der Administrator eine Möglichkeit, zwischen unterschiedlichen Profilen zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-415">Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-416">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-416">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e2c9a-417">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-417">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-418">msRTCSIP-locationProfileBL (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-418">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-419">Dieses mehrwertige Attribut enthält eine Liste von Standortprofil-Distinguished Names.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-419">This multi-valued attribute contains a list of location profile distinguished names.</span></span> <span data-ttu-id="e2c9a-420">Dieses Attribut gibt die Rückverknüpfung zu einem oder mehreren Standortprofilen an.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-420">This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="e2c9a-421">Link zurück: <strong>Link ID 11035</strong></span><span class="sxs-lookup"><span data-stu-id="e2c9a-421">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="e2c9a-422">Dieses Attribut entspricht dem Forward-Link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-422">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-423">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-423">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e2c9a-424">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-424">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-425">msRTCSIP-LocationProfileData (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-425">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-426">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-426">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-427">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-427">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e2c9a-428">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-428">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-429">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="e2c9a-429">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-430">Dieses Attribut enthält die Optionen für das Standortprofil.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-430">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-431">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-431">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-432">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="e2c9a-432">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-433">Dieses mehrwertige Attribut umfasst eine Liste von Anwendungs Kontakten.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-433">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-434">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-434">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-435">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="e2c9a-435">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-436">Dieses mehrwertige Attribut umfasst eine Liste von Standortprofilen.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-436">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-437">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-437">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-438">msRTCSIP-MaxNumOutstandingSearchPerServer (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-439">Dieses Attribut stellt die maximale Anzahl ausstehender Suchanforderungen pro Server dar.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-439">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-440">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-440">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-441">msRTCSIP-MaxNumSubscriptionsPerUser (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-442">Das-Attribut stellt die maximale Anzahl von Abonnements pro Benutzer dar.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-442">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-443">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-443">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-444">msRTCSIP-MaxPresenceSubscriptionTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-445">Dieses Attribut stellt das maximale Timeout Fenster für Abonnements dar.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-445">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-446">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-446">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-447">msRTCSIP-MaxRegistrationsTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-447">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-448">Dieses Attribut stellt das Timeout Fenster für maximale Registrierungen dar.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-448">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-449">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-449">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-451">Dieses Attribut stellt das Timeout Fenster für das maximale Roaming von Daten Abonnements dar.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-451">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-452">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-452">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-453">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="e2c9a-453">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-454">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-454">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-455">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-455">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-456">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="e2c9a-456">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-457">Dieses Attribut ist ein Dienststeuerungspunkt-Attribut unter der Computerklasse, das einen Link zurück zur MCU-Factory (Multipoint Control Unit) angibt, zu der es gehört.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-457">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs.</span></span> <span data-ttu-id="e2c9a-458">Dieser Dienst Steuerungs Pfad und das Attribut werden für jede Microsoft MCU erstellt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-458">This service control point and attribute is created for every Microsoft MCU.</span></span> <span data-ttu-id="e2c9a-459">Jede Microsoft MCU muss den Back-End-Server des Pools finden, zu dem Sie gehört, um Einstellungen auf Poolebene daraus abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-459">Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="e2c9a-460">Der Wert dieses Attributs ist der DN (Distinguished Name) der MCU-Factory.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-460">The value of this attribute is the distinguished name (DN) of the MCU Factory.</span></span> <span data-ttu-id="e2c9a-461">Hierbei handelt es sich um ein einwertiges Attribut, das für die Replikation des globalen Katalogs gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-461">This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="e2c9a-462">Link weiterleiten: <strong>Link ID 11026</strong></span><span class="sxs-lookup"><span data-stu-id="e2c9a-462">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="e2c9a-463">Die entsprechende Backlink to this Forward Link-Attribut ist <strong>msRTCSIP-MCUServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-463">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-464">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-464">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-465">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="e2c9a-465">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-466">Dies ist ein reserviertes Attribut mit mehreren Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-466">This is a multi-string reserved attribute.</span></span> <span data-ttu-id="e2c9a-467">In diesem Attribut gespeicherte Einstellungen werden als Name = Wert-Paare dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-467">Settings stored in this attribute are represented as name=value pairs.</span></span> <span data-ttu-id="e2c9a-468">Aktuell definierte Name = Wert-Paare sind:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-468">Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-469">FactoryURL = &lt; URL&gt;</span><span class="sxs-lookup"><span data-stu-id="e2c9a-469">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e2c9a-470">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-470">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-471">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="e2c9a-471">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-472">Hierbei handelt es sich um ein einwertiges Attribut, das den Distinguished Name (DN) einer einzelnen MCU-Factory enthält, die einem Pool zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-472">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="e2c9a-473">Link weiterleiten: <strong>Link ID 11024</strong></span><span class="sxs-lookup"><span data-stu-id="e2c9a-473">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="e2c9a-474">Die entsprechende Backlink to this Forward Link-Attribut ist <strong>msRTCSIP-PoolAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-474">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-475">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-475">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-476">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="e2c9a-476">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-477">Dieses Attribut ist eine einwertige Zeichenfolge, die die GUID des MCU-Factory-Anbieters angibt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-477">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="e2c9a-478">Basierend auf dem GUID-Wert bestimmt der MCU-factoryprozess, ob dieser MCU-Typ gewartet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-478">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="e2c9a-479">Wenn der GUID-Wert <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>ist, wird der MCU-factoryprozess (standardmäßig in lync Server verfügbar) verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-479">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="e2c9a-480">Für jeden anderen GUID-Wert wird der MCU-Prozess vom MCU-factoryprozess nicht gewartet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-480">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-481">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-481">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-482">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="e2c9a-482">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-483">Dieses Attribut ist eine mehrwertige Liste mit Distinguished Names (DN).</span><span class="sxs-lookup"><span data-stu-id="e2c9a-483">This attribute is a multi-valued list of distinguished names (DN).</span></span> <span data-ttu-id="e2c9a-484">Dieses Attribut enthält eine Liste aller MCU-Server desselben Typs und Anbieters, die dieser MCU-Factory zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-484">This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory.</span></span> <span data-ttu-id="e2c9a-485">Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN beträgt 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-485">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="e2c9a-486">Link zurück: Link ID 11027</span><span class="sxs-lookup"><span data-stu-id="e2c9a-486">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="e2c9a-487">Der entsprechende Weiterleitungslink zu diesem Rück Link ist <strong>msRTCSIP-MCUFactoryAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-487">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-488">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-488">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-489">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="e2c9a-489">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-490">Dieses Attribut ist eine einwertige Zeichenfolge, die das Medium angibt, mit dem die MCU umgehen kann.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-490">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="e2c9a-491">Unterstützte gültige Typen:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-491">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-492">Besprechungs</span><span class="sxs-lookup"><span data-stu-id="e2c9a-492">meeting</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-493">Audio-Video</span><span class="sxs-lookup"><span data-stu-id="e2c9a-493">audio-video</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-494">Chat</span><span class="sxs-lookup"><span data-stu-id="e2c9a-494">chat</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-495">Telefon-conf</span><span class="sxs-lookup"><span data-stu-id="e2c9a-495">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e2c9a-496">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-496">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-497">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="e2c9a-497">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-498">Dieses Attribut ist eine einwertige Zeichenfolge, die den Namen eines MCU-Anbieters angibt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-498">This attribute is a single-valued string that specifies an MCU vendor’s name.</span></span> <span data-ttu-id="e2c9a-499">Alle Microsoft-MCU gibt dieses Attribut als <strong>Microsoft Corporation</strong>an.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-499">All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-500">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-500">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-501">msRTCSIP-MeetingFlags (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-501">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-502">Dieses Attribut definiert unterschiedliche Besprechungsoptionen, die Global für alle Benutzer oder Kontaktobjekte aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-502">This attribute defines different meeting options that are enabled globally for all users or contact objects.</span></span> <span data-ttu-id="e2c9a-503">Dieses Attribut ist ein Bitmaskenwert des Typs Integer.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-503">This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="e2c9a-504">Die gültigen Werte (und zugeordneten Bit-Positionen) lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-504">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-505">0: AllowOrganizeMeetingWithAnonymousParticipants lautet ist keine (Benutzer dürfen keine anonymen Benutzer zu Besprechungen einladen) (keine Bits festgelegt)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-505">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-506">4: AllowOrganizeMeetingWithAnonymousParticipants lautet ist jeder (gestatten Sie allen Benutzern, anonyme Benutzer zu Besprechungen einzuladen) (Bit-Position 2)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-506">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-507">8: AllowOrganizeMeetingWithAnonymousParticipants lautet ist UsePerUserSetting (Benutzern das einladen anonymer Benutzer zu Besprechungen basierend auf der Einstellung pro Benutzer) (Bit-Position 3)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-507">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-508">16: UserPerUserMeetingPolicy (Besprechungsrichtlinie wird pro Benutzerdefiniert) (Bit-Position 4)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-508">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e2c9a-509">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-509">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e2c9a-510">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-510">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-511">msRTCSIP-meetingpolicy "(veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-511">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-512">Dieses Attribut gibt den Distinguished Name (DN) der Richtlinie an, die der Administrator diesem Benutzer als einwertiges Attribut zugewiesen hat.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-512">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-513">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-513">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e2c9a-514">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-514">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-515">msRTCSIP-MinPresenceSubscriptionTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-516">Dieses Attribut stellt das Timeout Fenster für das minimale Anwesenheits Abonnement dar.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-516">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-517">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-517">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-518">msRTCSIP-MinRegistrationTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-518">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-519">Dieses Attribut stellt das Timeout Fenster für die minimale Registrierung dar.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-519">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-520">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-520">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e2c9a-521">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-521">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-523">Dieses Attribut stellt das Timeout Fenster für das minimale Roaming-Datenabonnement dar.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-523">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-524">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-524">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e2c9a-525">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-525">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-526">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="e2c9a-526">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-527">Dieses Attribut wird verwendet, um das vom Front-End-Pool verwendete gespiegelte SQL Server-Back-End zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-527">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-528">Neu in lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-528">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-529">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="e2c9a-529">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-530">Dieses Attribut enthält Optionen und Flags zur Definition von Mobilitätseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-530">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-531">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-531">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-532">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="e2c9a-532">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-533">Dieses Attribut enthält den DN für ein mobilitätsrichtlinien Objekt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-533">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-534">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-534">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-535">msRTCSIP-NumDevicesPerUser (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-535">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-536">Dieses Attribut stellt die zulässige Anzahl von Geräten dar, auf denen ein Benutzer für die SIP-Kommunikation registrieren und die Anwesenheit abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-536">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-537">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-537">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e2c9a-538">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-538">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-539">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="e2c9a-539">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-540">Dieses Attribut gibt die Optionen an, die für das Benutzer-oder Kontaktobjekt aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-540">This attribute specifies the options that are enabled for the user or contact object.</span></span> <span data-ttu-id="e2c9a-541">Dieses Attribut ist ein Bitmaskenwert vom Typ Integer.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-541">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="e2c9a-542">Jede Option wird durch ein Bit dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-542">Each option is represented by a bit.</span></span> <span data-ttu-id="e2c9a-543">Dieses Attribut ist für die Replikation des globalen Katalogs gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-543">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="e2c9a-544">Die gültigen Werte (und zugeordneten Bit-Positionen) lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-544">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-545">1: für die Verbindung mit öffentlichen Sofortnachrichtendiensten (Bit-Position 0) aktiviert</span><span class="sxs-lookup"><span data-stu-id="e2c9a-545">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-546">2: reserviert (Bit-Position 1)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-546">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-547">4: reserviert (Bit-Position 2)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-547">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-548">8: reserviert (Bit-Position 3)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-548">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-549">16: Remote Anrufsteuerung aktiviert [Telefonie] (Bit-Position 4)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-549">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-550">64: AllowOrganizeMeetingWithAnonymousParticipants lautet (Benutzer können anonyme Benutzer zu Besprechungen einladen (Bit-Position 6)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-550">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-551">128: UCEnabled (Aktivieren von Benutzern für UC) (Bit-Position 7)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-551">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-552">256: EnabledForEnhancedPresence (Benutzer für öffentliche Chat Verbindungen aktivieren) (Bit-Position 8)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-552">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-553">512: RemoteCallControlDualMode (Bit-Position 9)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-553">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e2c9a-554">Neu in Live Communications Server 2005 mit SP1.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-554">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-555">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="e2c9a-555">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-556">Dieses Attribut wird in den Ressourcen-und zentralen Gesamtstruktur-Topologien verwendet, um einmaliges Anmelden zu aktivieren, wenn die Objekt-Nr eines Benutzers aus dem Windows NT Server-Prinzipal Konto in dieses Attribut des entsprechenden Benutzer-oder Kontaktobjekts in der Ressourcen-oder zentralen Gesamtstruktur kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-556">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="e2c9a-557">Communicator-Webzugriff sucht in AD DS mithilfe dieses Attributs oder der Objekt-Nr des Benutzers nach einem Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-557">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="e2c9a-558">Dieses Attribut ist für die Replikation des globalen Katalogs gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-558">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-559">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="e2c9a-559">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-560">Dieses Attribut ist der URN (Uniform Resource Name) des Besitzers für einen Anwendungs Kontakt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-560">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-561">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-561">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-562">msRTCSIP-Pattern (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-562">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-563">Dieses einwertige Zeichenfolgenattribut enthält ein Muster, das zum Zuordnen von Wähl Nummern zum E. 164-Format verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-563">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format.</span></span> <span data-ttu-id="e2c9a-564">Wenn die Wählnummer mit diesem Muster übereinstimmt, wird die Übersetzung auf die gewählte Nummer angewendet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-564">If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-565">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-565">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e2c9a-566">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-566">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-567">msRTCSIP-PhoneRouteBL (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-567">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-568">Dieses mehrwertige Attribut enthält eine Liste der Distinguished Names (DN) der Telefonroute.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-568">This multi-valued attribute contains a list of phone route distinguished names (DN).</span></span> <span data-ttu-id="e2c9a-569">Dieses Attribut gibt den hinteren Link zu einer oder mehreren Telefonrouten an.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-569">This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="e2c9a-570">Link zurück: <strong>Link ID 11033</strong></span><span class="sxs-lookup"><span data-stu-id="e2c9a-570">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="e2c9a-571">Dieses Attribut entspricht dem Forward-Link <strong>msRTCSIP-RouteUsageLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-571">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-572">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-572">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e2c9a-573">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-573">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-574">msRTCSIP-PhoneRouteData (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-574">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-575">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-575">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-576">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-576">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-577">msRTCSIP-PhoneRouteName (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-577">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-578">Dieses einfache Unicode-Zeichenfolgenattribut gibt den Anzeigenamen der Telefonroute an, sodass vom Administrator einfach auf ihn verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-578">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-579">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-579">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-580">msRTCSIP-PhoneUsageData (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-580">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-581">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-581">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-582">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-582">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e2c9a-583">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-583">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-584">msRTCSIP-PolicyContent (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-584">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-585">Dieses Attribut ist eine Unicode-Zeichenfolge mit einer einwertigen Wert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-585">This attribute is a single-valued Unicode string.</span></span> <span data-ttu-id="e2c9a-586">Dieses Zeichenfolgenattribut enthält die Richtliniendefinition im XML-Format.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-586">This string attribute contains the policy definition in XML format.</span></span> <span data-ttu-id="e2c9a-587">Die XML-Schema Definition ist in verschiedenen Richtlinientypen üblich, nur die Einstellungen unterscheiden sich für jeden Richtlinientyp.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-587">The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="e2c9a-588">Die XML-Schema Definition (XSD) ist wie folgt definiert:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-588">The XML schema definition (XSD) is defined as follows:</span></span></p>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;xs:schema id=&quot;instance&quot; xmlns=&quot;&quot; xmlns:xs=&quot;http://www.w3.org/2001/XMLSchema&quot; xmlns:msdata=&quot;urn:schemas-microsoft-com:xml-msdata&quot;&gt;
  &lt;xs:element name=&quot;instance&quot; msdata:IsDataSet=&quot;true&quot;&gt;
    &lt;xs:complexType&gt;
      &lt;xs:choice maxOccurs=&quot;unbounded&quot;&gt;
        &lt;xs:element name=&quot;property&quot; nillable=&quot;true&quot;&gt;
          &lt;xs:complexType&gt;
            &lt;xs:simpleContent msdata:ColumnName=&quot;property_Text&quot; msdata:Ordinal=&quot;1&quot;&gt;
              &lt;xs:extension base=&quot;xs:string&quot;&gt;
                &lt;xs:attribute name=&quot;name&quot; type=&quot;xs:string&quot; /&gt;
              &lt;/xs:extension&gt;
            &lt;/xs:simpleContent&gt;
          &lt;/xs:complexType&gt;
        &lt;/xs:element&gt;
      &lt;/xs:choice&gt;
    &lt;/xs:complexType&gt;
  &lt;/xs:element&gt;
&lt;/xs:schema&gt;</code></pre></td>
<td><p><span data-ttu-id="e2c9a-589">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-589">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e2c9a-590">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-590">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-591">msRTCSIP-Spalte PolicyData (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-591">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-592">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-592">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-593">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-593">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e2c9a-594">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-594">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-595">msRTCSIP-policyType (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-595">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-596">Dieses einwertige UNICODE-Zeichenfolgenattribut enthält den Richtlinientyp.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-596">This single-valued Unicode string attribute contains the policy type.</span></span> <span data-ttu-id="e2c9a-597">Gültige Richtlinientypen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-597">Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-598">Besprechungs</span><span class="sxs-lookup"><span data-stu-id="e2c9a-598">meeting</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-599">Telefonie</span><span class="sxs-lookup"><span data-stu-id="e2c9a-599">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e2c9a-600">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-600">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e2c9a-601">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-601">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-602">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="e2c9a-602">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-603">Dieses Attribut gibt einen Link zurück zu dem Pool, zu dem ein Computer gehört.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-603">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="e2c9a-604">Dieses Attribut wird unabhängig davon festgelegt, ob der Computer die Standard Edition oder die Enterprise Edition von lync Server ausführt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-604">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="e2c9a-605">Dieses Attribut ist für die Replikation des globalen Katalogs gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-605">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="e2c9a-606">Der gültige Wert ist der Domänenname des Pools.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-606">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="e2c9a-607">Link weiterleiten: <strong>Link ID 11022</strong></span><span class="sxs-lookup"><span data-stu-id="e2c9a-607">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="e2c9a-608">Die entsprechende Backlink to this Forward Link-Attribut ist <strong>msRTCSIP-FrontEndServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-608">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-609">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-609">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-610">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="e2c9a-610">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-611">Hierbei handelt es sich um ein mehrwertiges Attribut, das eine Liste der Distinguished Names (DN) von Pools enthält, mit denen die MCU-Factory verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-611">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="e2c9a-612">Link zurück: <strong>Link ID 11025</strong></span><span class="sxs-lookup"><span data-stu-id="e2c9a-612">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="e2c9a-613">Der entsprechende Weiterleitungslink zu diesem Rück Link ist <strong>msRTCSIP-MCUFactoryPath</strong>.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-613">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-614">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-614">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-615">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="e2c9a-615">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-616">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-616">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-617">Neu in Live Communications Server 2005 mit SP1.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-617">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-618">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="e2c9a-618">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-619">Dieses Attribut gibt einen beliebigen Namen für einen Pool an, der von der Verwaltungskonsole angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-619">This attribute specifies an arbitrary name for a pool that is displayed by the management console.</span></span> <span data-ttu-id="e2c9a-620">Dieser Name kann vom Administrator geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-620">This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="e2c9a-621">Der gültige Wert ist eine Zeichenfolge, die den Namen eines Pools darstellt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-621">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-622">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-622">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-623">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="e2c9a-623">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-624">Dieses Attribut ist ein einwertiger Zeichenfolgenwert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-624">This attribute is a single-valued string value.</span></span> <span data-ttu-id="e2c9a-625">Der Wert dieses Attributs stellt, sofern vorhanden, den Domänen-FQDN des Pools dar, wenn der Administrator eine Front-End-Pool mit einem FQDN erstellen möchte, der nicht der Active Directory Domänenstruktur entspricht, in der das Front-End-Pool erstellt wird (beispielsweise ein SIP-Namespace, der vom Domain Name System (DNS) Namespace abweicht).</span><span class="sxs-lookup"><span data-stu-id="e2c9a-625">The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="e2c9a-626">Es wird empfohlen, den Domänen-FQDN Front-End-Pool Domänennamen als Active Directory Domäne, in der sich der Pool befindet, dem Domänennamens Teil zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-626">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides.</span></span> <span data-ttu-id="e2c9a-627">Wenn in diesem Attribut kein Wert vorhanden ist, wird der Front-End-Pool-FQDN standardmäßig auf die Active Directory Domänennamenstruktur, wie durch das <strong>dNSHostName</strong> -Attribut gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-627">Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-628">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-628">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-629">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="e2c9a-629">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-630">Eine mehrwertige Liste der Domänennamen aller lync Server Enterprise Edition-Server, die einem Pool zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-630">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="e2c9a-631">Dieses Attribut vom Typ Integer definiert, ob der Pool Sofortnachrichten und Anwesenheitsinformationen und Besprechungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-631">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="e2c9a-632">Die möglichen gültigen Wertetypen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-632">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-633">Nicht definiert: Chat-und Anwesenheitsdienst (Live Communications Server 2005 und 2003)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-633">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-634">1: Chat und Anwesenheitsdienst (lync Server)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-634">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-635">2: Sofortnachrichten und Anwesenheits-und Besprechungs Dienst (lync Server)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-635">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e2c9a-636">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-636">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-637">msRTCSIP-pooltype</span><span class="sxs-lookup"><span data-stu-id="e2c9a-637">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-638">Dieses Attribut gibt an, ob ein Serverpool Standard Edition-Server oder Enterprise Edition-Server ausführt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-638">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server.</span></span> <span data-ttu-id="e2c9a-639">Dieses Attribut ist ein Bitmaskenwert vom Typ Integer.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-639">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="e2c9a-640">Jede Option wird durch ein Bit dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-640">Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="e2c9a-641">Die gültigen Werte (und zugeordneten Bit-Positionen) lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-641">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-642">1: Standard Edition-Server, hostet Benutzer (Bit-Position 0)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-642">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-643">2: Enterprise Edition-Server, hostet Benutzer (Bit-Position 1)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-643">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-644">4: Standard Edition-Server, hostet Anwendungen (Bit-Position 2)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-644">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-645">8: Enterprise Edition-Server, hostet Anwendungen (Bit-Position 3)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-645">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="e2c9a-646">Da lync Server keine Pools unterstützt, die nur Anwendungen hosten, gelten die folgenden Werte nur:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-646">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-647">5: Standard Edition-Server, hostet Benutzer und Anwendungen (Bit-Positionen 0 und 2)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-647">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-648">10: Enterprise Edition-Server, hostet Benutzer und Anwendungen (Bit-Positionen 1 und 3)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-648">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e2c9a-649">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-649">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-650">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="e2c9a-650">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-651">Dieses Attribut definiert die Pool Version.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-651">This attribute defines the pool version.</span></span> <span data-ttu-id="e2c9a-652">Es handelt sich um einen ganzzahligen Typ, der mit jeder Hauptprodukt Version inkrementiert wird.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-652">It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="e2c9a-653">Die möglichen gültigen Wertetypen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-653">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-654">0: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="e2c9a-654">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-655">1: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="e2c9a-655">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-656">2: Live Communications Server 2005 mit SP1</span><span class="sxs-lookup"><span data-stu-id="e2c9a-656">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-657">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="e2c9a-657">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-658">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="e2c9a-658">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-659">5: lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e2c9a-659">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e2c9a-660">Live Communications Server 2005 mit SP1.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-660">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-661">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="e2c9a-661">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-662">Dieses Attribut enthält Optionen und Flags, die Anwesenheitseinstellungen definieren.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-662">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-663">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-663">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-664">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="e2c9a-664">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-665">Dieses Attribut enthält den DN für ein Präsenz Richtlinienobjekt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-665">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-666">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-666">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-667">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="e2c9a-667">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-668">Dieses Attribut aktiviert einen Benutzer oder Kontakt für SIP-Messaging.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-668">This attribute enables a user or contact for SIP messaging.</span></span> <span data-ttu-id="e2c9a-669">Sie wird der Contact-Klasse hinzugefügt, da in der Topologie der zentralen Gesamtstruktur Kontaktobjekte und keine Benutzerobjekte SIP-aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-669">It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="e2c9a-670">Der gültige Wert ist der DN der Standard Edition-Server-oder Enterprise Edition-Front-End-Pool, in der ein Benutzer verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-670">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-671">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-671">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-672">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="e2c9a-672">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-673">Dieses Attribut enthält die SIP-Adresse eines bestimmten Benutzers.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-673">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-674">msRTCSIP-Privatsphäre</span><span class="sxs-lookup"><span data-stu-id="e2c9a-674">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-675">Dieses Attribut enthält die Geräte-ID des privaten Leitungen-Geräts.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-675">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-676">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-676">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-677">msRTCSIP – routingfähig</span><span class="sxs-lookup"><span data-stu-id="e2c9a-677">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-678">Dieses Attribut ist ein boolesches Attribut, das verwendet wird, um zu bestimmen, ob lync Server berechtigt ist, zu diesem Dienst unter Verwendung seiner GRUU-Adresse weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-678">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="e2c9a-679">Wenn dieser Wert auf <strong>true</strong>festgelegt ist, ist lync Server berechtigt, zu diesem Dienst weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-679">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="e2c9a-680">Wenn dieser Wert auf " <strong>false</strong>" festgelegt ist, ist lync Server nicht berechtigt, zu diesem Dienst weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-680">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-681">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-681">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-682">msRTCSIP-RouteUsageAttribute (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-682">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-683">Dieses einwertige UNICODE-Zeichenfolgenattribut definiert ein Attribut, das die Verwendung für eine Telefonroute qualifiziert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-683">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route.</span></span> <span data-ttu-id="e2c9a-684">Die Auswahl einer Telefonroute wird basierend auf zwei Elementen bestimmt: dem Verwendungsattribut, das der Telefonroute zugewiesen ist, und den zulässigen Richtlinien Verwendungsattributen des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-684">Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes.</span></span> <span data-ttu-id="e2c9a-685">Die erste Telefonroute mit einem Nutzungs Attribut, das mit der zulässigen Verwendung des Anrufers übereinstimmt, wird ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-685">The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-686">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-686">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e2c9a-687">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-687">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-688">msRTCSIP-RouteUsageLinks (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-688">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-689">Dieses mehrwertige Distinguished Name (DN)-Attribut enthält eine Liste der definierten Namen für die Routenverwendung.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-689">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="e2c9a-690">Link weiterleiten: <strong>Link ID 11032</strong></span><span class="sxs-lookup"><span data-stu-id="e2c9a-690">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="e2c9a-691">Dieses Attribut ist eine Weiterleitungs Verknüpfung mit der entsprechenden <strong>msRTCSIP-PhoneRouteBL-</strong>Back Link.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-691">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-692">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-692">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-693">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="e2c9a-693">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-694">Dieses Attribut enthält den DN, der auf den Pool zeigt, für den der gesamte an diesen MCU-oder vertrauenswürdigen Dienst adressierte SIP-Datenverkehr durchlaufen werden muss.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-694">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-695">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-695">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-696">msRTCSIP-RuleName (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-696">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-697">Dieses einwertige UNICODE-Zeichenfolgenattribut gibt den Anzeigenamen der Normalisierungsregel an, sodass von einem Administrator einfach auf ihn verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-697">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-698">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-698">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e2c9a-699">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-699">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-700">msRTCSIP-Schemaversion</span><span class="sxs-lookup"><span data-stu-id="e2c9a-700">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-701">Dieses Attribut stellt die derzeit in der Organisation bereitgestellte Schemaversion dar.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-701">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-702">msRTCSIP-SearchMaxRequests (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-702">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-703">Dieses Attribut schränkt die Anzahl der Suchergebnisse ein, die von einer Verzeichnissuche zurückgegeben werden, wenn ein Benutzer einen Kontakt mithilfe von Communicator sucht.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-703">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="e2c9a-704">Dieses Attribut setzt den vom Client bereitgestellten Wert außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-704">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-705">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-705">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-706">msRTCSIP-SearchMaxResults (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-706">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-707">Dieses Attribut schränkt die Anzahl der zurückgegebenen Suchanforderungen ein.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-707">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-708">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-708">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-709">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="e2c9a-709">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-710">Dieses mehrwertige Attribut ist ein Link zurück, der eine Liste mit Distinguished Names (DN) enthält.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-710">This multi-valued attribute is a back link that contains a list of distinguished names (DN).</span></span> <span data-ttu-id="e2c9a-711">Diese DNS verweist auf ein Pool-oder <strong>TrustedService</strong> -Objekt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-711">These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="e2c9a-712">Dieses Attribut entspricht dem Forward-Link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-712">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-713">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-713">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-714">msRTCSIP-Server</span><span class="sxs-lookup"><span data-stu-id="e2c9a-714">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-715">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-715">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-716">msRTCSIP-ServerReferenceBL (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-716">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-717">Dieses mehrwertige Attribut enthält eine Liste mit Distinguished Names.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-717">This multi-valued attribute contains a list of distinguished names.</span></span> <span data-ttu-id="e2c9a-718">Diese Distinguished Names sind Back Links, die auf andere Serverobjekte verweisen, denen ein Standardmäßiges Standortprofil zugewiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-718">These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="e2c9a-719">Link zurück: <strong>Link ID 11037</strong></span><span class="sxs-lookup"><span data-stu-id="e2c9a-719">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="e2c9a-720">Der entsprechende Weiterleitungslink zu diesem Rück Link ist <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-720">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="e2c9a-721">Dieses Back Link-Attribut verweist nur auf Pools und Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-721">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-722">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-722">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e2c9a-723">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-723">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-724">msRTCSIP-Server Version vom</span><span class="sxs-lookup"><span data-stu-id="e2c9a-724">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-725">Dieses Attribut definiert die Versionsinformationen des Servers.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-725">This attribute defines the version information of the server.</span></span> <span data-ttu-id="e2c9a-726">Diese Versionsnummer gilt für alle Serverrollen.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-726">This version number applies to all server roles.</span></span> <span data-ttu-id="e2c9a-727">Es handelt sich um eine monoton wachsende ganze Zahl, die mit jeder offiziellen Produktversion inkrementiert wird.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-727">It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="e2c9a-728">Die möglichen gültigen Werte lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-728">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-729">Undefined: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="e2c9a-729">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="e2c9a-730">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="e2c9a-730">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="e2c9a-731">                 Live Communications Server 2005 mit SP1</span><span class="sxs-lookup"><span data-stu-id="e2c9a-731">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-732">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="e2c9a-732">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-733">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="e2c9a-733">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-734">5: lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e2c9a-734">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-735">6: lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2c9a-735">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e2c9a-736">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-736">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-737">msRTCSIP-Quellobjekttyp</span><span class="sxs-lookup"><span data-stu-id="e2c9a-737">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-738">Dieses einwertige Attribut vom Typ Integer gibt den Typ des Objekts an, auf das das <strong>msDS-SourceObjectDN</strong> zeigt, wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-738">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-739">NULL | 0x00000001: stellt ein Windows NT Server-Prinzipal Benutzerobjekt aus einer anderen Gesamtstruktur dar.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-739">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-740">Die folgenden Attribute stellen einen Gruppentyp aus einer anderen Gesamtstruktur für die Erweiterung der Verteilergruppe dar:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-740">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="e2c9a-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="e2c9a-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="e2c9a-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="e2c9a-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="e2c9a-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-746">0x90000000: stellt eine automatische Telefonzentrale oder ein Teilnehmerzugriffs Objekt aus derselben Gesamtstruktur oder einer anderen Gesamtstruktur dar.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-746">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="e2c9a-747">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-747">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-748">msRTCSIP-SubscriptionAuthRequired (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-748">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e2c9a-749">Neu in Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-749">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="e2c9a-750">In Live Communications Server 2005 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-750">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-751">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="e2c9a-751">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-752">Mit diesem Attribut können Sie ein Benutzer-oder Kontaktobjekt von einem lync Server Pool in einen anderen migrieren.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-752">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="e2c9a-753">Dieses Attribut wird der Contact-Klasse hinzugefügt, da in der zentralen Gesamtstruktur-Topologie Kontaktobjekte und keine Benutzerobjekte SIP-aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-753">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="e2c9a-754">Der gültige Wert ist der DN des Ziel Standard Edition-Server oder Front-End-Pool, zu dem ein Benutzer verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-754">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-755">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-755">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-756">msRTCSIP-TargetPhoneNumber (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-756">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-757">Dieses einwertige Zeichenfolgenattribut enthält ein Telefonnummernmuster oder einen Bereich, der an die in <strong>msRTCSIP-Gateways</strong>definierten Gateways weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-757">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-758">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-758">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-759">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="e2c9a-759">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-760">Dieses Attribut speichert Name/Wert-Paare für Zielrichtlinien für lync Server Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-760">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-761">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-761">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-762">msRTCSIP-Mandanten-Nr</span><span class="sxs-lookup"><span data-stu-id="e2c9a-762">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-763">Dieses Attribut speichert den eindeutigen Bezeichner für einen Mandanten.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-763">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-764">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-764">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-765">msRTCSIP-Translation (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-765">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-766">Dieses Attribut wird von der VoIP-Funktion von lync Server verwendet und enthält die Übersetzungs Zeichenfolge, die für die gewählte Nummer angewendet wird, wenn eine Übereinstimmung gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-766">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-767">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-767">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e2c9a-768">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-768">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-769">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="e2c9a-769">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-770">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-770">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-771">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-771">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-772">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="e2c9a-772">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-773">Dieses Attribut ist ein String-Wert, der den FQDN der MCU enthält.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-773">This attribute is a string value that contains the FQDN of the MCU.</span></span> <span data-ttu-id="e2c9a-774">Hierbei handelt es sich um ein einwertiges Attribut.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-774">This is a single-valued attribute.</span></span> <span data-ttu-id="e2c9a-775">Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN beträgt 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-775">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-776">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-776">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-777">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="e2c9a-777">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-778">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-778">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-779">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-779">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-780">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="e2c9a-780">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-781">Dieses Attribut ist ein String-Wert, der den FQDN des Servers mit Proxy Server enthält.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-781">This attribute is a string value that contains the FQDN of the server running Proxy Server.</span></span> <span data-ttu-id="e2c9a-782">Dieses Attribut ist ein einwertiger Wert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-782">This attribute is single-valued.</span></span> <span data-ttu-id="e2c9a-783">Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN beträgt 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-783">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-784">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-784">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-785">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="e2c9a-785">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-786">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-786">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-787">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="e2c9a-787">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-788">Dieses Attribut ist ein Attribut mit einem Wert, das den FQDN eines vertrauenswürdigen Servers darstellt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-788">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-789">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-789">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-790">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="e2c9a-790">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-791">Dieses Attribut gibt die Versionsnummer eines Servers in der Liste der vertrauenswürdigen Server an.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-791">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="e2c9a-792">Die möglichen gültigen Werte lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-792">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-793">NULL: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="e2c9a-793">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-794">2: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="e2c9a-794">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-795">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="e2c9a-795">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-796">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="e2c9a-796">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-797">5: lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e2c9a-797">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-798">6: lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2c9a-798">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e2c9a-799">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-799">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-800">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="e2c9a-800">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-801">Dieses Attribut definiert die Optionen, die für den vertrauenswürdigen Dienst aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-801">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-802">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-802">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-803">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="e2c9a-803">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-804">Dieses mehrwertige Attribut enthält eine Liste mit Distinguished Names (DN), die auf ein vertrauenswürdiges Dienstobjekt verweisen, beispielsweise einen Medien Relay-Authentifizierungsdienst.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-804">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="e2c9a-805">Ein Medien Relay-Authentifizierungsdienst (physisch zusammen mit dem Edgeserver, auf dem der A/V-Konferenzdienst ausgeführt wird) muss einem Pool zugeordnet sein, um audioszenarioe für Remotebenutzer zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-805">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="e2c9a-806">Die entsprechende Backlink to this Forward Link-Attribut ist <strong>msRTCSIP-ServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-806">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-807">UC</span><span class="sxs-lookup"><span data-stu-id="e2c9a-807">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-808">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="e2c9a-808">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-809">Dieses Attribut ist eine ganze Zahl, die die Portnummer definiert, die zum Herstellen einer Verbindung mit diesem GRUU-Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-809">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-810">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-810">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-811">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="e2c9a-811">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-812">Dieses Attribut ist ein String-Wert, der den Typ des GRUU-Diensts definiert, den er darstellt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-812">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="e2c9a-813">Die gültigen GRUU-Diensttypen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-813">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-814">MediationServer</span><span class="sxs-lookup"><span data-stu-id="e2c9a-814">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-815">Gateway</span><span class="sxs-lookup"><span data-stu-id="e2c9a-815">Gateway</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-816">Medien Relay-Authentifizierungsdienst (MRAS)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-816">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-817">QoSM</span><span class="sxs-lookup"><span data-stu-id="e2c9a-817">QoSM</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-818">msRTCSIP-UserExtension-GAV</span><span class="sxs-lookup"><span data-stu-id="e2c9a-818">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e2c9a-819">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-819">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-820">msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="e2c9a-820">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-821">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-821">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-822">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-822">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-823">msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="e2c9a-823">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-824">Dieses Attribut ist ein String-Wert, der den FQDN des IIS-lync Server Webdienste enthält.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-824">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="e2c9a-825">Hierbei handelt es sich um ein einwertiges Attribut.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-825">This is a single-valued attribute.</span></span> <span data-ttu-id="e2c9a-826">Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN beträgt 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-826">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-827">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-827">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-828">msRTCSIP-UCFlags (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-828">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-829">Dieses Attribut definiert unterschiedliche UC-Optionen, die Global für alle Benutzer-oder Kontaktobjekte aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-829">This attribute defines different UC options that are enabled globally to all user or contact objects.</span></span> <span data-ttu-id="e2c9a-830">Dieses Attribut ist ein Bitmaskenwert des Typs Integer.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-830">This attribute is a bit-mask value of integer type.</span></span> <span data-ttu-id="e2c9a-831">Jede Option wird durch das vorhanden sein von ein Bit dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-831">Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="e2c9a-832">Der mögliche gültige Wert (und die zugehörige Bit-Position) lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-832">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-833">4: UsePerUserUCPolicy (Bit-Position 2)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-833">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="e2c9a-834">Wenn dieses Bit festgelegt ist, wird die UC-Richtlinie pro Benutzerdefiniert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-834">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-835">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-835">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-836">msRTCSIP-UCPolicy (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-836">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-837">Dieses einwertige Attribut enthält den Distinguished Name (DN) der UC-Richtlinie, die der Administrator diesem Benutzer zugewiesen hat.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-837">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-838">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-838">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-839">msRTCSIP-UserDomainList (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-839">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-840">Dieses Attribut enthält eine Liste aller Domänen in einer Gesamtstruktur, die SIP-aktivierte Benutzer hosten.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-840">This attribute provides a list of all the domains in a forest that host SIP-enabled users.</span></span> <span data-ttu-id="e2c9a-841">Der Standardwert ist eine leere Liste, die angibt, dass alle Domänen in der Gesamtstruktur SIP-fähig sind.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-841">The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="e2c9a-842">Gültige Werte sind mehrere Zeichenfolgen, die die Domänennamen einzelner Domänen darstellen.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-842">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-843">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-843">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e2c9a-844">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-844">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-845">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="e2c9a-845">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-846">Dieses Attribut bestimmt, ob der Benutzer derzeit für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-846">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-847">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="e2c9a-847">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-848">Dieses mehrwertige Attribut enthält eine Liste von Name-Wert-Paaren im Format von &quot; Name = Value. &quot; Dieses Attribut ist für die Replikation des globalen Katalogs gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-848">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-849">Neu in Live Communications Server 2005 mit SP1.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-849">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-850">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="e2c9a-850">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-851">Dieses Attribut enthält den Distinguished Name (DN), der auf ein Standortprofilobjekt zeigt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-851">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-852">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-852">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-853">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="e2c9a-853">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-854">Dieses Attribut speichert Name/Wert-Paare für Benutzerrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-854">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-855">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-855">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-856">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="e2c9a-856">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-857">Hierbei handelt es sich um ein mehrwertiges Attribut mit einer Liste von Distinguished Names with Binary (DN_WITH_BINARY), die auf globale Benutzerrichtlinien verschiedener Typen verweist.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-857">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types.</span></span> <span data-ttu-id="e2c9a-858">Der binäre Teil gibt den Typ der Richtlinie an, auf die der DN-Teil zeigt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-858">The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="e2c9a-859">Die gültigen binären Werte lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-859">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-860">0x00000001: Besprechungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="e2c9a-860">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-861">0x00000002: UC-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="e2c9a-861">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-862">0x00000005: Anwesenheitsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="e2c9a-862">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e2c9a-863">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-863">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-864">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="e2c9a-864">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-p165">Dies ist die SIP-Routinggruppen-ID. Benutzer in derselben Gruppe registrieren sich beim selben Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-p165">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-867">Neu in lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-867">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-868">msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="e2c9a-868">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-869">Hierbei handelt es sich um ein mehrwertiges Attribut.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-869">This is a multi-valued attribute.</span></span> <span data-ttu-id="e2c9a-870">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-870">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-871">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-871">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-872">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="e2c9a-872">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-873">Dieses einwertige Attribut verweist auf den Pool oder Standard Edition-Server, zu dem die Webkomponenten gehören.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-873">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="e2c9a-874">Link weiterleiten: <strong>Link ID 11028</strong></span><span class="sxs-lookup"><span data-stu-id="e2c9a-874">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="e2c9a-875">Die entsprechende Backlink to this Forward Link-Attribut ist <strong>msRTCSIP-WebComponentsServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-875">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-876">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-876">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-877">msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="e2c9a-877">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-878">Dieses Attribut ist eine mehrwertige Liste mit Distinguished Names.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-878">This attribute is a multi-valued list of distinguished names.</span></span> <span data-ttu-id="e2c9a-879">Dieses Attribut enthält eine Liste aller Webserver, die diesem Pool zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-879">This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="e2c9a-880">Link zurück: <strong>Link ID 11029</strong></span><span class="sxs-lookup"><span data-stu-id="e2c9a-880">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="e2c9a-881">Der entsprechende Weiterleitungslink zu diesem Rück Link ist <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-881">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-882">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-882">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-883">msRTCSIP-WMIInstanceId (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e2c9a-883">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e2c9a-884">Neu in Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-884">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="e2c9a-885">In Live Communications Server 2005 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-885">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-886">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="e2c9a-886">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-887">Dieses vorhandene Active Directory-Attribut wird von der Telefonie verwendet, um die Liste der alternativen TCP/IP-Adressen für ein Telefon anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-887">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-888">Neu in Windows Server 2008 Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-888">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-889">PhoneOfficeOther</span><span class="sxs-lookup"><span data-stu-id="e2c9a-889">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-890">Dieses vorhandene Active Directory Attribut wird von den VoIP-Komponenten in lync Server nur für Kontaktobjekte verwendet, um Anrufe an die automatische Telefonzentrale und Teilnehmerzugriffsnummern weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-890">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="e2c9a-891">Die bedingungslose Anruf Weiterleitungsadresse wird in diesem mehrwertigen Attribut gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-891">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="e2c9a-892">Dieses Konto wird für den speziellen Zweck der automatischen Telefonzentrale und des Teilnehmerzugriffs erstellt.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-892">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="e2c9a-893">Die Attribute dieses Kontos sollten von Administratoren nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-893">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-894">Neu im Betriebssystem Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-894">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2c9a-895">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="e2c9a-895">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-896">Dieses vorhandene Active Directory mehrwertige Attribut ist Teil des grundlegenden Active Directory Schemas, das in Windows 2000 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-896">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="e2c9a-897">Dieses Attribut enthält die verschiedenen X400-, x500-und SMTP-Adressen der e-Mail-Adresse des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-897">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="e2c9a-898">In Live Communications Server 2003 und höher wird der SIP-URI des Benutzers mithilfe des SIP:-Tags zu dieser Liste hinzugefügt &quot; &quot; .</span><span class="sxs-lookup"><span data-stu-id="e2c9a-898">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="e2c9a-899">Die folgenden Anwendungen durchsuchen den SIP-URI des Benutzers aus diesem Attribut:</span><span class="sxs-lookup"><span data-stu-id="e2c9a-899">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="e2c9a-900">Microsoft Office Outlook 2003 Messaging-und Zusammenarbeitsclient</span><span class="sxs-lookup"><span data-stu-id="e2c9a-900">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="e2c9a-901">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="e2c9a-901">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e2c9a-902">Neu im Betriebssystem Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-902">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2c9a-903">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="e2c9a-903">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-904">Dieses vorhandene Active Directory-Attribut enthält die Telefonnummer für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-904">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="e2c9a-905">Neu im Betriebssystem Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="e2c9a-905">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

