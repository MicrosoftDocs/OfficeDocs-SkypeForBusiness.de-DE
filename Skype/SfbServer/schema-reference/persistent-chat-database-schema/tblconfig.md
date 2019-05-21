---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig enthält eine nicht unterstützte Konfiguration für beständigen Chat Server in einer Zeile.
ms.openlocfilehash: 244eebcb88c67b521022f9d64888678f221d2369
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295454"
---
# <a name="tblconfig"></a><span data-ttu-id="d4216-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="d4216-103">tblConfig</span></span>
 
<span data-ttu-id="d4216-104">tblConfig enthält eine nicht unterstützte Konfiguration für beständigen Chat Server in einer Zeile.</span><span class="sxs-lookup"><span data-stu-id="d4216-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="d4216-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="d4216-105">**Columns**</span></span>

|<span data-ttu-id="d4216-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="d4216-106">**Column**</span></span>|<span data-ttu-id="d4216-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="d4216-107">**Type**</span></span>|<span data-ttu-id="d4216-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d4216-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d4216-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="d4216-109">configLabel</span></span>  <br/> |<span data-ttu-id="d4216-110">nvarchar (255); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="d4216-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="d4216-111">Enthält "Pool".</span><span class="sxs-lookup"><span data-stu-id="d4216-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="d4216-112">configContent</span><span class="sxs-lookup"><span data-stu-id="d4216-112">configContent</span></span>  <br/> |<span data-ttu-id="d4216-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="d4216-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="d4216-114">Konfigurationsinhalt.</span><span class="sxs-lookup"><span data-stu-id="d4216-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="d4216-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="d4216-115">configPoolID</span></span>  <br/> |<span data-ttu-id="d4216-116">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="d4216-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="d4216-117">Eindeutige ID der Datenbankinstanz.</span><span class="sxs-lookup"><span data-stu-id="d4216-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="d4216-118">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d4216-118">**Key**</span></span>

|<span data-ttu-id="d4216-119">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="d4216-119">**Column**</span></span>|<span data-ttu-id="d4216-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d4216-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d4216-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="d4216-121">configLabel</span></span>  <br/> |<span data-ttu-id="d4216-122">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="d4216-122">Primary key.</span></span>  <br/> |
   

