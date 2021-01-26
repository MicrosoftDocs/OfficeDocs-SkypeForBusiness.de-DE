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
description: 'Zusammenfassung: Erfahren Sie mehr über den Vorgang "Element aktualisieren", der Teil des Elementdiensts ist. Der Elementdienst ist Teil der Repository-API für das Anrufqualitätsdashboard. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 78da2fa414b4ba266f9e6aba4feac5ff73150062
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803085"
---
# <a name="update-item"></a>Aktualisieren eines Elements
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Element aktualisieren", der Teil des Elementdiensts ist. Der Elementdienst ist Teil der Repository-API für das Anrufqualitätsdashboard. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.
  
Der Vorgang "Element aktualisieren" ist Teil des Elementdiensts in der Repository-API für das Anrufqualitätsdashboard.
  
## <a name="update-item"></a>Aktualisieren eines Elements

"Element aktualisieren" aktualisiert ein bestimmtes Element im Repository.
  

|**Methode**|**Anforderungs-URI**|**HTTP Version**|
|:-----|:-----|:-----|
|PUT  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** : Keine.
  
 **Anforderungsheader** -Content-Type: application/json.
  
 **Anforderungstext** – JSON.
  
Beispielanforderungsnutzlast:
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *content*  JSON formatierte Daten, die als neuer Inhalt eines vorhandenen Unterelements gespeichert werden sollen. Technisch kann ein Repository jeden Beliebigen Inhalt eines Schemas speichern, aber bei Verwendung für das Anrufqualitätsdashboard sollte es sich entweder um einen Bericht oder eine Abfrage befinden. *type*  Geben Sie immer "application/json" für das Anrufqualitätsdashboard an.
  
 **Antwort** : Die Antwort enthält einen HTTP-Statuscode und eine Reihe von Antwortheadern.
  
 **Statuscode** : Bei einem erfolgreichen Vorgang wird der Statuscode 204 (Kein Inhalt) zurückgegeben. Wenn eine angegebene Element-ID nicht gefunden wird, wird der Statuscode 404 (Nicht gefunden) zurückgegeben.
  
> [!IMPORTANT]
> "Kein Inhalt" ist kein Fehlerstatus. Das bedeutet, dass eine Antwort nichts im Textkörper zurückgegeben hat (im Gegensatz dazu gibt 200 OK Inhalt im Textkörper zurück). Es gibt an, dass das Element erfolgreich aktualisiert wurde. 
  
 **Antwortheader –** Keine.
  
 **Antworttext** – Keine.
  

