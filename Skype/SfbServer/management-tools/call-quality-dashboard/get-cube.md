---
title: Abrufen von Cubes
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
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Zusammenfassung: Erfahren Sie mehr über den Vorgang zum Abrufen von Cubes, der Teil der Daten-API für das Anrufqualitätsdashboard ist. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: a3527f21bc1751c23bba088ae06c3e6702cb8c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832625"
---
# <a name="get-cube"></a>Abrufen von Cubes
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang zum Abrufen von Cubes, der Teil der Daten-API für das Anrufqualitätsdashboard ist. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.
  
Der Vorgang "Cube abrufen" ist Teil der Daten-API für das Anrufqualitätsdashboard.
  
## <a name="get-cube"></a>Abrufen von Cubes

Der Vorgang zum Erstellen eines Cubes gibt die Liste der verfügbaren Dimensionen und Messungen zurück.
  

|**Methode**|**Anforderungs-URI**|**HTTP Version**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoEDataService/CubeStructure  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** : Keine.
  
 **Anforderungsheader** – Keine zusätzlichen Header.
  
 **Anforderungstext** – Keine.
  
 **Antwort** : Die Antwort enthält einen HTTP-Statuscode und eine Reihe von Antwortheadern.
  
 **Statuscode** : Ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.
  
 **Antwortheader** : Keine zusätzlichen Header.
  
 **Antworttext** : Unten finden Sie eine Beispielantwortnutzlast in JSON.
  
> [!NOTE]
> In diesem Beispiel werden nur die ersten beiden Elemente jeder Gruppe von Cubeelementen angezeigt. 
  
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

 *KPIs*  – Reserviert. Im Abschnitt "KPIs" einer Anforderungsnutzlast können Sie mithilfe des Vorgangs "Abfrage ausführen" Werte für die im Cube definierten KPIs zurückgeben. Im QoE-Cube sind noch keine KPIs vorhanden.
  
 *Dimensionen*  – Die Liste der Dimensionen, die in den Abschnitten "Filter" und "Dimensionen" einer Anforderungsnutzlast für den Abfragevorgang "Ausführen" verwendet werden können. Wenn Sie eine Dimension in einem Filterausdruck verwenden möchten, müssen Sie ein Dimensionsmmitglied angeben, das mithilfe des Vorgangs "Dimensionsm elemente erhalten" erhalten werden kann.
  
 *Messungen*  – Die Liste der Messungen, die im Abschnitt "Messungen" einer Anforderungsnutzlast für den Abfragevorgang ausführen verwendet werden können.
  

