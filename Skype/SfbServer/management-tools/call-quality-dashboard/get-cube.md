---
title: Abrufen von Cubes
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
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang zum Abrufen von Cubes, der Teil der Daten-API für das Dashboard für die Anrufqualität ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 7ae24309ea49d8f7d8d2684c141adb44c5bff2b5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816834"
---
# <a name="get-cube"></a><span data-ttu-id="3a970-104">Abrufen von Cubes</span><span class="sxs-lookup"><span data-stu-id="3a970-104">Get Cube</span></span>
 
<span data-ttu-id="3a970-105">**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Cube abrufen", der Teil der Daten-API für die Anrufqualität ist.</span><span class="sxs-lookup"><span data-stu-id="3a970-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="3a970-106">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3a970-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="3a970-107">Der Vorgang zum Abrufen von Cubes ist Teil der Daten-API für das Dashboard für die Anrufqualität.</span><span class="sxs-lookup"><span data-stu-id="3a970-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="3a970-108">Abrufen von Cubes</span><span class="sxs-lookup"><span data-stu-id="3a970-108">Get Cube</span></span>

<span data-ttu-id="3a970-109">Get Cube Operation gibt die Liste der verfügbaren Dimensionen und Maße zurück.</span><span class="sxs-lookup"><span data-stu-id="3a970-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="3a970-110">**Methode**</span><span class="sxs-lookup"><span data-stu-id="3a970-110">**Method**</span></span>|<span data-ttu-id="3a970-111">**Anforderungs-URI**</span><span class="sxs-lookup"><span data-stu-id="3a970-111">**Request URI**</span></span>|<span data-ttu-id="3a970-112">**HTTP-Version**</span><span class="sxs-lookup"><span data-stu-id="3a970-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3a970-113">Erhalten</span><span class="sxs-lookup"><span data-stu-id="3a970-113">GET</span></span>  <br/> |<span data-ttu-id="3a970-114">https://\<-\>Portal/QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="3a970-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="3a970-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="3a970-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="3a970-116">**URI-Parameter** -None.</span><span class="sxs-lookup"><span data-stu-id="3a970-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="3a970-117">**Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="3a970-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="3a970-118">**Anforderungstext** – keine.</span><span class="sxs-lookup"><span data-stu-id="3a970-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="3a970-119">**Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.</span><span class="sxs-lookup"><span data-stu-id="3a970-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="3a970-120">**Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.</span><span class="sxs-lookup"><span data-stu-id="3a970-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="3a970-121">**Antwortheader** – keine zusätzlichen Überschriften.</span><span class="sxs-lookup"><span data-stu-id="3a970-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="3a970-122">**Antworttext** : Nachfolgend finden Sie eine Beispielantwort Nutzlast in JSON.</span><span class="sxs-lookup"><span data-stu-id="3a970-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3a970-123">In diesem Beispiel werden nur die ersten beiden Elemente der einzelnen Gruppen von Cube-Elementen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3a970-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
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

 <span data-ttu-id="3a970-124">*KPIs* – reserviert.</span><span class="sxs-lookup"><span data-stu-id="3a970-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="3a970-125">Der KPI-Abschnitt einer Anforderungsnutzlast ermöglicht das Ausführen des Abfragevorgangs, um Werte für die im Cube definierten KPIs zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="3a970-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="3a970-126">Im QoE-Cube sind noch keine KPIs vorhanden.</span><span class="sxs-lookup"><span data-stu-id="3a970-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="3a970-127">*Dimensionen* – die Liste der Dimensionen, die in den Abschnitten Filter und Dimensionen einer Anforderungsnutzlast für den Ausführungs Abfragevorgang verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="3a970-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="3a970-128">Wenn Sie eine Dimension in einem Filterausdruck verwenden möchten, müssen Sie ein Dimensionselement angeben, das mithilfe von Get Dimension Member Operation abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="3a970-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="3a970-129">*Maße* – die Liste der Messwerte, die im Abschnitt "Maße" einer Anforderungsnutzlast für die Ausführung des Abfragevorgangs verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="3a970-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

