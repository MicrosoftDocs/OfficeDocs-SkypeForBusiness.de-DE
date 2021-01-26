---
title: Abrufen der Benutzereinstellungen
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
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Zusammenfassung: Erfahren Sie mehr über den Vorgang "Benutzereinstellungen erhalten", der Teil des Benutzereinstellungsdiensts ist. Der Benutzereinstellungsdienst ist Teil der Repository-API für das Anrufqualitätsdashboard. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: e2ebf39ba5a7de5d36a8b1ea0441808b6e71f97b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832475"
---
# <a name="get-user-settings"></a>Abrufen der Benutzereinstellungen
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Benutzereinstellungen erhalten", der Teil des Benutzereinstellungsdiensts ist. Der Benutzereinstellungsdienst ist Teil der Repository-API für das Anrufqualitätsdashboard. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.
  
Der Vorgang "Benutzereinstellungen abrufen" ist Teil des Benutzereinstellungsdiensts in der Repository-API für das Anrufqualitätsdashboard.
  
## <a name="get-user-settings"></a>Abrufen der Benutzereinstellungen

Get User Settings returns a list of settings for a specified user.
  

|**Methode**|**Anforderungs-URI**|**HTTP Version**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter**
  
- *effective*  – Optional. Dieser Parameter gilt nur, wenn die spezielle Standardeinstellung für die Benutzer-ID verwendet wird. In anderen Fällen wird sie ignoriert. `True` gibt effektive Benutzereinstellungen zurück `false` und gibt nur Benutzereinstellungen zurück (Standard).
    
  **Anforderungsheader** – Keine zusätzlichen Header.
  
  **Anforderungstext** – Keine.
  
  **Antwort** : Die Antwort enthält einen HTTP-Statuscode und eine Reihe von Antwortheadern.
  
  **Statuscode** : Ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.
  
  **Antwortheader** – Keine zusätzlichen Header.
  
  **Antworttext** : Unten sehen Sie eine Beispielantwortnutzlast in JSON.
  
```json
[{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
},
{
"userId": 6,
"key": "ShowTimeStamps",
"value": "true"
}]
```
