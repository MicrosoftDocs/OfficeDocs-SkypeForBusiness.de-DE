---
title: 'Lync Server 2013: Liste der Server Tabellen für beständigen Chat'
description: 'Lync Server 2013: Liste der Server Tabellen für beständigen Chat.'
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
ms.openlocfilehash: 838e6d8f83b137923075851b29df4c602a487391
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550051"
---
# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a><span data-ttu-id="cad42-103">Liste der Server Tabellen für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cad42-103">List of Persistent Chat Server tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cad42-104">_**Letztes Änderungsstand des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="cad42-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="cad42-105">Das Datenbankschema für beständigen Chat besteht aus den folgenden Tabellen.</span><span class="sxs-lookup"><span data-stu-id="cad42-105">The Persistent Chat database schema consists of the following tables.</span></span>

<div>

## <a name="active-directory-sync"></a><span data-ttu-id="cad42-106">Active Directory-Synchronisierung</span><span class="sxs-lookup"><span data-stu-id="cad42-106">Active Directory Sync</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cad42-107">Tabelle</span><span class="sxs-lookup"><span data-stu-id="cad42-107">Table</span></span></th>
<th><span data-ttu-id="cad42-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cad42-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cad42-109"><a href="lync-server-2013-tbladcookie.md">tblADCookie in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-109"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-110">Enthält die aktuellen LDAP-Synchronisierungscookies (Lightweight Directory Access-Protokoll).</span><span class="sxs-lookup"><span data-stu-id="cad42-110">Contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span> <span data-ttu-id="cad42-111">Jede Zeile entspricht einer Active Directory-Domänendienste Domäne, die der Server für beständigen Chat aktiv auf Änderungen überwacht.</span><span class="sxs-lookup"><span data-stu-id="cad42-111">Each row corresponds to an Active Directory Domain Services domain that Persistent Chat Server is actively monitoring for changes.</span></span> <span data-ttu-id="cad42-112">(In dieser Tabelle werden nur die Active Directory Domänen dargestellt, die für den Server für beständigen Chat relevant sind.)</span><span class="sxs-lookup"><span data-stu-id="cad42-112">(Only the Active Directory domains that are relevant for Persistent Chat Server are represented in this table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cad42-113"><a href="lync-server-2013-tblprincipalmemberdifference.md">principalmemberdifference in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-113"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-114">Enthält Änderungen an Gruppenmitgliedschaften (sowohl hinzugefügte als auch entfernte Mitglieder), die noch nicht von den späteren Active Directory Synchronisierungs Schritten verarbeitet wurden und eine der temporären Tabellen (zusammen mit der tblADUpdates-Tabelle) sind, die im ersten Schritt der Active Directory Synchronisierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cad42-114">Contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with tblADUpdates table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="cad42-115">Mitgliedschaftsänderungen werden nur für Gruppen gespeichert und/oder verarbeitet, die in der  tblPrincipal-Tabelle aufgelistet sind oder für die hier bereits Mitglieder aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="cad42-115">Membership changes are stored, processed, or both, only for groups that are listed in the tblPrincipal table or that already have members listed there.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cad42-116"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-116"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-117">Enthält Änderungen an Active Directory-Domänendienste, die von den späteren Active Directory Synchronisierungs Schritten noch nicht verarbeitet wurden und eine der temporären Tabellen (zusammen mit der principalmemberdifference-Tabelle) sind, die im ersten Schritt der Active Directory Synchronisierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cad42-117">Contains changes to Active Directory Domain Services that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with the tblPrincipalMemberDifference table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="cad42-118">Änderungen an Active Directory werden nur für Prinzipale gespeichert, verarbeitet oder beide, die bereits in der tblPrincipal-Tabelle aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="cad42-118">Changes to Active Directory are stored, processed, or both only for principals that are already listed in the tblPrincipal table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cad42-119"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-119"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-120">Enthält Prinzipalmitgliedschaften.</span><span class="sxs-lookup"><span data-stu-id="cad42-120">Contains principal memberships.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cad42-121"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-121"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-122">Enthält die Prinzipale, die aus Active Directory aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="cad42-122">Contains the principals that have to be refreshed from Active Directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cad42-123"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-123"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-124">Enthält Zugehörigkeiten, die aus irgendeinem Grund nicht aktualisiert werden konnten, in der Regel aufgrund von Active Directory Zugriffsfehlern.</span><span class="sxs-lookup"><span data-stu-id="cad42-124">Contains affiliations that could not be refreshed for some reason, usually due to Active Directory access errors.</span></span></p>
<p><span data-ttu-id="cad42-p102">Diese Tabelle dient nur zu Informationszwecken. Der Inhalt dieser Tabelle wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="cad42-p102">This table is for informational purposes only. Its content is not used.</span></span></p>
<p><span data-ttu-id="cad42-127">Die Prinzipale mit Zugehörigkeiten, die nicht ordnungsgemäß aktualisiert werden konnten, werden in der tblPrincipalMeta-Tabelle gespeichert und bei Gelegenheit aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="cad42-127">The principals with affiliations that could not be refreshed properly are kept in the tblPrincipalMeta table and are given another chance to be refreshed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a><span data-ttu-id="cad42-128">Prinzipale, Zugehörigkeiten, Knoten, Bereiche und Rollen</span><span class="sxs-lookup"><span data-stu-id="cad42-128">Principals, Affiliations, Nodes, Scopes, and Roles</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cad42-129">Tabelle</span><span class="sxs-lookup"><span data-stu-id="cad42-129">Table</span></span></th>
<th><span data-ttu-id="cad42-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cad42-130">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cad42-131"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-131"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-p103">Enthält Prinzipaltypen zur Kategorisierung des Inhalts der Tabelle tblPrincipal. Diese Tabelle ist statisch. Sie wird beim Erstellen der Datenbank eingerichtet und nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="cad42-p103">Contains principal types to categorize what is in the tblPrincipal table. This table is static. It is set up during database creation and does not change.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cad42-135"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-135"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-136">Enthält alle Prinzipale (Benutzer, Ordner, Gruppen usw.).</span><span class="sxs-lookup"><span data-stu-id="cad42-136">Contains all principals (users, folders, groups, and so on).</span></span> <span data-ttu-id="cad42-137">Der Server für beständigen Chat verarbeitet dies als flache heterogene Liste.</span><span class="sxs-lookup"><span data-stu-id="cad42-137">Persistent Chat Server handles this as a flat heterogeneous list.</span></span> <span data-ttu-id="cad42-138">Verschiedene Spalten basieren auf dem Typ des jeweiligen Prinzipals.</span><span class="sxs-lookup"><span data-stu-id="cad42-138">Various columns are based on the type of each principal.</span></span></p>
<p><span data-ttu-id="cad42-139">Die meisten dieser Prinzipale sind zwischengespeicherte Kopien von Objekten, die in Active Directory gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="cad42-139">Most of these principals are cached copies of objects stored in Active Directory.</span></span> <span data-ttu-id="cad42-140">Das Erstellen der zwischengespeicherten Kopie in der Prinzipal Tabelle dieser Active Directory-Objekte wird als <em>Provision</em>bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="cad42-140">Creating the cached copy in the Principal table of these Active Directory objects is referred as <em>provisioning</em>.</span></span></p>
<p><span data-ttu-id="cad42-141">Einige Prinzipale werden aggressiver als andere erstellt, und einige Active Directory-Objekte werden insgesamt ignoriert.</span><span class="sxs-lookup"><span data-stu-id="cad42-141">Some principals are created more aggressively than others, and some Active Directory objects are ignored altogether.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cad42-142"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-142"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-143">Enthält Haupt Zuordnungen, in denen Mitgliedschaften in Active Directory Sicherheitsgruppen, in Active Directory Container usw. beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="cad42-143">Contains principal affiliations that describe memberships in Active Directory security groups, Active Directory containers, and so on.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cad42-144"><a href="lync-server-2013-tblnode.md">tblNode in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-144"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-145">Enthält den Category-Knoten, der in lync Server-Systemsteuerung verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="cad42-145">Contains the category node, as managed in Lync Server Control Panel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cad42-146"><a href="lync-server-2013-tblroletype.md">tblRoleType in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-146"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-147">Enthält Rollentypen und die zugehörigen Berechtigungsgruppen.</span><span class="sxs-lookup"><span data-stu-id="cad42-147">Contains role types and their associated permission sets.</span></span> <span data-ttu-id="cad42-148">Diese Nachschlagetabelle ist statisch.</span><span class="sxs-lookup"><span data-stu-id="cad42-148">This lookup table is static.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cad42-149"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-149"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-150">Enthält Bereiche, die Knoten zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="cad42-150">Contains scopes assigned to nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cad42-151"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-151"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-152">Enthält Rollen, die Knoten zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="cad42-152">Contains roles assigned to nodes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cad42-153"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-153"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-154">Enthält die registrierten Add-Ins, die Knoten zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="cad42-154">Contains the registered Add-ins that can be associated with nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cad42-155"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-155"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-156">Enthält nur die hartcodierten &quot; Sichtbarkeits &quot; -und &quot; Verhaltens &quot; Attribute, die in der tblNode-Tabelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cad42-156">Contains only the hardcoded &quot;Visibility&quot; and &quot;Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cad42-157"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-157"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-158">Enthält die Werte der hartcodierten &quot; Sichtbarkeits-und Verhaltens &quot; Attribute, die in der tblNode-Tabelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cad42-158">Contains the values of the hardcoded &quot;Visibility” and “Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a><span data-ttu-id="cad42-159">Einladungen, Chats und sonstige Clientunterstützung</span><span class="sxs-lookup"><span data-stu-id="cad42-159">Invites, Chats, and Other Client Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cad42-160">Tabelle</span><span class="sxs-lookup"><span data-stu-id="cad42-160">Table</span></span></th>
<th><span data-ttu-id="cad42-161">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cad42-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cad42-162"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-162"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-163">Enthält Einladungen für alle bereitgestellten Benutzer im System für alle Knoten mit aktivierter automatischer Einladung.</span><span class="sxs-lookup"><span data-stu-id="cad42-163">Contains invites for all provisioned users in the system for all nodes with Auto Invite enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cad42-164"><a href="lync-server-2013-tblchat.md">tblChat in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-164"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-165">Enthält alle Chatnachrichten.</span><span class="sxs-lookup"><span data-stu-id="cad42-165">Contains all chat messages.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cad42-166"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-166"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-167">Enthält die letzte Einladungs-ID, die für jeden Benutzer generiert (und in der tblPrincipalInvite-Tabelle) verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="cad42-167">Contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cad42-168"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-168"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-169">Enthält die letzte Chat-ID, die für jeden Benutzer generiert (und in der tblChat-Tabelle) verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="cad42-169">Contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cad42-170"><a href="lync-server-2013-tblpreference.md">tblPreference in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-170"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-171">Enthält Benutzerclienteinstellungen (nur von Legacyclients verwendet).</span><span class="sxs-lookup"><span data-stu-id="cad42-171">Contains user client preferences (used by legacy clients only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cad42-172"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-172"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-173">Enthält temporäre Token für Dateiübertragungszwecke.</span><span class="sxs-lookup"><span data-stu-id="cad42-173">Contains temporary tokens for file transfer purposes.</span></span> <span data-ttu-id="cad42-174">Jedes Mal, wenn eine Datei hochgeladen oder heruntergeladen wird, generiert der beständige Chat Dienst ein Token, das der Client für den Zugriff auf den Webdienstdatei Speicher verwendet.</span><span class="sxs-lookup"><span data-stu-id="cad42-174">Each time a file is uploaded or downloaded, the Persistent Chat service generates a token that the client uses to access the Web service file store.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a><span data-ttu-id="cad42-175">Serverunterstützung</span><span class="sxs-lookup"><span data-stu-id="cad42-175">Server Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cad42-176">Tabelle</span><span class="sxs-lookup"><span data-stu-id="cad42-176">Table</span></span></th>
<th><span data-ttu-id="cad42-177">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cad42-177">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cad42-178"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-178"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-179">Enthält die aktiven Server im Serverpool für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="cad42-179">Contains the active servers in the Persistent Chat Server pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cad42-180"><a href="lync-server-2013-tbladminlock.md">adminlock in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-180"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-p108">Enthält die Administratorsperre für die Ausführung einiger Administratorbefehle. Der Systemrevisionseintrag in der tblSystemRevision -Tabelle wird nach jeder Freigabe der Sperre schrittweise erhöht.</span><span class="sxs-lookup"><span data-stu-id="cad42-p108">Contains the administrator lock to run some administrator commands. The system revision entry in the tblSystemRevision table is incremented after each release of the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cad42-183"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-183"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-184">Enthält den Revisionsnummerneintrag, der (zusammen mit der AdminLock-Tabelle) zur Einhaltung der Konsistenz bei mehreren Servern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cad42-184">Contains the revision number entry used (along with the tblAdminLock table) for achieving consistency across multiple servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cad42-185"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-185"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-186">Enthält aktuelle Peer-to-Peer-Verbindungen zwischen beständigen Chat Diensten.</span><span class="sxs-lookup"><span data-stu-id="cad42-186">Contains current peer-to-peer connections between Persistent Chat services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cad42-187"><a href="lync-server-2013-tblconfig.md">tblConfig in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cad42-187"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cad42-188">Enthält die nicht unterstützte Konfiguration für den beständigen Chat Server.</span><span class="sxs-lookup"><span data-stu-id="cad42-188">Contains the Persistent Chat Server unsupported configuration.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

