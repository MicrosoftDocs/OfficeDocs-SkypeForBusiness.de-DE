---
title: 'Lync Server 2013: Ausführliche Informationen zur Tabelle für den Server für beständigen Chat'
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
ms.openlocfilehash: cd738a423744257968eb029abdd29e5964c0c623
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-table-details-in-lync-server-2013"></a><span data-ttu-id="0929e-102">Ausführliche Informationen zur Tabelle für den Server für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-102">Persistent Chat Server table details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0929e-103">_**Letztes Änderungsdatum des Themas:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="0929e-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="0929e-104">In den folgenden Themen werden die Spalten in den Schema Tabellen für persistente Chat-Datenbanken detailliert beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0929e-104">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0929e-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0929e-105">In This Section</span></span>

  - [<span data-ttu-id="0929e-106">tblADCookie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-106">tblADCookie in Lync Server 2013</span></span>](lync-server-2013-tbladcookie.md)

  - [<span data-ttu-id="0929e-107">tblPrincipalMemberDifference in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-107">tblPrincipalMemberDifference in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmemberdifference.md)

  - [<span data-ttu-id="0929e-108">tblADUpdates in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-108">tblADUpdates in Lync Server 2013</span></span>](lync-server-2013-tbladupdates.md)

  - [<span data-ttu-id="0929e-109">tblPrincipalMembers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-109">tblPrincipalMembers in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmembers.md)

  - [<span data-ttu-id="0929e-110">tblPrincipalMeta in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-110">tblPrincipalMeta in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmeta.md)

  - [<span data-ttu-id="0929e-111">tblSkippedAffiliations in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-111">tblSkippedAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblskippedaffiliations.md)

  - [<span data-ttu-id="0929e-112">tblPrincipalType in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-112">tblPrincipalType in Lync Server 2013</span></span>](lync-server-2013-tblprincipaltype.md)

  - [<span data-ttu-id="0929e-113">tblPrincipal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-113">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)

  - [<span data-ttu-id="0929e-114">tblPrincipalAffiliations in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-114">tblPrincipalAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblprincipalaffiliations.md)

  - [<span data-ttu-id="0929e-115">tblNode in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-115">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)

  - [<span data-ttu-id="0929e-116">tblRoleType in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-116">tblRoleType in Lync Server 2013</span></span>](lync-server-2013-tblroletype.md)

  - [<span data-ttu-id="0929e-117">tblScopePrincipal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-117">tblScopePrincipal in Lync Server 2013</span></span>](lync-server-2013-tblscopeprincipal.md)

  - [<span data-ttu-id="0929e-118">tblPrincipalRole in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-118">tblPrincipalRole in Lync Server 2013</span></span>](lync-server-2013-tblprincipalrole.md)

  - [<span data-ttu-id="0929e-119">tblSiopWhiteList in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-119">tblSiopWhiteList in Lync Server 2013</span></span>](lync-server-2013-tblsiopwhitelist.md)

  - [<span data-ttu-id="0929e-120">tblEnumAttribute in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-120">tblEnumAttribute in Lync Server 2013</span></span>](lync-server-2013-tblenumattribute.md)

  - [<span data-ttu-id="0929e-121">tblEnumValue in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-121">tblEnumValue in Lync Server 2013</span></span>](lync-server-2013-tblenumvalue.md)

  - [<span data-ttu-id="0929e-122">tblPrincipalInvites in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-122">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)

  - [<span data-ttu-id="0929e-123">tblChat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)

  - [<span data-ttu-id="0929e-124">tblLastInviteId in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-124">tblLastInviteId in Lync Server 2013</span></span>](lync-server-2013-tbllastinviteid.md)

  - [<span data-ttu-id="0929e-125">tblLastChatId in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-125">tblLastChatId in Lync Server 2013</span></span>](lync-server-2013-tbllastchatid.md)

  - [<span data-ttu-id="0929e-126">tblPreference in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-126">tblPreference in Lync Server 2013</span></span>](lync-server-2013-tblpreference.md)

  - [<span data-ttu-id="0929e-127">tblFileToken in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-127">tblFileToken in Lync Server 2013</span></span>](lync-server-2013-tblfiletoken.md)

  - [<span data-ttu-id="0929e-128">tblServerIdentity in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-128">tblServerIdentity in Lync Server 2013</span></span>](lync-server-2013-tblserveridentity.md)

  - [<span data-ttu-id="0929e-129">tblAdminLock in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-129">tblAdminLock in Lync Server 2013</span></span>](lync-server-2013-tbladminlock.md)

  - [<span data-ttu-id="0929e-130">tblSystemRevision in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-130">tblSystemRevision in Lync Server 2013</span></span>](lync-server-2013-tblsystemrevision.md)

  - [<span data-ttu-id="0929e-131">tblActivePeers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-131">tblActivePeers in Lync Server 2013</span></span>](lync-server-2013-tblactivepeers.md)

  - [<span data-ttu-id="0929e-132">tblConfig in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-132">tblConfig in Lync Server 2013</span></span>](lync-server-2013-tblconfig.md)

  - [<span data-ttu-id="0929e-133">tblComplianceData in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-133">tblComplianceData in Lync Server 2013</span></span>](lync-server-2013-tblcompliancedata.md)

  - [<span data-ttu-id="0929e-134">tblComplianceFanout in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-134">tblComplianceFanout in Lync Server 2013</span></span>](lync-server-2013-tblcompliancefanout.md)

  - [<span data-ttu-id="0929e-135">tblComplianceParticipant in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-135">tblComplianceParticipant in Lync Server 2013</span></span>](lync-server-2013-tblcomplianceparticipant.md)

  - [<span data-ttu-id="0929e-136">tblComplianceState in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0929e-136">tblComplianceState in Lync Server 2013</span></span>](lync-server-2013-tblcompliancestate.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

