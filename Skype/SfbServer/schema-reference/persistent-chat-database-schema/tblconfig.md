---
title: tblConfig
ms.reviewer: ''
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
ms.openlocfilehash: 9d28c0506b905975e2a72eeb83605fe4e32e7cfd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898937"
---
# <a name="tblconfig"></a><span data-ttu-id="499c1-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="499c1-103">tblConfig</span></span>
 
<span data-ttu-id="499c1-104">TblConfig enthält einige Persistent Chat Server nicht unterstützte Konfiguration in einer Zeile.</span><span class="sxs-lookup"><span data-stu-id="499c1-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="499c1-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="499c1-105">**Columns**</span></span>

|<span data-ttu-id="499c1-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="499c1-106">**Column**</span></span>|<span data-ttu-id="499c1-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="499c1-107">**Type**</span></span>|<span data-ttu-id="499c1-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="499c1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="499c1-109">Stellen configLabel</span><span class="sxs-lookup"><span data-stu-id="499c1-109">configLabel</span></span>  <br/> |<span data-ttu-id="499c1-110">Nvarchar (255), nicht null</span><span class="sxs-lookup"><span data-stu-id="499c1-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="499c1-111">Enthält "Pool".</span><span class="sxs-lookup"><span data-stu-id="499c1-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="499c1-112">configContent</span><span class="sxs-lookup"><span data-stu-id="499c1-112">configContent</span></span>  <br/> |<span data-ttu-id="499c1-113">Nvarchar (Max.)</span><span class="sxs-lookup"><span data-stu-id="499c1-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="499c1-114">Inhalt der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="499c1-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="499c1-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="499c1-115">configPoolID</span></span>  <br/> |<span data-ttu-id="499c1-116">GUID, nicht null</span><span class="sxs-lookup"><span data-stu-id="499c1-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="499c1-117">Eindeutige ID der Datenbankinstanz.</span><span class="sxs-lookup"><span data-stu-id="499c1-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="499c1-118">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="499c1-118">**Key**</span></span>

|<span data-ttu-id="499c1-119">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="499c1-119">**Column**</span></span>|<span data-ttu-id="499c1-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="499c1-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="499c1-121">Stellen configLabel</span><span class="sxs-lookup"><span data-stu-id="499c1-121">configLabel</span></span>  <br/> |<span data-ttu-id="499c1-122">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="499c1-122">Primary key.</span></span>  <br/> |
   

