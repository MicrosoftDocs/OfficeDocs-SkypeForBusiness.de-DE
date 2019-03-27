---
title: Abrufen einer Benutzereinstellung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Zusammenfassung: Informationen Sie zum Vorgang Benutzereinstellung erhalten möchten, der Teil der User Settings Service ist. Die User Settings Service ist Bestandteil der Repository-API für die Qualitätsdashboard aufrufen. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: 003850ed4e6f1e49fc0e8bafe8dfa7d828cae63f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889000"
---
# <a name="get-user-setting"></a>Abrufen einer Benutzereinstellung
 
**Zusammenfassung:** Informationen Sie zu den Vorgang erhalten Benutzer die Einstellung, der Teil der User Settings Service ist. Die User Settings Service ist Bestandteil der Repository-API für die Qualitätsdashboard aufrufen. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.
  
Der Vorgang erhalten Benutzer die Einstellung ist Bestandteil der Benutzerdienst Einstellungen in der Repository-API für die Qualitätsdashboard aufrufen.
  
## <a name="get-user-setting"></a>Abrufen einer Benutzereinstellung

Rufen Sie die Einstellung für Benutzer gibt eine Einstellung für die einzelnen Benutzer.
  

|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Erhalten  <br/> |https://\<Portal\>/QoERepositoryService/Repository/Benutzer / {Benutzer-ID} /setting/ {Schlüssel}  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** - None.
  
 **Anfordern von Kopfzeilen** - keine zusätzlichen Header.
  
 **Anforderungstextkörper** – None.
  
 **Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.
  
 **Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).
  
 **Antwortheader** - keine zusätzlichen Header.
  
 **Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON.
  
```
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 *UserId* - ID des Benutzers.
  
 *Key* - Schlüssel der Einstellung.
  
 *Wert* - Wert der Einstellung.
  

