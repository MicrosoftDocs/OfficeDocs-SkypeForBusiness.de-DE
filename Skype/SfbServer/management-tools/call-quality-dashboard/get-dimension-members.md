---
title: Abrufen von Dimensionselementen
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
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang zum Abrufen von Dimensionselementen. Der Vorgang zum Abrufen von Dimensionselementen ist Teil der Daten-API für das Dashboard für die Anrufqualität. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 40e5ac8b95c24c3a8cb759da99f7d7aeaa391576
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888814"
---
# <a name="get-dimension-members"></a><span data-ttu-id="ed7a0-105">Abrufen von Dimensionselementen</span><span class="sxs-lookup"><span data-stu-id="ed7a0-105">Get Dimension Members</span></span>
 
<span data-ttu-id="ed7a0-106">**Zusammenfassung:** Erfahren Sie mehr über den Vorgang zum Abrufen von Dimensionselementen.</span><span class="sxs-lookup"><span data-stu-id="ed7a0-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="ed7a0-107">Der Vorgang zum Abrufen von Dimensionselementen ist Teil der Daten-API für das Dashboard für die Anrufqualität.</span><span class="sxs-lookup"><span data-stu-id="ed7a0-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="ed7a0-108">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ed7a0-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="ed7a0-109">Der Vorgang zum Abrufen von Dimensionselementen ist Teil der Daten-API für das Dashboard für die Anrufqualität.</span><span class="sxs-lookup"><span data-stu-id="ed7a0-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="ed7a0-110">Abrufen von Dimensionselementen</span><span class="sxs-lookup"><span data-stu-id="ed7a0-110">Get Dimension Members</span></span>

<span data-ttu-id="ed7a0-111">Der Vorgang zum Abrufen von Dimensionselementen gibt die Liste der Elemente einer bestimmten Dimension zurück.</span><span class="sxs-lookup"><span data-stu-id="ed7a0-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="ed7a0-112">Darüber hinaus können Sie die Mitgliederliste Filtern und eine Teilmenge abrufen, um die Übertragungskosten zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="ed7a0-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="ed7a0-113">**Methode**</span><span class="sxs-lookup"><span data-stu-id="ed7a0-113">**Method**</span></span>|<span data-ttu-id="ed7a0-114">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="ed7a0-114">**Request URI**</span></span>|<span data-ttu-id="ed7a0-115">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="ed7a0-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ed7a0-116">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="ed7a0-116">POST</span></span>  <br/> |<span data-ttu-id="ed7a0-117">https://\<-\>Portal/QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="ed7a0-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="ed7a0-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="ed7a0-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="ed7a0-119">**URI-Parameter** -None.</span><span class="sxs-lookup"><span data-stu-id="ed7a0-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="ed7a0-120">**Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="ed7a0-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="ed7a0-121">**Anforderungstext** – dieser enthält den Namen der Dimension, für die die Mitglieder angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ed7a0-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="ed7a0-122">Außerdem können Sie die maximale Anzahl der zurückgegebenen Mitglieder angeben, indem Sie einige Filter angeben, um die zurückgegebenen Member zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="ed7a0-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
```json
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 <span data-ttu-id="ed7a0-123">**Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.</span><span class="sxs-lookup"><span data-stu-id="ed7a0-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="ed7a0-124">**Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.</span><span class="sxs-lookup"><span data-stu-id="ed7a0-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="ed7a0-125">**Antwortheader** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="ed7a0-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="ed7a0-126">**Antworttext** : Nachfolgend finden Sie eine Beispielantwort Nutzlast in JSON als Antwort auf eine Anforderung für "[StartDate]. [Month] "-Dimension.</span><span class="sxs-lookup"><span data-stu-id="ed7a0-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ed7a0-127">In der Liste wird nur ein kleiner Teil der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ed7a0-127">The list is only showing a small portion of the list.</span></span> 
  
```json
{
"MembersCount": 493,
"Members": [["[1990-01-01T00:00:00]",
"January 1990"],
["[1990-02-01T00:00:00]",
"February 1990"],
["[1990-03-01T00:00:00]",
"March 1990"],
 
    ...
    
["[2030-10-01T00:00:00]",
"October 2030"],
["[2030-11-01T00:00:00]",
"November 2030"],
["[2030-12-01T00:00:00]",
"December 2030"],
["[2031-01-01T00:00:00]",
"January 2031"]]
}
```
