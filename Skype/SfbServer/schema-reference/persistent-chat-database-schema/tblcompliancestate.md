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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState enthält Informationen zum Kompatibilitätszustand des Pools.
ms.openlocfilehash: 6f3a7b1b7744260d0630a5328021b1752137a797
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814633"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="afb8d-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="afb8d-103">tblComplianceState</span></span>
 
<span data-ttu-id="afb8d-104">tblComplianceState enthält Informationen zum Kompatibilitätszustand des Pools.</span><span class="sxs-lookup"><span data-stu-id="afb8d-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="afb8d-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="afb8d-105">**Columns**</span></span>

|<span data-ttu-id="afb8d-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="afb8d-106">**Column**</span></span>|<span data-ttu-id="afb8d-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="afb8d-107">**Type**</span></span>|<span data-ttu-id="afb8d-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="afb8d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="afb8d-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="afb8d-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="afb8d-110">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="afb8d-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="afb8d-111">Die ID des letzten verarbeiteten Compliance-Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="afb8d-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="afb8d-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="afb8d-112">activeServerID</span></span>  <br/> |<span data-ttu-id="afb8d-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="afb8d-113">int, not null</span></span>  <br/> |<span data-ttu-id="afb8d-114">Die ID des Kompatibilitätsservers, auf dem die exklusive Sperre für die Datenbank gespeichert ist, oder-1, wenn kein.</span><span class="sxs-lookup"><span data-stu-id="afb8d-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="afb8d-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="afb8d-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="afb8d-116">datetime2, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="afb8d-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="afb8d-117">Ablaufzeit Sperren (wenn activeServerID nicht-1 ist).</span><span class="sxs-lookup"><span data-stu-id="afb8d-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

