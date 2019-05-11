---
title: Abrufen von Dimensionselementen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Zusammenfassung: Informationen Sie zum Vorgang Dimensionselemente abrufen. Der erste Dimensionselemente-Vorgang ist Teil der Daten-API für die Qualitätsdashboard aufrufen. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: 482fe92a95c6754695e983ed9ff0ec69ed7a442b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926093"
---
# <a name="get-dimension-members"></a><span data-ttu-id="bf281-105">Abrufen von Dimensionselementen</span><span class="sxs-lookup"><span data-stu-id="bf281-105">Get Dimension Members</span></span>
 
<span data-ttu-id="bf281-106">**Zusammenfassung:** Informationen Sie zu den Vorgang Dimensionselemente abrufen.</span><span class="sxs-lookup"><span data-stu-id="bf281-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="bf281-107">Der erste Dimensionselemente-Vorgang ist Teil der Daten-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="bf281-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="bf281-108">Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="bf281-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="bf281-109">Der erste Dimensionselemente-Vorgang ist Teil der Daten-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="bf281-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="bf281-110">Abrufen von Dimensionselementen</span><span class="sxs-lookup"><span data-stu-id="bf281-110">Get Dimension Members</span></span>

<span data-ttu-id="bf281-111">Dimensionselemente Abrufvorgang gibt die Liste der Mitglieder einer bestimmten Dimension zurück.</span><span class="sxs-lookup"><span data-stu-id="bf281-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="bf281-112">Es auch bieten die Möglichkeit zum Filtern der Memberliste und erhalten Sie eine Teilmenge die Leitung Übertragung Kosten zu senken.</span><span class="sxs-lookup"><span data-stu-id="bf281-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="bf281-113">**Methode**</span><span class="sxs-lookup"><span data-stu-id="bf281-113">**Method**</span></span>|<span data-ttu-id="bf281-114">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="bf281-114">**Request URI**</span></span>|<span data-ttu-id="bf281-115">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="bf281-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bf281-116">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="bf281-116">POST</span></span>  <br/> |<span data-ttu-id="bf281-117">https://\<Portal\>/QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="bf281-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="bf281-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="bf281-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="bf281-119">**URI-Parameter** - None.</span><span class="sxs-lookup"><span data-stu-id="bf281-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="bf281-120">**Anfordern von Kopfzeilen** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="bf281-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="bf281-121">**Anfordern Body** – dies der Name der Dimension, wir die Mitglieder für möchten, enthält.</span><span class="sxs-lookup"><span data-stu-id="bf281-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="bf281-122">Maximale Anzahl der Elemente zurückgegeben werden, können neben Sie außerdem angeben einige Filter zum Einschränken der zurückgegebenen Elemente.</span><span class="sxs-lookup"><span data-stu-id="bf281-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
```
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 <span data-ttu-id="bf281-123">**Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.</span><span class="sxs-lookup"><span data-stu-id="bf281-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="bf281-124">**Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="bf281-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="bf281-125">**Antwortheader** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="bf281-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="bf281-126">**Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON als Antwort auf eine Anforderung für "StartDate. [Monat] "Dimension.</span><span class="sxs-lookup"><span data-stu-id="bf281-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bf281-127">Die Liste wird nur einen kleinen Teil der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bf281-127">The list is only showing a small portion of the list.</span></span> 
  
```
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
