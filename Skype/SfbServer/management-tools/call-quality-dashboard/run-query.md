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
ms.openlocfilehash: 3720ce118537963e5093741c4f05315e887bd60d
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569747"
---
# <a name="run-query"></a>Ausführen der Abfrage
 
**Zusammenfassung:** Informationen Sie zu den Vorgang Abfrage ausführen, der Teil der Daten-API für die Qualitätsdashboard aufrufen, ist. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.
  
Führen Sie beim Abfragevorgang ist Teil der Daten-API für die Qualitätsdashboard aufrufen.
  
## <a name="run-query"></a>Ausführen der Abfrage

Führen Sie Abfrage Vorgang die Möglichkeit zum Ausführen einer Abfrage für den Cube basierend auf angegebenen Dimensionen, Maßeinheiten und Filter bietet und wieder zurückgeben Sie die Daten.
  

|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Bereitstellen  <br/> |https://\<Portal\>/QoEDataService/RunQuery  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** - None.
  
 **Anfordern von Kopfzeilen** - keine zusätzlichen Header.
  
 **Anforderungstext** – hier ist ein Beispiel Anforderungsnutzlast in JSON. Sie enthält Dimensionen, Filter und Messung für eine Abfrage erforderlich.
  
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

 *Filter* - eine Liste von Filterausdrücken angewendet werden soll, beispielsweise, dass sich das resultierende DataSet nur die Teilmenge der Daten, die von Interesse sind.
  
 *Dimensionen* - eine Liste der Dimensionen, die für das Aggregieren von Daten verwendet werden. Mindestens eine Dimension ist erforderlich, aber mehrere Dimensionen angegeben werden können, um zusätzliche untergeordnete Aggregations erhalten.
  
 *Maßeinheiten* - eine Liste von Maßeinheiten, auch bekannt als Fakten, dass die gewünschten Metriken aggregiert werden auf die Dimensionen basieren, den Sie angegeben haben.
  
 *Trend* - zusätzliche Kontrolle Anweisungen zum Anpassen der Ergebnisdaten.
  
 **Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.
  
 **Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).
  
 **Antwortheader** - keine zusätzlichen Header.
  
 **Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON. Er enthält eine Datentabelle, die die Daten enthält, enthält auch ein Metadaten, der Ausführung der Abfrage und unabhängig davon, ob die Daten aus dem Cache werden angezeigt.
  
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

 *Ausführungszeit* - die gesamte Zeit für den Server, die Daten zurückgeben. Dies kann oder darf sich nicht Cache beziehen.
  
 *Datenergebnis* – das Ergebnis der Abfrage. Es ist ein zweidimensionales Array, die alle Variationen der Dimensionen Mitglieder und jedes Element, enthält der Dimensionen Elementnamen als auch die aggregierten Werte aus den angegebenen enthält.
  
 *Ergebnis ist aus Cache* - Diagnose. Gibt an, ob das Ergebnis aus dem Zwischenspeicher oder aus dem QoE-Cube stammt.