---
title: Ausführen der Abfrage
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 'Zusammenfassung: Informationen Sie zum Vorgang Abfrage ausführen, der Teil der Daten-API für die Qualitätsdashboard aufrufen, ist. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.'
ms.openlocfilehash: 720bcc16b89ed2cd2b92eababb389d6c363d734d
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26293903"
---
# <a name="run-query"></a><span data-ttu-id="635fb-104">Ausführen der Abfrage</span><span class="sxs-lookup"><span data-stu-id="635fb-104">Run Query</span></span>

<span data-ttu-id="635fb-105">**Zusammenfassung:** Informationen Sie zu den Vorgang Abfrage ausführen, der Teil der Daten-API für die Qualitätsdashboard aufrufen, ist.</span><span class="sxs-lookup"><span data-stu-id="635fb-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="635fb-106">Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="635fb-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>

<span data-ttu-id="635fb-107">Führen Sie beim Abfragevorgang ist Teil der Daten-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="635fb-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>

## <a name="run-query"></a><span data-ttu-id="635fb-108">Ausführen der Abfrage</span><span class="sxs-lookup"><span data-stu-id="635fb-108">Run Query</span></span>

<span data-ttu-id="635fb-109">Führen Sie Abfrage Vorgang die Möglichkeit zum Ausführen einer Abfrage für den Cube basierend auf angegebenen Dimensionen, Maßeinheiten und Filter bietet und wieder zurückgeben Sie die Daten.</span><span class="sxs-lookup"><span data-stu-id="635fb-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>


|<span data-ttu-id="635fb-110">**Methode**</span><span class="sxs-lookup"><span data-stu-id="635fb-110">**Method**</span></span>|<span data-ttu-id="635fb-111">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="635fb-111">**Request URI**</span></span>|<span data-ttu-id="635fb-112">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="635fb-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="635fb-113">Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="635fb-113">POST</span></span>  <br/> |<span data-ttu-id="635fb-114">https://\<Portal\>/QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="635fb-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="635fb-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="635fb-115">HTTP/1.1</span></span>  <br/> |

 <span data-ttu-id="635fb-116">**URI-Parameter** - None.</span><span class="sxs-lookup"><span data-stu-id="635fb-116">**URI Parameters** - None.</span></span>

 <span data-ttu-id="635fb-117">**Anfordern von Kopfzeilen** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="635fb-117">**Request Headers** - No additional headers.</span></span>

 <span data-ttu-id="635fb-118">**Anforderungstext** – hier ist ein Beispiel Anforderungsnutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="635fb-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="635fb-119">Sie enthält Dimensionen, Filter und Messung für eine Abfrage erforderlich.</span><span class="sxs-lookup"><span data-stu-id="635fb-119">It contains dimensions, filters, and measurement required for a query.</span></span>

```
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

 <span data-ttu-id="635fb-120">*Filter* - eine Liste von Filterausdrücken angewendet werden soll, beispielsweise, dass sich das resultierende DataSet nur die Teilmenge der Daten, die von Interesse sind.</span><span class="sxs-lookup"><span data-stu-id="635fb-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>

 <span data-ttu-id="635fb-121">*Dimensionen* - eine Liste der Dimensionen, die für das Aggregieren von Daten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="635fb-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="635fb-122">Mindestens eine Dimension ist erforderlich, aber mehrere Dimensionen angegeben werden können, um zusätzliche untergeordnete Aggregations erhalten.</span><span class="sxs-lookup"><span data-stu-id="635fb-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>

 <span data-ttu-id="635fb-123">*Maßeinheiten* - eine Liste von Maßeinheiten, auch bekannt als Fakten, dass die gewünschten Metriken aggregiert werden auf die Dimensionen basieren, den Sie angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="635fb-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>

 <span data-ttu-id="635fb-124">*Trend* - zusätzliche Kontrolle Anweisungen zum Anpassen der Ergebnisdaten.</span><span class="sxs-lookup"><span data-stu-id="635fb-124">*Trend*  - Additional control instructions to customize the result data.</span></span>

 <span data-ttu-id="635fb-125">**Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.</span><span class="sxs-lookup"><span data-stu-id="635fb-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>

 <span data-ttu-id="635fb-126">**Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="635fb-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>

 <span data-ttu-id="635fb-127">**Antwortheader** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="635fb-127">**Response Headers** - No additional headers.</span></span>

 <span data-ttu-id="635fb-128">**Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="635fb-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="635fb-129">Er enthält eine Datentabelle, die die Daten enthält, enthält auch ein Metadaten, der Ausführung der Abfrage und unabhängig davon, ob die Daten aus dem Cache werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="635fb-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>

```
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

 <span data-ttu-id="635fb-130">*Ausführungszeit* - die gesamte Zeit für den Server, die Daten zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="635fb-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="635fb-131">Dies kann oder darf sich nicht Cache beziehen.</span><span class="sxs-lookup"><span data-stu-id="635fb-131">This may or may not involve cache.</span></span>

 <span data-ttu-id="635fb-132">*Datenergebnis* – das Ergebnis der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="635fb-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="635fb-133">Es ist ein zweidimensionales Array, die alle Variationen der Dimensionen Mitglieder und jedes Element, enthält der Dimensionen Elementnamen als auch die aggregierten Werte aus den angegebenen enthält.</span><span class="sxs-lookup"><span data-stu-id="635fb-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>

 <span data-ttu-id="635fb-134">*Ergebnis ist aus Cache* - Diagnose.</span><span class="sxs-lookup"><span data-stu-id="635fb-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="635fb-135">Gibt an, ob das Ergebnis aus dem Zwischenspeicher oder aus dem QoE-Cube stammt.</span><span class="sxs-lookup"><span data-stu-id="635fb-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>