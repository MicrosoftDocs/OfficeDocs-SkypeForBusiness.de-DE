---
title: Abrufen eines Benutzers
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Zusammenfassung: Informationen Sie zum Vorgang Benutzer abrufen, der Teil der Benutzerdienst ist. Der Benutzer-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: 2d3c5febe30af2ea4d41d94aec026c25e27f21b9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32235723"
---
# <a name="get-user"></a><span data-ttu-id="663b5-105">Abrufen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="663b5-105">Get User</span></span>
 
<span data-ttu-id="663b5-106">**Zusammenfassung:** Informationen Sie zu den Vorgang erhalten Benutzer, der Teil der Benutzerdienst ist.</span><span class="sxs-lookup"><span data-stu-id="663b5-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="663b5-107">Der Benutzer-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="663b5-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="663b5-108">Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="663b5-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="663b5-109">Der Benutzer abrufen-Vorgang ist Teil des Dienstes Benutzer in der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="663b5-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="663b5-110">Abrufen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="663b5-110">Get User</span></span>

<span data-ttu-id="663b5-111">Rufen Sie Benutzer gibt Datensatz eines Benutzers aus dem Repository.</span><span class="sxs-lookup"><span data-stu-id="663b5-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="663b5-112">**Methode**</span><span class="sxs-lookup"><span data-stu-id="663b5-112">**Method**</span></span>|<span data-ttu-id="663b5-113">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="663b5-113">**Request URI**</span></span>|<span data-ttu-id="663b5-114">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="663b5-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="663b5-115">Erhalten</span><span class="sxs-lookup"><span data-stu-id="663b5-115">GET</span></span>  <br/> |<span data-ttu-id="663b5-116">https://\<Portal\>/QoERepositoryService/Repository/Benutzer / {Benutzer-ID}</span><span class="sxs-lookup"><span data-stu-id="663b5-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="663b5-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="663b5-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="663b5-118">**URI-Parameter** - None.</span><span class="sxs-lookup"><span data-stu-id="663b5-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="663b5-119">**Anfordern von Kopfzeilen** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="663b5-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="663b5-120">**Anforderungstextkörper** – None.</span><span class="sxs-lookup"><span data-stu-id="663b5-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="663b5-121">**Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.</span><span class="sxs-lookup"><span data-stu-id="663b5-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="663b5-122">**Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="663b5-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="663b5-123">Wenn einen angegebenen Benutzer-ID nicht gefunden wurde, wird der Statuscode 404 (nicht gefunden) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="663b5-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="663b5-124">**Antwortheader** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="663b5-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="663b5-125">**Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="663b5-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="663b5-126">*UserId* - ID des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="663b5-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="663b5-127">*LoginName* - externe Benutzer-ID für normale Benutzer.</span><span class="sxs-lookup"><span data-stu-id="663b5-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="663b5-128">Wenn Windows-Authentifizierung zum Authentifizieren von Benutzern verwendet wird, kann dies eine FQDN des Benutzers sein.</span><span class="sxs-lookup"><span data-stu-id="663b5-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="663b5-129">*DefaultItemId* - ID des Standard-Element für diesen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="663b5-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="663b5-130">Der Standardwert Element ist das oberste Element, das dem Benutzer zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="663b5-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="663b5-131">Alle anderen Elemente, die dieser Benutzer besitzt, können aus der Standard-Element navigiert werden.</span><span class="sxs-lookup"><span data-stu-id="663b5-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="663b5-132">Geben Sie die `defaultItemId` Wert zum Element abrufen Operation, die Details des Standard-Element abgerufen.</span><span class="sxs-lookup"><span data-stu-id="663b5-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

