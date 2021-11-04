---
title: Repository-API für das Anrufqualitäts-Dashboard (Call Quality Dashboard, CQD) in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Zusammenfassung: Erfahren Sie mehr über die Repository-API für das Anrufqualitäts-Dashboard. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 21765c4766e7fc729988f2b8ba23241175a96584
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759697"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>Repository-API für das Anrufqualitäts-Dashboard (Call Quality Dashboard, CQD) in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Repository-API für das Anrufqualitäts-Dashboard. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.
  
Die Repository-API bietet programmgesteuerten Zugriff für das Anrufqualitäts-Dashboard für Skype for Business Server.
  
## <a name="repository-api-for-call-quality-dashboard"></a>Repository-API für das Anrufqualitäts-Dashboard

Die Repository-API bietet eine Datenzugriffsschnittstelle für Repositorydatenbanken. Das Repository ermöglicht es, den Inhalt in einer Struktur oder Einer Diagrammstruktur so zu organisieren, dass Benutzer sie auf eine Weise gruppieren können, die für die Benutzer sinnvoll ist. Das Repository unterstützt zwei allgemeine Benutzertypen: Systembenutzer, bei denen es sich um einen integrierten Benutzer handelt, der das Repository darstellt, und reguläre Benutzer, die die autorisierten Benutzer des Repositorys darstellen.
  
Die Repository-API besteht aus drei allgemeinen Diensten: 
  
- [Benutzerdienst für CQD](user-service.md) – für den Zugriff auf Benutzer.
    
- [Item Service for Call Quality Dashboard (CQD)](item-service.md) – für den Zugriff auf Elemente und die in Elementen gespeicherten Inhalte.
    
- [User Einstellungen Service for Call Quality Dashboard (CQD)](user-settings-service.md) – für den Zugriff auf benutzerbasierte Einstellungen.
    
Das Anrufqualitätsdashboard verwendet die Repository-API, um die folgenden Informationen zu verwalten: 
  
- **Benutzer** – Darstellung der Benutzer, die Zugriff auf das Repository haben.
    
- **Bericht** – enthält eine Liste von Abfragen, die als Inhalt in Repositoryelementen gespeichert sind.
    
- **Abfrage** – wird verwendet, um Daten aus der Daten-API abzurufen, die als Inhalt in Repositoryelementen gespeichert sind.
    
- **Benutzereinstellung** – beschreibt ein optionales Anwendungsverhalten für den Benutzer.
    
  **Cross-Origin Resource Sharing (CORS)-Unterstützung für Repository-API**
  
Die Repository-API unterstützt cross-origin Resource Sharing (CORS). CORS ist ein HTTP-Feature, mit dem eine Webanwendung, die unter einer Domäne ausgeführt wird, auf Ressourcen in einer anderen Domäne zugreifen kann. Webbrowser implementieren eine Sicherheitseinschränkung, die als [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) Same-Origin Policy same-origin policy bezeichnet wird und verhindert, dass eine Webseite APIs in einer anderen Domäne aufruft. CORS bietet eine sichere Möglichkeit, einer Domäne (der Ursprungsdomäne) das Aufrufen von APIs in einer anderen Domäne zu ermöglichen. Details zu CORS finden Sie in der [CORS-Spezifikation.](https://www.w3.org/TR/cors/)
  
 **Aktivieren von CORS für die Repository-API**
  
 Es folgt ein Auszug der Repository-API-web.config mit zwei Domänen, die in den CorsTrustedOrigin-Anwendungseinstellungen aufgeführt sind. Alle Anforderungen, die von den von diesen Servern geladenen Skripts gestellt werden, werden von der Repository-API als vertrauenswürdig eingestuft.
  
Denken Sie daran, das genaue Protokoll, den Hostnamen und den Port (falls vorhanden) einzuschließen. Setzen Sie keinen Schrägstrich (/) am Ende. Mehrere Einträge können durch Kommas getrennt angegeben werden.
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


