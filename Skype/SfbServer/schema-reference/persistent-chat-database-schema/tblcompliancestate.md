---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState enthält Informationen zum Kompatibilitätszustand des Pools.
ms.openlocfilehash: 1c5571d7150c3859978f8d217f0264f67ee993d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295475"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="767d8-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="767d8-103">tblComplianceState</span></span>
 
<span data-ttu-id="767d8-104">tblComplianceState enthält Informationen zum Kompatibilitätszustand des Pools.</span><span class="sxs-lookup"><span data-stu-id="767d8-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="767d8-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="767d8-105">**Columns**</span></span>

|<span data-ttu-id="767d8-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="767d8-106">**Column**</span></span>|<span data-ttu-id="767d8-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="767d8-107">**Type**</span></span>|<span data-ttu-id="767d8-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="767d8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="767d8-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="767d8-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="767d8-110">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="767d8-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="767d8-111">Die ID des letzten verarbeiteten Compliance-Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="767d8-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="767d8-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="767d8-112">activeServerID</span></span>  <br/> |<span data-ttu-id="767d8-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="767d8-113">int, not null</span></span>  <br/> |<span data-ttu-id="767d8-114">Die ID des Kompatibilitätsservers, auf dem die exklusive Sperre für die Datenbank gespeichert ist, oder-1, wenn kein.</span><span class="sxs-lookup"><span data-stu-id="767d8-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="767d8-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="767d8-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="767d8-116">datetime2, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="767d8-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="767d8-117">Ablaufzeit Sperren (wenn activeServerID nicht-1 ist).</span><span class="sxs-lookup"><span data-stu-id="767d8-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

