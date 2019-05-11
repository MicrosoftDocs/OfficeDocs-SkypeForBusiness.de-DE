---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: "\"tblprincipalmembers\" enthält prinzipalmitgliedschaften."
ms.openlocfilehash: be66ee6124c7b0306583bcb10f7d78b777fcf10c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904160"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="81574-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="81574-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="81574-104">"tblprincipalmembers" enthält prinzipalmitgliedschaften.</span><span class="sxs-lookup"><span data-stu-id="81574-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="81574-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="81574-105">**Columns**</span></span>

|<span data-ttu-id="81574-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="81574-106">**Column**</span></span>|<span data-ttu-id="81574-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="81574-107">**Type**</span></span>|<span data-ttu-id="81574-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="81574-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="81574-109">prinID</span><span class="sxs-lookup"><span data-stu-id="81574-109">prinID</span></span>  <br/> |<span data-ttu-id="81574-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="81574-110">int, not null</span></span>  <br/> |<span data-ttu-id="81574-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="81574-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="81574-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="81574-112">memberADPath</span></span>  <br/> |<span data-ttu-id="81574-113">Nvarchar (384), nicht null</span><span class="sxs-lookup"><span data-stu-id="81574-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="81574-114">Distinguished Name eines Elements.</span><span class="sxs-lookup"><span data-stu-id="81574-114">Distinguished name of a member.</span></span> <span data-ttu-id="81574-115">Ein Element hat keinen zu einem Prinzipal (in der TblPrincipal-Tabelle).</span><span class="sxs-lookup"><span data-stu-id="81574-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="81574-116">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="81574-116">**Keys**</span></span>

|<span data-ttu-id="81574-117">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="81574-117">**Column**</span></span>|<span data-ttu-id="81574-118">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="81574-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="81574-119">\<PrinID memberADPath\></span><span class="sxs-lookup"><span data-stu-id="81574-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="81574-120">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="81574-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="81574-121">prinID</span><span class="sxs-lookup"><span data-stu-id="81574-121">prinID</span></span>  <br/> |<span data-ttu-id="81574-122">Fremdschlüssel mit Abfrage von tblprincipal.prinid.</span><span class="sxs-lookup"><span data-stu-id="81574-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

