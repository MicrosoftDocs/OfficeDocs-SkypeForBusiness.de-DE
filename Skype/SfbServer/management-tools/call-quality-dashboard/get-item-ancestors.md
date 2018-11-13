---
title: Abrufen der Vorgänger des Elements
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 'Zusammenfassung: Informationen Sie zum Vorgang Element Vorgänger erhalten möchten, der Teil der Element-Dienst ist. Der Element-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.'
ms.openlocfilehash: 872af4deb7f6cf7ad1d519b41b7e2405121b1eea
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294422"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="8b4a9-105">Abrufen der Vorgänger des Elements</span><span class="sxs-lookup"><span data-stu-id="8b4a9-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="8b4a9-106">**Zusammenfassung:** Informationen Sie zum Vorgang Element Vorgänger erhalten möchten, der Teil der Element-Dienst ist.</span><span class="sxs-lookup"><span data-stu-id="8b4a9-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="8b4a9-107">Der Element-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8b4a9-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="8b4a9-108">Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8b4a9-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8b4a9-109">Der erste Artikel Vorgänger Vorgang ist Teil des Diensts Element in der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8b4a9-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="8b4a9-110">Abrufen der Vorgänger des Elements</span><span class="sxs-lookup"><span data-stu-id="8b4a9-110">Get Item Ancestors</span></span>

<span data-ttu-id="8b4a9-111">Get-Element Vorgänger gibt ein Vorgänger bestimmte Elemente aus dem Repository zurück.</span><span class="sxs-lookup"><span data-stu-id="8b4a9-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="8b4a9-112">**Methode**</span><span class="sxs-lookup"><span data-stu-id="8b4a9-112">**Method**</span></span>|<span data-ttu-id="8b4a9-113">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="8b4a9-113">**Request URI**</span></span>|<span data-ttu-id="8b4a9-114">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="8b4a9-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8b4a9-115">Erhalten</span><span class="sxs-lookup"><span data-stu-id="8b4a9-115">GET</span></span>  <br/> |<span data-ttu-id="8b4a9-116">https://\<Portal\>/QoERepositoryService/Repository/ItemAncestors / {ItemId}</span><span class="sxs-lookup"><span data-stu-id="8b4a9-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="8b4a9-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="8b4a9-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="8b4a9-118">**URI-Parameter** - None.</span><span class="sxs-lookup"><span data-stu-id="8b4a9-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="8b4a9-119">**Anfordern von Kopfzeilen** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="8b4a9-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="8b4a9-120">**Anforderungstextkörper** – None.</span><span class="sxs-lookup"><span data-stu-id="8b4a9-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="8b4a9-121">**Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.</span><span class="sxs-lookup"><span data-stu-id="8b4a9-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="8b4a9-122">**Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="8b4a9-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="8b4a9-123">Wenn einen angegebenen Benutzer-ID nicht gefunden wurde, wird der Statuscode 404 (nicht gefunden) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8b4a9-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="8b4a9-124">**Antwortheader** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="8b4a9-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="8b4a9-125">**Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="8b4a9-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
[{
"item1": 1653,
"item2": 0,
"item3": "Audio Streams Monthly Trend"
},
{
"item1": 1652,
"item2": 1,
"item3": "All Audio Streams"
}]
```

 <span data-ttu-id="8b4a9-126">*Item1* - ID des Elements.</span><span class="sxs-lookup"><span data-stu-id="8b4a9-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="8b4a9-127">*Item2* - Tiefe wird der Abstand zwischen dem Element.</span><span class="sxs-lookup"><span data-stu-id="8b4a9-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="8b4a9-128">0 ist der unmittelbar übergeordnet.</span><span class="sxs-lookup"><span data-stu-id="8b4a9-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="8b4a9-129">*Item3* - Titel des Elements.</span><span class="sxs-lookup"><span data-stu-id="8b4a9-129">*Item3*  - Title of the item.</span></span>
  

