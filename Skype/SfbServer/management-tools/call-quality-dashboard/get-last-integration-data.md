---
title: Abrufen der letzten Integrationsdaten
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
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: 'Zusammenfassung: erfahren Sie mehr über den Vorgang "letzte Integrationsdaten abrufen", der Teil der Daten-API für die Anruf Qualitätssteuerung ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: a4b455a543dd77f0edce223f43d64fe5c03e4bcb
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888794"
---
# <a name="get-last-integration-data"></a>Abrufen der letzten Integrationsdaten
 
**Zusammenfassung:** Erfahren Sie mehr über den Vorgang "letzte Integrationsdaten abrufen", der Teil der Daten-API für die Anruf Qualitätssteuerung ist. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.
  
Der Vorgang zum Abrufen der letzten Integrationsdaten ist Teil der Daten-API für das Dashboard für die Anrufqualität.
  
## <a name="get-last-integration-data"></a>Abrufen der letzten Integrationsdaten

Abrufen des letzten Integrationsdaten Vorgangs gibt die Liste der letzten 5 Erfolge/Fehler bei der Archivierung und der Cube-Verarbeitung zurück.
  
Dieses Feature ist standardmäßig deaktiviert und muss durch Konfigurieren der Daten-API aktiviert werden.
  

|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Erhalten  <br/> |https://\<-\>Portal/QoEDataService/IntegrationLog/Status  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** -None.
  
 **Anforderungs Kopfzeilen** – keine zusätzlichen Überschriften.
  
 **Anforderungstext** – keine.
  
 **Antwort** – die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheadern.
  
 **Statuscode** – ein erfolgreicher Vorgang gibt den Statuscode 200 (OK) zurück.
  
 **Antwortheader** – keine zusätzlichen Überschriften.
  
 **Antworttext** : unten befindet sich ein Beispiel für einen Protokollstatus.
  
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
