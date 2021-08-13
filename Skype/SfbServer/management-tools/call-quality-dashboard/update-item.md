---
title: Aktualisieren eines Elements
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
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Zusammenfassung: Erfahren Sie mehr über den Vorgang "Element aktualisieren", der Teil des Elementdiensts ist. Der Elementdienst ist Teil der Repository-API für das Anrufqualitäts-Dashboard. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: ad615e5b6c6187a51293e86bcf3b1e2ee20c820f8c8c7a48b013d95befd03d87
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340801"
---
# <a name="update-item"></a>Aktualisieren eines Elements
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Element aktualisieren", der Teil des Elementdiensts ist. Der Elementdienst ist Teil der Repository-API für das Anrufqualitäts-Dashboard. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.
  
Der Vorgang "Element aktualisieren" ist Teil des Elementdiensts in der Repository-API für das Anrufqualitätsdashboard.
  
## <a name="update-item"></a>Aktualisieren eines Elements

Aktualisieren des Elements aktualisiert ein bestimmtes Element im Repository.
  

|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|PUT  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** : Keine.
  
 **Anforderungsheader** -Content-Type: application/json.
  
 **Anforderungstext** – JSON.
  
Beispiel-Anforderungsnutzlast:
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *Inhalt*  JSON-formatierte Daten, die als neuer Inhalt eines vorhandenen Unterelements gespeichert werden sollen. Technisch gesehen kann ein Repository jeden Inhalt eines beliebigen Schemas speichern, aber wenn es für das Anrufqualitätsdashboard verwendet wird, sollte es sich entweder um einen Bericht oder eine Abfrage handeln. *Typ*  Geben Sie immer "application/json" für das Anrufqualitäts-Dashboard an.
  
 **Antwort** : Die Antwort enthält einen HTTP-Statuscode und eine Reihe von Antwortheadern.
  
 **Statuscode:** Ein erfolgreicher Vorgang gibt den Statuscode 204 (kein Inhalt) zurück. Wenn eine angegebene Element-ID nicht gefunden wird, wird der Statuscode 404 (Nicht gefunden) zurückgegeben.
  
> [!IMPORTANT]
> "Kein Inhalt" ist kein Fehlerstatus. Dies bedeutet, dass eine Antwort nichts im Textkörper zurückgegeben hat (im Gegensatz dazu gibt 200 OK Inhalte im Textkörper zurück). Es gibt an, dass das Element erfolgreich aktualisiert wurde. 
  
 **Antwortheader** : Keine.
  
 **Antworttext** : Keine.
  

