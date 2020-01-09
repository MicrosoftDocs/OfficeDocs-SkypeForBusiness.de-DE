---
title: Abrufen von Benutzern
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang zum Abrufen von Benutzern, der Teil des Benutzer Diensts ist. Der Benutzer Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 6cf2248035c780c2efce6b1f4539a39cd2a5829a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992612"
---
# <a name="get-users"></a>Abrufen von Benutzern
 
**Zusammenfassung:** Informieren Sie sich über den Vorgang zum Abrufen von Benutzern, der Teil des Benutzer Diensts ist. Der Benutzer Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.
  
Der Vorgang zum Abrufen von Benutzern ist Teil des Benutzer Diensts in der Repository-API für die Anruf Qualitätssteuerung.
  
## <a name="get-users"></a>Abrufen von Benutzern

Benutzer abrufen gibt eine Liste der Benutzer im Repository zurück.
  
|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Erhalten  <br/> |https://\<-\>Portal/QoERepositoryService/Repository/User  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** -None.
  
 **Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.
  
 **Anforderungstext** – keine.
  
 **Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.
  
 **Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.
  
 **Antwortheader** – keine zusätzlichen Überschriften.
  
 **Antworttext** : Nachfolgend finden Sie eine Beispielantwort Nutzlast in JSON.
  
> [!NOTE]
> Ein Array von Benutzerobjekten wird zurückgegeben. Details zum Benutzerobjekt finden Sie unter Abrufen von Benutzern. 
  
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


