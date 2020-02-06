---
title: Daten-API für Anruf Qualitäts Dashboard (CQD) in Skype for Business Server
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
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Zusammenfassung: erfahren Sie mehr über die Daten-API für die Anrufqualität. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: e302c04dee298f9e5d2f33c908b5421ecff4de9a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816864"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>Daten-API für Anruf Qualitäts Dashboard (CQD) in Skype for Business Server
 
**Zusammenfassung:** Informieren Sie sich über die Daten-API für die Anrufqualität. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.
  
Die Daten-API bietet programmgesteuerten Zugriff für das Anruf Qualitäts Dashboard für Skype for Business Server.
  
## <a name="data-api-for-call-quality-dashboard"></a>Daten-API für Anruf Qualitäts Dashboard

Die Daten-API bietet eine Abfrageschnittstelle für den QoE-Cube. Die Daten-API ist eine Ruhe-API für die Arbeit mit mehrdimensionaler Datenbank, die aggregierte QoE-Metriken basierend auf angegebenen Dimensionen und Filtern bereitstellt.
  
Die übrigen Vorgänge sind in der folgenden Tabelle enthalten.
  

|**Vorgang**|**Beschreibung**|
|:-----|:-----|
|[Abrufen von Cubes](get-cube.md) <br/> |Rufen Sie die Liste der verfügbaren Dimensionen und Maße ab.  <br/> |
|[Abrufen von Dimensionselementen](get-dimension-members.md) <br/> |Der Vorgang zum Abrufen von Dimensionselementen gibt die Liste der Elemente einer bestimmten Dimension zurück. Darüber hinaus können Sie die Mitgliederliste Filtern und eine Teilmenge abrufen, um die Übertragungskosten zu reduzieren.  <br/> |
|[Ausführen von Abfragen](run-query.md) <br/> |Abfragevorgang ausführen bietet die Möglichkeit, eine Abfrage auf dem Cube basierend auf angegebenen Dimensionen, Maßen und Filtern auszuführen und die Daten zurückzugeben.  <br/> |
|[Leeren des Caches](clear-cache.md) <br/> |Löschen des Cache Vorgangs löscht den Cache auf dem Server für Abfragen und Daten. Dadurch wird der Cache zurückgesetzt, und wir erhalten neue Daten aus dem QoE-Cube später für neue Anforderungen.  <br/> |
|[Abrufen des Integrationsprotokolls](get-integration-log.md) <br/> |Der Vorgang "Integrationsprotokoll abrufen" gibt eine Liste der Protokolleinträge zurück, die die Aktivitäten in der QoE-Cube-Verarbeitung beschreiben.  <br/> |
|[Abrufen der letzten Integrationsdaten](get-last-integration-data.md) <br/> |Abrufen der letzten Integrationsdaten aus dem Cube  <br/> |
   
 **CORS-Unterstützung für die Daten-API**
  
Die Daten-API unterstützt die übergreifende Ressourcenfreigabe (CORS). CORS ist ein HTTP-Feature, mit dem eine Webanwendung, die unter einer Domäne ausgeführt wird, auf Ressourcen in einer anderen Domäne zugreifen kann. Webbrowser implementieren eine Sicherheitseinschränkung, die als identische [Ursprungs](https://www.w3.org/Security/wiki/Same_Origin_Policy) Richtlinie bekannt ist, die verhindert, dass eine Webseite APIs in einer anderen Domäne aufruft. CORS bietet eine sichere Möglichkeit, um eine Domäne (die Ursprungsdomäne) zu ermöglichen, APIs in einer anderen Domäne aufzurufen. Details zu CORS finden Sie in der [CORS-Spezifikation](https://www.w3.org/TR/cors/) .
  
 **Aktivieren von CORS für die Daten-API**
  
 Der folgende Code ist ein Auszug aus der Daten-API Web. config mit zwei in corsTrustedOrigin-Anwendungseinstellungen aufgelisteten Domänen. Alle Anforderungen der Skripts, die von diesen Servern geladen wurden, werden von der Daten-API als vertrauenswürdig eingestuft.
  
Denken Sie daran, das exakte Protokoll, den Hostnamen und den Port (sofern vorhanden) einzubeziehen. Setzen Sie am Ende keine Schrägstriche (/) ein. Mehrere Einträge können durch Kommas getrennt angegeben werden.
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


