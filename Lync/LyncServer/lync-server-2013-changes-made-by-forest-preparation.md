---
title: 'Lync Server 2013: von der Gesamtstrukturvorbereitung vorgenommene Änderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6954e8a4cd76e103516fd1f2323ef04d820dc056
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a><span data-ttu-id="52054-102">Von der Gesamtstrukturvorbereitung in lync Server 2013 vorgenommene Änderungen</span><span class="sxs-lookup"><span data-stu-id="52054-102">Changes made by forest preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52054-103">_**Letztes Änderungsstand des Themas:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="52054-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="52054-104">Dieser Abschnitt enthält eine Beschreibung der globalen Einstellungen und Objekte und der universellen Dienst- und Verwaltungsgruppen, die bei der Gesamtstrukturvorbereitung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="52054-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

<div>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="52054-105">Globale Einstellungen und Objekte in Active Directory</span><span class="sxs-lookup"><span data-stu-id="52054-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="52054-106">Wenn Sie globale Einstellungen im Container "Configuration" (wie bei allen neuen lync Server 2013-Bereitstellungen) speichern, verwendet die Gesamtstrukturvorbereitung den vorhandenen Dienste-Container und \*\*\*\* fügt unter dem Objekt "Configuration\\Services" ein RTC-Dienstobjekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="52054-106">If you store global settings in the Configuration container (as is the case for all new Lync Server 2013 deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\\Services object.</span></span> <span data-ttu-id="52054-107">Unterhalb des Objekts "RTC Service" wird bei der Gesamtstrukturvorbereitung ein Objekt **Global Settings** vom Typ "msRTCSIP-GlobalContainer" hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="52054-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="52054-108">Das Global Settings-Objekt umfasst alle Einstellungen, die für die lync Server-Bereitstellung gelten.</span><span class="sxs-lookup"><span data-stu-id="52054-108">The global settings object holds all the settings that apply to the Lync Server deployment.</span></span> <span data-ttu-id="52054-109">Wenn Sie globale Einstellungen im Systemcontainer speichern, verwendet die Gesamtstrukturvorbereitung einen Microsoft-Container unter dem Stammdomänen-Systemcontainer und ein RTC-Dienst\\Objekt unter dem Microsoft-Systemobjekt.</span><span class="sxs-lookup"><span data-stu-id="52054-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\\Microsoft object.</span></span>

<span data-ttu-id="52054-110">Außerdem wird während der Gesamtstrukturvorbereitung ein neues Objekt **msRTCSIP-Domain** für die Stammdomäne hinzugefügt, in der das Verfahren ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="52054-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="52054-111">Universelle Dienst- und Verwaltungsgruppen in Active Directory</span><span class="sxs-lookup"><span data-stu-id="52054-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="52054-p102">Die Gesamtstrukturvorbereitung erstellt universelle Gruppen anhand der von Ihnen angegebenen Domäne und fügt Zugriffssteuerungseinträge (Access Control Entries, ACEs) für diese Gruppen hinzu. In diesem Schritt werden die universellen Gruppen in den Benutzercontainern der Domäne erstellt, die Sie angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="52054-p102">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups. This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="52054-p103">Anhand von universellen Gruppen können Administratoren globale Einstellungen und Dienste verwenden und verwalten. Bei der Gesamtstrukturvorbereitung werden die folgenden Typen von universellen Gruppen hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="52054-p103">Universal groups allow administrators to access and manage global settings and services. Forest preparation adds the following types of universal groups:</span></span>

  - <span data-ttu-id="52054-116">**Administrative Gruppen**   diese Gruppen definieren Administratorrollen für ein lync Server Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="52054-116">**Administrative groups**   These groups define administrator roles for a Lync Server network.</span></span>

  - <span data-ttu-id="52054-117">**Infrastrukturgruppen**   diese Gruppen bieten die Berechtigung für den Zugriff auf bestimmte Bereiche der lync Server Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="52054-117">**Infrastructure groups**   These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="52054-118">Sie fungieren als Komponenten von administrativen Gruppen.</span><span class="sxs-lookup"><span data-stu-id="52054-118">They function as components of administrative groups.</span></span> <span data-ttu-id="52054-119">Sie sollten diese Gruppen weder ändern noch direkt Benutzer zu ihnen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="52054-119">You should not modify these groups or add users directly to them.</span></span>

  - <span data-ttu-id="52054-120">**Dienstgruppen**   diese Gruppen sind Dienstkonten, die für den Zugriff auf verschiedene lync Server Dienste erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="52054-120">**Service groups**   These groups are service accounts that are required to access various Lync Server services.</span></span>

<span data-ttu-id="52054-121">In der folgenden Tabelle werden die administrativen Gruppen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="52054-121">The following table describes the administrative groups.</span></span>

### <a name="administrative-groups-created-during-forest-preparation"></a><span data-ttu-id="52054-122">Administrative Gruppen, die während der Gesamtstrukturvorbereitung erstellt werden</span><span class="sxs-lookup"><span data-stu-id="52054-122">Administrative Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52054-123">Administrative Gruppe</span><span class="sxs-lookup"><span data-stu-id="52054-123">Administrative group</span></span></th>
<th><span data-ttu-id="52054-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52054-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52054-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="52054-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="52054-126">Erlaubt den Mitgliedern, Server- und Pooleinstellungen zu verwalten, darunter alle Serverrollen, globalen Einstellungen und Benutzer.</span><span class="sxs-lookup"><span data-stu-id="52054-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52054-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="52054-127">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="52054-128">Ermöglicht Mitgliedern das Verwalten von Benutzereinstellungen und das Verschieben von Benutzern von einem Server oder Pool zu einem anderen.</span><span class="sxs-lookup"><span data-stu-id="52054-128">Allows members to manage user settings and move users from one server or pool to another.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52054-129">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="52054-129">RTCUniversalReadOnlyAdmins</span></span></p></td>
<td><p><span data-ttu-id="52054-130">Ermöglicht Mitgliedern das Lesen von Server-, Pool- und Benutzereinstellungen.</span><span class="sxs-lookup"><span data-stu-id="52054-130">Allows members to read server, pool, and user settings.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="52054-131">In der folgenden Tabelle werden die Infrastrukturgruppen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="52054-131">The following table describes the infrastructure groups.</span></span>

### <a name="infrastructure-groups-created-during-forest-preparation"></a><span data-ttu-id="52054-132">Infrastrukturgruppen, die während der Gesamtstrukturvorbereitung erstellt werden</span><span class="sxs-lookup"><span data-stu-id="52054-132">Infrastructure Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52054-133">Infrastrukturgruppe</span><span class="sxs-lookup"><span data-stu-id="52054-133">Infrastructure group</span></span></th>
<th><span data-ttu-id="52054-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52054-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52054-135">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="52054-135">RTCUniversalGlobalWriteGroup</span></span></p></td>
<td><p><span data-ttu-id="52054-136">Gewährt Schreibzugriff auf globale Einstellungsobjekte für lync Server.</span><span class="sxs-lookup"><span data-stu-id="52054-136">Grants write access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52054-137">"RTCUniversalGlobalReadOnlyGroup"</span><span class="sxs-lookup"><span data-stu-id="52054-137">RTCUniversalGlobalReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="52054-138">Gewährt schreibgeschützten Zugriff auf globale Einstellungsobjekte für lync Server.</span><span class="sxs-lookup"><span data-stu-id="52054-138">Grants read-only access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52054-139">RTCUniversalUserReadOnlyGroup hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="52054-139">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="52054-140">Gewährt schreibgeschützten Zugriff auf lync Server Benutzereinstellungen.</span><span class="sxs-lookup"><span data-stu-id="52054-140">Grants read-only access to Lync Server user settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52054-141">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="52054-141">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="52054-142">Gewährt schreibgeschützten Zugriff auf lync Server Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="52054-142">Grants read-only access to Lync Server settings.</span></span> <span data-ttu-id="52054-143">Diese Gruppe hat keinen Zugriff auf die Einstellungen auf Poolebene, sondern lediglich auf Einstellungen für einzelne Server.</span><span class="sxs-lookup"><span data-stu-id="52054-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52054-144">Gruppe "rtcuniversalsbatechnicians</span><span class="sxs-lookup"><span data-stu-id="52054-144">RTCUniversalSBATechnicians</span></span></p></td>
<td><p><span data-ttu-id="52054-145">Gewährt schreibgeschützten Zugriff auf lync Server Konfiguration und wird während der Installation in der lokalen Gruppe Administratoren der Survivable Branch Appliances gespeichert.</span><span class="sxs-lookup"><span data-stu-id="52054-145">Grants read-only access to Lync Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="52054-146">In der folgenden Tabelle werden die Dienstgruppen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="52054-146">The following table describes the service groups.</span></span>

### <a name="service-groups-created-during-forest-preparation"></a><span data-ttu-id="52054-147">Dienstgruppen, die während der Gesamtstrukturvorbereitung erstellt werden</span><span class="sxs-lookup"><span data-stu-id="52054-147">Service Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52054-148">Dienstgruppe</span><span class="sxs-lookup"><span data-stu-id="52054-148">Service group</span></span></th>
<th><span data-ttu-id="52054-149">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52054-149">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52054-150">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="52054-150">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="52054-151">Enthält Dienstkonten, die zum Ausführen von Front-End-Server-und Standard Edition-Servern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="52054-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="52054-152">Diese Gruppe ermöglicht Servern Lese-/Schreibzugriff auf lync Server globalen Einstellungen und Active Directory Benutzerobjekten.</span><span class="sxs-lookup"><span data-stu-id="52054-152">This group allows servers read/write access to Lync Server global settings and Active Directory user objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52054-153">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="52054-153">RTCComponentUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="52054-154">Enthält Dienstkonten, die zum Ausführen von A/V-Konferenzservern, Webdienste, Vermittlungsserver, Archivierungsserver und Monitoring Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="52054-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52054-155">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="52054-155">RTCProxyUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="52054-156">Enthält Dienstkonten, die zum Ausführen lync Server Edgeserver verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="52054-156">Includes service accounts used to run Lync Server Edge Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52054-157">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="52054-157">RTCUniversalConfigReplicator</span></span></p></td>
<td><p><span data-ttu-id="52054-158">Enthält Server, die an lync Server Replikation des zentralen Verwaltungsspeichers teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="52054-158">Includes servers that can participate in Lync Server Central Management store replication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52054-159">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="52054-159">RTCSBAUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="52054-160">Gewährt schreibgeschützten Zugriff auf lync Server Einstellungen, ermöglicht jedoch die Konfiguration für die Installation eines Survivable Branch Servers und einer Survivable Branch Appliance-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="52054-160">Grants read-only access to Lync Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="52054-161">Die Gesamtstrukturvorbereitung fügt den entsprechenden Infrastrukturgruppen dann wie folgt Dienst- und Verwaltungsgruppen hinzu:</span><span class="sxs-lookup"><span data-stu-id="52054-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

  - <span data-ttu-id="52054-162">"RTCUniversalServerAdmins" wird zu "RTCUniversalGlobalReadOnlyGroup", "RTCUniversalGlobalWriteGroup", "RTCUniversalServerReadOnlyGroup" und "RTCUniversalUserReadOnlyGroup" hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="52054-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="52054-163">"RTCUniversalUserAdmins" wird als Mitglied von "RTCUniversalGlobalReadOnlyGroup", "RTCUniversalServerReadOnlyGroup" und "RTCUniversalUserReadOnlyGroup" hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="52054-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="52054-164">"RTCHSUniversalServices", "RTCComponentUniversalServices" und "RTCUniversalReadOnlyAdmins" werden als Mitglieder von "RTCUniversalGlobalReadOnlyGroup", "RTCUniversalServerReadOnlyGroup" und "RTCUniversalUserReadOnlyGroup" hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="52054-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="52054-165">Bei der Gesamtstrukturvorbereitung werden außerdem die folgenden rollenbasierten Zugriffssteuerungsgruppen erstellt:</span><span class="sxs-lookup"><span data-stu-id="52054-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

  - <span data-ttu-id="52054-166">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="52054-166">CSAdministrator</span></span>

  - <span data-ttu-id="52054-167">Csarchivingadministrator "</span><span class="sxs-lookup"><span data-stu-id="52054-167">CSArchivingAdministrator</span></span>

  - <span data-ttu-id="52054-168">"Cshelpdesk"</span><span class="sxs-lookup"><span data-stu-id="52054-168">CSHelpDesk</span></span>

  - <span data-ttu-id="52054-169">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="52054-169">CSLocationAdministrator</span></span>

  - <span data-ttu-id="52054-170">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="52054-170">CSResponseGroupAdministrator</span></span>

  - <span data-ttu-id="52054-171">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="52054-171">CSServerAdministrator</span></span>

  - <span data-ttu-id="52054-172">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="52054-172">CSUserAdministrator</span></span>

  - <span data-ttu-id="52054-173">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="52054-173">CSViewOnlyAdministrator</span></span>

  - <span data-ttu-id="52054-174">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="52054-174">CSVoiceAdministrator</span></span>

  - <span data-ttu-id="52054-175">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="52054-175">CsPersistentChatAdministator</span></span>

  - <span data-ttu-id="52054-176">Rolle csresponsegroupmanager</span><span class="sxs-lookup"><span data-stu-id="52054-176">CsResponseGroupManager</span></span>

<span data-ttu-id="52054-177">Ausführliche Informationen zu RBAC-Rollen und den jeweils zulässigen Aufgaben finden Sie unter [Planning for Role-Based Access Control in lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="52054-177">For details about RBAC roles and the tasks allowed for each, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="52054-178">Bei der Gesamtstrukturvorbereitung werden sowohl private als auch öffentliche ACEs erstellt.</span><span class="sxs-lookup"><span data-stu-id="52054-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="52054-179">Es erstellt private ACEs im Container "globale Einstellungen", der von lync Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="52054-179">It creates private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="52054-180">Dieser Container wird nur von lync Server verwendet und befindet sich in Abhängigkeit davon, wo Sie globale Einstellungen speichern, entweder im Konfigurationscontainer oder im System Container in der Stammdomäne.</span><span class="sxs-lookup"><span data-stu-id="52054-180">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="52054-181">Die von der Gesamtstrukturvorbereitung erstellten öffentlichen ACEs sind in der folgenden Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="52054-181">The public ACEs created by forest preparation are listed in the following table.</span></span>

### <a name="public-aces-created-by-forest-preparation"></a><span data-ttu-id="52054-182">Von der Gesamtstruktur erstellte öffentliche ACEs</span><span class="sxs-lookup"><span data-stu-id="52054-182">Public ACEs created by Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52054-183">ACE</span><span class="sxs-lookup"><span data-stu-id="52054-183">ACE</span></span></th>
<th><span data-ttu-id="52054-184">"RTCUniversalGlobalReadOnlyGroup"</span><span class="sxs-lookup"><span data-stu-id="52054-184">RTCUniversalGlobalReadOnlyGroup</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52054-185">Systemcontainer in der Stammdomäne lesen (nicht vererbt)<strong>\*</strong></span><span class="sxs-lookup"><span data-stu-id="52054-185">Read root domain System Container (not inherited)<strong>\*</strong></span></span></p></td>
<td><p><span data-ttu-id="52054-186">X</span><span class="sxs-lookup"><span data-stu-id="52054-186">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52054-187">DisplaySpecifiers-Container der Konfiguration lesen (nicht vererbt)</span><span class="sxs-lookup"><span data-stu-id="52054-187">Read Configuration’s DisplaySpecifiers container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="52054-188">X</span><span class="sxs-lookup"><span data-stu-id="52054-188">X</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="52054-189"><STRONG>\*</STRONG>Nicht geerbte ACEs gewähren keinen Zugriff auf untergeordnete Objekte unterhalb dieser Container.</span><span class="sxs-lookup"><span data-stu-id="52054-189"><STRONG>\*</STRONG>ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="52054-190">ACEs, die vererbt werden, gewähren Zugriff auf untergeordnete Objekte im betreffenden Container.</span><span class="sxs-lookup"><span data-stu-id="52054-190">ACEs that are inherited grant access to child objects under these containers.</span></span>



</div>

<span data-ttu-id="52054-191">Die Gesamtstrukturvorbereitung führt die folgenden Aufgaben im Konfigurationscontainer unter dem Namenskontext für die Konfiguration durch:</span><span class="sxs-lookup"><span data-stu-id="52054-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

  - <span data-ttu-id="52054-192">Hinzufügen eines Eintrags **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** für die Seite **RTC property** unter den Attributen "adminContextMenu" und "adminPropertyPages" des Anzeigebezeichners für Sprachen für Benutzer, Kontakte und InetOrgPersons (z. B.: CN=user-Display,CN=409,CN=DisplaySpecifiers)</span><span class="sxs-lookup"><span data-stu-id="52054-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="52054-193">Hinzufügen eines Objekts **RTCPropertySet** vom Typ **controlAccessRight** unterhalb von **Extended-Rights**, das auf die User- und Contact-Klassen angewendet wird</span><span class="sxs-lookup"><span data-stu-id="52054-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

  - <span data-ttu-id="52054-194">Hinzufügen eines Objekts **RTCUserSearchPropertySet** vom Typ **controlAccessRight** unterhalb von **Extended-Rights**, das auf die User-, Contact-, OU- und DomainDNS-Klassen angewendet wird</span><span class="sxs-lookup"><span data-stu-id="52054-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

  - <span data-ttu-id="52054-195">Hinzufügen von **msRTCSIP-PrimaryUserAddress** unter dem Attribut **extraColumns** der jeweiligen Anzeigebezeichner für die Sprachen der Organisationseinheit (z. B.: CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) und Kopieren der Werte des Attributs **extraColumns** der Standardanzeige (z. B.: CN=default-Display, CN=409,CN=DisplaySpecifiers)</span><span class="sxs-lookup"><span data-stu-id="52054-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="52054-196">Hinzufügen der Filterattribute **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** und **msRTCSIP-UserEnabled** unterhalb des Attributs **attributeDisplayNames** der jeweiligen Anzeigebezeichners für Sprachen für Benutzer-, Kontakt- und InetOrgPerson-Objekte (z. B. auf Englisch: CN=user-Display,CN=409,CN=DisplaySpecifiers)</span><span class="sxs-lookup"><span data-stu-id="52054-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

