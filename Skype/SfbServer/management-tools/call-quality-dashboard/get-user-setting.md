---
title: Abrufen einer Benutzereinstellung
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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Zusammenfassung: Erfahren Sie mehr über den Vorgang "Benutzereinstellung erhalten", der Teil des Benutzereinstellungsdiensts ist. Der Benutzereinstellungsdienst ist Teil der Repository-API für das Anrufqualitätsdashboard. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 82632f5de7ae215d6f34d9f0b39e500fb713a1be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832485"
---
# <a name="get-user-setting"></a>Abrufen einer Benutzereinstellung
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Benutzereinstellung erhalten", der Teil des Benutzereinstellungsdiensts ist. Der Benutzereinstellungsdienst ist Teil der Repository-API für das Anrufqualitätsdashboard. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.
  
Der Vorgang "Benutzereinstellung abrufen" ist Teil des Benutzereinstellungsdiensts in der Repository-API für das Anrufqualitätsdashboard.
  
## <a name="get-user-setting"></a>Abrufen einer Benutzereinstellung

"Benutzereinstellung erhalten" gibt eine einzelne Benutzereinstellung zurück.
  

|**Methode**|**Anforderungs-URI**|**HTTP Version**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting/{key}  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** : Keine.
  
 **Anforderungsheader** – Keine zusätzlichen Header.
  
 **Anforderungstext** – Keine.
  
 **Antwort** : Die Antwort enthält einen HTTP-Statuscode und eine Reihe von Antwortheadern.
  
 **Statuscode** : Ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.
  
 **Antwortheader** – Keine zusätzlichen Header.
  
 **Antworttext** : Unten sehen Sie eine Beispielantwortnutzlast in JSON.
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 *userId*  – ID des Benutzers.
  
 *-TASTE*  : Taste der Einstellung.
  
 *value*  – Wert der Einstellung.
  

