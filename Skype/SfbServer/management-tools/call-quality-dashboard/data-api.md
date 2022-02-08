---
title: Daten-API für das Anrufqualitäts-Dashboard (Call Quality Dashboard, CQD) in Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Zusammenfassung: Erfahren Sie mehr über die Daten-API für das Anrufqualitäts-Dashboard. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 4ed1c4716e88fcfe47200b97f2f9cd329e8c56a1
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392467"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>Daten-API für das Anrufqualitäts-Dashboard (Call Quality Dashboard, CQD) in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Daten-API für das Anrufqualitäts-Dashboard. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.
  
Die Daten-API bietet programmgesteuerten Zugriff für das Anrufqualitäts-Dashboard für Skype for Business Server.
  
## <a name="data-api-for-call-quality-dashboard"></a>Daten-API für das Anrufqualitäts-Dashboard

Die Daten-API bietet eine Abfrageschnittstelle zum QoE-Cube. Die Daten-API ist eine REST-API zum Arbeiten mit mehrdimensionalen Datenbanken, die aggregierte QoE-Metriken basierend auf angegebenen Dimensionen und Filtern bereitstellt.
  
Die REST-Vorgänge sind in der folgenden Tabelle enthalten.
  

|**Vorgang**|**Beschreibung**|
|:-----|:-----|
|[Abrufen von Cubes](get-cube.md) <br/> |Ruft die Liste der verfügbaren Dimensionen und Maße ab.  <br/> |
|[Abrufen von Dimensionselementen](get-dimension-members.md) <br/> |Der Vorgang "Dimension-Elemente abrufen" gibt die Liste der Elemente einer bestimmten Dimension zurück. Es bietet auch die Möglichkeit, die Mitgliederliste zu filtern und eine Teilmenge abzurufen, um die Übertragungskosten zu reduzieren.  <br/> |
|[Ausführen von Abfragen](run-query.md) <br/> |Der Vorgang "Abfrage ausführen" bietet die Möglichkeit, eine Abfrage auf dem Cube basierend auf angegebenen Dimensionen, Maßen und Filtern auszuführen und die Daten zurückzugeben.  <br/> |
|[Leeren des Caches](clear-cache.md) <br/> |Der Vorgang "Cache löschen" löscht den Cache auf dem Server für Abfragen und Daten. Dadurch wird der Cache zurückgesetzt, und wir erhalten anschließend neue Daten aus QoE Cube für neue Anforderungen.  <br/> |
|[Abrufen des Integrationsprotokolls](get-integration-log.md) <br/> |Der Vorgang "Integrationsprotokoll abrufen" gibt eine Liste von Protokolleinträgen zurück, die die Aktivitäten in der QoE-Cubeverarbeitung beschreiben.  <br/> |
|[Abrufen der letzten Integrationsdaten](get-last-integration-data.md) <br/> |Rufen Sie die letzten Integrationsdaten aus dem Cube ab.  <br/> |
   
 **Cross-Origin Resource Sharing (CORS)-Unterstützung für die Daten-API**
  
Die Daten-API unterstützt cross-origin Resource Sharing (CORS). CORS ist ein HTTP-Feature, mit dem eine Webanwendung, die unter einer Domäne ausgeführt wird, auf Ressourcen in einer anderen Domäne zugreifen kann. Webbrowser implementieren eine Sicherheitseinschränkung, die als [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) Same-Origin Policy same-origin policy bezeichnet wird und verhindert, dass eine Webseite APIs in einer anderen Domäne aufruft. CORS bietet eine sichere Möglichkeit, einer Domäne (der Ursprungsdomäne) das Aufrufen von APIs in einer anderen Domäne zu ermöglichen. Details zu CORS finden Sie in der [CORS-Spezifikation](https://www.w3.org/TR/cors/) .
  
 **Aktivieren von CORS für die Daten-API**
  
 Es folgt ein Auszug aus der Daten-API-web.config mit zwei Domänen, die in den CorsTrustedOrigin-Anwendungseinstellungen aufgelistet sind. Alle Anforderungen, die von den von diesen Servern geladenen Skripts gestellt werden, werden von der Daten-API als vertrauenswürdig eingestuft.
  
Denken Sie daran, das genaue Protokoll, den Hostnamen und den Port (falls vorhanden) einzuschließen. Setzen Sie keinen Schrägstrich (/) am Ende. Mehrere Einträge können durch Kommas getrennt angegeben werden.
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


