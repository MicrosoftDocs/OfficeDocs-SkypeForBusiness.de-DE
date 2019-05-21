---
title: Aktualisieren von Elementen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang "Element aktualisieren", der Teil des Element Diensts ist. Der Element Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: aa46be0babf5998fcf2fabea797cb7a769914f8e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274534"
---
# <a name="update-item"></a><span data-ttu-id="e27b5-105">Aktualisieren von Elementen</span><span class="sxs-lookup"><span data-stu-id="e27b5-105">Update Item</span></span>
 
<span data-ttu-id="e27b5-106">**Zusammenfassung:** Informieren Sie sich über den Vorgang "Element aktualisieren", der Teil des Element Diensts ist.</span><span class="sxs-lookup"><span data-stu-id="e27b5-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="e27b5-107">Der Element Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard.</span><span class="sxs-lookup"><span data-stu-id="e27b5-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="e27b5-108">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e27b5-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="e27b5-109">Der Vorgang "Element aktualisieren" ist Teil des Element Diensts in der Repository-API für das Dashboard für die Anrufqualität.</span><span class="sxs-lookup"><span data-stu-id="e27b5-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="e27b5-110">Aktualisieren von Elementen</span><span class="sxs-lookup"><span data-stu-id="e27b5-110">Update Item</span></span>

<span data-ttu-id="e27b5-111">Element aktualisieren aktualisiert ein bestimmtes Element im Repository.</span><span class="sxs-lookup"><span data-stu-id="e27b5-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="e27b5-112">**Methode**</span><span class="sxs-lookup"><span data-stu-id="e27b5-112">**Method**</span></span>|<span data-ttu-id="e27b5-113">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="e27b5-113">**Request URI**</span></span>|<span data-ttu-id="e27b5-114">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="e27b5-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e27b5-115">Setzen</span><span class="sxs-lookup"><span data-stu-id="e27b5-115">PUT</span></span>  <br/> |<span data-ttu-id="e27b5-116">https://\<-\>Portal/QoERepositoryService/Repository/Item/{Itemid}</span><span class="sxs-lookup"><span data-stu-id="e27b5-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="e27b5-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="e27b5-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="e27b5-118">**URI-Parameter** -None.</span><span class="sxs-lookup"><span data-stu-id="e27b5-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="e27b5-119">**Anforderungs Kopfzeilen** – Content-Type: Application/JSON.</span><span class="sxs-lookup"><span data-stu-id="e27b5-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="e27b5-120">**Anforderungstext** – JSON.</span><span class="sxs-lookup"><span data-stu-id="e27b5-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="e27b5-121">Beispiel für eine Anforderungsnutzlast:</span><span class="sxs-lookup"><span data-stu-id="e27b5-121">Sample request payload:</span></span>
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="e27b5-122">*Inhalt*  JSON-formatierte Daten, die als neuer Inhalt eines vorhandenen Unterelements gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e27b5-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="e27b5-123">Technisch gesehen kann ein Repository beliebigen Inhalt eines beliebigen Schemas speichern, wenn es aber für das Dashboard für die Anrufqualität verwendet wird, sollte es sich entweder um einen Bericht oder eine Abfrage handeln.</span><span class="sxs-lookup"><span data-stu-id="e27b5-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="e27b5-124">*geben* Sie  Geben Sie im Dashboard für die Anrufqualität immer "application/json" an.</span><span class="sxs-lookup"><span data-stu-id="e27b5-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="e27b5-125">**Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.</span><span class="sxs-lookup"><span data-stu-id="e27b5-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="e27b5-126">**Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 204 (kein Inhalt) zurück.</span><span class="sxs-lookup"><span data-stu-id="e27b5-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="e27b5-127">Wenn keine angegebene Element-ID gefunden wird, wird der Statuscode 404 (nicht gefunden) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e27b5-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e27b5-128">"Kein Inhalt" ist kein Fehlerstatus.</span><span class="sxs-lookup"><span data-stu-id="e27b5-128">"No Content" is not an error status.</span></span> <span data-ttu-id="e27b5-129">Das bedeutet, dass eine Antwort nichts im Text zurückgegeben hat (im Gegensatz dazu gibt 200 OK den Inhalt im Textkörper zurück).</span><span class="sxs-lookup"><span data-stu-id="e27b5-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="e27b5-130">Es gibt an, dass das Element erfolgreich aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e27b5-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="e27b5-131">**Antwortheader** – keine.</span><span class="sxs-lookup"><span data-stu-id="e27b5-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="e27b5-132">**Antworttext** – keine.</span><span class="sxs-lookup"><span data-stu-id="e27b5-132">**Response Body** - None.</span></span>
  

