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
# <a name="run-query"></a>Ausführen von Abfragen

**Zusammenfassung:** Informieren Sie sich über den Vorgang zum Ausführen von Abfragen, der Teil der Daten-API für die Anruf Qualitätssteuerung ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.

Der Vorgang "Abfrage ausführen" ist Teil der Daten-API für die Anruf Qualitätssteuerung.

## <a name="run-query"></a>Ausführen von Abfragen

Abfragevorgang ausführen bietet die Möglichkeit, eine Abfrage auf dem Cube basierend auf angegebenen Dimensionen, Maßen und Filtern auszuführen und die Daten zurückzugeben.


|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Bereitstellen  <br/> |https://\<-\>Portal/QoEDataService/RunQuery  <br/> |HTTP/1.1  <br/> |

 **URI-Parameter** -None.

 **Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.

 **Anforderungstext** – hier finden Sie eine Beispiel Nutzlast für Anforderungen in JSON. Sie enthält Dimensionen, Filter und Maße, die für eine Abfrage erforderlich sind.

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

 *Filter* – eine Liste der Filterausdrücke, die angewendet werden sollen, sodass die resultierende Datenmenge nur die Teilmenge der Daten reflektiert, die von Interesse sind.

 *Dimensionen* – eine Liste von Dimensionen, die für die Aggregation der Daten verwendet werden. Mindestens eine Dimension ist erforderlich, aber es können mehrere Dimensionen angegeben werden, um eine zusätzliche Ebene von unter Aggregationen zu erhalten.

 *Maße* – eine Liste von Maßen, die auch als "Facts" bezeichnet werden, die die gewünschten Metriken sind, die basierend auf den von Ihnen angegebenen Dimensionen aggregiert werden.

 *Trend* – zusätzliche Steueranweisungen zum Anpassen der Ergebnisdaten.

 **Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.

 **Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.

 **Antwortheader** – keine zusätzlichen Überschriften.

 **Antworttext** : Nachfolgend finden Sie eine Beispielantwort Nutzlast in JSON. Sie enthält eine Datentabelle, die die Daten enthält, außerdem enthält Sie eine Meta-Datei, die die Ausführungszeit der Abfrage zeigt und angibt, ob die Daten aus dem Cache abgerufen werden.

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

 *Ausführungszeit* : die Gesamtzeit, die der Server zum Zurückgeben der Daten benötigte. Hierbei kann es sich um einen Cache handelt.

 *Daten Ergebnis* – das Ergebnis der Abfrage. Es handelt sich dabei um ein zweidimensionales Array, das alle Permutationen der Dimensionen "Members" enthält, und jedes Element, das die Mitgliedernamen der Dimensionen sowie die aggregierten Werte der angegebenen Maße enthält.

 *Das Ergebnis ist aus dem Cache* -für Diagnosen. Gibt an, ob das Ergebnis aus dem Cache oder aus dem QoE-Cube kam.
