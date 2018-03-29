---
title: tblComplianceFanout
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: TblComplianceFanout enthält alle Server, die ein kompatibilitätsereignis verarbeitet.
ms.openlocfilehash: f9141a6f7144c20d8039756387a889cc25cc8f50
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="c201c-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="c201c-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="c201c-104">TblComplianceFanout enthält alle Server, die ein kompatibilitätsereignis verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="c201c-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="c201c-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="c201c-105">**Columns**</span></span>

|<span data-ttu-id="c201c-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="c201c-106">**Column**</span></span>|<span data-ttu-id="c201c-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="c201c-107">**Type**</span></span>|<span data-ttu-id="c201c-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c201c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c201c-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="c201c-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="c201c-110">int</span><span class="sxs-lookup"><span data-stu-id="c201c-110">int</span></span>  <br/> |<span data-ttu-id="c201c-111">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="c201c-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="c201c-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="c201c-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="c201c-113">int</span><span class="sxs-lookup"><span data-stu-id="c201c-113">int</span></span>  <br/> |<span data-ttu-id="c201c-114">Serveridentität (entsprechend zur tblServerIdentity.serverID-Tabelle).</span><span class="sxs-lookup"><span data-stu-id="c201c-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="c201c-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="c201c-115">**Key**</span></span>

|<span data-ttu-id="c201c-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="c201c-116">**Column**</span></span>|<span data-ttu-id="c201c-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c201c-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c201c-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="c201c-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="c201c-119">Fremdschlüssel mit Abfrage der tblComplianceData.cmplEventID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c201c-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

