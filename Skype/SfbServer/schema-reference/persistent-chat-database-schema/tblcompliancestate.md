---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: TblComplianceState enthält poolweite Informationen zum kompatibilitätszustand.
ms.openlocfilehash: 6f6b3891638fc3d769c0b0f4f4a42ca5f94a5a54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929847"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="50f34-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="50f34-103">tblComplianceState</span></span>
 
<span data-ttu-id="50f34-104">TblComplianceState enthält poolweite Informationen zum kompatibilitätszustand.</span><span class="sxs-lookup"><span data-stu-id="50f34-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="50f34-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="50f34-105">**Columns**</span></span>

|<span data-ttu-id="50f34-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="50f34-106">**Column**</span></span>|<span data-ttu-id="50f34-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="50f34-107">**Type**</span></span>|<span data-ttu-id="50f34-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="50f34-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="50f34-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="50f34-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="50f34-110">Bigint, nicht null</span><span class="sxs-lookup"><span data-stu-id="50f34-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="50f34-111">ID des letzten verarbeiteten kompatibilitätsereignisses.</span><span class="sxs-lookup"><span data-stu-id="50f34-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="50f34-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="50f34-112">activeServerID</span></span>  <br/> |<span data-ttu-id="50f34-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="50f34-113">int, not null</span></span>  <br/> |<span data-ttu-id="50f34-114">Die Einhaltung von Bestimmungen gedrückt halten die exklusive Sperre für die Datenbank oder -1, wenn keine ID.</span><span class="sxs-lookup"><span data-stu-id="50f34-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="50f34-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="50f34-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="50f34-116">datetime2, nicht null</span><span class="sxs-lookup"><span data-stu-id="50f34-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="50f34-117">Sperren Sie Ablaufzeit (wenn ActiveServerID nicht-1 ist).</span><span class="sxs-lookup"><span data-stu-id="50f34-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

