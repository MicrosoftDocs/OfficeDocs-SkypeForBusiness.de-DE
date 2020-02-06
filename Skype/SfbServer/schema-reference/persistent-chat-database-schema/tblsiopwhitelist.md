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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList ist die Liste der registrierten Add-Ins, die Knoten zugeordnet werden können.
ms.openlocfilehash: ae287a1a32b09ce309c688dac2a042913383a263
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812113"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="3c281-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="3c281-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="3c281-104">tblSiopWhiteList ist die Liste der registrierten Add-Ins, die Knoten zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="3c281-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="3c281-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="3c281-105">**Columns**</span></span>

|<span data-ttu-id="3c281-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="3c281-106">**Column**</span></span>|<span data-ttu-id="3c281-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="3c281-107">**Type**</span></span>|<span data-ttu-id="3c281-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="3c281-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3c281-109">siopID</span><span class="sxs-lookup"><span data-stu-id="3c281-109">siopID</span></span>  <br/> |<span data-ttu-id="3c281-110">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="3c281-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="3c281-111">GUID des Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="3c281-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="3c281-112">siopName</span><span class="sxs-lookup"><span data-stu-id="3c281-112">siopName</span></span>  <br/> |<span data-ttu-id="3c281-113">nvarchar (50); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="3c281-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="3c281-114">Anzeigename des Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="3c281-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="3c281-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="3c281-115">siopUrl</span></span>  <br/> |<span data-ttu-id="3c281-116">nvarchar (255); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="3c281-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="3c281-117">Die URL des Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="3c281-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="3c281-118">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="3c281-118">**Key**</span></span>

|<span data-ttu-id="3c281-119">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="3c281-119">**Column**</span></span>|<span data-ttu-id="3c281-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="3c281-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3c281-121">siopID</span><span class="sxs-lookup"><span data-stu-id="3c281-121">siopID</span></span>  <br/> |<span data-ttu-id="3c281-122">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="3c281-122">Primary key.</span></span>  <br/> |
   

