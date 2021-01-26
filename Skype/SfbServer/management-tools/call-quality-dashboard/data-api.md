---
title: Daten-API für das Anrufqualitätsdashboard (CQD) in Skype for Business Server
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
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Zusammenfassung: Erfahren Sie mehr über die Daten-API für das Anrufqualitätsdashboard. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 367aa1bf1103863fff37fbcd4f8d9fa379de7c1d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832695"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>Daten-API für das Anrufqualitätsdashboard (CQD) in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Daten-API für das Anrufqualitätsdashboard. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.
  
Die Daten-API bietet programmgesteuerten Zugriff für das Anrufqualitätsdashboard für Skype for Business Server.
  
## <a name="data-api-for-call-quality-dashboard"></a>Daten-API für das Anrufqualitätsdashboard

Die Daten-API bietet eine Abfrageschnittstelle für den QoE-Cube. Die Daten-API ist eine REST-API für die Arbeit mit mehrdimensionalen Datenbanken, die aggregierte QoE-Metriken basierend auf angegebenen Dimensionen und Filtern bietet.
  
Die REST-Vorgänge sind in der folgenden Tabelle enthalten.
  

|**Vorgang**|**Beschreibung**|
|:-----|:-----|
|[Abrufen von Cubes](get-cube.md) <br/> |Hier erhalten Sie eine Liste der verfügbaren Dimensionen und Messungen.  <br/> |
|[Abrufen von Dimensionselementen](get-dimension-members.md) <br/> |Der Vorgang "Dimensionsm elemente" gibt die Liste der Elemente einer bestimmten Dimension zurück. Es bietet auch die Möglichkeit, die Mitgliederliste zu filtern und eine Teilmenge zu erhalten, um die Übertragungskosten zu reduzieren.  <br/> |
|[Ausführen von Abfragen](run-query.md) <br/> |Der Abfragevorgang ausführen ermöglicht das Ausführen einer Abfrage für den Cube basierend auf angegebenen Dimensionen, Messungen und Filtern sowie das Zurückgeben der Daten.  <br/> |
|[Leeren des Caches](clear-cache.md) <br/> |Beim Löschen des Cachevorgangs wird der Cache auf dem Server für Abfragen und Daten gelöscht. Dadurch wird der Cache zurückgesetzt, und wir erhalten im Anschluss für neue Anforderungen neue Daten aus dem QoE-Cube.  <br/> |
|[Abrufen des Integrationsprotokolls](get-integration-log.md) <br/> |Der Vorgang "Integrationsprotokoll" gibt eine Liste von Protokolleinträgen zurück, die die Aktivitäten in der Verarbeitung von QoE-Cubes beschreiben.  <br/> |
|[Abrufen der letzten Integrationsdaten](get-last-integration-data.md) <br/> |Die letzten Integrationsdaten aus dem Cube erhalten.  <br/> |
   
 **Cross-Origin Resource Sharing (CORS)-Unterstützung für die Daten-API**
  
Die Daten-API unterstützt cross-Origin Resource Sharing (CORS). CORS ist ein HTTP-Feature, mit dem eine Webanwendung, die unter einer Domäne ausgeführt wird, auf Ressourcen in einer anderen Domäne zugreifen kann. Webbrowser implementieren eine Sicherheitseinschränkung, die als ["Richtlinie](https://www.w3.org/Security/wiki/Same_Origin_Policy) des gleichen Ursprungs" bezeichnet wird und verhindert, dass eine Webseite APIs in einer anderen Domäne aufruft. CORS bietet eine sichere Möglichkeit, einer Domäne (der Ursprungsdomäne) das Aufrufen von APIs in einer anderen Domäne zu ermöglichen. Details zu [CORS finden](https://www.w3.org/TR/cors/) Sie in der CORS-Spezifikation.
  
 **Aktivieren von CORS für die Daten-API**
  
 Es folgt ein Auszug aus der Daten-API-web.config mit zwei Domänen, die in den CorsTrustedOrigin-Anwendungseinstellungen aufgelistet sind. Alle Anforderungen der von diesen Servern geladenen Skripts werden von der Daten-API als vertrauenswürdig eingestuft.
  
Denken Sie daran, das genaue Protokoll, den Hostnamen und den Port (falls dies der Fall ist) zu verwenden. Setzen Sie keinen Schrägstrich (/) am Ende. Mehrere Einträge können durch Kommas getrennt angegeben werden.
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


