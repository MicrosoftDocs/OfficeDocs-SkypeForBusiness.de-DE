---
title: MediationServers-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: Die MediationServers-Tabelle ist eine Tabelle. Jeder Datensatz speichert Informationen über einen Vermittlungsserver, die beteiligt ist in Anrufe, die Datensätze in der Datenbank verfügen.
ms.openlocfilehash: 25f6c14a903ffde424cba1c2a6bb3292040b2391
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930546"
---
# <a name="mediationservers-table"></a><span data-ttu-id="7e931-104">MediationServers-Tabelle</span><span class="sxs-lookup"><span data-stu-id="7e931-104">MediationServers table</span></span>
 
<span data-ttu-id="7e931-105">Die MediationServers-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7e931-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="7e931-106">Jeder Datensatz speichert Informationen über einen Vermittlungsserver, die beteiligt ist in Anrufe, die Datensätze in der Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="7e931-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="7e931-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="7e931-107">**Column**</span></span>|<span data-ttu-id="7e931-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="7e931-108">**Data Type**</span></span>|<span data-ttu-id="7e931-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="7e931-109">**Key/Index**</span></span>|<span data-ttu-id="7e931-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="7e931-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7e931-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="7e931-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="7e931-112">int</span><span class="sxs-lookup"><span data-stu-id="7e931-112">int</span></span>  <br/> |<span data-ttu-id="7e931-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7e931-113">Primary</span></span>  <br/> |<span data-ttu-id="7e931-114">Eindeutige Zahl, die diesen Vermittlungsserver identifiziert.</span><span class="sxs-lookup"><span data-stu-id="7e931-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="7e931-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="7e931-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="7e931-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7e931-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="7e931-117">Name des Vermittlungsservers.</span><span class="sxs-lookup"><span data-stu-id="7e931-117">Mediation Server name.</span></span>  <br/> |
   

