---
title: Abrufen eines Elements
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
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Zusammenfassung: Erfahren Sie mehr über den Vorgang "Element abrufen", der Teil des Elementdiensts ist. Der Elementdienst ist Teil der Repository-API für das Anrufqualitäts-Dashboard. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: fa82d158b41826a950a852633e6c039e9262543d4aabece5c04397eba40be8ae
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278443"
---
# <a name="get-item"></a>Abrufen eines Elements
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Element abrufen", der Teil des Elementdiensts ist. Der Elementdienst ist Teil der Repository-API für das Anrufqualitäts-Dashboard. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.
  
Der Vorgang "Element abrufen" ist Teil des Elementdiensts in der Repository-API für das Anrufqualitätsdashboard.
  
## <a name="get-item"></a>Abrufen eines Elements

"Element abrufen" gibt ein bestimmtes Element im Repository zurück.
  
|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** : Keine.
  
 **Anforderungsheader** – keine zusätzlichen Kopfzeilen.
  
 **Anforderungstext** : Keine.
  
 **Antwort** : Die Antwort enthält einen HTTP-Statuscode und eine Reihe von Antwortheadern.
  
 **Statuscode** : Ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück. Wenn eine angegebene Element-ID nicht gefunden wird, wird der Statuscode 404 (Nicht gefunden) zurückgegeben.
  
 **Antwortheader** – keine zusätzlichen Kopfzeilen.
  
 **Antworttext** : Unten sehen Sie eine Beispielantwortnutzlast in JSON.
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 *itemId*  – ID des Elements.
  
 *userId*  – ID des Benutzers, der dieses Element besitzt.
  
 *content*  – Der anwendungsspezifische Inhalt.
  
 *type*  – Der Typ des Inhalts. Dieses Feld wird von den Anwendungen festgelegt.
  
 *subItemIds*  – Die IDs von Untergeordneten Elementen, falls vorhanden. Dies ist ein Kurzschluss des Vorgangs "Get Sub-Items" zum Speichern eines Anrufs. Anwendungen können alternativ die gleichen Informationen mithilfe des Vorgangs "Get Sub-Items" abrufen.
  

