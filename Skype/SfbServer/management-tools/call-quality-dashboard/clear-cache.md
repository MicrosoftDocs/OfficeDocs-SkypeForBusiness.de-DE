---
title: Leeren des Caches
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Zusammenfassung: Informationen Sie zu den Cache löschen-Vorgang, der Teil der Daten-API für die Qualitätsdashboard aufrufen, ist. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: c2371a7f99eb37e8e01be919bf6c31b0c9a452cb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32195551"
---
# <a name="clear-cache"></a><span data-ttu-id="07e6d-104">Leeren des Caches</span><span class="sxs-lookup"><span data-stu-id="07e6d-104">Clear Cache</span></span>
 
<span data-ttu-id="07e6d-105">**Zusammenfassung:** Informationen Sie zu den Cache löschen-Vorgang, der Teil der Daten-API für die Qualitätsdashboard aufrufen, ist.</span><span class="sxs-lookup"><span data-stu-id="07e6d-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="07e6d-106">Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="07e6d-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="07e6d-107">Der Cache löschen-Vorgang ist Teil der Daten-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="07e6d-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="07e6d-108">Leeren des Caches</span><span class="sxs-lookup"><span data-stu-id="07e6d-108">Clear Cache</span></span>

<span data-ttu-id="07e6d-109">Löschvorgang Cache löscht den Cache auf dem Server für Abfragen und Daten.</span><span class="sxs-lookup"><span data-stu-id="07e6d-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="07e6d-110">Dadurch wird den Cache zurückgesetzt, und wir erhalten neue Daten vom QoE-Cube später für neue Anfragen.</span><span class="sxs-lookup"><span data-stu-id="07e6d-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="07e6d-111">**Methode**</span><span class="sxs-lookup"><span data-stu-id="07e6d-111">**Method**</span></span>|<span data-ttu-id="07e6d-112">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="07e6d-112">**Request URI**</span></span>|<span data-ttu-id="07e6d-113">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="07e6d-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="07e6d-114">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="07e6d-114">POST</span></span>  <br/> |<span data-ttu-id="07e6d-115">https://\<Portal\>/QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="07e6d-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="07e6d-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="07e6d-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="07e6d-117">**URI-Parameter** - None.</span><span class="sxs-lookup"><span data-stu-id="07e6d-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="07e6d-118">**Anfordern von Kopfzeilen** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="07e6d-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="07e6d-119">**Anforderungstextkörper** – None.</span><span class="sxs-lookup"><span data-stu-id="07e6d-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="07e6d-120">**Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.</span><span class="sxs-lookup"><span data-stu-id="07e6d-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="07e6d-121">**Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="07e6d-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="07e6d-122">**Antwortheader** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="07e6d-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="07e6d-123">**Antworttext** – None.</span><span class="sxs-lookup"><span data-stu-id="07e6d-123">**Response Body** - None.</span></span>
  

