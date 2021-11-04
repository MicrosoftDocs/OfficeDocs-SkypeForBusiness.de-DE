---
title: Abrufen des Integrationsprotokolls
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Zusammenfassung: Erfahren Sie mehr über den Vorgang "Integrationsprotokoll abrufen", der Teil der Daten-API für das Anrufqualitätsdashboard ist. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 8eca61cf97cc79f34be1f6473f3223b9f2a639d4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759707"
---
# <a name="get-integration-log"></a>Abrufen des Integrationsprotokolls
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Integrationsprotokoll abrufen", der Teil der Daten-API für das Anrufqualitätsdashboard ist. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.
  
Der Vorgang "Integrationsprotokoll abrufen" ist Teil der Daten-API für das Anrufqualitäts-Dashboard.
  
## <a name="get-integration-log"></a>Abrufen des Integrationsprotokolls

Der Vorgang "Integrationsprotokoll abrufen" gibt eine Liste von Protokolleinträgen zurück, die die Aktivitäten in der QoE-Cubeverarbeitung beschreiben.
  
Dieser Vorgang ist aus Sicherheitsgründen standardmäßig deaktiviert. Wenn diese Option deaktiviert ist, wird eine leere Zeichenfolge zurückgegeben. Um diesen Vorgang zu aktivieren, müssen Administratoren die web.config für die Hostwebanwendung der Daten-API konfigurieren.
  

|Methode|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** : Keine.
  
 **Anforderungsheader** – keine zusätzlichen Kopfzeilen.
  
 **Anforderungstext** : Keine.
  
 **Antwort** : Die Antwort enthält einen HTTP-Statuscode und eine Reihe von Antwortheadern.
  
 **Statuscode:** Ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.
  
 **Antwortheader** – keine zusätzlichen Kopfzeilen.
  
 **Antworttext** : Unten sehen Sie eine Beispielstruktur von Protokolleinträgen.
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


