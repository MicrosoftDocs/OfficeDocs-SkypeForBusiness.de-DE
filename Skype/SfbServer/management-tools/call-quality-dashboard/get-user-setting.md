---
title: Get-Benutzereinstellung
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Zusammenfassung: Informationen Sie zum Vorgang Benutzereinstellung erhalten möchten, der Teil der User Settings Service ist. Die User Settings Service ist Bestandteil der Repository-API für die Qualitätsdashboard aufrufen. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.'
ms.openlocfilehash: e3646b1c6d5a7f959ee76565bb7b92ac84cbe8a4
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569250"
---
# <a name="get-user-setting"></a><span data-ttu-id="c5897-105">Get-Benutzereinstellung</span><span class="sxs-lookup"><span data-stu-id="c5897-105">Get User Setting</span></span>
 
<span data-ttu-id="c5897-106">**Zusammenfassung:** Informationen Sie zu den Vorgang erhalten Benutzer die Einstellung, der Teil der User Settings Service ist.</span><span class="sxs-lookup"><span data-stu-id="c5897-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="c5897-107">Die User Settings Service ist Bestandteil der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c5897-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="c5897-108">Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c5897-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c5897-109">Der Vorgang erhalten Benutzer die Einstellung ist Bestandteil der Benutzerdienst Einstellungen in der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c5897-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="c5897-110">Get-Benutzereinstellung</span><span class="sxs-lookup"><span data-stu-id="c5897-110">Get User Setting</span></span>

<span data-ttu-id="c5897-111">Rufen Sie die Einstellung für Benutzer gibt eine Einstellung für die einzelnen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="c5897-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="c5897-112">**Methode**</span><span class="sxs-lookup"><span data-stu-id="c5897-112">**Method**</span></span>|<span data-ttu-id="c5897-113">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="c5897-113">**Request URI**</span></span>|<span data-ttu-id="c5897-114">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="c5897-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c5897-115">Erhalten</span><span class="sxs-lookup"><span data-stu-id="c5897-115">GET</span></span>  <br/> |<span data-ttu-id="c5897-116">https://\<Portal\>/QoERepositoryService/Repository/Benutzer / {Benutzer-ID} /setting/ {Schlüssel}</span><span class="sxs-lookup"><span data-stu-id="c5897-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="c5897-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="c5897-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="c5897-118">**URI-Parameter** - None.</span><span class="sxs-lookup"><span data-stu-id="c5897-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="c5897-119">**Anfordern von Kopfzeilen** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="c5897-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c5897-120">**Anforderungstextkörper** – None.</span><span class="sxs-lookup"><span data-stu-id="c5897-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="c5897-121">**Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.</span><span class="sxs-lookup"><span data-stu-id="c5897-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="c5897-122">**Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="c5897-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="c5897-123">**Antwortheader** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="c5897-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c5897-124">**Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="c5897-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="c5897-125">*UserId* - ID des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="c5897-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="c5897-126">*Key* - Schlüssel der Einstellung.</span><span class="sxs-lookup"><span data-stu-id="c5897-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="c5897-127">*Wert* - Wert der Einstellung.</span><span class="sxs-lookup"><span data-stu-id="c5897-127">*value*  - Value of the setting.</span></span>
  

