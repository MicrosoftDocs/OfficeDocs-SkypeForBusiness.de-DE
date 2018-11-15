---
title: Update-Element
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Zusammenfassung: Informationen Sie zum Vorgang Update-Element, der Teil der Element-Dienst ist. Der Element-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: 5839118dc6e907696d4ce3e9adfbc58504808fac
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532225"
---
# <a name="update-item"></a><span data-ttu-id="8c854-105">Update-Element</span><span class="sxs-lookup"><span data-stu-id="8c854-105">Update Item</span></span>
 
<span data-ttu-id="8c854-106">**Zusammenfassung:** Informationen Sie zu den Vorgang Update-Element, der Teil der Element-Dienst ist.</span><span class="sxs-lookup"><span data-stu-id="8c854-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="8c854-107">Der Element-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8c854-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="8c854-108">Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="8c854-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="8c854-109">Der Vorgang der Update-Element ist Teil des Diensts Element in der Repository-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8c854-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="8c854-110">Update-Element</span><span class="sxs-lookup"><span data-stu-id="8c854-110">Update Item</span></span>

<span data-ttu-id="8c854-111">Update-Element aktualisiert ein bestimmtes Element im Repository.</span><span class="sxs-lookup"><span data-stu-id="8c854-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="8c854-112">**Methode**</span><span class="sxs-lookup"><span data-stu-id="8c854-112">**Method**</span></span>|<span data-ttu-id="8c854-113">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="8c854-113">**Request URI**</span></span>|<span data-ttu-id="8c854-114">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="8c854-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8c854-115">PUT</span><span class="sxs-lookup"><span data-stu-id="8c854-115">PUT</span></span>  <br/> |<span data-ttu-id="8c854-116">https://\<Portal\>/QoERepositoryService/Repository/Element / {ItemId}</span><span class="sxs-lookup"><span data-stu-id="8c854-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="8c854-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="8c854-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="8c854-118">**URI-Parameter** - None.</span><span class="sxs-lookup"><span data-stu-id="8c854-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="8c854-119">**Anfordern von Kopfzeilen** -Content-Type: Application/Json.</span><span class="sxs-lookup"><span data-stu-id="8c854-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="8c854-120">**Anforderungstextkörper** - JSON.</span><span class="sxs-lookup"><span data-stu-id="8c854-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="8c854-121">Beispiel-Anforderungsnutzlast:</span><span class="sxs-lookup"><span data-stu-id="8c854-121">Sample request payload:</span></span>
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="8c854-122">*Inhalt*  JSON formatierte Daten als neuer Inhalt eines vorhandenen untergeordneten Elements gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="8c854-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="8c854-123">Technisch gesehen ein Repository kann alle Inhalte von einem beliebigen Schema gespeichert, aber beim für aufrufen Qualitätsdashboard verwendet wird, sollte es sein, einem Bericht oder einer Abfrage.</span><span class="sxs-lookup"><span data-stu-id="8c854-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="8c854-124">*Typ*  Geben Sie immer "Application/Json" für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8c854-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="8c854-125">**Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.</span><span class="sxs-lookup"><span data-stu-id="8c854-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="8c854-126">**Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 204 (kein Inhalt).</span><span class="sxs-lookup"><span data-stu-id="8c854-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="8c854-127">Wenn eine angegebenes Element-ID nicht gefunden wird, wird der Statuscode 404 (nicht gefunden) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8c854-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8c854-128">"Keine Content" ist nicht Fehlerstatus.</span><span class="sxs-lookup"><span data-stu-id="8c854-128">"No Content" is not an error status.</span></span> <span data-ttu-id="8c854-129">Dies bedeutet, dass eine Antwort Suchzeichenfolge nicht im Textkörper (im Gegensatz dazu 200 OK gibt Inhalt im Textkörper) zurückgegeben hat.</span><span class="sxs-lookup"><span data-stu-id="8c854-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="8c854-130">Es gibt an, dass das Element erfolgreich aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="8c854-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="8c854-131">**Antwortheader** - None.</span><span class="sxs-lookup"><span data-stu-id="8c854-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="8c854-132">**Antworttext** – None.</span><span class="sxs-lookup"><span data-stu-id="8c854-132">**Response Body** - None.</span></span>
  

