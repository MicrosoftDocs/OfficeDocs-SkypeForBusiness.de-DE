---
title: Abrufen der Benutzereinstellungen
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Zusammenfassung: Erfahren Sie mehr über den Vorgang "Benutzer Einstellungen abrufen", der Teil des Benutzer-Einstellungen-Diensts ist. Der Benutzer-Einstellungen-Dienst ist Teil der Repository-API für das Anrufqualitäts-Dashboard. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.'
---

# <a name="get-user-settings"></a>Abrufen der Benutzereinstellungen
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Benutzer Einstellungen abrufen", der Teil des Benutzer-Einstellungen-Diensts ist. Der Benutzer-Einstellungen-Dienst ist Teil der Repository-API für das Anrufqualitäts-Dashboard. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.
  
Der Vorgang "Benutzer Einstellungen abrufen" ist Teil des Benutzer-Einstellungen-Diensts in der Repository-API für das Anrufqualitätsdashboard.
  
## <a name="get-user-settings"></a>Abrufen der Benutzereinstellungen

Abrufen von Benutzer Einstellungen gibt eine Liste der Einstellungen für einen angegebenen Benutzer zurück.
  

|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|GET  <br/> |\<portal\>https:///QoERepositoryService/repository/user/{userId}/setting  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter**
  
- *effektiv*  – Optional. Dieser Parameter gilt nur, wenn der Standardwert für die spezielle Benutzer-ID verwendet wird. In anderen Fällen wird sie ignoriert. `True` gibt effektive Benutzereinstellungen zurück und `false` gibt nur Benutzereinstellungen zurück (Standardeinstellung).
    
  **Anforderungsheader** – keine zusätzlichen Kopfzeilen.
  
  **Anforderungstext** : Keine.
  
  **Antwort** : Die Antwort enthält einen HTTP-Statuscode und eine Reihe von Antwortheadern.
  
  **Statuscode** : Ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.
  
  **Antwortheader** – keine zusätzlichen Kopfzeilen.
  
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
