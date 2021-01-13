---
title: Abrufen des Integrationsprotokolls
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Zusammenfassung: Erfahren Sie mehr über den Vorgang "Integrationsprotokoll abrufen", der Teil der Daten-API für das Anrufqualitätsdashboard ist. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 69827fa9f3fd3f56843a41867b029a071799ba66
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832595"
---
# <a name="get-integration-log"></a>Abrufen des Integrationsprotokolls
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Integrationsprotokoll abrufen", der Teil der Daten-API für das Anrufqualitätsdashboard ist. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.
  
Der Vorgang "Integrationsprotokoll abrufen" ist Teil der Daten-API für das Anrufqualitätsdashboard
  
## <a name="get-integration-log"></a>Abrufen des Integrationsprotokolls

Der Vorgang "Integrationsprotokoll" gibt eine Liste von Protokolleinträgen zurück, die die Aktivitäten in der Verarbeitung von QoE-Cubes beschreiben.
  
Dieser Vorgang ist aus Sicherheitsgründen standardmäßig deaktiviert. Wenn dies deaktiviert ist, wird eine leere Zeichenfolge zurückgegeben. Um diesen Vorgang zu aktivieren, müssen Administratoren die web.config für die Hostwebanwendung der Daten-API konfigurieren.
  

|Methode|**Anforderungs-URI**|**HTTP Version**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** : Keine.
  
 **Anforderungsheader** – Keine zusätzlichen Header.
  
 **Anforderungstext** – Keine.
  
 **Antwort** : Die Antwort enthält einen HTTP-Statuscode und eine Reihe von Antwortheadern.
  
 **Statuscode** : Ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.
  
 **Antwortheader** : Keine zusätzlichen Header.
  
 **Antworttext:** Nachfolgend finden Sie eine Beispielstruktur von Protokolleinträgen.
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


