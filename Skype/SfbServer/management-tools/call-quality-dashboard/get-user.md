---
title: Benutzer erhalten
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Zusammenfassung: Informationen Sie zum Vorgang Benutzer abrufen, der Teil der Benutzerdienst ist. Der Benutzer-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.'
ms.openlocfilehash: 7fd3a552f543d9e66e26feb4dfa60289c3aeb971
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569229"
---
# <a name="get-user"></a><span data-ttu-id="85d1f-105">Benutzer erhalten</span><span class="sxs-lookup"><span data-stu-id="85d1f-105">Get User</span></span>
 
<span data-ttu-id="85d1f-106">**Zusammenfassung:** Informationen Sie zu den Vorgang erhalten Benutzer, der Teil der Benutzerdienst ist.</span><span class="sxs-lookup"><span data-stu-id="85d1f-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="85d1f-107">Der Benutzer-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="85d1f-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="85d1f-108">Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="85d1f-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="85d1f-109">Der Benutzer abrufen-Vorgang ist Teil des Dienstes Benutzer in der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="85d1f-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="85d1f-110">Benutzer erhalten</span><span class="sxs-lookup"><span data-stu-id="85d1f-110">Get User</span></span>

<span data-ttu-id="85d1f-111">Rufen Sie Benutzer gibt Datensatz eines Benutzers aus dem Repository.</span><span class="sxs-lookup"><span data-stu-id="85d1f-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="85d1f-112">**Methode**</span><span class="sxs-lookup"><span data-stu-id="85d1f-112">**Method**</span></span>|<span data-ttu-id="85d1f-113">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="85d1f-113">**Request URI**</span></span>|<span data-ttu-id="85d1f-114">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="85d1f-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="85d1f-115">Erhalten</span><span class="sxs-lookup"><span data-stu-id="85d1f-115">GET</span></span>  <br/> |<span data-ttu-id="85d1f-116">https://\<Portal\>/QoERepositoryService/Repository/Benutzer / {Benutzer-ID}</span><span class="sxs-lookup"><span data-stu-id="85d1f-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="85d1f-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="85d1f-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="85d1f-118">**URI-Parameter** - None.</span><span class="sxs-lookup"><span data-stu-id="85d1f-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="85d1f-119">**Anfordern von Kopfzeilen** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="85d1f-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="85d1f-120">**Anforderungstextkörper** – None.</span><span class="sxs-lookup"><span data-stu-id="85d1f-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="85d1f-121">**Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.</span><span class="sxs-lookup"><span data-stu-id="85d1f-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="85d1f-122">**Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="85d1f-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="85d1f-123">Wenn einen angegebenen Benutzer-ID nicht gefunden wurde, wird der Statuscode 404 (nicht gefunden) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="85d1f-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="85d1f-124">**Antwortheader** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="85d1f-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="85d1f-125">**Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="85d1f-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="85d1f-126">*UserId* - ID des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="85d1f-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="85d1f-127">*LoginName* - externe Benutzer-ID für normale Benutzer.</span><span class="sxs-lookup"><span data-stu-id="85d1f-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="85d1f-128">Wenn Windows-Authentifizierung zum Authentifizieren von Benutzern verwendet wird, kann dies eine FQDN des Benutzers sein.</span><span class="sxs-lookup"><span data-stu-id="85d1f-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="85d1f-129">*DefaultItemId* - ID des Standard-Element für diesen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="85d1f-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="85d1f-130">Der Standardwert Element ist das oberste Element, das dem Benutzer zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="85d1f-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="85d1f-131">Alle anderen Elemente, die dieser Benutzer besitzt, können aus der Standard-Element navigiert werden.</span><span class="sxs-lookup"><span data-stu-id="85d1f-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="85d1f-132">Geben Sie die `defaultItemId` Wert zum Element abrufen Operation, die Details des Standard-Element abgerufen.</span><span class="sxs-lookup"><span data-stu-id="85d1f-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

