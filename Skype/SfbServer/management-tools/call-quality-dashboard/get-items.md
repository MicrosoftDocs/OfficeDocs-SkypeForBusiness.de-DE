---
title: Abrufen von Elementen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang zum Abrufen von Elementen, der Teil des Element Diensts ist. Der Element Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: be93e16750c1a977a6bc3cfc9651e78a043ef563
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992662"
---
# <a name="get-items"></a>Abrufen von Elementen
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Elemente abrufen", der Teil des Element Diensts ist. Der Element Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.
  
Der Vorgang zum Abrufen von Elementen ist Teil des Element Diensts in der Repository-API für die Anruf Qualitätssteuerung.
  
## <a name="get-items"></a>Abrufen von Elementen

Elemente abrufen gibt alle Elemente im Repository zurück.
  
|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Erhalten  <br/> |https://\<-\>Portal/QoERepositoryService/Repository/Item  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** -None.
  
 **Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.
  
 **Anforderungstext** – keine.
  
 **Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.
  
 **Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.
  
 **Antwortheader** – keine zusätzlichen Überschriften.
  
 **Antworttext** : Nachfolgend finden Sie eine Beispielantwort Nutzlast in JSON.
  
> [!NOTE]
> Ein Array von Item-Objekten wird zurückgegeben. Details zu Item-Objekten finden Sie unter Abrufen von Elementen. 
  
```json
[{
"itemId": 1652,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1654,
"userId": 0,
"type": "application/json"
}]
```
