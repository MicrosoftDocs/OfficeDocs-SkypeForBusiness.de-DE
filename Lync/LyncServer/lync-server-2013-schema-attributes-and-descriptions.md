---
title: 'Lync Server 2013: Schema Attribute und-Beschreibungen'
description: 'Lync Server 2013: Schema Attribute and Descriptions.'
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
ms.openlocfilehash: 18888d20a772b3e84970e7d874bd6b6964affc75
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557191"
---
# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="e8720-103">Schema Attribute und-Beschreibungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8720-103">Schema attributes and descriptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8720-104">_**Letztes Änderungsstand des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="e8720-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="e8720-105">In diesem Abschnitt werden alle Schema Attribute beschrieben, die von lync Server 2013 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e8720-105">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="e8720-106">Informationen zu den Klassen, die Attributen zugeordnet sind, finden Sie unter [Schema Attribute by class in lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="e8720-106">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="e8720-107">Eine Liste der Klassen und Attribute, die neu in lync Server 2013 sind, finden Sie unter [Schema Changes in lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="e8720-107">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="e8720-108">Attribute, bei denen es sich um verknüpfte Paare handelt, werden als Weiterleitungslinks oder als Backlinks angegeben.</span><span class="sxs-lookup"><span data-stu-id="e8720-108">Attributes that are linked pairs are specified as forward links or back links.</span></span> <span data-ttu-id="e8720-109">Ein Attribut, das auf ein anderes Objekt verweist, ist eine Weiterleitungsverbindung; das Attribut des anderen Objekts, das auf das erste Objekt zurückverweist, ist eine Rückverknüpfung.</span><span class="sxs-lookup"><span data-stu-id="e8720-109">An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link.</span></span> <span data-ttu-id="e8720-110">Weiterleitungslinks sind aktualisierbar, während Rück Verknüpfungen schreibgeschützt sind.</span><span class="sxs-lookup"><span data-stu-id="e8720-110">Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="e8720-111">Einige Attribute weisen einen Bitmaskenwert auf.</span><span class="sxs-lookup"><span data-stu-id="e8720-111">Some attributes have a bit-mask value.</span></span> <span data-ttu-id="e8720-112">Für diese Attribute wird jede Einstellung durch ein Bit dargestellt, und der angezeigte Dezimalwert stellt die Bit-Position dar.</span><span class="sxs-lookup"><span data-stu-id="e8720-112">For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position.</span></span> <span data-ttu-id="e8720-113">Bit-Positionen beginnen mit Bit 0.</span><span class="sxs-lookup"><span data-stu-id="e8720-113">Bit positions start with bit 0.</span></span> <span data-ttu-id="e8720-114">Beispiel: 1 (binär) ist Bit 0 und 10000 (binär) ist Bit 4 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e8720-114">For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set.</span></span> <span data-ttu-id="e8720-115">Jedes Bit stellt eine Eigenschaft dar.</span><span class="sxs-lookup"><span data-stu-id="e8720-115">Each bit represents a property.</span></span> <span data-ttu-id="e8720-116">Im Folgenden finden Sie einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="e8720-116">The following are some examples:</span></span>

  - <span data-ttu-id="e8720-117">10000 (Binary) hat den Dezimalwert 16 (das heißt, Bit 4 ist festgelegt).</span><span class="sxs-lookup"><span data-stu-id="e8720-117">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="e8720-118">100 Millionen (binär) hat den Dezimalwert 256 (das heißt, Bit 8 ist festgelegt).</span><span class="sxs-lookup"><span data-stu-id="e8720-118">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="e8720-119">1100 (Binary) hat den Dezimalwert 12 (d. r., Bits 2 und 3 sind festgelegt; die durch beide Bits dargestellten Eigenschaften sind aktiviert).</span><span class="sxs-lookup"><span data-stu-id="e8720-119">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="e8720-120">1111000001 (Binary) hat den Dezimalwert 961 (d. r., Bits 0, 6, 7, 8 und 9 sind festgelegt; Eigenschaften für jedes dieser Bits sind aktiviert).</span><span class="sxs-lookup"><span data-stu-id="e8720-120">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="e8720-121">Schema Attribute für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8720-121">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8720-122">Attribut</span><span class="sxs-lookup"><span data-stu-id="e8720-122">Attribute</span></span></th>
<th><span data-ttu-id="e8720-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8720-123">Description</span></span></th>
<th><span data-ttu-id="e8720-124">Kommentare</span><span class="sxs-lookup"><span data-stu-id="e8720-124">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8720-125">DNSHostName</span><span class="sxs-lookup"><span data-stu-id="e8720-125">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="e8720-126">Ein vorhandenes Attribut in Active Directory-Domänendienste, das nun den Klassen <strong>msRTCSIP-Pool</strong> und <strong>msRTCSIP-MonitoringServer</strong> zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="e8720-126">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="e8720-127">Dieses Attribut gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) eines Pools oder Monitoring Server an.</span><span class="sxs-lookup"><span data-stu-id="e8720-127">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="e8720-128">Ein gültiger Wert für jedes Segment ist 63 Zeichen; ein gültiger Wert für den gesamten FQDN ist 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e8720-128">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="e8720-129">Neu in Microsoft Office Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8720-129">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-130">MSDS-SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="e8720-130">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="e8720-131">Dieses Attribut enthält die Zeichenfolgendarstellung des Distinguished Name (DN) des Objekts in einer anderen Gesamtstruktur, die diesem Objekt entspricht.</span><span class="sxs-lookup"><span data-stu-id="e8720-131">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object.</span></span> <span data-ttu-id="e8720-132">Dieses Attribut wird für die Expansion von Verteilergruppen und die automatische Teilnahme verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8720-132">This attribute is used for distribution group expansion and auto attendance.</span></span> <span data-ttu-id="e8720-133">Dieses Attribut ist im Standard Active Directory Schema für Windows Server 2003 R2 definiert.</span><span class="sxs-lookup"><span data-stu-id="e8720-133">This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="e8720-134">Um zu vermeiden, dass ein Upgrade von AD DS auf Windows Server 2003 R2 erforderlich ist, erweitert Active Directory Schemavorbereitung das Windows Server 2003 Schema mit dieser Attributdefinition.</span><span class="sxs-lookup"><span data-stu-id="e8720-134">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="e8720-135">Neu in Microsoft Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-135">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-136">"msexchucvoicemailsettings"</span><span class="sxs-lookup"><span data-stu-id="e8720-136">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="e8720-137">Dieses mehrwertige Attribut umfasst Einstellungen für Voicemail.</span><span class="sxs-lookup"><span data-stu-id="e8720-137">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="e8720-138">Dieses Attribut ist für Exchange Unified Messaging (um) freigegeben.</span><span class="sxs-lookup"><span data-stu-id="e8720-138">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="e8720-139">Neu in Microsoft lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8720-139">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-140">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="e8720-140">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="e8720-141">Dieses mehrwertige Attribut enthält Bezeichner für Aufbewahrungsrichtlinien, die für den Benutzer gelten.</span><span class="sxs-lookup"><span data-stu-id="e8720-141">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="e8720-142">Mit Aufbewahrungsrichtlinien werden für den Benutzer Postfachelemente für die Dauer der Aufbewahrung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e8720-142">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="e8720-143">Dieses Attribut ist für Exchange 2013 freigegeben.</span><span class="sxs-lookup"><span data-stu-id="e8720-143">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="e8720-144">Neu in lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8720-144">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-145">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="e8720-145">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="e8720-146">Dieses Attribut speichert Informationen zu Audiokonferenz-Anbietern für einen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e8720-146">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="e8720-147">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8720-147">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-148">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="e8720-148">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="e8720-149">Dieses Attribut verweist auf den vertrauenswürdigen Diensteintrag für den Anwendungs Kontakt.</span><span class="sxs-lookup"><span data-stu-id="e8720-149">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="e8720-150">Neu in Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8720-150">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-151">msRTCSIP-applicationlist</span><span class="sxs-lookup"><span data-stu-id="e8720-151">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="e8720-152">Dieses Attribut enthält eine Liste der gehosteten Anwendungen auf dem Anwendungsserver.</span><span class="sxs-lookup"><span data-stu-id="e8720-152">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="e8720-153">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8720-153">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-154">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="e8720-154">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="e8720-155">Dieses Attribut gibt die Optionen für den Anwendungs Kontakt an.</span><span class="sxs-lookup"><span data-stu-id="e8720-155">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="e8720-156">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8720-156">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-157">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="e8720-157">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="e8720-158">Dieses Attribut enthält die primäre Sprache für den Anwendungs Kontakt.</span><span class="sxs-lookup"><span data-stu-id="e8720-158">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="e8720-159">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8720-159">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-160">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="e8720-160">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="e8720-161">Dieses Attribut mit mehreren Werten enthält die sekundären Sprachen für den Anwendungs Kontakt.</span><span class="sxs-lookup"><span data-stu-id="e8720-161">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="e8720-162">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8720-162">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-163">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="e8720-163">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="e8720-164">Dieses Attribut enthält eine Liste der Anwendungsserver, die zu diesem Pool gehören.</span><span class="sxs-lookup"><span data-stu-id="e8720-164">This attribute contains a list of application servers that belong to this pool.</span></span> <span data-ttu-id="e8720-165">Der entsprechende Weiterleitungslink zu diesem Backlink <strong>-Attribut lautet msRTCSIP-ApplicationServerPoolLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8720-165">The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8720-166">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8720-166">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-167">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="e8720-167">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="e8720-168">Dieses Attribut verweist auf den Pool, zu dem dieser Anwendungsserver gehört.</span><span class="sxs-lookup"><span data-stu-id="e8720-168">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="e8720-169">Dies ist der Weiterleitungslink.</span><span class="sxs-lookup"><span data-stu-id="e8720-169">This is the forward link.</span></span> <span data-ttu-id="e8720-170">Der entsprechende abwärts Link ist <strong>msRTCSIP-ApplicationServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8720-170">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8720-171">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8720-171">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-172">msRTCSIP-ArchiveDefault (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-172">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e8720-173">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8720-173">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e8720-174">In Office Communications Server 2007 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-174">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-175">msRTCSIP-ArchiveDefaultFlags (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-175">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-176">Dieses Attribut gibt den globalen Standardwert innerhalb der Gesamtstrukturgrenze für die Archivierung der gesamten Benutzerkommunikation an.</span><span class="sxs-lookup"><span data-stu-id="e8720-176">This attribute specifies the global default within the forest boundary for archiving all user communications.</span></span> <span data-ttu-id="e8720-177">Dies wird durch die Archivierungs-Agent-Schicht erzwungen.</span><span class="sxs-lookup"><span data-stu-id="e8720-177">This is enforced by the archiving agent layer.</span></span> <span data-ttu-id="e8720-178">Der Wertebereich für dieses Attribut lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e8720-178">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-179"><strong>True</strong>: Archivieren aller Benutzer</span><span class="sxs-lookup"><span data-stu-id="e8720-179"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="e8720-180"><strong>False</strong>: nicht alle Benutzer archivieren</span><span class="sxs-lookup"><span data-stu-id="e8720-180"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="e8720-181">Dieses Attribut steuert Global innerhalb der Gesamtstruktur Begrenzung, wie die Benutzerkommunikation innerhalb eines internen Netzwerks archiviert wird.</span><span class="sxs-lookup"><span data-stu-id="e8720-181">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="e8720-182"><strong>Live Communications Server 2005 Verhalten (jetzt veraltet)</strong></span><span class="sxs-lookup"><span data-stu-id="e8720-182"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="e8720-183">Der Wertebereich für dieses Attribut lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e8720-183">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-184">0: Nachrichtentext archivieren [Bit 0]</span><span class="sxs-lookup"><span data-stu-id="e8720-184">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="e8720-185">1: Nachrichtentext nicht archivieren [Bit 0]</span><span class="sxs-lookup"><span data-stu-id="e8720-185">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="e8720-186"><strong>Office Communications Server 2007 Verhalten</strong></span><span class="sxs-lookup"><span data-stu-id="e8720-186"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="e8720-187">Der Wertebereich für dieses Attribut lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e8720-187">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-188">0: ArchiveFederationDefaultWithoutBody (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-188">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="e8720-189">1-2: ArchiveInternalCommunications</span><span class="sxs-lookup"><span data-stu-id="e8720-189">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="e8720-190">3-4: ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="e8720-190">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="e8720-191">5: RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="e8720-191">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="e8720-192">6: RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="e8720-192">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="e8720-193">7: RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="e8720-193">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="e8720-194">8: RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="e8720-194">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="e8720-195">9: RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="e8720-195">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="e8720-196">10: RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="e8720-196">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="e8720-197">11: RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="e8720-197">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="e8720-198">12: RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="e8720-198">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="e8720-199">13: RecordMeetingInstantiations</span><span class="sxs-lookup"><span data-stu-id="e8720-199">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="e8720-200">14: RecordMeetingJoins</span><span class="sxs-lookup"><span data-stu-id="e8720-200">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="e8720-201">15: RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="e8720-201">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="e8720-202">16: RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="e8720-202">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8720-203">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8720-203">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e8720-204">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-204">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-205">msRTCSIP-ArchiveFederationDefault (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-205">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e8720-206">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8720-206">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e8720-207">In Office Communications Server 2007 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-207">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-208">msRTCSIP-ArchiveFederationDefaultFlags (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-208">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e8720-209">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8720-209">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e8720-210">In Office Communications Server 2007 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-210">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-211">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="e8720-211">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="e8720-212">Dieses Attribut ist eine ganze Zahl, die als Bit-Feld verwendet wird, um zu steuern, ob die Kommunikation eines einzelnen Benutzers archiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e8720-212">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived.</span></span> <span data-ttu-id="e8720-213">Dieses Steuerelement wird von der Archivierungs-Agent-Schicht erzwungen.</span><span class="sxs-lookup"><span data-stu-id="e8720-213">This control is enforced by the archiving agent layer.</span></span> <span data-ttu-id="e8720-214">Sie ist für die Replikation des globalen Katalogs markiert.</span><span class="sxs-lookup"><span data-stu-id="e8720-214">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="e8720-215">Der Bereich dieses Attributs ist für einen einzelnen Benutzer oder Kontakt spezifisch.</span><span class="sxs-lookup"><span data-stu-id="e8720-215">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="e8720-216">Die gültigen Werte (und zugeordneten Bit-Positionen) in lync Server lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e8720-216">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-217">0: nicht archivieren (keine Bit-Festlegung)</span><span class="sxs-lookup"><span data-stu-id="e8720-217">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="e8720-218">1: zurückgezogen (Bit-Position 0)</span><span class="sxs-lookup"><span data-stu-id="e8720-218">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="e8720-219">2: zurückgezogen (Bit-Position 1)</span><span class="sxs-lookup"><span data-stu-id="e8720-219">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="e8720-220">4: Archivieren der internen Kommunikation (Bit-Position 2)</span><span class="sxs-lookup"><span data-stu-id="e8720-220">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="e8720-221">8: Archivieren der Verbundkommunikation (Bit-Position 3)</span><span class="sxs-lookup"><span data-stu-id="e8720-221">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="e8720-222">Zuvor gültige Werte in Live Communications Server 2005 lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e8720-222">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-223">0: Verwenden Sie den von <strong>msRTCSIP-ArchiveDefault</strong> und <strong>msRTCSIP-ArchiveFederation</strong> in dieser Rangfolge definierten Standardwert:</span><span class="sxs-lookup"><span data-stu-id="e8720-223">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-224">1: Archiv</span><span class="sxs-lookup"><span data-stu-id="e8720-224">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="e8720-225">2: nicht archivieren</span><span class="sxs-lookup"><span data-stu-id="e8720-225">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="e8720-226">3: Archivieren ohne Nachrichtentext</span><span class="sxs-lookup"><span data-stu-id="e8720-226">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="e8720-227">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8720-227">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-228">msRTCSIP-ArchivingServerData (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-228">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-229">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e8720-229">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8720-230">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-230">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-231">msRTCSIP-ArchivingServerVersion (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-231">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-232">Dieses Attribut definiert die Version des Archivierungsdiensts.</span><span class="sxs-lookup"><span data-stu-id="e8720-232">This attribute defines the version of the Archiving service.</span></span> <span data-ttu-id="e8720-233">Dieses Attribut ist ein monoton zunehmender ganzzahliger Typ, der mit jeder offiziellen Produktversion inkrementiert wird.</span><span class="sxs-lookup"><span data-stu-id="e8720-233">This attribute is a monotonously increasing integer type that increments with each official product release.</span></span> <span data-ttu-id="e8720-234">Die zulässigen Werte sind:</span><span class="sxs-lookup"><span data-stu-id="e8720-234">The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-235">Undefined: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="e8720-235">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="e8720-236">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="e8720-236">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="e8720-237">                 Live Communications Server 2005 mit SP1</span><span class="sxs-lookup"><span data-stu-id="e8720-237">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="e8720-238">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="e8720-238">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="e8720-239">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="e8720-239">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8720-240">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-240">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8720-241">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-241">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-242">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="e8720-242">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="e8720-243">Dieses Attribut gibt den FQDN des Back-End-Servers des Pools an.</span><span class="sxs-lookup"><span data-stu-id="e8720-243">This attribute specifies the FQDN of the Back End Server of the pool.</span></span> <span data-ttu-id="e8720-244">Da es nur einen einzelnen Back-End-Server pro Pool geben kann, handelt es sich um ein einwertiges Attribut.</span><span class="sxs-lookup"><span data-stu-id="e8720-244">Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="e8720-245">Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN beträgt 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e8720-245">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="e8720-246">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8720-246">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-247">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="e8720-247">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="e8720-248">Dieses Attribut enthält den Bezeichner des Pools, der das Konferenzverzeichnis hostet.</span><span class="sxs-lookup"><span data-stu-id="e8720-248">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="e8720-249">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8720-249">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-250">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="e8720-250">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="e8720-251">Dieses Attribut enthält den Bezeichner eines Konferenz Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="e8720-251">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="e8720-252">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8720-252">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-253">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="e8720-253">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="e8720-254">Dieses Attribut enthält den Bezeichner des Pools, in den das Konferenzverzeichnis verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="e8720-254">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="e8720-255">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8720-255">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-256">msRTCSIP – Standard</span><span class="sxs-lookup"><span data-stu-id="e8720-256">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="e8720-257">Dieses boolesche Attribut legt fest, ob es sich bei der Telefonverwendung um eine Standardverwendung handelt.</span><span class="sxs-lookup"><span data-stu-id="e8720-257">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="e8720-258">Wenn dieses Attribut auf <strong>true</strong>festgelegt ist, ist die Telefonverwendung eine standardmäßige Verwendung und kann vom Administrator nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="e8720-258">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="e8720-259">Wenn dieses Attribut auf <strong>false</strong>festgelegt ist, kann die Verwendung gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="e8720-259">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="e8720-260">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-260">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-261">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="e8720-261">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="e8720-262">Dieses Attribut identifiziert die Communicator-Webzugriffs-URL für Benutzer außerhalb der Organisation.</span><span class="sxs-lookup"><span data-stu-id="e8720-262">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="e8720-263">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8720-263">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-264">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="e8720-264">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="e8720-265">Dieses Attribut identifiziert die Communicator-Webzugriffs-URL für Benutzer, die sich innerhalb der Organisation befinden.</span><span class="sxs-lookup"><span data-stu-id="e8720-265">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="e8720-266">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8720-266">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-267">msRTCSIP-DefaultLocationProfileLink (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-267">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-268">Dieses einwertige Attribut enthält den Distinguished Name (DN) eines Standortprofil-Klassenobjekts, das ihm zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="e8720-268">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="e8720-269">Link weiterleiten: <strong>Link ID 11036</strong></span><span class="sxs-lookup"><span data-stu-id="e8720-269">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="e8720-270">Der entsprechende abwärts Link ist <strong>msRTCSIP-ServerReferenceBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8720-270">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8720-271">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-271">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-272">msRTCSIP-DefaultPolicy (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-272">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-273">Dieses boolesche Attribut gibt an, ob es sich bei der Richtlinie um eine Standardrichtlinie handelt.</span><span class="sxs-lookup"><span data-stu-id="e8720-273">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="e8720-274">Die Richtlinie ist eine Standardrichtlinie, wenn Sie auf <strong>true</strong>festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e8720-274">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8720-275">Neu in Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="e8720-275">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="e8720-276">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-276">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-277">msRTCSIP-DefaultRouteToEdgeProxy (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-277">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-278">Dieses Attribut gibt den FQDN der Edgeserver an, auf die der Zugriffs-Edgedienst, auf den direkt zugegriffen werden kann, oder das Hardwaregerät zum Lastenausgleich für einen Serverpool mit Zugriffs-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="e8720-278">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="e8720-279">Wenn auf den Servern mit Zugriffs-Edgedienst nur über einen oder mehrere Directors zugegriffen werden kann, gibt dieses Attribut den FQDN und optional die Portnummer des Directors oder des Hardware-Lastenausgleichs an, der eine Directorpool bedient.</span><span class="sxs-lookup"><span data-stu-id="e8720-279">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="e8720-280">Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN beträgt 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e8720-280">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="e8720-281">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8720-281">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e8720-282">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-282">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-283">msRTCSIP-DefaultRouteToEdgeProxyPort (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-283">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-284">Dieses Attribut stellt die Portnummer dar, die zum Herstellen einer Verbindung mit dem Server mit Zugriffs-Edgedienst verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e8720-284">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="e8720-285">Der gültige Wert ist ein ganzzahliger Wert, der den zu verwendenden Port angibt.</span><span class="sxs-lookup"><span data-stu-id="e8720-285">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="e8720-286">Der Standardwert lautet 5061.</span><span class="sxs-lookup"><span data-stu-id="e8720-286">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="e8720-287">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8720-287">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e8720-288">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-288">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-289">msRTCSIP-DefPresenceSubscriptionTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-289">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-290">Dieses Attribut stellt den Standardtimeout Zeitraum für Anwesenheitsabonnements dar.</span><span class="sxs-lookup"><span data-stu-id="e8720-290">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="e8720-291">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-291">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-292">msRTCSIP-DefRegistrationTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-292">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-293">Dieses Attribut stellt das standardmäßige Registrierungstimeout Fenster dar.</span><span class="sxs-lookup"><span data-stu-id="e8720-293">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="e8720-294">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-294">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-295">msRTCSIP-DefRoamingDataSubscriptionTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-295">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-296">Dieses Attribut stellt das Standardtimeout Fenster für das Roaming-Datenabonnement dar.</span><span class="sxs-lookup"><span data-stu-id="e8720-296">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="e8720-297">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-297">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-298">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="e8720-298">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="e8720-299">Dieses Attribut wird in einer geteilten Domänentopologie verwendet und enthält einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN).</span><span class="sxs-lookup"><span data-stu-id="e8720-299">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="e8720-300">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8720-300">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-301">msRTCSIP-Description (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-301">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-302">Dieses einwertige UNICODE-Zeichenfolgenattribut enthält eine benutzerfreundliche Beschreibung dieser Telefonroute oder Normalisierungsregel.</span><span class="sxs-lookup"><span data-stu-id="e8720-302">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="e8720-303">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-303">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8720-304">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-304">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-305">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="e8720-305">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="e8720-306">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e8720-306">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-307">msRTCSIP-Domänenname</span><span class="sxs-lookup"><span data-stu-id="e8720-307">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="e8720-308">Dieses Attribut stellt eine für die Registrierungsstelle konfigurierte Domäne dar.</span><span class="sxs-lookup"><span data-stu-id="e8720-308">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-309">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="e8720-309">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="e8720-310">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e8720-310">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8720-311">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8720-311">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-312">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="e8720-312">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="e8720-313">Dieses Attribut gibt den FQDN des Servers an, auf dem Zugriffs-Edgedienst ausführt.</span><span class="sxs-lookup"><span data-stu-id="e8720-313">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="e8720-314">Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN beträgt 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e8720-314">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="e8720-315">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8720-315">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-316">msRTCSIP-EnableBestEffortNotify (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-316">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-317">Dieses Attribut steuert, ob ein Server eine Benachrichtigungsanforderung (Best Effort notify, BENOTIFY) anstelle einer Notify-Anforderung als Antwort auf eine subscribe-Anforderung eines Clients generiert.</span><span class="sxs-lookup"><span data-stu-id="e8720-317">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client.</span></span> <span data-ttu-id="e8720-318">BENOTIFY ist eine leistungssteigernde Erweiterung des Subscribe-Benachrichtigungs Handshakes, bei dem der Server BENOTIFY-Anforderungen anstelle von regulären NOTIFY-Anforderungen generiert.</span><span class="sxs-lookup"><span data-stu-id="e8720-318">BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests.</span></span> <span data-ttu-id="e8720-319">Der Leistungsvorteil besteht darin, dass für eine BENOTIFY-Anforderung keine 200 OK-Antwort vom Client erforderlich ist, wenn die Notify-Anforderung dies tut.</span><span class="sxs-lookup"><span data-stu-id="e8720-319">The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="e8720-320">Gültige Werte sind <strong>true</strong> oder <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8720-320">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e8720-321">BENOTIFY-Anforderungen werden von Live Communications Server 2003 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e8720-321">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="e8720-322">Zur Zusammenarbeit mit Serveranwendungen, die mit der Live Communications Server 2003 Server-API geschrieben werden, die auf Live Communications Server 2005-und Drittanbieterservern ausgeführt wird, können BENOTIFY-Anforderungen deaktiviert werden, indem der Wert auf <STRONG>false</STRONG>festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="e8720-322">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="e8720-323">BENOTIFY ist derzeit nicht Teil des IETF-Standardisierungsprozesses (Internet Engineering Task Force).</span><span class="sxs-lookup"><span data-stu-id="e8720-323">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="e8720-324">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8720-324">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e8720-325">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-325">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-326">msRTCSIP-EnableFederation (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-326">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-327">Dieses Attribut ist ein globaler Switch, mit dem IT-Administratoren konfigurieren können, ob Benutzer mit Benutzern aus anderen Organisationen kommunizieren dürfen.</span><span class="sxs-lookup"><span data-stu-id="e8720-327">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations.</span></span> <span data-ttu-id="e8720-328">Es ermöglicht einem Administrator das Überschreiben des <strong>FederationEnabled</strong> -Attributs eines einzelnen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="e8720-328">It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute.</span></span> <span data-ttu-id="e8720-329">Dieses Attribut kann hilfreich sein, um das interne Netzwerk vor Internet Angriffen zu schützen, die möglicherweise durch Würmer, Viren oder gezielte Angriffe auf das Unternehmen verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="e8720-329">This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="e8720-330">Die gültigen Werte (und zugeordneten Bit-Positionen) lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e8720-330">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-331">1: für öffentliche Chat Verbindungen aktiviert (Bit-Position 0)</span><span class="sxs-lookup"><span data-stu-id="e8720-331">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="e8720-332">2: reserviert (Bit-Position 1)</span><span class="sxs-lookup"><span data-stu-id="e8720-332">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="e8720-333">4: reserviert (Bit-Position 2)</span><span class="sxs-lookup"><span data-stu-id="e8720-333">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="e8720-334">8: reserviert (Bit-Position 3)</span><span class="sxs-lookup"><span data-stu-id="e8720-334">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="e8720-335">16: Remote Anrufsteuerung aktiviert [Telefonie] (Bit-Position 4)</span><span class="sxs-lookup"><span data-stu-id="e8720-335">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="e8720-336">64: AllowOrganizeMeetingWithAnonymousParticipants lautet (Benutzer können anonyme Benutzer zu Besprechungen einladen (Bit-Position 6)</span><span class="sxs-lookup"><span data-stu-id="e8720-336">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="e8720-337">128: UCEnabled (Benutzer für Unified Communications aktivieren) (Bit-Position 7)</span><span class="sxs-lookup"><span data-stu-id="e8720-337">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="e8720-338">256: EnabledForEnhancedPresence (Benutzer für öffentliche Chat Verbindungen aktivieren) (Bit-Position 8)</span><span class="sxs-lookup"><span data-stu-id="e8720-338">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="e8720-339">512: RemoteCallControlDualMode (Bit-Position 9)</span><span class="sxs-lookup"><span data-stu-id="e8720-339">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8720-340">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8720-340">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e8720-341">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-341">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-342">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="e8720-342">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="e8720-343">Dieses Attribut gibt an, ob die Enterprise-Dienste auf dem angegebenen Server geladen werden.</span><span class="sxs-lookup"><span data-stu-id="e8720-343">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-344">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="e8720-344">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="e8720-345">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e8720-345">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-346">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="e8720-346">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="e8720-347">Dieses Attribut enthält die Wählnummer für den externen Zugriff.</span><span class="sxs-lookup"><span data-stu-id="e8720-347">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="e8720-348">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8720-348">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-349">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="e8720-349">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="e8720-350">Mit diesem Attribut wird gesteuert, ob ein einzelner Benutzer für den Partnerverbund aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e8720-350">This attribute controls whether a single user is enabled for federation.</span></span> <span data-ttu-id="e8720-351">Sie wird von der Enterprise Services-Schicht erzwungen.</span><span class="sxs-lookup"><span data-stu-id="e8720-351">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="e8720-352">Sie ist für die Replikation des globalen Katalogs markiert.</span><span class="sxs-lookup"><span data-stu-id="e8720-352">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="e8720-353">Gültige Werte sind <strong>true</strong> oder <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8720-353">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8720-354">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8720-354">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-355">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="e8720-355">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="e8720-356">Dieses Attribut ist eine mehrwertige Liste der Domänennamen aller Enterprise Edition-Server, die einem Pool zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e8720-356">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="e8720-357">Link zurück: <strong>Link ID 11023</strong></span><span class="sxs-lookup"><span data-stu-id="e8720-357">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="e8720-358">Der entsprechende Weiterleitungslink zu diesem Rück Link ist <strong>msRTCSIP-PoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8720-358">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8720-359">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8720-359">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-360">msRTCSIP-Gateways (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-360">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-361">Dieses mehrwertige Zeichenfolgenattribut enthält eine Liste von Gateways und Ports (pro Gateway).</span><span class="sxs-lookup"><span data-stu-id="e8720-361">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="e8720-362">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-362">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-363">msRTCSIP-GlobalSettingsData (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-363">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-364">Dieses Attribut speichert Name: Wert-Paare.</span><span class="sxs-lookup"><span data-stu-id="e8720-364">This attribute stores name:value pairs.</span></span> <span data-ttu-id="e8720-365">Das bereits definierte Name: Value-Paar ist für die Einstellung <strong>Abruf für Anwesenheit zulassen</strong> .</span><span class="sxs-lookup"><span data-stu-id="e8720-365">The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="e8720-366">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-366">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-367">msRTCSIP-Gruppierung</span><span class="sxs-lookup"><span data-stu-id="e8720-367">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="e8720-368">Dieses Attribut ist ein eindeutiger Bezeichner einer Gruppe, die zum Gruppieren von Adressbucheinträgen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e8720-368">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="e8720-369">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8720-369">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-370">msRTCSIP-Homeserver (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-370">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e8720-371">Neu in Live Communications Server 2003 (nicht verwendet).</span><span class="sxs-lookup"><span data-stu-id="e8720-371">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="e8720-372">In Live Communications Server 2005 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-372">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-373">msRTCSIP-HomeServerString (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-373">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e8720-374">Neu in Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="e8720-374">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="e8720-375">In Live Communications Server 2005 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-375">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-376">msRTCSIP-Heimuser (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-376">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e8720-377">Neu in Live Communications Server 2003 (nicht verwendet).</span><span class="sxs-lookup"><span data-stu-id="e8720-377">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="e8720-378">In Live Communications Server 2005 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-378">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-379">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="e8720-379">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="e8720-380">Mit diesem Attribut wird gesteuert, ob ein einzelner Benutzer für den Zugriff durch externe Benutzer aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e8720-380">This attribute controls whether a single user is enabled for outside user access.</span></span> <span data-ttu-id="e8720-381">Sie wird von der Enterprise Services-Schicht erzwungen.</span><span class="sxs-lookup"><span data-stu-id="e8720-381">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="e8720-382">Sie ist für die Replikation des globalen Katalogs markiert.</span><span class="sxs-lookup"><span data-stu-id="e8720-382">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="e8720-383">Gültige Werte sind <strong>true</strong> oder <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8720-383">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8720-384">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8720-384">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-385">msRTCSIP-IsMaster (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-385">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e8720-386">Neu in Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="e8720-386">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="e8720-387">In Live Communications Server 2005 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-387">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-388">msRTCSIP-Line</span><span class="sxs-lookup"><span data-stu-id="e8720-388">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="e8720-389">Dieses einwertige Attribut enthält die Geräte-ID (entweder den SIP-URI oder den Tel-URI des Telefons, den der Benutzer steuert), der von lync für die Telefonie verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e8720-389">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="e8720-390">Dieses Attribut ist für die Replikation des globalen Katalogs gekennzeichnet und wird indiziert.</span><span class="sxs-lookup"><span data-stu-id="e8720-390">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="e8720-391">Wenn ein Benutzer für Enterprise-VoIP aktiviert ist, wird in diesem Attribut die normalisierte E. 164-Version der Telefonnummer des Benutzers gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e8720-391">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="e8720-392">Neu in Microsoft Office Live Communications Server 2005 mit SP1</span><span class="sxs-lookup"><span data-stu-id="e8720-392">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-393">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="e8720-393">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="e8720-394">Dieses Attribut mit einem Wert enthält den SIP-URI des CSTA-SIP-Gatewayservers.</span><span class="sxs-lookup"><span data-stu-id="e8720-394">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server.</span></span> <span data-ttu-id="e8720-395">Dieses Attribut ist für die Replikation des globalen Katalogs gekennzeichnet, jedoch nicht indiziert.</span><span class="sxs-lookup"><span data-stu-id="e8720-395">This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="e8720-396">Neu in Microsoft Office Live Communications Server 2005 mit SP1</span><span class="sxs-lookup"><span data-stu-id="e8720-396">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-397">msRTCSIP-LocalNormalizationData (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-397">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-398">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e8720-398">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8720-399">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-399">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8720-400">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-400">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-401">msRTCSIP-LocalNormalizationLinks (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-401">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-402">Dieses mehrwertige Attribut enthält eine Liste der lokalen normalisierungs Namen (Distinguished Names, DN), die diesem Standortprofil zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e8720-402">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile.</span></span> <span data-ttu-id="e8720-403">Der Typ dieses Attributs ist eine DN-Binärdatei.</span><span class="sxs-lookup"><span data-stu-id="e8720-403">The type of this attribute is a DN binary.</span></span> <span data-ttu-id="e8720-404">Es gibt eine 1: n-Beziehung zwischen Standortprofil und lokalen Normalisierungsregeln.</span><span class="sxs-lookup"><span data-stu-id="e8720-404">There is a one-to-many relationship between location profile and local normalization rules.</span></span> <span data-ttu-id="e8720-405">Die Sortierung der Liste der lokalen normalisierungs-DNS muss in der vom Administrator angegebenen Reihenfolge aufrecht erhalten werden.</span><span class="sxs-lookup"><span data-stu-id="e8720-405">The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator.</span></span> <span data-ttu-id="e8720-406">Die Beibehaltung der Reihenfolge wird durch den binären Teil der DN-Binärdatei verwaltet, der den Reihenfolgeindex angibt.</span><span class="sxs-lookup"><span data-stu-id="e8720-406">The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="e8720-407">Link weiterleiten: <strong>Link ID 11034</strong></span><span class="sxs-lookup"><span data-stu-id="e8720-407">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="e8720-408">Die entsprechende Backlink to this Forward Link-Attribut ist <strong>msRTCSIP-LocationProfileBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8720-408">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8720-409">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-409">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8720-410">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-410">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-411">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="e8720-411">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="e8720-412">Dieses Attribut enthält eine Liste von Optionen für die Normalisierungsregel.</span><span class="sxs-lookup"><span data-stu-id="e8720-412">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="e8720-413">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8720-413">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-414">msRTCSIP-LocationName (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-414">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-415">Dieses einwertige Attribut enthält einen Anzeigenamen für das Standortprofil, das angibt, welche Position dieses Profil darstellt.</span><span class="sxs-lookup"><span data-stu-id="e8720-415">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents.</span></span> <span data-ttu-id="e8720-416">Da es mehrere Standortprofile geben kann, benötigt der Administrator eine Möglichkeit, zwischen unterschiedlichen Profilen zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="e8720-416">Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="e8720-417">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-417">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8720-418">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-418">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-419">msRTCSIP-locationProfileBL (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-419">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-420">Dieses mehrwertige Attribut enthält eine Liste von Standortprofil-Distinguished Names.</span><span class="sxs-lookup"><span data-stu-id="e8720-420">This multi-valued attribute contains a list of location profile distinguished names.</span></span> <span data-ttu-id="e8720-421">Dieses Attribut gibt die Rückverknüpfung zu einem oder mehreren Standortprofilen an.</span><span class="sxs-lookup"><span data-stu-id="e8720-421">This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="e8720-422">Link zurück: <strong>Link ID 11035</strong></span><span class="sxs-lookup"><span data-stu-id="e8720-422">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="e8720-423">Dieses Attribut entspricht dem Forward-Link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8720-423">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8720-424">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-424">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8720-425">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-425">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-426">msRTCSIP-LocationProfileData (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-426">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-427">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e8720-427">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8720-428">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-428">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8720-429">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-429">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-430">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="e8720-430">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="e8720-431">Dieses Attribut enthält die Optionen für das Standortprofil.</span><span class="sxs-lookup"><span data-stu-id="e8720-431">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="e8720-432">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8720-432">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-433">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="e8720-433">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="e8720-434">Dieses mehrwertige Attribut umfasst eine Liste von Anwendungs Kontakten.</span><span class="sxs-lookup"><span data-stu-id="e8720-434">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="e8720-435">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8720-435">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-436">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="e8720-436">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="e8720-437">Dieses mehrwertige Attribut umfasst eine Liste von Standortprofilen.</span><span class="sxs-lookup"><span data-stu-id="e8720-437">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="e8720-438">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8720-438">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-439">msRTCSIP-MaxNumOutstandingSearchPerServer (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-439">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-440">Dieses Attribut stellt die maximale Anzahl ausstehender Suchanforderungen pro Server dar.</span><span class="sxs-lookup"><span data-stu-id="e8720-440">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="e8720-441">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-441">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-442">msRTCSIP-MaxNumSubscriptionsPerUser (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-442">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-443">Das-Attribut stellt die maximale Anzahl von Abonnements pro Benutzer dar.</span><span class="sxs-lookup"><span data-stu-id="e8720-443">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="e8720-444">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-444">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-445">msRTCSIP-MaxPresenceSubscriptionTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-445">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-446">Dieses Attribut stellt das maximale Timeout Fenster für Abonnements dar.</span><span class="sxs-lookup"><span data-stu-id="e8720-446">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="e8720-447">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-447">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-448">msRTCSIP-MaxRegistrationsTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-448">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-449">Dieses Attribut stellt das Timeout Fenster für maximale Registrierungen dar.</span><span class="sxs-lookup"><span data-stu-id="e8720-449">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="e8720-450">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-450">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-451">msRTCSIP-MaxRoamingDataSubscriptionTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-451">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-452">Dieses Attribut stellt das Timeout Fenster für das maximale Roaming von Daten Abonnements dar.</span><span class="sxs-lookup"><span data-stu-id="e8720-452">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="e8720-453">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-453">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-454">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="e8720-454">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="e8720-455">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e8720-455">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8720-456">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-456">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-457">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="e8720-457">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="e8720-458">Dieses Attribut ist ein Dienststeuerungspunkt-Attribut unter der Computerklasse, das einen Link zurück zur MCU-Factory (Multipoint Control Unit) angibt, zu der es gehört.</span><span class="sxs-lookup"><span data-stu-id="e8720-458">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs.</span></span> <span data-ttu-id="e8720-459">Dieser Dienst Steuerungs Pfad und das Attribut werden für jede Microsoft MCU erstellt.</span><span class="sxs-lookup"><span data-stu-id="e8720-459">This service control point and attribute is created for every Microsoft MCU.</span></span> <span data-ttu-id="e8720-460">Jede Microsoft MCU muss den Back-End-Server des Pools finden, zu dem Sie gehört, um Einstellungen auf Poolebene daraus abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e8720-460">Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="e8720-461">Der Wert dieses Attributs ist der DN (Distinguished Name) der MCU-Factory.</span><span class="sxs-lookup"><span data-stu-id="e8720-461">The value of this attribute is the distinguished name (DN) of the MCU Factory.</span></span> <span data-ttu-id="e8720-462">Hierbei handelt es sich um ein einwertiges Attribut, das für die Replikation des globalen Katalogs gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="e8720-462">This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="e8720-463">Link weiterleiten: <strong>Link ID 11026</strong></span><span class="sxs-lookup"><span data-stu-id="e8720-463">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="e8720-464">Die entsprechende Backlink to this Forward Link-Attribut ist <strong>msRTCSIP-MCUServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8720-464">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8720-465">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-465">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-466">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="e8720-466">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="e8720-467">Dies ist ein reserviertes Attribut mit mehreren Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="e8720-467">This is a multi-string reserved attribute.</span></span> <span data-ttu-id="e8720-468">In diesem Attribut gespeicherte Einstellungen werden als Name = Wert-Paare dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e8720-468">Settings stored in this attribute are represented as name=value pairs.</span></span> <span data-ttu-id="e8720-469">Aktuell definierte Name = Wert-Paare sind:</span><span class="sxs-lookup"><span data-stu-id="e8720-469">Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-470">FactoryURL = &lt; URL&gt;</span><span class="sxs-lookup"><span data-stu-id="e8720-470">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8720-471">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-471">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-472">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="e8720-472">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="e8720-473">Hierbei handelt es sich um ein einwertiges Attribut, das den Distinguished Name (DN) einer einzelnen MCU-Factory enthält, die einem Pool zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="e8720-473">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="e8720-474">Link weiterleiten: <strong>Link ID 11024</strong></span><span class="sxs-lookup"><span data-stu-id="e8720-474">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="e8720-475">Die entsprechende Backlink to this Forward Link-Attribut ist <strong>msRTCSIP-PoolAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8720-475">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8720-476">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-476">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-477">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="e8720-477">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="e8720-478">Dieses Attribut ist eine einwertige Zeichenfolge, die die GUID des MCU-Factory-Anbieters angibt.</span><span class="sxs-lookup"><span data-stu-id="e8720-478">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="e8720-479">Basierend auf dem GUID-Wert bestimmt der MCU-factoryprozess, ob dieser MCU-Typ gewartet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e8720-479">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="e8720-480">Wenn der GUID-Wert <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>ist, wird der MCU-factoryprozess (standardmäßig in lync Server verfügbar) verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="e8720-480">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="e8720-481">Für jeden anderen GUID-Wert wird der MCU-Prozess vom MCU-factoryprozess nicht gewartet.</span><span class="sxs-lookup"><span data-stu-id="e8720-481">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="e8720-482">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-482">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-483">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="e8720-483">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="e8720-484">Dieses Attribut ist eine mehrwertige Liste mit Distinguished Names (DN).</span><span class="sxs-lookup"><span data-stu-id="e8720-484">This attribute is a multi-valued list of distinguished names (DN).</span></span> <span data-ttu-id="e8720-485">Dieses Attribut enthält eine Liste aller MCU-Server desselben Typs und Anbieters, die dieser MCU-Factory zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e8720-485">This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory.</span></span> <span data-ttu-id="e8720-486">Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN beträgt 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e8720-486">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="e8720-487">Link zurück: Link ID 11027</span><span class="sxs-lookup"><span data-stu-id="e8720-487">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="e8720-488">Der entsprechende Weiterleitungslink zu diesem Rück Link ist <strong>msRTCSIP-MCUFactoryAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8720-488">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8720-489">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-489">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-490">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="e8720-490">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="e8720-491">Dieses Attribut ist eine einwertige Zeichenfolge, die das Medium angibt, mit dem die MCU umgehen kann.</span><span class="sxs-lookup"><span data-stu-id="e8720-491">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="e8720-492">Unterstützte gültige Typen:</span><span class="sxs-lookup"><span data-stu-id="e8720-492">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-493">Besprechungs</span><span class="sxs-lookup"><span data-stu-id="e8720-493">meeting</span></span></p></li>
<li><p><span data-ttu-id="e8720-494">Audio-Video</span><span class="sxs-lookup"><span data-stu-id="e8720-494">audio-video</span></span></p></li>
<li><p><span data-ttu-id="e8720-495">Chat</span><span class="sxs-lookup"><span data-stu-id="e8720-495">chat</span></span></p></li>
<li><p><span data-ttu-id="e8720-496">Telefon-conf</span><span class="sxs-lookup"><span data-stu-id="e8720-496">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8720-497">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-497">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-498">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="e8720-498">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="e8720-499">Dieses Attribut ist eine einwertige Zeichenfolge, die den Namen eines MCU-Anbieters angibt.</span><span class="sxs-lookup"><span data-stu-id="e8720-499">This attribute is a single-valued string that specifies an MCU vendor’s name.</span></span> <span data-ttu-id="e8720-500">Alle Microsoft-MCU gibt dieses Attribut als <strong>Microsoft Corporation</strong>an.</span><span class="sxs-lookup"><span data-stu-id="e8720-500">All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8720-501">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-501">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-502">msRTCSIP-MeetingFlags (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-502">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-503">Dieses Attribut definiert unterschiedliche Besprechungsoptionen, die Global für alle Benutzer oder Kontaktobjekte aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="e8720-503">This attribute defines different meeting options that are enabled globally for all users or contact objects.</span></span> <span data-ttu-id="e8720-504">Dieses Attribut ist ein Bitmaskenwert des Typs Integer.</span><span class="sxs-lookup"><span data-stu-id="e8720-504">This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="e8720-505">Die gültigen Werte (und zugeordneten Bit-Positionen) lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e8720-505">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-506">0: AllowOrganizeMeetingWithAnonymousParticipants lautet ist keine (Benutzer dürfen keine anonymen Benutzer zu Besprechungen einladen) (keine Bits festgelegt)</span><span class="sxs-lookup"><span data-stu-id="e8720-506">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="e8720-507">4: AllowOrganizeMeetingWithAnonymousParticipants lautet ist jeder (gestatten Sie allen Benutzern, anonyme Benutzer zu Besprechungen einzuladen) (Bit-Position 2)</span><span class="sxs-lookup"><span data-stu-id="e8720-507">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="e8720-508">8: AllowOrganizeMeetingWithAnonymousParticipants lautet ist UsePerUserSetting (Benutzern das einladen anonymer Benutzer zu Besprechungen basierend auf der Einstellung pro Benutzer) (Bit-Position 3)</span><span class="sxs-lookup"><span data-stu-id="e8720-508">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="e8720-509">16: UserPerUserMeetingPolicy (Besprechungsrichtlinie wird pro Benutzerdefiniert) (Bit-Position 4)</span><span class="sxs-lookup"><span data-stu-id="e8720-509">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8720-510">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-510">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8720-511">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-511">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-512">msRTCSIP-meetingpolicy "(veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-512">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-513">Dieses Attribut gibt den Distinguished Name (DN) der Richtlinie an, die der Administrator diesem Benutzer als einwertiges Attribut zugewiesen hat.</span><span class="sxs-lookup"><span data-stu-id="e8720-513">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="e8720-514">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-514">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8720-515">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-515">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-516">msRTCSIP-MinPresenceSubscriptionTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-516">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-517">Dieses Attribut stellt das Timeout Fenster für das minimale Anwesenheits Abonnement dar.</span><span class="sxs-lookup"><span data-stu-id="e8720-517">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="e8720-518">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-518">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-519">msRTCSIP-MinRegistrationTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-519">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-520">Dieses Attribut stellt das Timeout Fenster für die minimale Registrierung dar.</span><span class="sxs-lookup"><span data-stu-id="e8720-520">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="e8720-521">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-521">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8720-522">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-522">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-523">msRTCSIP-MinRoamingDataSubscriptionTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-523">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-524">Dieses Attribut stellt das Timeout Fenster für das minimale Roaming-Datenabonnement dar.</span><span class="sxs-lookup"><span data-stu-id="e8720-524">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="e8720-525">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-525">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8720-526">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-526">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-527">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="e8720-527">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="e8720-528">Dieses Attribut wird verwendet, um das vom Front-End-Pool verwendete gespiegelte SQL Server-Back-End zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e8720-528">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="e8720-529">Neu in lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8720-529">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-530">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="e8720-530">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="e8720-531">Dieses Attribut enthält Optionen und Flags zur Definition von Mobilitätseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="e8720-531">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="e8720-532">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8720-532">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-533">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="e8720-533">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="e8720-534">Dieses Attribut enthält den DN für ein mobilitätsrichtlinien Objekt.</span><span class="sxs-lookup"><span data-stu-id="e8720-534">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="e8720-535">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8720-535">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-536">msRTCSIP-NumDevicesPerUser (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-536">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-537">Dieses Attribut stellt die zulässige Anzahl von Geräten dar, auf denen ein Benutzer für die SIP-Kommunikation registrieren und die Anwesenheit abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="e8720-537">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="e8720-538">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-538">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8720-539">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-539">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-540">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="e8720-540">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="e8720-541">Dieses Attribut gibt die Optionen an, die für das Benutzer-oder Kontaktobjekt aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="e8720-541">This attribute specifies the options that are enabled for the user or contact object.</span></span> <span data-ttu-id="e8720-542">Dieses Attribut ist ein Bitmaskenwert vom Typ Integer.</span><span class="sxs-lookup"><span data-stu-id="e8720-542">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="e8720-543">Jede Option wird durch ein Bit dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e8720-543">Each option is represented by a bit.</span></span> <span data-ttu-id="e8720-544">Dieses Attribut ist für die Replikation des globalen Katalogs gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="e8720-544">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="e8720-545">Die gültigen Werte (und zugeordneten Bit-Positionen) lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e8720-545">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-546">1: für die Verbindung mit öffentlichen Sofortnachrichtendiensten (Bit-Position 0) aktiviert</span><span class="sxs-lookup"><span data-stu-id="e8720-546">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="e8720-547">2: reserviert (Bit-Position 1)</span><span class="sxs-lookup"><span data-stu-id="e8720-547">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="e8720-548">4: reserviert (Bit-Position 2)</span><span class="sxs-lookup"><span data-stu-id="e8720-548">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="e8720-549">8: reserviert (Bit-Position 3)</span><span class="sxs-lookup"><span data-stu-id="e8720-549">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="e8720-550">16: Remote Anrufsteuerung aktiviert [Telefonie] (Bit-Position 4)</span><span class="sxs-lookup"><span data-stu-id="e8720-550">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="e8720-551">64: AllowOrganizeMeetingWithAnonymousParticipants lautet (Benutzer können anonyme Benutzer zu Besprechungen einladen (Bit-Position 6)</span><span class="sxs-lookup"><span data-stu-id="e8720-551">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="e8720-552">128: UCEnabled (Aktivieren von Benutzern für UC) (Bit-Position 7)</span><span class="sxs-lookup"><span data-stu-id="e8720-552">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="e8720-553">256: EnabledForEnhancedPresence (Benutzer für öffentliche Chat Verbindungen aktivieren) (Bit-Position 8)</span><span class="sxs-lookup"><span data-stu-id="e8720-553">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="e8720-554">512: RemoteCallControlDualMode (Bit-Position 9)</span><span class="sxs-lookup"><span data-stu-id="e8720-554">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8720-555">Neu in Live Communications Server 2005 mit SP1.</span><span class="sxs-lookup"><span data-stu-id="e8720-555">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-556">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="e8720-556">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="e8720-557">Dieses Attribut wird in den Ressourcen-und zentralen Gesamtstruktur-Topologien verwendet, um einmaliges Anmelden zu aktivieren, wenn die Objekt-Nr eines Benutzers aus dem Windows NT Server-Prinzipal Konto in dieses Attribut des entsprechenden Benutzer-oder Kontaktobjekts in der Ressourcen-oder zentralen Gesamtstruktur kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="e8720-557">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="e8720-558">Communicator-Webzugriff sucht in AD DS mithilfe dieses Attributs oder der Objekt-Nr des Benutzers nach einem Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e8720-558">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="e8720-559">Dieses Attribut ist für die Replikation des globalen Katalogs gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="e8720-559">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-560">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="e8720-560">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="e8720-561">Dieses Attribut ist der URN (Uniform Resource Name) des Besitzers für einen Anwendungs Kontakt.</span><span class="sxs-lookup"><span data-stu-id="e8720-561">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="e8720-562">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8720-562">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-563">msRTCSIP-Pattern (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-563">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-564">Dieses einwertige Zeichenfolgenattribut enthält ein Muster, das zum Zuordnen von Wähl Nummern zum E. 164-Format verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e8720-564">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format.</span></span> <span data-ttu-id="e8720-565">Wenn die Wählnummer mit diesem Muster übereinstimmt, wird die Übersetzung auf die gewählte Nummer angewendet.</span><span class="sxs-lookup"><span data-stu-id="e8720-565">If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="e8720-566">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-566">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8720-567">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-567">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-568">msRTCSIP-PhoneRouteBL (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-568">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-569">Dieses mehrwertige Attribut enthält eine Liste der Distinguished Names (DN) der Telefonroute.</span><span class="sxs-lookup"><span data-stu-id="e8720-569">This multi-valued attribute contains a list of phone route distinguished names (DN).</span></span> <span data-ttu-id="e8720-570">Dieses Attribut gibt den hinteren Link zu einer oder mehreren Telefonrouten an.</span><span class="sxs-lookup"><span data-stu-id="e8720-570">This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="e8720-571">Link zurück: <strong>Link ID 11033</strong></span><span class="sxs-lookup"><span data-stu-id="e8720-571">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="e8720-572">Dieses Attribut entspricht dem Forward-Link <strong>msRTCSIP-RouteUsageLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8720-572">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8720-573">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-573">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8720-574">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-574">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-575">msRTCSIP-PhoneRouteData (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-575">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-576">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e8720-576">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8720-577">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-577">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-578">msRTCSIP-PhoneRouteName (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-578">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-579">Dieses einfache Unicode-Zeichenfolgenattribut gibt den Anzeigenamen der Telefonroute an, sodass vom Administrator einfach auf ihn verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e8720-579">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="e8720-580">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-580">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-581">msRTCSIP-PhoneUsageData (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-581">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-582">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e8720-582">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8720-583">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-583">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8720-584">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-584">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-585">msRTCSIP-PolicyContent (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-585">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-586">Dieses Attribut ist eine Unicode-Zeichenfolge mit einer einwertigen Wert.</span><span class="sxs-lookup"><span data-stu-id="e8720-586">This attribute is a single-valued Unicode string.</span></span> <span data-ttu-id="e8720-587">Dieses Zeichenfolgenattribut enthält die Richtliniendefinition im XML-Format.</span><span class="sxs-lookup"><span data-stu-id="e8720-587">This string attribute contains the policy definition in XML format.</span></span> <span data-ttu-id="e8720-588">Die XML-Schema Definition ist in verschiedenen Richtlinientypen üblich, nur die Einstellungen unterscheiden sich für jeden Richtlinientyp.</span><span class="sxs-lookup"><span data-stu-id="e8720-588">The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="e8720-589">Die XML-Schema Definition (XSD) ist wie folgt definiert:</span><span class="sxs-lookup"><span data-stu-id="e8720-589">The XML schema definition (XSD) is defined as follows:</span></span></p>
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
<td><p><span data-ttu-id="e8720-590">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-590">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8720-591">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-591">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-592">msRTCSIP-Spalte PolicyData (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-592">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-593">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e8720-593">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8720-594">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-594">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8720-595">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-595">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-596">msRTCSIP-policyType (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-596">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-597">Dieses einwertige UNICODE-Zeichenfolgenattribut enthält den Richtlinientyp.</span><span class="sxs-lookup"><span data-stu-id="e8720-597">This single-valued Unicode string attribute contains the policy type.</span></span> <span data-ttu-id="e8720-598">Gültige Richtlinientypen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e8720-598">Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-599">Besprechungs</span><span class="sxs-lookup"><span data-stu-id="e8720-599">meeting</span></span></p></li>
<li><p><span data-ttu-id="e8720-600">Telefonie</span><span class="sxs-lookup"><span data-stu-id="e8720-600">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8720-601">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-601">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8720-602">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-602">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-603">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="e8720-603">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="e8720-604">Dieses Attribut gibt einen Link zurück zu dem Pool, zu dem ein Computer gehört.</span><span class="sxs-lookup"><span data-stu-id="e8720-604">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="e8720-605">Dieses Attribut wird unabhängig davon festgelegt, ob der Computer die Standard Edition oder die Enterprise Edition von lync Server ausführt.</span><span class="sxs-lookup"><span data-stu-id="e8720-605">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="e8720-606">Dieses Attribut ist für die Replikation des globalen Katalogs gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="e8720-606">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="e8720-607">Der gültige Wert ist der Domänenname des Pools.</span><span class="sxs-lookup"><span data-stu-id="e8720-607">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="e8720-608">Link weiterleiten: <strong>Link ID 11022</strong></span><span class="sxs-lookup"><span data-stu-id="e8720-608">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="e8720-609">Die entsprechende Backlink to this Forward Link-Attribut ist <strong>msRTCSIP-FrontEndServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8720-609">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8720-610">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8720-610">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-611">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="e8720-611">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="e8720-612">Hierbei handelt es sich um ein mehrwertiges Attribut, das eine Liste der Distinguished Names (DN) von Pools enthält, mit denen die MCU-Factory verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="e8720-612">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="e8720-613">Link zurück: <strong>Link ID 11025</strong></span><span class="sxs-lookup"><span data-stu-id="e8720-613">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="e8720-614">Der entsprechende Weiterleitungslink zu diesem Rück Link ist <strong>msRTCSIP-MCUFactoryPath</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8720-614">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8720-615">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-615">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-616">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="e8720-616">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="e8720-617">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e8720-617">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8720-618">Neu in Live Communications Server 2005 mit SP1.</span><span class="sxs-lookup"><span data-stu-id="e8720-618">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-619">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="e8720-619">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="e8720-620">Dieses Attribut gibt einen beliebigen Namen für einen Pool an, der von der Verwaltungskonsole angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e8720-620">This attribute specifies an arbitrary name for a pool that is displayed by the management console.</span></span> <span data-ttu-id="e8720-621">Dieser Name kann vom Administrator geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e8720-621">This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="e8720-622">Der gültige Wert ist eine Zeichenfolge, die den Namen eines Pools darstellt.</span><span class="sxs-lookup"><span data-stu-id="e8720-622">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="e8720-623">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8720-623">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-624">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="e8720-624">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="e8720-625">Dieses Attribut ist ein einwertiger Zeichenfolgenwert.</span><span class="sxs-lookup"><span data-stu-id="e8720-625">This attribute is a single-valued string value.</span></span> <span data-ttu-id="e8720-626">Der Wert dieses Attributs stellt, sofern vorhanden, den Domänen-FQDN des Pools dar, wenn der Administrator eine Front-End-Pool mit einem FQDN erstellen möchte, der nicht der Active Directory Domänenstruktur entspricht, in der das Front-End-Pool erstellt wird (beispielsweise ein SIP-Namespace, der vom Domain Name System (DNS) Namespace abweicht).</span><span class="sxs-lookup"><span data-stu-id="e8720-626">The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="e8720-627">Es wird empfohlen, den Domänen-FQDN Front-End-Pool Domänennamen als Active Directory Domäne, in der sich der Pool befindet, dem Domänennamens Teil zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="e8720-627">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides.</span></span> <span data-ttu-id="e8720-628">Wenn in diesem Attribut kein Wert vorhanden ist, wird der Front-End-Pool-FQDN standardmäßig auf die Active Directory Domänennamenstruktur, wie durch das <strong>dNSHostName</strong> -Attribut gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="e8720-628">Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="e8720-629">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-629">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-630">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="e8720-630">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="e8720-631">Eine mehrwertige Liste der Domänennamen aller lync Server Enterprise Edition-Server, die einem Pool zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e8720-631">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="e8720-632">Dieses Attribut vom Typ Integer definiert, ob der Pool Sofortnachrichten und Anwesenheitsinformationen und Besprechungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e8720-632">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="e8720-633">Die möglichen gültigen Wertetypen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e8720-633">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-634">Nicht definiert: Chat-und Anwesenheitsdienst (Live Communications Server 2005 und 2003)</span><span class="sxs-lookup"><span data-stu-id="e8720-634">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="e8720-635">1: Chat und Anwesenheitsdienst (lync Server)</span><span class="sxs-lookup"><span data-stu-id="e8720-635">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="e8720-636">2: Sofortnachrichten und Anwesenheits-und Besprechungs Dienst (lync Server)</span><span class="sxs-lookup"><span data-stu-id="e8720-636">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8720-637">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-637">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-638">msRTCSIP-pooltype</span><span class="sxs-lookup"><span data-stu-id="e8720-638">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="e8720-639">Dieses Attribut gibt an, ob ein Serverpool Standard Edition-Server oder Enterprise Edition-Server ausführt.</span><span class="sxs-lookup"><span data-stu-id="e8720-639">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server.</span></span> <span data-ttu-id="e8720-640">Dieses Attribut ist ein Bitmaskenwert vom Typ Integer.</span><span class="sxs-lookup"><span data-stu-id="e8720-640">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="e8720-641">Jede Option wird durch ein Bit dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e8720-641">Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="e8720-642">Die gültigen Werte (und zugeordneten Bit-Positionen) lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e8720-642">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-643">1: Standard Edition-Server, hostet Benutzer (Bit-Position 0)</span><span class="sxs-lookup"><span data-stu-id="e8720-643">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="e8720-644">2: Enterprise Edition-Server, hostet Benutzer (Bit-Position 1)</span><span class="sxs-lookup"><span data-stu-id="e8720-644">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="e8720-645">4: Standard Edition-Server, hostet Anwendungen (Bit-Position 2)</span><span class="sxs-lookup"><span data-stu-id="e8720-645">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="e8720-646">8: Enterprise Edition-Server, hostet Anwendungen (Bit-Position 3)</span><span class="sxs-lookup"><span data-stu-id="e8720-646">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="e8720-647">Da lync Server keine Pools unterstützt, die nur Anwendungen hosten, gelten die folgenden Werte nur:</span><span class="sxs-lookup"><span data-stu-id="e8720-647">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-648">5: Standard Edition-Server, hostet Benutzer und Anwendungen (Bit-Positionen 0 und 2)</span><span class="sxs-lookup"><span data-stu-id="e8720-648">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="e8720-649">10: Enterprise Edition-Server, hostet Benutzer und Anwendungen (Bit-Positionen 1 und 3)</span><span class="sxs-lookup"><span data-stu-id="e8720-649">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8720-650">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8720-650">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-651">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="e8720-651">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="e8720-652">Dieses Attribut definiert die Pool Version.</span><span class="sxs-lookup"><span data-stu-id="e8720-652">This attribute defines the pool version.</span></span> <span data-ttu-id="e8720-653">Es handelt sich um einen ganzzahligen Typ, der mit jeder Hauptprodukt Version inkrementiert wird.</span><span class="sxs-lookup"><span data-stu-id="e8720-653">It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="e8720-654">Die möglichen gültigen Wertetypen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e8720-654">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-655">0: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="e8720-655">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="e8720-656">1: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="e8720-656">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="e8720-657">2: Live Communications Server 2005 mit SP1</span><span class="sxs-lookup"><span data-stu-id="e8720-657">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="e8720-658">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="e8720-658">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="e8720-659">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="e8720-659">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="e8720-660">5: lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e8720-660">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8720-661">Live Communications Server 2005 mit SP1.</span><span class="sxs-lookup"><span data-stu-id="e8720-661">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-662">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="e8720-662">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="e8720-663">Dieses Attribut enthält Optionen und Flags, die Anwesenheitseinstellungen definieren.</span><span class="sxs-lookup"><span data-stu-id="e8720-663">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="e8720-664">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8720-664">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-665">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="e8720-665">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="e8720-666">Dieses Attribut enthält den DN für ein Präsenz Richtlinienobjekt.</span><span class="sxs-lookup"><span data-stu-id="e8720-666">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="e8720-667">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8720-667">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-668">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="e8720-668">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="e8720-669">Dieses Attribut aktiviert einen Benutzer oder Kontakt für SIP-Messaging.</span><span class="sxs-lookup"><span data-stu-id="e8720-669">This attribute enables a user or contact for SIP messaging.</span></span> <span data-ttu-id="e8720-670">Sie wird der Contact-Klasse hinzugefügt, da in der Topologie der zentralen Gesamtstruktur Kontaktobjekte und keine Benutzerobjekte SIP-aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="e8720-670">It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="e8720-671">Der gültige Wert ist der DN der Standard Edition-Server-oder Enterprise Edition-Front-End-Pool, in der ein Benutzer verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="e8720-671">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="e8720-672">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8720-672">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-673">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="e8720-673">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="e8720-674">Dieses Attribut enthält die SIP-Adresse eines bestimmten Benutzers.</span><span class="sxs-lookup"><span data-stu-id="e8720-674">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-675">msRTCSIP-Privatsphäre</span><span class="sxs-lookup"><span data-stu-id="e8720-675">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="e8720-676">Dieses Attribut enthält die Geräte-ID des privaten Leitungen-Geräts.</span><span class="sxs-lookup"><span data-stu-id="e8720-676">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="e8720-677">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8720-677">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-678">msRTCSIP – routingfähig</span><span class="sxs-lookup"><span data-stu-id="e8720-678">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="e8720-679">Dieses Attribut ist ein boolesches Attribut, das verwendet wird, um zu bestimmen, ob lync Server berechtigt ist, zu diesem Dienst unter Verwendung seiner GRUU-Adresse weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="e8720-679">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="e8720-680">Wenn dieser Wert auf <strong>true</strong>festgelegt ist, ist lync Server berechtigt, zu diesem Dienst weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="e8720-680">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="e8720-681">Wenn dieser Wert auf " <strong>false</strong>" festgelegt ist, ist lync Server nicht berechtigt, zu diesem Dienst weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="e8720-681">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="e8720-682">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-682">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-683">msRTCSIP-RouteUsageAttribute (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-683">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-684">Dieses einwertige UNICODE-Zeichenfolgenattribut definiert ein Attribut, das die Verwendung für eine Telefonroute qualifiziert.</span><span class="sxs-lookup"><span data-stu-id="e8720-684">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route.</span></span> <span data-ttu-id="e8720-685">Die Auswahl einer Telefonroute wird basierend auf zwei Elementen bestimmt: dem Verwendungsattribut, das der Telefonroute zugewiesen ist, und den zulässigen Richtlinien Verwendungsattributen des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="e8720-685">Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes.</span></span> <span data-ttu-id="e8720-686">Die erste Telefonroute mit einem Nutzungs Attribut, das mit der zulässigen Verwendung des Anrufers übereinstimmt, wird ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="e8720-686">The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="e8720-687">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-687">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8720-688">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-688">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-689">msRTCSIP-RouteUsageLinks (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-689">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-690">Dieses mehrwertige Distinguished Name (DN)-Attribut enthält eine Liste der definierten Namen für die Routenverwendung.</span><span class="sxs-lookup"><span data-stu-id="e8720-690">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="e8720-691">Link weiterleiten: <strong>Link ID 11032</strong></span><span class="sxs-lookup"><span data-stu-id="e8720-691">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="e8720-692">Dieses Attribut ist eine Weiterleitungs Verknüpfung mit der entsprechenden <strong>msRTCSIP-PhoneRouteBL-</strong>Back Link.</span><span class="sxs-lookup"><span data-stu-id="e8720-692">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8720-693">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-693">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-694">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="e8720-694">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="e8720-695">Dieses Attribut enthält den DN, der auf den Pool zeigt, für den der gesamte an diesen MCU-oder vertrauenswürdigen Dienst adressierte SIP-Datenverkehr durchlaufen werden muss.</span><span class="sxs-lookup"><span data-stu-id="e8720-695">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="e8720-696">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8720-696">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-697">msRTCSIP-RuleName (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-697">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-698">Dieses einwertige UNICODE-Zeichenfolgenattribut gibt den Anzeigenamen der Normalisierungsregel an, sodass von einem Administrator einfach auf ihn verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e8720-698">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="e8720-699">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-699">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8720-700">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-700">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-701">msRTCSIP-Schemaversion</span><span class="sxs-lookup"><span data-stu-id="e8720-701">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="e8720-702">Dieses Attribut stellt die derzeit in der Organisation bereitgestellte Schemaversion dar.</span><span class="sxs-lookup"><span data-stu-id="e8720-702">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-703">msRTCSIP-SearchMaxRequests (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-703">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-704">Dieses Attribut schränkt die Anzahl der Suchergebnisse ein, die von einer Verzeichnissuche zurückgegeben werden, wenn ein Benutzer einen Kontakt mithilfe von Communicator sucht.</span><span class="sxs-lookup"><span data-stu-id="e8720-704">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="e8720-705">Dieses Attribut setzt den vom Client bereitgestellten Wert außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="e8720-705">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="e8720-706">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-706">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-707">msRTCSIP-SearchMaxResults (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-707">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-708">Dieses Attribut schränkt die Anzahl der zurückgegebenen Suchanforderungen ein.</span><span class="sxs-lookup"><span data-stu-id="e8720-708">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="e8720-709">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-709">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-710">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="e8720-710">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="e8720-711">Dieses mehrwertige Attribut ist ein Link zurück, der eine Liste mit Distinguished Names (DN) enthält.</span><span class="sxs-lookup"><span data-stu-id="e8720-711">This multi-valued attribute is a back link that contains a list of distinguished names (DN).</span></span> <span data-ttu-id="e8720-712">Diese DNS verweist auf ein Pool-oder <strong>TrustedService</strong> -Objekt.</span><span class="sxs-lookup"><span data-stu-id="e8720-712">These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="e8720-713">Dieses Attribut entspricht dem Forward-Link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8720-713">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8720-714">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-714">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-715">msRTCSIP-Server</span><span class="sxs-lookup"><span data-stu-id="e8720-715">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="e8720-716">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e8720-716">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-717">msRTCSIP-ServerReferenceBL (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-717">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-718">Dieses mehrwertige Attribut enthält eine Liste mit Distinguished Names.</span><span class="sxs-lookup"><span data-stu-id="e8720-718">This multi-valued attribute contains a list of distinguished names.</span></span> <span data-ttu-id="e8720-719">Diese Distinguished Names sind Back Links, die auf andere Serverobjekte verweisen, denen ein Standardmäßiges Standortprofil zugewiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e8720-719">These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="e8720-720">Link zurück: <strong>Link ID 11037</strong></span><span class="sxs-lookup"><span data-stu-id="e8720-720">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="e8720-721">Der entsprechende Weiterleitungslink zu diesem Rück Link ist <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8720-721">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="e8720-722">Dieses Back Link-Attribut verweist nur auf Pools und Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="e8720-722">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="e8720-723">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-723">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8720-724">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-724">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-725">msRTCSIP-Server Version vom</span><span class="sxs-lookup"><span data-stu-id="e8720-725">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="e8720-726">Dieses Attribut definiert die Versionsinformationen des Servers.</span><span class="sxs-lookup"><span data-stu-id="e8720-726">This attribute defines the version information of the server.</span></span> <span data-ttu-id="e8720-727">Diese Versionsnummer gilt für alle Serverrollen.</span><span class="sxs-lookup"><span data-stu-id="e8720-727">This version number applies to all server roles.</span></span> <span data-ttu-id="e8720-728">Es handelt sich um eine monoton wachsende ganze Zahl, die mit jeder offiziellen Produktversion inkrementiert wird.</span><span class="sxs-lookup"><span data-stu-id="e8720-728">It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="e8720-729">Die möglichen gültigen Werte lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e8720-729">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-730">Undefined: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="e8720-730">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="e8720-731">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="e8720-731">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="e8720-732">                 Live Communications Server 2005 mit SP1</span><span class="sxs-lookup"><span data-stu-id="e8720-732">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="e8720-733">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="e8720-733">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="e8720-734">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="e8720-734">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="e8720-735">5: lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e8720-735">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="e8720-736">6: lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8720-736">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8720-737">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-737">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-738">msRTCSIP-Quellobjekttyp</span><span class="sxs-lookup"><span data-stu-id="e8720-738">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="e8720-739">Dieses einwertige Attribut vom Typ Integer gibt den Typ des Objekts an, auf das das <strong>msDS-SourceObjectDN</strong> zeigt, wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e8720-739">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-740">NULL | 0x00000001: stellt ein Windows NT Server-Prinzipal Benutzerobjekt aus einer anderen Gesamtstruktur dar.</span><span class="sxs-lookup"><span data-stu-id="e8720-740">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="e8720-741">Die folgenden Attribute stellen einen Gruppentyp aus einer anderen Gesamtstruktur für die Erweiterung der Verteilergruppe dar:</span><span class="sxs-lookup"><span data-stu-id="e8720-741">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-742">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="e8720-742">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="e8720-743">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="e8720-743">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="e8720-744">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="e8720-744">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="e8720-745">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="e8720-745">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="e8720-746">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="e8720-746">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="e8720-747">0x90000000: stellt eine automatische Telefonzentrale oder ein Teilnehmerzugriffs Objekt aus derselben Gesamtstruktur oder einer anderen Gesamtstruktur dar.</span><span class="sxs-lookup"><span data-stu-id="e8720-747">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="e8720-748">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-748">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-749">msRTCSIP-SubscriptionAuthRequired (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-749">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e8720-750">Neu in Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="e8720-750">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="e8720-751">In Live Communications Server 2005 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-751">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-752">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="e8720-752">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="e8720-753">Mit diesem Attribut können Sie ein Benutzer-oder Kontaktobjekt von einem lync Server Pool in einen anderen migrieren.</span><span class="sxs-lookup"><span data-stu-id="e8720-753">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="e8720-754">Dieses Attribut wird der Contact-Klasse hinzugefügt, da in der zentralen Gesamtstruktur-Topologie Kontaktobjekte und keine Benutzerobjekte SIP-aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="e8720-754">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="e8720-755">Der gültige Wert ist der DN des Ziel Standard Edition-Server oder Front-End-Pool, zu dem ein Benutzer verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="e8720-755">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="e8720-756">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8720-756">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-757">msRTCSIP-TargetPhoneNumber (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-757">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-758">Dieses einwertige Zeichenfolgenattribut enthält ein Telefonnummernmuster oder einen Bereich, der an die in <strong>msRTCSIP-Gateways</strong>definierten Gateways weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e8720-758">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8720-759">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-759">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-760">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="e8720-760">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="e8720-761">Dieses Attribut speichert Name/Wert-Paare für Zielrichtlinien für lync Server Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e8720-761">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="e8720-762">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8720-762">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-763">msRTCSIP-Mandanten-Nr</span><span class="sxs-lookup"><span data-stu-id="e8720-763">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="e8720-764">Dieses Attribut speichert den eindeutigen Bezeichner für einen Mandanten.</span><span class="sxs-lookup"><span data-stu-id="e8720-764">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="e8720-765">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8720-765">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-766">msRTCSIP-Translation (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-766">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-767">Dieses Attribut wird von der VoIP-Funktion von lync Server verwendet und enthält die Übersetzungs Zeichenfolge, die für die gewählte Nummer angewendet wird, wenn eine Übereinstimmung gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="e8720-767">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="e8720-768">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-768">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="e8720-769">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-769">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-770">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="e8720-770">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="e8720-771">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e8720-771">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8720-772">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-772">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-773">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="e8720-773">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="e8720-774">Dieses Attribut ist ein String-Wert, der den FQDN der MCU enthält.</span><span class="sxs-lookup"><span data-stu-id="e8720-774">This attribute is a string value that contains the FQDN of the MCU.</span></span> <span data-ttu-id="e8720-775">Hierbei handelt es sich um ein einwertiges Attribut.</span><span class="sxs-lookup"><span data-stu-id="e8720-775">This is a single-valued attribute.</span></span> <span data-ttu-id="e8720-776">Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN beträgt 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e8720-776">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="e8720-777">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-777">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-778">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="e8720-778">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="e8720-779">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e8720-779">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8720-780">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-780">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-781">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="e8720-781">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="e8720-782">Dieses Attribut ist ein String-Wert, der den FQDN des Servers mit Proxy Server enthält.</span><span class="sxs-lookup"><span data-stu-id="e8720-782">This attribute is a string value that contains the FQDN of the server running Proxy Server.</span></span> <span data-ttu-id="e8720-783">Dieses Attribut ist ein einwertiger Wert.</span><span class="sxs-lookup"><span data-stu-id="e8720-783">This attribute is single-valued.</span></span> <span data-ttu-id="e8720-784">Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN beträgt 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e8720-784">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="e8720-785">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-785">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-786">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="e8720-786">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="e8720-787">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e8720-787">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-788">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="e8720-788">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="e8720-789">Dieses Attribut ist ein Attribut mit einem Wert, das den FQDN eines vertrauenswürdigen Servers darstellt.</span><span class="sxs-lookup"><span data-stu-id="e8720-789">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="e8720-790">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8720-790">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-791">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="e8720-791">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="e8720-792">Dieses Attribut gibt die Versionsnummer eines Servers in der Liste der vertrauenswürdigen Server an.</span><span class="sxs-lookup"><span data-stu-id="e8720-792">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="e8720-793">Die möglichen gültigen Werte lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e8720-793">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-794">NULL: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="e8720-794">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="e8720-795">2: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="e8720-795">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="e8720-796">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="e8720-796">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="e8720-797">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="e8720-797">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="e8720-798">5: lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e8720-798">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="e8720-799">6: lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8720-799">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8720-800">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8720-800">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-801">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="e8720-801">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="e8720-802">Dieses Attribut definiert die Optionen, die für den vertrauenswürdigen Dienst aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="e8720-802">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="e8720-803">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8720-803">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-804">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="e8720-804">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="e8720-805">Dieses mehrwertige Attribut enthält eine Liste mit Distinguished Names (DN), die auf ein vertrauenswürdiges Dienstobjekt verweisen, beispielsweise einen Medien Relay-Authentifizierungsdienst.</span><span class="sxs-lookup"><span data-stu-id="e8720-805">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="e8720-806">Ein Medien Relay-Authentifizierungsdienst (physisch zusammen mit dem Edgeserver, auf dem der A/V-Konferenzdienst ausgeführt wird) muss einem Pool zugeordnet sein, um audioszenarioe für Remotebenutzer zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e8720-806">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="e8720-807">Die entsprechende Backlink to this Forward Link-Attribut ist <strong>msRTCSIP-ServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8720-807">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8720-808">UC</span><span class="sxs-lookup"><span data-stu-id="e8720-808">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-809">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="e8720-809">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="e8720-810">Dieses Attribut ist eine ganze Zahl, die die Portnummer definiert, die zum Herstellen einer Verbindung mit diesem GRUU-Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e8720-810">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="e8720-811">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-811">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-812">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="e8720-812">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="e8720-813">Dieses Attribut ist ein String-Wert, der den Typ des GRUU-Diensts definiert, den er darstellt.</span><span class="sxs-lookup"><span data-stu-id="e8720-813">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="e8720-814">Die gültigen GRUU-Diensttypen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e8720-814">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-815">MediationServer</span><span class="sxs-lookup"><span data-stu-id="e8720-815">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="e8720-816">Gateway</span><span class="sxs-lookup"><span data-stu-id="e8720-816">Gateway</span></span></p></li>
<li><p><span data-ttu-id="e8720-817">Medien Relay-Authentifizierungsdienst (MRAS)</span><span class="sxs-lookup"><span data-stu-id="e8720-817">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="e8720-818">QoSM</span><span class="sxs-lookup"><span data-stu-id="e8720-818">QoSM</span></span></p></li>
<li><p><span data-ttu-id="e8720-819">msRTCSIP-UserExtension-GAV</span><span class="sxs-lookup"><span data-stu-id="e8720-819">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8720-820">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-820">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-821">msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="e8720-821">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="e8720-822">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e8720-822">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8720-823">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-823">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-824">msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="e8720-824">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="e8720-825">Dieses Attribut ist ein String-Wert, der den FQDN des IIS-lync Server Webdienste enthält.</span><span class="sxs-lookup"><span data-stu-id="e8720-825">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="e8720-826">Hierbei handelt es sich um ein einwertiges Attribut.</span><span class="sxs-lookup"><span data-stu-id="e8720-826">This is a single-valued attribute.</span></span> <span data-ttu-id="e8720-827">Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN beträgt 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e8720-827">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="e8720-828">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-828">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-829">msRTCSIP-UCFlags (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-829">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-830">Dieses Attribut definiert unterschiedliche UC-Optionen, die Global für alle Benutzer-oder Kontaktobjekte aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="e8720-830">This attribute defines different UC options that are enabled globally to all user or contact objects.</span></span> <span data-ttu-id="e8720-831">Dieses Attribut ist ein Bitmaskenwert des Typs Integer.</span><span class="sxs-lookup"><span data-stu-id="e8720-831">This attribute is a bit-mask value of integer type.</span></span> <span data-ttu-id="e8720-832">Jede Option wird durch das vorhanden sein von ein Bit dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e8720-832">Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="e8720-833">Der mögliche gültige Wert (und die zugehörige Bit-Position) lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e8720-833">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-834">4: UsePerUserUCPolicy (Bit-Position 2)</span><span class="sxs-lookup"><span data-stu-id="e8720-834">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="e8720-835">Wenn dieses Bit festgelegt ist, wird die UC-Richtlinie pro Benutzerdefiniert.</span><span class="sxs-lookup"><span data-stu-id="e8720-835">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="e8720-836">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-836">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-837">msRTCSIP-UCPolicy (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-837">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-838">Dieses einwertige Attribut enthält den Distinguished Name (DN) der UC-Richtlinie, die der Administrator diesem Benutzer zugewiesen hat.</span><span class="sxs-lookup"><span data-stu-id="e8720-838">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="e8720-839">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-839">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-840">msRTCSIP-UserDomainList (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-840">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="e8720-841">Dieses Attribut enthält eine Liste aller Domänen in einer Gesamtstruktur, die SIP-aktivierte Benutzer hosten.</span><span class="sxs-lookup"><span data-stu-id="e8720-841">This attribute provides a list of all the domains in a forest that host SIP-enabled users.</span></span> <span data-ttu-id="e8720-842">Der Standardwert ist eine leere Liste, die angibt, dass alle Domänen in der Gesamtstruktur SIP-fähig sind.</span><span class="sxs-lookup"><span data-stu-id="e8720-842">The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="e8720-843">Gültige Werte sind mehrere Zeichenfolgen, die die Domänennamen einzelner Domänen darstellen.</span><span class="sxs-lookup"><span data-stu-id="e8720-843">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="e8720-844">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="e8720-844">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="e8720-845">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-845">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-846">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="e8720-846">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="e8720-847">Dieses Attribut bestimmt, ob der Benutzer derzeit für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e8720-847">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-848">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="e8720-848">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="e8720-849">Dieses mehrwertige Attribut enthält eine Liste von Name-Wert-Paaren im Format von &quot; Name = Value. &quot; Dieses Attribut ist für die Replikation des globalen Katalogs gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="e8720-849">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="e8720-850">Neu in Live Communications Server 2005 mit SP1.</span><span class="sxs-lookup"><span data-stu-id="e8720-850">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-851">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="e8720-851">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="e8720-852">Dieses Attribut enthält den Distinguished Name (DN), der auf ein Standortprofilobjekt zeigt.</span><span class="sxs-lookup"><span data-stu-id="e8720-852">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="e8720-853">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8720-853">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-854">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="e8720-854">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="e8720-855">Dieses Attribut speichert Name/Wert-Paare für Benutzerrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="e8720-855">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="e8720-856">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8720-856">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-857">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="e8720-857">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="e8720-858">Hierbei handelt es sich um ein mehrwertiges Attribut mit einer Liste von Distinguished Names with Binary (DN_WITH_BINARY), die auf globale Benutzerrichtlinien verschiedener Typen verweist.</span><span class="sxs-lookup"><span data-stu-id="e8720-858">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types.</span></span> <span data-ttu-id="e8720-859">Der binäre Teil gibt den Typ der Richtlinie an, auf die der DN-Teil zeigt.</span><span class="sxs-lookup"><span data-stu-id="e8720-859">The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="e8720-860">Die gültigen binären Werte lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e8720-860">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-861">0x00000001: Besprechungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="e8720-861">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="e8720-862">0x00000002: UC-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="e8720-862">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="e8720-863">0x00000005: Anwesenheitsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="e8720-863">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8720-864">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-864">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-865">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="e8720-865">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="e8720-p165">Dies ist die SIP-Routinggruppen-ID. Benutzer in derselben Gruppe registrieren sich beim selben Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="e8720-p165">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="e8720-868">Neu in lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8720-868">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-869">msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="e8720-869">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="e8720-870">Hierbei handelt es sich um ein mehrwertiges Attribut.</span><span class="sxs-lookup"><span data-stu-id="e8720-870">This is a multi-valued attribute.</span></span> <span data-ttu-id="e8720-871">Dieses Attribut ist für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e8720-871">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="e8720-872">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-872">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-873">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="e8720-873">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="e8720-874">Dieses einwertige Attribut verweist auf den Pool oder Standard Edition-Server, zu dem die Webkomponenten gehören.</span><span class="sxs-lookup"><span data-stu-id="e8720-874">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="e8720-875">Link weiterleiten: <strong>Link ID 11028</strong></span><span class="sxs-lookup"><span data-stu-id="e8720-875">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="e8720-876">Die entsprechende Backlink to this Forward Link-Attribut ist <strong>msRTCSIP-WebComponentsServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8720-876">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8720-877">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-877">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-878">msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="e8720-878">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="e8720-879">Dieses Attribut ist eine mehrwertige Liste mit Distinguished Names.</span><span class="sxs-lookup"><span data-stu-id="e8720-879">This attribute is a multi-valued list of distinguished names.</span></span> <span data-ttu-id="e8720-880">Dieses Attribut enthält eine Liste aller Webserver, die diesem Pool zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e8720-880">This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="e8720-881">Link zurück: <strong>Link ID 11029</strong></span><span class="sxs-lookup"><span data-stu-id="e8720-881">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="e8720-882">Der entsprechende Weiterleitungslink zu diesem Rück Link ist <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="e8720-882">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="e8720-883">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e8720-883">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-884">msRTCSIP-WMIInstanceId (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e8720-884">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e8720-885">Neu in Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="e8720-885">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="e8720-886">In Live Communications Server 2005 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8720-886">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-887">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="e8720-887">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="e8720-888">Dieses vorhandene Active Directory-Attribut wird von der Telefonie verwendet, um die Liste der alternativen TCP/IP-Adressen für ein Telefon anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e8720-888">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="e8720-889">Neu in Windows Server 2008 Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="e8720-889">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-890">PhoneOfficeOther</span><span class="sxs-lookup"><span data-stu-id="e8720-890">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="e8720-891">Dieses vorhandene Active Directory Attribut wird von den VoIP-Komponenten in lync Server nur für Kontaktobjekte verwendet, um Anrufe an die automatische Telefonzentrale und Teilnehmerzugriffsnummern weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="e8720-891">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="e8720-892">Die bedingungslose Anruf Weiterleitungsadresse wird in diesem mehrwertigen Attribut gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e8720-892">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="e8720-893">Dieses Konto wird für den speziellen Zweck der automatischen Telefonzentrale und des Teilnehmerzugriffs erstellt.</span><span class="sxs-lookup"><span data-stu-id="e8720-893">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="e8720-894">Die Attribute dieses Kontos sollten von Administratoren nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e8720-894">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="e8720-895">Neu im Betriebssystem Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="e8720-895">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8720-896">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="e8720-896">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="e8720-897">Dieses vorhandene Active Directory mehrwertige Attribut ist Teil des grundlegenden Active Directory Schemas, das in Windows 2000 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="e8720-897">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="e8720-898">Dieses Attribut enthält die verschiedenen X400-, x500-und SMTP-Adressen der e-Mail-Adresse des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="e8720-898">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="e8720-899">In Live Communications Server 2003 und höher wird der SIP-URI des Benutzers mithilfe des SIP:-Tags zu dieser Liste hinzugefügt &quot; &quot; .</span><span class="sxs-lookup"><span data-stu-id="e8720-899">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="e8720-900">Die folgenden Anwendungen durchsuchen den SIP-URI des Benutzers aus diesem Attribut:</span><span class="sxs-lookup"><span data-stu-id="e8720-900">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="e8720-901">Microsoft Office Outlook 2003 Messaging-und Zusammenarbeitsclient</span><span class="sxs-lookup"><span data-stu-id="e8720-901">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="e8720-902">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="e8720-902">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8720-903">Neu im Betriebssystem Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="e8720-903">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8720-904">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="e8720-904">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="e8720-905">Dieses vorhandene Active Directory-Attribut enthält die Telefonnummer für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e8720-905">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="e8720-906">Neu im Betriebssystem Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="e8720-906">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

