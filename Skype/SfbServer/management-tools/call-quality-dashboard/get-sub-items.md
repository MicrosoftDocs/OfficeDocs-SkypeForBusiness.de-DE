---
title: Untergeordnete Elemente abrufen
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Zusammenfassung: Informationen Sie zum Vorgang untergeordnete Elemente abrufen, der Teil der Element-Dienst ist. Der Element-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.'
ms.openlocfilehash: f125a10ac9d3f608216ea23d17f614d0bff88af7
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295939"
---
# <a name="get-sub-items"></a>Untergeordnete Elemente abrufen
 
**Zusammenfassung:** Informationen Sie zu den Vorgang untergeordnete Elemente abrufen, der Teil der Element-Dienst ist. Der Element-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.
  
Der untergeordneten Elemente abrufen Vorgang ist Teil des Diensts Element in der Repository-API für die Qualitätsdashboard aufrufen.
  
## <a name="get-sub-items"></a>Untergeordnete Elemente abrufen

Rufen Sie ein bestimmtes Element Unterelemente Unterelemente gibt.
  

|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Erhalten  <br/> |https://\<Portal\>/QoERepositoryService/Repository/Element / {ItemId} / subitem  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** - None.
  
 **Anfordern von Kopfzeilen** - keine zusätzlichen Header.
  
 **Anforderungstextkörper** – None.
  
 **Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.
  
 **Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK). Wenn einen angegebenen Benutzer-ID nicht gefunden wurde, wird der Statuscode 404 (nicht gefunden) zurückgegeben.
  
 **Antwortheader** - keine zusätzlichen Header.
  
 **Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON.
  
> [!NOTE]
> Ein Array von Item-Objekt wird zurückgegeben. 
  
```
[{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1710,
"userId": 0,
"type": "json"
}]
```

Item-Objekts zurückgegebenen Elemente Vorgang enthält nur die folgenden drei Felder. 
  
 *ItemId* - ID des Elements.
  
 *UserId* - ID des Benutzers, der dieses Element gehört.
  
 *Typ* – der Typ des Inhalts. Dieses Feld wird durch die Anwendung festgelegt.
  
> [!NOTE]
>  `Content`und `subItems` Felder sind nicht enthalten, die als Antwort auf die über das Netzwerk übertragen Datenmenge zu reduzieren.
  

