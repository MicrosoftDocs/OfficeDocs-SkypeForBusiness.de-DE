---
title: 'Lync Server 2013: Liste der CDR-Tabellen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ca9fd0b05eba812730c926685fedb244d60a29e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="7aeed-102">Liste der CDR-Tabellen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7aeed-102">List of CDR tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7aeed-103">_**Letztes Änderungsstand des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="7aeed-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="7aeed-104">Das Datenbankschema für die Aufzeichnung von Kommunikationsdatensätzen (KDS) besteht aus den folgenden Tabellen.</span><span class="sxs-lookup"><span data-stu-id="7aeed-104">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="7aeed-105">Statische Tabellen</span><span class="sxs-lookup"><span data-stu-id="7aeed-105">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7aeed-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="7aeed-106">Table</span></span></th>
<th><span data-ttu-id="7aeed-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7aeed-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-108"><a href="lync-server-2013-callpriorities-table.md">CallPriorities-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-108"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-109">Speichert die Liste möglicher Kommunikationsprioritäten, wie z. B. Notfall, dringend, normal, nicht dringend usw.</span><span class="sxs-lookup"><span data-stu-id="7aeed-109">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-111">Speichert die Klassifizierungsgrenzen, die vom zusammenfassenden Bericht über den Zeitpunkt des Konferenzbeitritts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7aeed-111">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-112"><a href="lync-server-2013-deregistertype-table.md">Deregistertype-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-112"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-113">&quot;Speichert die Liste der möglichen Benutzer deregister Gründe, beispielsweise initiierter Client,&quot; &quot;Registrierung abgelaufen,&quot; &quot;Client Absturz&quot; und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="7aeed-113">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-114"><a href="lync-server-2013-medialist-table.md">Medialist-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-114"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-115">Speichert die Liste der Medientypen, von denen Einträge in der Datenbank generiert werden können (z. B. Sofortnachricht, Audio, Video und Dateiübertragung).</span><span class="sxs-lookup"><span data-stu-id="7aeed-115">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-116"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-116"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-117">Speichert Informationen, mit denen angegeben wird, ob (und wann) verwaltete Kommunikationsdatensätze automatisch aus der CDR-Datenbank gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="7aeed-117">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-118"><a href="lync-server-2013-roles-table.md">Tabelle "Roles" in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-118"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-119">Speichert die Liste möglicher Konferenzrollen (z. B. Teilnehmer und Referent).</span><span class="sxs-lookup"><span data-stu-id="7aeed-119">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-120"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-120"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-121">Speichert eine Liste mit SIP-Antwortcodes und der Klassifizierung und Definition der einzelnen Codes.</span><span class="sxs-lookup"><span data-stu-id="7aeed-121">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="7aeed-122">Hilfstabellen</span><span class="sxs-lookup"><span data-stu-id="7aeed-122">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7aeed-123">Tabelle</span><span class="sxs-lookup"><span data-stu-id="7aeed-123">Table</span></span></th>
<th><span data-ttu-id="7aeed-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7aeed-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-125"><a href="lync-server-2013-clientversions-table.md">Client Versions-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-125"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-126">Speichert die Clients (sowohl Clienttyp als auch Versionsnummer) aller an einem Anruf beteiligten Clients, wobei die Informationen in dieser Datenbank erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="7aeed-126">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-127"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-127"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-128">Speichert eine Liste der ConferenceURI-Werte, die bei Telefonkonferenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7aeed-128">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-129"><a href="lync-server-2013-contenttypes-table.md">ContentTypes-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-129"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-130">Speichert eine Liste der SIP-Inhaltstypen (Session Initiation-Protokoll), die bei Peer-zu-Peer-Anrufen und Telefonkonferenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7aeed-130">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-131"><a href="lync-server-2013-devices-table.md">Devices-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-131"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-132">Speichert eine Liste der Geräte, einschließlich Hersteller, Hardwareversion und MAC-Adresse.</span><span class="sxs-lookup"><span data-stu-id="7aeed-132">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-133"><a href="lync-server-2013-dialogs-table.md">Dialogfelder (Tabelle) in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-133"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-134">Speichert Informationen zur Dialog-ID für jede Sitzung in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="7aeed-134">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-135"><a href="lync-server-2013-edgeservers-table.md">EdgeServers-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-135"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-136">Speichert eine Liste der für externe Anrufe verwendeten Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="7aeed-136">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-137"><a href="lync-server-2013-gateways-table.md">Gateways-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-137"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-138">Speichert eine Liste der für VoIP-Anrufe verwendeten Gateways.</span><span class="sxs-lookup"><span data-stu-id="7aeed-138">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-139"><a href="lync-server-2013-hardwareversions-table.md">Hardware Versions-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-139"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-140">Speichert eine Liste der Hardwareversionen von Geräten (Telefonapparat).</span><span class="sxs-lookup"><span data-stu-id="7aeed-140">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-141"><a href="lync-server-2013-manufacturers-table.md">Herstellertabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-141"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-142">Speichert eine Liste der Hersteller von Geräten (Telefonapparat).</span><span class="sxs-lookup"><span data-stu-id="7aeed-142">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-143"><a href="lync-server-2013-mcus-table.md">Tabelle "MCU" in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-143"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-144">Speichert Informationen zu den verschiedenen A/V-Konferenzservern und deren URIs.</span><span class="sxs-lookup"><span data-stu-id="7aeed-144">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-145"><a href="lync-server-2013-mediationservers-table.md">MediationServers-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-145"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-146">Speichert eine Liste der für VoIP-Anrufe verwendeten Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="7aeed-146">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-147"><a href="lync-server-2013-phones-table.md">Phones-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-147"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-148">Speichert alle Telefonnummern, die bei VoIP-Anrufen verwendet wurden und die archiviert oder deren Kommunikationsdatensätze aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="7aeed-148">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-149"><a href="lync-server-2013-pools-table.md">Tabelle "Pools" in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-149"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-150">Speichert die Namen der Pools, in denen Sofortnachrichten erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="7aeed-150">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-151"><a href="lync-server-2013-servers-table.md">Server-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-151"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-152">Speichert den Namen der an Anrufen beteiligten Server.</span><span class="sxs-lookup"><span data-stu-id="7aeed-152">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-153"><a href="lync-server-2013-tenants-table.md">Tabelle "Mandanten" in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-153"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-154">Speichert die von der aktuellen Bereitstellung unterstützten Mandanten.</span><span class="sxs-lookup"><span data-stu-id="7aeed-154">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="7aeed-155">Es gibt einige integrierte Mandanten für Unternehmensbenutzer, Verbundbenutzer, Benutzer mit Verbindung mit öffentlichen Instant Messaging-Diensten sowie anonyme Benutzer.</span><span class="sxs-lookup"><span data-stu-id="7aeed-155">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-156"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-156"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-157">Ordnet Benutzeragent-IDs den beschreibenden Namen von Agents zu.</span><span class="sxs-lookup"><span data-stu-id="7aeed-157">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-158"><a href="lync-server-2013-users-table.md">Tabelle "Users" in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-158"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-159">Speichert die Benutzer-URIs von Benutzern, die an Sitzungen teilgenommen haben, die in dieser Datenbank aufgezeichnet oder archiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="7aeed-159">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-160"><a href="lync-server-2013-userstatistics-table.md">UserStatistics-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-160"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-161">Speichert Informationen zur Systemnutzung eines einzelnen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="7aeed-161">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="7aeed-162">Spezifische Tabellen für Konferenzkommunikationsdatensätze</span><span class="sxs-lookup"><span data-stu-id="7aeed-162">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7aeed-163">Tabelle</span><span class="sxs-lookup"><span data-stu-id="7aeed-163">Table</span></span></th>
<th><span data-ttu-id="7aeed-164">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7aeed-164">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-165"><a href="lync-server-2013-conferences-table.md">Konferenz Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-165"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-166">Speichert Informationen zu allen Konferenzen, die archiviert wurden oder deren Details aufgezeichnet wurden, einschließlich "ConferenceURI" sowie Start- und Endzeit.</span><span class="sxs-lookup"><span data-stu-id="7aeed-166">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-167"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-167"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-168">Speichert für jede Sitzung Informationen zu jeder SIP-basierten Konferenzsitzung, einschließlich Start- und Endzeit, Benutzer-ID, Antwortcode und Diagnose-ID.</span><span class="sxs-lookup"><span data-stu-id="7aeed-168">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-170">Speichert Informationen zum Beitreten zu sowie zum Verlassen von Konferenzen, einschließlich der Rolle von Benutzern und der Clientversion.</span><span class="sxs-lookup"><span data-stu-id="7aeed-170">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-172">Speichert Informationen zu den an einer Konferenz beteiligten A/V-Konferenzservern sowie die Zeiten, wann Benutzer Konferenzen beitreten und sie verlassen.</span><span class="sxs-lookup"><span data-stu-id="7aeed-172">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="7aeed-173">Tabellen für Nachrichten bei Sofortnachrichten-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="7aeed-173">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7aeed-174">Tabelle</span><span class="sxs-lookup"><span data-stu-id="7aeed-174">Table</span></span></th>
<th><span data-ttu-id="7aeed-175">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7aeed-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-176"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-176"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-177">Für jede Sofortnachrichten-Konferenz wird die Anzahl der von jedem Benutzer gesendeten Nachrichten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7aeed-177">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-178"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-178"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-179">Stellt einen Gesamtbericht zu den durchgeführten Chatsitzungen einer Organisation bereit.</span><span class="sxs-lookup"><span data-stu-id="7aeed-179">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="7aeed-180">Tabellen für Peer-zu-Peer-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="7aeed-180">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7aeed-181">Tabelle</span><span class="sxs-lookup"><span data-stu-id="7aeed-181">Table</span></span></th>
<th><span data-ttu-id="7aeed-182">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7aeed-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-183"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-183"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-184">Speichert für jeden Benutzer Informationen zu jeder Peer-zu-Peer-Sitzung, einschließlich Start- und Endzeit, Benutzer-ID, Antwortcode und Nachrichtenanzahl.</span><span class="sxs-lookup"><span data-stu-id="7aeed-184">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-185"><a href="lync-server-2013-filetransfers-table.md">Filetransfers-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-185"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-186">Speichert Informationen zu Dateiübertragungssitzungen, einschließlich Dateiname und Ergebnis (akzeptiert, abgelehnt oder abgebrochen).</span><span class="sxs-lookup"><span data-stu-id="7aeed-186">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-187"><a href="lync-server-2013-media-table.md">Medientabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-187"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-188">Speichert Informationen zu den an Peer-zu-Peer-Sitzungen beteiligten Medientypen.</span><span class="sxs-lookup"><span data-stu-id="7aeed-188">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="7aeed-189">Tabelle für VoIP-Kommunikationsdatensätze</span><span class="sxs-lookup"><span data-stu-id="7aeed-189">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7aeed-190">Tabelle</span><span class="sxs-lookup"><span data-stu-id="7aeed-190">Table</span></span></th>
<th><span data-ttu-id="7aeed-191">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7aeed-191">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-192"><a href="lync-server-2013-voipdetails-table.md">VoipDetails-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-192"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-193">Speichert für jeden VoIP/PSTN-Anruf mit zwei Parteien Informationen zum Anruf, wie z. B. die Telefon-ID des VoIP-Telefons, das verwendete Gateway und welche Partei getrennt wurde.</span><span class="sxs-lookup"><span data-stu-id="7aeed-193">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="7aeed-194">Bezieht sich auf die <a href="lync-server-2013-sessiondetails-table.md">SessionDetails-Tabelle in lync Server 2013</a> für die Start-und Endzeit des Anrufs und den Antwortcode.</span><span class="sxs-lookup"><span data-stu-id="7aeed-194">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="7aeed-195">Wenn eine Anrufpartei ein VoIP-Benutzer ist oder wenn ein Vermittlungsserver am Anruf beteiligt war, wird in dieser Tabelle ein Datensatz erstellt.</span><span class="sxs-lookup"><span data-stu-id="7aeed-195">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="7aeed-196">Informationen zu VoIP/VoIP-Anrufen, die kein Telefon Festnetz (Public Switched Telephone Network, PSTN) betreffen, werden in der <A href="lync-server-2013-sessiondetails-table.md">SessionDetails-Tabelle in lync Server 2013</A>erfasst.</span><span class="sxs-lookup"><span data-stu-id="7aeed-196">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="7aeed-197">Tabelle für die E9-1-1-Anrufüberwachung</span><span class="sxs-lookup"><span data-stu-id="7aeed-197">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7aeed-198">Tabelle</span><span class="sxs-lookup"><span data-stu-id="7aeed-198">Table</span></span></th>
<th><span data-ttu-id="7aeed-199">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7aeed-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-200"><a href="lync-server-2013-locations-table.md">Tabelle "Locations" in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-200"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-201">Für jeden Notruf, wie z. B. einen erweiterten 9-1-1-Anruf (E9-1-1) werden Standortinformationen zum Anruf gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7aeed-201">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="7aeed-202">Bezieht sich auf die <a href="lync-server-2013-sessiondetails-table.md">SessionDetails-Tabelle in lync Server 2013</a> für die Start-und Endzeit des Anrufs und den Antwortcode.</span><span class="sxs-lookup"><span data-stu-id="7aeed-202">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="7aeed-p105">Diese Tabelle enthält nur den Standort-BLOB für den E9-1-1-Anruf. Weitere ausführliche Informationen zum Anruf finden Sie in der SessionDetails-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7aeed-p105">This table only contains the location blob for the E9-1-1 call. Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="7aeed-205">Tabellen für die Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="7aeed-205">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7aeed-206">Tabelle</span><span class="sxs-lookup"><span data-stu-id="7aeed-206">Table</span></span></th>
<th><span data-ttu-id="7aeed-207">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7aeed-207">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-208"><a href="lync-server-2013-application-table.md">Anwendungstabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-208"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-209">Speichert Informationen zu verschiedenen Prozessen in lync Server 2013, die an Routing und Verbindungen beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="7aeed-209">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-210"><a href="lync-server-2013-calltype-table.md">CallType-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-210"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-211">Speichert Informationen zu Anruftypen, wie z. B. "Audio", "Sofortnachrichten", "Audio und Video" und "Anwendungsfreigabe".</span><span class="sxs-lookup"><span data-stu-id="7aeed-211">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-212"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-212"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-213">Speichert den Anzeigenamen für jede Microsoft lync Server 2013 Diagnose Klassifizierung.</span><span class="sxs-lookup"><span data-stu-id="7aeed-213">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-214"><a href="lync-server-2013-errordef-table.md">ErrorDef-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-214"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-215">Speichert Informationen zu Fehlertypen und deren Definitionen.</span><span class="sxs-lookup"><span data-stu-id="7aeed-215">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-216"><a href="lync-server-2013-errorreport-table.md">ErrorReport-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-216"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-217">Speichert Informationen zu aufgetretenen Fehlern.</span><span class="sxs-lookup"><span data-stu-id="7aeed-217">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-218"><a href="lync-server-2013-progressreport-table.md">ProgressReport-Tabelle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7aeed-218"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7aeed-219">Speichert Informationen über die Fortschrittsberichte verschiedener Schritte, die an lync Server 2013 Prozessen beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="7aeed-219">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7aeed-220">Die Tabellen in der folgenden Liste werden intern von lync Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="7aeed-220">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="7aeed-221">Die zugehörigen Details werden in diesem Dokument nicht beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7aeed-221">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="7aeed-222">Tabellen für die interne Verwendung durch Lync Server</span><span class="sxs-lookup"><span data-stu-id="7aeed-222">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7aeed-223">Tabelle</span><span class="sxs-lookup"><span data-stu-id="7aeed-223">Table</span></span></th>
<th><span data-ttu-id="7aeed-224">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7aeed-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-225"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="7aeed-225"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7aeed-226">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="7aeed-226">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-227"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="7aeed-227"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="7aeed-228">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="7aeed-228">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-229"><strong>Dberrormessage</strong></span><span class="sxs-lookup"><span data-stu-id="7aeed-229"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="7aeed-230">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="7aeed-230">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-231"><strong>FrontEnd-Tabelle</strong></span><span class="sxs-lookup"><span data-stu-id="7aeed-231"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="7aeed-232">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="7aeed-232">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-233"><strong>MSMQProcessing-Tabelle</strong></span><span class="sxs-lookup"><span data-stu-id="7aeed-233"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="7aeed-234">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="7aeed-234">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-235"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="7aeed-235"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="7aeed-236">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="7aeed-236">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-237"><strong>Syndicators-Tabelle</strong></span><span class="sxs-lookup"><span data-stu-id="7aeed-237"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="7aeed-238">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="7aeed-238">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-239"><strong>SyndicatorsTenantMap-Tabelle</strong></span><span class="sxs-lookup"><span data-stu-id="7aeed-239"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="7aeed-240">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="7aeed-240">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-241"><strong>Aufgabentabelle</strong></span><span class="sxs-lookup"><span data-stu-id="7aeed-241"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="7aeed-242">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="7aeed-242">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-243"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="7aeed-243"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="7aeed-244">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="7aeed-244">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-245"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="7aeed-245"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="7aeed-246">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="7aeed-246">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-247"><strong>UsageSummary</strong></span><span class="sxs-lookup"><span data-stu-id="7aeed-247"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="7aeed-248">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="7aeed-248">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-249"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="7aeed-249"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="7aeed-250">Nur für interne Verwendung.</span><span class="sxs-lookup"><span data-stu-id="7aeed-250">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-251"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="7aeed-251"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="7aeed-252">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="7aeed-252">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-253"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="7aeed-253"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="7aeed-254">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="7aeed-254">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-255"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="7aeed-255"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="7aeed-256">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="7aeed-256">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-257"><strong>FailureSummary</strong></span><span class="sxs-lookup"><span data-stu-id="7aeed-257"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="7aeed-258">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="7aeed-258">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aeed-259"><strong>ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="7aeed-259"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="7aeed-260">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="7aeed-260">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aeed-261"><strong>MsDiagMetaData</strong></span><span class="sxs-lookup"><span data-stu-id="7aeed-261"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="7aeed-262">Nur zur internen Verwendung.</span><span class="sxs-lookup"><span data-stu-id="7aeed-262">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

