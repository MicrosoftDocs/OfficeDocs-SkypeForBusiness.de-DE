---
title: Ausführliche Informationen zur Tabelle für den Server für beständigen Chat
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c22d4a76-da50-49de-9038-e0ed7b8e1b58
description: In den folgenden Themen werden die Spalten den beständigen Chat Database Schema Tabellen.
ms.openlocfilehash: a7dc2f9cc545627630286d6166adf47fbb8c4c57
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-server-table-details"></a><span data-ttu-id="b9449-103">Ausführliche Informationen zur Tabelle für den Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="b9449-103">Persistent Chat Server table details</span></span>
 
<span data-ttu-id="b9449-104">In den folgenden Themen werden die Spalten den beständigen Chat Database Schema Tabellen.</span><span class="sxs-lookup"><span data-stu-id="b9449-104">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="b9449-105">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="b9449-105">In this section</span></span>

- [<span data-ttu-id="b9449-106">"tbladcookie"</span><span class="sxs-lookup"><span data-stu-id="b9449-106">tblADCookie</span></span>](tbladcookie.md)
    
- [<span data-ttu-id="b9449-107">Principalmemberdifference</span><span class="sxs-lookup"><span data-stu-id="b9449-107">tblPrincipalMemberDifference</span></span>](tblprincipalmemberdifference.md)
    
- [<span data-ttu-id="b9449-108">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="b9449-108">tblADUpdates</span></span>](tbladupdates.md)
    
- [<span data-ttu-id="b9449-109">"tblprincipalmembers"</span><span class="sxs-lookup"><span data-stu-id="b9449-109">tblPrincipalMembers</span></span>](tblprincipalmembers.md)
    
- [<span data-ttu-id="b9449-110">"tblprincipalmeta"</span><span class="sxs-lookup"><span data-stu-id="b9449-110">tblPrincipalMeta</span></span>](tblprincipalmeta.md)
    
- [<span data-ttu-id="b9449-111">Skippedaffiliations</span><span class="sxs-lookup"><span data-stu-id="b9449-111">tblSkippedAffiliations</span></span>](tblskippedaffiliations.md)
    
- [<span data-ttu-id="b9449-112">"tblprincipaltype"</span><span class="sxs-lookup"><span data-stu-id="b9449-112">tblPrincipalType</span></span>](tblprincipaltype.md)
    
- [<span data-ttu-id="b9449-113">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="b9449-113">tblPrincipal</span></span>](tblprincipal.md)
    
- [<span data-ttu-id="b9449-114">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="b9449-114">tblPrincipalAffiliations</span></span>](tblprincipalaffiliations.md)
    
- [<span data-ttu-id="b9449-115">tblNode</span><span class="sxs-lookup"><span data-stu-id="b9449-115">tblNode</span></span>](tblnode.md)
    
- [<span data-ttu-id="b9449-116">"tblroletype"</span><span class="sxs-lookup"><span data-stu-id="b9449-116">tblRoleType</span></span>](tblroletype.md)
    
- [<span data-ttu-id="b9449-117">in "tblscopeprincipal"</span><span class="sxs-lookup"><span data-stu-id="b9449-117">tblScopePrincipal</span></span>](tblscopeprincipal.md)
    
- [<span data-ttu-id="b9449-118">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="b9449-118">tblPrincipalRole</span></span>](tblprincipalrole.md)
    
- [<span data-ttu-id="b9449-119">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="b9449-119">tblSiopWhiteList</span></span>](tblsiopwhitelist.md)
    
- [<span data-ttu-id="b9449-120">Enumattribute</span><span class="sxs-lookup"><span data-stu-id="b9449-120">tblEnumAttribute</span></span>](tblenumattribute.md)
    
- [<span data-ttu-id="b9449-121">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="b9449-121">tblEnumValue</span></span>](tblenumvalue.md)
    
- [<span data-ttu-id="b9449-122">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="b9449-122">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
    
- [<span data-ttu-id="b9449-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="b9449-123">tblChat</span></span>](tblchat.md)
    
- [<span data-ttu-id="b9449-124">"tbllastinviteid"</span><span class="sxs-lookup"><span data-stu-id="b9449-124">tblLastInviteId</span></span>](tbllastinviteid.md)
    
- [<span data-ttu-id="b9449-125">"lastchatid"</span><span class="sxs-lookup"><span data-stu-id="b9449-125">tblLastChatId</span></span>](tbllastchatid.md)
    
- [<span data-ttu-id="b9449-126">tblPreference</span><span class="sxs-lookup"><span data-stu-id="b9449-126">tblPreference</span></span>](tblpreference.md)
    
- [<span data-ttu-id="b9449-127">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="b9449-127">tblFileToken</span></span>](tblfiletoken.md)
    
- [<span data-ttu-id="b9449-128">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="b9449-128">tblServerIdentity</span></span>](tblserveridentity.md)
    
- [<span data-ttu-id="b9449-129">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="b9449-129">tblAdminLock</span></span>](tbladminlock.md)
    
- [<span data-ttu-id="b9449-130">"tblsystemrevision"</span><span class="sxs-lookup"><span data-stu-id="b9449-130">tblSystemRevision</span></span>](tblsystemrevision.md)
    
- [<span data-ttu-id="b9449-131">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="b9449-131">tblActivePeers</span></span>](tblactivepeers.md)
    
- [<span data-ttu-id="b9449-132">tblConfig</span><span class="sxs-lookup"><span data-stu-id="b9449-132">tblConfig</span></span>](tblconfig.md)
    
- [<span data-ttu-id="b9449-133">"tblcompliancedata"</span><span class="sxs-lookup"><span data-stu-id="b9449-133">tblComplianceData</span></span>](tblcompliancedata.md)
    
- [<span data-ttu-id="b9449-134">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="b9449-134">tblComplianceFanout</span></span>](tblcompliancefanout.md)
    
- [<span data-ttu-id="b9449-135">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="b9449-135">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md)
    
- [<span data-ttu-id="b9449-136">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="b9449-136">tblComplianceState</span></span>](tblcompliancestate.md)
    

