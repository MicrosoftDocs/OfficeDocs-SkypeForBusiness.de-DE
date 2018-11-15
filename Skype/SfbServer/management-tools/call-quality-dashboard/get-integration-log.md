---
title: Integration Protokoll abrufen
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Zusammenfassung: Informationen Sie zum Vorgang Integration Protokoll abrufen, der Teil der Daten-API für die Qualitätsdashboard aufrufen, ist. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: 6408d0a773ee00854f82c4430e4402e79db23fa6
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531088"
---
# <a name="get-integration-log"></a>Integration Protokoll abrufen
 
**Zusammenfassung:** Informationen Sie zu den Vorgang Integration Protokoll erhalten möchten, der Teil der Daten-API für die Qualitätsdashboard aufrufen, ist. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.
  
Die erste Integration Log-Operation ist Teil der Daten-API für die Qualitätsdashboard aufrufen
  
## <a name="get-integration-log"></a>Integration Protokoll abrufen

Möchten Sie Integration Protokoll Operation gibt eine Liste der Protokolleinträge, beschreibt die Aktivitäten in QoE-Cube zurück, Verarbeitung erhalten.
  
Dieser Vorgang ist aus Sicherheitsgründen standardmäßig deaktiviert. Wenn deaktiviert, wird eine leere Zeichenfolge zurückgegeben. Um diesen Vorgang zu aktivieren, müssen die Administratoren die Web.config-Datei für Daten-API-Host-Web-Anwendung konfigurieren.
  

|Methode|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Erhalten  <br/> |https://\<Portal\>/QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** - None.
  
 **Anfordern von Kopfzeilen** - keine zusätzlichen Header.
  
 **Anforderungstextkörper** – None.
  
 **Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.
  
 **Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).
  
 **Antwortheader** - keine zusätzlichen Header.
  
 **Antworttext** – Es folgt eine Beispielstruktur der Protokolleinträge.
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


