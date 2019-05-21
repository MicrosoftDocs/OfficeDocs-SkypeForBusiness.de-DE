---
title: Abrufen von untergeordneten Elementen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang "untergeordnete Elemente abrufen", der Teil des Element Diensts ist. Der Element Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 7be427ed4ea90cd46c6f8cea4ffe3a97be98479b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274660"
---
# <a name="get-sub-items"></a>Abrufen von untergeordneten Elementen
 
**Zusammenfassung:** Informieren Sie sich über den Vorgang "untergeordnete Elemente abrufen", der Teil des Element Diensts ist. Der Element Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.
  
Der Vorgang "untergeordnete Elemente abrufen" ist Teil des Element Diensts in der Repository-API für das Dashboard für die Anrufqualität.
  
## <a name="get-sub-items"></a>Abrufen von untergeordneten Elementen

Abrufen untergeordneter Elemente gibt die untergeordneten Elemente eines bestimmten Elements zurück.
  

|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Erhalten  <br/> |https://\<-\>Portal/QoERepositoryService/Repository/Item/{Itemid}/SubItem  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** -None.
  
 **Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.
  
 **Anforderungstext** – keine.
  
 **Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.
  
 **Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück. Wenn keine angegebene Benutzer-ID gefunden wird, wird der Statuscode 404 (nicht gefunden) zurückgegeben.
  
 **Antwortheader** – keine zusätzlichen Überschriften.
  
 **Antworttext** : Nachfolgend finden Sie eine Beispielantwort Nutzlast in JSON.
  
> [!NOTE]
> Ein Array von Item-Objekt wird zurückgegeben. 
  
```
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

Das vom Unterelement Vorgang zurückgegebene Element Objekt enthält nur die folgenden drei Felder. 
  
 *ItemID* -ID des Elements.
  
 *UserID* -ID des Benutzers, der Besitzer dieses Elements ist.
  
 *Type* – der Typ des Inhalts. Dieses Feld wird von den Anwendungen gesetzt.
  
> [!NOTE]
>  `Content`und `subItems` Felder werden in der Antwort nicht berücksichtigt, um die Datenmenge zu verringern, die über das Netzwerk übertragen wird.
  

