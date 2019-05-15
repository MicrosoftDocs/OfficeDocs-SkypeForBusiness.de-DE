---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: TblComplianceFanout enthält alle Server, die ein kompatibilitätsereignis verarbeitet.
ms.openlocfilehash: 002ffe3fd825dd90a5223dca06316ff3a60fddd9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929923"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="7d76f-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="7d76f-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="7d76f-104">TblComplianceFanout enthält alle Server, die ein kompatibilitätsereignis verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="7d76f-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="7d76f-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="7d76f-105">**Columns**</span></span>

|<span data-ttu-id="7d76f-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="7d76f-106">**Column**</span></span>|<span data-ttu-id="7d76f-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="7d76f-107">**Type**</span></span>|<span data-ttu-id="7d76f-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="7d76f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7d76f-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="7d76f-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="7d76f-110">int</span><span class="sxs-lookup"><span data-stu-id="7d76f-110">int</span></span>  <br/> |<span data-ttu-id="7d76f-111">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="7d76f-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="7d76f-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="7d76f-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="7d76f-113">int</span><span class="sxs-lookup"><span data-stu-id="7d76f-113">int</span></span>  <br/> |<span data-ttu-id="7d76f-114">Serveridentität (entsprechend zur tblServerIdentity.serverID-Tabelle).</span><span class="sxs-lookup"><span data-stu-id="7d76f-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="7d76f-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="7d76f-115">**Key**</span></span>

|<span data-ttu-id="7d76f-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="7d76f-116">**Column**</span></span>|<span data-ttu-id="7d76f-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="7d76f-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7d76f-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="7d76f-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="7d76f-119">Fremdschlüssel mit Abfrage der tblComplianceData.cmplEventID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7d76f-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

