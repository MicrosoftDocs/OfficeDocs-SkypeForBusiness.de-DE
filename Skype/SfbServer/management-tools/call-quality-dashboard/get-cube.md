---
title: Abrufen von Cubes
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Zusammenfassung: Informationen Sie zum Vorgang Cube abrufen, der Teil der Daten-API für die Qualitätsdashboard aufrufen, ist. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: 3d6d1ceecb330219bdc563ca126bb13c49d1902b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886880"
---
# <a name="get-cube"></a><span data-ttu-id="049ce-104">Abrufen von Cubes</span><span class="sxs-lookup"><span data-stu-id="049ce-104">Get Cube</span></span>
 
<span data-ttu-id="049ce-105">**Zusammenfassung:** Informationen Sie zu den Cube abrufen-Vorgang, der Teil der Daten-API für die Qualitätsdashboard aufrufen, ist.</span><span class="sxs-lookup"><span data-stu-id="049ce-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="049ce-106">Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="049ce-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="049ce-107">Die erste Cube-Operation ist Teil der Daten-API für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="049ce-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="049ce-108">Abrufen von Cubes</span><span class="sxs-lookup"><span data-stu-id="049ce-108">Get Cube</span></span>

<span data-ttu-id="049ce-109">Get-Cube-Operation wird die Liste der verfügbaren Dimensionen und Maßeinheiten.</span><span class="sxs-lookup"><span data-stu-id="049ce-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="049ce-110">**Methode**</span><span class="sxs-lookup"><span data-stu-id="049ce-110">**Method**</span></span>|<span data-ttu-id="049ce-111">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="049ce-111">**Request URI**</span></span>|<span data-ttu-id="049ce-112">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="049ce-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="049ce-113">Erhalten</span><span class="sxs-lookup"><span data-stu-id="049ce-113">GET</span></span>  <br/> |<span data-ttu-id="049ce-114">https://\<Portal\>/QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="049ce-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="049ce-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="049ce-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="049ce-116">**URI-Parameter** - None.</span><span class="sxs-lookup"><span data-stu-id="049ce-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="049ce-117">**Anfordern von Kopfzeilen** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="049ce-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="049ce-118">**Anforderungstextkörper** – None.</span><span class="sxs-lookup"><span data-stu-id="049ce-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="049ce-119">**Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.</span><span class="sxs-lookup"><span data-stu-id="049ce-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="049ce-120">**Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="049ce-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="049ce-121">**Antwortheader** - keine zusätzlichen Header.</span><span class="sxs-lookup"><span data-stu-id="049ce-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="049ce-122">**Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="049ce-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="049ce-123">In diesem Beispiel werden die ersten zwei Elemente der einzelnen Gruppen der Cubeelemente nur angezeigt.</span><span class="sxs-lookup"><span data-stu-id="049ce-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
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

 <span data-ttu-id="049ce-124">*KPIs* - reserviert.</span><span class="sxs-lookup"><span data-stu-id="049ce-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="049ce-125">Im Abschnitt Key Performance Indicators, der eine Anforderungsnutzlast ermöglicht ausführen Abfragevorgang für die KPIs, die im Cube definiert Werte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="049ce-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="049ce-126">Keine KPIs vorhanden noch im QoE Cube.</span><span class="sxs-lookup"><span data-stu-id="049ce-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="049ce-127">*Dimensionen* - die Liste der Dimensionen, die in Filter und Dimensionen Abschnitten einer Anforderung Nutzlast für ausführen Abfragevorgang verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="049ce-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="049ce-128">Um eine Dimension in einem Filterausdruck für verwenden, müssen Sie ein Dimensionselement angeben, die mit Dimensionselemente Get-Operation abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="049ce-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="049ce-129">*Maßeinheiten* – die Liste der Maßeinheiten, die im Abschnitt einer Anforderung Nutzlast Maßangaben für ausführen Abfragevorgang verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="049ce-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

