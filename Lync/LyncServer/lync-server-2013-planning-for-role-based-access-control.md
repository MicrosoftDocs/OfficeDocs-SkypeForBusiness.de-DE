---
title: 'Lync Server 2013: Planen für die rollenbasierte Zugriffssteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b89e4bdc075783d33bebcfb85398b1b627e1bf1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a><span data-ttu-id="42b0a-102">Planen für die rollenbasierte Zugriffssteuerung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42b0a-102">Planning for role-based access control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42b0a-103">_**Letztes Änderungsdatum des Themas:** 2015-01-27_</span><span class="sxs-lookup"><span data-stu-id="42b0a-103">_**Topic Last Modified:** 2015-01-27_</span></span>

<span data-ttu-id="42b0a-104">Damit Sie administrative Aufgaben delegieren und gleichzeitig hohe Standards für die Sicherheit aufrecht erhalten können, bietet lync Server 2013 rollenbasierte Zugriffssteuerung.</span><span class="sxs-lookup"><span data-stu-id="42b0a-104">To enable you to delegate administrative tasks while maintaining high standards for security, Lync Server 2013 offers role-based access control (RBAC).</span></span> <span data-ttu-id="42b0a-105">Mit RBAC wird Administratorprivilegien gewährt, indem Benutzeradministratorrollen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="42b0a-105">With RBAC, administrative privilege is granted by assigning users to administrative roles.</span></span> <span data-ttu-id="42b0a-106">Lync Server 2013 umfasst zahlreiche integrierte Administratorrollen und ermöglicht Ihnen außerdem, neue Rollen zu erstellen und eine benutzerdefinierte Liste mit Cmdlets für jede neue Rolle festzulegen.</span><span class="sxs-lookup"><span data-stu-id="42b0a-106">Lync Server 2013 includes a rich set of built-in administrative roles, and also enables you to create new roles and specify a custom list of cmdlets for each new role.</span></span> <span data-ttu-id="42b0a-107">Sie können auch Skripten von Cmdlets zu den zulässigen Aufgaben von vordefinierten und benutzerdefinierten RBAC-Rollen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="42b0a-107">You can also add scripts of cmdlets to the allowed tasks of both predefined and custom RBAC roles.</span></span>

<div>

## <a name="better-server-security-and-centralization"></a><span data-ttu-id="42b0a-108">Bessere Server Sicherheit und Zentralisierung</span><span class="sxs-lookup"><span data-stu-id="42b0a-108">Better Server Security and Centralization</span></span>

<span data-ttu-id="42b0a-109">Mit RBAC basieren Zugriff und Autorisierung exakt auf der lync-Server Rolle eines Benutzers.</span><span class="sxs-lookup"><span data-stu-id="42b0a-109">With RBAC, access and authorization is based precisely on a user’s Lync Server role.</span></span> <span data-ttu-id="42b0a-110">Auf diese Weise wird die Verwendung der Sicherheitspraxis von "Least Privilege" ermöglicht, sodass Administratoren und Benutzern nur die Rechte gewährt werden, die für Ihren Auftrag erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="42b0a-110">This enables use of the security practice of "least privilege," granting administrators and users only the rights that are necessary for their job.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="42b0a-111">RBAC-Einschränkungen funktionieren nur für Administratoren, die Remote arbeiten, entweder über die lync Server-Systemsteuerung oder die lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="42b0a-111">RBAC restrictions work only on administrators working remotely, using either the Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="42b0a-112">Ein Benutzer, der auf einem Server mit lync Server sitzt, ist nicht durch RBAC eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="42b0a-112">A user sitting at a server running Lync Server is not restricted by RBAC.</span></span> <span data-ttu-id="42b0a-113">Daher ist die physische Sicherheit Ihres lync-Servers wichtig, um RBAC-Einschränkungen beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="42b0a-113">Therefore, physical security of your Lync Server is important to preserve RBAC restrictions.</span></span>



</div>

</div>

<div>

## <a name="roles-and-scope"></a><span data-ttu-id="42b0a-114">Rollen und Bereich</span><span class="sxs-lookup"><span data-stu-id="42b0a-114">Roles and Scope</span></span>

<span data-ttu-id="42b0a-115">In RBAC ist eine *Rolle* aktiviert, um eine Liste von Cmdlets zu verwenden, die für einen bestimmten Typ von Administrator oder Techniker nützlich sein sollen.</span><span class="sxs-lookup"><span data-stu-id="42b0a-115">In RBAC, a *role* is enabled to use a list of cmdlets, designed to be useful for a certain type of administrator or technician.</span></span> <span data-ttu-id="42b0a-116">Ein *Bereich* ist die Gruppe von Objekten, auf die die in einer Rolle definierten Cmdlets angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="42b0a-116">A *scope* is the set of objects which the cmdlets defined in a role can operate on.</span></span> <span data-ttu-id="42b0a-117">Die Objekte, auf die sich der Bereich auswirkt, können entweder Benutzerkonten (gruppiert nach Organisationseinheit) oder Server (gruppiert nach Website) sein.</span><span class="sxs-lookup"><span data-stu-id="42b0a-117">The objects that scope affects can be either user accounts (grouped by organizational unit) or servers (grouped by site).</span></span>

<span data-ttu-id="42b0a-118">In der folgenden Tabelle sind die vordefinierten Rollen in lync Server aufgelistet, und es wird eine allgemeine Übersicht über die einzelnen Aufgabentypen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="42b0a-118">The following table lists the predefined roles in Lync Server, and gives a general overview of the types of tasks each can do.</span></span> <span data-ttu-id="42b0a-119">Die vierte Spalte zeigt die ähnliche Microsoft Exchange-Serverrolle für jede lync-Serverrolle, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="42b0a-119">The fourth column shows the similar Microsoft Exchange Server role for each Lync Server role, if there is one.</span></span>

### <a name="predefined-administrative-roles"></a><span data-ttu-id="42b0a-120">Vordefinierte Administratorrollen</span><span class="sxs-lookup"><span data-stu-id="42b0a-120">Predefined Administrative Roles</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42b0a-121">Rolle</span><span class="sxs-lookup"><span data-stu-id="42b0a-121">Role</span></span></th>
<th><span data-ttu-id="42b0a-122">Zulässige Aufgaben</span><span class="sxs-lookup"><span data-stu-id="42b0a-122">Tasks allowed</span></span></th>
<th><span data-ttu-id="42b0a-123">Zugrunde liegende Active Directory-Gruppe</span><span class="sxs-lookup"><span data-stu-id="42b0a-123">Underlying Active Directory group</span></span></th>
<th><span data-ttu-id="42b0a-124">Exchange-Äquivalent</span><span class="sxs-lookup"><span data-stu-id="42b0a-124">Exchange equivalent</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42b0a-125">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="42b0a-125">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="42b0a-126">Kann alle administrativen Aufgaben ausführen und alle Einstellungen ändern, einschließlich des Erstellens von Rollen und Zuweisen von Benutzern zu Rollen.</span><span class="sxs-lookup"><span data-stu-id="42b0a-126">Can perform all administrative tasks and modify all settings, including creating roles and assigning users to roles.</span></span> <span data-ttu-id="42b0a-127">Kann eine Bereitstellung erweitern, indem neue Websites, Pools und Dienste hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="42b0a-127">Can expand a deployment by adding new sites, pools, and services.</span></span></p></td>
<td><p><span data-ttu-id="42b0a-128">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="42b0a-128">CSAdministrator</span></span></p></td>
<td><p><span data-ttu-id="42b0a-129">Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="42b0a-129">Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42b0a-130">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="42b0a-130">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="42b0a-131">Kann Benutzer für lync Server aktivieren und deaktivieren, Benutzer verschieben und Benutzern vorhandene Richtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="42b0a-131">Can enable and disable users for Lync Server, move users and assign existing policies to users.</span></span> <span data-ttu-id="42b0a-132">Richtlinien können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="42b0a-132">Cannot modify policies.</span></span></p></td>
<td><p><span data-ttu-id="42b0a-133">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="42b0a-133">CSUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="42b0a-134">E-Mail-Empfänger</span><span class="sxs-lookup"><span data-stu-id="42b0a-134">Mail Recipients</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42b0a-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="42b0a-135">CsVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="42b0a-136">Kann sprachbezogene Einstellungen und Richtlinien erstellen, konfigurieren und verwalten.</span><span class="sxs-lookup"><span data-stu-id="42b0a-136">Can create, configure, and manage voice-related settings and policies.</span></span></p></td>
<td><p><span data-ttu-id="42b0a-137">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="42b0a-137">CSVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="42b0a-138">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="42b0a-138">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42b0a-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="42b0a-139">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="42b0a-140">Kann Server und Dienste verwalten, überwachen und Problembehandlung durchführen.</span><span class="sxs-lookup"><span data-stu-id="42b0a-140">Can manage, monitor, and troubleshoot servers and services.</span></span> <span data-ttu-id="42b0a-141">Kann neue Verbindungen mit Servern verhindern, Dienste beenden und starten und Softwareupdates anwenden.</span><span class="sxs-lookup"><span data-stu-id="42b0a-141">Can prevent new connections to servers, stop and start services, and apply software updates.</span></span> <span data-ttu-id="42b0a-142">Mit Auswirkungen auf die globale Konfiguration können keine Änderungen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="42b0a-142">Cannot make changes with global configuration impact.</span></span></p></td>
<td><p><span data-ttu-id="42b0a-143">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="42b0a-143">CSServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="42b0a-144">Server Verwaltung</span><span class="sxs-lookup"><span data-stu-id="42b0a-144">Server Management</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42b0a-145">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="42b0a-145">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="42b0a-146">Kann die Bereitstellung, einschließlich Benutzer-und Server Informationen, anzeigen, um den Bereitstellungsstatus zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="42b0a-146">Can view the deployment, including user and server information, in order to monitor deployment health.</span></span></p></td>
<td><p><span data-ttu-id="42b0a-147">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="42b0a-147">CSViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="42b0a-148">Organisationsverwaltung mit Ansicht</span><span class="sxs-lookup"><span data-stu-id="42b0a-148">View-Only Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42b0a-149">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="42b0a-149">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="42b0a-150">Kann die Bereitstellung anzeigen, einschließlich der Eigenschaften und Richtlinien des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="42b0a-150">Can view the deployment, including user's properties and policies.</span></span> <span data-ttu-id="42b0a-151">Kann bestimmte Problembehandlungsaufgaben ausführen.</span><span class="sxs-lookup"><span data-stu-id="42b0a-151">Can run specific troubleshooting tasks.</span></span> <span data-ttu-id="42b0a-152">Benutzereigenschaften oder-Richtlinien, Serverkonfiguration oder Dienste können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="42b0a-152">Cannot change user properties or policies, server configuration, or services.</span></span></p></td>
<td><p><span data-ttu-id="42b0a-153">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="42b0a-153">CSHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="42b0a-154">Helpdesk</span><span class="sxs-lookup"><span data-stu-id="42b0a-154">HelpDesk</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42b0a-155">CsArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="42b0a-155">CsArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="42b0a-156">Kann die Archivierungskonfiguration und-Richtlinien ändern.</span><span class="sxs-lookup"><span data-stu-id="42b0a-156">Can modify archiving configuration and policies.</span></span></p></td>
<td><p><span data-ttu-id="42b0a-157">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="42b0a-157">CSArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="42b0a-158">Aufbewahrungsverwaltung, rechtliche Aufbewahrung</span><span class="sxs-lookup"><span data-stu-id="42b0a-158">Retention Management, Legal Hold</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42b0a-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="42b0a-159">CsResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="42b0a-160">Kann die Konfiguration der reaktionsgruppenanwendung innerhalb einer Website verwalten.</span><span class="sxs-lookup"><span data-stu-id="42b0a-160">Can manage the configuration of the Response Group application within a site.</span></span></p></td>
<td><p><span data-ttu-id="42b0a-161">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="42b0a-161">CSResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="42b0a-162">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="42b0a-162">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42b0a-163">CsLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="42b0a-163">CsLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="42b0a-164">Niedrigste Ebene der Rechte für eine erweiterte Verwaltung von 9-1-1 (E9-1-1), einschließlich der Erstellung von E9-1-1-Speicherorten und Netzwerk Bezeichnern sowie deren Zuordnung untereinander.</span><span class="sxs-lookup"><span data-stu-id="42b0a-164">Lowest level of rights for Enhanced 9-1-1 (E9-1-1) management, including creating E9-1-1 locations and network identifiers, and associating these with each other.</span></span> <span data-ttu-id="42b0a-165">Diese Rolle wird immer mit einem globalen Bereich zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="42b0a-165">This role is always assigned with a global scope.</span></span></p></td>
<td><p><span data-ttu-id="42b0a-166">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="42b0a-166">CSLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="42b0a-167">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="42b0a-167">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42b0a-168">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="42b0a-168">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="42b0a-169">Kann bestimmte Antwortgruppen verwalten.</span><span class="sxs-lookup"><span data-stu-id="42b0a-169">Can manage specific response groups.</span></span></p></td>
<td><p><span data-ttu-id="42b0a-170">CSResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="42b0a-170">CSResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="42b0a-171">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="42b0a-171">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42b0a-172">CsPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="42b0a-172">CsPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="42b0a-173">Kann das Feature für beständigen Chat und bestimmte beständige Chatrooms verwalten.</span><span class="sxs-lookup"><span data-stu-id="42b0a-173">Can manage the Persistent Chat feature and specific Persistent Chat rooms.</span></span></p></td>
<td><p><span data-ttu-id="42b0a-174">CSPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="42b0a-174">CSPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="42b0a-175">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="42b0a-175">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="42b0a-176">Alle vordefinierten Rollen, die in lync Server ausgeliefert werden, verfügen über einen globalen Bereich.</span><span class="sxs-lookup"><span data-stu-id="42b0a-176">All predefined roles shipped in Lync Server have a global scope.</span></span> <span data-ttu-id="42b0a-177">Wenn Sie nur eine begrenzte Anzahl von Servern oder Benutzern verwalten möchten, sollten Sie Benutzern keine Rollen mit globalem Gültigkeitsbereich zuweisen, wenn Sie nur eine begrenzte Anzahl von Servern oder Benutzern verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="42b0a-177">To follow least privilege practices, you should not assign users to roles with global scope if they are going to administer only a limited set of servers or users.</span></span> <span data-ttu-id="42b0a-178">Um dies zu erreichen, können Sie Rollen erstellen, die auf einer vorhandenen Rolle basieren, jedoch mit einem eingeschränkten Bereich.</span><span class="sxs-lookup"><span data-stu-id="42b0a-178">To accomplish this, you can create roles which are based on an existing role, but with a more limited scope.</span></span>

<div>

## <a name="creating-a-scoped-role"></a><span data-ttu-id="42b0a-179">Erstellen einer Rolle im Bereich "Bereich"</span><span class="sxs-lookup"><span data-stu-id="42b0a-179">Creating a Scoped Role</span></span>

<span data-ttu-id="42b0a-180">Wenn Sie eine Rolle mit einem eingeschränkten Bereich (einer Rolle mit Gültigkeitsbereich) erstellen, geben Sie den Bereich zusammen mit der vorhandenen Rolle an, auf der er basiert, und der Active Directory-Gruppe, der die Rolle zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="42b0a-180">When you create a role with limited scope (a scoped role), you specify the scope, along with the existing role it is based on and the Active Directory group to be assigned the role.</span></span> <span data-ttu-id="42b0a-181">Die von Ihnen angegebene Active Directory-Gruppe muss bereits erstellt sein.</span><span class="sxs-lookup"><span data-stu-id="42b0a-181">The Active Directory group you specify must already be created.</span></span> <span data-ttu-id="42b0a-182">Das folgende Cmdlet ist ein Beispiel für das Erstellen einer Rolle, die über die Privilegien einer vordefinierten Administratorrolle verfügt, jedoch mit begrenztem Umfang.</span><span class="sxs-lookup"><span data-stu-id="42b0a-182">The following cmdlet is an example of a creating a role which has the privileges of one of the pre-defined administrative roles, but with limited scope.</span></span> <span data-ttu-id="42b0a-183">Sie erstellt eine neue Rolle mit `Site01 Server Administrators`dem Namen.</span><span class="sxs-lookup"><span data-stu-id="42b0a-183">It creates a new role called `Site01 Server Administrators`.</span></span> <span data-ttu-id="42b0a-184">Die Rolle verfügt über die Fähigkeiten der vordefinierten CsServerAdministrator-Rolle, aber nur für die Server, die sich auf der Site01-Website befinden.</span><span class="sxs-lookup"><span data-stu-id="42b0a-184">The role has the abilities of the predefined CsServerAdministrator role, but only for the servers located in the Site01 site.</span></span> <span data-ttu-id="42b0a-185">Damit dieses Cmdlet funktioniert, muss die Site01-Website bereits definiert sein, und es muss bereits eine Univers `Site01 Server Administrators` Elle Sicherheitsgruppe mit dem Namen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="42b0a-185">For this cmdlet to work, the Site01 site must already be defined, and a universal security group named `Site01 Server Administrators` must already exist.</span></span>

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

<span data-ttu-id="42b0a-186">Nachdem dieses Cmdlet ausgeführt wurde, verfügen alle Benutzer, die Mitglieder `Site01 Server Administrators` der Gruppe sind, über Serveradministratorrechte für die Server in Site01.</span><span class="sxs-lookup"><span data-stu-id="42b0a-186">After this cmdlet runs, all users who are members of the `Site01 Server Administrators` group will have server administrator privileges for the servers in Site01.</span></span> <span data-ttu-id="42b0a-187">Darüber hinaus erhalten alle Benutzer, die dieser universellen Sicherheitsgruppe später hinzugefügt werden, auch die Privilegien dieser Rolle.</span><span class="sxs-lookup"><span data-stu-id="42b0a-187">Additionally, any users who are later added to this universal security group also gain the privileges of this role.</span></span> <span data-ttu-id="42b0a-188">Beachten Sie, dass die Rolle selbst und die universelle Sicherheitsgruppe, der Sie zugewiesen ist `Site01 Server Administrators`, aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="42b0a-188">Note that both the role itself, and the universal security group it is assigned to are called `Site01 Server Administrators`.</span></span>

<span data-ttu-id="42b0a-189">Im folgenden Beispiel wird der Benutzerbereich anstelle des Serverbereichs eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="42b0a-189">The following example limits user scope instead of server scope.</span></span> <span data-ttu-id="42b0a-190">Sie erstellt eine `Sales Users Administrator` Rolle, um die Benutzerkonten in der Organisationseinheit "Sales" zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="42b0a-190">It creates a `Sales Users Administrator` role to administer the user accounts in the Sales organizational unit.</span></span> <span data-ttu-id="42b0a-191">Die universelle Sicherheitsgruppe SalesUsersAdministrator muss bereits erstellt sein, damit dieses Cmdlet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="42b0a-191">The SalesUsersAdministrator universal security group must already be created for this cmdlet to work.</span></span>

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a><span data-ttu-id="42b0a-192">Erstellen einer neuen Rolle</span><span class="sxs-lookup"><span data-stu-id="42b0a-192">Creating a New Role</span></span>

<span data-ttu-id="42b0a-193">Zum Erstellen einer Rolle, die Zugriff auf eine Reihe von Cmdlets hat, die nicht in einer der vordefinierten Rollen enthalten sind, oder auf eine Reihe von Skripten oder Modulen, verwenden Sie erneut eine der vordefinierten Rollen als Vorlage.</span><span class="sxs-lookup"><span data-stu-id="42b0a-193">To create a role that has access to a set of cmdlets not in one of the predefined roles, or to a set of scripts or modules, you again start by using one of the predefined roles as a template.</span></span> <span data-ttu-id="42b0a-194">Beachten Sie, dass Skripts und Module, die Rollen ausführen können, an den folgenden Speicherorten gespeichert werden müssen:</span><span class="sxs-lookup"><span data-stu-id="42b0a-194">Note that scripts and modules that roles are to be able to run must be stored in the following locations:</span></span>

  - <span data-ttu-id="42b0a-195">Der lync-Modul Pfad, der standardmäßig C lautet\\: Program\\Files Common\\Files Microsoft lync Server\\2013\\modules lync</span><span class="sxs-lookup"><span data-stu-id="42b0a-195">The Lync module path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\Lync</span></span>

  - <span data-ttu-id="42b0a-196">Der Benutzer Skriptpfad, der standardmäßig C lautet:\\Program Files\\Common Files\\Microsoft lync Server 2013\\AdminScripts</span><span class="sxs-lookup"><span data-stu-id="42b0a-196">The user script path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\AdminScripts</span></span>

<span data-ttu-id="42b0a-197">Zum Erstellen einer neuen Rolle verwenden Sie das Cmdlet **New-CsAdminRole** .</span><span class="sxs-lookup"><span data-stu-id="42b0a-197">To make a new role, you use the **New-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="42b0a-198">Bevor Sie **New-CsAdminRole**ausführen, müssen Sie zuerst die zugrunde liegende universelle Sicherheitsgruppe erstellen, die dieser Rolle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="42b0a-198">Before running **New-CsAdminRole**, you must first create the underlying universal security group that will be associated with this role.</span></span>

<span data-ttu-id="42b0a-199">Die folgenden Cmdlets dienen als Beispiel für das Erstellen einer neuen Rolle.</span><span class="sxs-lookup"><span data-stu-id="42b0a-199">The following cmdlets serve as an example of a creating a new role.</span></span> <span data-ttu-id="42b0a-200">Sie erstellen einen neuen Rollentyp mit `MyHelpDeskScriptRole`dem Namen.</span><span class="sxs-lookup"><span data-stu-id="42b0a-200">They create a new role type called `MyHelpDeskScriptRole`.</span></span> <span data-ttu-id="42b0a-201">Die neue Rolle verfügt über die Fähigkeiten der vordefinierten CsHelpDesk-Rolle und kann die Funktionen zusätzlich in einem Skript mit dem Namen "testscript" ausführen.</span><span class="sxs-lookup"><span data-stu-id="42b0a-201">The new role has the abilities of the predefined CsHelpDesk role, and can additionally run the functions in a script named “testscript”.</span></span>

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

<span data-ttu-id="42b0a-202">Damit dieses Cmdlet funktioniert, müssen Sie zuerst die universelle Sicherheitsgruppe MyHelpDeskScriptRole erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="42b0a-202">For this cmdlet to work, you must have first created the universal security group MyHelpDeskScriptRole.</span></span>

<span data-ttu-id="42b0a-203">Nachdem dieses Cmdlet ausgeführt wurde, können Sie Benutzer dieser Rolle direkt zuweisen (in diesem Fall verfügen Sie über einen globalen Bereich), oder Sie können auf der Grundlage dieser Rolle eine Bereichs Rolle erstellen, wie unter Erstellen einer Rolle im Bereich zuvor in diesem Dokument erläutert.</span><span class="sxs-lookup"><span data-stu-id="42b0a-203">After this cmdlet runs, you can assign users directly to this role (in which case they have global scope), or create a scoped role based on this role, as explained in Creating a Scoped Role, previously in this document.</span></span>

</div>

<div>

## <a name="assigning-roles-to-users"></a><span data-ttu-id="42b0a-204">Zuweisen von Rollen zu Benutzern</span><span class="sxs-lookup"><span data-stu-id="42b0a-204">Assigning Roles to Users</span></span>

<span data-ttu-id="42b0a-205">Jeder lync-Server Rolle ist eine zugrunde liegende universelle Active Directory-Sicherheitsgruppe zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="42b0a-205">Each Lync Server role is associated with an underlying Active Directory universal security group.</span></span> <span data-ttu-id="42b0a-206">Alle Benutzer, die Sie der zugrunde liegenden Gruppe hinzufügen, erhalten die Fähigkeiten dieser Rolle.</span><span class="sxs-lookup"><span data-stu-id="42b0a-206">Any users who you add to the underlying group gain the abilities of that role.</span></span>

<span data-ttu-id="42b0a-207">In den Beispielen in den vorherigen Abschnitten wurde eine neue Rolle erstellt und der neuen Rolle eine vorhandene universelle Sicherheitsgruppe zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="42b0a-207">The examples in the preceding sections both created a new role and assigned an existing universal security group to the new role.</span></span> <span data-ttu-id="42b0a-208">Wenn Sie einer oder mehreren Benutzern eine vorhandene Rolle zuweisen möchten, fügen Sie diese Benutzer der Gruppe hinzu, die der Rolle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="42b0a-208">To assign an existing role to one or more users, add those users to the group associated with the role.</span></span> <span data-ttu-id="42b0a-209">Sie können diesen Gruppen sowohl einzelne Benutzer als auch universelle Sicherheitsgruppen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="42b0a-209">You can add both individual users and universal security groups to these groups.</span></span>

<span data-ttu-id="42b0a-210">Beispielsweise wird der **CsAdministrator** -Rolle automatisch die universelle Sicherheitsgruppe **CS-Administratoren** in Active Directory gewährt.</span><span class="sxs-lookup"><span data-stu-id="42b0a-210">For example, the **CsAdministrator** role is automatically granted to the **CS Administrators** universal security group in Active Directory.</span></span> <span data-ttu-id="42b0a-211">Diese universelle Sicherheitsgruppe wird in Active Directory erstellt, wenn Sie lync Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="42b0a-211">This universal security group is created in Active Directory when you deploy Lync Server.</span></span> <span data-ttu-id="42b0a-212">Um einem Benutzer oder einer Gruppe diese Berechtigung zu erteilen, können Sie ihn einfach der Gruppe **CS-Administratoren** hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="42b0a-212">To grant a user or group this privilege, you can simply add them to the **CS Administrators** group.</span></span>

<span data-ttu-id="42b0a-213">Einem Benutzer können mehrere RBAC-Rollen zugewiesen werden, indem er zu den zugrunde liegenden Active Directory-Gruppen hinzugefügt wird, die jeder Rolle entsprechen.</span><span class="sxs-lookup"><span data-stu-id="42b0a-213">A user can be given multiple RBAC roles by being added to the underlying Active Directory groups that correspond to each role.</span></span>

<span data-ttu-id="42b0a-214">Beachten Sie, dass Benutzer, die später der zugrunde liegenden Active Directory-Gruppe hinzugefügt werden, die Fähigkeiten dieser Rolle erhalten, wenn Sie eine Rolle erstellen.</span><span class="sxs-lookup"><span data-stu-id="42b0a-214">Note that when you create a role, users who are later added to the underlying Active Directory group gain the abilities of that role.</span></span>

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a><span data-ttu-id="42b0a-215">Ändern der Fähigkeiten einer Rolle</span><span class="sxs-lookup"><span data-stu-id="42b0a-215">Modifying the Abilities of a Role</span></span>

<span data-ttu-id="42b0a-216">Sie können die Liste der Cmdlets und Skripts ändern, die von einer Rolle ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="42b0a-216">You can modify the list of cmdlets and scripts that a role can run.</span></span> <span data-ttu-id="42b0a-217">Sie können sowohl die Cmdlets und Skripts ändern, die benutzerdefinierte Rollen ausführen können, aber Sie können nur die Skripts für vordefinierte Rollen ändern.</span><span class="sxs-lookup"><span data-stu-id="42b0a-217">You can modify both the cmdlets and scripts that custom roles can run, but you can modify only the scripts for predefined roles.</span></span> <span data-ttu-id="42b0a-218">Jedes von Ihnen eingegebene Cmdlet kann Cmdlets oder Skripts hinzufügen, entfernen oder ersetzen.</span><span class="sxs-lookup"><span data-stu-id="42b0a-218">Each cmdlet you type can add, remove, or replace cmdlets or scripts.</span></span>

<span data-ttu-id="42b0a-219">Wenn Sie eine Rolle ändern möchten, verwenden Sie das Cmdlet " **Satz-CsAdminRole** ".</span><span class="sxs-lookup"><span data-stu-id="42b0a-219">To modify a role, use the **Set-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="42b0a-220">Das folgende Cmdlet entfernt ein Skript aus der Rolle.</span><span class="sxs-lookup"><span data-stu-id="42b0a-220">The following cmdlet removes one script from the role.</span></span>

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a><span data-ttu-id="42b0a-221">Planen für RBAC</span><span class="sxs-lookup"><span data-stu-id="42b0a-221">Planning for RBAC</span></span>

<span data-ttu-id="42b0a-222">Berücksichtigen Sie für jede Person, die für Ihre lync Server-Bereitstellung jede Art von Administratorrechten erhalten soll, genau, welche Aufgaben Sie durchführen müssen, und weisen Sie Sie den Rollen mit den für Ihren Auftrag erforderlichen geringsten Rechten und Umfang zu.</span><span class="sxs-lookup"><span data-stu-id="42b0a-222">For each person who is to be given any kind of administrative rights for your Lync Server deployment, consider exactly which tasks they need to perform, then assign them to roles with the least privilege and scope necessary for their job.</span></span> <span data-ttu-id="42b0a-223">Falls erforderlich, können Sie das Cmdlet " **Satz-CsAdminRole** " verwenden, um eine neue Rolle mit nur den für die Aufgaben dieser Person erforderlichen Cmdlets zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="42b0a-223">If necessary, you can use the **Set-CsAdminRole** cmdlet to create a new role with only the cmdlets necessary for this person’s tasks.</span></span>

<span data-ttu-id="42b0a-224">Benutzer mit der CsAdministrator-Rolle können alle Typen von Rollen, einschließlich Rollen basierend auf CsAdministrator, erstellen und Ihnen Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="42b0a-224">Users who have the CsAdministrator role can create all types of roles, including roles based on CsAdministrator, and assign users to them.</span></span> <span data-ttu-id="42b0a-225">Die bewährte Methode besteht darin, die CsAdministrator-Rolle einem sehr kleinen Satz vertrauenswürdiger Benutzer zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="42b0a-225">The best practice is to assign the CsAdministrator role to a very small set of trusted users.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

