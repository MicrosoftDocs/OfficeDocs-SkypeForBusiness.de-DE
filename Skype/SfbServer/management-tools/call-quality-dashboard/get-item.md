---
title: Abrufen eines Elements
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Zusammenfassung: Informationen Sie zum Vorgang Element abrufen, der Teil der Element-Dienst ist. Der Element-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: cd72eb583ff0e0813e4197031b119200ecf4b2fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926079"
---
# <a name="get-item"></a>Abrufen eines Elements
 
**Zusammenfassung:** Informationen Sie zum Vorgang Element abrufen, der Teil der Element-Dienst ist. Der Element-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.
  
Der Vorgang Element abrufen ist Teil des Diensts Element in der Repository-API für die Qualitätsdashboard aufrufen.
  
## <a name="get-item"></a>Abrufen eines Elements

Rufen Sie gibt ein bestimmtes Element im Repository.
  
|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Erhalten  <br/> |https://\<Portal\>/QoERepositoryService/Repository/Element / {ItemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** - None.
  
 **Anfordern von Kopfzeilen** - keine zusätzlichen Header.
  
 **Anforderungstextkörper** – None.
  
 **Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.
  
 **Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK). Wenn eine angegebenes Element-ID nicht gefunden wird, wird der Statuscode 404 (nicht gefunden) zurückgegeben.
  
 **Antwortheader** - keine zusätzlichen Header.
  
 **Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON.
  
```
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 *ItemId* - ID des Elements.
  
 *UserId* - ID des Benutzers, der dieses Element gehört.
  
 *Content* - anwendungsspezifischen-Inhalt.
  
 *Typ* – der Typ des Inhalts. Dieses Feld wird durch die Anwendung festgelegt.
  
 *SubItemIds* - die IDs der untergeordneten Elemente, sofern vorhanden. Hierbei handelt es sich um einen Kurzschluss des Vorgangs untergeordnete Elemente abrufen, um einen Anruf zu speichern. Anwendungen können alternativ mit untergeordneten Elemente abrufen-Operation dieselbe Informationen abrufen.
  

