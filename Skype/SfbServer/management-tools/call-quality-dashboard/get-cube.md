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
ms.openlocfilehash: bbb2419fb66f6ecf397a2ccbcb4fe2858ce0d8fe
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569145"
---
# <a name="get-cube"></a>Abrufen von Cubes
 
**Zusammenfassung:** Informationen Sie zu den Cube abrufen-Vorgang, der Teil der Daten-API für die Qualitätsdashboard aufrufen, ist. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.
  
Die erste Cube-Operation ist Teil der Daten-API für die Qualitätsdashboard aufrufen.
  
## <a name="get-cube"></a>Abrufen von Cubes

Get-Cube-Operation wird die Liste der verfügbaren Dimensionen und Maßeinheiten.
  

|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Erhalten  <br/> |https://\<Portal\>/QoEDataService/CubeStructure  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** - None.
  
 **Anfordern von Kopfzeilen** - keine zusätzlichen Header.
  
 **Anforderungstextkörper** – None.
  
 **Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.
  
 **Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).
  
 **Antwortheader** - keine zusätzlichen Header.
  
 **Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON.
  
> [!NOTE]
> In diesem Beispiel werden die ersten zwei Elemente der einzelnen Gruppen der Cubeelemente nur angezeigt. 
  
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

 *KPIs* - reserviert. Im Abschnitt Key Performance Indicators, der eine Anforderungsnutzlast ermöglicht ausführen Abfragevorgang für die KPIs, die im Cube definiert Werte zurückgeben. Keine KPIs vorhanden noch im QoE Cube.
  
 *Dimensionen* - die Liste der Dimensionen, die in Filter und Dimensionen Abschnitten einer Anforderung Nutzlast für ausführen Abfragevorgang verwendet werden können. Um eine Dimension in einem Filterausdruck für verwenden, müssen Sie ein Dimensionselement angeben, die mit Dimensionselemente Get-Operation abgerufen werden können.
  
 *Maßeinheiten* – die Liste der Maßeinheiten, die im Abschnitt einer Anforderung Nutzlast Maßangaben für ausführen Abfragevorgang verwendet werden können.
  

