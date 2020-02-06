---
title: Ausführen von Abfragen
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
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang zum Ausführen von Abfragen, der Teil der Daten-API für das Dashboard für die Anrufqualität ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 4e520921496a1650af12b342fd5a0244fe9eb7a5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816684"
---
# <a name="run-query"></a><span data-ttu-id="901f7-104">Ausführen von Abfragen</span><span class="sxs-lookup"><span data-stu-id="901f7-104">Run Query</span></span>

<span data-ttu-id="901f7-105">**Zusammenfassung:** Informieren Sie sich über den Vorgang zum Ausführen von Abfragen, der Teil der Daten-API für die Anruf Qualitätssteuerung ist.</span><span class="sxs-lookup"><span data-stu-id="901f7-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="901f7-106">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="901f7-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="901f7-107">Der Vorgang "Abfrage ausführen" ist Teil der Daten-API für die Anruf Qualitätssteuerung.</span><span class="sxs-lookup"><span data-stu-id="901f7-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>

## <a name="run-query"></a><span data-ttu-id="901f7-108">Ausführen von Abfragen</span><span class="sxs-lookup"><span data-stu-id="901f7-108">Run Query</span></span>

<span data-ttu-id="901f7-109">Abfragevorgang ausführen bietet die Möglichkeit, eine Abfrage auf dem Cube basierend auf angegebenen Dimensionen, Maßen und Filtern auszuführen und die Daten zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="901f7-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>


|<span data-ttu-id="901f7-110">**Methode**</span><span class="sxs-lookup"><span data-stu-id="901f7-110">**Method**</span></span>|<span data-ttu-id="901f7-111">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="901f7-111">**Request URI**</span></span>|<span data-ttu-id="901f7-112">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="901f7-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="901f7-113">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="901f7-113">POST</span></span>  <br/> |<span data-ttu-id="901f7-114">https://\<-\>Portal/QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="901f7-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="901f7-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="901f7-115">HTTP/1.1</span></span>  <br/> |

 <span data-ttu-id="901f7-116">**URI-Parameter** -None.</span><span class="sxs-lookup"><span data-stu-id="901f7-116">**URI Parameters** - None.</span></span>

 <span data-ttu-id="901f7-117">**Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="901f7-117">**Request Headers** - No additional headers.</span></span>

 <span data-ttu-id="901f7-118">**Anforderungstext** – hier finden Sie eine Beispiel Nutzlast für Anforderungen in JSON.</span><span class="sxs-lookup"><span data-stu-id="901f7-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="901f7-119">Sie enthält Dimensionen, Filter und Maße, die für eine Abfrage erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="901f7-119">It contains dimensions, filters, and measurement required for a query.</span></span>

```json
{
"Filters": [{
"DataModelName": "[StartDate].[Month]",
"Caption": "July 2013",
"Value": "[2015-03-01T00:00:00]",
"Operand": 0,
"UnionGroup": ""
}],
"Dimensions": [{
"DataModelName": "[StartDate].[Month]"
}],
"Measurements": [{
"DataModelName": "[Measures].[Audio Good Streams Count]"
},
{
"DataModelName": "[Measures].[Audio UnClassified Streams Count]"
},
{
"DataModelName": "[Measures].[Audio Poor Streams Count]"
},
{
"DataModelName": "[Measures].[AudioPoorPercentage]"
}],
"Trend": {
"EnableTrend": true,
"SpanCount": 7,
"TrendDate": "2015-3",
"Type": 0
}
}
```

 <span data-ttu-id="901f7-120">*Filter* – eine Liste der Filterausdrücke, die angewendet werden sollen, sodass die resultierende Datenmenge nur die Teilmenge der Daten reflektiert, die von Interesse sind.</span><span class="sxs-lookup"><span data-stu-id="901f7-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>

 <span data-ttu-id="901f7-121">*Dimensionen* – eine Liste von Dimensionen, die für die Aggregation der Daten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="901f7-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="901f7-122">Mindestens eine Dimension ist erforderlich, aber es können mehrere Dimensionen angegeben werden, um eine zusätzliche Ebene von unter Aggregationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="901f7-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>

 <span data-ttu-id="901f7-123">*Maße* – eine Liste von Maßen, die auch als "Facts" bezeichnet werden, die die gewünschten Metriken sind, die basierend auf den von Ihnen angegebenen Dimensionen aggregiert werden.</span><span class="sxs-lookup"><span data-stu-id="901f7-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>

 <span data-ttu-id="901f7-124">*Trend* – zusätzliche Steueranweisungen zum Anpassen der Ergebnisdaten.</span><span class="sxs-lookup"><span data-stu-id="901f7-124">*Trend*  - Additional control instructions to customize the result data.</span></span>

 <span data-ttu-id="901f7-125">**Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.</span><span class="sxs-lookup"><span data-stu-id="901f7-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>

 <span data-ttu-id="901f7-126">**Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.</span><span class="sxs-lookup"><span data-stu-id="901f7-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>

 <span data-ttu-id="901f7-127">**Antwortheader** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="901f7-127">**Response Headers** - No additional headers.</span></span>

 <span data-ttu-id="901f7-128">**Antworttext** : Nachfolgend finden Sie eine Beispielantwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="901f7-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="901f7-129">Sie enthält eine Datentabelle, die die Daten enthält, außerdem enthält Sie eine Meta-Datei, die die Ausführungszeit der Abfrage zeigt und angibt, ob die Daten aus dem Cache abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="901f7-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>

```json
{
"ExecutionTime": "00:00:00.2102630",
"DataResult": [["September 2014",
        1792,
        34,
        78,
        4.171],
        ["October 2014",
        37017,
        1731,
        3305,
        8.197],
        ["November 2014",
        79184,
        3033,
        5556,
        6.557],
        ["December 2014",
        122253,
        4050,
        5444,
        4.263],
        ["January 2015",
        31246,
        1069,
        1342,
        4.118]],
"ResultIsFromCache": false,
"ErrorType": 0
}
```

 <span data-ttu-id="901f7-130">*Ausführungszeit* : die Gesamtzeit, die der Server zum Zurückgeben der Daten benötigte.</span><span class="sxs-lookup"><span data-stu-id="901f7-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="901f7-131">Hierbei kann es sich um einen Cache handelt.</span><span class="sxs-lookup"><span data-stu-id="901f7-131">This may or may not involve cache.</span></span>

 <span data-ttu-id="901f7-132">*Daten Ergebnis* – das Ergebnis der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="901f7-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="901f7-133">Es handelt sich dabei um ein zweidimensionales Array, das alle Permutationen der Dimensionen "Members" enthält, und jedes Element, das die Mitgliedernamen der Dimensionen sowie die aggregierten Werte der angegebenen Maße enthält.</span><span class="sxs-lookup"><span data-stu-id="901f7-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>

 <span data-ttu-id="901f7-134">*Das Ergebnis ist aus dem Cache* -für Diagnosen.</span><span class="sxs-lookup"><span data-stu-id="901f7-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="901f7-135">Gibt an, ob das Ergebnis aus dem Cache oder aus dem QoE-Cube kam.</span><span class="sxs-lookup"><span data-stu-id="901f7-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>
