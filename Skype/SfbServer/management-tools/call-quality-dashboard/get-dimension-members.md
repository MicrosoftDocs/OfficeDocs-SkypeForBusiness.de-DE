---
title: Abrufen von Dimensionselementen
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Zusammenfassung: Erfahren Sie mehr über den Vorgang "Dimension-Elemente abrufen". Der Vorgang "Dimension-Elemente abrufen" ist Teil der Daten-API für das Anrufqualitäts-Dashboard. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 701a44d8d226b7953938b9a07883ff556ecbd7ec
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58629597"
---
# <a name="get-dimension-members"></a>Abrufen von Dimensionselementen
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Dimension-Elemente abrufen". Der Vorgang "Dimension-Elemente abrufen" ist Teil der Daten-API für das Anrufqualitäts-Dashboard. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.
  
Der Vorgang "Dimension-Elemente abrufen" ist Teil der Daten-API für das Anrufqualitäts-Dashboard.
  
## <a name="get-dimension-members"></a>Abrufen von Dimensionselementen

Der Vorgang "Dimension-Elemente abrufen" gibt die Liste der Elemente einer bestimmten Dimension zurück. Es bietet auch die Möglichkeit, die Mitgliederliste zu filtern und eine Teilmenge abzurufen, um die Übertragungskosten zu reduzieren.
  

|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|POST  <br/> |https:// \<portal\> /QoEDataService/DimensionMembers  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** : Keine.
  
 **Anforderungsheader** – keine zusätzlichen Kopfzeilen.
  
 **Anforderungstext** : Enthält den Namen der Dimension, für die die Elemente vorgesehen sind. Außerdem können Sie die maximale Anzahl der zurückgegebenen Elemente angeben, neben denen Sie filtern können, um die zurückgegebenen Elemente zu begrenzen.
  
```json
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 **Antwort** : Die Antwort enthält einen HTTP-Statuscode und eine Reihe von Antwortheadern.
  
 **Statuscode** : Ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.
  
 **Antwortheader** – keine zusätzlichen Kopfzeilen.
  
 **Antworttext** – Unten sehen Sie eine Beispielantwortnutzlast in JSON als Antwort auf eine Anforderung für "[StartDate]. [Monat]"-Dimension.
  
> [!NOTE]
> Die Liste zeigt nur einen kleinen Teil der Liste an. 
  
```json
{
"MembersCount": 493,
"Members": [["[1990-01-01T00:00:00]",
"January 1990"],
["[1990-02-01T00:00:00]",
"February 1990"],
["[1990-03-01T00:00:00]",
"March 1990"],
 
    ...
    
["[2030-10-01T00:00:00]",
"October 2030"],
["[2030-11-01T00:00:00]",
"November 2030"],
["[2030-12-01T00:00:00]",
"December 2030"],
["[2031-01-01T00:00:00]",
"January 2031"]]
}
```
