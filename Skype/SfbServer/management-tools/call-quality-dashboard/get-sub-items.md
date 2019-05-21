---
title: Abrufen von untergeordneten Elementen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang "untergeordnete Elemente abrufen", der Teil des Element Diensts ist. Der Element Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 7be427ed4ea90cd46c6f8cea4ffe3a97be98479b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274660"
---
# <a name="get-sub-items"></a><span data-ttu-id="4996a-105">Abrufen von untergeordneten Elementen</span><span class="sxs-lookup"><span data-stu-id="4996a-105">Get Sub-Items</span></span>
 
<span data-ttu-id="4996a-106">**Zusammenfassung:** Informieren Sie sich über den Vorgang "untergeordnete Elemente abrufen", der Teil des Element Diensts ist.</span><span class="sxs-lookup"><span data-stu-id="4996a-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="4996a-107">Der Element Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard.</span><span class="sxs-lookup"><span data-stu-id="4996a-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="4996a-108">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4996a-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="4996a-109">Der Vorgang "untergeordnete Elemente abrufen" ist Teil des Element Diensts in der Repository-API für das Dashboard für die Anrufqualität.</span><span class="sxs-lookup"><span data-stu-id="4996a-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="4996a-110">Abrufen von untergeordneten Elementen</span><span class="sxs-lookup"><span data-stu-id="4996a-110">Get Sub-Items</span></span>

<span data-ttu-id="4996a-111">Abrufen untergeordneter Elemente gibt die untergeordneten Elemente eines bestimmten Elements zurück.</span><span class="sxs-lookup"><span data-stu-id="4996a-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="4996a-112">**Methode**</span><span class="sxs-lookup"><span data-stu-id="4996a-112">**Method**</span></span>|<span data-ttu-id="4996a-113">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="4996a-113">**Request URI**</span></span>|<span data-ttu-id="4996a-114">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="4996a-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4996a-115">Erhalten</span><span class="sxs-lookup"><span data-stu-id="4996a-115">GET</span></span>  <br/> |<span data-ttu-id="4996a-116">https://\<-\>Portal/QoERepositoryService/Repository/Item/{Itemid}/SubItem</span><span class="sxs-lookup"><span data-stu-id="4996a-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="4996a-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="4996a-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="4996a-118">**URI-Parameter** -None.</span><span class="sxs-lookup"><span data-stu-id="4996a-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="4996a-119">**Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="4996a-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="4996a-120">**Anforderungstext** – keine.</span><span class="sxs-lookup"><span data-stu-id="4996a-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="4996a-121">**Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.</span><span class="sxs-lookup"><span data-stu-id="4996a-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="4996a-122">**Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.</span><span class="sxs-lookup"><span data-stu-id="4996a-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="4996a-123">Wenn keine angegebene Benutzer-ID gefunden wird, wird der Statuscode 404 (nicht gefunden) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4996a-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="4996a-124">**Antwortheader** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="4996a-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="4996a-125">**Antworttext** : Nachfolgend finden Sie eine Beispielantwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="4996a-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4996a-126">Ein Array von Item-Objekt wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4996a-126">An array of Item object is returned.</span></span> 
  
```
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

<span data-ttu-id="4996a-127">Das vom Unterelement Vorgang zurückgegebene Element Objekt enthält nur die folgenden drei Felder.</span><span class="sxs-lookup"><span data-stu-id="4996a-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="4996a-128">*ItemID* -ID des Elements.</span><span class="sxs-lookup"><span data-stu-id="4996a-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="4996a-129">*UserID* -ID des Benutzers, der Besitzer dieses Elements ist.</span><span class="sxs-lookup"><span data-stu-id="4996a-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="4996a-130">*Type* – der Typ des Inhalts.</span><span class="sxs-lookup"><span data-stu-id="4996a-130">*type*  - The type of the content.</span></span> <span data-ttu-id="4996a-131">Dieses Feld wird von den Anwendungen gesetzt.</span><span class="sxs-lookup"><span data-stu-id="4996a-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="4996a-132">`Content`und `subItems` Felder werden in der Antwort nicht berücksichtigt, um die Datenmenge zu verringern, die über das Netzwerk übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="4996a-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

