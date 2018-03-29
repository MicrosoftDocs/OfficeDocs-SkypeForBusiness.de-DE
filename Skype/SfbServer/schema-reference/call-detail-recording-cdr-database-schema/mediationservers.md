---
title: MediationServers-Tabelle
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: Die MediationServers-Tabelle ist eine Tabelle. Jeder Datensatz speichert Informationen über einen Vermittlungsserver, die beteiligt ist in Anrufe, die Datensätze in der Datenbank verfügen.
ms.openlocfilehash: 5854e9787497316d76b7262821be8d4953532d56
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="mediationservers-table"></a><span data-ttu-id="4df51-104">MediationServers-Tabelle</span><span class="sxs-lookup"><span data-stu-id="4df51-104">MediationServers table</span></span>
 
<span data-ttu-id="4df51-105">Die MediationServers-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4df51-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="4df51-106">Jeder Datensatz speichert Informationen über einen Vermittlungsserver, die beteiligt ist in Anrufe, die Datensätze in der Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="4df51-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="4df51-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="4df51-107">**Column**</span></span>|<span data-ttu-id="4df51-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="4df51-108">**Data Type**</span></span>|<span data-ttu-id="4df51-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="4df51-109">**Key/Index**</span></span>|<span data-ttu-id="4df51-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="4df51-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4df51-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="4df51-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="4df51-112">int</span><span class="sxs-lookup"><span data-stu-id="4df51-112">int</span></span>  <br/> |<span data-ttu-id="4df51-113">Primary</span><span class="sxs-lookup"><span data-stu-id="4df51-113">Primary</span></span>  <br/> |<span data-ttu-id="4df51-114">Eindeutige Zahl, die diesen Vermittlungsserver identifiziert.</span><span class="sxs-lookup"><span data-stu-id="4df51-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="4df51-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="4df51-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="4df51-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4df51-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="4df51-117">Name des Vermittlungsservers.</span><span class="sxs-lookup"><span data-stu-id="4df51-117">Mediation Server name.</span></span>  <br/> |
   

