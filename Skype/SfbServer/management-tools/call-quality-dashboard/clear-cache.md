---
title: Leeren des Caches
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang zum Löschen des Caches, der Teil der Daten-API für das Dashboard für die Anrufqualität ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 38648e1a910f93a30bd6da8807321acad0330e62
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274835"
---
# <a name="clear-cache"></a><span data-ttu-id="80e57-104">Leeren des Caches</span><span class="sxs-lookup"><span data-stu-id="80e57-104">Clear Cache</span></span>
 
<span data-ttu-id="80e57-105">**Zusammenfassung:** Erfahren Sie mehr über den Vorgang zum Löschen des Caches, der Teil der Daten-API für das Dashboard für die Anrufqualität ist.</span><span class="sxs-lookup"><span data-stu-id="80e57-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="80e57-106">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="80e57-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="80e57-107">Der Vorgang zum Löschen des Caches ist Teil der Daten-API für das Dashboard für die Anrufqualität.</span><span class="sxs-lookup"><span data-stu-id="80e57-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="80e57-108">Leeren des Caches</span><span class="sxs-lookup"><span data-stu-id="80e57-108">Clear Cache</span></span>

<span data-ttu-id="80e57-109">Löschen des Cache Vorgangs löscht den Cache auf dem Server für Abfragen und Daten.</span><span class="sxs-lookup"><span data-stu-id="80e57-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="80e57-110">Dadurch wird der Cache zurückgesetzt, und wir erhalten neue Daten aus dem QoE-Cube später für neue Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="80e57-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="80e57-111">**Methode**</span><span class="sxs-lookup"><span data-stu-id="80e57-111">**Method**</span></span>|<span data-ttu-id="80e57-112">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="80e57-112">**Request URI**</span></span>|<span data-ttu-id="80e57-113">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="80e57-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="80e57-114">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="80e57-114">POST</span></span>  <br/> |<span data-ttu-id="80e57-115">https://\<-\>Portal/QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="80e57-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="80e57-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="80e57-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="80e57-117">**URI-Parameter** -None.</span><span class="sxs-lookup"><span data-stu-id="80e57-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="80e57-118">**Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="80e57-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="80e57-119">**Anforderungstext** – keine.</span><span class="sxs-lookup"><span data-stu-id="80e57-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="80e57-120">**Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.</span><span class="sxs-lookup"><span data-stu-id="80e57-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="80e57-121">**Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.</span><span class="sxs-lookup"><span data-stu-id="80e57-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="80e57-122">**Antwortheader** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="80e57-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="80e57-123">**Antworttext** – keine.</span><span class="sxs-lookup"><span data-stu-id="80e57-123">**Response Body** - None.</span></span>
  

