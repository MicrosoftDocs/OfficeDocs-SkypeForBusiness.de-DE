---
title: MediationServers-Tabelle
ms.reviewer: ''
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
ms.openlocfilehash: 77173fbb81bc2046a1906c61456f607ec7f2b5b3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212901"
---
# <a name="mediationservers-table"></a><span data-ttu-id="bbf94-104">MediationServers-Tabelle</span><span class="sxs-lookup"><span data-stu-id="bbf94-104">MediationServers table</span></span>
 
<span data-ttu-id="bbf94-105">Die MediationServers-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="bbf94-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="bbf94-106">Jeder Datensatz speichert Informationen über einen Vermittlungsserver, die beteiligt ist in Anrufe, die Datensätze in der Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="bbf94-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="bbf94-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="bbf94-107">**Column**</span></span>|<span data-ttu-id="bbf94-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="bbf94-108">**Data Type**</span></span>|<span data-ttu-id="bbf94-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="bbf94-109">**Key/Index**</span></span>|<span data-ttu-id="bbf94-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="bbf94-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bbf94-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="bbf94-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="bbf94-112">int</span><span class="sxs-lookup"><span data-stu-id="bbf94-112">int</span></span>  <br/> |<span data-ttu-id="bbf94-113">Primary</span><span class="sxs-lookup"><span data-stu-id="bbf94-113">Primary</span></span>  <br/> |<span data-ttu-id="bbf94-114">Eindeutige Zahl, die diesen Vermittlungsserver identifiziert.</span><span class="sxs-lookup"><span data-stu-id="bbf94-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="bbf94-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="bbf94-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="bbf94-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bbf94-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="bbf94-117">Name des Vermittlungsservers.</span><span class="sxs-lookup"><span data-stu-id="bbf94-117">Mediation Server name.</span></span>  <br/> |
   

