---
title: 'Lync Server 2013: Details zur CdR-Tabelle'
description: 'Lync Server 2013: CdR-Tabellendetails.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CDR table details
ms:assetid: 896198f5-672b-48ea-852f-0211c0c90857
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398693(v=OCS.15)
ms:contentKeyID: 48184730
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 331a3dfd4ffccac2ac4a442eeb9ad9171defb41c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544391"
---
# <a name="cdr-table-details-in-lync-server-2013"></a><span data-ttu-id="5bd1f-103">Details zur KDS-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-103">CDR table details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5bd1f-104">_**Letztes Änderungsstand des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="5bd1f-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="5bd1f-105">In den folgenden Themen werden die Spalten in den einzelnen KDS-Daten Satz Tabellen (Call Detail Records) detailliert beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5bd1f-105">The following topics detail the columns in each of the call detail records (CDR) database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5bd1f-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5bd1f-106">In This Section</span></span>

  - [<span data-ttu-id="5bd1f-107">Anwendungstabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-107">Application table in Lync Server 2013</span></span>](lync-server-2013-application-table.md)

  - [<span data-ttu-id="5bd1f-108">CallPriorities-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-108">CallPriorities table in Lync Server 2013</span></span>](lync-server-2013-callpriorities-table.md)

  - [<span data-ttu-id="5bd1f-109">CallType-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-109">CallType table in Lync Server 2013</span></span>](lync-server-2013-calltype-table.md)

  - [<span data-ttu-id="5bd1f-110">Client Versions-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-110">ClientVersions table in Lync Server 2013</span></span>](lync-server-2013-clientversions-table.md)

  - [<span data-ttu-id="5bd1f-111">ConferenceJoinTimeThresholds-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-111">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>](lync-server-2013-conferencejointimethresholds-table.md)

  - [<span data-ttu-id="5bd1f-112">ConferenceMessageCount-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-112">ConferenceMessageCount table in Lync Server 2013</span></span>](lync-server-2013-conferencemessagecount-table.md)

  - [<span data-ttu-id="5bd1f-113">Konferenz Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-113">Conferences table in Lync Server 2013</span></span>](lync-server-2013-conferences-table.md)

  - [<span data-ttu-id="5bd1f-114">ConferenceSessionDetails-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-114">ConferenceSessionDetails table in Lync Server 2013</span></span>](lync-server-2013-conferencesessiondetails-table.md)

  - [<span data-ttu-id="5bd1f-115">ConferenceUris-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-115">ConferenceUris table in Lync Server 2013</span></span>](lync-server-2013-conferenceuris-table.md)

  - [<span data-ttu-id="5bd1f-116">ContentTypes-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-116">ContentTypes table in Lync Server 2013</span></span>](lync-server-2013-contenttypes-table.md)

  - [<span data-ttu-id="5bd1f-117">Deregistertype-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-117">DeRegisterType table in Lync Server 2013</span></span>](lync-server-2013-deregistertype-table.md)

  - [<span data-ttu-id="5bd1f-118">Devices-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-118">Devices table in Lync Server 2013</span></span>](lync-server-2013-devices-table.md)

  - [<span data-ttu-id="5bd1f-119">Dialogfelder (Tabelle) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-119">Dialogs table in Lync Server 2013</span></span>](lync-server-2013-dialogs-table.md)

  - [<span data-ttu-id="5bd1f-120">EdgeServers-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-120">EdgeServers table in Lync Server 2013</span></span>](lync-server-2013-edgeservers-table.md)

  - [<span data-ttu-id="5bd1f-121">ErrorCategory-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-121">ErrorCategory table in Lync Server 2013</span></span>](lync-server-2013-errorcategory-table.md)

  - [<span data-ttu-id="5bd1f-122">ErrorDef-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-122">ErrorDef table in Lync Server 2013</span></span>](lync-server-2013-errordef-table.md)

  - [<span data-ttu-id="5bd1f-123">ErrorReport-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-123">ErrorReport table in Lync Server 2013</span></span>](lync-server-2013-errorreport-table.md)

  - [<span data-ttu-id="5bd1f-124">Filetransfers-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-124">FileTransfers table in Lync Server 2013</span></span>](lync-server-2013-filetransfers-table.md)

  - [<span data-ttu-id="5bd1f-125">FocusJoinsAndLeaves-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-125">FocusJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-focusjoinsandleaves-table.md)

  - [<span data-ttu-id="5bd1f-126">Frontend-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-126">FrontEnd table in Lync Server 2013</span></span>](lync-server-2013-frontend-table.md)

  - [<span data-ttu-id="5bd1f-127">Gateways-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-127">Gateways table in Lync Server 2013</span></span>](lync-server-2013-gateways-table.md)

  - [<span data-ttu-id="5bd1f-128">Hardware Versions-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-128">HardwareVersions table in Lync Server 2013</span></span>](lync-server-2013-hardwareversions-table.md)

  - [<span data-ttu-id="5bd1f-129">IMReportSummary-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-129">IMReportSummary table in Lync Server 2013</span></span>](lync-server-2013-imreportsummary-table.md)

  - [<span data-ttu-id="5bd1f-130">Tabelle "Locations" in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-130">Locations table in Lync Server 2013</span></span>](lync-server-2013-locations-table.md)

  - [<span data-ttu-id="5bd1f-131">Herstellertabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-131">Manufacturers table in Lync Server 2013</span></span>](lync-server-2013-manufacturers-table.md)

  - [<span data-ttu-id="5bd1f-132">McuJoinsAndLeaves-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-132">McuJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-mcujoinsandleaves-table.md)

  - [<span data-ttu-id="5bd1f-133">Tabelle "MCU" in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-133">Mcus table in Lync Server 2013</span></span>](lync-server-2013-mcus-table.md)

  - [<span data-ttu-id="5bd1f-134">Medientabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-134">Media table in Lync Server 2013</span></span>](lync-server-2013-media-table.md)

  - [<span data-ttu-id="5bd1f-135">Medialist-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-135">MediaList table in Lync Server 2013</span></span>](lync-server-2013-medialist-table.md)

  - [<span data-ttu-id="5bd1f-136">MediationServers-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-136">MediationServers table in Lync Server 2013</span></span>](lync-server-2013-mediationservers-table.md)

  - [<span data-ttu-id="5bd1f-137">MSMQProcessing-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-137">MSMQProcessing table in Lync Server 2013</span></span>](lync-server-2013-msmqprocessing-table.md)

  - [<span data-ttu-id="5bd1f-138">Phones-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-138">Phones table in Lync Server 2013</span></span>](lync-server-2013-phones-table.md)

  - [<span data-ttu-id="5bd1f-139">Tabelle "Pools" in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-139">Pools table in Lync Server 2013</span></span>](lync-server-2013-pools-table.md)

  - [<span data-ttu-id="5bd1f-140">ProgressReport-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-140">ProgressReport table in Lync Server 2013</span></span>](lync-server-2013-progressreport-table.md)

  - [<span data-ttu-id="5bd1f-141">PurgeSettings-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-141">PurgeSettings table in Lync Server 2013</span></span>](lync-server-2013-purgesettings-table.md)

  - [<span data-ttu-id="5bd1f-142">Registrierungstabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-142">Registration table in Lync Server 2013</span></span>](lync-server-2013-registration-table.md)

  - [<span data-ttu-id="5bd1f-143">Tabelle "Roles" in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-143">Roles table in Lync Server 2013</span></span>](lync-server-2013-roles-table.md)

  - [<span data-ttu-id="5bd1f-144">Server-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-144">Servers table in Lync Server 2013</span></span>](lync-server-2013-servers-table.md)

  - [<span data-ttu-id="5bd1f-145">SessionDetails-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-145">SessionDetails table in Lync Server 2013</span></span>](lync-server-2013-sessiondetails-table.md)

  - [<span data-ttu-id="5bd1f-146">SIPResponseMetaData-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-146">SIPResponseMetaData table in Lync Server 2013</span></span>](lync-server-2013-sipresponsemetadata-table.md)

  - [<span data-ttu-id="5bd1f-147">Tabelle "Syndikator" in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-147">Syndicators table in Lync Server 2013</span></span>](lync-server-2013-syndicators-table.md)

  - [<span data-ttu-id="5bd1f-148">SyndicatorsTenantMap-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-148">SyndicatorsTenantMap table in Lync Server 2013</span></span>](lync-server-2013-syndicatorstenantmap-table.md)

  - [<span data-ttu-id="5bd1f-149">Vorgangstabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-149">Task table in Lync Server 2013</span></span>](lync-server-2013-task-table.md)

  - [<span data-ttu-id="5bd1f-150">Tabelle "Mandanten" in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-150">Tenants table in Lync Server 2013</span></span>](lync-server-2013-tenants-table.md)

  - [<span data-ttu-id="5bd1f-151">UriTypes-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-151">UriTypes table in Lync Server 2013</span></span>](lync-server-2013-uritypes-table.md)

  - [<span data-ttu-id="5bd1f-152">Tabelle "Users" in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-152">Users table in Lync Server 2013</span></span>](lync-server-2013-users-table.md)

  - [<span data-ttu-id="5bd1f-153">UserAgentDef-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-153">UserAgentDef table in Lync Server 2013</span></span>](lync-server-2013-useragentdef-table.md)

  - [<span data-ttu-id="5bd1f-154">UserStatistics-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-154">UserStatistics table in Lync Server 2013</span></span>](lync-server-2013-userstatistics-table.md)

  - [<span data-ttu-id="5bd1f-155">VoipDetails-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd1f-155">VoipDetails table in Lync Server 2013</span></span>](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

