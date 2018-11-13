---
title: Cache löschen
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Zusammenfassung: Informationen Sie zu den Cache löschen-Vorgang, der Teil der Daten-API für die Qualitätsdashboard aufrufen, ist. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.'
ms.openlocfilehash: 64873e7257877859ff8b16c504cee93d3287f9ed
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294511"
---
# <a name="clear-cache"></a><span data-ttu-id="f73a0-104">Cache löschen</span><span class="sxs-lookup"><span data-stu-id="f73a0-104">Clear Cache</span></span>
 
<span data-ttu-id="f73a0-105">**Zusammenfassung:** Informationen Sie zu den Cache löschen-Vorgang, der Teil der Daten-API für die Qualitätsdashboard aufrufen, ist.</span><span class="sxs-lookup"><span data-stu-id="f73a0-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="f73a0-106">Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f73a0-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="f73a0-107">Der Cache löschen-Vorgang ist Teil der Daten-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f73a0-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="f73a0-108">Cache löschen</span><span class="sxs-lookup"><span data-stu-id="f73a0-108">Clear Cache</span></span>

<span data-ttu-id="f73a0-109">Löschvorgang Cache löscht den Cache auf dem Server für Abfragen und Daten.</span><span class="sxs-lookup"><span data-stu-id="f73a0-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="f73a0-110">Dadurch wird den Cache zurückgesetzt, und wir erhalten neue Daten vom QoE-Cube später für neue Anfragen.</span><span class="sxs-lookup"><span data-stu-id="f73a0-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="f73a0-111">**Methode**</span><span class="sxs-lookup"><span data-stu-id="f73a0-111">**Method**</span></span>|<span data-ttu-id="f73a0-112">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="f73a0-112">**Request URI**</span></span>|<span data-ttu-id="f73a0-113">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="f73a0-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f73a0-114">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="f73a0-114">POST</span></span>  <br/> |<span data-ttu-id="f73a0-115">https://\<Portal\>/QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="f73a0-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="f73a0-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="f73a0-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="f73a0-117">**URI-Parameter** - None.</span><span class="sxs-lookup"><span data-stu-id="f73a0-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="f73a0-118">**Anfordern von Kopfzeilen** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="f73a0-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="f73a0-119">**Anforderungstextkörper** – None.</span><span class="sxs-lookup"><span data-stu-id="f73a0-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="f73a0-120">**Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.</span><span class="sxs-lookup"><span data-stu-id="f73a0-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="f73a0-121">**Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="f73a0-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="f73a0-122">**Antwortheader** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="f73a0-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="f73a0-123">**Antworttext** – None.</span><span class="sxs-lookup"><span data-stu-id="f73a0-123">**Response Body** - None.</span></span>
  

