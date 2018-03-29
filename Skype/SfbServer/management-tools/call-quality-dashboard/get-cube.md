---
title: Abrufen von Cubes
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Zusammenfassung: Informationen Sie zum Vorgang Cube abrufen, der Teil der Daten-API für die Qualitätsdashboard aufrufen, ist. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.'
ms.openlocfilehash: e39a88e249dc807b201b08d966285d93ae7f82a6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="get-cube"></a><span data-ttu-id="0eef9-104">Abrufen von Cubes</span><span class="sxs-lookup"><span data-stu-id="0eef9-104">Get Cube</span></span>
 
<span data-ttu-id="0eef9-105">**Zusammenfassung:** Informationen Sie zu den Cube abrufen-Vorgang, der Teil der Daten-API für die Qualitätsdashboard aufrufen, ist.</span><span class="sxs-lookup"><span data-stu-id="0eef9-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="0eef9-106">Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0eef9-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="0eef9-107">Die erste Cube-Operation ist Teil der Daten-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0eef9-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="0eef9-108">Abrufen von Cubes</span><span class="sxs-lookup"><span data-stu-id="0eef9-108">Get Cube</span></span>

<span data-ttu-id="0eef9-109">Get-Cube-Operation wird die Liste der verfügbaren Dimensionen und Maßeinheiten.</span><span class="sxs-lookup"><span data-stu-id="0eef9-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="0eef9-110">**Methode**</span><span class="sxs-lookup"><span data-stu-id="0eef9-110">**Method**</span></span>|<span data-ttu-id="0eef9-111">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="0eef9-111">**Request URI**</span></span>|<span data-ttu-id="0eef9-112">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="0eef9-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0eef9-113">Erhalten</span><span class="sxs-lookup"><span data-stu-id="0eef9-113">GET</span></span>  <br/> |<span data-ttu-id="0eef9-114">https://\<Portal\>/QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="0eef9-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="0eef9-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="0eef9-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="0eef9-116">**URI-Parameter** - None.</span><span class="sxs-lookup"><span data-stu-id="0eef9-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="0eef9-117">**Anfordern von Kopfzeilen** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="0eef9-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0eef9-118">**Anforderungstextkörper** – None.</span><span class="sxs-lookup"><span data-stu-id="0eef9-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="0eef9-119">**Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.</span><span class="sxs-lookup"><span data-stu-id="0eef9-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="0eef9-120">**Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="0eef9-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="0eef9-121">**Antwortheader** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="0eef9-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0eef9-122">**Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="0eef9-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0eef9-123">In diesem Beispiel werden die ersten zwei Elemente der einzelnen Gruppen der Cubeelemente nur angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0eef9-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
```
{
"Kpis": [{
"FriendlyName": "Poor Trend Month",
"DataModelName": "[KPIValue].Poor Trend Month",
"Description": null
},
{
"FriendlyName": "Poor Rate Trend Month",
"DataModelName": "[KPIValue].Poor Rate Trend Month",
"Description": null
}],
"Dimensions": [{
"Category": "Access Location Pair",
"Attributes": [{
"FriendlyName": "Location Pair",
"DataModelName": "[Access Location Pair].[Location Pair]",
"Description": "Description of Location Pair"
}]
},
{
"Category": "Audio Bandwidth Est",
"Attributes": [{
"FriendlyName": "Metric",
"DataModelName": "[Audio Bandwidth Est].[Metric]",
"Description": "Description of Metric"
}]
}],
"Measurements": [{
"FriendlyName": "Audio Streams Count",
"DataModelName": "[Measures].[Audio Streams Count]",
"Description": "Description of Audio Streams Count"
},
{
"FriendlyName": "Audio Good Streams JPDR Count",
"DataModelName": "[Measures].[Audio Good Streams JPDR Count]",
"Description": "Description of Audio Good Streams JPDR Count"
}]
}

```

 <span data-ttu-id="0eef9-124">*KPIs* - reserviert.</span><span class="sxs-lookup"><span data-stu-id="0eef9-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="0eef9-125">Im Abschnitt Key Performance Indicators, der eine Anforderungsnutzlast ermöglicht ausführen Abfragevorgang für die KPIs, die im Cube definiert Werte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="0eef9-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="0eef9-126">Keine KPIs vorhanden noch im QoE Cube.</span><span class="sxs-lookup"><span data-stu-id="0eef9-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="0eef9-127">*Dimensionen* - die Liste der Dimensionen, die in Filter und Dimensionen Abschnitten einer Anforderung Nutzlast für ausführen Abfragevorgang verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="0eef9-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="0eef9-128">Um eine Dimension in einem Filterausdruck für verwenden, müssen Sie ein Dimensionselement angeben, die mit Dimensionselemente Get-Operation abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="0eef9-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="0eef9-129">*Maßeinheiten* – die Liste der Maßeinheiten, die im Abschnitt einer Anforderung Nutzlast Maßangaben für ausführen Abfragevorgang verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="0eef9-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

