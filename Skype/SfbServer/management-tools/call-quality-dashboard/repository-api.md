---
title: Repository-API für das Anruf Qualitäts Dashboard (CQD) in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Zusammenfassung: erfahren Sie mehr über die Repository-API für die Anrufqualität. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 723b7a9340737e3f1cec47112b33ff1175597cd0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274576"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>Repository-API für das Anruf Qualitäts Dashboard (CQD) in Skype for Business Server
 
**Zusammenfassung:** Informieren Sie sich über die Repository-API für die Anrufqualität. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.
  
Die Repository-API bietet programmgesteuerten Zugriff für das Anruf Qualitäts Dashboard für Skype for Business Server.
  
## <a name="repository-api-for-call-quality-dashboard"></a>Repository-API für Anruf Qualitäts Dashboard

Die Repository-API bietet eine Datenzugriffsschnittstelle zur Repository-Datenbank. Das Repository ermöglicht es, die Inhalte in einer Struktur-oder Diagrammstruktur zu organisieren, sodass Benutzer Sie in der Weise gruppieren können, die für die Benutzer sinnvoll ist. Das Repository unterstützt zwei allgemeine Benutzertypen: Systembenutzer, ein integrierter Benutzer, der das Repository darstellt, und reguläre Benutzer, die die autorisierten Benutzer des Repositorys darstellen.
  
Die Repository-API besteht aus drei allgemeinen Diensten: 
  
- [Benutzer Dienst für CQD](user-service.md) -für den Zugriff auf Benutzer.
    
- [Element Dienst für das Anruf Qualitäts Dashboard (CQD)](item-service.md) – für den Zugriff auf Elemente und die Inhalte, die in Elementen gespeichert sind.
    
- [Benutzer Einstellungsdienst für das Anruf Qualitäts Dashboard (CQD)](user-settings-service.md) – für den Zugriff auf Benutzereinstellungen.
    
Das Dashboard für die Anrufqualität verwendet die Repository-API, um die folgenden Informationen zu verwalten: 
  
- **Benutzer** Darstellung von Benutzern, die auf das Repository zugreifen können
    
- **Bericht** – enthält eine Liste von Abfragen, die als Inhalt in Repository-Elementen gespeichert sind.
    
- **Query** – wird verwendet, um Daten aus der Daten-API abzurufen, die als Inhalt in Repository-Elementen gespeichert sind.
    
- **Benutzereinstellung** – beschreibt ein optionales Anwendungsverhalten für den Benutzer.
    
  **CORS-Unterstützung für die Repository-API**
  
Repository-API unterstützt die übergreifende Ressourcenfreigabe (CORS). CORS ist ein HTTP-Feature, mit dem eine Webanwendung, die unter einer Domäne ausgeführt wird, auf Ressourcen in einer anderen Domäne zugreifen kann. Webbrowser implementieren eine Sicherheitseinschränkung, die als identische [Ursprungs](https://www.w3.org/Security/wiki/Same_Origin_Policy) Richtlinie bekannt ist, die verhindert, dass eine Webseite APIs in einer anderen Domäne aufruft. CORS bietet eine sichere Möglichkeit, um eine Domäne (die Ursprungsdomäne) zu ermöglichen, APIs in einer anderen Domäne aufzurufen. Details zu CORS finden Sie in der [CORS-Spezifikation](https://www.w3.org/TR/cors/) .
  
 **Aktivieren von CORS für die Repository-API**
  
 Im folgenden finden Sie einen Auszug aus der Repository-API Web. config mit zwei in corsTrustedOrigin-Anwendungseinstellungen aufgelisteten Domänen. Alle Anforderungen der Skripts, die von diesen Servern geladen wurden, werden von der Repository-API als vertrauenswürdig eingestuft.
  
Denken Sie daran, das exakte Protokoll, den Hostnamen und den Port (sofern vorhanden) einzubeziehen. Setzen Sie am Ende keine Schrägstriche (/) ein. Mehrere Einträge können durch Kommas getrennt angegeben werden.
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


