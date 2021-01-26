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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Zusammenfassung: Informationen zum Get Dimension Members-Vorgang. Der Vorgang "Dimensionsmashboard abrufen" ist Teil der Daten-API für das Anrufqualitätsdashboard. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: ffec3b02a3c876a003adb679a28b0e8f2edb91c2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832635"
---
# <a name="get-dimension-members"></a>Abrufen von Dimensionselementen
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Dimension-Elemente erhalten". Der Vorgang "Dimensionsmashboard abrufen" ist Teil der Daten-API für das Anrufqualitätsdashboard. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.
  
Der Vorgang "Dimensionsmashboard abrufen" ist Teil der Daten-API für das Anrufqualitätsdashboard.
  
## <a name="get-dimension-members"></a>Abrufen von Dimensionselementen

Der Vorgang "Dimensionsmdimensionen" gibt die Liste der Elemente einer bestimmten Dimension zurück. Es bietet auch die Möglichkeit, die Mitgliederliste zu filtern und eine Teilmenge zu erhalten, um die Übertragungskosten zu reduzieren.
  

|**Methode**|**Anforderungs-URI**|**HTTP Version**|
|:-----|:-----|:-----|
|POST  <br/> |https:// \<portal\> /QoEDataService/DimensionMembers  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** : Keine.
  
 **Anforderungsheader** – Keine zusätzlichen Header.
  
 **Anforderungstext** : Enthält den Namen der Dimension, für die die Elemente verwendet werden soll. Außerdem können Sie eine maximale Anzahl von zurückgegebenen Mitgliedern angeben, neben der Sie einige Filter angeben können, um die zurückgegebenen Elemente zu begrenzen.
  
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
  
 **Antwortheader** : Keine zusätzlichen Header.
  
 **Antworttext** : Unten sehen Sie eine Beispielantwortnutzlast in JSON als Antwort auf eine Anforderung für "[StartDate]. [Month]"-Dimension.
  
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
