---
title: tblConfig
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: TblConfig enthält einige Persistent Chat Server nicht unterstützte Konfiguration in einer Zeile.
ms.openlocfilehash: 099060f0957ae21c14b285eac1b753ad0b8c1719
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblconfig"></a><span data-ttu-id="a20f1-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="a20f1-103">tblConfig</span></span>
 
<span data-ttu-id="a20f1-104">TblConfig enthält einige Persistent Chat Server nicht unterstützte Konfiguration in einer Zeile.</span><span class="sxs-lookup"><span data-stu-id="a20f1-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="a20f1-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="a20f1-105">**Columns**</span></span>

|<span data-ttu-id="a20f1-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="a20f1-106">**Column**</span></span>|<span data-ttu-id="a20f1-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="a20f1-107">**Type**</span></span>|<span data-ttu-id="a20f1-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a20f1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a20f1-109">Stellen configLabel</span><span class="sxs-lookup"><span data-stu-id="a20f1-109">configLabel</span></span>  <br/> |<span data-ttu-id="a20f1-110">Nvarchar (255), nicht null</span><span class="sxs-lookup"><span data-stu-id="a20f1-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="a20f1-111">Enthält "Pool".</span><span class="sxs-lookup"><span data-stu-id="a20f1-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="a20f1-112">configContent</span><span class="sxs-lookup"><span data-stu-id="a20f1-112">configContent</span></span>  <br/> |<span data-ttu-id="a20f1-113">Nvarchar (Max.)</span><span class="sxs-lookup"><span data-stu-id="a20f1-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="a20f1-114">Inhalt der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="a20f1-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="a20f1-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="a20f1-115">configPoolID</span></span>  <br/> |<span data-ttu-id="a20f1-116">GUID, nicht null</span><span class="sxs-lookup"><span data-stu-id="a20f1-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="a20f1-117">Eindeutige ID der Datenbankinstanz.</span><span class="sxs-lookup"><span data-stu-id="a20f1-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="a20f1-118">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="a20f1-118">**Key**</span></span>

|<span data-ttu-id="a20f1-119">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="a20f1-119">**Column**</span></span>|<span data-ttu-id="a20f1-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a20f1-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a20f1-121">Stellen configLabel</span><span class="sxs-lookup"><span data-stu-id="a20f1-121">configLabel</span></span>  <br/> |<span data-ttu-id="a20f1-122">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="a20f1-122">Primary key.</span></span>  <br/> |
   

