---
title: 'Lync Server 2013: Planen der rollenbasierten Zugriffssteuerung'
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
ms.openlocfilehash: d88353019a266fbb094df8808faa4543e31bf562
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a><span data-ttu-id="11d1f-102">Planen der rollenbasierten Zugriffssteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11d1f-102">Planning for role-based access control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11d1f-103">_**Letztes Änderungsstand des Themas:** 2015-01-27_</span><span class="sxs-lookup"><span data-stu-id="11d1f-103">_**Topic Last Modified:** 2015-01-27_</span></span>

<span data-ttu-id="11d1f-104">Damit Sie administrative Aufgaben delegieren und gleichzeitig hohe Sicherheitsstandards beibehalten können, bietet lync Server 2013 rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC).</span><span class="sxs-lookup"><span data-stu-id="11d1f-104">To enable you to delegate administrative tasks while maintaining high standards for security, Lync Server 2013 offers role-based access control (RBAC).</span></span> <span data-ttu-id="11d1f-105">Bei der rollenbasierten Zugriffssteuerung werden administrative Berechtigungen erteilt, indem Benutzer Administratorrollen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="11d1f-105">With RBAC, administrative privilege is granted by assigning users to administrative roles.</span></span> <span data-ttu-id="11d1f-106">Lync Server 2013 enthält eine umfangreiche Reihe integrierter Administratorrollen und ermöglicht Ihnen außerdem das Erstellen neuer Rollen und das Angeben einer benutzerdefinierten Liste von Cmdlets für jede neue Rolle.</span><span class="sxs-lookup"><span data-stu-id="11d1f-106">Lync Server 2013 includes a rich set of built-in administrative roles, and also enables you to create new roles and specify a custom list of cmdlets for each new role.</span></span> <span data-ttu-id="11d1f-107">Sie können außerdem den erlaubten Aufgaben der vordefinierten und der benutzerdefinierten rollenbasierten Zugriffssteuerung Skripte von Cmdlets hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="11d1f-107">You can also add scripts of cmdlets to the allowed tasks of both predefined and custom RBAC roles.</span></span>

<div>

## <a name="better-server-security-and-centralization"></a><span data-ttu-id="11d1f-108">Verbesserte Serversicherheit und Zentralisierung</span><span class="sxs-lookup"><span data-stu-id="11d1f-108">Better Server Security and Centralization</span></span>

<span data-ttu-id="11d1f-109">Bei RBAC basiert der Zugriff und die Autorisierung genau auf der lync Server Rolle eines Benutzers.</span><span class="sxs-lookup"><span data-stu-id="11d1f-109">With RBAC, access and authorization is based precisely on a user’s Lync Server role.</span></span> <span data-ttu-id="11d1f-110">So können Sie dem Sicherheitsprinzip "so wenige Rechte wie möglich" folgen, bei dem Administratoren und Benutzer nur die Rechte erhalten, die sie für ihre Arbeit benötigen.</span><span class="sxs-lookup"><span data-stu-id="11d1f-110">This enables use of the security practice of "least privilege," granting administrators and users only the rights that are necessary for their job.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="11d1f-111">RBAC-Einschränkungen funktionieren nur für Administratoren, die Remote arbeiten, indem Sie entweder die lync Server-Systemsteuerung oder lync Server-Verwaltungsshell verwenden.</span><span class="sxs-lookup"><span data-stu-id="11d1f-111">RBAC restrictions work only on administrators working remotely, using either the Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="11d1f-112">Ein Benutzer, der auf einem Server mit lync Server sitzt, wird nicht durch RBAC eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="11d1f-112">A user sitting at a server running Lync Server is not restricted by RBAC.</span></span> <span data-ttu-id="11d1f-113">Daher ist die physische Sicherheit Ihrer lync Server wichtig, um RBAC-Einschränkungen beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="11d1f-113">Therefore, physical security of your Lync Server is important to preserve RBAC restrictions.</span></span>



</div>

</div>

<div>

## <a name="roles-and-scope"></a><span data-ttu-id="11d1f-114">Rollen und Bereiche</span><span class="sxs-lookup"><span data-stu-id="11d1f-114">Roles and Scope</span></span>

<span data-ttu-id="11d1f-p104">Bei der rollenbasierten Zugriffssteuerung kann eine *Rolle* eine Liste von Cmdlets verwenden, die für einen bestimmten Administratortyp oder Techniker von Interesse sind. Ein *Bereich* ist der Satz an Objekten, auf den die in einer Rolle definierten Cmdlets angewendet werden können. Bei den Objekten für diesen Bereich kann es sich entweder um Benutzerkonten (gruppiert nach Organisationseinheit) oder um Server (gruppiert nach Standort) handeln.</span><span class="sxs-lookup"><span data-stu-id="11d1f-p104">In RBAC, a *role* is enabled to use a list of cmdlets, designed to be useful for a certain type of administrator or technician. A *scope* is the set of objects which the cmdlets defined in a role can operate on. The objects that scope affects can be either user accounts (grouped by organizational unit) or servers (grouped by site).</span></span>

<span data-ttu-id="11d1f-118">In der folgenden Tabelle sind die vordefinierten Rollen in lync Server aufgeführt, und es wird eine allgemeine Übersicht über die Aufgabentypen gegeben, die jeweils ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="11d1f-118">The following table lists the predefined roles in Lync Server, and gives a general overview of the types of tasks each can do.</span></span> <span data-ttu-id="11d1f-119">In der vierten Spalte wird die ähnliche Exchange Server Rolle für jede lync Server Rolle angezeigt (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="11d1f-119">The fourth column shows the similar Microsoft Exchange Server role for each Lync Server role, if there is one.</span></span>

### <a name="predefined-administrative-roles"></a><span data-ttu-id="11d1f-120">Vordefinierte Administratorrollen</span><span class="sxs-lookup"><span data-stu-id="11d1f-120">Predefined Administrative Roles</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11d1f-121">Rolle</span><span class="sxs-lookup"><span data-stu-id="11d1f-121">Role</span></span></th>
<th><span data-ttu-id="11d1f-122">Zulässige Aufgaben</span><span class="sxs-lookup"><span data-stu-id="11d1f-122">Tasks allowed</span></span></th>
<th><span data-ttu-id="11d1f-123">Zugrunde liegende Active Directory-Gruppe</span><span class="sxs-lookup"><span data-stu-id="11d1f-123">Underlying Active Directory group</span></span></th>
<th><span data-ttu-id="11d1f-124">Exchange-Äquivalent</span><span class="sxs-lookup"><span data-stu-id="11d1f-124">Exchange equivalent</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11d1f-125">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="11d1f-125">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="11d1f-p106">Kann sämtliche Verwaltungsaufgaben ausführen und alle Einstellungen ändern, einschließlich der Erstellung von Rollen und der Zuweisung von Benutzern zu Rollen. Kann eine Bereitstellung erweitern, indem neue Standorte, Pools und Dienste hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="11d1f-p106">Can perform all administrative tasks and modify all settings, including creating roles and assigning users to roles. Can expand a deployment by adding new sites, pools, and services.</span></span></p></td>
<td><p><span data-ttu-id="11d1f-128">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="11d1f-128">CSAdministrator</span></span></p></td>
<td><p><span data-ttu-id="11d1f-129">Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="11d1f-129">Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11d1f-130">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="11d1f-130">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="11d1f-131">Kann Benutzer für lync Server aktivieren und deaktivieren, Benutzer verlagern und vorhandene Richtlinien Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="11d1f-131">Can enable and disable users for Lync Server, move users and assign existing policies to users.</span></span> <span data-ttu-id="11d1f-132">Kann keine Richtlinien bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="11d1f-132">Cannot modify policies.</span></span></p></td>
<td><p><span data-ttu-id="11d1f-133">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="11d1f-133">CSUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="11d1f-134">Mailempfänger</span><span class="sxs-lookup"><span data-stu-id="11d1f-134">Mail Recipients</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11d1f-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="11d1f-135">CsVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="11d1f-136">Kann VoIP-bezogene Einstellungen und Richtlinien erstellen, konfigurieren und verwalten.</span><span class="sxs-lookup"><span data-stu-id="11d1f-136">Can create, configure, and manage voice-related settings and policies.</span></span></p></td>
<td><p><span data-ttu-id="11d1f-137">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="11d1f-137">CSVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="11d1f-138">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="11d1f-138">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11d1f-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="11d1f-139">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="11d1f-p108">Kann Server und Dienste verwalten, überwachen und eine Problembehandlung durchführen. Kann neue Verbindungen mit Servern verhindern, Dienste beenden und starten und Softwareupdates anwenden. Kann keine Änderungen mit Auswirkung auf die globale Konfiguration durchführen.</span><span class="sxs-lookup"><span data-stu-id="11d1f-p108">Can manage, monitor, and troubleshoot servers and services. Can prevent new connections to servers, stop and start services, and apply software updates. Cannot make changes with global configuration impact.</span></span></p></td>
<td><p><span data-ttu-id="11d1f-143">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="11d1f-143">CSServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="11d1f-144">Serververwaltung</span><span class="sxs-lookup"><span data-stu-id="11d1f-144">Server Management</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11d1f-145">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="11d1f-145">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="11d1f-146">Kann die Bereitstellung anzeigen, einschließlich Benutzer- und Serverinformationen, um die Bereitstellungsintegrität zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="11d1f-146">Can view the deployment, including user and server information, in order to monitor deployment health.</span></span></p></td>
<td><p><span data-ttu-id="11d1f-147">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="11d1f-147">CSViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="11d1f-148">Organisationsverwaltung (Nur Lesen)</span><span class="sxs-lookup"><span data-stu-id="11d1f-148">View-Only Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11d1f-149">"Cshelpdesk"</span><span class="sxs-lookup"><span data-stu-id="11d1f-149">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="11d1f-p109">Kann die Bereitstellung anzeigen, Benutzereigenschaften und -richtlinien eingeschlossen. Kann Aufgaben im Rahmen der Problembehandlung ausführen. Kann keine Benutzereigenschaften oder -richtlinien, Serverkonfigurationen oder Dienste ändern.</span><span class="sxs-lookup"><span data-stu-id="11d1f-p109">Can view the deployment, including user's properties and policies. Can run specific troubleshooting tasks. Cannot change user properties or policies, server configuration, or services.</span></span></p></td>
<td><p><span data-ttu-id="11d1f-153">"Cshelpdesk"</span><span class="sxs-lookup"><span data-stu-id="11d1f-153">CSHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="11d1f-154">Helpdesk</span><span class="sxs-lookup"><span data-stu-id="11d1f-154">HelpDesk</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11d1f-155">Csarchivingadministrator "</span><span class="sxs-lookup"><span data-stu-id="11d1f-155">CsArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="11d1f-156">Kann Archivierungskonfiguration und -richtlinien ändern.</span><span class="sxs-lookup"><span data-stu-id="11d1f-156">Can modify archiving configuration and policies.</span></span></p></td>
<td><p><span data-ttu-id="11d1f-157">Csarchivingadministrator "</span><span class="sxs-lookup"><span data-stu-id="11d1f-157">CSArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="11d1f-158">Verwaltung der Aufbewahrung, rechtliche Aufbewahrungspflicht</span><span class="sxs-lookup"><span data-stu-id="11d1f-158">Retention Management, Legal Hold</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11d1f-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="11d1f-159">CsResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="11d1f-160">Kann die Konfiguration der Reaktionsgruppenanwendung innerhalb eines Standorts verwalten.</span><span class="sxs-lookup"><span data-stu-id="11d1f-160">Can manage the configuration of the Response Group application within a site.</span></span></p></td>
<td><p><span data-ttu-id="11d1f-161">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="11d1f-161">CSResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="11d1f-162">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="11d1f-162">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11d1f-163">CsLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="11d1f-163">CsLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="11d1f-p110">Niedrigste Berechtigungsstufe für E9-1-1-Verwaltung (9-1-1 [erweitert]), einschließlich Erstellung von E9-1-1-Standorten und Netzwerk-IDs, sowie deren Zuordnung zueinander. Diese Rolle wird immer mit globalem Gültigkeitsbereich zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="11d1f-p110">Lowest level of rights for Enhanced 9-1-1 (E9-1-1) management, including creating E9-1-1 locations and network identifiers, and associating these with each other. This role is always assigned with a global scope.</span></span></p></td>
<td><p><span data-ttu-id="11d1f-166">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="11d1f-166">CSLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="11d1f-167">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="11d1f-167">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11d1f-168">Rolle csresponsegroupmanager</span><span class="sxs-lookup"><span data-stu-id="11d1f-168">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="11d1f-169">Kann spezifische Reaktionsgruppen verwalten.</span><span class="sxs-lookup"><span data-stu-id="11d1f-169">Can manage specific response groups.</span></span></p></td>
<td><p><span data-ttu-id="11d1f-170">Rolle csresponsegroupmanager</span><span class="sxs-lookup"><span data-stu-id="11d1f-170">CSResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="11d1f-171">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="11d1f-171">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11d1f-172">"Cspersistentchatadministrator"</span><span class="sxs-lookup"><span data-stu-id="11d1f-172">CsPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="11d1f-173">Kann die Funktion "Beständiger Chat" und spezifische Räume dafür verwalten.</span><span class="sxs-lookup"><span data-stu-id="11d1f-173">Can manage the Persistent Chat feature and specific Persistent Chat rooms.</span></span></p></td>
<td><p><span data-ttu-id="11d1f-174">"Cspersistentchatadministrator"</span><span class="sxs-lookup"><span data-stu-id="11d1f-174">CSPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="11d1f-175">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="11d1f-175">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="11d1f-176">Alle vordefinierten Rollen, die in lync Server ausgeliefert werden, haben einen globalen Bereich.</span><span class="sxs-lookup"><span data-stu-id="11d1f-176">All predefined roles shipped in Lync Server have a global scope.</span></span> <span data-ttu-id="11d1f-177">Um dem Prinzip "so wenige Rechte wie möglich" zu folgen, sollten Sie Benutzern keine Rollen mit globalem Bereich zuweisen, wenn sie nur einen beschränkten Satz an Servern oder Benutzern verwalten sollen.</span><span class="sxs-lookup"><span data-stu-id="11d1f-177">To follow least privilege practices, you should not assign users to roles with global scope if they are going to administer only a limited set of servers or users.</span></span> <span data-ttu-id="11d1f-178">Stattdessen können Sie Rollen erstellen, die auf einer bestehenden Rolle basieren, deren Bereich jedoch eingeschränkter ist.</span><span class="sxs-lookup"><span data-stu-id="11d1f-178">To accomplish this, you can create roles which are based on an existing role, but with a more limited scope.</span></span>

<div>

## <a name="creating-a-scoped-role"></a><span data-ttu-id="11d1f-179">Erstellen einer bereichsbezogenen Rolle</span><span class="sxs-lookup"><span data-stu-id="11d1f-179">Creating a Scoped Role</span></span>

<span data-ttu-id="11d1f-180">Wenn Sie eine Rolle mit begrenztem Bereich erstellen (eine bereichsbezogene Rolle), geben Sie den Bereich zusammen mit der vorhandenen Rolle und der Active Directory Gruppe an, der die Rolle zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="11d1f-180">When you create a role with limited scope (a scoped role), you specify the scope, along with the existing role it is based on and the Active Directory group to be assigned the role.</span></span> <span data-ttu-id="11d1f-181">Die von Ihnen angegebene Active Directory Gruppe muss bereits erstellt sein.</span><span class="sxs-lookup"><span data-stu-id="11d1f-181">The Active Directory group you specify must already be created.</span></span> <span data-ttu-id="11d1f-182">Das folgende Cmdlet ist ein Beispiel für das Erstellen einer Rolle mit den Berechtigungen einer der vordefinierten Administratorrollen, jedoch mit begrenztem Bereich.</span><span class="sxs-lookup"><span data-stu-id="11d1f-182">The following cmdlet is an example of a creating a role which has the privileges of one of the pre-defined administrative roles, but with limited scope.</span></span> <span data-ttu-id="11d1f-183">Es wird eine neue Rolle mit `Site01 Server Administrators`dem Namen erstellt.</span><span class="sxs-lookup"><span data-stu-id="11d1f-183">It creates a new role called `Site01 Server Administrators`.</span></span> <span data-ttu-id="11d1f-184">Die Rolle besitzt die Fähigkeiten der vordefinierten CsServerAdministrator-Rolle, jedoch nur für die Server, die sich am Site01-Standort befinden.</span><span class="sxs-lookup"><span data-stu-id="11d1f-184">The role has the abilities of the predefined CsServerAdministrator role, but only for the servers located in the Site01 site.</span></span> <span data-ttu-id="11d1f-185">Damit dieses Cmdlet funktioniert, muss der Site01-Standort bereits definiert sein, und es muss bereits eine Univers `Site01 Server Administrators` Elle Sicherheitsgruppe mit dem Namen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="11d1f-185">For this cmdlet to work, the Site01 site must already be defined, and a universal security group named `Site01 Server Administrators` must already exist.</span></span>

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

<span data-ttu-id="11d1f-186">Nachdem dieses Cmdlet ausgeführt wurde, verfügen alle Benutzer, die Mitglied `Site01 Server Administrators` der Gruppe sind, über Serveradministratorrechte für die Server in Site01.</span><span class="sxs-lookup"><span data-stu-id="11d1f-186">After this cmdlet runs, all users who are members of the `Site01 Server Administrators` group will have server administrator privileges for the servers in Site01.</span></span> <span data-ttu-id="11d1f-187">Darüber hinaus erhalten alle Benutzer, die dieser universellen Sicherheitsgruppe später hinzugefügt werden, auch die Rechte dieser Rolle.</span><span class="sxs-lookup"><span data-stu-id="11d1f-187">Additionally, any users who are later added to this universal security group also gain the privileges of this role.</span></span> <span data-ttu-id="11d1f-188">Beachten Sie, dass sowohl die Rolle selbst als auch die universelle Sicherheitsgruppe, der Sie `Site01 Server Administrators`zugewiesen ist, aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="11d1f-188">Note that both the role itself, and the universal security group it is assigned to are called `Site01 Server Administrators`.</span></span>

<span data-ttu-id="11d1f-189">Im folgenden Beispiel wird der Serverbereich auf den Benutzerbereich eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="11d1f-189">The following example limits user scope instead of server scope.</span></span> <span data-ttu-id="11d1f-190">Es wird eine `Sales Users Administrator` Rolle zum Verwalten der Benutzerkonten in der Organisationseinheit "Sales" erstellt.</span><span class="sxs-lookup"><span data-stu-id="11d1f-190">It creates a `Sales Users Administrator` role to administer the user accounts in the Sales organizational unit.</span></span> <span data-ttu-id="11d1f-191">Die universelle Sicherheitsgruppe SalesUsersAdministrator muss bereits erstellt sein, damit dieses Cmdlet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="11d1f-191">The SalesUsersAdministrator universal security group must already be created for this cmdlet to work.</span></span>

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a><span data-ttu-id="11d1f-192">Erstellen einer neuen Rolle</span><span class="sxs-lookup"><span data-stu-id="11d1f-192">Creating a New Role</span></span>

<span data-ttu-id="11d1f-p115">Um eine Rolle zu erstellen, die Zugriff auf einen Satz von Cmdlets außerhalb der vordefinierten Rollen oder auf einen Satz von Skripts oder Modulen hat, müssen Sie ebenfalls zunächst eine der vordefinierten Rollen als Vorlage verwenden. Beachten Sie, dass Skripts und Module, die Rollen ausführen können sollen, an folgenden Orten gespeichert werden müssen:</span><span class="sxs-lookup"><span data-stu-id="11d1f-p115">To create a role that has access to a set of cmdlets not in one of the predefined roles, or to a set of scripts or modules, you again start by using one of the predefined roles as a template. Note that scripts and modules that roles are to be able to run must be stored in the following locations:</span></span>

  - <span data-ttu-id="11d1f-195">Der lync-Modul Pfad, der standardmäßig C:\\Programmdateien\\allgemeine Dateien\\Microsoft lync Server 2013\\Module\\lync</span><span class="sxs-lookup"><span data-stu-id="11d1f-195">The Lync module path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\Lync</span></span>

  - <span data-ttu-id="11d1f-196">Der Benutzer\\Skriptpfad, der standardmäßig C: Programmdateien\\allgemeine Dateien\\Microsoft lync Server 2013 AdminScripts\\</span><span class="sxs-lookup"><span data-stu-id="11d1f-196">The user script path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\AdminScripts</span></span>

<span data-ttu-id="11d1f-197">Um eine neue Rolle zu erstellen, verwenden Sie das Cmdlet **New-CsAdminRole**.</span><span class="sxs-lookup"><span data-stu-id="11d1f-197">To make a new role, you use the **New-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="11d1f-198">Vor dem Ausführen von **New-CsAdminRole**müssen Sie zuerst die zugrunde liegende universelle Sicherheitsgruppe erstellen, die dieser Rolle zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="11d1f-198">Before running **New-CsAdminRole**, you must first create the underlying universal security group that will be associated with this role.</span></span>

<span data-ttu-id="11d1f-199">Die folgenden Cmdlet-Beispiele zeigen die Erstellung einer neuen Rolle.</span><span class="sxs-lookup"><span data-stu-id="11d1f-199">The following cmdlets serve as an example of a creating a new role.</span></span> <span data-ttu-id="11d1f-200">Sie erstellen einen neuen Rollentypen mit `MyHelpDeskScriptRole`dem Namen.</span><span class="sxs-lookup"><span data-stu-id="11d1f-200">They create a new role type called `MyHelpDeskScriptRole`.</span></span> <span data-ttu-id="11d1f-201">Die neue Rolle besitzt die Fähigkeiten der vordefinierten Rolle "CsHelpDesk" und kann außerdem die Funktionen in einem Skript namens "testscript" ausführen.</span><span class="sxs-lookup"><span data-stu-id="11d1f-201">The new role has the abilities of the predefined CsHelpDesk role, and can additionally run the functions in a script named “testscript”.</span></span>

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

<span data-ttu-id="11d1f-202">Damit dieses Cmdlet funktioniert, müssen Sie zuerst die universelle Sicherheitsgruppe MyHelpDeskScriptRole erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="11d1f-202">For this cmdlet to work, you must have first created the universal security group MyHelpDeskScriptRole.</span></span>

<span data-ttu-id="11d1f-203">Nach der Ausführung dieses Cmdlets können Sie Benutzer direkt dieser Rolle zuweisen (in diesem Fall haben sie globalen Gültigkeitsbereich) oder eine auf dieser Rolle basierende bereichsbezogene Rolle erstellen. Dies wird weiter oben in diesem Dokument unter "Erstellen einer bereichsbezogenen Rolle" beschrieben.</span><span class="sxs-lookup"><span data-stu-id="11d1f-203">After this cmdlet runs, you can assign users directly to this role (in which case they have global scope), or create a scoped role based on this role, as explained in Creating a Scoped Role, previously in this document.</span></span>

</div>

<div>

## <a name="assigning-roles-to-users"></a><span data-ttu-id="11d1f-204">Zuweisen von Rollen zu Benutzern</span><span class="sxs-lookup"><span data-stu-id="11d1f-204">Assigning Roles to Users</span></span>

<span data-ttu-id="11d1f-205">Jede lync Server Rolle ist einer zugrunde liegenden Active Directory universellen Sicherheitsgruppe zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="11d1f-205">Each Lync Server role is associated with an underlying Active Directory universal security group.</span></span> <span data-ttu-id="11d1f-206">Alle Benutzer, die Sie der zugrunde liegenden Gruppe hinzufügen, erhalten die Fähigkeiten dieser Rolle.</span><span class="sxs-lookup"><span data-stu-id="11d1f-206">Any users who you add to the underlying group gain the abilities of that role.</span></span>

<span data-ttu-id="11d1f-207">In den Beispielen in den vorherigen Abschnitten wurde eine neue Rolle erstellt und der neuen Rolle eine vorhandene universelle Sicherheitsgruppe zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="11d1f-207">The examples in the preceding sections both created a new role and assigned an existing universal security group to the new role.</span></span> <span data-ttu-id="11d1f-208">Wenn Sie einer vorhandenen Rolle einen oder mehrere Benutzer zuweisen möchten, fügen Sie diese Benutzer der Gruppe zu, die der Rolle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="11d1f-208">To assign an existing role to one or more users, add those users to the group associated with the role.</span></span> <span data-ttu-id="11d1f-209">Sie können diesen Gruppen sowohl einzelne Benutzer als auch universelle Sicherheitsgruppen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="11d1f-209">You can add both individual users and universal security groups to these groups.</span></span>

<span data-ttu-id="11d1f-210">Beispielsweise wird die **CsAdministrator** -Rolle automatisch der universellen Sicherheitsgruppe **CS-Administratoren** in Active Directory erteilt.</span><span class="sxs-lookup"><span data-stu-id="11d1f-210">For example, the **CsAdministrator** role is automatically granted to the **CS Administrators** universal security group in Active Directory.</span></span> <span data-ttu-id="11d1f-211">Diese universelle Sicherheitsgruppe wird in Active Directory erstellt, wenn Sie lync Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="11d1f-211">This universal security group is created in Active Directory when you deploy Lync Server.</span></span> <span data-ttu-id="11d1f-212">Wenn Sie einem Benutzer oder einer Gruppe diese Berechtigungen gewähren möchten, können Sie sie einfach der Gruppe **CS-Administratoren** hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="11d1f-212">To grant a user or group this privilege, you can simply add them to the **CS Administrators** group.</span></span>

<span data-ttu-id="11d1f-213">Einem Benutzer können mehrere rollenbasierte Zugriffssteuerungsrollen hinzugefügt werden, indem er den zugrunde liegenden Active Directory-Gruppen hinzugefügt wird, die dieser Rolle entsprechen.</span><span class="sxs-lookup"><span data-stu-id="11d1f-213">A user can be given multiple RBAC roles by being added to the underlying Active Directory groups that correspond to each role.</span></span>

<span data-ttu-id="11d1f-214">Beachten Sie, dass beim Erstellen einer Rolle alle Benutzer, die der zugrunde liegenden Active Directory-Gruppe später hinzugefügt werden, die Fähigkeiten dieser Rolle erhalten.</span><span class="sxs-lookup"><span data-stu-id="11d1f-214">Note that when you create a role, users who are later added to the underlying Active Directory group gain the abilities of that role.</span></span>

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a><span data-ttu-id="11d1f-215">Ändern der Fähigkeiten einer Rolle</span><span class="sxs-lookup"><span data-stu-id="11d1f-215">Modifying the Abilities of a Role</span></span>

<span data-ttu-id="11d1f-p121">Sie können die Liste der Cmdlets und Skripts ändern, die von einer Rolle ausgeführt werden können. Sie können sowohl die Cmdlets als auch die Skripts bearbeiten, die von benutzerdefinierten Rollen ausgeführt werden können, bei vordefinierten Rollen können Sie jedoch nur die Skripts bearbeiten. Jedes Cmdlet, das Sie eingeben, kann Cmdlets oder Skripts hinzufügen, entfernen oder ersetzen.</span><span class="sxs-lookup"><span data-stu-id="11d1f-p121">You can modify the list of cmdlets and scripts that a role can run. You can modify both the cmdlets and scripts that custom roles can run, but you can modify only the scripts for predefined roles. Each cmdlet you type can add, remove, or replace cmdlets or scripts.</span></span>

<span data-ttu-id="11d1f-219">Um eine Rolle zu bearbeiten, verwenden Sie das Cmdlet **Set-CsAdminRole**.</span><span class="sxs-lookup"><span data-stu-id="11d1f-219">To modify a role, use the **Set-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="11d1f-220">Mit dem folgenden Cmdlet wird ein Skript aus der Rolle entfernt.</span><span class="sxs-lookup"><span data-stu-id="11d1f-220">The following cmdlet removes one script from the role.</span></span>

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a><span data-ttu-id="11d1f-221">Planen der rollenbasierten Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="11d1f-221">Planning for RBAC</span></span>

<span data-ttu-id="11d1f-222">Berücksichtigen Sie für jede Person, die eine beliebige Anzahl von Administratorrechten für Ihre lync Server-Bereitstellung erhalten soll, genau, welche Aufgaben Sie durchführen müssen, und weisen Sie Sie Rollen mit den geringsten Rechten und dem für Ihren Auftrag erforderlichen Bereich zu.</span><span class="sxs-lookup"><span data-stu-id="11d1f-222">For each person who is to be given any kind of administrative rights for your Lync Server deployment, consider exactly which tasks they need to perform, then assign them to roles with the least privilege and scope necessary for their job.</span></span> <span data-ttu-id="11d1f-223">Falls erforderlich, können Sie das Cmdlet " **CsAdminRole** " verwenden, um eine neue Rolle mit nur den für die Aufgaben dieser Person erforderlichen Cmdlets zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="11d1f-223">If necessary, you can use the **Set-CsAdminRole** cmdlet to create a new role with only the cmdlets necessary for this person’s tasks.</span></span>

<span data-ttu-id="11d1f-p124">Benutzer mit der Rolle "CsAdministrator" können Rollen jeglichen Typs erstellen – auf "CsAdministrator" basierende Rollen eingeschlossen – und diesen Rollen Benutzer zuweisen. Als bewährte Methode sollte die Rolle "CsAdministrator" nur einem sehr kleinen Kreis vertrauenswürdiger Benutzer zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="11d1f-p124">Users who have the CsAdministrator role can create all types of roles, including roles based on CsAdministrator, and assign users to them. The best practice is to assign the CsAdministrator role to a very small set of trusted users.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

