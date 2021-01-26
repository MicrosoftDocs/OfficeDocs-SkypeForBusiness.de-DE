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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Zusammenfassung: Informationen zum Get Sub-Items-Vorgang, der Teil des Elementdiensts ist. Der Elementdienst ist Teil der Repository-API für das Anrufqualitätsdashboard. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: defb0b898c5101513cbb4f6da4382a8bb43bce6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832505"
---
# <a name="get-sub-items"></a>Abrufen von untergeordneten Elementen
 
**Zusammenfassung:** Informationen zum Get Sub-Items-Vorgang, der Teil des Elementdiensts ist. Der Elementdienst ist Teil der Repository-API für das Anrufqualitätsdashboard. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.
  
Der Vorgang Sub-Items A0 ist Teil des Elementdiensts in der Repository-API für das Anrufqualitätsdashboard.
  
## <a name="get-sub-items"></a>Abrufen von untergeordneten Elementen

Get Sub-Items returns a specific Item's sub-items.
  

|**Methode**|**Anforderungs-URI**|**HTTP Version**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}/subitem  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** : Keine.
  
 **Anforderungsheader** – Keine zusätzlichen Header.
  
 **Anforderungstext** – Keine.
  
 **Antwort** : Die Antwort enthält einen HTTP-Statuscode und eine Reihe von Antwortheadern.
  
 **Statuscode** : Ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück. Wenn eine angegebene Benutzer-ID nicht gefunden wird, wird der Statuscode 404 (Nicht gefunden) zurückgegeben.
  
 **Antwortheader** : Keine zusätzlichen Header.
  
 **Antworttext** : Unten finden Sie eine Beispielantwortnutzlast in JSON.
  
> [!NOTE]
> Ein Array von Item -Objekt wird zurückgegeben. 
  
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

Das item-Objekt, das von Sub-Items zurückgegeben wird, enthält nur die folgenden drei Felder. 
  
 *itemId*  – ID des Elements.
  
 *userId*  – ID des Benutzers, der das Element besitzt.
  
 *type*  – Der Typ des Inhalts. Dieses Feld wird von den Anwendungen festgelegt.
  
> [!NOTE]
>  `Content` und Felder sind nicht in der Antwort enthalten, um die Menge der über `subItems` das Netzwerk übertragenen Daten zu reduzieren.
  

