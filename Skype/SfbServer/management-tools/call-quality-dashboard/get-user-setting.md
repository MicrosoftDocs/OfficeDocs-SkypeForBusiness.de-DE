---
title: Abrufen einer Benutzereinstellung
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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang zum Abrufen der Benutzereinstellung, der Teil des Benutzer Einstellungs Diensts ist. Der Benutzer Einstellungsdienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 4ab9d4d718a2ff411db72f38b59a758523935504
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816754"
---
# <a name="get-user-setting"></a><span data-ttu-id="96bc6-105">Abrufen einer Benutzereinstellung</span><span class="sxs-lookup"><span data-stu-id="96bc6-105">Get User Setting</span></span>
 
<span data-ttu-id="96bc6-106">**Zusammenfassung:** Informieren Sie sich über den Vorgang zum Abrufen der Benutzereinstellung, der Teil des Benutzer Einstellungs Diensts ist.</span><span class="sxs-lookup"><span data-stu-id="96bc6-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="96bc6-107">Der Benutzer Einstellungsdienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard.</span><span class="sxs-lookup"><span data-stu-id="96bc6-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="96bc6-108">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="96bc6-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="96bc6-109">Der Vorgang zum Abrufen der Benutzereinstellung ist Teil des Benutzer Einstellungs Diensts in der Repository-API für das Dashboard für die Anrufqualität.</span><span class="sxs-lookup"><span data-stu-id="96bc6-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="96bc6-110">Abrufen einer Benutzereinstellung</span><span class="sxs-lookup"><span data-stu-id="96bc6-110">Get User Setting</span></span>

<span data-ttu-id="96bc6-111">Benutzereinstellung abrufen gibt eine Einstellung für einen einzelnen Benutzer zurück.</span><span class="sxs-lookup"><span data-stu-id="96bc6-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="96bc6-112">**Methode**</span><span class="sxs-lookup"><span data-stu-id="96bc6-112">**Method**</span></span>|<span data-ttu-id="96bc6-113">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="96bc6-113">**Request URI**</span></span>|<span data-ttu-id="96bc6-114">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="96bc6-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="96bc6-115">Erhalten</span><span class="sxs-lookup"><span data-stu-id="96bc6-115">GET</span></span>  <br/> |<span data-ttu-id="96bc6-116">https://\<-\>Portal/QoERepositoryService/Repository/User/{UserID}/Setting/{Key}</span><span class="sxs-lookup"><span data-stu-id="96bc6-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="96bc6-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="96bc6-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="96bc6-118">**URI-Parameter** -None.</span><span class="sxs-lookup"><span data-stu-id="96bc6-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="96bc6-119">**Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="96bc6-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="96bc6-120">**Anforderungstext** – keine.</span><span class="sxs-lookup"><span data-stu-id="96bc6-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="96bc6-121">**Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.</span><span class="sxs-lookup"><span data-stu-id="96bc6-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="96bc6-122">**Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.</span><span class="sxs-lookup"><span data-stu-id="96bc6-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="96bc6-123">**Antwortheader** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="96bc6-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="96bc6-124">**Antworttext** : Nachfolgend finden Sie eine Beispielantwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="96bc6-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="96bc6-125">*UserID* -ID des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="96bc6-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="96bc6-126">*Tasten* Kombination der Einstellung.</span><span class="sxs-lookup"><span data-stu-id="96bc6-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="96bc6-127">*value* -Wert der Einstellung.</span><span class="sxs-lookup"><span data-stu-id="96bc6-127">*value*  - Value of the setting.</span></span>
  

