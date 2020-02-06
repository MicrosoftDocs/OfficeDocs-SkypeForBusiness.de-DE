---
title: Abrufen der Benutzereinstellungen
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
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang zum Abrufen von Benutzereinstellungen, der Teil des Benutzer Einstellungs Diensts ist. Der Benutzer Einstellungsdienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 5b5ad679387866ba6562e031b6d3a42cc68851a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816744"
---
# <a name="get-user-settings"></a><span data-ttu-id="9827b-105">Abrufen der Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="9827b-105">Get User Settings</span></span>
 
<span data-ttu-id="9827b-106">**Zusammenfassung:** Erfahren Sie mehr über den Vorgang zum Abrufen von Benutzereinstellungen, der Teil des Benutzer Einstellungs Diensts ist.</span><span class="sxs-lookup"><span data-stu-id="9827b-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="9827b-107">Der Benutzer Einstellungsdienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard.</span><span class="sxs-lookup"><span data-stu-id="9827b-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="9827b-108">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9827b-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="9827b-109">Der Vorgang zum Abrufen von Benutzereinstellungen ist Teil des Benutzer Einstellungs Diensts in der Repository-API für die Anruf Qualitätssteuerung.</span><span class="sxs-lookup"><span data-stu-id="9827b-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="9827b-110">Abrufen der Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="9827b-110">Get User Settings</span></span>

<span data-ttu-id="9827b-111">Abrufen von Benutzereinstellungen gibt eine Liste der Einstellungen für einen bestimmten Benutzer zurück.</span><span class="sxs-lookup"><span data-stu-id="9827b-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="9827b-112">**Methode**</span><span class="sxs-lookup"><span data-stu-id="9827b-112">**Method**</span></span>|<span data-ttu-id="9827b-113">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="9827b-113">**Request URI**</span></span>|<span data-ttu-id="9827b-114">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="9827b-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9827b-115">Erhalten</span><span class="sxs-lookup"><span data-stu-id="9827b-115">GET</span></span>  <br/> |<span data-ttu-id="9827b-116">https://\<-\>Portal/QoERepositoryService/Repository/User/{UserID}/Setting</span><span class="sxs-lookup"><span data-stu-id="9827b-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="9827b-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="9827b-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="9827b-118">**URI-Parameter**</span><span class="sxs-lookup"><span data-stu-id="9827b-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="9827b-119">*effektiv* – optional.</span><span class="sxs-lookup"><span data-stu-id="9827b-119">*effective*  - Optional.</span></span> <span data-ttu-id="9827b-120">Dieser Parameter gilt nur, wenn die spezielle Benutzer-ID Standard verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9827b-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="9827b-121">In anderen Fällen wird Sie ignoriert.</span><span class="sxs-lookup"><span data-stu-id="9827b-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="9827b-122">`True`gibt effektive Benutzereinstellungen zurück `false` und gibt nur Benutzereinstellungen zurück (Standard).</span><span class="sxs-lookup"><span data-stu-id="9827b-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="9827b-123">**Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="9827b-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="9827b-124">**Anforderungstext** – keine.</span><span class="sxs-lookup"><span data-stu-id="9827b-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="9827b-125">**Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.</span><span class="sxs-lookup"><span data-stu-id="9827b-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="9827b-126">**Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.</span><span class="sxs-lookup"><span data-stu-id="9827b-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="9827b-127">**Antwortheader** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="9827b-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="9827b-128">**Antworttext** : Nachfolgend finden Sie eine Beispielantwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="9827b-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
[{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
},
{
"userId": 6,
"key": "ShowTimeStamps",
"value": "true"
}]
```
