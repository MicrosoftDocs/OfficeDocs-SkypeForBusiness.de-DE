---
title: Abrufen eines Elements
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang "Element abrufen", der Teil des Element Diensts ist. Der Element Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: bfd5015603ac73fb48c4e30635cf8ae0fb14bf13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274716"
---
# <a name="get-item"></a><span data-ttu-id="73896-105">Abrufen eines Elements</span><span class="sxs-lookup"><span data-stu-id="73896-105">Get Item</span></span>
 
<span data-ttu-id="73896-106">**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Element abrufen", der Teil des Element Diensts ist.</span><span class="sxs-lookup"><span data-stu-id="73896-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="73896-107">Der Element Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard.</span><span class="sxs-lookup"><span data-stu-id="73896-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="73896-108">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="73896-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="73896-109">Der Vorgang "Element abrufen" ist Teil des Element Diensts in der Repository-API für die Anruf Qualitätssteuerung.</span><span class="sxs-lookup"><span data-stu-id="73896-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="73896-110">Abrufen eines Elements</span><span class="sxs-lookup"><span data-stu-id="73896-110">Get Item</span></span>

<span data-ttu-id="73896-111">Get Item gibt ein bestimmtes Element im Repository zurück.</span><span class="sxs-lookup"><span data-stu-id="73896-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="73896-112">**Methode**</span><span class="sxs-lookup"><span data-stu-id="73896-112">**Method**</span></span>|<span data-ttu-id="73896-113">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="73896-113">**Request URI**</span></span>|<span data-ttu-id="73896-114">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="73896-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="73896-115">Erhalten</span><span class="sxs-lookup"><span data-stu-id="73896-115">GET</span></span>  <br/> |<span data-ttu-id="73896-116">https://\<-\>Portal/QoERepositoryService/Repository/Item/{Itemid}</span><span class="sxs-lookup"><span data-stu-id="73896-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="73896-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="73896-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="73896-118">**URI-Parameter** -None.</span><span class="sxs-lookup"><span data-stu-id="73896-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="73896-119">**Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="73896-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="73896-120">**Anforderungstext** – keine.</span><span class="sxs-lookup"><span data-stu-id="73896-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="73896-121">**Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.</span><span class="sxs-lookup"><span data-stu-id="73896-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="73896-122">**Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.</span><span class="sxs-lookup"><span data-stu-id="73896-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="73896-123">Wenn keine angegebene Element-ID gefunden wird, wird der Statuscode 404 (nicht gefunden) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="73896-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="73896-124">**Antwortheader** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="73896-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="73896-125">**Antworttext** : Nachfolgend finden Sie eine Beispielantwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="73896-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="73896-126">*ItemID* -ID des Elements.</span><span class="sxs-lookup"><span data-stu-id="73896-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="73896-127">*UserID* -ID des Benutzers, der Besitzer dieses Elements ist.</span><span class="sxs-lookup"><span data-stu-id="73896-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="73896-128">*Inhalt* – der anwendungsspezifische Inhalt.</span><span class="sxs-lookup"><span data-stu-id="73896-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="73896-129">*Type* – der Typ des Inhalts.</span><span class="sxs-lookup"><span data-stu-id="73896-129">*type*  - The type of the content.</span></span> <span data-ttu-id="73896-130">Dieses Feld wird von den Anwendungen gesetzt.</span><span class="sxs-lookup"><span data-stu-id="73896-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="73896-131">\*\* subitemids-die IDs der untergeordneten Elemente (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="73896-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="73896-132">Hierbei handelt es sich um einen Kurzschluss des Vorgangs "untergeordnete Elemente abrufen", um einen Anruf zu speichern.</span><span class="sxs-lookup"><span data-stu-id="73896-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="73896-133">Anwendungen können die gleichen Informationen auch mithilfe von untergeordneten Elementen abrufen.</span><span class="sxs-lookup"><span data-stu-id="73896-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

