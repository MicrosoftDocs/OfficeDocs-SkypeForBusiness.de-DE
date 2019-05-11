---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: TblConfig enthält einige Persistent Chat Server nicht unterstützte Konfiguration in einer Zeile.
ms.openlocfilehash: 79cd7e2303210bb07f35fa2c6b7ecc5c86b7e8cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930022"
---
# <a name="tblconfig"></a><span data-ttu-id="1f81e-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="1f81e-103">tblConfig</span></span>
 
<span data-ttu-id="1f81e-104">TblConfig enthält einige Persistent Chat Server nicht unterstützte Konfiguration in einer Zeile.</span><span class="sxs-lookup"><span data-stu-id="1f81e-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="1f81e-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="1f81e-105">**Columns**</span></span>

|<span data-ttu-id="1f81e-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="1f81e-106">**Column**</span></span>|<span data-ttu-id="1f81e-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="1f81e-107">**Type**</span></span>|<span data-ttu-id="1f81e-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1f81e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1f81e-109">Stellen configLabel</span><span class="sxs-lookup"><span data-stu-id="1f81e-109">configLabel</span></span>  <br/> |<span data-ttu-id="1f81e-110">Nvarchar (255), nicht null</span><span class="sxs-lookup"><span data-stu-id="1f81e-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="1f81e-111">Enthält "Pool".</span><span class="sxs-lookup"><span data-stu-id="1f81e-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="1f81e-112">configContent</span><span class="sxs-lookup"><span data-stu-id="1f81e-112">configContent</span></span>  <br/> |<span data-ttu-id="1f81e-113">Nvarchar (Max.)</span><span class="sxs-lookup"><span data-stu-id="1f81e-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="1f81e-114">Inhalt der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="1f81e-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="1f81e-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="1f81e-115">configPoolID</span></span>  <br/> |<span data-ttu-id="1f81e-116">GUID, nicht null</span><span class="sxs-lookup"><span data-stu-id="1f81e-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="1f81e-117">Eindeutige ID der Datenbankinstanz.</span><span class="sxs-lookup"><span data-stu-id="1f81e-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="1f81e-118">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="1f81e-118">**Key**</span></span>

|<span data-ttu-id="1f81e-119">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="1f81e-119">**Column**</span></span>|<span data-ttu-id="1f81e-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1f81e-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1f81e-121">Stellen configLabel</span><span class="sxs-lookup"><span data-stu-id="1f81e-121">configLabel</span></span>  <br/> |<span data-ttu-id="1f81e-122">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="1f81e-122">Primary key.</span></span>  <br/> |
   

