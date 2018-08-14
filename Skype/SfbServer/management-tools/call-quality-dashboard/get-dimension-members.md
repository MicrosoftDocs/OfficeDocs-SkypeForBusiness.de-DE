---
title: Abrufen von Dimensionselementen
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Zusammenfassung: Informationen Sie zum Vorgang Dimensionselemente abrufen. Der erste Dimensionselemente-Vorgang ist Teil der Daten-API für die Qualitätsdashboard aufrufen. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.'
ms.openlocfilehash: e15f63d5ad52c9fbc52d692fd5bbb0480a41a50a
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569278"
---
# <a name="get-dimension-members"></a><span data-ttu-id="619e8-105">Abrufen von Dimensionselementen</span><span class="sxs-lookup"><span data-stu-id="619e8-105">Get Dimension Members</span></span>
 
<span data-ttu-id="619e8-106">**Zusammenfassung:** Informationen Sie zu den Vorgang Dimensionselemente abrufen.</span><span class="sxs-lookup"><span data-stu-id="619e8-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="619e8-107">Der erste Dimensionselemente-Vorgang ist Teil der Daten-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="619e8-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="619e8-108">Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="619e8-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="619e8-109">Der erste Dimensionselemente-Vorgang ist Teil der Daten-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="619e8-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="619e8-110">Abrufen von Dimensionselementen</span><span class="sxs-lookup"><span data-stu-id="619e8-110">Get Dimension Members</span></span>

<span data-ttu-id="619e8-111">Dimensionselemente Abrufvorgang gibt die Liste der Mitglieder einer bestimmten Dimension zurück.</span><span class="sxs-lookup"><span data-stu-id="619e8-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="619e8-112">Es auch bieten die Möglichkeit zum Filtern der Memberliste und erhalten Sie eine Teilmenge die Leitung Übertragung Kosten zu senken.</span><span class="sxs-lookup"><span data-stu-id="619e8-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="619e8-113">**Methode**</span><span class="sxs-lookup"><span data-stu-id="619e8-113">**Method**</span></span>|<span data-ttu-id="619e8-114">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="619e8-114">**Request URI**</span></span>|<span data-ttu-id="619e8-115">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="619e8-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="619e8-116">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="619e8-116">POST</span></span>  <br/> |<span data-ttu-id="619e8-117">https://\<Portal\>/QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="619e8-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="619e8-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="619e8-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="619e8-119">**URI-Parameter** - None.</span><span class="sxs-lookup"><span data-stu-id="619e8-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="619e8-120">**Anfordern von Kopfzeilen** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="619e8-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="619e8-121">**Anfordern Body** – dies der Name der Dimension, wir die Mitglieder für möchten, enthält.</span><span class="sxs-lookup"><span data-stu-id="619e8-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="619e8-122">Maximale Anzahl der Elemente zurückgegeben werden, können neben Sie außerdem angeben einige Filter zum Einschränken der zurückgegebenen Elemente.</span><span class="sxs-lookup"><span data-stu-id="619e8-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
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

 <span data-ttu-id="619e8-123">**Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.</span><span class="sxs-lookup"><span data-stu-id="619e8-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="619e8-124">**Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="619e8-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="619e8-125">**Antwortheader** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="619e8-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="619e8-126">**Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON als Antwort auf eine Anforderung für "StartDate. [Monat] "Dimension.</span><span class="sxs-lookup"><span data-stu-id="619e8-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="619e8-127">Die Liste wird nur einen kleinen Teil der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="619e8-127">The list is only showing a small portion of the list.</span></span> 
  
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