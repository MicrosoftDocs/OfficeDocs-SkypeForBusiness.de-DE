---
title: Untergeordnete Elemente abrufen
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Zusammenfassung: Informationen Sie zum Vorgang untergeordnete Elemente abrufen, der Teil der Element-Dienst ist. Der Element-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.'
ms.openlocfilehash: f125a10ac9d3f608216ea23d17f614d0bff88af7
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295939"
---
# <a name="get-sub-items"></a><span data-ttu-id="118c9-105">Untergeordnete Elemente abrufen</span><span class="sxs-lookup"><span data-stu-id="118c9-105">Get Sub-Items</span></span>
 
<span data-ttu-id="118c9-106">**Zusammenfassung:** Informationen Sie zu den Vorgang untergeordnete Elemente abrufen, der Teil der Element-Dienst ist.</span><span class="sxs-lookup"><span data-stu-id="118c9-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="118c9-107">Der Element-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="118c9-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="118c9-108">Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="118c9-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="118c9-109">Der untergeordneten Elemente abrufen Vorgang ist Teil des Diensts Element in der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="118c9-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="118c9-110">Untergeordnete Elemente abrufen</span><span class="sxs-lookup"><span data-stu-id="118c9-110">Get Sub-Items</span></span>

<span data-ttu-id="118c9-111">Rufen Sie ein bestimmtes Element Unterelemente Unterelemente gibt.</span><span class="sxs-lookup"><span data-stu-id="118c9-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="118c9-112">**Methode**</span><span class="sxs-lookup"><span data-stu-id="118c9-112">**Method**</span></span>|<span data-ttu-id="118c9-113">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="118c9-113">**Request URI**</span></span>|<span data-ttu-id="118c9-114">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="118c9-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="118c9-115">Erhalten</span><span class="sxs-lookup"><span data-stu-id="118c9-115">GET</span></span>  <br/> |<span data-ttu-id="118c9-116">https://\<Portal\>/QoERepositoryService/Repository/Element / {ItemId} / subitem</span><span class="sxs-lookup"><span data-stu-id="118c9-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="118c9-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="118c9-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="118c9-118">**URI-Parameter** - None.</span><span class="sxs-lookup"><span data-stu-id="118c9-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="118c9-119">**Anfordern von Kopfzeilen** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="118c9-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="118c9-120">**Anforderungstextkörper** – None.</span><span class="sxs-lookup"><span data-stu-id="118c9-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="118c9-121">**Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.</span><span class="sxs-lookup"><span data-stu-id="118c9-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="118c9-122">**Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="118c9-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="118c9-123">Wenn einen angegebenen Benutzer-ID nicht gefunden wurde, wird der Statuscode 404 (nicht gefunden) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="118c9-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="118c9-124">**Antwortheader** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="118c9-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="118c9-125">**Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="118c9-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="118c9-126">Ein Array von Item-Objekt wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="118c9-126">An array of Item object is returned.</span></span> 
  
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

<span data-ttu-id="118c9-127">Item-Objekts zurückgegebenen Elemente Vorgang enthält nur die folgenden drei Felder.</span><span class="sxs-lookup"><span data-stu-id="118c9-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="118c9-128">*ItemId* - ID des Elements.</span><span class="sxs-lookup"><span data-stu-id="118c9-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="118c9-129">*UserId* - ID des Benutzers, der dieses Element gehört.</span><span class="sxs-lookup"><span data-stu-id="118c9-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="118c9-130">*Typ* – der Typ des Inhalts.</span><span class="sxs-lookup"><span data-stu-id="118c9-130">*type*  - The type of the content.</span></span> <span data-ttu-id="118c9-131">Dieses Feld wird durch die Anwendung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="118c9-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="118c9-132">`Content`und `subItems` Felder sind nicht enthalten, die als Antwort auf die über das Netzwerk übertragen Datenmenge zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="118c9-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

