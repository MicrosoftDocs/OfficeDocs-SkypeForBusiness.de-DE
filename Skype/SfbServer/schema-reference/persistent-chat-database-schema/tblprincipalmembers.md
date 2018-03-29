---
title: "\"tblprincipalmembers\""
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: "\"tblprincipalmembers\" enthält prinzipalmitgliedschaften."
ms.openlocfilehash: 77151cc245b90fa22d9da426a1448c49866dccc2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="d7b28-103">"tblprincipalmembers"</span><span class="sxs-lookup"><span data-stu-id="d7b28-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="d7b28-104">"tblprincipalmembers" enthält prinzipalmitgliedschaften.</span><span class="sxs-lookup"><span data-stu-id="d7b28-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="d7b28-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="d7b28-105">**Columns**</span></span>

|<span data-ttu-id="d7b28-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="d7b28-106">**Column**</span></span>|<span data-ttu-id="d7b28-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="d7b28-107">**Type**</span></span>|<span data-ttu-id="d7b28-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d7b28-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d7b28-109">prinID</span><span class="sxs-lookup"><span data-stu-id="d7b28-109">prinID</span></span>  <br/> |<span data-ttu-id="d7b28-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="d7b28-110">int, not null</span></span>  <br/> |<span data-ttu-id="d7b28-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="d7b28-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="d7b28-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="d7b28-112">memberADPath</span></span>  <br/> |<span data-ttu-id="d7b28-113">Nvarchar (384), nicht null</span><span class="sxs-lookup"><span data-stu-id="d7b28-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="d7b28-114">Distinguished Name eines Elements.</span><span class="sxs-lookup"><span data-stu-id="d7b28-114">Distinguished name of a member.</span></span> <span data-ttu-id="d7b28-115">Ein Element hat keinen zu einem Prinzipal (in der TblPrincipal-Tabelle).</span><span class="sxs-lookup"><span data-stu-id="d7b28-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="d7b28-116">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d7b28-116">**Keys**</span></span>

|<span data-ttu-id="d7b28-117">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="d7b28-117">**Column**</span></span>|<span data-ttu-id="d7b28-118">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d7b28-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d7b28-119">\<PrinID memberADPath\></span><span class="sxs-lookup"><span data-stu-id="d7b28-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="d7b28-120">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="d7b28-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="d7b28-121">prinID</span><span class="sxs-lookup"><span data-stu-id="d7b28-121">prinID</span></span>  <br/> |<span data-ttu-id="d7b28-122">Fremdschlüssel mit Abfrage von tblprincipal.prinid.</span><span class="sxs-lookup"><span data-stu-id="d7b28-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

