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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Zusammenfassung: Erfahren Sie mehr über den Vorgang "Benutzereinstellung abrufen", der Teil des Benutzer-Einstellungen-Diensts ist. Der Benutzer-Einstellungen-Dienst ist Teil der Repository-API für das Anrufqualitäts-Dashboard. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 1faff1a206ece2ebd0208a32988a679be9739dd7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601460"
---
# <a name="get-user-setting"></a>Abrufen einer Benutzereinstellung
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Benutzereinstellung abrufen", der Teil des Benutzer-Einstellungen-Diensts ist. Der Benutzer-Einstellungen-Dienst ist Teil der Repository-API für das Anrufqualitäts-Dashboard. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.
  
Der Vorgang "Benutzereinstellung abrufen" ist Teil des Diensts "Benutzer Einstellungen" in der Repository-API für das Anrufqualitätsdashboard.
  
## <a name="get-user-setting"></a>Abrufen einer Benutzereinstellung

"Benutzereinstellung abrufen" gibt eine einzelne Benutzereinstellung zurück.
  

|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting/{key}  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** : Keine.
  
 **Anforderungsheader** – keine zusätzlichen Kopfzeilen.
  
 **Anforderungstext** : Keine.
  
 **Antwort** : Die Antwort enthält einen HTTP-Statuscode und eine Reihe von Antwortheadern.
  
 **Statuscode** : Ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.
  
 **Antwortheader** – keine zusätzlichen Kopfzeilen.
  
 **Antworttext** : Unten sehen Sie eine Beispielantwortnutzlast in JSON.
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 *userId*  – ID des Benutzers.
  
 *key*  – Schlüssel der Einstellung.
  
 *value*  – Wert der Einstellung.
  

