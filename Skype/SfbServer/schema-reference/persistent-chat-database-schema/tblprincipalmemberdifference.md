---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference enthält Gruppenmitgliedschaftsänderungen (sowohl hinzugefügte als auch entfernte Mitglieder), die noch nicht von den späteren Synchronisierungs Schritten von Active Directory-Domänendiensten verarbeitet wurden.
ms.openlocfilehash: 18d0f3f5c8700db0bb81470f5ee90851e8d277ad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295300"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="88704-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="88704-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="88704-104">tblPrincipalMemberDifference enthält Gruppenmitgliedschaftsänderungen (sowohl hinzugefügte als auch entfernte Mitglieder), die noch nicht von den späteren Synchronisierungs Schritten von Active Directory-Domänendiensten verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="88704-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="88704-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="88704-105">**Columns**</span></span>

|<span data-ttu-id="88704-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="88704-106">**Column**</span></span>|<span data-ttu-id="88704-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="88704-107">**Type**</span></span>|<span data-ttu-id="88704-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="88704-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="88704-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="88704-109">prinGuid</span></span>  <br/> |<span data-ttu-id="88704-110">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="88704-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="88704-111">Prinzipal-GUID der geänderten Gruppe.</span><span class="sxs-lookup"><span data-stu-id="88704-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="88704-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="88704-112">memberADPath</span></span>  <br/> |<span data-ttu-id="88704-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="88704-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="88704-114">Distinguished Name des Members.</span><span class="sxs-lookup"><span data-stu-id="88704-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="88704-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="88704-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="88704-116">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="88704-116">bit, not null</span></span>  <br/> |<span data-ttu-id="88704-117">False, wenn das Mitglied hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="88704-117">False if the member was added.</span></span> <span data-ttu-id="88704-118">"True", wenn das Element entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="88704-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="88704-119">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="88704-119">**Key**</span></span>

|<span data-ttu-id="88704-120">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="88704-120">**Column**</span></span>|<span data-ttu-id="88704-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="88704-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="88704-122">\<prinGuid, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="88704-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="88704-123">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="88704-123">Primary key.</span></span>  <br/> |
   

