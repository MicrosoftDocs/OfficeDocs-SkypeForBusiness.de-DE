---
title: Abrufen eines Benutzers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Zusammenfassung: Informationen Sie zum Vorgang Benutzer abrufen, der Teil der Benutzerdienst ist. Der Benutzer-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: da07290582c6ccd0ca4f8f331d22e1b51e124a6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930665"
---
# <a name="get-user"></a>Abrufen eines Benutzers
 
**Zusammenfassung:** Informationen Sie zu den Vorgang erhalten Benutzer, der Teil der Benutzerdienst ist. Der Benutzer-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.
  
Der Benutzer abrufen-Vorgang ist Teil des Dienstes Benutzer in der Repository-API für die Qualitätsdashboard aufrufen.
  
## <a name="get-user"></a>Abrufen eines Benutzers

Rufen Sie Benutzer gibt Datensatz eines Benutzers aus dem Repository.
  
|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Erhalten  <br/> |https://\<Portal\>/QoERepositoryService/Repository/Benutzer / {Benutzer-ID}  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** - None.
  
 **Anfordern von Kopfzeilen** - keine zusätzlichen Header.
  
 **Anforderungstextkörper** – None.
  
 **Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.
  
 **Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK). Wenn einen angegebenen Benutzer-ID nicht gefunden wurde, wird der Statuscode 404 (nicht gefunden) zurückgegeben.
  
 **Antwortheader** - keine zusätzlichen Header.
  
 **Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON.
  
```
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *UserId* - ID des Benutzers.
  
 *LoginName* - externe Benutzer-ID für normale Benutzer. Wenn Windows-Authentifizierung zum Authentifizieren von Benutzern verwendet wird, kann dies eine FQDN des Benutzers sein.
  
 *DefaultItemId* - ID des Standard-Element für diesen Benutzer. Der Standardwert Element ist das oberste Element, das dem Benutzer zugeordnet ist. Alle anderen Elemente, die dieser Benutzer besitzt, können aus der Standard-Element navigiert werden.
  
> [!NOTE]
> Geben Sie die `defaultItemId` Wert zum Element abrufen Operation, die Details des Standard-Element abgerufen.
  

