---
title: tblComplianceFanout
ms.reviewer: ''
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
ms.openlocfilehash: 7f24b1a78dab16b43036734e21d5a8a9b876ca7a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212628"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="b74a4-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="b74a4-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="b74a4-104">TblComplianceFanout enthält alle Server, die ein kompatibilitätsereignis verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b74a4-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="b74a4-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="b74a4-105">**Columns**</span></span>

|<span data-ttu-id="b74a4-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="b74a4-106">**Column**</span></span>|<span data-ttu-id="b74a4-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="b74a4-107">**Type**</span></span>|<span data-ttu-id="b74a4-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b74a4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b74a4-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="b74a4-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="b74a4-110">int</span><span class="sxs-lookup"><span data-stu-id="b74a4-110">int</span></span>  <br/> |<span data-ttu-id="b74a4-111">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b74a4-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="b74a4-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="b74a4-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="b74a4-113">int</span><span class="sxs-lookup"><span data-stu-id="b74a4-113">int</span></span>  <br/> |<span data-ttu-id="b74a4-114">Serveridentität (entsprechend zur tblServerIdentity.serverID-Tabelle).</span><span class="sxs-lookup"><span data-stu-id="b74a4-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="b74a4-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="b74a4-115">**Key**</span></span>

|<span data-ttu-id="b74a4-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="b74a4-116">**Column**</span></span>|<span data-ttu-id="b74a4-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b74a4-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b74a4-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="b74a4-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="b74a4-119">Fremdschlüssel mit Abfrage der tblComplianceData.cmplEventID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b74a4-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

