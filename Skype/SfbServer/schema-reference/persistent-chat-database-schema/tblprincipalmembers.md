---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers enthält Prinzipal Mitgliedschaften.
ms.openlocfilehash: 12c3bf86b7416665f0f2355af0bfc9f98e3c1f1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295286"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="b12d8-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="b12d8-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="b12d8-104">tblPrincipalMembers enthält Prinzipal Mitgliedschaften.</span><span class="sxs-lookup"><span data-stu-id="b12d8-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="b12d8-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="b12d8-105">**Columns**</span></span>

|<span data-ttu-id="b12d8-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="b12d8-106">**Column**</span></span>|<span data-ttu-id="b12d8-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="b12d8-107">**Type**</span></span>|<span data-ttu-id="b12d8-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b12d8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b12d8-109">prinID</span><span class="sxs-lookup"><span data-stu-id="b12d8-109">prinID</span></span>  <br/> |<span data-ttu-id="b12d8-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="b12d8-110">int, not null</span></span>  <br/> |<span data-ttu-id="b12d8-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="b12d8-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="b12d8-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="b12d8-112">memberADPath</span></span>  <br/> |<span data-ttu-id="b12d8-113">nvarchar (384); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="b12d8-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="b12d8-114">Distinguished Name eines Members.</span><span class="sxs-lookup"><span data-stu-id="b12d8-114">Distinguished name of a member.</span></span> <span data-ttu-id="b12d8-115">Ein Mitglied muss kein Prinzipal sein (in der tblPrincipal-Tabelle).</span><span class="sxs-lookup"><span data-stu-id="b12d8-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="b12d8-116">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="b12d8-116">**Keys**</span></span>

|<span data-ttu-id="b12d8-117">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="b12d8-117">**Column**</span></span>|<span data-ttu-id="b12d8-118">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b12d8-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b12d8-119">\<prinID, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="b12d8-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="b12d8-120">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="b12d8-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="b12d8-121">prinID</span><span class="sxs-lookup"><span data-stu-id="b12d8-121">prinID</span></span>  <br/> |<span data-ttu-id="b12d8-122">Fremdschlüssel mit Lookup in tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="b12d8-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

