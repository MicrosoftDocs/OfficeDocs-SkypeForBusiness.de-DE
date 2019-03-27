---
title: tblComplianceState
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: TblComplianceState enthält poolweite Informationen zum kompatibilitätszustand.
ms.openlocfilehash: 4e9f103ef019e743b5dfcb4ef554ff6a28c340b8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899292"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="c0512-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="c0512-103">tblComplianceState</span></span>
 
<span data-ttu-id="c0512-104">TblComplianceState enthält poolweite Informationen zum kompatibilitätszustand.</span><span class="sxs-lookup"><span data-stu-id="c0512-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="c0512-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="c0512-105">**Columns**</span></span>

|<span data-ttu-id="c0512-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="c0512-106">**Column**</span></span>|<span data-ttu-id="c0512-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="c0512-107">**Type**</span></span>|<span data-ttu-id="c0512-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c0512-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c0512-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="c0512-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="c0512-110">Bigint, nicht null</span><span class="sxs-lookup"><span data-stu-id="c0512-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="c0512-111">ID des letzten verarbeiteten kompatibilitätsereignisses.</span><span class="sxs-lookup"><span data-stu-id="c0512-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="c0512-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="c0512-112">activeServerID</span></span>  <br/> |<span data-ttu-id="c0512-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="c0512-113">int, not null</span></span>  <br/> |<span data-ttu-id="c0512-114">Die Einhaltung von Bestimmungen gedrückt halten die exklusive Sperre für die Datenbank oder -1, wenn keine ID.</span><span class="sxs-lookup"><span data-stu-id="c0512-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="c0512-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="c0512-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="c0512-116">datetime2, nicht null</span><span class="sxs-lookup"><span data-stu-id="c0512-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="c0512-117">Sperren Sie Ablaufzeit (wenn ActiveServerID nicht-1 ist).</span><span class="sxs-lookup"><span data-stu-id="c0512-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

