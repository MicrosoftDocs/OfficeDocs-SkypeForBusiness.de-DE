---
title: Abrufen eines Elements
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang "Element abrufen", der Teil des Element Diensts ist. Der Element Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 295276e6f3b0f577dae9a43c4c0f62e23b8582f4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816794"
---
# <a name="get-item"></a><span data-ttu-id="d56c0-105">Abrufen eines Elements</span><span class="sxs-lookup"><span data-stu-id="d56c0-105">Get Item</span></span>
 
<span data-ttu-id="d56c0-106">**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Element abrufen", der Teil des Element Diensts ist.</span><span class="sxs-lookup"><span data-stu-id="d56c0-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="d56c0-107">Der Element Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard.</span><span class="sxs-lookup"><span data-stu-id="d56c0-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="d56c0-108">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d56c0-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="d56c0-109">Der Vorgang "Element abrufen" ist Teil des Element Diensts in der Repository-API für die Anruf Qualitätssteuerung.</span><span class="sxs-lookup"><span data-stu-id="d56c0-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="d56c0-110">Abrufen eines Elements</span><span class="sxs-lookup"><span data-stu-id="d56c0-110">Get Item</span></span>

<span data-ttu-id="d56c0-111">Get Item gibt ein bestimmtes Element im Repository zurück.</span><span class="sxs-lookup"><span data-stu-id="d56c0-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="d56c0-112">**Methode**</span><span class="sxs-lookup"><span data-stu-id="d56c0-112">**Method**</span></span>|<span data-ttu-id="d56c0-113">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="d56c0-113">**Request URI**</span></span>|<span data-ttu-id="d56c0-114">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="d56c0-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d56c0-115">Erhalten</span><span class="sxs-lookup"><span data-stu-id="d56c0-115">GET</span></span>  <br/> |<span data-ttu-id="d56c0-116">https://\<-\>Portal/QoERepositoryService/Repository/Item/{Itemid}</span><span class="sxs-lookup"><span data-stu-id="d56c0-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="d56c0-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="d56c0-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="d56c0-118">**URI-Parameter** -None.</span><span class="sxs-lookup"><span data-stu-id="d56c0-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="d56c0-119">**Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="d56c0-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="d56c0-120">**Anforderungstext** – keine.</span><span class="sxs-lookup"><span data-stu-id="d56c0-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="d56c0-121">**Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.</span><span class="sxs-lookup"><span data-stu-id="d56c0-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="d56c0-122">**Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.</span><span class="sxs-lookup"><span data-stu-id="d56c0-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="d56c0-123">Wenn keine angegebene Element-ID gefunden wird, wird der Statuscode 404 (nicht gefunden) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d56c0-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="d56c0-124">**Antwortheader** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="d56c0-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="d56c0-125">**Antworttext** : Nachfolgend finden Sie eine Beispielantwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="d56c0-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="d56c0-126">*ItemID* -ID des Elements.</span><span class="sxs-lookup"><span data-stu-id="d56c0-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="d56c0-127">*UserID* -ID des Benutzers, der Besitzer dieses Elements ist.</span><span class="sxs-lookup"><span data-stu-id="d56c0-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="d56c0-128">*Inhalt* – der anwendungsspezifische Inhalt.</span><span class="sxs-lookup"><span data-stu-id="d56c0-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="d56c0-129">*Type* – der Typ des Inhalts.</span><span class="sxs-lookup"><span data-stu-id="d56c0-129">*type*  - The type of the content.</span></span> <span data-ttu-id="d56c0-130">Dieses Feld wird von den Anwendungen gesetzt.</span><span class="sxs-lookup"><span data-stu-id="d56c0-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="d56c0-131">*subitemids* -die IDs der untergeordneten Elemente (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="d56c0-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="d56c0-132">Hierbei handelt es sich um einen Kurzschluss des Vorgangs "untergeordnete Elemente abrufen", um einen Anruf zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d56c0-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="d56c0-133">Anwendungen können die gleichen Informationen auch mithilfe von untergeordneten Elementen abrufen.</span><span class="sxs-lookup"><span data-stu-id="d56c0-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

