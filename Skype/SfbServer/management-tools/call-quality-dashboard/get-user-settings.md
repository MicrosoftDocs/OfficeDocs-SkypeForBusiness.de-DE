---
title: Abrufen der Benutzereinstellungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Zusammenfassung: Informationen Sie zum Vorgang Benutzereinstellungen erhalten möchten, der Teil des Diensts für Benutzer ist. Die User Settings Service ist Bestandteil der Repository-API für die Qualitätsdashboard aufrufen. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: cef6eef88f4fa7a7410f4967ad698972f98d7c5f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930588"
---
# <a name="get-user-settings"></a><span data-ttu-id="c5766-105">Abrufen der Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="c5766-105">Get User Settings</span></span>
 
<span data-ttu-id="c5766-106">**Zusammenfassung:** Informationen Sie zu den Get User Settings-Vorgang, der Teil des Diensts für Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="c5766-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="c5766-107">Die User Settings Service ist Bestandteil der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c5766-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="c5766-108">Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="c5766-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="c5766-109">Der erste User Settings-Vorgang ist Teil der Benutzerdienst Einstellungen in der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c5766-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="c5766-110">Abrufen der Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="c5766-110">Get User Settings</span></span>

<span data-ttu-id="c5766-111">Get-Benutzereinstellungen gibt eine Liste der Einstellungen für einen angegebenen Benutzer zurück.</span><span class="sxs-lookup"><span data-stu-id="c5766-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="c5766-112">**Methode**</span><span class="sxs-lookup"><span data-stu-id="c5766-112">**Method**</span></span>|<span data-ttu-id="c5766-113">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="c5766-113">**Request URI**</span></span>|<span data-ttu-id="c5766-114">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="c5766-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c5766-115">Erhalten</span><span class="sxs-lookup"><span data-stu-id="c5766-115">GET</span></span>  <br/> |<span data-ttu-id="c5766-116">https://\<Portal\>/QoERepositoryService/Repository/Benutzer / {Benutzer-ID} / festlegen</span><span class="sxs-lookup"><span data-stu-id="c5766-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="c5766-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="c5766-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="c5766-118">**URI-Parameter**</span><span class="sxs-lookup"><span data-stu-id="c5766-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="c5766-119">*eine effektive* - Optional.</span><span class="sxs-lookup"><span data-stu-id="c5766-119">*effective*  - Optional.</span></span> <span data-ttu-id="c5766-120">Dieser Parameter gilt nur, wenn die spezielle Benutzer-ID-Standardeinstellung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c5766-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="c5766-121">In anderen Fällen wird sie ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c5766-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="c5766-122">`True`Gibt eine effektive benutzereinstellungen und `false` gibt nur die benutzereinstellungen (Standard).</span><span class="sxs-lookup"><span data-stu-id="c5766-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="c5766-123">**Anfordern von Kopfzeilen** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="c5766-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="c5766-124">**Anforderungstextkörper** – None.</span><span class="sxs-lookup"><span data-stu-id="c5766-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="c5766-125">**Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.</span><span class="sxs-lookup"><span data-stu-id="c5766-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="c5766-126">**Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="c5766-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="c5766-127">**Antwortheader** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="c5766-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="c5766-128">**Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="c5766-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
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
