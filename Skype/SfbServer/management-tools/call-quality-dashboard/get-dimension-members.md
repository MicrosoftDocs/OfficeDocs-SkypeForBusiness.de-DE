---
title: Abrufen von Dimensionselementen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang zum Abrufen von Dimensionselementen. Der Vorgang zum Abrufen von Dimensionselementen ist Teil der Daten-API für das Dashboard für die Anrufqualität. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: c457e7f3b42aaeb11c35180bc4c1ae6ee42b914e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274751"
---
# <a name="get-dimension-members"></a>Abrufen von Dimensionselementen
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang zum Abrufen von Dimensionselementen. Der Vorgang zum Abrufen von Dimensionselementen ist Teil der Daten-API für das Dashboard für die Anrufqualität. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.
  
Der Vorgang zum Abrufen von Dimensionselementen ist Teil der Daten-API für das Dashboard für die Anrufqualität.
  
## <a name="get-dimension-members"></a>Abrufen von Dimensionselementen

Der Vorgang zum Abrufen von Dimensionselementen gibt die Liste der Elemente einer bestimmten Dimension zurück. Darüber hinaus können Sie die Mitgliederliste Filtern und eine Teilmenge abrufen, um die Übertragungskosten zu reduzieren.
  

|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Bereitstellen  <br/> |https://\<-\>Portal/QoEDataService/DimensionMembers  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** -None.
  
 **Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.
  
 **Anforderungstext** – dieser enthält den Namen der Dimension, für die die Mitglieder angezeigt werden sollen. Außerdem können Sie die maximale Anzahl der zurückgegebenen Mitglieder angeben, indem Sie einige Filter angeben, um die zurückgegebenen Member zu begrenzen.
  
```
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 **Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.
  
 **Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.
  
 **Antwortheader** – keine zusätzlichen Überschriften.
  
 **Antworttext** : Nachfolgend finden Sie eine Beispielantwort Nutzlast in JSON als Antwort auf eine Anforderung für "[StartDate]. [Month] "-Dimension.
  
> [!NOTE]
> In der Liste wird nur ein kleiner Teil der Liste angezeigt. 
  
```
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
