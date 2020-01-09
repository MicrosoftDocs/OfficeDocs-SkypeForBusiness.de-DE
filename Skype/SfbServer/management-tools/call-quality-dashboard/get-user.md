---
title: Abrufen eines Benutzers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang zum Abrufen des Benutzers, der Teil des Benutzer Diensts ist. Der Benutzer Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 09dcbbaeaae98ed7b01f3d710cfda23aa5fa986f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992622"
---
# <a name="get-user"></a>Abrufen eines Benutzers
 
**Zusammenfassung:** Informieren Sie sich über den Vorgang "Benutzer abrufen", der Teil des Benutzer Diensts ist. Der Benutzer Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.
  
Der Vorgang zum Abrufen von Benutzern ist Teil des Benutzer Diensts in der Repository-API für die Anruf Qualitätssteuerung.
  
## <a name="get-user"></a>Abrufen eines Benutzers

Der Benutzer erhält einen Benutzerdatensatz aus dem Repository zurück.
  
|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Erhalten  <br/> |https://\<-\>Portal/QoERepositoryService/Repository/User/{UserID}  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** -None.
  
 **Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.
  
 **Anforderungstext** – keine.
  
 **Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.
  
 **Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück. Wenn keine angegebene Benutzer-ID gefunden wird, wird der Statuscode 404 (nicht gefunden) zurückgegeben.
  
 **Antwortheader** – keine zusätzlichen Überschriften.
  
 **Antworttext** : Nachfolgend finden Sie eine Beispielantwort Nutzlast in JSON.
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *UserID* -ID des Benutzers.
  
 *LoginName* – externe Benutzerkennung für reguläre Benutzer. Wenn die Windows-Authentifizierung für die Authentifizierung von Benutzern verwendet wird, kann dies ein FQDN des Benutzers sein.
  
 *defaultItemId* -ID des Standardelements für diesen Benutzer. Das Standardelement ist das oberste Element, das dem Benutzer zugeordnet ist. Alle anderen Elemente, denen dieser Benutzer angehört, können vom Standardelement aus navigiert werden.
  
> [!NOTE]
> Geben Sie `defaultItemId` den Wert zum Abrufen des Element Vorgangs an, um die Details des Standardelements abzurufen.
  

