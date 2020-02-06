---
title: tblComplianceFanout
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout enthält alle Server, die ein Compliance-Ereignis verarbeitet haben.
ms.openlocfilehash: cdf455563ccfc971963144b9d4e848d5678cac80
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814653"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="a7840-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="a7840-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="a7840-104">tblComplianceFanout enthält alle Server, die ein Compliance-Ereignis verarbeitet haben.</span><span class="sxs-lookup"><span data-stu-id="a7840-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="a7840-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="a7840-105">**Columns**</span></span>

|<span data-ttu-id="a7840-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="a7840-106">**Column**</span></span>|<span data-ttu-id="a7840-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="a7840-107">**Type**</span></span>|<span data-ttu-id="a7840-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a7840-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a7840-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="a7840-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="a7840-110">int</span><span class="sxs-lookup"><span data-stu-id="a7840-110">int</span></span>  <br/> |<span data-ttu-id="a7840-111">Ereignis-ID.</span><span class="sxs-lookup"><span data-stu-id="a7840-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="a7840-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="a7840-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="a7840-113">int</span><span class="sxs-lookup"><span data-stu-id="a7840-113">int</span></span>  <br/> |<span data-ttu-id="a7840-114">Serveridentität (entsprechend der Tabelle "tblServerIdentity. Serverkennung").</span><span class="sxs-lookup"><span data-stu-id="a7840-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="a7840-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="a7840-115">**Key**</span></span>

|<span data-ttu-id="a7840-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="a7840-116">**Column**</span></span>|<span data-ttu-id="a7840-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a7840-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a7840-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="a7840-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="a7840-119">Fremdschlüssel mit Lookup in der tblComplianceData. cmplEventID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a7840-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

