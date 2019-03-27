---
title: Leeren des Caches
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Zusammenfassung: Informationen Sie zu den Cache löschen-Vorgang, der Teil der Daten-API für die Qualitätsdashboard aufrufen, ist. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: c2371a7f99eb37e8e01be919bf6c31b0c9a452cb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889238"
---
# <a name="clear-cache"></a>Leeren des Caches
 
**Zusammenfassung:** Informationen Sie zu den Cache löschen-Vorgang, der Teil der Daten-API für die Qualitätsdashboard aufrufen, ist. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.
  
Der Cache löschen-Vorgang ist Teil der Daten-API für die Qualitätsdashboard aufrufen.
  
## <a name="clear-cache"></a>Leeren des Caches

Löschvorgang Cache löscht den Cache auf dem Server für Abfragen und Daten. Dadurch wird den Cache zurückgesetzt, und wir erhalten neue Daten vom QoE-Cube später für neue Anfragen.
  

|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Bereitstellen  <br/> |https://\<Portal\>/QoEDataService/ClearCache  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** - None.
  
 **Anfordern von Kopfzeilen** - keine zusätzlichen Header.
  
 **Anforderungstextkörper** – None.
  
 **Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.
  
 **Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).
  
 **Antwortheader** - keine zusätzlichen Header.
  
 **Antworttext** – None.
  

