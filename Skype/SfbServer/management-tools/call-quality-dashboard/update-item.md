---
title: Aktualisieren von Elementen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang "Element aktualisieren", der Teil des Element Diensts ist. Der Element Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 460e6b26375bba28887d170c9827864bfc600138
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816674"
---
# <a name="update-item"></a>Aktualisieren von Elementen
 
**Zusammenfassung:** Informieren Sie sich über den Vorgang "Element aktualisieren", der Teil des Element Diensts ist. Der Element Dienst ist Teil der Repository-API für das Anruf Qualitäts Dashboard. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.
  
Der Vorgang "Element aktualisieren" ist Teil des Element Diensts in der Repository-API für das Dashboard für die Anrufqualität.
  
## <a name="update-item"></a>Aktualisieren von Elementen

Element aktualisieren aktualisiert ein bestimmtes Element im Repository.
  

|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Setzen  <br/> |https://\<-\>Portal/QoERepositoryService/Repository/Item/{Itemid}  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** -None.
  
 **Anforderungs Kopfzeilen** – Content-Type: Application/JSON.
  
 **Anforderungstext** – JSON.
  
Beispiel für eine Anforderungsnutzlast:
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *Inhalt*  JSON-formatierte Daten, die als neuer Inhalt eines vorhandenen Unterelements gespeichert werden sollen. Technisch gesehen kann ein Repository beliebigen Inhalt eines beliebigen Schemas speichern, wenn es aber für das Dashboard für die Anrufqualität verwendet wird, sollte es sich entweder um einen Bericht oder eine Abfrage handeln. *geben* Sie  Geben Sie im Dashboard für die Anrufqualität immer "application/json" an.
  
 **Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.
  
 **Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 204 (kein Inhalt) zurück. Wenn keine angegebene Element-ID gefunden wird, wird der Statuscode 404 (nicht gefunden) zurückgegeben.
  
> [!IMPORTANT]
> "Kein Inhalt" ist kein Fehlerstatus. Das bedeutet, dass eine Antwort nichts im Text zurückgegeben hat (im Gegensatz dazu gibt 200 OK den Inhalt im Textkörper zurück). Es gibt an, dass das Element erfolgreich aktualisiert wurde. 
  
 **Antwortheader** – keine.
  
 **Antworttext** – keine.
  

