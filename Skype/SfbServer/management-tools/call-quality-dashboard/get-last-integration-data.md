---
title: Abrufen der letzten Integrationsdaten
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
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: 'Zusammenfassung: Erfahren Sie mehr über den Vorgang "Letzte Integrationsdaten abrufen", der Teil der Daten-API für das Anrufqualitätsdashboard ist. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: c40041e41e04d2bdc62a9eb9fa1eb699697a5b3d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832515"
---
# <a name="get-last-integration-data"></a>Abrufen der letzten Integrationsdaten
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "Letzte Integrationsdaten abrufen", der Teil der Daten-API für das Anrufqualitätsdashboard ist. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.
  
Der Vorgang "Letzte Integrationsdaten abrufen" ist Teil der Daten-API für das Anrufqualitätsdashboard.
  
## <a name="get-last-integration-data"></a>Abrufen der letzten Integrationsdaten

Get Last Integration Data operation returns the list of last 5 success/failure of archiving and cube processing.
  
Dieses Feature ist standardmäßig deaktiviert und muss durch Konfigurieren der Daten-API aktiviert werden.
  

|**Methode**|**Anforderungs-URI**|**HTTP Version**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoEDataService/IntegrationLog/Status  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** : Keine.
  
 **Anforderungsheader** – Keine zusätzlichen Header.
  
 **Anforderungstext** – Keine.
  
 **Antwort** : Die Antwort enthält einen HTTP-Statuscode und eine Reihe von Antwortheadern.
  
 **Statuscode** : Ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.
  
 **Antwortheader** – Keine zusätzlichen Header.
  
 **Antworttext:** Nachfolgend finden Sie einen Beispielprotokollstatus.
  
```json
{
"LastSuccessIntegrations": ["01/18/2015 10:30:13",
"01/18/2015 10:28:29",
"01/17/2015 15:15:17",
"01/17/2015 15:00:17",
"01/17/2015 14:45:13"],
"LastSuccessCubeProcessings": ["01/17/2015 15:16:40",
"01/17/2015 15:01:41",
"01/17/2015 14:47:19",
"01/17/2015 14:31:40",
"01/17/2015 14:17:01"],
"LastFailedIntegrations":  ,
"LastFailedCubeProcessings": ["01/18/2015 10:30:58",
"01/18/2015 10:29:28",
"01/17/2015 10:02:20",
"01/15/2015 20:01:56",
"01/15/2015 19:45:50"],
"LastDataIntegrationStart": null,
"LastCubeProcessingStart": "01/18/2015 10:30:16"
}
```
