---
title: 'Lync Server 2013: Tabellendetails für persistent Chat Server'
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
ms.openlocfilehash: e103fa03aa747e0c04a680507fe6d57bd6de04d0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-table-details-in-lync-server-2013"></a><span data-ttu-id="1e013-102">Tabellendetails für persistent Chat Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-102">Persistent Chat Server table details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e013-103">_**Letztes Änderungsstand des Themas:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="1e013-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="1e013-104">In den folgenden Themen werden die Spalten in den einzelnen Datenbankschema Tabellen für beständigen Chat ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1e013-104">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1e013-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1e013-105">In This Section</span></span>

  - [<span data-ttu-id="1e013-106">tblADCookie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-106">tblADCookie in Lync Server 2013</span></span>](lync-server-2013-tbladcookie.md)

  - [<span data-ttu-id="1e013-107">principalmemberdifference in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-107">tblPrincipalMemberDifference in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmemberdifference.md)

  - [<span data-ttu-id="1e013-108">tblADUpdates in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-108">tblADUpdates in Lync Server 2013</span></span>](lync-server-2013-tbladupdates.md)

  - [<span data-ttu-id="1e013-109">tblPrincipalMembers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-109">tblPrincipalMembers in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmembers.md)

  - [<span data-ttu-id="1e013-110">tblPrincipalMeta in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-110">tblPrincipalMeta in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmeta.md)

  - [<span data-ttu-id="1e013-111">tblSkippedAffiliations in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-111">tblSkippedAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblskippedaffiliations.md)

  - [<span data-ttu-id="1e013-112">tblPrincipalType in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-112">tblPrincipalType in Lync Server 2013</span></span>](lync-server-2013-tblprincipaltype.md)

  - [<span data-ttu-id="1e013-113">tblPrincipal in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-113">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)

  - [<span data-ttu-id="1e013-114">tblPrincipalAffiliations in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-114">tblPrincipalAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblprincipalaffiliations.md)

  - [<span data-ttu-id="1e013-115">tblNode in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-115">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)

  - [<span data-ttu-id="1e013-116">tblRoleType in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-116">tblRoleType in Lync Server 2013</span></span>](lync-server-2013-tblroletype.md)

  - [<span data-ttu-id="1e013-117">tblScopePrincipal in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-117">tblScopePrincipal in Lync Server 2013</span></span>](lync-server-2013-tblscopeprincipal.md)

  - [<span data-ttu-id="1e013-118">tblPrincipalRole in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-118">tblPrincipalRole in Lync Server 2013</span></span>](lync-server-2013-tblprincipalrole.md)

  - [<span data-ttu-id="1e013-119">tblSiopWhiteList in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-119">tblSiopWhiteList in Lync Server 2013</span></span>](lync-server-2013-tblsiopwhitelist.md)

  - [<span data-ttu-id="1e013-120">tblEnumAttribute in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-120">tblEnumAttribute in Lync Server 2013</span></span>](lync-server-2013-tblenumattribute.md)

  - [<span data-ttu-id="1e013-121">tblEnumValue in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-121">tblEnumValue in Lync Server 2013</span></span>](lync-server-2013-tblenumvalue.md)

  - [<span data-ttu-id="1e013-122">tblPrincipalInvites in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-122">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)

  - [<span data-ttu-id="1e013-123">tblChat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)

  - [<span data-ttu-id="1e013-124">tblLastInviteId in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-124">tblLastInviteId in Lync Server 2013</span></span>](lync-server-2013-tbllastinviteid.md)

  - [<span data-ttu-id="1e013-125">tblLastChatId in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-125">tblLastChatId in Lync Server 2013</span></span>](lync-server-2013-tbllastchatid.md)

  - [<span data-ttu-id="1e013-126">tblPreference in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-126">tblPreference in Lync Server 2013</span></span>](lync-server-2013-tblpreference.md)

  - [<span data-ttu-id="1e013-127">tblFileToken in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-127">tblFileToken in Lync Server 2013</span></span>](lync-server-2013-tblfiletoken.md)

  - [<span data-ttu-id="1e013-128">tblServerIdentity in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-128">tblServerIdentity in Lync Server 2013</span></span>](lync-server-2013-tblserveridentity.md)

  - [<span data-ttu-id="1e013-129">adminlock in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-129">tblAdminLock in Lync Server 2013</span></span>](lync-server-2013-tbladminlock.md)

  - [<span data-ttu-id="1e013-130">tblSystemRevision in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-130">tblSystemRevision in Lync Server 2013</span></span>](lync-server-2013-tblsystemrevision.md)

  - [<span data-ttu-id="1e013-131">tblActivePeers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-131">tblActivePeers in Lync Server 2013</span></span>](lync-server-2013-tblactivepeers.md)

  - [<span data-ttu-id="1e013-132">tblConfig in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-132">tblConfig in Lync Server 2013</span></span>](lync-server-2013-tblconfig.md)

  - [<span data-ttu-id="1e013-133">tblComplianceData in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-133">tblComplianceData in Lync Server 2013</span></span>](lync-server-2013-tblcompliancedata.md)

  - [<span data-ttu-id="1e013-134">tblComplianceFanout in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-134">tblComplianceFanout in Lync Server 2013</span></span>](lync-server-2013-tblcompliancefanout.md)

  - [<span data-ttu-id="1e013-135">tblComplianceParticipant in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-135">tblComplianceParticipant in Lync Server 2013</span></span>](lync-server-2013-tblcomplianceparticipant.md)

  - [<span data-ttu-id="1e013-136">tblComplianceState in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e013-136">tblComplianceState in Lync Server 2013</span></span>](lync-server-2013-tblcompliancestate.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

