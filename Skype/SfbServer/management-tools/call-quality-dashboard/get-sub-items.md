---
title: Abrufen von untergeordneten Elementen
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
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang "untergeordnete Elemente abrufen", der Teil des Element Diensts ist. Der Element Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 523a6050065680550685337dabfec72c87f30bf7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816764"
---
# <a name="get-sub-items"></a><span data-ttu-id="be753-105">Abrufen von untergeordneten Elementen</span><span class="sxs-lookup"><span data-stu-id="be753-105">Get Sub-Items</span></span>
 
<span data-ttu-id="be753-106">**Zusammenfassung:** Informieren Sie sich über den Vorgang "untergeordnete Elemente abrufen", der Teil des Element Diensts ist.</span><span class="sxs-lookup"><span data-stu-id="be753-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="be753-107">Der Element Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard.</span><span class="sxs-lookup"><span data-stu-id="be753-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="be753-108">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="be753-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="be753-109">Der Vorgang "untergeordnete Elemente abrufen" ist Teil des Element Diensts in der Repository-API für das Dashboard für die Anrufqualität.</span><span class="sxs-lookup"><span data-stu-id="be753-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="be753-110">Abrufen von untergeordneten Elementen</span><span class="sxs-lookup"><span data-stu-id="be753-110">Get Sub-Items</span></span>

<span data-ttu-id="be753-111">Abrufen untergeordneter Elemente gibt die untergeordneten Elemente eines bestimmten Elements zurück.</span><span class="sxs-lookup"><span data-stu-id="be753-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="be753-112">**Methode**</span><span class="sxs-lookup"><span data-stu-id="be753-112">**Method**</span></span>|<span data-ttu-id="be753-113">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="be753-113">**Request URI**</span></span>|<span data-ttu-id="be753-114">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="be753-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="be753-115">Erhalten</span><span class="sxs-lookup"><span data-stu-id="be753-115">GET</span></span>  <br/> |<span data-ttu-id="be753-116">https://\<-\>Portal/QoERepositoryService/Repository/Item/{Itemid}/SubItem</span><span class="sxs-lookup"><span data-stu-id="be753-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="be753-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="be753-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="be753-118">**URI-Parameter** -None.</span><span class="sxs-lookup"><span data-stu-id="be753-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="be753-119">**Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="be753-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="be753-120">**Anforderungstext** – keine.</span><span class="sxs-lookup"><span data-stu-id="be753-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="be753-121">**Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.</span><span class="sxs-lookup"><span data-stu-id="be753-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="be753-122">**Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.</span><span class="sxs-lookup"><span data-stu-id="be753-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="be753-123">Wenn keine angegebene Benutzer-ID gefunden wird, wird der Statuscode 404 (nicht gefunden) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="be753-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="be753-124">**Antwortheader** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="be753-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="be753-125">**Antworttext** : Nachfolgend finden Sie eine Beispielantwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="be753-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="be753-126">Ein Array von Item-Objekt wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="be753-126">An array of Item object is returned.</span></span> 
  
```json
[{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1710,
"userId": 0,
"type": "json"
}]
```

<span data-ttu-id="be753-127">Das vom Unterelement Vorgang zurückgegebene Element Objekt enthält nur die folgenden drei Felder.</span><span class="sxs-lookup"><span data-stu-id="be753-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="be753-128">*ItemID* -ID des Elements.</span><span class="sxs-lookup"><span data-stu-id="be753-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="be753-129">*UserID* -ID des Benutzers, der Besitzer dieses Elements ist.</span><span class="sxs-lookup"><span data-stu-id="be753-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="be753-130">*Type* – der Typ des Inhalts.</span><span class="sxs-lookup"><span data-stu-id="be753-130">*type*  - The type of the content.</span></span> <span data-ttu-id="be753-131">Dieses Feld wird von den Anwendungen gesetzt.</span><span class="sxs-lookup"><span data-stu-id="be753-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="be753-132">`Content`und `subItems` Felder werden in der Antwort nicht berücksichtigt, um die Datenmenge zu verringern, die über das Netzwerk übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="be753-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

