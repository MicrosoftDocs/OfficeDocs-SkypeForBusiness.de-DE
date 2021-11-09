---
title: Leeren des Caches
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Zusammenfassung: Erfahren Sie mehr über den Vorgang "Cache löschen", der Teil der Daten-API für das Anrufqualitätsdashboard ist. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: de956a3541416100cf7877b46340f2eccb38b3ea
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843818"
---
# <a name="clear-cache"></a>Leeren des Caches
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Cache löschen", der Teil der Daten-API für das Anrufqualitäts-Dashboard ist. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.
  
Der Vorgang "Cache löschen" ist Teil der Daten-API für das Anrufqualitäts-Dashboard.
  
## <a name="clear-cache"></a>Leeren des Caches

Der Vorgang "Cache löschen" löscht den Cache auf dem Server für Abfragen und Daten. Dadurch wird der Cache zurückgesetzt, und wir erhalten anschließend neue Daten aus QoE Cube für neue Anforderungen.
  

|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|POST  <br/> |https:// \<portal\> /QoEDataService/ClearCache  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** : Keine.
  
 **Anforderungsheader** – keine zusätzlichen Kopfzeilen.
  
 **Anforderungstext** : Keine.
  
 **Antwort** : Die Antwort enthält einen HTTP-Statuscode und eine Reihe von Antwortheadern.
  
 **Statuscode** : Ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.
  
 **Antwortheader** – keine zusätzlichen Kopfzeilen.
  
 **Antworttext** : Keine.
  

