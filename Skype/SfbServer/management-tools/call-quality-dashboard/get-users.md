---
title: Abrufen von Benutzern
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Zusammenfassung: Informationen Sie zum Vorgang Benutzer abrufen, der Teil der Benutzerdienst ist. Der Benutzer-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: 11c4e8d1230385f51992dac7559d65ddc2ec4ac0
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035638"
---
# <a name="get-users"></a><span data-ttu-id="63607-105">Abrufen von Benutzern</span><span class="sxs-lookup"><span data-stu-id="63607-105">Get Users</span></span>
 
<span data-ttu-id="63607-106">**Zusammenfassung:** Informationen Sie zu den Vorgang erhalten Benutzer, der Teil der Benutzerdienst ist.</span><span class="sxs-lookup"><span data-stu-id="63607-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="63607-107">Der Benutzer-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="63607-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="63607-108">Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="63607-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="63607-109">Der Benutzer abrufen-Vorgang ist Teil des Dienstes Benutzer in der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="63607-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="63607-110">Abrufen von Benutzern</span><span class="sxs-lookup"><span data-stu-id="63607-110">Get Users</span></span>

<span data-ttu-id="63607-111">Rufen Sie Benutzer gibt eine Liste der Benutzer im Repository.</span><span class="sxs-lookup"><span data-stu-id="63607-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="63607-112">**Methode**</span><span class="sxs-lookup"><span data-stu-id="63607-112">**Method**</span></span>|<span data-ttu-id="63607-113">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="63607-113">**Request URI**</span></span>|<span data-ttu-id="63607-114">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="63607-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="63607-115">Erhalten</span><span class="sxs-lookup"><span data-stu-id="63607-115">GET</span></span>  <br/> |<span data-ttu-id="63607-116">https://\<Portal\>/QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="63607-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="63607-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="63607-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="63607-118">**URI-Parameter** - None.</span><span class="sxs-lookup"><span data-stu-id="63607-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="63607-119">**Anfordern von Kopfzeilen** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="63607-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="63607-120">**Anforderungstextkörper** – None.</span><span class="sxs-lookup"><span data-stu-id="63607-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="63607-121">**Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.</span><span class="sxs-lookup"><span data-stu-id="63607-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="63607-122">**Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="63607-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="63607-123">**Antwortheader** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="63607-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="63607-124">**Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="63607-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="63607-125">Es wird ein Array von User-Objekte zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="63607-125">An array of User objects is returned.</span></span> <span data-ttu-id="63607-126">Ausführliche Informationen über das Benutzerobjekt finden Sie unter Benutzer abrufen.</span><span class="sxs-lookup"><span data-stu-id="63607-126">For details about the User object, see Get User.</span></span> 
  
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


