---
title: 'Lync Server 2013: Liste der Tabellen für den Server für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server tables
ms:assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558628(v=OCS.15)
ms:contentKeyID: 48183659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4902f0710752dd38c146b01bddcc44e135735201
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a><span data-ttu-id="a8b8c-102">Liste der Tabellen für den Server für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8b8c-102">List of Persistent Chat Server tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8b8c-103">_**Letztes Änderungsdatum des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="a8b8c-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="a8b8c-104">Das Datenbank-Schema des beständigen Chats besteht aus den folgenden Tabellen.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-104">The Persistent Chat database schema consists of the following tables.</span></span>

<div>

## <a name="active-directory-sync"></a><span data-ttu-id="a8b8c-105">Active Directory-Synchronisierung</span><span class="sxs-lookup"><span data-stu-id="a8b8c-105">Active Directory Sync</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8b8c-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a8b8c-106">Table</span></span></th>
<th><span data-ttu-id="a8b8c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a8b8c-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8b8c-108"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-108"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-109">Enthält die aktuellen LDAP-Synchronisierungs Cookies (Lightweight Directory Access Protocol).</span><span class="sxs-lookup"><span data-stu-id="a8b8c-109">Contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span> <span data-ttu-id="a8b8c-110">Jede Zeile entspricht einer Active Directory-Domänendienst Domäne, die vom beständigen Chat Server aktiv auf Änderungen überwacht wird.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-110">Each row corresponds to an Active Directory Domain Services domain that Persistent Chat Server is actively monitoring for changes.</span></span> <span data-ttu-id="a8b8c-111">(In dieser Tabelle werden nur die Active Directory-Domänen dargestellt, die für den beständigen Chat Server relevant sind.)</span><span class="sxs-lookup"><span data-stu-id="a8b8c-111">(Only the Active Directory domains that are relevant for Persistent Chat Server are represented in this table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8b8c-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-113">Enthält Änderungen an Gruppenmitgliedschaften (sowohl hinzugefügte als auch entfernte Mitglieder), die noch nicht von den späteren Active Directory-Synchronisierungs Schritten verarbeitet wurden und eine der temporären Tabellen (zusammen mit der tblADUpdates-Tabelle) sind, die im ersten Schritt der Active Directory-Synchronisierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-113">Contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with tblADUpdates table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="a8b8c-114">Mitgliedschaftsänderungen werden gespeichert, verarbeitet oder beides, nur für Gruppen, die in der tblPrincipal-Tabelle aufgelistet sind oder in denen bereits Mitglieder aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-114">Membership changes are stored, processed, or both, only for groups that are listed in the tblPrincipal table or that already have members listed there.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8b8c-115"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-115"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-116">Enthält Änderungen an Active Directory-Domänendiensten, die noch nicht von den späteren Active Directory-Synchronisierungs Schritten verarbeitet wurden und eine der temporären Tabellen (zusammen mit der tblPrincipalMemberDifference-Tabelle) sind, die im ersten Schritt von Active Directory verwendet werden. Synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-116">Contains changes to Active Directory Domain Services that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with the tblPrincipalMemberDifference table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="a8b8c-117">Änderungen an Active Directory werden nur für Prinzipale gespeichert, verarbeitet oder beides, die bereits in der tblPrincipal-Tabelle aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-117">Changes to Active Directory are stored, processed, or both only for principals that are already listed in the tblPrincipal table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8b8c-118"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-118"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-119">Enthält Prinzipal Mitgliedschaften.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-119">Contains principal memberships.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8b8c-120"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-120"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-121">Enthält die Prinzipale, die aus Active Directory aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-121">Contains the principals that have to be refreshed from Active Directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8b8c-122"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-122"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-123">Enthält Zugehörigkeiten, die aus irgendeinem Grund nicht aktualisiert werden konnten, in der Regel aufgrund von Active Directory-Zugriffsfehlern.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-123">Contains affiliations that could not be refreshed for some reason, usually due to Active Directory access errors.</span></span></p>
<p><span data-ttu-id="a8b8c-124">Diese Tabelle dient nur zu Informationszwecken.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-124">This table is for informational purposes only.</span></span> <span data-ttu-id="a8b8c-125">Der Inhalt wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-125">Its content is not used.</span></span></p>
<p><span data-ttu-id="a8b8c-126">Die Prinzipale mit Zuordnungen, die nicht ordnungsgemäß aktualisiert werden konnten, werden in der tblPrincipalMeta-Tabelle aufbewahrt und erhalten eine weitere Chance, aktualisiert zu werden.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-126">The principals with affiliations that could not be refreshed properly are kept in the tblPrincipalMeta table and are given another chance to be refreshed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a><span data-ttu-id="a8b8c-127">Prinzipale, Zuordnungen, Knoten, Bereiche und Rollen</span><span class="sxs-lookup"><span data-stu-id="a8b8c-127">Principals, Affiliations, Nodes, Scopes, and Roles</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8b8c-128">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a8b8c-128">Table</span></span></th>
<th><span data-ttu-id="a8b8c-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a8b8c-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8b8c-130"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-130"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-131">Enthält Prinzipaltypen, um zu kategorisieren, was in der tblPrincipal-Tabelle enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-131">Contains principal types to categorize what is in the tblPrincipal table.</span></span> <span data-ttu-id="a8b8c-132">Diese Tabelle ist statisch.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-132">This table is static.</span></span> <span data-ttu-id="a8b8c-133">Sie wird während der Datenbankerstellung eingerichtet und ändert sich nicht.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-133">It is set up during database creation and does not change.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8b8c-134"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-134"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-135">Enthält alle Prinzipale (Benutzer, Ordner, Gruppen usw.).</span><span class="sxs-lookup"><span data-stu-id="a8b8c-135">Contains all principals (users, folders, groups, and so on).</span></span> <span data-ttu-id="a8b8c-136">Der Server für beständigen Chat behandelt dies als flache heterogene Liste.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-136">Persistent Chat Server handles this as a flat heterogeneous list.</span></span> <span data-ttu-id="a8b8c-137">Verschiedene Spalten basieren auf dem Typ jedes Prinzipals.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-137">Various columns are based on the type of each principal.</span></span></p>
<p><span data-ttu-id="a8b8c-138">Bei den meisten dieser Prinzipale handelt es sich um zwischengespeicherte Kopien von Objekten, die in Active Directory gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-138">Most of these principals are cached copies of objects stored in Active Directory.</span></span> <span data-ttu-id="a8b8c-139">Das Erstellen der zwischengespeicherten Kopie in der Prinzipal Tabelle dieser Active Directory-Objekte wird als <em>Bereitstellung</em>bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-139">Creating the cached copy in the Principal table of these Active Directory objects is referred as <em>provisioning</em>.</span></span></p>
<p><span data-ttu-id="a8b8c-140">Einige Prinzipale werden aggressiver als andere erstellt, und einige Active Directory-Objekte werden insgesamt ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-140">Some principals are created more aggressively than others, and some Active Directory objects are ignored altogether.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8b8c-141"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-141"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-142">Enthält Haupt Zuordnungen, die Mitgliedschaften in Active Directory-Sicherheitsgruppen, Active Directory-Container usw. beschreiben.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-142">Contains principal affiliations that describe memberships in Active Directory security groups, Active Directory containers, and so on.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8b8c-143"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-143"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-144">Enthält den Kategorie-Knoten, wie in der lync Server-Systemsteuerung verwaltet.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-144">Contains the category node, as managed in Lync Server Control Panel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8b8c-145"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-145"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-146">Enthält Rollentypen und die zugehörigen Berechtigungssätze.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-146">Contains role types and their associated permission sets.</span></span> <span data-ttu-id="a8b8c-147">Diese Nachschlagetabelle ist statisch.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-147">This lookup table is static.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8b8c-148"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-148"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-149">Enthält Bereiche, die Knoten zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-149">Contains scopes assigned to nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8b8c-150"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-150"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-151">Enthält Rollen, die Knoten zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-151">Contains roles assigned to nodes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8b8c-152"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-152"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-153">Enthält die registrierten Add-Ins, die Knoten zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-153">Contains the registered Add-ins that can be associated with nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8b8c-154"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-154"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-155">Enthält nur die hart &quot;codierten&quot; Sichtbarkeits-und &quot;Verhaltens&quot; Attribute, die in der tblNode-Tabelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-155">Contains only the hardcoded &quot;Visibility&quot; and &quot;Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8b8c-156"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-156"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-157">Enthält die Werte der hartcodierten &quot;Sichtbarkeits-und Verhaltens&quot; Attribute, die in der tblNode-Tabelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-157">Contains the values of the hardcoded &quot;Visibility” and “Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a><span data-ttu-id="a8b8c-158">Einladungen, Chats und andere Client Unterstützung</span><span class="sxs-lookup"><span data-stu-id="a8b8c-158">Invites, Chats, and Other Client Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8b8c-159">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a8b8c-159">Table</span></span></th>
<th><span data-ttu-id="a8b8c-160">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a8b8c-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8b8c-161"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-161"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-162">Enthält Einladungen für alle bereitgestellten Benutzer im System für alle Knoten, bei denen die automatische Einladung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-162">Contains invites for all provisioned users in the system for all nodes with Auto Invite enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8b8c-163"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-163"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-164">Enthält alle Chatnachrichten.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-164">Contains all chat messages.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8b8c-165"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-165"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-166">Enthält die letzte Einladungs-ID, die für jeden Benutzer generiert (und in der tblPrincipalInvites-Tabelle verwendet) wurde.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-166">Contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8b8c-167"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-167"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-168">Enthält die letzte Chat-ID, die für jeden Benutzer generiert (und in der tblChat-Tabelle verwendet) wurde.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-168">Contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8b8c-169"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-169"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-170">Enthält Benutzer-Client-Einstellungen (nur von Legacy-Clients verwendet).</span><span class="sxs-lookup"><span data-stu-id="a8b8c-170">Contains user client preferences (used by legacy clients only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8b8c-171"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-171"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-172">Enthält temporäre Token für Datei Übertragungs Zwecke.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-172">Contains temporary tokens for file transfer purposes.</span></span> <span data-ttu-id="a8b8c-173">Jedes Mal, wenn eine Datei hochgeladen oder heruntergeladen wird, generiert der beständige Chat Dienst ein Token, das der Client für den Zugriff auf den Webdienst-Dateispeicher verwendet.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-173">Each time a file is uploaded or downloaded, the Persistent Chat service generates a token that the client uses to access the Web service file store.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a><span data-ttu-id="a8b8c-174">Serverunterstützung</span><span class="sxs-lookup"><span data-stu-id="a8b8c-174">Server Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8b8c-175">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a8b8c-175">Table</span></span></th>
<th><span data-ttu-id="a8b8c-176">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a8b8c-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8b8c-177"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-177"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-178">Enthält die aktiven Server im Server Pool für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-178">Contains the active servers in the Persistent Chat Server pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8b8c-179"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-179"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-180">Enthält die administratorsperre zum Ausführen einiger Administrator Befehle.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-180">Contains the administrator lock to run some administrator commands.</span></span> <span data-ttu-id="a8b8c-181">Der systemrevision-Eintrag in der tblSystemRevision-Tabelle wird nach jeder Version der Sperre inkrementiert.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-181">The system revision entry in the tblSystemRevision table is incremented after each release of the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8b8c-182"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-182"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-183">Enthält den Eintrag für die Revisionsnummer (zusammen mit der tblAdminLock-Tabelle), um die Konsistenz auf mehreren Servern zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-183">Contains the revision number entry used (along with the tblAdminLock table) for achieving consistency across multiple servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8b8c-184"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-184"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-185">Enthält aktuelle Peer-to-Peer-Verbindungen zwischen beständigen Chat Diensten.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-185">Contains current peer-to-peer connections between Persistent Chat services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8b8c-186"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8b8c-186"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a8b8c-187">Enthält die Konfiguration des beständigen Chat Servers, die nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="a8b8c-187">Contains the Persistent Chat Server unsupported configuration.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

