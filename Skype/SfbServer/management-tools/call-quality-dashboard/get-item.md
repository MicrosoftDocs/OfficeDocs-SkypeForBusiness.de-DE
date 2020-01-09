---
title: Abrufen eines Elements
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang "Element abrufen", der Teil des Element Diensts ist. Der Element Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 208ad3d1852ab58b7fcd0d01eeb440097328f733
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992672"
---
# <a name="get-item"></a>Abrufen eines Elements
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Element abrufen", der Teil des Element Diensts ist. Der Element Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.
  
Der Vorgang "Element abrufen" ist Teil des Element Diensts in der Repository-API für die Anruf Qualitätssteuerung.
  
## <a name="get-item"></a>Abrufen eines Elements

Get Item gibt ein bestimmtes Element im Repository zurück.
  
|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Erhalten  <br/> |https://\<-\>Portal/QoERepositoryService/Repository/Item/{Itemid}  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** -None.
  
 **Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.
  
 **Anforderungstext** – keine.
  
 **Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.
  
 **Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück. Wenn keine angegebene Element-ID gefunden wird, wird der Statuscode 404 (nicht gefunden) zurückgegeben.
  
 **Antwortheader** – keine zusätzlichen Überschriften.
  
 **Antworttext** : Nachfolgend finden Sie eine Beispielantwort Nutzlast in JSON.
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 *ItemID* -ID des Elements.
  
 *UserID* -ID des Benutzers, der Besitzer dieses Elements ist.
  
 *Inhalt* – der anwendungsspezifische Inhalt.
  
 *Type* – der Typ des Inhalts. Dieses Feld wird von den Anwendungen gesetzt.
  
 *subitemids* -die IDs der untergeordneten Elemente (sofern vorhanden). Hierbei handelt es sich um einen Kurzschluss des Vorgangs "untergeordnete Elemente abrufen", um einen Anruf zu speichern. Anwendungen können die gleichen Informationen auch mithilfe von untergeordneten Elementen abrufen.
  

