---
title: Abrufen von Integrationsdaten der letzten
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: 'Zusammenfassung: Informationen Sie zum Vorgang letzten Integrationsdaten abrufen, der Teil der Daten-API für die Qualitätsdashboard aufrufen, ist. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: b2e759766987b6ee52795845ee55546920181807
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531787"
---
# <a name="get-last-integration-data"></a>Abrufen von Integrationsdaten der letzten
 
**Zusammenfassung:** Informationen Sie zu den letzten Integrationsdaten abrufen-Vorgang, der Teil der Daten-API für die Qualitätsdashboard aufrufen, ist. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.
  
Der letzte Integrationsdaten abrufen-Vorgang ist Teil der Daten-API für die Qualitätsdashboard aufrufen.
  
## <a name="get-last-integration-data"></a>Abrufen von Integrationsdaten der letzten

Rufen Sie zuletzt Integrationsdaten Vorgang gibt die Liste der letzten 5 Erfolg/Fehlschlag der Archivierung und Verarbeiten des Cubes.
  
Dieses Feature ist standardmäßig deaktiviert und muss aktiviert werden, um die Daten-API konfigurieren.
  

|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Erhalten  <br/> |https://\<Portal\>/QoEDataService/IntegrationLog/Status  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter** - None.
  
 **Anfordern von Kopfzeilen** - keine zusätzlichen Header.
  
 **Anforderungstextkörper** – None.
  
 **Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.
  
 **Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).
  
 **Antwortheader** - keine zusätzlichen Header.
  
 **Antworttext** - ist im folgenden Beispiel Protokollierungsstatus.
  
```
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