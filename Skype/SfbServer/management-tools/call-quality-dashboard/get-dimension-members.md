---
title: Abrufen von Dimensionselementen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Zusammenfassung: Informationen Sie zum Vorgang Dimensionselemente abrufen. Der erste Dimensionselemente-Vorgang ist Teil der Daten-API für die Qualitätsdashboard aufrufen. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: 59cc44cfabca8f216b9d03046fbe697daccbaee2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897101"
---
# <a name="get-dimension-members"></a>Abrufen von Dimensionselementen
 
**Zusammenfassung:** Informationen Sie zu den Vorgang Dimensionselemente abrufen. Der erste Dimensionselemente-Vorgang ist Teil der Daten-API für die Qualitätsdashboard aufrufen. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.
  
Der erste Dimensionselemente-Vorgang ist Teil der Daten-API für die Qualitätsdashboard aufrufen.
  
## <a name="get-dimension-members"></a>Abrufen von Dimensionselementen

Dimensionselemente Abrufvorgang gibt die Liste der Mitglieder einer bestimmten Dimension zurück. Es auch bieten die Möglichkeit zum Filtern der Memberliste und erhalten Sie eine Teilmenge die Leitung Übertragung Kosten zu senken.
  

|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Bereitstellen  <br/> |https://\<Portal\>/QoEDataService/DimensionMembers  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** - None.
  
 **Anfordern von Kopfzeilen** - keine zusätzlichen Header.
  
 **Anfordern Body** – dies der Name der Dimension, wir die Mitglieder für möchten, enthält. Maximale Anzahl der Elemente zurückgegeben werden, können neben Sie außerdem angeben einige Filter zum Einschränken der zurückgegebenen Elemente.
  
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

 **Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.
  
 **Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).
  
 **Antwortheader** - keine zusätzlichen Header.
  
 **Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON als Antwort auf eine Anforderung für "StartDate. [Monat] "Dimension.
  
> [!NOTE]
> Die Liste wird nur einen kleinen Teil der Liste angezeigt. 
  
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
