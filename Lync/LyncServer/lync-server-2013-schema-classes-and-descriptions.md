---
title: 'Lync Server 2013: Schema Klassen und-Beschreibungen'
description: 'Lync Server 2013: Schema Klassen und-Beschreibungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema classes and descriptions
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48184612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec27c2e00a7f969dbc13c91b06313c8045894a9e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557101"
---
# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="6e7b1-103">Schema Klassen und Beschreibungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e7b1-103">Schema classes and descriptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e7b1-104">_**Letztes Änderungsstand des Themas:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="6e7b1-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="6e7b1-105">In diesem Abschnitt werden alle Schemaklassen beschrieben, die von lync Server 2013 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-105">This section describes all the schema classes used by Lync Server 2013.</span></span>

<div>

## <a name="schema-classes-and-descriptions"></a><span data-ttu-id="6e7b1-106">Schemaklassen und Beschreibungen</span><span class="sxs-lookup"><span data-stu-id="6e7b1-106">Schema Classes and Descriptions</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e7b1-107">Klasse</span><span class="sxs-lookup"><span data-stu-id="6e7b1-107">Class</span></span></th>
<th><span data-ttu-id="6e7b1-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6e7b1-108">Description</span></span></th>
<th><span data-ttu-id="6e7b1-109">Kommentare</span><span class="sxs-lookup"><span data-stu-id="6e7b1-109">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-110">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="6e7b1-110">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-111">Exchange Unified Messaging (um) e-Mail-Empfänger.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-111">Exchange Unified Messaging (UM) email recipient.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-112">Diese Erweiterungsklasse wird für Exchange um freigegeben.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-112">This auxiliary class is shared with Exchange UM.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-113">msRTCSIP-ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="6e7b1-113">msRTCSIP-ApplicationContacts</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-114">Diese Klasse ist ein Container für mehrere Anwendungskontakte und enthält selbst keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-114">This class is a container for multiple application contacts and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-115">Neu in Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-115">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-116">msRTCSIP-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="6e7b1-116">msRTCSIP-ApplicationServer</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-117">Diese Klasse enthält den Eintrag für den Dienststeuerungspunkt für eine Instanz von Unified Communications-Anwendungsdiensten.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-117">This class holds the entry for the service control point for an instance of Unified Communications Application Services (UCAS).</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-118">Neu in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-118">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-119">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="6e7b1-119">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-120">Diese Klasse stellt eine Zuordnung zwischen einem bestimmten Pool und dem Anwendungsdienst bereit.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-120">This class provides an association from a specific pool to its Application service.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-121">Neu in Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-121">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-122">msRTCSIP-ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="6e7b1-122">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-123">Diese Auxiliary-Klasse für msRTCSIP-ApplicationServer hält Attribute, die Einstellungen für Instanzen des Anwendungsdienst darstellen.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-123">This auxiliary class to msRTCSIP-ApplicationServer holds attributes representing settings for instances of the Application service.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-124">Neu in Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-124">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-125">msRTCSIP-Archive (veraltet)</span><span class="sxs-lookup"><span data-stu-id="6e7b1-125">msRTCSIP-Archive (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-126">Diese Erweiterungsklasse zu "msRTCSIP-GlobalContainer" enthält alle Einstellungen, die sich auf die Archivierung beziehen.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-126">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to archiving.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-127">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-127">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-128">msRTCSIP-ArchivingServer (veraltet)</span><span class="sxs-lookup"><span data-stu-id="6e7b1-128">msRTCSIP-ArchivingServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-p101">Diese Klasse stellt einen einzelnen Instant Messaging-Archivierungsserver dar. Eine Instanz dieser Klasse wird erstellt, wenn ein Computer als Instant Messaging-Archivierungsserver (z. B. ein Computer, auf dem der Instant Messaging-Archivierungsdienst installiert ist) aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-p101">This class represents a single instant messaging Archiving Server. An instance of this class is created when a computer is activated as an instant messaging Archiving Server, such as a computer with the Instant Messaging Archiving service installed.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-131">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-131">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-132">msRTCSIP-conferencedirectories "</span><span class="sxs-lookup"><span data-stu-id="6e7b1-132">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-133">Diese Klasse ist ein Container für mehrere Instanzen von Konferenzverzeichnissen und enthält selbst keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-133">This class is a container for multiple instances of conference directories and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-134">Neu in Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-134">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-135">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="6e7b1-135">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-136">Diese Klasse enthält Attribute, die Einstellungen für ein bestimmtes Konferenzverzeichnis darstellen.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-136">This class holds attributes representing settings for a specific conference directory.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-137">Neu in Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-137">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-138">msRTCSIP-ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="6e7b1-138">msRTCSIP-ConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-139">Allgemeiner Dienststeuerungspunkt (Service Control Points, SCP) zum Angeben des Computers als Server mit lync Server.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-139">Generic service control point (SCP) to specify the computer as a server running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-140">Neu in lync 2010.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-140">New in Lync 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-141">msRTCSIP-DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="6e7b1-141">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-142">Diese Auxiliary-Klasse beinhaltet die Einstellungen für eine Microsoft lync Web App Bank.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-142">This auxiliary class holds the settings for a Microsoft Lync Web App bank.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-143">Neu in Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-143">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-144">msRTCSIP-Domäne</span><span class="sxs-lookup"><span data-stu-id="6e7b1-144">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-145">Diese Klasse enthält Attribute, die die konfigurierten Domänen der SIP-Registrierung definieren.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-145">This class holds attributes that define the configured domains of the SIP Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-146">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="6e7b1-146">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-147">Dieser Klassencontainer stellt einen einzelnen Zugriffs-Edgedienst dar.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-147">This class container represents a single Access Edge service.</span></span> <span data-ttu-id="6e7b1-148">Da ein Zugriffs-Edgedienst im Umkreisnetzwerk bereitgestellt wird und Kunden normalerweise nicht Active Directory-Domänendienste Zugriff aus dem Umkreisnetzwerk zulassen, werden Instanzen von Zugriffs-Edgedienst nicht mit dem Active Directory Netzwerk des Intranets verbunden.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-148">Because an Access Edge service is deployed in the perimeter network and customers usually do not allow Active Directory Domain Services access from the perimeter network, instances of Access Edge service are not joined to the intranet’s Active Directory network.</span></span> <span data-ttu-id="6e7b1-149">Somit werden Zugriffsproxys nicht automatisch in AD DS registriert.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-149">Therefore, Access Proxies are not automatically registered in AD DS.</span></span> <span data-ttu-id="6e7b1-150">Der Administrator muss das vorhanden sein jeder Instanz von Zugriffs-Edgedienst in AD DS manuell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-150">The administrator must manually configure the existence of each instance of Access Edge service in AD DS.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-151">msRTCSIP-EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="6e7b1-151">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-152">Diese Erweiterungsklasse zu "msRTCSIP-MCU" enthält Attribute, die Einstellungen für Konferenzserver darstellen.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-152">This auxiliary class to msRTCSIP-MCU holds attributes representing settings for Conferencing servers.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-153">Neu in Microsoft Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-153">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-154">msRTCSIP-EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="6e7b1-154">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-155">Diese Erweiterungsklasse zu "msRTCSIP-MediationServer" enthält Attribute, die Einstellungen für Vermittlungsserver darstellen.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-155">This auxiliary class to msRTCSIP-MediationServer holds attributes representing settings for Mediation Servers.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-156">Neu in Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-156">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-157">msRTCSIP-EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="6e7b1-157">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-158">Diese Erweiterungsklasse zu "msRTCSIP-Server" enthält Attribute, die Einstellungen für SIP-Server darstellen.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-158">This auxiliary class to msRTCSIP-Server holds attributes representing settings for SIP servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-159">msRTCSIP-Partnerverbund</span><span class="sxs-lookup"><span data-stu-id="6e7b1-159">msRTCSIP-Federation</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-160">Diese Erweiterungsklasse zu "msRTCSIP-GlobalContainer" enthält alle Einstellungen, die sich auf den Partnerverbund beziehen.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-160">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to federation.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-161">msRTCSIP-Global Container</span><span class="sxs-lookup"><span data-stu-id="6e7b1-161">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-162">Diese Klasse umfasst alle Einstellungen, die in einer lync Server-Bereitstellung gelten.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-162">This class holds all settings that apply throughout a Lync Server deployment.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-163">msRTCSIP-GlobalUserPolicy (veraltet)</span><span class="sxs-lookup"><span data-stu-id="6e7b1-163">msRTCSIP-GlobalUserPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-164">Diese Klasse stellt eine einzelne Office Communications Server Besprechungsrichtlinie dar.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-164">This class represents a single Office Communications Server meeting policy.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-165">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-165">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-166">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="6e7b1-166">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-167">Das lokale Einstellungsobjekt für die globale Topologie.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-167">The local global topology setting object.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-168">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-168">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-169">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="6e7b1-169">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-170">Container mit Einstellungsobjekten für die globale Topologie.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-170">Container to hold global topology setting objects.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-171">Neu in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-171">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-172">msRTCSIP-LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="6e7b1-172">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-173">Diese Klasse ist ein Container und stellt eine Instanz einer Standortnormalisierungsregel dar.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-173">This class is a container that represents an instance of a location normalization rule.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-174">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="6e7b1-174">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-175">Diese Klasse wird vom Konferenzzentrale erstellt und hält Attribute, die zum Kategorisieren von Konferenztelefon Nummern nach Regionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-175">This class is created by the Conferencing Attendant application and holds attributes used to categorize conference telephone numbers by region.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-176">Neu in Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-176">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-177">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="6e7b1-177">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-178">Diese Klasse ist ein Container für mehrere Instanzen von Standortkontaktzuordnungen und enthält selbst keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-178">This class is a container for multiple instances of location contact mappings and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-179">Neu in Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-179">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-180">msRTCSIP-LocationProfile</span><span class="sxs-lookup"><span data-stu-id="6e7b1-180">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-181">Diese Klasse ist ein Container und stellt ein bestimmtes Standortprofil dar.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-181">This class is a container that represents a specific location profile.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-182">msRTCSIP-LocationProfiles (veraltet)</span><span class="sxs-lookup"><span data-stu-id="6e7b1-182">msRTCSIP-LocationProfiles (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-183">Diese Klasse ist ein Container für mehrere Standortprofile und enthält selbst keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-183">This class is a container for multiple location profiles and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-184">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-184">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-185">msRTCSIP-LocalNormalizations (veraltet)</span><span class="sxs-lookup"><span data-stu-id="6e7b1-185">msRTCSIP-LocalNormalizations (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-186">Diese Klasse ist ein Container für mehrere lokale Normalisierungsregeln und enthält selbst keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-186">This class is a container for multiple local normalization rules and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-187">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-187">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-188">msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="6e7b1-188">msRTCSIP-MCU</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-189">Diese Klasse stellt einen einzelnen Konferenzserver dar.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-189">This class represents a single Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-190">Neu in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-190">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-191">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="6e7b1-191">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-192">Diese Klasse enthält mehrere msRTCSIP-MCUFactory-Klassen und weist selbst keine Attribute auf.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-192">This class holds multiple msRTCSIP-MCUFactory classes and does not have attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-193">Neu in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-193">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-194">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="6e7b1-194">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-p103">Diese Klasse ist ein Container und stellt eine Zuordnungsinstanz für Konferenzserver für einen einzelnen Medientyp dar. Eine Instanz dieser Klasse wird erstellt, sobald der erste Konferenzserver für diesen spezifischen Typ und Hersteller aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-p103">This class is a container representing a Conferencing Server Factory for a single medium type. An instance of this class is created when the first Conferencing server for this particular type and vendor is activated.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-197">Neu in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-197">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-198">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="6e7b1-198">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-199">Diese Klasse stellt eine Zuordnung zwischen einem bestimmten Pool und der dazugehörigen Zuordnungsinstanz für Konferenzserver bereit.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-199">This class provides an association from a specific pool to its Conferencing Server Factory.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-200">Neu in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-200">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-201">msRTCSIP-MediationServer</span><span class="sxs-lookup"><span data-stu-id="6e7b1-201">msRTCSIP-MediationServer</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-202">Diese Klasse enthält den Eintrag für den Dienststeuerungspunkt eines Vermittlungsservers.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-202">This class holds the entry for the service control point for a Mediation Server.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-203">Neu in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-203">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-204">msRTCSIP-Meeting (veraltet)</span><span class="sxs-lookup"><span data-stu-id="6e7b1-204">msRTCSIP-Meeting (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-205">Diese Erweiterungsklasse zu "msRTCSIP-GlobalContainer" enthält Attribute, die konfigurierbare Besprechungseinstellungen darstellen.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-205">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing configurable meeting settings.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-206">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-206">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-207">msRTCSIP-Mobilität</span><span class="sxs-lookup"><span data-stu-id="6e7b1-207">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-208">Container zum Speichern der globalen Mobilitätseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-208">Container that stores the global mobility settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-209">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="6e7b1-209">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-210">Diese Klasse umfasst Attribute, die Einstellungen für einen einzelnen Monitoring Server darstellen.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-210">This class holds attributes that represent settings for a single Monitoring Server.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-211">Neu in Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-211">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-212">msRTCSIP-PhoneRoute (veraltet)</span><span class="sxs-lookup"><span data-stu-id="6e7b1-212">msRTCSIP-PhoneRoute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-p104">Diese Klasse ist ein Container und stellt eine Instanz einer Least-Cost-Route zu einem Gateway oder einem Satz mehrerer Gateways dar. Diese Informationen werden von allen Enterprise-Pools oder Standard Edition-Servern verwendet, um ausgehende Gespräche möglichst kosteneffizient an das PSTN-Netzwerk weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-p104">This class is a container representing an instance of a least cost route to a gateway or set of gateways. This information is used by all Enterprise pools or servers running Standard Edition to route outgoing calls to the public switched telephone network (PSTN) in the most cost effective way.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-215">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-215">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-216">msRTCSIP-PhoneRoutes (veraltet)</span><span class="sxs-lookup"><span data-stu-id="6e7b1-216">msRTCSIP-PhoneRoutes (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-217">Diese Klasse ist ein Container für mehrere Least-Cost-Routen und enthält selbst keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-217">This class is a container for multiple, least cost routes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-218">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-218">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-219">msRTCSIP-Policies (veraltet)</span><span class="sxs-lookup"><span data-stu-id="6e7b1-219">msRTCSIP-Policies (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-220">Diese Klasse enthält mehrere lync Server Richtlinien Klassen und weist selbst keine Attribute auf.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-220">This class holds multiple Lync Server policy classes and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-221">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-221">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-222">msRTCSIP-Pool</span><span class="sxs-lookup"><span data-stu-id="6e7b1-222">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-223">Diese Klasse stellt einen einzelnen lync Server Pool dar.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-223">This class represents a single Lync Server pool.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-224">msRTCSIP-Pools</span><span class="sxs-lookup"><span data-stu-id="6e7b1-224">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-225">Diese Klasse enthält mehrere lync Server Pools und verfügt über keine Attribute selbst.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-225">This class holds multiple Lync Server pools and does not have any attributes itself.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-226">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="6e7b1-226">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-p105">Diese Klasse stellt den Dienststeuerungspunkt eines Pools dar. Das msRTCSIP-PrimaryHomeServer-Attribut von Benutzern in einem Pool zeigt auf eine Instanz dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-p105">This class represents the service control pointservice control point of a pool. Users hosted on a pool have their msRTCSIP-PrimaryHomeServer attribute point to an instance of this class.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-229">msRTCSIP-Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="6e7b1-229">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-230">Container zum Speichern der globalen Anwesenheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-230">Container that stores the global presence settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-231">msRTCSIP-Registrar</span><span class="sxs-lookup"><span data-stu-id="6e7b1-231">msRTCSIP-Registrar</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-232">Diese Erweiterungsklasse zu "msRTCSIP-GlobalContainer" enthält Attribute, die von den SIP-Registrierungsservern verwaltete Benutzereinstellungen darstellen.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-232">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing user settings maintained by the SIP Registrar servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-233">msRTCSIP-RouteUsage (veraltet)</span><span class="sxs-lookup"><span data-stu-id="6e7b1-233">msRTCSIP-RouteUsage (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-p106">Diese Klasse ist ein Container und stellt eine Instanz einer Telefonroutenverwendung dar. Eine Verwendungsklasse für Telefonrouten besteht aus einem Attribut- und einem Beschreibungsfeld. Das Attributfeld definiert einen Verwendungstyp. Im Beschreibungsfeld können Administratoren Hinweise zur Verwendung dieses Attributs in der Telefonroute angeben.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-p106">This class is a container representing an instance of a phone route usage. A phone route usage class consists of an attribute field and a description field. The attribute field defines a usage type. The description field allows administrators to describe the usage for this attribute in the phone route.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-238">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-238">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-239">msRTCSIP-RouteUsages (veraltet)</span><span class="sxs-lookup"><span data-stu-id="6e7b1-239">msRTCSIP-RouteUsages (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-240">Diese Klasse enthält mehrere Instanzen der Klasse "msRTCSIP-RouteUsage" und weist selbst keine Attribute auf.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-240">This class holds multiple instances of the msRTCSIP-RouteUsage class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-241">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-241">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-242">msRTCSIP-Suche</span><span class="sxs-lookup"><span data-stu-id="6e7b1-242">msRTCSIP-Search</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-243">Diese Erweiterungsklasse zu "msRTCSIP-GlobalContainer" enthält Attribute, die den Umfang von Suchergebnissen begrenzen und steuern.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-243">This auxiliary class to msRTCSIP-GlobalContainer holds attributes that limit and control the scope of search results.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-244">msRTCSIP-Server</span><span class="sxs-lookup"><span data-stu-id="6e7b1-244">msRTCSIP-Server</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-245">Diese Klasse stellt einen einzelnen Server mit lync Server dar.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-245">This class represents a single server running Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-246">msRTCSIP-Service</span><span class="sxs-lookup"><span data-stu-id="6e7b1-246">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-247">Diese Klasse enthält den Container für globale Einstellungen und msRTCSIP-Domain-Objekte.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-247">This class holds the global settings container and msRTCSIP-Domain objects.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-248">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="6e7b1-248">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-249">Diese Klasse enthält Attribute, die Einstellungen für einen vertrauenswürdigen Konferenzserver darstellen.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-249">This class holds attributes that represent settings for a trusted Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-250">Neu in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-250">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-251">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="6e7b1-251">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-252">Diese Klasse enthält mehrere Instanzen der Klasse "msRTCSIP-TrustedMCU" und weist selbst keine Attribute auf.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-252">This class holds multiple instances of the msRTCSIP-TrustedMCU class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-253">Neu in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-253">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-254">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="6e7b1-254">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-255">Diese Klasse enthält mehrere msRTCSIP-TrustedProxy-Klassen und weist selbst keine Attribute auf.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-255">This class holds multiple msRTCSIP-TrustedProxy classes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-256">Neu in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-256">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-257">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="6e7b1-257">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-p107">Diese Klasse ist ein Container und stellt einen Server dar, auf dem ein Proxyserver ausgeführt wird. Eine Instanz dieser Klasse wird erstellt, sobald ein neuer Proxyserver auf einem Computer aktiviert wird, der Mitglied von AD DS ist.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-p107">This class is a container representing a server running Proxy Server. An instance of this class is created when activating a new Proxy Server on a computer joined to AD DS.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-260">Neu in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-260">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-261">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="6e7b1-261">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-262">Diese Klasse enthält Attribute, die Einstellungen für einen vertrauenswürdigen Server darstellen.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-262">This class holds attributes that represent settings for a trusted server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-263">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="6e7b1-263">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-264">Diese Klasse ist ein Container und stellt einen vertrauenswürdigen Dienst dar, der unter Verwendung einer GRUU-Adresse (Globally Routable User Agent URI) routingfähig ist.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-264">This class is a container representing a trusted service that is routable using a Globally Routable User Agent URI (GRUU) address.</span></span> <span data-ttu-id="6e7b1-265">Eine Instanz dieser Klasse wird erstellt, wenn ein neuer Server aktiviert wird, der von lync Server als vertrauenswürdig eingestuft wird.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-265">An instance of this class is created when a new server that is trusted by Lync Server is activated.</span></span> <span data-ttu-id="6e7b1-266">Dieser vertrauenswürdige Server muss Mitglied einer Active Directory-Domäne sein.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-266">This trusted server must be joined to an Active Directory domain.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-267">Neu in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-267">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-268">msRTCSIP-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="6e7b1-268">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-269">Diese Klasse ist ein Container für mehrere GRUU-Server und enthält selbst keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-269">This class is a container for multiple GRUU servers and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-270">Neu in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-270">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-271">msRTCSIP-TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="6e7b1-271">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-272">Diese Klasse enthält Attribute, die die Einstellungen für eine vertrauenswürdige Webkomponente darstellen.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-272">This class holds attributes that represent the settings for a trusted web component.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-273">Neu in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-273">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-274">msRTCSIP-TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="6e7b1-274">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-275">Diese Klasse enthält mehrere Instanzen der Klasse "msRTCSIP-TrustedWebComponentServer" und weist selbst keine Attribute auf.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-275">This class holds multiple instances of the msRTCSIP-TrustedWebComponentServer class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-276">Neu in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-276">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-277">msRTCSIP-UnifiedCommunications (veraltet)</span><span class="sxs-lookup"><span data-stu-id="6e7b1-277">msRTCSIP-UnifiedCommunications (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-278">Diese Erweiterungsklasse zu "msRTCSIP-GlobalContainer" enthält Attribute, die Unified Communications betreffen.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-278">This auxiliary class to msRTCSIP-GlobalContainer holds attributes related to unified communications.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-279">In lync Server 2010 veraltet.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-279">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-280">msRTCSIP-Webkomponenten</span><span class="sxs-lookup"><span data-stu-id="6e7b1-280">msRTCSIP-WebComponents</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-p109">Diese Klasse enthält den Dienststeuerungspunkt für Internetinformationsdienste (Internet Information Services, IIS). Sie identifiziert einen Server als Webkomponentenserver.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-p109">This class holds the service control pointservice control point for Internet Information Server (IIS). It identifies a server as a web components server.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-283">Neu in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-283">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e7b1-284">msRTCSIP-WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="6e7b1-284">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-285">Diese Klasse liefert eine Zuordnung zwischen einem bestimmten Pool und den Webkomponenten, die für diesen Pool verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-285">This class provides an association from a specific pool to the web components that the pool will use.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-286">Neu in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-286">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e7b1-287">msRTCSIP-WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="6e7b1-287">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-288">Diese Erweiterungsklasse zu "msRTCSIP-WebComponents" enthält Attribute, die Einstellungen für Webkomponenten darstellen.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-288">This auxiliary class to msRTCSIP-WebComponents holds attributes representing settings for web components.</span></span></p></td>
<td><p><span data-ttu-id="6e7b1-289">Neu in Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="6e7b1-289">New in Communications Server 2007.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

