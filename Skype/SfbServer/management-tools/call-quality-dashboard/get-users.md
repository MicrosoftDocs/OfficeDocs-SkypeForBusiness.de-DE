---
title: Abrufen von Benutzern
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang zum Abrufen von Benutzern, der Teil des Benutzer Diensts ist. Der Benutzer Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 22223c37dad39f171afc27eb9e0520b8b32335c5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274646"
---
# <a name="get-users"></a><span data-ttu-id="045bb-105">Abrufen von Benutzern</span><span class="sxs-lookup"><span data-stu-id="045bb-105">Get Users</span></span>
 
<span data-ttu-id="045bb-106">**Zusammenfassung:** Informieren Sie sich über den Vorgang zum Abrufen von Benutzern, der Teil des Benutzer Diensts ist.</span><span class="sxs-lookup"><span data-stu-id="045bb-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="045bb-107">Der Benutzer Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard.</span><span class="sxs-lookup"><span data-stu-id="045bb-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="045bb-108">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="045bb-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="045bb-109">Der Vorgang zum Abrufen von Benutzern ist Teil des Benutzer Diensts in der Repository-API für die Anruf Qualitätssteuerung.</span><span class="sxs-lookup"><span data-stu-id="045bb-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="045bb-110">Abrufen von Benutzern</span><span class="sxs-lookup"><span data-stu-id="045bb-110">Get Users</span></span>

<span data-ttu-id="045bb-111">Benutzer abrufen gibt eine Liste der Benutzer im Repository zurück.</span><span class="sxs-lookup"><span data-stu-id="045bb-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="045bb-112">**Methode**</span><span class="sxs-lookup"><span data-stu-id="045bb-112">**Method**</span></span>|<span data-ttu-id="045bb-113">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="045bb-113">**Request URI**</span></span>|<span data-ttu-id="045bb-114">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="045bb-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="045bb-115">Erhalten</span><span class="sxs-lookup"><span data-stu-id="045bb-115">GET</span></span>  <br/> |<span data-ttu-id="045bb-116">https://\<-\>Portal/QoERepositoryService/Repository/User</span><span class="sxs-lookup"><span data-stu-id="045bb-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="045bb-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="045bb-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="045bb-118">**URI-Parameter** -None.</span><span class="sxs-lookup"><span data-stu-id="045bb-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="045bb-119">**Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="045bb-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="045bb-120">**Anforderungstext** – keine.</span><span class="sxs-lookup"><span data-stu-id="045bb-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="045bb-121">**Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.</span><span class="sxs-lookup"><span data-stu-id="045bb-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="045bb-122">**Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.</span><span class="sxs-lookup"><span data-stu-id="045bb-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="045bb-123">**Antwortheader** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="045bb-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="045bb-124">**Antworttext** : Nachfolgend finden Sie eine Beispielantwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="045bb-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="045bb-125">Ein Array von Benutzerobjekten wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="045bb-125">An array of User objects is returned.</span></span> <span data-ttu-id="045bb-126">Details zum Benutzerobjekt finden Sie unter Abrufen von Benutzern.</span><span class="sxs-lookup"><span data-stu-id="045bb-126">For details about the User object, see Get User.</span></span> 
  
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


