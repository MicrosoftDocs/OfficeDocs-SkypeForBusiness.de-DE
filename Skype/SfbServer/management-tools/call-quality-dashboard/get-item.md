---
title: Element abrufen
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Zusammenfassung: Informationen Sie zum Vorgang Element abrufen, der Teil der Element-Dienst ist. Der Element-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: 12b52bdd51e8ba59f1aa90e2a366b3e11fb54805
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532362"
---
# <a name="get-item"></a><span data-ttu-id="4d21c-105">Element abrufen</span><span class="sxs-lookup"><span data-stu-id="4d21c-105">Get Item</span></span>
 
<span data-ttu-id="4d21c-106">**Zusammenfassung:** Informationen Sie zum Vorgang Element abrufen, der Teil der Element-Dienst ist.</span><span class="sxs-lookup"><span data-stu-id="4d21c-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="4d21c-107">Der Element-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4d21c-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="4d21c-108">Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="4d21c-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="4d21c-109">Der Vorgang Element abrufen ist Teil des Diensts Element in der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4d21c-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="4d21c-110">Element abrufen</span><span class="sxs-lookup"><span data-stu-id="4d21c-110">Get Item</span></span>

<span data-ttu-id="4d21c-111">Rufen Sie gibt ein bestimmtes Element im Repository.</span><span class="sxs-lookup"><span data-stu-id="4d21c-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="4d21c-112">**Methode**</span><span class="sxs-lookup"><span data-stu-id="4d21c-112">**Method**</span></span>|<span data-ttu-id="4d21c-113">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="4d21c-113">**Request URI**</span></span>|<span data-ttu-id="4d21c-114">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="4d21c-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4d21c-115">Erhalten</span><span class="sxs-lookup"><span data-stu-id="4d21c-115">GET</span></span>  <br/> |<span data-ttu-id="4d21c-116">https://\<Portal\>/QoERepositoryService/Repository/Element / {ItemId}</span><span class="sxs-lookup"><span data-stu-id="4d21c-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="4d21c-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="4d21c-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="4d21c-118">**URI-Parameter** - None.</span><span class="sxs-lookup"><span data-stu-id="4d21c-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="4d21c-119">**Anfordern von Kopfzeilen** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="4d21c-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="4d21c-120">**Anforderungstextkörper** – None.</span><span class="sxs-lookup"><span data-stu-id="4d21c-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="4d21c-121">**Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.</span><span class="sxs-lookup"><span data-stu-id="4d21c-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="4d21c-122">**Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="4d21c-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="4d21c-123">Wenn eine angegebenes Element-ID nicht gefunden wird, wird der Statuscode 404 (nicht gefunden) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4d21c-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="4d21c-124">**Antwortheader** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="4d21c-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="4d21c-125">**Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="4d21c-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="4d21c-126">*ItemId* - ID des Elements.</span><span class="sxs-lookup"><span data-stu-id="4d21c-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="4d21c-127">*UserId* - ID des Benutzers, der dieses Element gehört.</span><span class="sxs-lookup"><span data-stu-id="4d21c-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="4d21c-128">*Content* - anwendungsspezifischen-Inhalt.</span><span class="sxs-lookup"><span data-stu-id="4d21c-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="4d21c-129">*Typ* – der Typ des Inhalts.</span><span class="sxs-lookup"><span data-stu-id="4d21c-129">*type*  - The type of the content.</span></span> <span data-ttu-id="4d21c-130">Dieses Feld wird durch die Anwendung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4d21c-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="4d21c-131">*SubItemIds* - die IDs der untergeordneten Elemente, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="4d21c-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="4d21c-132">Hierbei handelt es sich um einen Kurzschluss des Vorgangs untergeordnete Elemente abrufen, um einen Anruf zu speichern.</span><span class="sxs-lookup"><span data-stu-id="4d21c-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="4d21c-133">Anwendungen können alternativ mit untergeordneten Elemente abrufen-Operation dieselbe Informationen abrufen.</span><span class="sxs-lookup"><span data-stu-id="4d21c-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

