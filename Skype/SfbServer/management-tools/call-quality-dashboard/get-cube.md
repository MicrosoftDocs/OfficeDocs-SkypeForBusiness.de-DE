---
title: Abrufen von Cubes
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Zusammenfassung: Erfahren Sie mehr über den Vorgang "Cube abrufen", der Teil der Daten-API für das Anrufqualitäts-Dashboard ist. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.'
---

# <a name="get-cube"></a>Abrufen von Cubes
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Cube abrufen", der Teil der Daten-API für das Anrufqualitäts-Dashboard ist. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.
  
Der Vorgang "Cube abrufen" ist Teil der Daten-API für das Anrufqualitäts-Dashboard.
  
## <a name="get-cube"></a>Abrufen von Cubes

Der Vorgang "Cube abrufen" gibt die Liste der verfügbaren Dimensionen und Maße zurück.
  

|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|GET  <br/> |\<portal\>https:///QoEDataService/CubeStructure  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** : Keine.
  
 **Anforderungsheader** – keine zusätzlichen Kopfzeilen.
  
 **Anforderungstext** : Keine.
  
 **Antwort** : Die Antwort enthält einen HTTP-Statuscode und eine Reihe von Antwortheadern.
  
 **Statuscode** : Ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.
  
 **Antwortheader** – keine zusätzlichen Kopfzeilen.
  
 **Antworttext** : Unten sehen Sie eine Beispielantwortnutzlast in JSON.
  
> [!NOTE]
> In diesem Beispiel werden nur die ersten beiden Elemente jeder Cube-Elementgruppen angezeigt. 
  
```json
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

 *KPIs*  – Reserviert. Der KPIs-Abschnitt einer Anforderungsnutzlast ermöglicht es dem Ausführen eines Abfragevorgangs, Werte für die im Cube definierten KPIs zurückzugeben. Im QoE-Cube sind noch keine KPIs vorhanden.
  
 *Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation. Um eine Dimension in einem Filterausdruck zu verwenden, müssen Sie ein Dimensionselement angeben, das mithilfe des Vorgangs "Dimension-Elemente abrufen" abgerufen werden kann.
  
 *Maßangaben*  – Die Liste der Messungen, die im Abschnitt "Messungen" einer Anforderungsnutzlast für den Vorgang "Abfrage ausführen" verwendet werden kann.
  

