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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig enthält eine nicht unterstützte Konfiguration für beständigen Chat Server in einer Zeile.
ms.openlocfilehash: f79af00d6a9f97f0ce0836684a284779be662c1d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814623"
---
# <a name="tblconfig"></a><span data-ttu-id="8281e-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="8281e-103">tblConfig</span></span>
 
<span data-ttu-id="8281e-104">tblConfig enthält eine nicht unterstützte Konfiguration für beständigen Chat Server in einer Zeile.</span><span class="sxs-lookup"><span data-stu-id="8281e-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="8281e-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="8281e-105">**Columns**</span></span>

|<span data-ttu-id="8281e-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="8281e-106">**Column**</span></span>|<span data-ttu-id="8281e-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="8281e-107">**Type**</span></span>|<span data-ttu-id="8281e-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8281e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8281e-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="8281e-109">configLabel</span></span>  <br/> |<span data-ttu-id="8281e-110">nvarchar (255); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="8281e-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="8281e-111">Enthält "Pool".</span><span class="sxs-lookup"><span data-stu-id="8281e-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="8281e-112">configContent</span><span class="sxs-lookup"><span data-stu-id="8281e-112">configContent</span></span>  <br/> |<span data-ttu-id="8281e-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="8281e-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="8281e-114">Konfigurationsinhalt.</span><span class="sxs-lookup"><span data-stu-id="8281e-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="8281e-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="8281e-115">configPoolID</span></span>  <br/> |<span data-ttu-id="8281e-116">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="8281e-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="8281e-117">Eindeutige ID der Datenbankinstanz.</span><span class="sxs-lookup"><span data-stu-id="8281e-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="8281e-118">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="8281e-118">**Key**</span></span>

|<span data-ttu-id="8281e-119">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="8281e-119">**Column**</span></span>|<span data-ttu-id="8281e-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8281e-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8281e-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="8281e-121">configLabel</span></span>  <br/> |<span data-ttu-id="8281e-122">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="8281e-122">Primary key.</span></span>  <br/> |
   

