---
title: 'Lync Server 2013: Tabellendetails für persistent Chat Server'
description: 'Lync Server 2013: Tabellendetails für persistent Chat Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server table details
ms:assetid: c22d4a76-da50-49de-9038-e0ed7b8e1b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615034(v=OCS.15)
ms:contentKeyID: 48185323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a27feaaccf861d537127f06920cf903be5ae000
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545131"
---
# <a name="persistent-chat-server-table-details-in-lync-server-2013"></a><span data-ttu-id="55506-103">Tabellendetails für persistent Chat Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-103">Persistent Chat Server table details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55506-104">_**Letztes Änderungsstand des Themas:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="55506-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="55506-105">In den folgenden Themen werden die Spalten in den einzelnen Datenbankschema Tabellen für beständigen Chat ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="55506-105">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="55506-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="55506-106">In This Section</span></span>

  - [<span data-ttu-id="55506-107">tblADCookie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-107">tblADCookie in Lync Server 2013</span></span>](lync-server-2013-tbladcookie.md)

  - [<span data-ttu-id="55506-108">principalmemberdifference in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-108">tblPrincipalMemberDifference in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmemberdifference.md)

  - [<span data-ttu-id="55506-109">tblADUpdates in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-109">tblADUpdates in Lync Server 2013</span></span>](lync-server-2013-tbladupdates.md)

  - [<span data-ttu-id="55506-110">tblPrincipalMembers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-110">tblPrincipalMembers in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmembers.md)

  - [<span data-ttu-id="55506-111">tblPrincipalMeta in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-111">tblPrincipalMeta in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmeta.md)

  - [<span data-ttu-id="55506-112">tblSkippedAffiliations in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-112">tblSkippedAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblskippedaffiliations.md)

  - [<span data-ttu-id="55506-113">tblPrincipalType in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-113">tblPrincipalType in Lync Server 2013</span></span>](lync-server-2013-tblprincipaltype.md)

  - [<span data-ttu-id="55506-114">tblPrincipal in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-114">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)

  - [<span data-ttu-id="55506-115">tblPrincipalAffiliations in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-115">tblPrincipalAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblprincipalaffiliations.md)

  - [<span data-ttu-id="55506-116">tblNode in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-116">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)

  - [<span data-ttu-id="55506-117">tblRoleType in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-117">tblRoleType in Lync Server 2013</span></span>](lync-server-2013-tblroletype.md)

  - [<span data-ttu-id="55506-118">tblScopePrincipal in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-118">tblScopePrincipal in Lync Server 2013</span></span>](lync-server-2013-tblscopeprincipal.md)

  - [<span data-ttu-id="55506-119">tblPrincipalRole in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-119">tblPrincipalRole in Lync Server 2013</span></span>](lync-server-2013-tblprincipalrole.md)

  - [<span data-ttu-id="55506-120">tblSiopWhiteList in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-120">tblSiopWhiteList in Lync Server 2013</span></span>](lync-server-2013-tblsiopwhitelist.md)

  - [<span data-ttu-id="55506-121">tblEnumAttribute in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-121">tblEnumAttribute in Lync Server 2013</span></span>](lync-server-2013-tblenumattribute.md)

  - [<span data-ttu-id="55506-122">tblEnumValue in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-122">tblEnumValue in Lync Server 2013</span></span>](lync-server-2013-tblenumvalue.md)

  - [<span data-ttu-id="55506-123">tblPrincipalInvites in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-123">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)

  - [<span data-ttu-id="55506-124">tblChat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-124">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)

  - [<span data-ttu-id="55506-125">tblLastInviteId in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-125">tblLastInviteId in Lync Server 2013</span></span>](lync-server-2013-tbllastinviteid.md)

  - [<span data-ttu-id="55506-126">tblLastChatId in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-126">tblLastChatId in Lync Server 2013</span></span>](lync-server-2013-tbllastchatid.md)

  - [<span data-ttu-id="55506-127">tblPreference in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-127">tblPreference in Lync Server 2013</span></span>](lync-server-2013-tblpreference.md)

  - [<span data-ttu-id="55506-128">tblFileToken in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-128">tblFileToken in Lync Server 2013</span></span>](lync-server-2013-tblfiletoken.md)

  - [<span data-ttu-id="55506-129">tblServerIdentity in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-129">tblServerIdentity in Lync Server 2013</span></span>](lync-server-2013-tblserveridentity.md)

  - [<span data-ttu-id="55506-130">adminlock in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-130">tblAdminLock in Lync Server 2013</span></span>](lync-server-2013-tbladminlock.md)

  - [<span data-ttu-id="55506-131">tblSystemRevision in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-131">tblSystemRevision in Lync Server 2013</span></span>](lync-server-2013-tblsystemrevision.md)

  - [<span data-ttu-id="55506-132">tblActivePeers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-132">tblActivePeers in Lync Server 2013</span></span>](lync-server-2013-tblactivepeers.md)

  - [<span data-ttu-id="55506-133">tblConfig in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-133">tblConfig in Lync Server 2013</span></span>](lync-server-2013-tblconfig.md)

  - [<span data-ttu-id="55506-134">tblComplianceData in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-134">tblComplianceData in Lync Server 2013</span></span>](lync-server-2013-tblcompliancedata.md)

  - [<span data-ttu-id="55506-135">tblComplianceFanout in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-135">tblComplianceFanout in Lync Server 2013</span></span>](lync-server-2013-tblcompliancefanout.md)

  - [<span data-ttu-id="55506-136">tblComplianceParticipant in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-136">tblComplianceParticipant in Lync Server 2013</span></span>](lync-server-2013-tblcomplianceparticipant.md)

  - [<span data-ttu-id="55506-137">tblComplianceState in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55506-137">tblComplianceState in Lync Server 2013</span></span>](lync-server-2013-tblcompliancestate.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

