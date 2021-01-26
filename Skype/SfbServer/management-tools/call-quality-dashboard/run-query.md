---
title: Ausführen einer Abfrage
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 'Zusammenfassung: Informationen zum Ausführen des Abfragevorgangs, der Teil der Daten-API für das Anrufqualitätsdashboard ist. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: bff24ca5a4d651ba276b4b0d795afabce3c6d0dd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803115"
---
# <a name="run-query"></a>Ausführen einer Abfrage

**Zusammenfassung:** Erfahren Sie mehr über den Abfragevorgang ausführen, der Teil der Daten-API für das Anrufqualitätsdashboard ist. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.

Der Vorgang "Abfrage ausführen" ist Teil der Daten-API für das Anrufqualitätsdashboard.

## <a name="run-query"></a>Ausführen einer Abfrage

Der Abfragevorgang ausführen ermöglicht das Ausführen einer Abfrage für den Cube basierend auf angegebenen Dimensionen, Messungen und Filtern sowie das Zurückgeben der Daten.


|**Methode**|**Anforderungs-URI**|**HTTP Version**|
|:-----|:-----|:-----|
|POST  <br/> |https:// \<portal\> /QoEDataService/RunQuery  <br/> |HTTP/1.1  <br/> |

 **URI-Parameter** : Keine.

 **Anforderungsheader** – Keine zusätzlichen Header.

 **Anforderungstext** : Hier sehen Sie eine Beispielanforderungsnutzlast in JSON. Sie enthält Dimensionen, Filter und Maßangaben, die für eine Abfrage erforderlich sind.

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

 *Filter*  – Eine Liste der anzuwendenden Filterausdrücke, damit der resultierende Datensatz nur die Teilmenge der daten wiederspiegelt, die von Interesse sind.

 *Dimensionen*  – Eine Liste der Dimensionen, die zum Aggregieren der Daten verwendet werden. Mindestens eine Dimension ist erforderlich, es können jedoch mehrere Dimensionen angegeben werden, um zusätzliche Ebenen von Unteraggregationen zu erhalten.

 *Messungen*  – Eine Liste von Messungen, auch bekannt als Fakten, die die gewünschten Metriken sind, die basierend auf den angegebenen Dimensionen aggregiert werden sollen.

 *Trend*  – Zusätzliche Steuerelementanweisungen zum Anpassen der Ergebnisdaten.

 **Antwort** : Die Antwort enthält einen HTTP-Statuscode und eine Reihe von Antwortheadern.

 **Statuscode** : Ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.

 **Antwortheader** : Keine zusätzlichen Header.

 **Antworttext** : Unten finden Sie eine Beispielantwortnutzlast in JSON. Sie enthält eine Datentabelle, die die Daten enthält. Außerdem enthält sie eine Metadaten, die die Abfrageausführungszeit und zeigt, ob die Daten aus dem Cache stammt.

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

 *Ausführungszeit*  – Die Gesamtzeit, die der Server zum Zurückgeben der Daten brauchte. Dies kann den Cache umfassen oder nicht.

 *Datenergebnis*  – Das Ergebnis der Abfrage. Es handelt sich um ein zweidimensionales Array, das alle Permutationen der Dimensionselemente und jedes Element enthält, das die Elementnamen der Dimensionen sowie die aggregierten Werte der angegebenen Messungen enthält.

 *Ergebnis ist "Aus Cache"*  – für die Diagnose. Gibt an, ob das Ergebnis aus dem Cache oder aus dem QoE-Cube stammt.
