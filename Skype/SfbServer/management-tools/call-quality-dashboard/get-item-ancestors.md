---
title: Abrufen von übergeordneten Elementen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 'Zusammenfassung: Informationen Sie zum Vorgang Element Vorgänger erhalten möchten, der Teil der Element-Dienst ist. Der Element-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: 7afeecb81d1933b0a308b174e49f6d8ff45a93dd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873112"
---
# <a name="get-item-ancestors"></a>Abrufen von übergeordneten Elementen
 
**Zusammenfassung:** Informationen Sie zum Vorgang Element Vorgänger erhalten möchten, der Teil der Element-Dienst ist. Der Element-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.
  
Der erste Artikel Vorgänger Vorgang ist Teil des Diensts Element in der Repository-API für die Qualitätsdashboard aufrufen.
  
## <a name="get-item-ancestors"></a>Abrufen von übergeordneten Elementen

Get-Element Vorgänger gibt ein Vorgänger bestimmte Elemente aus dem Repository zurück.
  

|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Erhalten  <br/> |https://\<Portal\>/QoERepositoryService/Repository/ItemAncestors / {ItemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** - None.
  
 **Anfordern von Kopfzeilen** - keine zusätzlichen Header.
  
 **Anforderungstextkörper** – None.
  
 **Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.
  
 **Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK). Wenn einen angegebenen Benutzer-ID nicht gefunden wurde, wird der Statuscode 404 (nicht gefunden) zurückgegeben.
  
 **Antwortheader** - keine zusätzlichen Header.
  
 **Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON.
  
```
[{
"item1": 1653,
"item2": 0,
"item3": "Audio Streams Monthly Trend"
},
{
"item1": 1652,
"item2": 1,
"item3": "All Audio Streams"
}]
```

 *Item1* - ID des Elements.
  
 *Item2* - Tiefe wird der Abstand zwischen dem Element. 0 ist der unmittelbar übergeordnet.
  
 *Item3* - Titel des Elements.
  

