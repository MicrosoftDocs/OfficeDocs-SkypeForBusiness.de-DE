---
title: Abrufen von Elementen
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 'Zusammenfassung: Informationen Sie zum Vorgang Elemente abrufen, der Teil der Element-Dienst ist. Der Element-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.'
ms.openlocfilehash: 526d578d65ded98a6cd1a5cfc09a6749319683c3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="get-items"></a><span data-ttu-id="bd08e-105">Abrufen von Elementen</span><span class="sxs-lookup"><span data-stu-id="bd08e-105">Get Items</span></span>
 
<span data-ttu-id="bd08e-106">**Zusammenfassung:** Informationen Sie zu den Vorgang Elemente abrufen, der Teil der Element-Dienst ist.</span><span class="sxs-lookup"><span data-stu-id="bd08e-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="bd08e-107">Der Element-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="bd08e-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="bd08e-108">Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="bd08e-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="bd08e-109">Der Vorgang Elemente abrufen ist Teil des Diensts Element in der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="bd08e-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="bd08e-110">Abrufen von Elementen</span><span class="sxs-lookup"><span data-stu-id="bd08e-110">Get Items</span></span>

<span data-ttu-id="bd08e-111">Rufen Sie Elemente gibt alle Elemente im Repository.</span><span class="sxs-lookup"><span data-stu-id="bd08e-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="bd08e-112">**Methode**</span><span class="sxs-lookup"><span data-stu-id="bd08e-112">**Method**</span></span>|<span data-ttu-id="bd08e-113">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="bd08e-113">**Request URI**</span></span>|<span data-ttu-id="bd08e-114">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="bd08e-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bd08e-115">Erhalten</span><span class="sxs-lookup"><span data-stu-id="bd08e-115">GET</span></span>  <br/> |<span data-ttu-id="bd08e-116">https://\<Portal\>/QoERepositoryService/repository/item</span><span class="sxs-lookup"><span data-stu-id="bd08e-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="bd08e-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="bd08e-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="bd08e-118">**URI-Parameter** - None.</span><span class="sxs-lookup"><span data-stu-id="bd08e-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="bd08e-119">**Anfordern von Kopfzeilen** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="bd08e-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="bd08e-120">**Anforderungstextkörper** – None.</span><span class="sxs-lookup"><span data-stu-id="bd08e-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="bd08e-121">**Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.</span><span class="sxs-lookup"><span data-stu-id="bd08e-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="bd08e-122">**Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="bd08e-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="bd08e-123">**Antwortheader** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="bd08e-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="bd08e-124">**Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="bd08e-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bd08e-125">Ein Array von Elementobjekten wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bd08e-125">An array of Item objects is returned.</span></span> <span data-ttu-id="bd08e-126">Ausführliche Informationen zu Elementobjekt finden Sie unter Get-Element.</span><span class="sxs-lookup"><span data-stu-id="bd08e-126">For details about Item object, see Get Item.</span></span> 
  
```
[{
"itemId": 1652,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1654,
"userId": 0,
"type": "application/json"
}]

```


