---
title: MediationServers-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: Die Tabelle MediationServers ist eine unterstützende Tabelle. Jeder Datensatz speichert Informationen zu einem Vermittlungs Server, der an anrufen beteiligt ist, die Datensätze in der Datenbank aufweisen.
ms.openlocfilehash: a79c7c1d81f220e034e63263ef8dbf81a13d4024
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295993"
---
# <a name="mediationservers-table"></a><span data-ttu-id="4d188-104">MediationServers-Tabelle</span><span class="sxs-lookup"><span data-stu-id="4d188-104">MediationServers table</span></span>
 
<span data-ttu-id="4d188-105">Die Tabelle MediationServers ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4d188-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="4d188-106">Jeder Datensatz speichert Informationen zu einem Vermittlungs Server, der an anrufen beteiligt ist, die Datensätze in der Datenbank aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4d188-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="4d188-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="4d188-107">**Column**</span></span>|<span data-ttu-id="4d188-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="4d188-108">**Data Type**</span></span>|<span data-ttu-id="4d188-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="4d188-109">**Key/Index**</span></span>|<span data-ttu-id="4d188-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="4d188-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4d188-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="4d188-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="4d188-112">int</span><span class="sxs-lookup"><span data-stu-id="4d188-112">int</span></span>  <br/> |<span data-ttu-id="4d188-113">Primary</span><span class="sxs-lookup"><span data-stu-id="4d188-113">Primary</span></span>  <br/> |<span data-ttu-id="4d188-114">Eindeutige Nummer, die diesen Vermittlungs Server identifiziert.</span><span class="sxs-lookup"><span data-stu-id="4d188-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="4d188-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="4d188-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="4d188-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4d188-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="4d188-117">Name des Vermittlungsservers.</span><span class="sxs-lookup"><span data-stu-id="4d188-117">Mediation Server name.</span></span>  <br/> |
   

