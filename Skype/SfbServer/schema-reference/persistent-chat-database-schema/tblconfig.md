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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213067"
---
# <a name="tblconfig"></a><span data-ttu-id="38af2-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="38af2-103">tblConfig</span></span>
 
<span data-ttu-id="38af2-104">TblConfig enthält einige Persistent Chat Server nicht unterstützte Konfiguration in einer Zeile.</span><span class="sxs-lookup"><span data-stu-id="38af2-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="38af2-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="38af2-105">**Columns**</span></span>

|<span data-ttu-id="38af2-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="38af2-106">**Column**</span></span>|<span data-ttu-id="38af2-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="38af2-107">**Type**</span></span>|<span data-ttu-id="38af2-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="38af2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="38af2-109">Stellen configLabel</span><span class="sxs-lookup"><span data-stu-id="38af2-109">configLabel</span></span>  <br/> |<span data-ttu-id="38af2-110">Nvarchar (255), nicht null</span><span class="sxs-lookup"><span data-stu-id="38af2-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="38af2-111">Enthält "Pool".</span><span class="sxs-lookup"><span data-stu-id="38af2-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="38af2-112">configContent</span><span class="sxs-lookup"><span data-stu-id="38af2-112">configContent</span></span>  <br/> |<span data-ttu-id="38af2-113">Nvarchar (Max.)</span><span class="sxs-lookup"><span data-stu-id="38af2-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="38af2-114">Inhalt der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="38af2-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="38af2-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="38af2-115">configPoolID</span></span>  <br/> |<span data-ttu-id="38af2-116">GUID, nicht null</span><span class="sxs-lookup"><span data-stu-id="38af2-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="38af2-117">Eindeutige ID der Datenbankinstanz.</span><span class="sxs-lookup"><span data-stu-id="38af2-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="38af2-118">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="38af2-118">**Key**</span></span>

|<span data-ttu-id="38af2-119">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="38af2-119">**Column**</span></span>|<span data-ttu-id="38af2-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="38af2-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="38af2-121">Stellen configLabel</span><span class="sxs-lookup"><span data-stu-id="38af2-121">configLabel</span></span>  <br/> |<span data-ttu-id="38af2-122">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="38af2-122">Primary key.</span></span>  <br/> |
   

