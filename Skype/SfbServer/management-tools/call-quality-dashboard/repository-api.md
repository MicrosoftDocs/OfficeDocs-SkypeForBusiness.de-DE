---
title: Repository-API für Anruf Qualitätsdashboard (CQD) in Skype für Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Zusammenfassung: Informationen Sie zu der Repository-API für die Qualitätsdashboard Anruf. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: 9181cd1454311bb5446bb18f51af56914387e7c3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217656"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>Repository-API für Anruf Qualitätsdashboard (CQD) in Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zu der Repository-API für Anrufqualität Dashboard. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.
  
Die Repository-API ermöglicht den programmgesteuerten Zugriff für die Qualitätsdashboard Aufrufen für Skype für Business Server.
  
## <a name="repository-api-for-call-quality-dashboard"></a>Repository-API für die Qualitätsdashboard Anruf

Repository-API bietet eine Schnittstelle für den Zugriff auf Repository-Datenbank. Das Repository ermöglicht den Inhalt in einer Struktur oder Diagramm-Struktur so, dass Benutzer diese Weise gruppieren können, die, die den Benutzern sinnvoll organisiert werden. Das Repository unterstützt zwei allgemeine Arten von Benutzern: System-Benutzer ist ein integrierter Benutzer, die das Repository darstellt, und normale Benutzer, die die autorisierten Benutzer des Repositorys darstellen.
  
Repository-API besteht aus drei allgemeine Dienste: 
  
- [Benutzerdienst für CQD](user-service.md) – für den Zugriff auf Benutzer.
    
- [Dienst für aufrufen Quality Dashboard (CQD)](item-service.md) – für den Zugriff auf Elemente und den Inhalt in dem Elemente gespeichert.
    
- [User Settings Service für aufrufen Quality Dashboard (CQD)](user-settings-service.md) – für den Zugriff auf Benutzereinstellungen.
    
Anruf Qualitätsdashboard verwendet Repository-API, um die folgenden Informationen zu verwalten: 
  
- **Benutzer** - Darstellung der Benutzer, die auf das Repository zugreifen können.
    
- **Bericht** - enthält eine Liste von Abfragen, die als eine Inhalt im Repository-Elemente gespeichert.
    
- **Abfrage** - zum Abrufen von Daten aus Daten-API, gespeichert als eine Inhalt im Repository-Elemente verwendet.
    
- **Die Einstellung für Benutzer** - beschreibt eine optionale Anwendungsverhalten für den Benutzer.
    
  **Cross-Origin Resource Sharing (CORS) Unterstützung für Repository-API**
  
Repository-API unterstützt Cross-Origin Resource Sharing (CORS). CORS ist ein HTTP-Feature, mit dem eine Webanwendung in einer Domäne mit Zugriff auf Ressourcen in einer anderen Domäne. Webbrowser implementieren eine Einschränkung für die Sicherheit als [Same Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same Origin Policy, die verhindert, eine Webseite nicht Aufrufen von APIs in einer anderen Domäne dass bezeichnet. CORS bietet auf sichere Weise zu einer Domäne (der Ursprungsdomäne) in einer anderen Domäne APIs aufrufen können. Informationen finden Sie die [Spezifikation CORS](https://www.w3.org/TR/cors/) auf CORS.
  
 **Aktivieren von CORS für Repository-API**
  
 Das folgende ist ein Auszug aus Repository API "Web.config", mit zwei Domänen, die in CorsTrustedOrigin Anwendungseinstellungen aufgelistet. Alle Anfragen, die durch die Skripts, die aus diesen Servern geladen werden vom Repository API als vertrauenswürdig.
  
Denken Sie daran, die genaue Protokoll, Hostname und Port (falls vorhanden). Nicht, um zu führen Sie einem Zeichen (/) am Ende Schrägstrich. Mehrere Einträge können durch Kommas getrennt angegeben werden.
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


