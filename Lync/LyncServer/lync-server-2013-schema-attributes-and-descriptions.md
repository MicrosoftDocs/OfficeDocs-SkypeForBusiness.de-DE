---
title: 'Lync Server 2013: Schema Attribute und Beschreibungen'
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
ms.openlocfilehash: 72da4adb0f660604dba7f20c9ddc333425086df2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="97e5f-102">Schema Attribute und Beschreibungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97e5f-102">Schema attributes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97e5f-103">_**Letztes Änderungsdatum des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="97e5f-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="97e5f-104">In diesem Abschnitt werden alle Schema Attribute beschrieben, die von lync Server 2013 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="97e5f-104">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="97e5f-105">Informationen zu den Klassen, die Attributen zugeordnet sind, finden Sie unter [Schema Attribute nach Klasse in lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="97e5f-105">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="97e5f-106">Eine Liste der Klassen und Attribute, die in lync Server 2013 neu sind, finden Sie unter [Schema Änderungen in lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="97e5f-106">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="97e5f-107">Attribute, die verknüpfte Paare sind, werden als Weiterleitungs-oder zurück-Links angegeben.</span><span class="sxs-lookup"><span data-stu-id="97e5f-107">Attributes that are linked pairs are specified as forward links or back links.</span></span> <span data-ttu-id="97e5f-108">Ein Attribut, das auf ein anderes Objekt verweist, ist ein Weiterleitungslink; das Attribut des anderen Objekts, das auf das erste Objekt zurückverweist, ist ein Link zurück.</span><span class="sxs-lookup"><span data-stu-id="97e5f-108">An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link.</span></span> <span data-ttu-id="97e5f-109">Forward-Links sind aktualisierbare, während zurück-Links schreibgeschützt sind.</span><span class="sxs-lookup"><span data-stu-id="97e5f-109">Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="97e5f-110">Einige Attribute weisen einen Bitmaskenwert auf.</span><span class="sxs-lookup"><span data-stu-id="97e5f-110">Some attributes have a bit-mask value.</span></span> <span data-ttu-id="97e5f-111">Bei diesen Attributen wird jede Einstellung durch ein Bit dargestellt, und der angezeigte Dezimalwert stellt die Bit-Position dar.</span><span class="sxs-lookup"><span data-stu-id="97e5f-111">For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position.</span></span> <span data-ttu-id="97e5f-112">Bit-Positionen beginnen mit Bit 0.</span><span class="sxs-lookup"><span data-stu-id="97e5f-112">Bit positions start with bit 0.</span></span> <span data-ttu-id="97e5f-113">Beispiel: 1 (Binary) ist Bit 0-Satz und 10000 (binär) ist Bit 4 gesetzt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-113">For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set.</span></span> <span data-ttu-id="97e5f-114">Jedes Bit stellt eine Eigenschaft dar.</span><span class="sxs-lookup"><span data-stu-id="97e5f-114">Each bit represents a property.</span></span> <span data-ttu-id="97e5f-115">Im folgenden finden Sie einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="97e5f-115">The following are some examples:</span></span>

  - <span data-ttu-id="97e5f-116">10000 (Binary) hat einen Dezimalwert von 16 (das heißt, Bit 4 ist festzulegen).</span><span class="sxs-lookup"><span data-stu-id="97e5f-116">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="97e5f-117">100 Millionen (Binary) hat einen Dezimalwert von 256 (das heißt, Bit 8 ist festzulegen).</span><span class="sxs-lookup"><span data-stu-id="97e5f-117">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="97e5f-118">1100 (Binary) hat den Dezimalwert 12 (das heißt, Bits 2 und 3 werden festgesetzt; die von beiden Bits dargestellten Eigenschaften sind aktiviert).</span><span class="sxs-lookup"><span data-stu-id="97e5f-118">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="97e5f-119">1111000001 (Binary) hat einen Dezimalwert von 961 (das heißt, Bits 0, 6, 7, 8 und 9 werden festgesetzt; Eigenschaften für jedes dieser Bits sind aktiviert).</span><span class="sxs-lookup"><span data-stu-id="97e5f-119">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="97e5f-120">Schema Attribute für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97e5f-120">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97e5f-121">Attribut</span><span class="sxs-lookup"><span data-stu-id="97e5f-121">Attribute</span></span></th>
<th><span data-ttu-id="97e5f-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="97e5f-122">Description</span></span></th>
<th><span data-ttu-id="97e5f-123">Kommentare</span><span class="sxs-lookup"><span data-stu-id="97e5f-123">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-124">DNSHostName</span><span class="sxs-lookup"><span data-stu-id="97e5f-124">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="97e5f-125">Ein vorhandenes Attribut in den Active Directory-Domänendiensten, das jetzt den <strong>Attribut msRTCSIP-</strong> und <strong>Attribut msRTCSIP-MonitoringServer</strong> -Klassen zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="97e5f-125">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="97e5f-126">Dieses Attribut gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) eines Pools oder Überwachungsservers an.</span><span class="sxs-lookup"><span data-stu-id="97e5f-126">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="97e5f-127">Ein gültiger Wert für jedes Segment ist 63 Zeichen; ein gültiger Wert für den gesamten FQDN ist 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="97e5f-127">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-128">Neu in Microsoft Office Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-128">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-129">MSDS-SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="97e5f-129">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="97e5f-130">Dieses Attribut enthält die Zeichenfolgendarstellung des Distinguished Name (DN) des Objekts in einer anderen Gesamtstruktur, die diesem Objekt entspricht.</span><span class="sxs-lookup"><span data-stu-id="97e5f-130">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object.</span></span> <span data-ttu-id="97e5f-131">Dieses Attribut wird für die Erweiterung der Verteilergruppe und für die automatische Anwesenheit verwendet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-131">This attribute is used for distribution group expansion and auto attendance.</span></span> <span data-ttu-id="97e5f-132">Dieses Attribut ist im standardmäßigen Active Directory-Schema für Windows Server 2003 R2 definiert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-132">This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="97e5f-133">Um zu vermeiden, dass ein Upgrade von AD DS auf Windows Server 2003 R2 erforderlich ist, wird das Windows Server 2003-Schema durch die Active Directory-Schemavorbereitung mit dieser Attributdefinition erweitert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-133">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-134">Neu in Microsoft Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-134">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-135">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="97e5f-135">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="97e5f-136">Dieses mehrwertige Attribut enthält Einstellungen für Voicemail.</span><span class="sxs-lookup"><span data-stu-id="97e5f-136">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="97e5f-137">Dieses Attribut wird für Exchange Unified Messaging (um) freigegeben.</span><span class="sxs-lookup"><span data-stu-id="97e5f-137">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="97e5f-138">Neu in Microsoft lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="97e5f-138">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-139">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="97e5f-139">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="97e5f-140">Dieses mehrwertige Attribut enthält Bezeichner für für den Benutzer geltende Aufbewahrungsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="97e5f-140">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="97e5f-141">Aufbewahrungsrichtlinien behalten Postfachelemente für den Benutzer für die Dauer des haltebereichs bei.</span><span class="sxs-lookup"><span data-stu-id="97e5f-141">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="97e5f-142">Dieses Attribut wird für Exchange 2013 freigegeben.</span><span class="sxs-lookup"><span data-stu-id="97e5f-142">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-143">Neu in lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="97e5f-143">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-144">Attribut msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="97e5f-144">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="97e5f-145">Dieses Attribut speichert Informationen zu Audiokonferenz-Anbietern für einen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="97e5f-145">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-146">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="97e5f-146">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-147">Attribut msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="97e5f-147">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="97e5f-148">Dieses Attribut verweist auf den vertrauenswürdigen Diensteintrag für den Anwendungs Kontakt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-148">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-149">Neu in Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="97e5f-149">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-150">Attribut msRTCSIP-applicationlist</span><span class="sxs-lookup"><span data-stu-id="97e5f-150">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="97e5f-151">Dieses Attribut enthält eine Liste der gehosteten Anwendungen auf dem Anwendungsserver.</span><span class="sxs-lookup"><span data-stu-id="97e5f-151">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-152">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="97e5f-152">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-153">Attribut msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="97e5f-153">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="97e5f-154">Dieses Attribut gibt die Optionen für den Anwendungs Kontakt an.</span><span class="sxs-lookup"><span data-stu-id="97e5f-154">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-155">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="97e5f-155">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-156">Attribut msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="97e5f-156">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="97e5f-157">Dieses Attribut enthält die primäre Sprache für den Anwendungs Kontakt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-157">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-158">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="97e5f-158">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-159">Attribut msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="97e5f-159">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="97e5f-160">Dieses Attribut mit mehreren Werten enthält die sekundären Sprachen für den Anwendungs Kontakt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-160">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-161">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="97e5f-161">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-162">Attribut msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="97e5f-162">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="97e5f-163">Dieses Attribut enthält eine Liste der Anwendungsserver, die zu diesem Pool gehören.</span><span class="sxs-lookup"><span data-stu-id="97e5f-163">This attribute contains a list of application servers that belong to this pool.</span></span> <span data-ttu-id="97e5f-164">Der entsprechende Forward-Link zu diesem zurück Link-Attribut lautet <strong>Attribut msRTCSIP-ApplicationServerPoolLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="97e5f-164">The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-165">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="97e5f-165">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-166">Attribut msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="97e5f-166">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="97e5f-167">Dieses Attribut verweist auf den Pool, zu dem dieser Anwendungsserver gehört.</span><span class="sxs-lookup"><span data-stu-id="97e5f-167">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="97e5f-168">Dies ist der Link weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="97e5f-168">This is the forward link.</span></span> <span data-ttu-id="97e5f-169">Der entsprechende rückwärts Link lautet <strong>Attribut msRTCSIP-ApplicationServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="97e5f-169">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-170">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="97e5f-170">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-171">Attribut msRTCSIP-ArchiveDefault (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-171">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="97e5f-172">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-172">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="97e5f-173">Veraltet in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-173">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-174">Attribut msRTCSIP-ArchiveDefaultFlags (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-174">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-175">Dieses Attribut gibt den globalen Standardwert innerhalb der Gesamtstrukturgrenze für die Archivierung der gesamten Benutzerkommunikation an.</span><span class="sxs-lookup"><span data-stu-id="97e5f-175">This attribute specifies the global default within the forest boundary for archiving all user communications.</span></span> <span data-ttu-id="97e5f-176">Dies wird vom Archivierungs-Agent-Layer erzwungen.</span><span class="sxs-lookup"><span data-stu-id="97e5f-176">This is enforced by the archiving agent layer.</span></span> <span data-ttu-id="97e5f-177">Der Wertebereich für dieses Attribut lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="97e5f-177">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-178"><strong>True</strong>: alle Benutzer archivieren</span><span class="sxs-lookup"><span data-stu-id="97e5f-178"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="97e5f-179"><strong>Falsch</strong>: nicht alle Benutzer archivieren</span><span class="sxs-lookup"><span data-stu-id="97e5f-179"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="97e5f-180">Dieses Attribut steuert Global innerhalb der Gesamtstruktur-Grenze, wie die Benutzerkommunikation in einem internen Netzwerk archiviert wird.</span><span class="sxs-lookup"><span data-stu-id="97e5f-180">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="97e5f-181"><strong>Live Communications Server 2005-Verhalten (jetzt eingestellt)</strong></span><span class="sxs-lookup"><span data-stu-id="97e5f-181"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="97e5f-182">Der Wertebereich für dieses Attribut lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="97e5f-182">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-183">0: Archivieren des Nachrichtentexts [Bit 0]</span><span class="sxs-lookup"><span data-stu-id="97e5f-183">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="97e5f-184">1: den Nachrichtentext nicht archivieren [Bit 0]</span><span class="sxs-lookup"><span data-stu-id="97e5f-184">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="97e5f-185"><strong>Office Communications Server 2007-Verhalten</strong></span><span class="sxs-lookup"><span data-stu-id="97e5f-185"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="97e5f-186">Der Wertebereich für dieses Attribut lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="97e5f-186">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-187">0: ArchiveFederationDefaultWithoutBody (eingestellt)</span><span class="sxs-lookup"><span data-stu-id="97e5f-187">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-188">1-2: ArchiveInternalCommunications</span><span class="sxs-lookup"><span data-stu-id="97e5f-188">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="97e5f-189">3-4: ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="97e5f-189">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="97e5f-190">5: RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="97e5f-190">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="97e5f-191">6: RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="97e5f-191">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="97e5f-192">7: RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="97e5f-192">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="97e5f-193">8: RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="97e5f-193">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="97e5f-194">9: RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="97e5f-194">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="97e5f-195">10: RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="97e5f-195">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="97e5f-196">11: RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="97e5f-196">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="97e5f-197">12: RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="97e5f-197">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="97e5f-198">13: RecordMeetingInstantiations</span><span class="sxs-lookup"><span data-stu-id="97e5f-198">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="97e5f-199">14: RecordMeetingJoins</span><span class="sxs-lookup"><span data-stu-id="97e5f-199">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="97e5f-200">15: RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="97e5f-200">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="97e5f-201">16: RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="97e5f-201">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="97e5f-202">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-202">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="97e5f-203">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-203">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-204">Attribut msRTCSIP-ArchiveFederationDefault (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-204">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="97e5f-205">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-205">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="97e5f-206">Veraltet in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-206">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-207">Attribut msRTCSIP-ArchiveFederationDefaultFlags (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-207">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="97e5f-208">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-208">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="97e5f-209">Veraltet in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-209">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-210">Attribut msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="97e5f-210">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="97e5f-211">Dieses Attribut ist eine ganze Zahl, die als Bitfeld verwendet wird, um zu steuern, ob die Kommunikation eines einzelnen Benutzers archiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="97e5f-211">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived.</span></span> <span data-ttu-id="97e5f-212">Dieses Steuerelement wird vom Archivierungs-Agent-Layer erzwungen.</span><span class="sxs-lookup"><span data-stu-id="97e5f-212">This control is enforced by the archiving agent layer.</span></span> <span data-ttu-id="97e5f-213">Sie ist für die Replikation des globalen Katalogs markiert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-213">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="97e5f-214">Der Bereich dieses Attributs ist für einen einzelnen Benutzer oder Kontakt spezifisch.</span><span class="sxs-lookup"><span data-stu-id="97e5f-214">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="97e5f-215">Die gültigen Werte (und zugeordnete Bit-Positionen) in lync Server lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="97e5f-215">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-216">0: nicht archivieren (kein Bit-Satz)</span><span class="sxs-lookup"><span data-stu-id="97e5f-216">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-217">1: eingestellt (Bit-Position 0)</span><span class="sxs-lookup"><span data-stu-id="97e5f-217">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-218">2: eingestellt (Bit-Position 1)</span><span class="sxs-lookup"><span data-stu-id="97e5f-218">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-219">4: Archivieren interner Kommunikation (Bit-Position 2)</span><span class="sxs-lookup"><span data-stu-id="97e5f-219">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-220">8: Archivieren der Föderations Kommunikation (Bit-Position 3)</span><span class="sxs-lookup"><span data-stu-id="97e5f-220">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="97e5f-221">Zuvor gültige Werte in Live Communications Server 2005 lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="97e5f-221">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-222">0: Verwenden Sie den Standardwert, der in dieser Rangfolge von <strong>Attribut msRTCSIP-ArchiveDefault</strong> und <strong>Attribut msRTCSIP-ArchiveFederation</strong> definiert ist:</span><span class="sxs-lookup"><span data-stu-id="97e5f-222">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-223">1: Archivieren</span><span class="sxs-lookup"><span data-stu-id="97e5f-223">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="97e5f-224">2: nicht archivieren</span><span class="sxs-lookup"><span data-stu-id="97e5f-224">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="97e5f-225">3: Archivieren ohne Nachrichtentext</span><span class="sxs-lookup"><span data-stu-id="97e5f-225">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="97e5f-226">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-226">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-227">Attribut msRTCSIP-ArchivingServerData (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-227">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-228">Dieses Attribut ist für die spätere Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-228">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-229">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-229">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-230">Attribut msRTCSIP-ArchivingServerVersion (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-230">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-231">Dieses Attribut definiert die Version des Archivierungsdiensts.</span><span class="sxs-lookup"><span data-stu-id="97e5f-231">This attribute defines the version of the Archiving service.</span></span> <span data-ttu-id="97e5f-232">Bei diesem Attribut handelt es sich um einen monoton zunehmenden ganzzahligen Typ, der mit jeder offiziellen Produktversion inkrementiert wird.</span><span class="sxs-lookup"><span data-stu-id="97e5f-232">This attribute is a monotonously increasing integer type that increments with each official product release.</span></span> <span data-ttu-id="97e5f-233">Die möglichen gültigen Werte lauten:</span><span class="sxs-lookup"><span data-stu-id="97e5f-233">The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-234">Undefined: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="97e5f-234">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="97e5f-235">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="97e5f-235">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="97e5f-236">                 Live Communications Server 2005 mit SP1</span><span class="sxs-lookup"><span data-stu-id="97e5f-236">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="97e5f-237">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="97e5f-237">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="97e5f-238">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="97e5f-238">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="97e5f-239">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-239">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="97e5f-240">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-241">Attribut msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="97e5f-241">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="97e5f-242">Dieses Attribut gibt den FQDN des Back-End-Servers des Pools an.</span><span class="sxs-lookup"><span data-stu-id="97e5f-242">This attribute specifies the FQDN of the Back End Server of the pool.</span></span> <span data-ttu-id="97e5f-243">Da es nur einen einzigen Back-End-Server pro Pool geben kann, handelt es sich hierbei um ein Single-Value-Attribut.</span><span class="sxs-lookup"><span data-stu-id="97e5f-243">Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="97e5f-244">Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN ist 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="97e5f-244">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-245">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-245">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-246">Attribut msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="97e5f-246">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="97e5f-247">Dieses Attribut enthält den Bezeichner des Pools, der das Konferenzverzeichnis hostet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-247">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-248">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="97e5f-248">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-249">Attribut msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="97e5f-249">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="97e5f-250">Dieses Attribut enthält den Bezeichner eines Konferenz Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="97e5f-250">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-251">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="97e5f-251">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-252">Attribut msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="97e5f-252">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="97e5f-253">Dieses Attribut enthält den Bezeichner des Pools, in den das Konferenzverzeichnis verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="97e5f-253">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-254">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="97e5f-254">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-255">Attribut msRTCSIP-Standard</span><span class="sxs-lookup"><span data-stu-id="97e5f-255">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="97e5f-256">Dieses boolesche Attribut definiert, ob es sich bei der Verwendung des Telefons um eine Standardverwendung handelt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-256">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="97e5f-257">Wenn dieses Attribut auf " <strong>true</strong>" festgelegt ist, handelt es sich bei der Verwendung des Telefons um eine Standardverwendung, die vom Administrator nicht gelöscht werden kann.</span><span class="sxs-lookup"><span data-stu-id="97e5f-257">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="97e5f-258">Wenn dieses Attribut auf " <strong>false</strong>" festgelegt ist, kann die Verwendung gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="97e5f-258">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-259">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-259">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-260">Attribut msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="97e5f-260">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="97e5f-261">Dieses Attribut identifiziert die Communicator Web Access-URL für Benutzer, die sich außerhalb der Organisation befinden.</span><span class="sxs-lookup"><span data-stu-id="97e5f-261">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-262">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="97e5f-262">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-263">Attribut msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="97e5f-263">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="97e5f-264">Dieses Attribut identifiziert die Communicator Web Access-URL für Benutzer, die sich innerhalb der Organisation befinden.</span><span class="sxs-lookup"><span data-stu-id="97e5f-264">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-265">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="97e5f-265">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-266">Attribut msRTCSIP-DefaultLocationProfileLink (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-266">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-267">Dieses Attribut mit einem Wert enthält den Distinguished Name (DN) eines ihm zugewiesenen Standortprofil-Klassenobjekts.</span><span class="sxs-lookup"><span data-stu-id="97e5f-267">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="97e5f-268">Link weiterleiten: <strong>Link-ID 11036</strong></span><span class="sxs-lookup"><span data-stu-id="97e5f-268">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="97e5f-269">Der entsprechende rückwärts Link lautet <strong>Attribut msRTCSIP-ServerReferenceBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="97e5f-269">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-270">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-270">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-271">Attribut msRTCSIP-DefaultPolicy (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-271">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-272">Dieses boolesche Attribut gibt an, ob es sich bei der Richtlinie um eine Standardrichtlinie handelt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-272">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="97e5f-273">Die Richtlinie ist eine Standardrichtlinie, wenn Sie auf " <strong>true</strong>" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="97e5f-273">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-274">Neu in Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="97e5f-274">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="97e5f-275">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-275">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-276">Attribut msRTCSIP-DefaultRouteToEdgeProxy (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-276">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-277">Dieses Attribut gibt den FQDN des Edge-Servers an, auf dem der Access-Edgedienst ausgeführt wird, wenn er direkt aufgerufen werden kann, oder des Hardwarelastenausgleichs für einen Serverpool, auf dem Access Edge Service ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="97e5f-277">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="97e5f-278">Wenn auf den Servern, auf denen Access Edge Service ausgeführt wird, nur über einen oder mehrere Directors zugegriffen werden kann, gibt dieses Attribut den FQDN und optional die Portnummer des Directors oder des Hardwarelastenausgleichs an, der einen Director-Pool bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-278">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="97e5f-279">Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN ist 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="97e5f-279">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-280">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-280">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="97e5f-281">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-281">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-282">Attribut msRTCSIP-DefaultRouteToEdgeProxyPort (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-283">Dieses Attribut stellt die Portnummer dar, die für die Verbindung mit dem Server, auf dem Access Edge Service ausgeführt wird, verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="97e5f-283">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="97e5f-284">Der gültige Wert ist ein ganzzahliger Wert, der den zu verwendenden Port angibt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-284">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="97e5f-285">Der Standardwert ist 5061.</span><span class="sxs-lookup"><span data-stu-id="97e5f-285">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-286">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-286">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="97e5f-287">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-287">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-288">Attribut msRTCSIP-DefPresenceSubscriptionTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-289">Dieses Attribut stellt den Standardtimeout Zeitraum für Anwesenheitsabonnements dar.</span><span class="sxs-lookup"><span data-stu-id="97e5f-289">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-290">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-290">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-291">Attribut msRTCSIP-DefRegistrationTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-291">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-292">Dieses Attribut steht für das Standardtimeout Fenster für die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="97e5f-292">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-293">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-293">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-294">Attribut msRTCSIP-DefRoamingDataSubscriptionTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-295">Dieses Attribut steht für das Standardtimeout Fenster des Roaming-Daten Abonnements.</span><span class="sxs-lookup"><span data-stu-id="97e5f-295">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-296">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-296">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-297">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="97e5f-297">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="97e5f-298">Dieses Attribut wird in einer geteilten Domänentopologie verwendet und enthält einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN).</span><span class="sxs-lookup"><span data-stu-id="97e5f-298">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="97e5f-299">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="97e5f-299">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-300">Attribut msRTCSIP-Description (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-300">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-301">Dieses Single-Value-UNICODE-Zeichenfolgenattribut enthält eine Beschreibung dieser Telefonroute oder Normalisierungsregel.</span><span class="sxs-lookup"><span data-stu-id="97e5f-301">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-302">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-302">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="97e5f-303">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-303">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-304">Attribut msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="97e5f-304">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="97e5f-305">Dieses Attribut ist für die spätere Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-305">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-306">Attribut msRTCSIP-Domänenname</span><span class="sxs-lookup"><span data-stu-id="97e5f-306">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="97e5f-307">Dieses Attribut stellt eine für die Registrierungsstelle konfigurierte Domäne dar.</span><span class="sxs-lookup"><span data-stu-id="97e5f-307">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-308">Attribut msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="97e5f-308">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="97e5f-309">Dieses Attribut ist für die spätere Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-309">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-310">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-310">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-311">Attribut msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="97e5f-311">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="97e5f-312">Dieses Attribut gibt den FQDN des Servers an, auf dem Access Edge-Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="97e5f-312">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="97e5f-313">Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN ist 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="97e5f-313">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-314">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-314">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-315">Attribut msRTCSIP-EnableBestEffortNotify (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-315">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-316">Dieses Attribut steuert, ob ein Server als Antwort auf eine subscribe-Anforderung von einem Client eine Aufforderung zur Benachrichtigung über beste Leistung (BENOTIFY) anstelle einer Benachrichtigungsanforderung generiert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-316">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client.</span></span> <span data-ttu-id="97e5f-317">BENOTIFY ist eine leistungsverbessernde Erweiterung des Subscribe-Benachrichtigungs Handshakes, bei der der Server statt regelmäßiger Benachrichtigungsanforderungen BENOTIFY-Anforderungen generiert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-317">BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests.</span></span> <span data-ttu-id="97e5f-318">Der Leistungsvorteil besteht darin, dass eine BENOTIFY-Anforderung keine 200-OK-Antwort vom Client erfordert, wie dies bei der Benachrichtigungsanforderung der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="97e5f-318">The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="97e5f-319">Die gültigen Werte sind " <strong>wahr</strong> " oder " <strong>falsch</strong>".</span><span class="sxs-lookup"><span data-stu-id="97e5f-319">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="97e5f-320">Live Communications Server 2003 unterstützt keine BENOTIFY-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="97e5f-320">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="97e5f-321">Um mit Serveranwendungen zu interagieren, die mit der Live Communications Server 2003-Server-API auf Live Communications Server 2005-und Drittanbieterservern geschrieben wurden, können BENOTIFY-Anforderungen deaktiviert werden, indem der Wert auf <STRONG>false</STRONG>festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="97e5f-321">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="97e5f-322">BENOTIFY ist derzeit nicht Teil des IETF (Internet Engineering Task Force) SIP-Standardisierungsprozesses.</span><span class="sxs-lookup"><span data-stu-id="97e5f-322">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="97e5f-323">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-323">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="97e5f-324">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-324">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-325">Attribut msRTCSIP-EnableFederation (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-325">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-326">Dieses Attribut ist ein globaler Schalter, den IT-Administratoren verwenden, um zu konfigurieren, ob Benutzer mit Benutzern aus anderen Organisationen kommunizieren dürfen.</span><span class="sxs-lookup"><span data-stu-id="97e5f-326">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations.</span></span> <span data-ttu-id="97e5f-327">Sie ermöglicht es einem Administrator, das <strong>FederationEnabled</strong> -Attribut eines einzelnen Benutzers zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="97e5f-327">It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute.</span></span> <span data-ttu-id="97e5f-328">Dieses Attribut kann hilfreich sein, um das interne Netzwerk vor Internet Angriffen zu schützen, die möglicherweise durch Würmer, Viren oder gezielte Angriffe auf das Unternehmen verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="97e5f-328">This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="97e5f-329">Die gültigen Werte (und zugeordnete Bit-Positionen) lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="97e5f-329">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-330">1: aktiviert für öffentliche Chat Verbindungen (Bit-Position 0)</span><span class="sxs-lookup"><span data-stu-id="97e5f-330">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-331">2: reserviert (Bit-Position 1)</span><span class="sxs-lookup"><span data-stu-id="97e5f-331">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-332">4: reserviert (Bit-Position 2)</span><span class="sxs-lookup"><span data-stu-id="97e5f-332">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-333">8: reserviert (Bit-Position 3)</span><span class="sxs-lookup"><span data-stu-id="97e5f-333">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-334">16: Remote-Anrufsteuerung aktiviert [Telefonie] (Bit-Position 4)</span><span class="sxs-lookup"><span data-stu-id="97e5f-334">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-335">64: AllowOrganizeMeetingWithAnonymousParticipants lautet (Benutzern gestatten, anonyme Benutzer zu Besprechungen einzuladen (Bit-Position 6)</span><span class="sxs-lookup"><span data-stu-id="97e5f-335">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-336">128: UCEnabled (Aktivieren von Benutzern für Unified Communications) (Bit-Position 7)</span><span class="sxs-lookup"><span data-stu-id="97e5f-336">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-337">256: EnabledForEnhancedPresence (Aktivieren des Benutzers für öffentliche Chat Verbindungen) (Bit-Position 8)</span><span class="sxs-lookup"><span data-stu-id="97e5f-337">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-338">512: RemoteCallControlDualMode (Bit-Position 9)</span><span class="sxs-lookup"><span data-stu-id="97e5f-338">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="97e5f-339">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-339">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="97e5f-340">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-340">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-341">Attribut msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="97e5f-341">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="97e5f-342">Dieses Attribut gibt an, ob die Enterprise-Dienste auf dem angegebenen Server geladen werden.</span><span class="sxs-lookup"><span data-stu-id="97e5f-342">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-343">Attribut msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="97e5f-343">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="97e5f-344">Dieses Attribut ist für die spätere Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-344">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-345">Attribut msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="97e5f-345">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="97e5f-346">Dieses Attribut enthält die Wähl Vorwahl für den externen Zugriff.</span><span class="sxs-lookup"><span data-stu-id="97e5f-346">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-347">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="97e5f-347">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-348">Attribut msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="97e5f-348">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="97e5f-349">Dieses Attribut steuert, ob ein einzelner Benutzer für den Verbund aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="97e5f-349">This attribute controls whether a single user is enabled for federation.</span></span> <span data-ttu-id="97e5f-350">Sie wird von der Enterprise Services-Schicht erzwungen.</span><span class="sxs-lookup"><span data-stu-id="97e5f-350">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="97e5f-351">Sie ist für die Replikation des globalen Katalogs markiert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-351">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="97e5f-352">Die gültigen Werte sind " <strong>wahr</strong> " oder " <strong>falsch</strong>".</span><span class="sxs-lookup"><span data-stu-id="97e5f-352">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-353">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-353">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-354">Attribut msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="97e5f-354">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="97e5f-355">Dieses Attribut ist eine mehrwertige Liste der Domänennamen aller Enterprise Edition-Server, die einem Pool zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="97e5f-355">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="97e5f-356">Link zurück: <strong>Link-ID 11023</strong></span><span class="sxs-lookup"><span data-stu-id="97e5f-356">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="97e5f-357">Der entsprechende Weiterleitungslink zu diesem zurück <strong>-Link lautet Attribut msRTCSIP-PoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="97e5f-357">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-358">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-358">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-359">Attribut msRTCSIP-Gateways (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-359">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-360">Dieses Attribut für mehrwertige Zeichenfolgen enthält eine Liste der Gateways und Ports (pro Gateway).</span><span class="sxs-lookup"><span data-stu-id="97e5f-360">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="97e5f-361">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-361">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-362">Attribut msRTCSIP-GlobalSettingsData (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-362">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-363">Dieses Attribut speichert Name: Wert-Paare.</span><span class="sxs-lookup"><span data-stu-id="97e5f-363">This attribute stores name:value pairs.</span></span> <span data-ttu-id="97e5f-364">Das bereits definierte Name: Wert-Paar ist für die Einstellung <strong>Polling für Anwesenheit zulassen</strong> .</span><span class="sxs-lookup"><span data-stu-id="97e5f-364">The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-365">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-365">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-366">Attribut msRTCSIP-Gruppierungs-Nr</span><span class="sxs-lookup"><span data-stu-id="97e5f-366">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="97e5f-367">Dieses Attribut ist ein eindeutiger Bezeichner einer Gruppe, die zum Gruppieren von Adressbucheinträgen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="97e5f-367">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-368">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="97e5f-368">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-369">Attribut msRTCSIP-Homeserver (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-369">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="97e5f-370">Neu in Live Communications Server 2003 (nicht verwendet).</span><span class="sxs-lookup"><span data-stu-id="97e5f-370">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="97e5f-371">Veraltet in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-371">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-372">Attribut msRTCSIP-HomeServerString (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-372">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="97e5f-373">Neu in Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="97e5f-373">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="97e5f-374">Veraltet in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-374">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-375">Attribut msRTCSIP-Heimuser (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-375">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="97e5f-376">Neu in Live Communications Server 2003 (nicht verwendet).</span><span class="sxs-lookup"><span data-stu-id="97e5f-376">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="97e5f-377">Veraltet in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-377">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-378">Attribut msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="97e5f-378">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="97e5f-379">Dieses Attribut steuert, ob ein einzelner Benutzer für den Zugriff durch externe Benutzer aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="97e5f-379">This attribute controls whether a single user is enabled for outside user access.</span></span> <span data-ttu-id="97e5f-380">Sie wird von der Enterprise Services-Schicht erzwungen.</span><span class="sxs-lookup"><span data-stu-id="97e5f-380">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="97e5f-381">Sie ist für die Replikation des globalen Katalogs markiert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-381">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="97e5f-382">Die gültigen Werte sind " <strong>wahr</strong> " oder " <strong>falsch</strong>".</span><span class="sxs-lookup"><span data-stu-id="97e5f-382">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-383">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-383">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-384">Attribut msRTCSIP-IsMaster (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-384">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="97e5f-385">Neu in Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="97e5f-385">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="97e5f-386">Veraltet in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-386">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-387">Attribut msRTCSIP-Zeile</span><span class="sxs-lookup"><span data-stu-id="97e5f-387">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="97e5f-388">Dieses Attribut mit einem Wert enthält die Geräte-ID (entweder den SIP-URI oder den Tel-URI des Telefons, den der Benutzer steuert), der von lync für die Telefonie verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="97e5f-388">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="97e5f-389">Dieses Attribut ist für die Replikation des globalen Katalogs markiert und indiziert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-389">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="97e5f-390">Wenn ein Benutzer für Enterprise-VoIP aktiviert ist, speichert dieses Attribut die normalisierte E. 164-Version der Telefonnummer des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="97e5f-390">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-391">Neu in Microsoft Office Live Communications Server 2005 mit SP1</span><span class="sxs-lookup"><span data-stu-id="97e5f-391">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-392">Attribut msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="97e5f-392">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="97e5f-393">Dieses Attribut mit einem Wert enthält den SIP-URI des CSTA-SIP-Gatewayservers.</span><span class="sxs-lookup"><span data-stu-id="97e5f-393">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server.</span></span> <span data-ttu-id="97e5f-394">Dieses Attribut ist für die Replikation des globalen Katalogs markiert, aber nicht indiziert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-394">This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-395">Neu in Microsoft Office Live Communications Server 2005 mit SP1</span><span class="sxs-lookup"><span data-stu-id="97e5f-395">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-396">Attribut msRTCSIP-LocalNormalizationData (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-396">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-397">Dieses Attribut ist für die spätere Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-397">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-398">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-398">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="97e5f-399">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-399">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-400">Attribut msRTCSIP-LocalNormalizationLinks (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-400">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-401">Dieses mehrwertige Attribut enthält eine Liste der lokalen normalisierungs Namen (Distinguished Names, DN), die diesem Standortprofil zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="97e5f-401">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile.</span></span> <span data-ttu-id="97e5f-402">Der Typ dieses Attributs ist eine DN-Binärdatei.</span><span class="sxs-lookup"><span data-stu-id="97e5f-402">The type of this attribute is a DN binary.</span></span> <span data-ttu-id="97e5f-403">Es gibt eine 1: n-Beziehung zwischen Standortprofil und lokalen Normalisierungsregeln.</span><span class="sxs-lookup"><span data-stu-id="97e5f-403">There is a one-to-many relationship between location profile and local normalization rules.</span></span> <span data-ttu-id="97e5f-404">Die Reihenfolge der Liste der DNS für die lokale Normalisierung muss in der vom Administrator angegebenen Reihenfolge verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="97e5f-404">The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator.</span></span> <span data-ttu-id="97e5f-405">Die Beibehaltung der Reihenfolge wird durch den binären Teil der DN-Binärdatei verwaltet, der den Reihenfolgeindex angibt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-405">The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="97e5f-406">Link weiterleiten: <strong>Link-ID 11034</strong></span><span class="sxs-lookup"><span data-stu-id="97e5f-406">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="97e5f-407">Der entsprechende Link zurück zu diesem Forward Link-Attribut lautet <strong>Attribut msRTCSIP-LocationProfileBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="97e5f-407">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-408">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-408">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="97e5f-409">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-409">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-410">Attribut msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="97e5f-410">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="97e5f-411">Dieses Attribut enthält eine Liste der Optionen für die Normalisierungsregel.</span><span class="sxs-lookup"><span data-stu-id="97e5f-411">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-412">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="97e5f-412">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-413">Attribut msRTCSIP-LocationName (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-413">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-414">Dieses Attribut mit einem Wert enthält einen Anzeigenamen für das Standortprofil, das angibt, an welcher Position dieses Profil steht.</span><span class="sxs-lookup"><span data-stu-id="97e5f-414">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents.</span></span> <span data-ttu-id="97e5f-415">Da es mehrere Standortprofile geben kann, benötigt der Administrator eine Möglichkeit, zwischen verschiedenen Profilen zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="97e5f-415">Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-416">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-416">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="97e5f-417">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-417">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-418">Attribut msRTCSIP-locationProfileBL (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-418">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-419">Dieses mehrwertige Attribut enthält eine Liste mit definierten Namen für Standortprofile.</span><span class="sxs-lookup"><span data-stu-id="97e5f-419">This multi-valued attribute contains a list of location profile distinguished names.</span></span> <span data-ttu-id="97e5f-420">Dieses Attribut gibt den zurück-Link zu einem oder mehreren Standortprofilen an.</span><span class="sxs-lookup"><span data-stu-id="97e5f-420">This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="97e5f-421">Link zurück: <strong>Link-ID 11035</strong></span><span class="sxs-lookup"><span data-stu-id="97e5f-421">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="97e5f-422">Dieses Attribut entspricht dem Forward-Link <strong>Attribut msRTCSIP-LocalNormalizationLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="97e5f-422">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-423">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-423">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="97e5f-424">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-424">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-425">Attribut msRTCSIP-LocationProfileData (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-425">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-426">Dieses Attribut ist für die spätere Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-426">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-427">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-427">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="97e5f-428">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-428">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-429">Attribut msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="97e5f-429">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="97e5f-430">Dieses Attribut enthält die Optionen für das Standortprofil.</span><span class="sxs-lookup"><span data-stu-id="97e5f-430">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-431">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="97e5f-431">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-432">Attribut msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="97e5f-432">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="97e5f-433">Dieses Attribut mit mehreren Werten enthält eine Liste von Anwendungs Kontakten.</span><span class="sxs-lookup"><span data-stu-id="97e5f-433">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-434">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="97e5f-434">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-435">Attribut msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="97e5f-435">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="97e5f-436">Dieses Attribut mit mehreren Werten enthält eine Liste von Standortprofilen.</span><span class="sxs-lookup"><span data-stu-id="97e5f-436">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-437">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="97e5f-437">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-438">Attribut msRTCSIP-MaxNumOutstandingSearchPerServer (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-439">Dieses Attribut stellt die maximale Anzahl ausstehender Suchanforderungen pro Server dar.</span><span class="sxs-lookup"><span data-stu-id="97e5f-439">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-440">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-440">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-441">Attribut msRTCSIP-MaxNumSubscriptionsPerUser (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-442">Das Attribut stellt die maximale Anzahl von Abonnements pro Benutzer dar.</span><span class="sxs-lookup"><span data-stu-id="97e5f-442">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-443">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-443">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-444">Attribut msRTCSIP-MaxPresenceSubscriptionTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-445">Dieses Attribut stellt das maximale Timeout Fenster für Abonnements dar.</span><span class="sxs-lookup"><span data-stu-id="97e5f-445">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-446">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-446">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-447">Attribut msRTCSIP-MaxRegistrationsTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-447">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-448">Dieses Attribut stellt das Timeout Fenster für maximale Registrierungen dar.</span><span class="sxs-lookup"><span data-stu-id="97e5f-448">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-449">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-449">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-450">Attribut msRTCSIP-MaxRoamingDataSubscriptionTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-451">Dieses Attribut steht für das maximale Timeout Fenster für Roaming-Daten Abonnements.</span><span class="sxs-lookup"><span data-stu-id="97e5f-451">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-452">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-452">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-453">Attribut msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="97e5f-453">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="97e5f-454">Dieses Attribut ist für die spätere Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-454">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-455">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-455">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-456">Attribut msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="97e5f-456">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="97e5f-457">Bei diesem Attribut handelt es sich um ein Dienst Kontrollpunkt-Attribut unter der Computerklasse, das einen Link zurück zur Factory-Einheit (Multipoint Control Unit, MCU) angibt, zu der er gehört.</span><span class="sxs-lookup"><span data-stu-id="97e5f-457">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs.</span></span> <span data-ttu-id="97e5f-458">Dieser Dienst Kontrollpunkt und das Attribut werden für jede Microsoft-MCU erstellt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-458">This service control point and attribute is created for every Microsoft MCU.</span></span> <span data-ttu-id="97e5f-459">Jede Microsoft-MCU muss den Back-End-Server des Pools finden, zu dem Sie gehört, um Einstellungen auf Poolebene abzurufen.</span><span class="sxs-lookup"><span data-stu-id="97e5f-459">Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="97e5f-460">Der Wert dieses Attributs ist der Distinguished Name (DN) der MCU-Factory.</span><span class="sxs-lookup"><span data-stu-id="97e5f-460">The value of this attribute is the distinguished name (DN) of the MCU Factory.</span></span> <span data-ttu-id="97e5f-461">Hierbei handelt es sich um ein Single-Value-Attribut, das für die Replikation des globalen Katalogs markiert ist.</span><span class="sxs-lookup"><span data-stu-id="97e5f-461">This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="97e5f-462">Link weiterleiten: <strong>Link-ID 11026</strong></span><span class="sxs-lookup"><span data-stu-id="97e5f-462">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="97e5f-463">Der entsprechende Link zurück zu diesem Forward Link-Attribut lautet <strong>Attribut msRTCSIP-MCUServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="97e5f-463">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-464">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-464">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-465">Attribut msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="97e5f-465">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="97e5f-466">Hierbei handelt es sich um ein reserviertes Attribut mit mehreren Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="97e5f-466">This is a multi-string reserved attribute.</span></span> <span data-ttu-id="97e5f-467">In diesem Attribut gespeicherte Einstellungen werden als Name = Wert-Paare dargestellt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-467">Settings stored in this attribute are represented as name=value pairs.</span></span> <span data-ttu-id="97e5f-468">Derzeit definierte Name = Wert-Paare:</span><span class="sxs-lookup"><span data-stu-id="97e5f-468">Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-469">FactoryURL = &lt;URL&gt;</span><span class="sxs-lookup"><span data-stu-id="97e5f-469">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="97e5f-470">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-470">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-471">Attribut msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="97e5f-471">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="97e5f-472">Hierbei handelt es sich um ein Single-Value-Attribut, das den Distinguished Name (DN) einer einzelnen MCU-Factory enthält, die einem Pool zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="97e5f-472">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="97e5f-473">Link weiterleiten: <strong>Link-ID 11024</strong></span><span class="sxs-lookup"><span data-stu-id="97e5f-473">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="97e5f-474">Der entsprechende Link zurück zu diesem Forward Link-Attribut lautet <strong>Attribut msRTCSIP-PoolAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="97e5f-474">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-475">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-475">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-476">Attribut msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="97e5f-476">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="97e5f-477">Dieses Attribut ist eine Single-Wert-Zeichenfolge, die die GUID des MCU-Factory-Anbieters angibt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-477">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="97e5f-478">Basierend auf dem GUID-Wert bestimmt der MCU Factory-Prozess, ob dieser MCU-Typ gewartet werden soll.</span><span class="sxs-lookup"><span data-stu-id="97e5f-478">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="97e5f-479">Wenn es sich bei dem GUID-Wert um <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>handelt, wird der MCU-factoryprozess (standardmäßig in lync Server verfügbar) verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-479">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="97e5f-480">Für einen beliebigen anderen GUID-Wert wird der MCU-factoryprozess nicht von dem MCU-Typ gewartet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-480">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-481">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-481">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-482">Attribut msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="97e5f-482">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="97e5f-483">Dieses Attribut ist eine mehrwertige Liste mit Distinguished Names (DN).</span><span class="sxs-lookup"><span data-stu-id="97e5f-483">This attribute is a multi-valued list of distinguished names (DN).</span></span> <span data-ttu-id="97e5f-484">Dieses Attribut enthält eine Liste aller MCU-Server desselben Typs und Lieferanten, die dieser MCU-Factory zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="97e5f-484">This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory.</span></span> <span data-ttu-id="97e5f-485">Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN ist 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="97e5f-485">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="97e5f-486">Link zurück: Link-ID 11027</span><span class="sxs-lookup"><span data-stu-id="97e5f-486">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="97e5f-487">Der entsprechende Weiterleitungslink zu diesem zurück <strong>-Link lautet Attribut msRTCSIP-MCUFactoryAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="97e5f-487">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-488">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-488">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-489">Attribut msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="97e5f-489">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="97e5f-490">Dieses Attribut ist eine einwertige Zeichenfolge, die das Medium angibt, das die MCU verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="97e5f-490">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="97e5f-491">Unterstützte gültige Typen:</span><span class="sxs-lookup"><span data-stu-id="97e5f-491">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-492">Besprechung</span><span class="sxs-lookup"><span data-stu-id="97e5f-492">meeting</span></span></p></li>
<li><p><span data-ttu-id="97e5f-493">Audio-Video</span><span class="sxs-lookup"><span data-stu-id="97e5f-493">audio-video</span></span></p></li>
<li><p><span data-ttu-id="97e5f-494">Chat</span><span class="sxs-lookup"><span data-stu-id="97e5f-494">chat</span></span></p></li>
<li><p><span data-ttu-id="97e5f-495">Telefon-conf</span><span class="sxs-lookup"><span data-stu-id="97e5f-495">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="97e5f-496">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-496">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-497">Attribut msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="97e5f-497">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="97e5f-498">Dieses Attribut ist eine Single-Wert-Zeichenfolge, die den Namen eines MCU-Anbieters angibt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-498">This attribute is a single-valued string that specifies an MCU vendor’s name.</span></span> <span data-ttu-id="97e5f-499">Dieses Attribut wird von allen Microsoft-MCU als <strong>Microsoft Corporation</strong>angegeben.</span><span class="sxs-lookup"><span data-stu-id="97e5f-499">All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-500">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-500">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-501">Attribut msRTCSIP-MeetingFlags (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-501">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-502">Dieses Attribut definiert verschiedene Besprechungsoptionen, die für alle Benutzer oder Kontaktobjekte global aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="97e5f-502">This attribute defines different meeting options that are enabled globally for all users or contact objects.</span></span> <span data-ttu-id="97e5f-503">Dieses Attribut ist ein Bitmaskenwert vom Typ "ganze Zahl".</span><span class="sxs-lookup"><span data-stu-id="97e5f-503">This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="97e5f-504">Die gültigen Werte (und zugeordnete Bit-Positionen) lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="97e5f-504">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-505">0: AllowOrganizeMeetingWithAnonymousParticipants lautet ist keine (Benutzer dürfen keine anonymen Benutzer zu Besprechungen einladen) (kein Bits-Satz)</span><span class="sxs-lookup"><span data-stu-id="97e5f-505">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-506">4: AllowOrganizeMeetingWithAnonymousParticipants lautet ist jeder (allen Benutzern gestatten, anonyme Benutzer zu Besprechungen einzuladen) (Bit-Position 2)</span><span class="sxs-lookup"><span data-stu-id="97e5f-506">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-507">8: AllowOrganizeMeetingWithAnonymousParticipants lautet ist UsePerUserSetting (Benutzern gestatten, anonyme Benutzer zu Besprechungen basierend auf der Einstellung pro Benutzer einzuladen) (Bit-Position 3)</span><span class="sxs-lookup"><span data-stu-id="97e5f-507">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-508">16: UserPerUserMeetingPolicy (die Besprechungsrichtlinie wird pro Benutzerdefiniert) (Bit-Position 4)</span><span class="sxs-lookup"><span data-stu-id="97e5f-508">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="97e5f-509">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-509">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="97e5f-510">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-510">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-511">Attribut msRTCSIP-MeetingPolicy (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-511">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-512">Dieses Attribut gibt den Distinguished Name (DN) der Richtlinie an, die der Administrator für diesen Benutzer als Single-Wert-Attribut zugewiesen hat.</span><span class="sxs-lookup"><span data-stu-id="97e5f-512">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-513">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-513">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="97e5f-514">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-514">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-515">Attribut msRTCSIP-MinPresenceSubscriptionTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-516">Dieses Attribut steht für das minimale Timeout Fenster für Anwesenheitsabonnements.</span><span class="sxs-lookup"><span data-stu-id="97e5f-516">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-517">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-517">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-518">Attribut msRTCSIP-MinRegistrationTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-518">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-519">Dieses Attribut steht für das minimale Registrierungstimeout Fenster.</span><span class="sxs-lookup"><span data-stu-id="97e5f-519">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-520">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-520">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="97e5f-521">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-521">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-522">Attribut msRTCSIP-MinRoamingDataSubscriptionTimeout (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-523">Dieses Attribut stellt das minimale Timeout Fenster für Roaming-Daten Abonnements dar.</span><span class="sxs-lookup"><span data-stu-id="97e5f-523">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-524">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-524">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="97e5f-525">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-525">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-526">Attribut msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="97e5f-526">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="97e5f-527">Dieses Attribut wird zum Speichern des vom Front-End-Pool verwendeten gespiegelten SQL Server-Back-Ends verwendet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-527">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-528">Neu in lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="97e5f-528">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-529">Attribut msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="97e5f-529">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="97e5f-530">Dieses Attribut enthält Optionen und Flags, mit denen Mobilitätseinstellungen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="97e5f-530">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-531">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="97e5f-531">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-532">Attribut msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="97e5f-532">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="97e5f-533">Dieses Attribut enthält den DN für ein mobilitätsrichtlinien Objekt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-533">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-534">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="97e5f-534">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-535">Attribut msRTCSIP-NumDevicesPerUser (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-535">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-536">Dieses Attribut stellt die zulässige Anzahl von Geräten dar, auf denen ein Benutzer für die SIP-Kommunikation registrieren und den Anwesenheitsstatus abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="97e5f-536">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-537">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-537">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="97e5f-538">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-538">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-539">Attribut msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="97e5f-539">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="97e5f-540">Dieses Attribut gibt die Optionen an, die für den Benutzer oder das Kontaktobjekt aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="97e5f-540">This attribute specifies the options that are enabled for the user or contact object.</span></span> <span data-ttu-id="97e5f-541">Dieses Attribut ist ein Bitmaskenwert vom Typ Integer.</span><span class="sxs-lookup"><span data-stu-id="97e5f-541">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="97e5f-542">Jede Option wird durch ein Bit dargestellt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-542">Each option is represented by a bit.</span></span> <span data-ttu-id="97e5f-543">Dieses Attribut ist für die Replikation des globalen Katalogs markiert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-543">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="97e5f-544">Die gültigen Werte (und zugeordnete Bit-Positionen) lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="97e5f-544">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-545">1: für öffentliche Instant Messaging (im)-Konnektivität (Bit-Position 0) aktiviert</span><span class="sxs-lookup"><span data-stu-id="97e5f-545">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-546">2: reserviert (Bit-Position 1)</span><span class="sxs-lookup"><span data-stu-id="97e5f-546">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-547">4: reserviert (Bit-Position 2)</span><span class="sxs-lookup"><span data-stu-id="97e5f-547">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-548">8: reserviert (Bit-Position 3)</span><span class="sxs-lookup"><span data-stu-id="97e5f-548">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-549">16: Remote-Anrufsteuerung aktiviert [Telefonie] (Bit-Position 4)</span><span class="sxs-lookup"><span data-stu-id="97e5f-549">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-550">64: AllowOrganizeMeetingWithAnonymousParticipants lautet (Benutzern gestatten, anonyme Benutzer zu Besprechungen einzuladen (Bit-Position 6)</span><span class="sxs-lookup"><span data-stu-id="97e5f-550">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-551">128: UCEnabled (Aktivieren von Benutzern für UC) (Bit-Position 7)</span><span class="sxs-lookup"><span data-stu-id="97e5f-551">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-552">256: EnabledForEnhancedPresence (Aktivieren des Benutzers für öffentliche Chat Verbindungen) (Bit-Position 8)</span><span class="sxs-lookup"><span data-stu-id="97e5f-552">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-553">512: RemoteCallControlDualMode (Bit-Position 9)</span><span class="sxs-lookup"><span data-stu-id="97e5f-553">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="97e5f-554">Neu in Live Communications Server 2005 mit SP1.</span><span class="sxs-lookup"><span data-stu-id="97e5f-554">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-555">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="97e5f-555">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="97e5f-556">Dieses Attribut wird in Ressourcen-und zentralen Gesamtstruktur Topologien verwendet, um die einmalige Anmeldung zu aktivieren, wenn die Objekt-Nr des Benutzers aus dem Windows NT Server-Prinzipal Konto in dieses Attribut des entsprechenden Benutzers oder Kontaktobjekts in der Ressource oder der zentralen Gesamtstruktur kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="97e5f-556">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="97e5f-557">Communicator Web Access sucht nach einem Benutzer in AD DS mithilfe dieses Attributs oder der Objekt-Nr des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="97e5f-557">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="97e5f-558">Dieses Attribut ist für die Replikation des globalen Katalogs markiert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-558">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-559">Attribut msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="97e5f-559">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="97e5f-560">Dieses Attribut ist der Uniform Resource Name (URN) des Besitzers für einen Anwendungs Kontakt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-560">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-561">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="97e5f-561">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-562">Attribut msRTCSIP-Muster (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-562">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-563">Dieses Attribut mit einer Wert Zeichenfolge enthält ein Muster, das für die Übereinstimmung von Wähl Nummern im E. 164-Format verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="97e5f-563">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format.</span></span> <span data-ttu-id="97e5f-564">Wenn die Wählnummer mit diesem Muster übereinstimmt, wird die Übersetzung auf die gewählte Nummer angewendet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-564">If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-565">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-565">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="97e5f-566">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-566">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-567">Attribut msRTCSIP-PhoneRouteBL (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-567">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-568">Dieses mehrwertige Attribut enthält eine Liste von Distinguished Names (DN) für die Telefonroute.</span><span class="sxs-lookup"><span data-stu-id="97e5f-568">This multi-valued attribute contains a list of phone route distinguished names (DN).</span></span> <span data-ttu-id="97e5f-569">Dieses Attribut gibt den zurück-Link zu einer oder mehreren Telefonrouten an.</span><span class="sxs-lookup"><span data-stu-id="97e5f-569">This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="97e5f-570">Link zurück: <strong>Link-ID 11033</strong></span><span class="sxs-lookup"><span data-stu-id="97e5f-570">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="97e5f-571">Dieses Attribut entspricht dem Forward-Link <strong>Attribut msRTCSIP-RouteUsageLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="97e5f-571">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-572">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-572">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="97e5f-573">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-573">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-574">Attribut msRTCSIP-PhoneRouteData (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-574">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-575">Dieses Attribut ist für die spätere Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-575">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-576">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-576">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-577">Attribut msRTCSIP-PhoneRouteName (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-577">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-578">Dieses Single-Value-UNICODE-Zeichenfolgenattribut gibt den Anzeigenamen der Telefonroute an, sodass vom Administrator einfach darauf verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="97e5f-578">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-579">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-579">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-580">Attribut msRTCSIP-PhoneUsageData (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-580">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-581">Dieses Attribut ist für die spätere Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-581">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-582">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-582">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="97e5f-583">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-583">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-584">Attribut msRTCSIP-PolicyContent (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-584">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-585">Dieses Attribut ist eine Unicode-Zeichenfolge mit einem Wert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-585">This attribute is a single-valued Unicode string.</span></span> <span data-ttu-id="97e5f-586">Dieses Zeichenfolgenattribut enthält die Richtliniendefinition im XML-Format.</span><span class="sxs-lookup"><span data-stu-id="97e5f-586">This string attribute contains the policy definition in XML format.</span></span> <span data-ttu-id="97e5f-587">Die XML-Schema Definition ist in verschiedenen Richtlinientypen üblich, nur die Einstellungen unterscheiden sich für jeden Richtlinientyp.</span><span class="sxs-lookup"><span data-stu-id="97e5f-587">The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="97e5f-588">Die XML-Schema Definition (XSD) ist wie folgt definiert:</span><span class="sxs-lookup"><span data-stu-id="97e5f-588">The XML schema definition (XSD) is defined as follows:</span></span></p>
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
<td><p><span data-ttu-id="97e5f-589">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-589">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="97e5f-590">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-590">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-591">Attribut msRTCSIP-Spalte PolicyData (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-591">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-592">Dieses Attribut ist für die spätere Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-592">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-593">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-593">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="97e5f-594">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-594">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-595">Attribut msRTCSIP-policyType (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-595">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-596">Dieses Single-Value-UNICODE-Zeichenfolgenattribut enthält den Richtlinientyp.</span><span class="sxs-lookup"><span data-stu-id="97e5f-596">This single-valued Unicode string attribute contains the policy type.</span></span> <span data-ttu-id="97e5f-597">Gültige Richtlinientypen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="97e5f-597">Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-598">Besprechung</span><span class="sxs-lookup"><span data-stu-id="97e5f-598">meeting</span></span></p></li>
<li><p><span data-ttu-id="97e5f-599">Telefonie</span><span class="sxs-lookup"><span data-stu-id="97e5f-599">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="97e5f-600">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-600">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="97e5f-601">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-601">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-602">Attribut msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="97e5f-602">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="97e5f-603">Dieses Attribut gibt einen Link zurück zu dem Pool, zu dem ein Computer gehört.</span><span class="sxs-lookup"><span data-stu-id="97e5f-603">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="97e5f-604">Dieses Attribut wird unabhängig davon festgesetzt, ob auf dem Computer die Standard Edition oder die Enterprise-Edition von lync Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="97e5f-604">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="97e5f-605">Dieses Attribut ist für die Replikation des globalen Katalogs markiert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-605">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="97e5f-606">Der gültige Wert ist der Domänenname des Pools.</span><span class="sxs-lookup"><span data-stu-id="97e5f-606">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="97e5f-607">Link weiterleiten: <strong>Link-ID 11022</strong></span><span class="sxs-lookup"><span data-stu-id="97e5f-607">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="97e5f-608">Der entsprechende Link zurück zu diesem Forward Link-Attribut lautet <strong>Attribut msRTCSIP-FrontEndServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="97e5f-608">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-609">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-609">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-610">Attribut msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="97e5f-610">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="97e5f-611">Hierbei handelt es sich um ein mehrwertiges Attribut, das eine Liste der Distinguished Names (DN) der Pools enthält, denen die MCU-Factory zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="97e5f-611">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="97e5f-612">Link zurück: <strong>Link-ID 11025</strong></span><span class="sxs-lookup"><span data-stu-id="97e5f-612">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="97e5f-613">Der entsprechende Weiterleitungslink zu diesem zurück <strong>-Link lautet Attribut msRTCSIP-MCUFactoryPath</strong>.</span><span class="sxs-lookup"><span data-stu-id="97e5f-613">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-614">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-614">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-615">Attribut msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="97e5f-615">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="97e5f-616">Dieses Attribut ist für die spätere Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-616">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-617">Neu in Live Communications Server 2005 mit SP1.</span><span class="sxs-lookup"><span data-stu-id="97e5f-617">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-618">Attribut msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="97e5f-618">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="97e5f-619">Dieses Attribut gibt einen beliebigen Namen für einen Pool an, der von der Verwaltungskonsole angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="97e5f-619">This attribute specifies an arbitrary name for a pool that is displayed by the management console.</span></span> <span data-ttu-id="97e5f-620">Dieser Name kann vom Administrator geändert werden.</span><span class="sxs-lookup"><span data-stu-id="97e5f-620">This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="97e5f-621">Der gültige Wert ist eine Zeichenfolge, die den Namen eines Pools darstellt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-621">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-622">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-622">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-623">Attribut msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="97e5f-623">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="97e5f-624">Dieses Attribut ist ein einwertiger Zeichenfolgenwert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-624">This attribute is a single-valued string value.</span></span> <span data-ttu-id="97e5f-625">Der Wert dieses Attributs steht, sofern vorhanden, für den Domänen-FQDN des Pools, wenn der Administrator einen Front-End-Pool mit einem FQDN erstellen möchte, der nicht der Active Directory-Domänenstruktur entspricht, in der der Front-End-Pool erstellt wird (beispielsweise ein SIP der Namespace wurde vom DNS-Namespace (Domain Name System) nicht mehr verwendet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-625">The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="97e5f-626">Wir empfehlen, dass Sie den Domänen-FQDN des Front-End-Pools dem Domänennamen Teil als die Active Directory-Domäne zuordnen, in der sich der Pool befindet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-626">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides.</span></span> <span data-ttu-id="97e5f-627">Wenn in diesem Attribut kein Wert vorhanden ist, wird der FQDN des Front-End-Pools standardmäßig auf die Active Directory-Domänennamenstruktur zurückgeführt, die durch das <strong>dNSHostName</strong> -Attribut gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="97e5f-627">Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-628">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-628">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-629">Attribut msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="97e5f-629">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="97e5f-630">Eine mehrwertige Liste der Domänennamen aller lync Server-Enterprise Edition-Server, die einem Pool zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="97e5f-630">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="97e5f-631">Dieses Attribut des Typs Integer definiert, ob der Pool Instant Messaging (im) und Anwesenheitsfunktionen und Besprechungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-631">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="97e5f-632">Die möglichen gültigen Wertetypen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="97e5f-632">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-633">Undefined: Chat-und Anwesenheitsdienst (Live Communications Server 2005 und 2003)</span><span class="sxs-lookup"><span data-stu-id="97e5f-633">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-634">1: Chat und Anwesenheitsdienst (lync Server)</span><span class="sxs-lookup"><span data-stu-id="97e5f-634">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-635">2: Chat und Anwesenheits-und Besprechungs Dienst (lync Server)</span><span class="sxs-lookup"><span data-stu-id="97e5f-635">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="97e5f-636">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-636">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-637">Attribut msRTCSIP-pooltype</span><span class="sxs-lookup"><span data-stu-id="97e5f-637">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="97e5f-638">Dieses Attribut gibt an, ob ein Serverpool den Standard Edition-Server oder Enterprise Edition-Server ausführt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-638">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server.</span></span> <span data-ttu-id="97e5f-639">Dieses Attribut ist ein Bitmaskenwert vom Typ Integer.</span><span class="sxs-lookup"><span data-stu-id="97e5f-639">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="97e5f-640">Jede Option wird durch ein Bit dargestellt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-640">Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="97e5f-641">Die gültigen Werte (und zugeordnete Bit-Positionen) lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="97e5f-641">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-642">1: Standard Edition-Server, hostet Benutzer (Bit-Position 0)</span><span class="sxs-lookup"><span data-stu-id="97e5f-642">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-643">2: Enterprise Edition-Server, hostet Benutzer (Bit-Position 1)</span><span class="sxs-lookup"><span data-stu-id="97e5f-643">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-644">4: Standard Edition-Server, Host-Anwendungen (Bit-Position 2)</span><span class="sxs-lookup"><span data-stu-id="97e5f-644">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-645">8: Enterprise Edition-Server, Host-Anwendungen (Bit-Position 3)</span><span class="sxs-lookup"><span data-stu-id="97e5f-645">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="97e5f-646">Da lync Server keine Pools unterstützt, die nur Anwendungen hosten, gelten die einzigen gültigen Werte wie folgt:</span><span class="sxs-lookup"><span data-stu-id="97e5f-646">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-647">5: Standard Edition-Server, hostet Benutzer und Anwendungen (Bit-Positionen 0 und 2)</span><span class="sxs-lookup"><span data-stu-id="97e5f-647">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-648">10: Enterprise Edition-Server, hostet Benutzer und Anwendungen (Bit-Positionen 1 und 3)</span><span class="sxs-lookup"><span data-stu-id="97e5f-648">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="97e5f-649">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-649">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-650">Attribut msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="97e5f-650">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="97e5f-651">Dieses Attribut definiert die Pool-Version.</span><span class="sxs-lookup"><span data-stu-id="97e5f-651">This attribute defines the pool version.</span></span> <span data-ttu-id="97e5f-652">Hierbei handelt es sich um einen ganzzahligen Typ, der mit jeder Hauptprodukt Version inkrementiert wird.</span><span class="sxs-lookup"><span data-stu-id="97e5f-652">It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="97e5f-653">Die möglichen gültigen Wertetypen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="97e5f-653">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-654">0: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="97e5f-654">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="97e5f-655">1: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="97e5f-655">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="97e5f-656">2: Live Communications Server 2005 mit SP1</span><span class="sxs-lookup"><span data-stu-id="97e5f-656">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="97e5f-657">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="97e5f-657">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="97e5f-658">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="97e5f-658">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="97e5f-659">5: lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="97e5f-659">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="97e5f-660">Live Communications Server 2005 mit SP1</span><span class="sxs-lookup"><span data-stu-id="97e5f-660">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-661">Attribut msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="97e5f-661">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="97e5f-662">Dieses Attribut enthält Optionen und Flags, mit denen Anwesenheitseinstellungen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="97e5f-662">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-663">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="97e5f-663">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-664">Attribut msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="97e5f-664">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="97e5f-665">Dieses Attribut enthält den DN für ein Anwesenheitsrichtlinienobjekt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-665">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-666">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="97e5f-666">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-667">Attribut msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="97e5f-667">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="97e5f-668">Dieses Attribut ermöglicht einem Benutzer oder Kontakt für SIP-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="97e5f-668">This attribute enables a user or contact for SIP messaging.</span></span> <span data-ttu-id="97e5f-669">Sie wird der Contact-Klasse hinzugefügt, da in der zentralen Gesamtstrukturtopologie die Kontaktobjekte, nicht die Benutzerobjekte, SIP-fähig sind.</span><span class="sxs-lookup"><span data-stu-id="97e5f-669">It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="97e5f-670">Der gültige Wert ist der DN des Standard Edition-Servers oder des Enterprise Edition-Front-End-Pools, in dem ein Benutzer beheimatet ist.</span><span class="sxs-lookup"><span data-stu-id="97e5f-670">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-671">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-671">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-672">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="97e5f-672">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="97e5f-673">Dieses Attribut enthält die SIP-Adresse eines angegebenen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="97e5f-673">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-674">Attribut msRTCSIP-Privatsphäre</span><span class="sxs-lookup"><span data-stu-id="97e5f-674">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="97e5f-675">Dieses Attribut enthält die Geräte-ID des privaten Leitungs Geräts.</span><span class="sxs-lookup"><span data-stu-id="97e5f-675">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-676">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="97e5f-676">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-677">Attribut msRTCSIP-routingfähig</span><span class="sxs-lookup"><span data-stu-id="97e5f-677">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="97e5f-678">Dieses Attribut ist ein boolesches Attribut, das verwendet wird, um zu ermitteln, ob lync Server zum Weiterleiten an diesen Dienst mit seiner GRUU-Adresse autorisiert ist.</span><span class="sxs-lookup"><span data-stu-id="97e5f-678">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="97e5f-679">Wenn dieser Wert auf " <strong>true</strong>" festgelegt ist, ist lync Server zum Weiterleiten an diesen Dienst autorisiert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-679">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="97e5f-680">Wenn dieser Wert auf " <strong>false</strong>" festgelegt ist, ist lync Server nicht zum Weiterleiten an diesen Dienst autorisiert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-680">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-681">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-681">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-682">Attribut msRTCSIP-RouteUsageAttribute (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-682">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-683">Dieses Single-Value-UNICODE-Zeichenfolgenattribut definiert ein Attribut, das die Verwendung für eine Telefonroute qualifiziert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-683">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route.</span></span> <span data-ttu-id="97e5f-684">Die Auswahl einer Telefonroute wird auf der Grundlage von zwei Elementen bestimmt: dem Nutzungs Attribut, das der Telefonroute zugewiesen ist, und den zulässigen Richtlinien Verwendungsattributen des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="97e5f-684">Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes.</span></span> <span data-ttu-id="97e5f-685">Die erste Telefonroute mit einem Nutzungs Attribut, das der zulässigen Verwendung des Anrufers entspricht, ist ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-685">The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-686">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-686">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="97e5f-687">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-687">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-688">Attribut msRTCSIP-RouteUsageLinks (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-688">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-689">Dieses Attribut für mehrwertigen Distinguished Name (DN) enthält eine Liste der definierten Namen für die Routenverwendung.</span><span class="sxs-lookup"><span data-stu-id="97e5f-689">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="97e5f-690">Link weiterleiten: <strong>Link-ID 11032</strong></span><span class="sxs-lookup"><span data-stu-id="97e5f-690">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="97e5f-691">Dieses Attribut ist ein Forward-Link zum entsprechenden Backlink <strong>Attribut msRTCSIP-PhoneRouteBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="97e5f-691">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-692">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-692">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-693">Attribut msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="97e5f-693">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="97e5f-694">Dieses Attribut enthält den DN, der auf den Pool verweist, der den gesamten SIP-Datenverkehr an diesen MCU oder vertrauenswürdigen Dienst durchlaufen muss.</span><span class="sxs-lookup"><span data-stu-id="97e5f-694">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-695">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="97e5f-695">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-696">Attribut msRTCSIP-RuleName (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-696">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-697">Dieses einmalige UNICODE-Zeichenfolgenattribut gibt den Anzeigenamen der Normalisierungsregel an, sodass von einem Administrator einfach darauf verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="97e5f-697">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-698">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-698">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="97e5f-699">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-699">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-700">Attribut msRTCSIP-Schemaversion</span><span class="sxs-lookup"><span data-stu-id="97e5f-700">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="97e5f-701">Dieses Attribut steht für die Schemaversion, die derzeit in der Organisation bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="97e5f-701">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-702">Attribut msRTCSIP-SearchMaxRequests (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-702">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-703">Dieses Attribut schränkt die Anzahl der Suchergebnisse ein, die von einer Verzeichnissuche zurückgegeben werden sollen, wenn ein Benutzer mit Communicator nach einem Kontakt sucht.</span><span class="sxs-lookup"><span data-stu-id="97e5f-703">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="97e5f-704">Mit diesem Attribut wird der vom Client bereitgestellte Wert überschrieben.</span><span class="sxs-lookup"><span data-stu-id="97e5f-704">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-705">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-705">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-706">Attribut msRTCSIP-SearchMaxResults (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-706">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-707">Dieses Attribut schränkt die Anzahl der zurückgegebenen Suchanforderungen ein.</span><span class="sxs-lookup"><span data-stu-id="97e5f-707">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-708">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-708">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-709">Attribut msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="97e5f-709">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="97e5f-710">Bei diesem mehrwertigen Attribut handelt es sich um einen Link zurück, der eine Liste von Distinguished Names (DN) enthält.</span><span class="sxs-lookup"><span data-stu-id="97e5f-710">This multi-valued attribute is a back link that contains a list of distinguished names (DN).</span></span> <span data-ttu-id="97e5f-711">Dieser DNS-Punkt verweist auf ein Pool-oder <strong>TrustedService</strong> -Objekt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-711">These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="97e5f-712">Dieses Attribut entspricht dem Forward-Link <strong>Attribut msRTCSIP-TrustedServiceLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="97e5f-712">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-713">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-713">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-714">Attribut msRTCSIP-Server</span><span class="sxs-lookup"><span data-stu-id="97e5f-714">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="97e5f-715">Dieses Attribut ist für die spätere Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-715">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-716">Attribut msRTCSIP-ServerReferenceBL (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-716">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-717">Dieses mehrwertige Attribut enthält eine Liste von Distinguished Names.</span><span class="sxs-lookup"><span data-stu-id="97e5f-717">This multi-valued attribute contains a list of distinguished names.</span></span> <span data-ttu-id="97e5f-718">Bei diesen definierten Namen handelt es sich um zurück-Links, die auf andere Serverobjekte verweisen, denen ein Standardstandortprofil zugewiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="97e5f-718">These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="97e5f-719">Link zurück: <strong>Link-ID 11037</strong></span><span class="sxs-lookup"><span data-stu-id="97e5f-719">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="97e5f-720">Der entsprechende Weiterleitungslink zu diesem zurück <strong>-Link lautet Attribut msRTCSIP-DefaultLocationProfileLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="97e5f-720">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="97e5f-721">Dieses zurück Link-Attribut verweist nur auf Pools und Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="97e5f-721">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-722">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-722">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="97e5f-723">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-723">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-724">Attribut msRTCSIP-Server Version vom</span><span class="sxs-lookup"><span data-stu-id="97e5f-724">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="97e5f-725">Dieses Attribut definiert die Versionsinformationen des Servers.</span><span class="sxs-lookup"><span data-stu-id="97e5f-725">This attribute defines the version information of the server.</span></span> <span data-ttu-id="97e5f-726">Diese Versionsnummer gilt für alle Serverrollen.</span><span class="sxs-lookup"><span data-stu-id="97e5f-726">This version number applies to all server roles.</span></span> <span data-ttu-id="97e5f-727">Hierbei handelt es sich um eine monoton-Ganzzahl, die mit jeder offiziellen Produktversion inkrementiert wird.</span><span class="sxs-lookup"><span data-stu-id="97e5f-727">It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="97e5f-728">Die möglichen gültigen Werte lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="97e5f-728">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-729">Undefined: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="97e5f-729">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="97e5f-730">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="97e5f-730">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="97e5f-731">                 Live Communications Server 2005 mit SP1</span><span class="sxs-lookup"><span data-stu-id="97e5f-731">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="97e5f-732">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="97e5f-732">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="97e5f-733">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="97e5f-733">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="97e5f-734">5: lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="97e5f-734">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="97e5f-735">6: lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97e5f-735">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="97e5f-736">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-736">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-737">Attribut msRTCSIP-Quellobjekttyp</span><span class="sxs-lookup"><span data-stu-id="97e5f-737">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="97e5f-738">Dieses Attribut mit einem Wert vom Typ "Ganzzahl" gibt den Typ des Objekts an, auf das <strong>msDS-SourceObjectDN</strong> zeigt, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="97e5f-738">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-739">NULL | 0x00000001: stellt ein Windows NT Server Principal-Benutzerobjekt aus einer anderen Gesamtstruktur dar.</span><span class="sxs-lookup"><span data-stu-id="97e5f-739">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="97e5f-740">Die folgenden Attribute stellen einen Gruppentyp aus einer anderen Gesamtstruktur für die Erweiterung der Verteilergruppe dar:</span><span class="sxs-lookup"><span data-stu-id="97e5f-740">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="97e5f-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="97e5f-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="97e5f-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="97e5f-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="97e5f-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="97e5f-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="97e5f-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="97e5f-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="97e5f-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="97e5f-746">0x90000000: stellt eine automatische Telefonzentrale oder ein Teilnehmerzugriffs Objekt aus derselben Gesamtstruktur oder einer anderen Gesamtstruktur dar.</span><span class="sxs-lookup"><span data-stu-id="97e5f-746">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="97e5f-747">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-747">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-748">Attribut msRTCSIP-SubscriptionAuthRequired (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-748">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="97e5f-749">Neu in Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="97e5f-749">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="97e5f-750">Veraltet in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-750">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-751">Attribut msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="97e5f-751">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="97e5f-752">Mit diesem Attribut können Sie einen Benutzer oder ein Kontaktobjekt aus einem lync Server-Pool in einen anderen verschieben.</span><span class="sxs-lookup"><span data-stu-id="97e5f-752">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="97e5f-753">Dieses Attribut wird der Contact-Klasse hinzugefügt, da in der zentralen Gesamtstrukturtopologie die Kontaktobjekte, nicht die Benutzerobjekte, SIP-fähig sind.</span><span class="sxs-lookup"><span data-stu-id="97e5f-753">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="97e5f-754">Der gültige Wert ist der DN des Ziel-Standard Edition-Servers oder-Front-End-Pools, in den ein Benutzer verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="97e5f-754">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-755">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-755">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-756">Attribut msRTCSIP-TargetPhoneNumber (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-756">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-757">Dieses Attribut mit einer Wert Zeichenfolge enthält ein Telefonnummernmuster oder einen Bereich, der an die in <strong>Attribut msRTCSIP-Gateways</strong>definierten Gateways weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="97e5f-757">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-758">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-758">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-759">Attribut msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="97e5f-759">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="97e5f-760">Dieses Attribut speichert Name-Wert-Paare für Zielrichtlinien für lync Server-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="97e5f-760">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-761">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="97e5f-761">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-762">Attribut msRTCSIP-Mandanten-Nr</span><span class="sxs-lookup"><span data-stu-id="97e5f-762">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="97e5f-763">Dieses Attribut speichert den eindeutigen Bezeichner für einen Mandanten.</span><span class="sxs-lookup"><span data-stu-id="97e5f-763">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-764">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="97e5f-764">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-765">Attribut msRTCSIP-Translation (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-765">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-766">Dieses Attribut wird von der Sprachfunktion von lync Server verwendet und enthält die Übersetzungs Zeichenfolge, die für die gewählte Nummer gelten soll, wenn eine Übereinstimmung gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="97e5f-766">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-767">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-767">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="97e5f-768">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-768">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-769">Attribut msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="97e5f-769">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="97e5f-770">Dieses Attribut ist für die spätere Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-770">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-771">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-771">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-772">Attribut msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="97e5f-772">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="97e5f-773">Dieses Attribut ist ein Zeichenfolgenwert, der den FQDN des MCU enthält.</span><span class="sxs-lookup"><span data-stu-id="97e5f-773">This attribute is a string value that contains the FQDN of the MCU.</span></span> <span data-ttu-id="97e5f-774">Hierbei handelt es sich um ein Single-Value-Attribut.</span><span class="sxs-lookup"><span data-stu-id="97e5f-774">This is a single-valued attribute.</span></span> <span data-ttu-id="97e5f-775">Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN ist 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="97e5f-775">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-776">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-776">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-777">Attribut msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="97e5f-777">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="97e5f-778">Dieses Attribut ist für die spätere Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-778">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-779">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-779">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-780">Attribut msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="97e5f-780">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="97e5f-781">Dieses Attribut ist ein Zeichenfolgenwert, der den FQDN des Servers enthält, auf dem Proxy Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="97e5f-781">This attribute is a string value that contains the FQDN of the server running Proxy Server.</span></span> <span data-ttu-id="97e5f-782">Dieses Attribut ist ein Single-Wert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-782">This attribute is single-valued.</span></span> <span data-ttu-id="97e5f-783">Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN ist 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="97e5f-783">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-784">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-784">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-785">Attribut msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="97e5f-785">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="97e5f-786">Dieses Attribut ist für die spätere Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-786">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-787">Attribut msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="97e5f-787">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="97e5f-788">Dieses Attribut ist ein Single-Value-Attribut, das den FQDN eines vertrauenswürdigen Servers darstellt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-788">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-789">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-789">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-790">Attribut msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="97e5f-790">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="97e5f-791">Dieses Attribut gibt die Versionsnummer eines Servers in der Liste der vertrauenswürdigen Server an.</span><span class="sxs-lookup"><span data-stu-id="97e5f-791">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="97e5f-792">Die möglichen gültigen Werte lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="97e5f-792">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-793">NULL: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="97e5f-793">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="97e5f-794">2: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="97e5f-794">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="97e5f-795">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="97e5f-795">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="97e5f-796">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="97e5f-796">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="97e5f-797">5: lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="97e5f-797">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="97e5f-798">6: lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97e5f-798">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="97e5f-799">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-799">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-800">Attribut msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="97e5f-800">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="97e5f-801">Dieses Attribut definiert die Optionen, die für den vertrauenswürdigen Dienst aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="97e5f-801">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-802">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="97e5f-802">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-803">Attribut msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="97e5f-803">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="97e5f-804">Dieses mehrwertige Attribut enthält eine Liste von Distinguished Names (DN), die auf ein vertrauenswürdiges Dienstobjekt verweisen, beispielsweise einen Media Relay-Authentifizierungsdienst.</span><span class="sxs-lookup"><span data-stu-id="97e5f-804">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="97e5f-805">Ein Media Relay-Authentifizierungsdienst (physisch auf dem Edgeserver mit dem A/V-Konferenzdienst) muss einem Pool zugeordnet sein, um audioszenarien für Remotebenutzer zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="97e5f-805">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="97e5f-806">Der entsprechende Link zurück zu diesem Forward Link-Attribut lautet <strong>Attribut msRTCSIP-ServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="97e5f-806">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-807">UC</span><span class="sxs-lookup"><span data-stu-id="97e5f-807">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-808">Attribut msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="97e5f-808">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="97e5f-809">Dieses Attribut ist eine ganze Zahl, die die Portnummer definiert, die zum Herstellen der Verbindung mit diesem GRUU-Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="97e5f-809">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-810">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-810">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-811">Attribut msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="97e5f-811">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="97e5f-812">Dieses Attribut ist ein Zeichenfolgenwert, der den Typ des GRUU-Diensts definiert, den er darstellt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-812">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="97e5f-813">Die gültigen GRUU-Diensttypen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="97e5f-813">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-814">„MediationServer“</span><span class="sxs-lookup"><span data-stu-id="97e5f-814">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="97e5f-815">Gateway</span><span class="sxs-lookup"><span data-stu-id="97e5f-815">Gateway</span></span></p></li>
<li><p><span data-ttu-id="97e5f-816">Media Relay-Authentifizierungsdienst (MRAS)</span><span class="sxs-lookup"><span data-stu-id="97e5f-816">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="97e5f-817">QoSM</span><span class="sxs-lookup"><span data-stu-id="97e5f-817">QoSM</span></span></p></li>
<li><p><span data-ttu-id="97e5f-818">Attribut msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="97e5f-818">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="97e5f-819">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-819">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-820">Attribut msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="97e5f-820">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="97e5f-821">Dieses Attribut ist für die spätere Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-821">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-822">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-822">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-823">Attribut msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="97e5f-823">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="97e5f-824">Dieses Attribut ist ein Zeichenfolgenwert, der den FQDN des IIS mit lync Server-Webdiensten enthält.</span><span class="sxs-lookup"><span data-stu-id="97e5f-824">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="97e5f-825">Hierbei handelt es sich um ein Single-Value-Attribut.</span><span class="sxs-lookup"><span data-stu-id="97e5f-825">This is a single-valued attribute.</span></span> <span data-ttu-id="97e5f-826">Der gültige Wert für jedes Segment ist 63 Zeichen; der gültige Wert für den gesamten FQDN ist 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="97e5f-826">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-827">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-827">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-828">Attribut msRTCSIP-UCFlags (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-828">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-829">Dieses Attribut definiert verschiedene UC-Optionen, die für alle Benutzer-oder Kontaktobjekte global aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="97e5f-829">This attribute defines different UC options that are enabled globally to all user or contact objects.</span></span> <span data-ttu-id="97e5f-830">Dieses Attribut ist ein Bitmaskenwert vom Typ "ganze Zahl".</span><span class="sxs-lookup"><span data-stu-id="97e5f-830">This attribute is a bit-mask value of integer type.</span></span> <span data-ttu-id="97e5f-831">Jede Option wird durch das vorhanden sein eines Bits dargestellt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-831">Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="97e5f-832">Der mögliche gültige Wert (und die zugehörige Bit-Position) lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="97e5f-832">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-833">4: UsePerUserUCPolicy (Bit-Position 2)</span><span class="sxs-lookup"><span data-stu-id="97e5f-833">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="97e5f-834">Wenn dieses Bit festgelegt ist, wird die UC-Richtlinie pro Benutzerdefiniert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-834">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-835">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-835">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-836">Attribut msRTCSIP-UCPolicy (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-836">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-837">Dieses Attribut mit einem Wert enthält den Distinguished Name (DN) der UC-Richtlinie, die der Administrator für diesen Benutzer zugewiesen hat.</span><span class="sxs-lookup"><span data-stu-id="97e5f-837">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-838">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-838">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-839">Attribut msRTCSIP-UserDomainList (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-839">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="97e5f-840">Dieses Attribut enthält eine Liste aller Domänen in einer Gesamtstruktur, die SIP-fähige Benutzer hosten.</span><span class="sxs-lookup"><span data-stu-id="97e5f-840">This attribute provides a list of all the domains in a forest that host SIP-enabled users.</span></span> <span data-ttu-id="97e5f-841">Der Standardwert ist eine leere Liste, die angibt, dass alle Domänen in der Gesamtstruktur SIP-fähig sind.</span><span class="sxs-lookup"><span data-stu-id="97e5f-841">The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="97e5f-842">Gültige Werte sind mehrere Zeichenfolgen, die die Domänennamen einzelner Domänen darstellen.</span><span class="sxs-lookup"><span data-stu-id="97e5f-842">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-843">Neu in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-843">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="97e5f-844">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="97e5f-844">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-845">Attribut msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="97e5f-845">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="97e5f-846">Dieses Attribut bestimmt, ob der Benutzer derzeit für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="97e5f-846">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-847">Attribut msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="97e5f-847">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="97e5f-848">Dieses mehrwertige Attribut enthält eine Liste von Name-Wert-Paaren im Format &quot;von Name = Wert. &quot; Dieses Attribut ist für die Replikation des globalen Katalogs markiert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-848">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-849">Neu in Live Communications Server 2005 mit SP1.</span><span class="sxs-lookup"><span data-stu-id="97e5f-849">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-850">Attribut msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="97e5f-850">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="97e5f-851">Dieses Attribut enthält den Distinguished Name (DN), der auf ein Standortprofilobjekt verweist.</span><span class="sxs-lookup"><span data-stu-id="97e5f-851">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-852">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="97e5f-852">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-853">Attribut msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="97e5f-853">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="97e5f-854">Dieses Attribut speichert Name-Wert-Paare für Benutzerrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="97e5f-854">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-855">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="97e5f-855">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-856">Attribut msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="97e5f-856">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="97e5f-857">Hierbei handelt es sich um ein mehrwertiges Attribut, das eine Liste von definierten Namen mit binären (DN_WITH_BINARY) enthält, die auf globale Benutzerrichtlinien unterschiedlicher Typen verweisen.</span><span class="sxs-lookup"><span data-stu-id="97e5f-857">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types.</span></span> <span data-ttu-id="97e5f-858">Der binäre Teil gibt den Typ der Richtlinie an, auf die der DN-Anteil verweist.</span><span class="sxs-lookup"><span data-stu-id="97e5f-858">The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="97e5f-859">Die gültigen binären Werte lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="97e5f-859">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-860">0x00000001: Besprechungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="97e5f-860">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="97e5f-861">0x00000002: UC-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="97e5f-861">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="97e5f-862">0x00000005: Anwesenheitsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="97e5f-862">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="97e5f-863">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-863">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-864">Attribut msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="97e5f-864">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="97e5f-865">Hierbei handelt es sich um die SIP-Routinggruppen-ID.</span><span class="sxs-lookup"><span data-stu-id="97e5f-865">This is the SIP routing group ID.</span></span> <span data-ttu-id="97e5f-866">Benutzer in der gleichen Gruppe werden für denselben Front-End-Server registriert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-866">Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-867">Neu in lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="97e5f-867">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-868">Attribut msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="97e5f-868">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="97e5f-869">Hierbei handelt es sich um ein mehrwertiges Attribut.</span><span class="sxs-lookup"><span data-stu-id="97e5f-869">This is a multi-valued attribute.</span></span> <span data-ttu-id="97e5f-870">Dieses Attribut ist für die spätere Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-870">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-871">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-871">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-872">Attribut msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="97e5f-872">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="97e5f-873">Dieses Attribut mit einem Wert verweist auf den Pool oder den Standard Edition-Server, zu dem die Webkomponenten gehören.</span><span class="sxs-lookup"><span data-stu-id="97e5f-873">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="97e5f-874">Link weiterleiten: <strong>Link-ID 11028</strong></span><span class="sxs-lookup"><span data-stu-id="97e5f-874">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="97e5f-875">Der entsprechende Link zurück zu diesem Forward Link-Attribut lautet <strong>Attribut msRTCSIP-WebComponentsServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="97e5f-875">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-876">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-876">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-877">Attribut msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="97e5f-877">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="97e5f-878">Dieses Attribut ist eine mehrwertige Liste mit definierten Namen.</span><span class="sxs-lookup"><span data-stu-id="97e5f-878">This attribute is a multi-valued list of distinguished names.</span></span> <span data-ttu-id="97e5f-879">Dieses Attribut enthält eine Liste aller Webserver, die diesem Pool zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="97e5f-879">This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="97e5f-880">Link zurück: <strong>Link-ID 11029</strong></span><span class="sxs-lookup"><span data-stu-id="97e5f-880">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="97e5f-881">Der entsprechende Weiterleitungslink zu diesem zurück <strong>-Link lautet Attribut msRTCSIP-WebComponentsPoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="97e5f-881">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-882">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="97e5f-882">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-883">Attribut msRTCSIP-WMIInstanceId (veraltet)</span><span class="sxs-lookup"><span data-stu-id="97e5f-883">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="97e5f-884">Neu in Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="97e5f-884">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="97e5f-885">Veraltet in Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="97e5f-885">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-886">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="97e5f-886">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="97e5f-887">Dieses vorhandene Active Directory-Attribut wird von der Telefonie verwendet, um die Liste der alternativen TCP/IP-Adressen für ein Telefon festzulegen.</span><span class="sxs-lookup"><span data-stu-id="97e5f-887">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-888">Neu im Windows Server 2008-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="97e5f-888">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-889">PhoneOfficeOther</span><span class="sxs-lookup"><span data-stu-id="97e5f-889">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="97e5f-890">Dieses vorhandene Active Directory-Attribut wird von den VoIP-Komponenten in lync Server für nur-Kontaktobjekte verwendet, um Anrufe an die automatische Telefonzentrale und die Teilnehmerzugriffsnummern von Unified Messaging weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="97e5f-890">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="97e5f-891">Die bedingungslose Anruf Weiterleitungsadresse wird in diesem mehrwertigen Attribut gespeichert.</span><span class="sxs-lookup"><span data-stu-id="97e5f-891">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="97e5f-892">Dieses Konto wird für den spezifischen Zweck der automatischen Telefonzentrale und des Abonnenten Zugriffs erstellt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-892">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="97e5f-893">Die Attribute dieses Kontos sollten nicht von Administratoren geändert werden.</span><span class="sxs-lookup"><span data-stu-id="97e5f-893">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-894">Neu im Windows 2000-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="97e5f-894">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e5f-895">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="97e5f-895">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="97e5f-896">Dieses vorhandene Active Directory-mehrwertige Attribut ist Teil des Active Directory-Basisschemas, das in Windows 2000 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="97e5f-896">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="97e5f-897">Dieses Attribut enthält die verschiedenen X400-, x500-und SMTP-Adressen der e-Mail-Adresse des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="97e5f-897">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="97e5f-898">In Live Communications Server 2003 und höher wird der SIP-URI des Benutzers mithilfe des &quot;SIP:&quot; -Tags zu dieser Liste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="97e5f-898">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="97e5f-899">Die folgenden Anwendungen durchsuchen den SIP-URI des Benutzers anhand dieses Attributs:</span><span class="sxs-lookup"><span data-stu-id="97e5f-899">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="97e5f-900">Microsoft Office Outlook 2003-Messaging-und Zusammenarbeitsclient</span><span class="sxs-lookup"><span data-stu-id="97e5f-900">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="97e5f-901">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="97e5f-901">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="97e5f-902">Neu im Windows 2000-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="97e5f-902">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e5f-903">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="97e5f-903">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="97e5f-904">Dieses vorhandene Active Directory-Attribut enthält die Telefonnummer für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="97e5f-904">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="97e5f-905">Neu im Windows 2000-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="97e5f-905">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

