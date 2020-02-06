---
title: Abrufen eines Benutzers
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
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang zum Abrufen des Benutzers, der Teil des Benutzer Diensts ist. Der Benutzer Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: e07a232b61e5ef0bb7462b3fff58d642a14496ec
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816734"
---
# <a name="get-user"></a><span data-ttu-id="c88d6-105">Abrufen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="c88d6-105">Get User</span></span>
 
<span data-ttu-id="c88d6-106">**Zusammenfassung:** Informieren Sie sich über den Vorgang "Benutzer abrufen", der Teil des Benutzer Diensts ist.</span><span class="sxs-lookup"><span data-stu-id="c88d6-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="c88d6-107">Der Benutzer Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard.</span><span class="sxs-lookup"><span data-stu-id="c88d6-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="c88d6-108">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c88d6-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="c88d6-109">Der Vorgang zum Abrufen von Benutzern ist Teil des Benutzer Diensts in der Repository-API für die Anruf Qualitätssteuerung.</span><span class="sxs-lookup"><span data-stu-id="c88d6-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="c88d6-110">Abrufen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="c88d6-110">Get User</span></span>

<span data-ttu-id="c88d6-111">Der Benutzer erhält einen Benutzerdatensatz aus dem Repository zurück.</span><span class="sxs-lookup"><span data-stu-id="c88d6-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="c88d6-112">**Methode**</span><span class="sxs-lookup"><span data-stu-id="c88d6-112">**Method**</span></span>|<span data-ttu-id="c88d6-113">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="c88d6-113">**Request URI**</span></span>|<span data-ttu-id="c88d6-114">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="c88d6-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c88d6-115">Erhalten</span><span class="sxs-lookup"><span data-stu-id="c88d6-115">GET</span></span>  <br/> |<span data-ttu-id="c88d6-116">https://\<-\>Portal/QoERepositoryService/Repository/User/{UserID}</span><span class="sxs-lookup"><span data-stu-id="c88d6-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="c88d6-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="c88d6-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="c88d6-118">**URI-Parameter** -None.</span><span class="sxs-lookup"><span data-stu-id="c88d6-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="c88d6-119">**Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="c88d6-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c88d6-120">**Anforderungstext** – keine.</span><span class="sxs-lookup"><span data-stu-id="c88d6-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="c88d6-121">**Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.</span><span class="sxs-lookup"><span data-stu-id="c88d6-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="c88d6-122">**Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.</span><span class="sxs-lookup"><span data-stu-id="c88d6-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="c88d6-123">Wenn keine angegebene Benutzer-ID gefunden wird, wird der Statuscode 404 (nicht gefunden) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c88d6-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="c88d6-124">**Antwortheader** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="c88d6-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c88d6-125">**Antworttext** : Nachfolgend finden Sie eine Beispielantwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="c88d6-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="c88d6-126">*UserID* -ID des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="c88d6-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="c88d6-127">*LoginName* – externe Benutzerkennung für reguläre Benutzer.</span><span class="sxs-lookup"><span data-stu-id="c88d6-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="c88d6-128">Wenn die Windows-Authentifizierung für die Authentifizierung von Benutzern verwendet wird, kann dies ein FQDN des Benutzers sein.</span><span class="sxs-lookup"><span data-stu-id="c88d6-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="c88d6-129">*defaultItemId* -ID des Standardelements für diesen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="c88d6-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="c88d6-130">Das Standardelement ist das oberste Element, das dem Benutzer zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="c88d6-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="c88d6-131">Alle anderen Elemente, denen dieser Benutzer angehört, können vom Standardelement aus navigiert werden.</span><span class="sxs-lookup"><span data-stu-id="c88d6-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c88d6-132">Geben Sie `defaultItemId` den Wert zum Abrufen des Element Vorgangs an, um die Details des Standardelements abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c88d6-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

