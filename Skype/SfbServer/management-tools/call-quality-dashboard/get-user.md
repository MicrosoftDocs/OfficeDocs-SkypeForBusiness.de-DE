---
title: Abrufen eines Benutzers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang zum Abrufen des Benutzers, der Teil des Benutzer Diensts ist. Der Benutzer Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 6c38bb2db2bef1a21dfc5c4791de7a163c57ff5f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274597"
---
# <a name="get-user"></a><span data-ttu-id="a79d8-105">Abrufen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="a79d8-105">Get User</span></span>
 
<span data-ttu-id="a79d8-106">**Zusammenfassung:** Informieren Sie sich über den Vorgang "Benutzer abrufen", der Teil des Benutzer Diensts ist.</span><span class="sxs-lookup"><span data-stu-id="a79d8-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="a79d8-107">Der Benutzer Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard.</span><span class="sxs-lookup"><span data-stu-id="a79d8-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="a79d8-108">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a79d8-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="a79d8-109">Der Vorgang zum Abrufen von Benutzern ist Teil des Benutzer Diensts in der Repository-API für die Anruf Qualitätssteuerung.</span><span class="sxs-lookup"><span data-stu-id="a79d8-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="a79d8-110">Abrufen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="a79d8-110">Get User</span></span>

<span data-ttu-id="a79d8-111">Der Benutzer erhält einen Benutzerdatensatz aus dem Repository zurück.</span><span class="sxs-lookup"><span data-stu-id="a79d8-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="a79d8-112">**Methode**</span><span class="sxs-lookup"><span data-stu-id="a79d8-112">**Method**</span></span>|<span data-ttu-id="a79d8-113">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="a79d8-113">**Request URI**</span></span>|<span data-ttu-id="a79d8-114">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="a79d8-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a79d8-115">Erhalten</span><span class="sxs-lookup"><span data-stu-id="a79d8-115">GET</span></span>  <br/> |<span data-ttu-id="a79d8-116">https://\<-\>Portal/QoERepositoryService/Repository/User/{UserID}</span><span class="sxs-lookup"><span data-stu-id="a79d8-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="a79d8-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="a79d8-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="a79d8-118">**URI-Parameter** -None.</span><span class="sxs-lookup"><span data-stu-id="a79d8-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="a79d8-119">**Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="a79d8-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a79d8-120">**Anforderungstext** – keine.</span><span class="sxs-lookup"><span data-stu-id="a79d8-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="a79d8-121">**Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.</span><span class="sxs-lookup"><span data-stu-id="a79d8-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="a79d8-122">**Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.</span><span class="sxs-lookup"><span data-stu-id="a79d8-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="a79d8-123">Wenn keine angegebene Benutzer-ID gefunden wird, wird der Statuscode 404 (nicht gefunden) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a79d8-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="a79d8-124">**Antwortheader** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="a79d8-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a79d8-125">**Antworttext** : Nachfolgend finden Sie eine Beispielantwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="a79d8-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="a79d8-126">*UserID* -ID des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="a79d8-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="a79d8-127">*LoginName* – externe Benutzerkennung für reguläre Benutzer.</span><span class="sxs-lookup"><span data-stu-id="a79d8-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="a79d8-128">Wenn die Windows-Authentifizierung für die Authentifizierung von Benutzern verwendet wird, kann dies ein FQDN des Benutzers sein.</span><span class="sxs-lookup"><span data-stu-id="a79d8-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="a79d8-129">*defaultItemId* -ID des Standardelements für diesen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="a79d8-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="a79d8-130">Das Standardelement ist das oberste Element, das dem Benutzer zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a79d8-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="a79d8-131">Alle anderen Elemente, denen dieser Benutzer angehört, können vom Standardelement aus navigiert werden.</span><span class="sxs-lookup"><span data-stu-id="a79d8-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a79d8-132">Geben Sie `defaultItemId` den Wert zum Abrufen des Element Vorgangs an, um die Details des Standardelements abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a79d8-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

