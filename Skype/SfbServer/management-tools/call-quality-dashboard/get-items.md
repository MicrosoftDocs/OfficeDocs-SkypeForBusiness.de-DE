---
title: Abrufen von Elementen
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
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang zum Abrufen von Elementen, der Teil des Element Diensts ist. Der Element Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 6345201fe3843e3fe8cf6671f01d2db30fb4e22e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816784"
---
# <a name="get-items"></a><span data-ttu-id="cc8d7-105">Abrufen von Elementen</span><span class="sxs-lookup"><span data-stu-id="cc8d7-105">Get Items</span></span>
 
<span data-ttu-id="cc8d7-106">**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Elemente abrufen", der Teil des Element Diensts ist.</span><span class="sxs-lookup"><span data-stu-id="cc8d7-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="cc8d7-107">Der Element Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard.</span><span class="sxs-lookup"><span data-stu-id="cc8d7-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="cc8d7-108">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cc8d7-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="cc8d7-109">Der Vorgang zum Abrufen von Elementen ist Teil des Element Diensts in der Repository-API für die Anruf Qualitätssteuerung.</span><span class="sxs-lookup"><span data-stu-id="cc8d7-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="cc8d7-110">Abrufen von Elementen</span><span class="sxs-lookup"><span data-stu-id="cc8d7-110">Get Items</span></span>

<span data-ttu-id="cc8d7-111">Elemente abrufen gibt alle Elemente im Repository zurück.</span><span class="sxs-lookup"><span data-stu-id="cc8d7-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="cc8d7-112">**Methode**</span><span class="sxs-lookup"><span data-stu-id="cc8d7-112">**Method**</span></span>|<span data-ttu-id="cc8d7-113">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="cc8d7-113">**Request URI**</span></span>|<span data-ttu-id="cc8d7-114">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="cc8d7-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cc8d7-115">Erhalten</span><span class="sxs-lookup"><span data-stu-id="cc8d7-115">GET</span></span>  <br/> |<span data-ttu-id="cc8d7-116">https://\<-\>Portal/QoERepositoryService/Repository/Item</span><span class="sxs-lookup"><span data-stu-id="cc8d7-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="cc8d7-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="cc8d7-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="cc8d7-118">**URI-Parameter** -None.</span><span class="sxs-lookup"><span data-stu-id="cc8d7-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="cc8d7-119">**Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="cc8d7-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="cc8d7-120">**Anforderungstext** – keine.</span><span class="sxs-lookup"><span data-stu-id="cc8d7-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="cc8d7-121">**Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.</span><span class="sxs-lookup"><span data-stu-id="cc8d7-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="cc8d7-122">**Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.</span><span class="sxs-lookup"><span data-stu-id="cc8d7-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="cc8d7-123">**Antwortheader** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="cc8d7-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="cc8d7-124">**Antworttext** : Nachfolgend finden Sie eine Beispielantwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="cc8d7-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cc8d7-125">Ein Array von Item-Objekten wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cc8d7-125">An array of Item objects is returned.</span></span> <span data-ttu-id="cc8d7-126">Details zu Item-Objekten finden Sie unter Abrufen von Elementen.</span><span class="sxs-lookup"><span data-stu-id="cc8d7-126">For details about Item object, see Get Item.</span></span> 
  
```json
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
