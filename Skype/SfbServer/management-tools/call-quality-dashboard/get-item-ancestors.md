---
title: Abrufen von übergeordneten Elementen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang "Element Vorgänger abrufen", der Teil des Element Diensts ist. Der Element Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: c82ae699cab0bf812f281fc2f2ad54323bcf8f7f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992682"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="280af-105">Abrufen von übergeordneten Elementen</span><span class="sxs-lookup"><span data-stu-id="280af-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="280af-106">**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Element Vorgänger abrufen", der Teil des Element Diensts ist.</span><span class="sxs-lookup"><span data-stu-id="280af-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="280af-107">Der Element Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard.</span><span class="sxs-lookup"><span data-stu-id="280af-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="280af-108">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="280af-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="280af-109">Der Vorgang Element Vorgänger abrufen ist Teil des Element Diensts in der Repository-API für das Anruf Qualitäts Dashboard.</span><span class="sxs-lookup"><span data-stu-id="280af-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="280af-110">Abrufen von übergeordneten Elementen</span><span class="sxs-lookup"><span data-stu-id="280af-110">Get Item Ancestors</span></span>

<span data-ttu-id="280af-111">Get Item Ancestors gibt ein bestimmtes Element aus dem Repository zurück.</span><span class="sxs-lookup"><span data-stu-id="280af-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="280af-112">**Methode**</span><span class="sxs-lookup"><span data-stu-id="280af-112">**Method**</span></span>|<span data-ttu-id="280af-113">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="280af-113">**Request URI**</span></span>|<span data-ttu-id="280af-114">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="280af-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="280af-115">Erhalten</span><span class="sxs-lookup"><span data-stu-id="280af-115">GET</span></span>  <br/> |<span data-ttu-id="280af-116">https://\<-\>Portal/QoERepositoryService/Repository/itemAncestors/{Itemid}</span><span class="sxs-lookup"><span data-stu-id="280af-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="280af-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="280af-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="280af-118">**URI-Parameter** -None.</span><span class="sxs-lookup"><span data-stu-id="280af-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="280af-119">**Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="280af-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="280af-120">**Anforderungstext** – keine.</span><span class="sxs-lookup"><span data-stu-id="280af-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="280af-121">**Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.</span><span class="sxs-lookup"><span data-stu-id="280af-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="280af-122">**Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.</span><span class="sxs-lookup"><span data-stu-id="280af-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="280af-123">Wenn keine angegebene Benutzer-ID gefunden wird, wird der Statuscode 404 (nicht gefunden) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="280af-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="280af-124">**Antwortheader** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="280af-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="280af-125">**Antworttext** : Nachfolgend finden Sie eine Beispielantwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="280af-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
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

 <span data-ttu-id="280af-126">*Element1* -ID des Elements.</span><span class="sxs-lookup"><span data-stu-id="280af-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="280af-127">*Element2* -depth ist der Abstand vom Element.</span><span class="sxs-lookup"><span data-stu-id="280af-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="280af-128">0 ist das unmittelbar übergeordnete Element.</span><span class="sxs-lookup"><span data-stu-id="280af-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="280af-129">*Item3* -Titel des Elements.</span><span class="sxs-lookup"><span data-stu-id="280af-129">*Item3*  - Title of the item.</span></span>
  

