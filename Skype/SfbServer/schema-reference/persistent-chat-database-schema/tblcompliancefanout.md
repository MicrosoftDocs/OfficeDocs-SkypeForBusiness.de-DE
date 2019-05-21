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
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout enthält alle Server, die ein Compliance-Ereignis verarbeitet haben.
ms.openlocfilehash: 1d2dfc99619e0669a08db33dbacc75930053f0dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295503"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="36488-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="36488-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="36488-104">tblComplianceFanout enthält alle Server, die ein Compliance-Ereignis verarbeitet haben.</span><span class="sxs-lookup"><span data-stu-id="36488-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="36488-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="36488-105">**Columns**</span></span>

|<span data-ttu-id="36488-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="36488-106">**Column**</span></span>|<span data-ttu-id="36488-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="36488-107">**Type**</span></span>|<span data-ttu-id="36488-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="36488-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="36488-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="36488-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="36488-110">int</span><span class="sxs-lookup"><span data-stu-id="36488-110">int</span></span>  <br/> |<span data-ttu-id="36488-111">Ereignis-ID.</span><span class="sxs-lookup"><span data-stu-id="36488-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="36488-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="36488-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="36488-113">int</span><span class="sxs-lookup"><span data-stu-id="36488-113">int</span></span>  <br/> |<span data-ttu-id="36488-114">Serveridentität (entsprechend der Tabelle "tblServerIdentity. Serverkennung").</span><span class="sxs-lookup"><span data-stu-id="36488-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="36488-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="36488-115">**Key**</span></span>

|<span data-ttu-id="36488-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="36488-116">**Column**</span></span>|<span data-ttu-id="36488-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="36488-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="36488-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="36488-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="36488-119">Fremdschlüssel mit Lookup in der tblComplianceData. cmplEventID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="36488-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

