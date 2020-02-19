---
title: 'Lync Server 2013: Details zur CdR-Tabelle'
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
ms.openlocfilehash: dcb8d75948f1b85257f0182d571ea2fe08f3a0d6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="cdr-table-details-in-lync-server-2013"></a><span data-ttu-id="e509c-102">Details zur KDS-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-102">CDR table details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e509c-103">_**Letztes Änderungsstand des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="e509c-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="e509c-104">In den folgenden Themen werden die Spalten in den einzelnen KDS-Daten Satz Tabellen (Call Detail Records) detailliert beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e509c-104">The following topics detail the columns in each of the call detail records (CDR) database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e509c-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e509c-105">In This Section</span></span>

  - [<span data-ttu-id="e509c-106">Anwendungstabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-106">Application table in Lync Server 2013</span></span>](lync-server-2013-application-table.md)

  - [<span data-ttu-id="e509c-107">CallPriorities-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-107">CallPriorities table in Lync Server 2013</span></span>](lync-server-2013-callpriorities-table.md)

  - [<span data-ttu-id="e509c-108">CallType-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-108">CallType table in Lync Server 2013</span></span>](lync-server-2013-calltype-table.md)

  - [<span data-ttu-id="e509c-109">Client Versions-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-109">ClientVersions table in Lync Server 2013</span></span>](lync-server-2013-clientversions-table.md)

  - [<span data-ttu-id="e509c-110">ConferenceJoinTimeThresholds-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-110">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>](lync-server-2013-conferencejointimethresholds-table.md)

  - [<span data-ttu-id="e509c-111">ConferenceMessageCount-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-111">ConferenceMessageCount table in Lync Server 2013</span></span>](lync-server-2013-conferencemessagecount-table.md)

  - [<span data-ttu-id="e509c-112">Konferenz Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-112">Conferences table in Lync Server 2013</span></span>](lync-server-2013-conferences-table.md)

  - [<span data-ttu-id="e509c-113">ConferenceSessionDetails-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-113">ConferenceSessionDetails table in Lync Server 2013</span></span>](lync-server-2013-conferencesessiondetails-table.md)

  - [<span data-ttu-id="e509c-114">ConferenceUris-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-114">ConferenceUris table in Lync Server 2013</span></span>](lync-server-2013-conferenceuris-table.md)

  - [<span data-ttu-id="e509c-115">ContentTypes-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-115">ContentTypes table in Lync Server 2013</span></span>](lync-server-2013-contenttypes-table.md)

  - [<span data-ttu-id="e509c-116">Deregistertype-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-116">DeRegisterType table in Lync Server 2013</span></span>](lync-server-2013-deregistertype-table.md)

  - [<span data-ttu-id="e509c-117">Devices-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-117">Devices table in Lync Server 2013</span></span>](lync-server-2013-devices-table.md)

  - [<span data-ttu-id="e509c-118">Dialogfelder (Tabelle) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-118">Dialogs table in Lync Server 2013</span></span>](lync-server-2013-dialogs-table.md)

  - [<span data-ttu-id="e509c-119">EdgeServers-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-119">EdgeServers table in Lync Server 2013</span></span>](lync-server-2013-edgeservers-table.md)

  - [<span data-ttu-id="e509c-120">ErrorCategory-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-120">ErrorCategory table in Lync Server 2013</span></span>](lync-server-2013-errorcategory-table.md)

  - [<span data-ttu-id="e509c-121">ErrorDef-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-121">ErrorDef table in Lync Server 2013</span></span>](lync-server-2013-errordef-table.md)

  - [<span data-ttu-id="e509c-122">ErrorReport-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-122">ErrorReport table in Lync Server 2013</span></span>](lync-server-2013-errorreport-table.md)

  - [<span data-ttu-id="e509c-123">Filetransfers-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-123">FileTransfers table in Lync Server 2013</span></span>](lync-server-2013-filetransfers-table.md)

  - [<span data-ttu-id="e509c-124">FocusJoinsAndLeaves-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-124">FocusJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-focusjoinsandleaves-table.md)

  - [<span data-ttu-id="e509c-125">Frontend-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-125">FrontEnd table in Lync Server 2013</span></span>](lync-server-2013-frontend-table.md)

  - [<span data-ttu-id="e509c-126">Gateways-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-126">Gateways table in Lync Server 2013</span></span>](lync-server-2013-gateways-table.md)

  - [<span data-ttu-id="e509c-127">Hardware Versions-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-127">HardwareVersions table in Lync Server 2013</span></span>](lync-server-2013-hardwareversions-table.md)

  - [<span data-ttu-id="e509c-128">IMReportSummary-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-128">IMReportSummary table in Lync Server 2013</span></span>](lync-server-2013-imreportsummary-table.md)

  - [<span data-ttu-id="e509c-129">Tabelle "Locations" in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-129">Locations table in Lync Server 2013</span></span>](lync-server-2013-locations-table.md)

  - [<span data-ttu-id="e509c-130">Herstellertabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-130">Manufacturers table in Lync Server 2013</span></span>](lync-server-2013-manufacturers-table.md)

  - [<span data-ttu-id="e509c-131">McuJoinsAndLeaves-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-131">McuJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-mcujoinsandleaves-table.md)

  - [<span data-ttu-id="e509c-132">Tabelle "MCU" in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-132">Mcus table in Lync Server 2013</span></span>](lync-server-2013-mcus-table.md)

  - [<span data-ttu-id="e509c-133">Medientabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-133">Media table in Lync Server 2013</span></span>](lync-server-2013-media-table.md)

  - [<span data-ttu-id="e509c-134">Medialist-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-134">MediaList table in Lync Server 2013</span></span>](lync-server-2013-medialist-table.md)

  - [<span data-ttu-id="e509c-135">MediationServers-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-135">MediationServers table in Lync Server 2013</span></span>](lync-server-2013-mediationservers-table.md)

  - [<span data-ttu-id="e509c-136">MSMQProcessing-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-136">MSMQProcessing table in Lync Server 2013</span></span>](lync-server-2013-msmqprocessing-table.md)

  - [<span data-ttu-id="e509c-137">Phones-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-137">Phones table in Lync Server 2013</span></span>](lync-server-2013-phones-table.md)

  - [<span data-ttu-id="e509c-138">Tabelle "Pools" in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-138">Pools table in Lync Server 2013</span></span>](lync-server-2013-pools-table.md)

  - [<span data-ttu-id="e509c-139">ProgressReport-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-139">ProgressReport table in Lync Server 2013</span></span>](lync-server-2013-progressreport-table.md)

  - [<span data-ttu-id="e509c-140">PurgeSettings-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-140">PurgeSettings table in Lync Server 2013</span></span>](lync-server-2013-purgesettings-table.md)

  - [<span data-ttu-id="e509c-141">Registrierungstabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-141">Registration table in Lync Server 2013</span></span>](lync-server-2013-registration-table.md)

  - [<span data-ttu-id="e509c-142">Tabelle "Roles" in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-142">Roles table in Lync Server 2013</span></span>](lync-server-2013-roles-table.md)

  - [<span data-ttu-id="e509c-143">Server-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-143">Servers table in Lync Server 2013</span></span>](lync-server-2013-servers-table.md)

  - [<span data-ttu-id="e509c-144">SessionDetails-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-144">SessionDetails table in Lync Server 2013</span></span>](lync-server-2013-sessiondetails-table.md)

  - [<span data-ttu-id="e509c-145">SIPResponseMetaData-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-145">SIPResponseMetaData table in Lync Server 2013</span></span>](lync-server-2013-sipresponsemetadata-table.md)

  - [<span data-ttu-id="e509c-146">Tabelle "Syndikator" in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-146">Syndicators table in Lync Server 2013</span></span>](lync-server-2013-syndicators-table.md)

  - [<span data-ttu-id="e509c-147">SyndicatorsTenantMap-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-147">SyndicatorsTenantMap table in Lync Server 2013</span></span>](lync-server-2013-syndicatorstenantmap-table.md)

  - [<span data-ttu-id="e509c-148">Vorgangstabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-148">Task table in Lync Server 2013</span></span>](lync-server-2013-task-table.md)

  - [<span data-ttu-id="e509c-149">Tabelle "Mandanten" in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-149">Tenants table in Lync Server 2013</span></span>](lync-server-2013-tenants-table.md)

  - [<span data-ttu-id="e509c-150">UriTypes-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-150">UriTypes table in Lync Server 2013</span></span>](lync-server-2013-uritypes-table.md)

  - [<span data-ttu-id="e509c-151">Tabelle "Users" in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-151">Users table in Lync Server 2013</span></span>](lync-server-2013-users-table.md)

  - [<span data-ttu-id="e509c-152">UserAgentDef-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-152">UserAgentDef table in Lync Server 2013</span></span>](lync-server-2013-useragentdef-table.md)

  - [<span data-ttu-id="e509c-153">UserStatistics-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-153">UserStatistics table in Lync Server 2013</span></span>](lync-server-2013-userstatistics-table.md)

  - [<span data-ttu-id="e509c-154">VoipDetails-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e509c-154">VoipDetails table in Lync Server 2013</span></span>](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

