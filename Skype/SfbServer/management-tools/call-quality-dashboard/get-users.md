---
title: Abrufen von Benutzern
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Zusammenfassung: Informationen Sie zum Vorgang Benutzer abrufen, der Teil der Benutzerdienst ist. Der Benutzer-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: 4f3c1a00134cb0f8276d511d80ae7bc6f82f2d72
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897331"
---
# <a name="get-users"></a><span data-ttu-id="6a47d-105">Abrufen von Benutzern</span><span class="sxs-lookup"><span data-stu-id="6a47d-105">Get Users</span></span>
 
<span data-ttu-id="6a47d-106">**Zusammenfassung:** Informationen Sie zu den Vorgang erhalten Benutzer, der Teil der Benutzerdienst ist.</span><span class="sxs-lookup"><span data-stu-id="6a47d-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="6a47d-107">Der Benutzer-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="6a47d-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="6a47d-108">Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="6a47d-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="6a47d-109">Der Benutzer abrufen-Vorgang ist Teil des Dienstes Benutzer in der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="6a47d-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="6a47d-110">Abrufen von Benutzern</span><span class="sxs-lookup"><span data-stu-id="6a47d-110">Get Users</span></span>

<span data-ttu-id="6a47d-111">Rufen Sie Benutzer gibt eine Liste der Benutzer im Repository.</span><span class="sxs-lookup"><span data-stu-id="6a47d-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="6a47d-112">**Methode**</span><span class="sxs-lookup"><span data-stu-id="6a47d-112">**Method**</span></span>|<span data-ttu-id="6a47d-113">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="6a47d-113">**Request URI**</span></span>|<span data-ttu-id="6a47d-114">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="6a47d-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6a47d-115">Erhalten</span><span class="sxs-lookup"><span data-stu-id="6a47d-115">GET</span></span>  <br/> |<span data-ttu-id="6a47d-116">https://\<Portal\>/QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="6a47d-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="6a47d-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="6a47d-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="6a47d-118">**URI-Parameter** - None.</span><span class="sxs-lookup"><span data-stu-id="6a47d-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="6a47d-119">**Anfordern von Kopfzeilen** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="6a47d-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6a47d-120">**Anforderungstextkörper** – None.</span><span class="sxs-lookup"><span data-stu-id="6a47d-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="6a47d-121">**Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.</span><span class="sxs-lookup"><span data-stu-id="6a47d-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="6a47d-122">**Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="6a47d-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="6a47d-123">**Antwortheader** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="6a47d-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6a47d-124">**Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="6a47d-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6a47d-125">Es wird ein Array von User-Objekte zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6a47d-125">An array of User objects is returned.</span></span> <span data-ttu-id="6a47d-126">Ausführliche Informationen über das Benutzerobjekt finden Sie unter Benutzer abrufen.</span><span class="sxs-lookup"><span data-stu-id="6a47d-126">For details about the User object, see Get User.</span></span> 
  
```
[{
"userId": 0,
"loginName": "system",
"defaultItemId": 1652
},
{
"userId": 1,
"loginName": "SAMPLEDOMAIN\\testuser1",
"defaultItemId": 1652
},
{
"userId": 2,
"loginName": "SAMPLEDOMAIN\\testuser2",
"defaultItemId": 1774
}]
```


