---
title: Daten-API für Anruf Qualitätsdashboard (CQD) in Skype für Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Zusammenfassung: Informationen Sie zu den Rata-API für die Qualitätsdashboard Anruf. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.'
ms.openlocfilehash: e48d1a6719f77e5f91167aa76ce4f58704883fc9
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26293846"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server-2015"></a>Daten-API für Anruf Qualitätsdashboard (CQD) in Skype für Business Server 2015
 
**Zusammenfassung:** Informationen Sie zu den Rata API für Anrufqualität Dashboard. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.
  
Die Daten-API ermöglicht den programmgesteuerten Zugriff für die Qualitätsdashboard Aufrufen für Skype für Business Server 2015.
  
## <a name="data-api-for-call-quality-dashboard"></a>Daten-API für die Qualitätsdashboard Anruf

Die Daten-API bietet eine Abfrageschnittstelle an den QoE-Cube. Die Daten-API ist eine REST-API für die Arbeit mit mehrdimensionale Datenbank, die basierend auf angegebenen Dimensionen und Filter aggregierte QoE-Metriken bereitstellt.
  
In der folgenden Tabelle sind die REST-Vorgänge enthalten.
  

|**Vorgang**|**Beschreibung**|
|:-----|:-----|
|[Abrufen von Cubes](get-cube.md) <br/> |Rufen Sie die Liste der verfügbaren Dimensionen und Maßeinheiten an.  <br/> |
|[Abrufen von Dimensionselementen](get-dimension-members.md) <br/> |Dimensionselemente Abrufvorgang gibt die Liste der Mitglieder einer bestimmten Dimension zurück. Es auch bieten die Möglichkeit zum Filtern der Memberliste und erhalten Sie eine Teilmenge die Leitung Übertragung Kosten zu senken.  <br/> |
|[Ausführen der Abfrage](run-query.md) <br/> |Führen Sie Abfrage Vorgang die Möglichkeit zum Ausführen einer Abfrage für den Cube basierend auf angegebenen Dimensionen, Maßeinheiten und Filter bietet und wieder zurückgeben Sie die Daten.  <br/> |
|[Cache löschen](clear-cache.md) <br/> |Löschvorgang Cache löscht den Cache auf dem Server für Abfragen und Daten. Dadurch wird den Cache zurückgesetzt, und wir erhalten neue Daten vom QoE-Cube später für neue Anfragen.  <br/> |
|[Integration Protokoll abrufen](get-integration-log.md) <br/> |Möchten Sie Integration Protokoll Operation gibt eine Liste der Protokolleinträge, beschreibt die Aktivitäten in QoE-Cube zurück, Verarbeitung erhalten.  <br/> |
|[Abrufen von Integrationsdaten der letzten](get-last-integration-data.md) <br/> |Rufen Sie die letzten von Integrationsdaten aus dem Cube.  <br/> |
   
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


