---
title: Update-Element
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/8/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Zusammenfassung: Informationen Sie zum Vorgang Update-Element, der Teil der Element-Dienst ist. Der Element-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.'
ms.openlocfilehash: 04a0ebf29537bbc2e62e6d5b35008fe9e329ab4f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="update-item"></a>Update-Element
 
**Zusammenfassung:** Informationen Sie zu den Vorgang Update-Element, der Teil der Element-Dienst ist. Der Element-Dienst ist Teil der Repository-API für die Qualitätsdashboard aufrufen. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.
  
Der Vorgang der Update-Element ist Teil des Diensts Element in der Repository-API für die Qualitätsdashboard aufrufen.
  
## <a name="update-item"></a>Update-Element

Update-Element aktualisiert ein bestimmtes Element im Repository.
  

|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|PUT  <br/> |https://\<Portal\>/QoERepositoryService/Repository/Element / {ItemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** - None.
  
 **Anfordern von Kopfzeilen** -Content-Type: Application/Json.
  
 **Anforderungstextkörper** - JSON.
  
Beispiel-Anforderungsnutzlast:
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *Inhalt*  JSON formatierte Daten als neuer Inhalt eines vorhandenen untergeordneten Elements gespeichert werden. Technisch gesehen ein Repository kann alle Inhalte von einem beliebigen Schema gespeichert, aber beim für aufrufen Qualitätsdashboard verwendet wird, sollte es sein, einem Bericht oder einer Abfrage. *Typ*  Geben Sie immer "Application/Json" für die Qualitätsdashboard aufrufen.
  
 **Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.
  
 **Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 204 (kein Inhalt). Wenn eine angegebenes Element-ID nicht gefunden wird, wird der Statuscode 404 (nicht gefunden) zurückgegeben.
  
> [!IMPORTANT]
> "Keine Content" ist nicht Fehlerstatus. Dies bedeutet, dass eine Antwort Suchzeichenfolge nicht im Textkörper (im Gegensatz dazu 200 OK gibt Inhalt im Textkörper) zurückgegeben hat. Es gibt an, dass das Element erfolgreich aktualisiert wurde. 
  
 **Antwortheader** - None.
  
 **Antworttext** – None.
  

