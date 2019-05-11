---
title: Daten-API für Anruf Qualitätsdashboard (CQD) in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Zusammenfassung: Informationen Sie zu den Rata-API für die Qualitätsdashboard Anruf. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: e1143752031406885a77e5afab975463d5732220
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930700"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>Daten-API für Anruf Qualitätsdashboard (CQD) in Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zu den Rata API für Anrufqualität Dashboard. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.
  
Die Daten-API ermöglicht den programmgesteuerten Zugriff für die Qualitätsdashboard Aufrufen für Skype für Business Server.
  
## <a name="data-api-for-call-quality-dashboard"></a>Daten-API für die Qualitätsdashboard Anruf

Die Daten-API bietet eine Abfrageschnittstelle an den QoE-Cube. Die Daten-API ist eine REST-API für die Arbeit mit mehrdimensionale Datenbank, die basierend auf angegebenen Dimensionen und Filter aggregierte QoE-Metriken bereitstellt.
  
In der folgenden Tabelle sind die REST-Vorgänge enthalten.
  

|**Vorgang**|**Beschreibung**|
|:-----|:-----|
|[Abrufen von Cubes](get-cube.md) <br/> |Rufen Sie die Liste der verfügbaren Dimensionen und Maßeinheiten an.  <br/> |
|[Abrufen von Dimensionselementen](get-dimension-members.md) <br/> |Dimensionselemente Abrufvorgang gibt die Liste der Mitglieder einer bestimmten Dimension zurück. Es auch bieten die Möglichkeit zum Filtern der Memberliste und erhalten Sie eine Teilmenge die Leitung Übertragung Kosten zu senken.  <br/> |
|[Ausführen von Abfragen](run-query.md) <br/> |Führen Sie Abfrage Vorgang die Möglichkeit zum Ausführen einer Abfrage für den Cube basierend auf angegebenen Dimensionen, Maßeinheiten und Filter bietet und wieder zurückgeben Sie die Daten.  <br/> |
|[Leeren des Caches](clear-cache.md) <br/> |Löschvorgang Cache löscht den Cache auf dem Server für Abfragen und Daten. Dadurch wird den Cache zurückgesetzt, und wir erhalten neue Daten vom QoE-Cube später für neue Anfragen.  <br/> |
|[Abrufen des Integrationsprotokolls](get-integration-log.md) <br/> |Möchten Sie Integration Protokoll Operation gibt eine Liste der Protokolleinträge, beschreibt die Aktivitäten in QoE-Cube zurück, Verarbeitung erhalten.  <br/> |
|[Abrufen der letzten Integrationsdaten](get-last-integration-data.md) <br/> |Rufen Sie die letzten von Integrationsdaten aus dem Cube.  <br/> |
   
 **Cross-Origin Resource Sharing (CORS)-Unterstützung für Daten-API**
  
Daten-API unterstützt Cross-Origin Resource Sharing (CORS). CORS ist ein HTTP-Feature, mit dem eine Webanwendung in einer Domäne mit Zugriff auf Ressourcen in einer anderen Domäne. Webbrowser implementieren eine Einschränkung für die Sicherheit als [Same Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same Origin Policy, die verhindert, eine Webseite nicht Aufrufen von APIs in einer anderen Domäne dass bezeichnet. CORS bietet auf sichere Weise zu einer Domäne (der Ursprungsdomäne) in einer anderen Domäne APIs aufrufen können. Informationen finden Sie die [Spezifikation CORS](https://www.w3.org/TR/cors/) auf CORS.
  
 **Aktivieren von CORS für Daten-API**
  
 Das folgende ist ein Auszug aus Daten-API "Web.config", mit zwei Domänen, die in CorsTrustedOrigin Anwendungseinstellungen aufgelistet. Alle Anfragen, die durch die Skripts, die aus diesen Servern geladen werden Daten-API vertraut.
  
Denken Sie daran, die genaue Protokoll, Hostname und Port (falls vorhanden). Nicht, um zu führen Sie einem Zeichen (/) am Ende Schrägstrich. Mehrere Einträge können durch Kommas getrennt angegeben werden.
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


