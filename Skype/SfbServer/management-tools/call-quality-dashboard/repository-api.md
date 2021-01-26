---
title: Repository-API für das Anrufqualitätsdashboard (CQD) in Skype for Business Server
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
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Zusammenfassung: Erfahren Sie mehr über die Repository-API für das Anrufqualitätsdashboard. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 982ec0932f0a57958e1929a6ae2413ada0b5c9fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803125"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>Repository-API für das Anrufqualitätsdashboard (CQD) in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Repository-API für das Anrufqualitätsdashboard. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.
  
Die Repository-API bietet programmgesteuerten Zugriff für das Anrufqualitätsdashboard für Skype for Business Server.
  
## <a name="repository-api-for-call-quality-dashboard"></a>Repository-API für anrufqualitätsdashboard

Die Repository-API bietet eine Datenzugriffsschnittstelle für die Repositorydatenbank. Das Repository ermöglicht es, die Inhalte in einer Struktur oder Diagrammstruktur so zu organisieren, dass Benutzer sie auf die für die Benutzer sinnvollen Weise gruppieren können. Das Repository unterstützt zwei allgemeine Benutzertypen: Systembenutzer, bei denen es sich um einen integrierten Benutzer handelt, der das Repository darstellt, und reguläre Benutzer, die die autorisierten Benutzer des Repositorys darstellen.
  
Die Repository-API besteht aus drei allgemeinen Diensten: 
  
- [Benutzerdienst für CQD](user-service.md) – für den Zugriff auf Benutzer.
    
- [Item Service for Call Quality Dashboard (CQD)](item-service.md) – für den Zugriff auf Elemente und die in Elementen gespeicherten Inhalte.
    
- [Dienst für Benutzereinstellungen für das Anrufqualitätsdashboard (CQD)](user-settings-service.md) für den Zugriff auf Benutzereinstellungen.
    
Das Anrufqualitätsdashboard verwendet die Repository-API, um die folgenden Informationen zu verwalten: 
  
- **Benutzer** – Darstellung der Benutzer, die Zugriff auf das Repository haben.
    
- **Bericht** – enthält eine Liste von Abfragen, die als Inhalt in Repositoryelementen gespeichert sind.
    
- **Abfrage** – wird verwendet, um Daten aus der Daten-API abzurufen, die als Inhalt in Repositoryelementen gespeichert sind.
    
- **Benutzereinstellung** – beschreibt ein optionales Anwendungsverhalten für den Benutzer.
    
  **Cross-Origin Resource Sharing (CORS)-Unterstützung für Repository-API**
  
Die Repository-API unterstützt cross-Origin Resource Sharing (CORS). CORS ist ein HTTP-Feature, mit dem eine Webanwendung, die unter einer Domäne ausgeführt wird, auf Ressourcen in einer anderen Domäne zugreifen kann. Webbrowser implementieren eine Sicherheitseinschränkung, die als "Richtlinie des gleichen Ursprungs" bezeichnet wird und verhindert, dass eine Webseite APIs in einer anderen Domäne aufruft. [](https://www.w3.org/Security/wiki/Same_Origin_Policy) CORS bietet eine sichere Möglichkeit, einer Domäne (der Ursprungsdomäne) das Aufrufen von APIs in einer anderen Domäne zu ermöglichen. Details zu [CORS finden](https://www.w3.org/TR/cors/) Sie in der CORS-Spezifikation.
  
 **Aktivieren von CORS für die Repository-API**
  
 Es folgt ein Auszug aus repository-API-web.config mit zwei Domänen, die in den CorsTrustedOrigin-Anwendungseinstellungen aufgelistet sind. Alle Anforderungen der von diesen Servern geladenen Skripts werden von der Repository-API als vertrauenswürdig eingestuft.
  
Denken Sie daran, das genaue Protokoll, den Hostnamen und den Port (falls dies der Fall ist) zu verwenden. Setzen Sie keinen Schrägstrich (/) am Ende. Mehrere Einträge können durch Kommas getrennt angegeben werden.
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


