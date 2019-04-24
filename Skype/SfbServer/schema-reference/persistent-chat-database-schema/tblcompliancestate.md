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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212635"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="129b3-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="129b3-103">tblComplianceState</span></span>
 
<span data-ttu-id="129b3-104">TblComplianceState enthält poolweite Informationen zum kompatibilitätszustand.</span><span class="sxs-lookup"><span data-stu-id="129b3-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="129b3-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="129b3-105">**Columns**</span></span>

|<span data-ttu-id="129b3-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="129b3-106">**Column**</span></span>|<span data-ttu-id="129b3-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="129b3-107">**Type**</span></span>|<span data-ttu-id="129b3-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="129b3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="129b3-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="129b3-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="129b3-110">Bigint, nicht null</span><span class="sxs-lookup"><span data-stu-id="129b3-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="129b3-111">ID des letzten verarbeiteten kompatibilitätsereignisses.</span><span class="sxs-lookup"><span data-stu-id="129b3-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="129b3-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="129b3-112">activeServerID</span></span>  <br/> |<span data-ttu-id="129b3-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="129b3-113">int, not null</span></span>  <br/> |<span data-ttu-id="129b3-114">Die Einhaltung von Bestimmungen gedrückt halten die exklusive Sperre für die Datenbank oder -1, wenn keine ID.</span><span class="sxs-lookup"><span data-stu-id="129b3-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="129b3-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="129b3-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="129b3-116">datetime2, nicht null</span><span class="sxs-lookup"><span data-stu-id="129b3-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="129b3-117">Sperren Sie Ablaufzeit (wenn ActiveServerID nicht-1 ist).</span><span class="sxs-lookup"><span data-stu-id="129b3-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

