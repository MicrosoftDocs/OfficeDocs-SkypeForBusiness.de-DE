---
title: Abrufen der Benutzereinstellungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang zum Abrufen von Benutzereinstellungen, der Teil des Benutzer Einstellungs Diensts ist. Der Benutzer Einstellungsdienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 42934496b8b65132a67d4012d81d7b8997859726
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992632"
---
# <a name="get-user-settings"></a>Abrufen der Benutzereinstellungen
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang zum Abrufen von Benutzereinstellungen, der Teil des Benutzer Einstellungs Diensts ist. Der Benutzer Einstellungsdienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.
  
Der Vorgang zum Abrufen von Benutzereinstellungen ist Teil des Benutzer Einstellungs Diensts in der Repository-API für die Anruf Qualitätssteuerung.
  
## <a name="get-user-settings"></a>Abrufen der Benutzereinstellungen

Abrufen von Benutzereinstellungen gibt eine Liste der Einstellungen für einen bestimmten Benutzer zurück.
  

|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Erhalten  <br/> |https://\<-\>Portal/QoERepositoryService/Repository/User/{UserID}/Setting  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter**
  
- *effektiv* – optional. Dieser Parameter gilt nur, wenn die spezielle Benutzer-ID Standard verwendet wird. In anderen Fällen wird Sie ignoriert. `True`gibt effektive Benutzereinstellungen zurück `false` und gibt nur Benutzereinstellungen zurück (Standard).
    
  **Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.
  
  **Anforderungstext** – keine.
  
  **Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.
  
  **Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.
  
  **Antwortheader** – keine zusätzlichen Überschriften.
  
  **Antworttext** : Nachfolgend finden Sie eine Beispielantwort Nutzlast in JSON.
  
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
