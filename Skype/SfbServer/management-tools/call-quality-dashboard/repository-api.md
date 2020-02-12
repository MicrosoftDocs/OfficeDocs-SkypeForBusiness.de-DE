---
title: Repository-API für das Anruf Qualitäts Dashboard (CQD) in Skype for Business Server
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
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Zusammenfassung: erfahren Sie mehr über die Repository-API für die Anrufqualität. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 283ef7544435c3954898b2d5ae9e5f5b38762f3c
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888784"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="4c4bc-104">Repository-API für das Anruf Qualitäts Dashboard (CQD) in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4c4bc-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="4c4bc-105">**Zusammenfassung:** Informieren Sie sich über die Repository-API für die Anrufqualität.</span><span class="sxs-lookup"><span data-stu-id="4c4bc-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="4c4bc-106">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4c4bc-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="4c4bc-107">Die Repository-API bietet programmgesteuerten Zugriff für das Anruf Qualitäts Dashboard für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4c4bc-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="4c4bc-108">Repository-API für Anruf Qualitäts Dashboard</span><span class="sxs-lookup"><span data-stu-id="4c4bc-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="4c4bc-109">Die Repository-API bietet eine Datenzugriffsschnittstelle zur Repository-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="4c4bc-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="4c4bc-110">Das Repository ermöglicht es, die Inhalte in einer Struktur-oder Diagrammstruktur zu organisieren, sodass Benutzer Sie in der Weise gruppieren können, die für die Benutzer sinnvoll ist.</span><span class="sxs-lookup"><span data-stu-id="4c4bc-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="4c4bc-111">Das Repository unterstützt zwei allgemeine Benutzertypen: Systembenutzer, ein integrierter Benutzer, der das Repository darstellt, und reguläre Benutzer, die die autorisierten Benutzer des Repositorys darstellen.</span><span class="sxs-lookup"><span data-stu-id="4c4bc-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="4c4bc-112">Die Repository-API besteht aus drei allgemeinen Diensten:</span><span class="sxs-lookup"><span data-stu-id="4c4bc-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="4c4bc-113">[Benutzer Dienst für CQD](user-service.md) -für den Zugriff auf Benutzer.</span><span class="sxs-lookup"><span data-stu-id="4c4bc-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="4c4bc-114">[Element Dienst für das Anruf Qualitäts Dashboard (CQD)](item-service.md) – für den Zugriff auf Elemente und die Inhalte, die in Elementen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="4c4bc-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="4c4bc-115">[Benutzer Einstellungsdienst für das Anruf Qualitäts Dashboard (CQD)](user-settings-service.md) – für den Zugriff auf Benutzereinstellungen.</span><span class="sxs-lookup"><span data-stu-id="4c4bc-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="4c4bc-116">Das Dashboard für die Anrufqualität verwendet die Repository-API, um die folgenden Informationen zu verwalten:</span><span class="sxs-lookup"><span data-stu-id="4c4bc-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="4c4bc-117">**Benutzer** Darstellung von Benutzern, die auf das Repository zugreifen können</span><span class="sxs-lookup"><span data-stu-id="4c4bc-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="4c4bc-118">**Bericht** – enthält eine Liste von Abfragen, die als Inhalt in Repository-Elementen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="4c4bc-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="4c4bc-119">**Query** – wird verwendet, um Daten aus der Daten-API abzurufen, die als Inhalt in Repository-Elementen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="4c4bc-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="4c4bc-120">**Benutzereinstellung** – beschreibt ein optionales Anwendungsverhalten für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="4c4bc-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
  <span data-ttu-id="4c4bc-121">**CORS-Unterstützung für die Repository-API**</span><span class="sxs-lookup"><span data-stu-id="4c4bc-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="4c4bc-122">Repository-API unterstützt die übergreifende Ressourcenfreigabe (CORS).</span><span class="sxs-lookup"><span data-stu-id="4c4bc-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="4c4bc-123">CORS ist ein HTTP-Feature, mit dem eine Webanwendung, die unter einer Domäne ausgeführt wird, auf Ressourcen in einer anderen Domäne zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="4c4bc-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="4c4bc-124">Webbrowser implementieren eine Sicherheitseinschränkung, die als identische [Ursprungs](https://www.w3.org/Security/wiki/Same_Origin_Policy) Richtlinie bekannt ist, die verhindert, dass eine Webseite APIs in einer anderen Domäne aufruft.</span><span class="sxs-lookup"><span data-stu-id="4c4bc-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="4c4bc-125">CORS bietet eine sichere Möglichkeit, um eine Domäne (die Ursprungsdomäne) zu ermöglichen, APIs in einer anderen Domäne aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="4c4bc-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="4c4bc-126">Details zu CORS finden Sie in der [CORS-Spezifikation](https://www.w3.org/TR/cors/) .</span><span class="sxs-lookup"><span data-stu-id="4c4bc-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="4c4bc-127">**Aktivieren von CORS für die Repository-API**</span><span class="sxs-lookup"><span data-stu-id="4c4bc-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="4c4bc-128">Im folgenden finden Sie einen Auszug aus der Repository-API Web. config mit zwei in corsTrustedOrigin-Anwendungseinstellungen aufgelisteten Domänen.</span><span class="sxs-lookup"><span data-stu-id="4c4bc-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="4c4bc-129">Alle Anforderungen der Skripts, die von diesen Servern geladen wurden, werden von der Repository-API als vertrauenswürdig eingestuft.</span><span class="sxs-lookup"><span data-stu-id="4c4bc-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="4c4bc-130">Denken Sie daran, das exakte Protokoll, den Hostnamen und den Port (sofern vorhanden) einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="4c4bc-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="4c4bc-131">Setzen Sie am Ende keine Schrägstriche (/) ein.</span><span class="sxs-lookup"><span data-stu-id="4c4bc-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="4c4bc-132">Mehrere Einträge können durch Kommas getrennt angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4c4bc-132">Multiple entries can be specified by separating with commas.</span></span>
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


