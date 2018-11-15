---
title: Cache löschen
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
ms.openlocfilehash: 745fdff57843c42ebf55c1caee011d4b7f4ed250
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531288"
---
# <a name="clear-cache"></a>Cache löschen
 
**Zusammenfassung:** Informationen Sie zu den Cache löschen-Vorgang, der Teil der Daten-API für die Qualitätsdashboard aufrufen, ist. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.
  
Der Cache löschen-Vorgang ist Teil der Daten-API für die Qualitätsdashboard aufrufen.
  
## <a name="clear-cache"></a>Cache löschen

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
  

