---
title: tblPrincipalMembers
ms.reviewer: ''
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
ms.openlocfilehash: 2b2b9616c76095ec27178887e69dd482bcf6da92
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212488"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="bf625-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="bf625-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="bf625-104">"tblprincipalmembers" enthält prinzipalmitgliedschaften.</span><span class="sxs-lookup"><span data-stu-id="bf625-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="bf625-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="bf625-105">**Columns**</span></span>

|<span data-ttu-id="bf625-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="bf625-106">**Column**</span></span>|<span data-ttu-id="bf625-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="bf625-107">**Type**</span></span>|<span data-ttu-id="bf625-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="bf625-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bf625-109">prinID</span><span class="sxs-lookup"><span data-stu-id="bf625-109">prinID</span></span>  <br/> |<span data-ttu-id="bf625-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="bf625-110">int, not null</span></span>  <br/> |<span data-ttu-id="bf625-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="bf625-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="bf625-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="bf625-112">memberADPath</span></span>  <br/> |<span data-ttu-id="bf625-113">Nvarchar (384), nicht null</span><span class="sxs-lookup"><span data-stu-id="bf625-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="bf625-114">Distinguished Name eines Elements.</span><span class="sxs-lookup"><span data-stu-id="bf625-114">Distinguished name of a member.</span></span> <span data-ttu-id="bf625-115">Ein Element hat keinen zu einem Prinzipal (in der TblPrincipal-Tabelle).</span><span class="sxs-lookup"><span data-stu-id="bf625-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="bf625-116">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="bf625-116">**Keys**</span></span>

|<span data-ttu-id="bf625-117">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="bf625-117">**Column**</span></span>|<span data-ttu-id="bf625-118">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="bf625-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bf625-119">\<PrinID memberADPath\></span><span class="sxs-lookup"><span data-stu-id="bf625-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="bf625-120">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="bf625-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="bf625-121">prinID</span><span class="sxs-lookup"><span data-stu-id="bf625-121">prinID</span></span>  <br/> |<span data-ttu-id="bf625-122">Fremdschlüssel mit Abfrage von tblprincipal.prinid.</span><span class="sxs-lookup"><span data-stu-id="bf625-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

