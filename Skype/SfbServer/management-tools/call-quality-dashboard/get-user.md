---
title: Abrufen eines Benutzers
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
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Zusammenfassung: Erfahren Sie mehr über den Vorgang "Benutzer abrufen", der Teil des Benutzerdiensts ist. Der Benutzerdienst ist Teil der Repository-API für das Anrufqualitäts-Dashboard. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: bb99ec52cb270bdef51eac65070c1f5204bb03b93c81dd46d31f86a2ffc3b836
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54311043"
---
# <a name="get-user"></a>Abrufen eines Benutzers
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Benutzer abrufen", der Teil des Benutzerdiensts ist. Der Benutzerdienst ist Teil der Repository-API für das Anrufqualitäts-Dashboard. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.
  
Der Vorgang "Benutzer abrufen" ist Teil des Benutzerdiensts in der Repository-API für das Anrufqualitäts-Dashboard.
  
## <a name="get-user"></a>Abrufen eines Benutzers

"Benutzer abrufen" gibt einen Benutzerdatensatz aus dem Repository zurück.
  
|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** : Keine.
  
 **Anforderungsheader** – keine zusätzlichen Kopfzeilen.
  
 **Anforderungstext** : Keine.
  
 **Antwort** : Die Antwort enthält einen HTTP-Statuscode und eine Reihe von Antwortheadern.
  
 **Statuscode** : Ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück. Wenn eine angegebene Benutzer-ID nicht gefunden wird, wird der Statuscode 404 (Nicht gefunden) zurückgegeben.
  
 **Antwortheader** – keine zusätzlichen Kopfzeilen.
  
 **Antworttext** : Unten sehen Sie eine Beispielantwortnutzlast in JSON.
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *userId*  – ID des Benutzers.
  
 *loginName*  – Externe Benutzeridentifikation für reguläre Benutzer. Wenn Windows Authentifizierung für die Authentifizierung von Benutzern verwendet wird, kann dies ein FQDN des Benutzers sein.
  
 *defaultItemId*  – ID des Standardelements für diesen Benutzer. Das Standardelement ist das oberste Element, das dem Benutzer zugeordnet ist. Alle anderen Elemente, die dieser Benutzer besitzt, können über das Standardelement navigiert werden.
  
> [!NOTE]
> Geben Sie den  `defaultItemId` Wert für den Vorgang "Element abrufen" an, um die Details des Standardelements abzurufen.
  

