---
title: Abrufen von Cubes
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang zum Abrufen von Cubes, der Teil der Daten-API für das Dashboard für die Anrufqualität ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 970187ce9f95700185ab09bd7aadf9045575b393
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274772"
---
# <a name="get-cube"></a>Abrufen von Cubes
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Cube abrufen", der Teil der Daten-API für die Anrufqualität ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.
  
Der Vorgang zum Abrufen von Cubes ist Teil der Daten-API für das Dashboard für die Anrufqualität.
  
## <a name="get-cube"></a>Abrufen von Cubes

Get Cube Operation gibt die Liste der verfügbaren Dimensionen und Maße zurück.
  

|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Erhalten  <br/> |https://\<-\>Portal/QoEDataService/CubeStructure  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** -None.
  
 **Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.
  
 **Anforderungstext** – keine.
  
 **Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.
  
 **Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.
  
 **Antwortheader** – keine zusätzlichen Überschriften.
  
 **Antworttext** : Nachfolgend finden Sie eine Beispielantwort Nutzlast in JSON.
  
> [!NOTE]
> In diesem Beispiel werden nur die ersten beiden Elemente der einzelnen Gruppen von Cube-Elementen angezeigt. 
  
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

 *KPIs* – reserviert. Der KPI-Abschnitt einer Anforderungsnutzlast ermöglicht das Ausführen des Abfragevorgangs, um Werte für die im Cube definierten KPIs zurückzugeben. Im QoE-Cube sind noch keine KPIs vorhanden.
  
 *Dimensionen* – die Liste der Dimensionen, die in den Abschnitten Filter und Dimensionen einer Anforderungsnutzlast für den Ausführungs Abfragevorgang verwendet werden können. Wenn Sie eine Dimension in einem Filterausdruck verwenden möchten, müssen Sie ein Dimensionselement angeben, das mithilfe von Get Dimension Member Operation abgerufen werden kann.
  
 *Maße* – die Liste der Messwerte, die im Abschnitt "Maße" einer Anforderungsnutzlast für die Ausführung des Abfragevorgangs verwendet werden können.
  

