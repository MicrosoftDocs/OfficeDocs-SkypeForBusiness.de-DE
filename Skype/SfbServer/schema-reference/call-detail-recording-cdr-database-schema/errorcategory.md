---
title: ErrorCategory-Tabelle in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'Die ErrorCategory-Tabelle enthält den Anzeigenamen für jede Diagnose Klassifizierung für Skype for Business Server 2015. Standardmäßig verwendet Skype for Business Server 2015 die folgenden Klassifizierungen:'
ms.openlocfilehash: bafeb75ee9e6ae0f96b08e26909828f1b36f7e7b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296287"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="54e1f-104">ErrorCategory-Tabelle in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="54e1f-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="54e1f-105">Die ErrorCategory-Tabelle enthält den Anzeigenamen für jede Diagnose Klassifizierung für Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="54e1f-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="54e1f-106">Standardmäßig verwendet Skype for Business Server 2015 die folgenden Klassifizierungen:</span><span class="sxs-lookup"><span data-stu-id="54e1f-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="54e1f-107">0--Erfolg</span><span class="sxs-lookup"><span data-stu-id="54e1f-107">0 -- Success</span></span>
    
- <span data-ttu-id="54e1f-108">1 – Erwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="54e1f-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="54e1f-109">2 – unerwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="54e1f-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="54e1f-110">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="54e1f-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="54e1f-111">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="54e1f-111">**Column**</span></span>|<span data-ttu-id="54e1f-112">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="54e1f-112">**Data Type**</span></span>|<span data-ttu-id="54e1f-113">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="54e1f-113">**Key/Index**</span></span>|<span data-ttu-id="54e1f-114">**Details**</span><span class="sxs-lookup"><span data-stu-id="54e1f-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="54e1f-115">**CategoryID**</span><span class="sxs-lookup"><span data-stu-id="54e1f-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="54e1f-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="54e1f-116">tinyint</span></span>  <br/> |<span data-ttu-id="54e1f-117">Primary</span><span class="sxs-lookup"><span data-stu-id="54e1f-117">Primary</span></span>  <br/> |<span data-ttu-id="54e1f-118">Eindeutiger Bezeichner für die Klassifizierung.</span><span class="sxs-lookup"><span data-stu-id="54e1f-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="54e1f-119">**Name**</span><span class="sxs-lookup"><span data-stu-id="54e1f-119">**Name**</span></span> <br/> |<span data-ttu-id="54e1f-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="54e1f-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="54e1f-121">Wert und Anzeigename, der der Klassifizierung zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="54e1f-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="54e1f-122">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="54e1f-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="54e1f-123">0--Erfolg</span><span class="sxs-lookup"><span data-stu-id="54e1f-123">0 -- Success</span></span> <br/>  <span data-ttu-id="54e1f-124">1 – Erwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="54e1f-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="54e1f-125">2 – unerwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="54e1f-125">2 - Unexpected failure</span></span> <br/> |
   

