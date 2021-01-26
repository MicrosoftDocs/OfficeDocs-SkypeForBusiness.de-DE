---
title: Abrufen von Benutzern
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
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Zusammenfassung: Erfahren Sie mehr über den Vorgang "Benutzer erhalten", der Teil des Benutzerdiensts ist. Der Benutzerdienst ist Teil der Repository-API für das Anrufqualitätsdashboard. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: a830663fc97d8fda727d1ebb008d97407796cc7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832425"
---
# <a name="get-users"></a>Abrufen von Benutzern
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Benutzer erhalten", der Teil des Benutzerdiensts ist. Der Benutzerdienst ist Teil der Repository-API für das Anrufqualitätsdashboard. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.
  
Der Vorgang "Benutzer abrufen" ist Teil des Benutzerdiensts in der Repository-API für das Anrufqualitätsdashboard.
  
## <a name="get-users"></a>Abrufen von Benutzern

"Get Users" gibt eine Liste der Benutzer im Repository zurück.
  
|**Methode**|**Anforderungs-URI**|**HTTP Version**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** : Keine.
  
 **Anforderungsheader** – Keine zusätzlichen Header.
  
 **Anforderungstext** – Keine.
  
 **Antwort** : Die Antwort enthält einen HTTP-Statuscode und eine Reihe von Antwortheadern.
  
 **Statuscode** : Ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.
  
 **Antwortheader** – Keine zusätzlichen Header.
  
 **Antworttext** : Unten sehen Sie eine Beispielantwortnutzlast in JSON.
  
> [!NOTE]
> Es wird ein Array von Benutzerobjekten zurückgegeben. Details zum Benutzerobjekt finden Sie unter "Benutzer erhalten". 
  
```json
[{
"userId": 0,
"loginName": "system",
"defaultItemId": 1652
},
{
"userId": 1,
"loginName": "SAMPLEDOMAIN\\testuser1",
"defaultItemId": 1652
},
{
"userId": 2,
"loginName": "SAMPLEDOMAIN\\testuser2",
"defaultItemId": 1774
}]
```


