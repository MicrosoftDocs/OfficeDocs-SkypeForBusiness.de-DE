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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers enthält Prinzipal Mitgliedschaften.
ms.openlocfilehash: c56ab16f96322cb295c4eff6fc63e01ba887dd22
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813943"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="7e57c-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="7e57c-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="7e57c-104">tblPrincipalMembers enthält Prinzipal Mitgliedschaften.</span><span class="sxs-lookup"><span data-stu-id="7e57c-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="7e57c-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="7e57c-105">**Columns**</span></span>

|<span data-ttu-id="7e57c-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="7e57c-106">**Column**</span></span>|<span data-ttu-id="7e57c-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="7e57c-107">**Type**</span></span>|<span data-ttu-id="7e57c-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="7e57c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7e57c-109">prinID</span><span class="sxs-lookup"><span data-stu-id="7e57c-109">prinID</span></span>  <br/> |<span data-ttu-id="7e57c-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7e57c-110">int, not null</span></span>  <br/> |<span data-ttu-id="7e57c-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="7e57c-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="7e57c-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="7e57c-112">memberADPath</span></span>  <br/> |<span data-ttu-id="7e57c-113">nvarchar (384); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7e57c-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="7e57c-114">Distinguished Name eines Members.</span><span class="sxs-lookup"><span data-stu-id="7e57c-114">Distinguished name of a member.</span></span> <span data-ttu-id="7e57c-115">Ein Mitglied muss kein Prinzipal sein (in der tblPrincipal-Tabelle).</span><span class="sxs-lookup"><span data-stu-id="7e57c-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="7e57c-116">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="7e57c-116">**Keys**</span></span>

|<span data-ttu-id="7e57c-117">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="7e57c-117">**Column**</span></span>|<span data-ttu-id="7e57c-118">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="7e57c-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7e57c-119">\<prinID, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="7e57c-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="7e57c-120">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="7e57c-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="7e57c-121">prinID</span><span class="sxs-lookup"><span data-stu-id="7e57c-121">prinID</span></span>  <br/> |<span data-ttu-id="7e57c-122">Fremdschlüssel mit Lookup in tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="7e57c-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

