---
title: Abrufen des Integrationsprotokolls
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
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang "Integrationsprotokoll abrufen", der Teil der Daten-API für das Dashboard für die Anrufqualität ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 9caa909e80a0bab5257af16fe77e9d154947a56e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816814"
---
# <a name="get-integration-log"></a>Abrufen des Integrationsprotokolls
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang zum Abrufen von Integrations Protokollen, der Teil der Daten-API für das Dashboard für die Anrufqualität ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.
  
Der Vorgang "Integrationsprotokoll abrufen" ist Teil der Daten-API für das Anruf Qualitäts Dashboard
  
## <a name="get-integration-log"></a>Abrufen des Integrationsprotokolls

Der Vorgang "Integrationsprotokoll abrufen" gibt eine Liste der Protokolleinträge zurück, die die Aktivitäten in der QoE-Cube-Verarbeitung beschreiben.
  
Dieser Vorgang ist aus Sicherheitsgründen standardmäßig deaktiviert. Wenn diese Option deaktiviert ist, wird eine leere Zeichenfolge zurückgegeben. Um diesen Vorgang zu aktivieren, müssen Administratoren die Web. config für die Host-Webanwendung der Daten-API konfigurieren.
  

|Methode|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Erhalten  <br/> |https://\<-\>Portal/QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** -None.
  
 **Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.
  
 **Anforderungstext** – keine.
  
 **Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.
  
 **Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.
  
 **Antwortheader** – keine zusätzlichen Überschriften.
  
 **Antworttext** : Nachfolgend finden Sie eine Beispiel Struktur für Protokolleinträge.
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


