---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList ist die Liste der registrierten Add-Ins, die Knoten zugeordnet werden können.
ms.openlocfilehash: 3277ec3a2d4fe11000b2eda60fa2327547c77d2b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295174"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="263a2-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="263a2-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="263a2-104">tblSiopWhiteList ist die Liste der registrierten Add-Ins, die Knoten zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="263a2-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="263a2-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="263a2-105">**Columns**</span></span>

|<span data-ttu-id="263a2-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="263a2-106">**Column**</span></span>|<span data-ttu-id="263a2-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="263a2-107">**Type**</span></span>|<span data-ttu-id="263a2-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="263a2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="263a2-109">siopID</span><span class="sxs-lookup"><span data-stu-id="263a2-109">siopID</span></span>  <br/> |<span data-ttu-id="263a2-110">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="263a2-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="263a2-111">GUID des Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="263a2-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="263a2-112">siopName</span><span class="sxs-lookup"><span data-stu-id="263a2-112">siopName</span></span>  <br/> |<span data-ttu-id="263a2-113">nvarchar (50); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="263a2-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="263a2-114">Anzeigename des Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="263a2-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="263a2-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="263a2-115">siopUrl</span></span>  <br/> |<span data-ttu-id="263a2-116">nvarchar (255); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="263a2-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="263a2-117">Die URL des Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="263a2-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="263a2-118">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="263a2-118">**Key**</span></span>

|<span data-ttu-id="263a2-119">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="263a2-119">**Column**</span></span>|<span data-ttu-id="263a2-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="263a2-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="263a2-121">siopID</span><span class="sxs-lookup"><span data-stu-id="263a2-121">siopID</span></span>  <br/> |<span data-ttu-id="263a2-122">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="263a2-122">Primary key.</span></span>  <br/> |
   

