---
title: Abrufen von Benutzern
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Zusammenfassung: Informationen Sie zum Vorgang Benutzer abrufen, der Teil der Benutzerdienst ist. Der Benutzer-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.'
ms.openlocfilehash: ed26614c0fd4b443e9c5d698d1db9467291ca3d0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="get-users"></a><span data-ttu-id="c8f24-105">Abrufen von Benutzern</span><span class="sxs-lookup"><span data-stu-id="c8f24-105">Get Users</span></span>
 
<span data-ttu-id="c8f24-106">**Zusammenfassung:** Informationen Sie zu den Vorgang erhalten Benutzer, der Teil der Benutzerdienst ist.</span><span class="sxs-lookup"><span data-stu-id="c8f24-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="c8f24-107">Der Benutzer-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c8f24-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="c8f24-108">Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c8f24-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c8f24-109">Der Benutzer abrufen-Vorgang ist Teil des Dienstes Benutzer in der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c8f24-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="c8f24-110">Abrufen von Benutzern</span><span class="sxs-lookup"><span data-stu-id="c8f24-110">Get Users</span></span>

<span data-ttu-id="c8f24-111">Rufen Sie Benutzer gibt eine Liste der Benutzer im Repository.</span><span class="sxs-lookup"><span data-stu-id="c8f24-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="c8f24-112">**Methode**</span><span class="sxs-lookup"><span data-stu-id="c8f24-112">**Method**</span></span>|<span data-ttu-id="c8f24-113">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="c8f24-113">**Request URI**</span></span>|<span data-ttu-id="c8f24-114">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="c8f24-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c8f24-115">Erhalten</span><span class="sxs-lookup"><span data-stu-id="c8f24-115">GET</span></span>  <br/> |<span data-ttu-id="c8f24-116">https://\<Portal\>/QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="c8f24-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="c8f24-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="c8f24-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="c8f24-118">**URI-Parameter** - None.</span><span class="sxs-lookup"><span data-stu-id="c8f24-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="c8f24-119">**Anfordern von Kopfzeilen** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="c8f24-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c8f24-120">**Anforderungstextkörper** – None.</span><span class="sxs-lookup"><span data-stu-id="c8f24-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="c8f24-121">**Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.</span><span class="sxs-lookup"><span data-stu-id="c8f24-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="c8f24-122">**Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="c8f24-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="c8f24-123">**Antwortheader** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="c8f24-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c8f24-124">**Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="c8f24-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c8f24-125">Es wird ein Array von User-Objekte zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c8f24-125">An array of User objects is returned.</span></span> <span data-ttu-id="c8f24-126">Ausführliche Informationen über das Benutzerobjekt finden Sie unter Benutzer abrufen.</span><span class="sxs-lookup"><span data-stu-id="c8f24-126">For details about the User object, see Get User.</span></span> 
  
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


