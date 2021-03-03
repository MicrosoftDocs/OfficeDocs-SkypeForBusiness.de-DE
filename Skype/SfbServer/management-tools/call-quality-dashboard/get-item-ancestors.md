---
title: Abrufen von übergeordneten Elementen
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
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 'Zusammenfassung: Erfahren Sie mehr über den Vorgang "Element-Vorgänger", der Teil des Elementdiensts ist. Der Elementdienst ist Teil der Repository-API für das Anrufqualitätsdashboard. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 59fcd10f620b32151346e8732e67ae6151a258ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832575"
---
# <a name="get-item-ancestors"></a>Abrufen von übergeordneten Elementen
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Element-Vorgänger" (Get Item Ancestors), der Teil des Elementdiensts ist. Der Elementdienst ist Teil der Repository-API für das Anrufqualitätsdashboard. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.
  
Der Vorgang "Element-Vorgänger abrufen" ist Teil des Elementdiensts in der Repository-API für das Anrufqualitätsdashboard.
  
## <a name="get-item-ancestors"></a>Abrufen von übergeordneten Elementen

"Element-Vorgänger" gibt ein bestimmtes Element vorgänger aus dem Repository zurück.
  

|**Methode**|**Anforderungs-URI**|**HTTP Version**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/itemAncestors/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** : Keine.
  
 **Anforderungsheader** – Keine zusätzlichen Header.
  
 **Anforderungstext** – Keine.
  
 **Antwort** : Die Antwort enthält einen HTTP-Statuscode und eine Reihe von Antwortheadern.
  
 **Statuscode** : Ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück. Wenn eine angegebene Benutzer-ID nicht gefunden wird, wird der Statuscode 404 (Nicht gefunden) zurückgegeben.
  
 **Antwortheader** : Keine zusätzlichen Header.
  
 **Antworttext** : Unten finden Sie eine Beispielantwortnutzlast in JSON.
  
```json
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

 *Element1*  – ID des Elements.
  
 *Element2*  – Tiefe ist der Abstand zum Element. 0 ist das unmittelbar übergeordnete Element.
  
 *Element3*  – Titel des Elements.
  

