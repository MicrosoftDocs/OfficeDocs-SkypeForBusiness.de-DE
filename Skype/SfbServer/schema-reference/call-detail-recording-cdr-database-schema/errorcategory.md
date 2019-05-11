---
title: ErrorCategory-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'ErrorCategory-Tabelle enthält den Anzeigenamen für jedes Skype für Business Server 2015-diagnoseklassifizierung. Skype für Business Server 2015 verwendet standardmäßig die folgenden Klassifikationen:'
ms.openlocfilehash: b6226396302353b815138b41b7c19f170a0d6b4d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901087"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="b3e24-104">ErrorCategory-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b3e24-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b3e24-105">ErrorCategory-Tabelle enthält den Anzeigenamen für jedes Skype für Business Server 2015-diagnoseklassifizierung.</span><span class="sxs-lookup"><span data-stu-id="b3e24-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="b3e24-106">Skype für Business Server 2015 verwendet standardmäßig die folgenden Klassifikationen:</span><span class="sxs-lookup"><span data-stu-id="b3e24-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="b3e24-107">0 – Erfolg</span><span class="sxs-lookup"><span data-stu-id="b3e24-107">0 -- Success</span></span>
    
- <span data-ttu-id="b3e24-108">1--Erwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="b3e24-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="b3e24-109">2 – unerwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="b3e24-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="b3e24-110">Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b3e24-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="b3e24-111">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="b3e24-111">**Column**</span></span>|<span data-ttu-id="b3e24-112">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="b3e24-112">**Data Type**</span></span>|<span data-ttu-id="b3e24-113">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="b3e24-113">**Key/Index**</span></span>|<span data-ttu-id="b3e24-114">**Details**</span><span class="sxs-lookup"><span data-stu-id="b3e24-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b3e24-115">**CategoryId**</span><span class="sxs-lookup"><span data-stu-id="b3e24-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="b3e24-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="b3e24-116">tinyint</span></span>  <br/> |<span data-ttu-id="b3e24-117">Primary</span><span class="sxs-lookup"><span data-stu-id="b3e24-117">Primary</span></span>  <br/> |<span data-ttu-id="b3e24-118">Eindeutiger Bezeichner für die Klassifikation.</span><span class="sxs-lookup"><span data-stu-id="b3e24-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="b3e24-119">**Name**</span><span class="sxs-lookup"><span data-stu-id="b3e24-119">**Name**</span></span> <br/> |<span data-ttu-id="b3e24-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b3e24-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="b3e24-121">Wert und dem Anzeigenamen der Klassifikation zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b3e24-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="b3e24-122">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="b3e24-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="b3e24-123">0 – Erfolg</span><span class="sxs-lookup"><span data-stu-id="b3e24-123">0 -- Success</span></span> <br/>  <span data-ttu-id="b3e24-124">1--Erwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="b3e24-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="b3e24-125">2 – unerwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="b3e24-125">2 - Unexpected failure</span></span> <br/> |
   

