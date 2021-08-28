---
title: Abrufen von untergeordneten Elementen
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
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Zusammenfassung: Erfahren Sie mehr über den Vorgang "Get Sub-Items", der Teil des Elementdiensts ist. Der Elementdienst ist Teil der Repository-API für das Anrufqualitäts-Dashboard. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 0fb1421d604cce450d28077558f2d00f20c2ff01
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58591119"
---
# <a name="get-sub-items"></a>Abrufen von untergeordneten Elementen
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Get Sub-Items", der Teil des Elementdiensts ist. Der Elementdienst ist Teil der Repository-API für das Anrufqualitäts-Dashboard. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.
  
Der Vorgang "Abrufen Sub-Items" ist Teil des Elementdiensts in der Repository-API für das Anrufqualitätsdashboard.
  
## <a name="get-sub-items"></a>Abrufen von untergeordneten Elementen

Dient zum Abrufen Sub-Items gibt die Unterelemente eines bestimmten Elements zurück.
  

|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}/subitem  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** : Keine.
  
 **Anforderungsheader** – keine zusätzlichen Kopfzeilen.
  
 **Anforderungstext** : Keine.
  
 **Antwort** : Die Antwort enthält einen HTTP-Statuscode und eine Reihe von Antwortheadern.
  
 **Statuscode** : Ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück. Wenn eine angegebene Benutzer-ID nicht gefunden wird, wird der Statuscode 404 (Nicht gefunden) zurückgegeben.
  
 **Antwortheader** – keine zusätzlichen Kopfzeilen.
  
 **Antworttext** : Unten sehen Sie eine Beispielantwortnutzlast in JSON.
  
> [!NOTE]
> Ein Array des Item-Objekts wird zurückgegeben. 
  
```json
[{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1710,
"userId": 0,
"type": "json"
}]
```

Das von Sub-Items Vorgang zurückgegebene Item-Objekt enthält nur die folgenden drei Felder. 
  
 *itemId*  – ID des Elements.
  
 *userId*  – ID des Benutzers, der dieses Element besitzt.
  
 *type*  – Der Typ des Inhalts. Dieses Feld wird von den Anwendungen festgelegt.
  
> [!NOTE]
>  `Content` und `subItems` Felder sind nicht in der Antwort enthalten, um die Menge der über das Netzwerk übertragenen Daten zu reduzieren.
  

