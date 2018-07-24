---
title: Repository-API für Anruf Qualitätsdashboard (CQD) in Skype für Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Zusammenfassung: Informationen Sie zu der Repository-API für die Qualitätsdashboard Anruf. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.'
ms.openlocfilehash: 67378b6b0e927f45605a1ca0f7cdddffafac3022
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20989094"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server-2015"></a><span data-ttu-id="dcd80-104">Repository-API für Anruf Qualitätsdashboard (CQD) in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dcd80-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="dcd80-105">**Zusammenfassung:** Informationen Sie zu der Repository-API für Anrufqualität Dashboard.</span><span class="sxs-lookup"><span data-stu-id="dcd80-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="dcd80-106">Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="dcd80-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="dcd80-107">Die Repository-API ermöglicht den programmgesteuerten Zugriff für die Qualitätsdashboard Aufrufen für Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="dcd80-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server 2015.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="dcd80-108">Repository-API für die Qualitätsdashboard Anruf</span><span class="sxs-lookup"><span data-stu-id="dcd80-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="dcd80-109">Repository-API bietet eine Schnittstelle für den Zugriff auf Repository-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="dcd80-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="dcd80-110">Das Repository ermöglicht den Inhalt in einer Struktur oder Diagramm-Struktur so, dass Benutzer diese Weise gruppieren können, die, die den Benutzern sinnvoll organisiert werden.</span><span class="sxs-lookup"><span data-stu-id="dcd80-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="dcd80-111">Das Repository unterstützt zwei allgemeine Arten von Benutzern: System-Benutzer ist ein integrierter Benutzer, die das Repository darstellt, und normale Benutzer, die die autorisierten Benutzer des Repositorys darstellen.</span><span class="sxs-lookup"><span data-stu-id="dcd80-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="dcd80-112">Repository-API besteht aus drei allgemeine Dienste:</span><span class="sxs-lookup"><span data-stu-id="dcd80-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="dcd80-113">[Benutzerdienst für CQD](user-service.md) – für den Zugriff auf Benutzer.</span><span class="sxs-lookup"><span data-stu-id="dcd80-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="dcd80-114">[Dienst für aufrufen Quality Dashboard (CQD)](item-service.md) – für den Zugriff auf Elemente und den Inhalt in dem Elemente gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dcd80-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="dcd80-115">[User Settings Service für aufrufen Quality Dashboard (CQD)](user-settings-service.md) – für den Zugriff auf Benutzereinstellungen.</span><span class="sxs-lookup"><span data-stu-id="dcd80-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="dcd80-116">Anruf Qualitätsdashboard verwendet Repository-API, um die folgenden Informationen zu verwalten:</span><span class="sxs-lookup"><span data-stu-id="dcd80-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="dcd80-117">**Benutzer** - Darstellung der Benutzer, die auf das Repository zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="dcd80-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="dcd80-118">**Bericht** - enthält eine Liste von Abfragen, die als eine Inhalt im Repository-Elemente gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dcd80-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="dcd80-119">**Abfrage** - zum Abrufen von Daten aus Daten-API, gespeichert als eine Inhalt im Repository-Elemente verwendet.</span><span class="sxs-lookup"><span data-stu-id="dcd80-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="dcd80-120">**Die Einstellung für Benutzer** - beschreibt eine optionale Anwendungsverhalten für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="dcd80-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
 <span data-ttu-id="dcd80-121">**Cross-Origin Resource Sharing (CORS) Unterstützung für Repository-API**</span><span class="sxs-lookup"><span data-stu-id="dcd80-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="dcd80-122">Repository-API unterstützt Cross-Origin Resource Sharing (CORS).</span><span class="sxs-lookup"><span data-stu-id="dcd80-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="dcd80-123">CORS ist ein HTTP-Feature, mit dem eine Webanwendung in einer Domäne mit Zugriff auf Ressourcen in einer anderen Domäne.</span><span class="sxs-lookup"><span data-stu-id="dcd80-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="dcd80-124">Webbrowser implementieren eine Einschränkung für die Sicherheit als [Same Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same Origin Policy, die verhindert, eine Webseite nicht Aufrufen von APIs in einer anderen Domäne dass bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="dcd80-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="dcd80-125">CORS bietet auf sichere Weise zu einer Domäne (der Ursprungsdomäne) in einer anderen Domäne APIs aufrufen können.</span><span class="sxs-lookup"><span data-stu-id="dcd80-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="dcd80-126">Informationen finden Sie die [Spezifikation CORS](https://www.w3.org/TR/cors/) auf CORS.</span><span class="sxs-lookup"><span data-stu-id="dcd80-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="dcd80-127">**Aktivieren von CORS für Repository-API**</span><span class="sxs-lookup"><span data-stu-id="dcd80-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="dcd80-128">Das folgende ist ein Auszug aus Repository API "Web.config", mit zwei Domänen, die in CorsTrustedOrigin Anwendungseinstellungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="dcd80-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="dcd80-129">Alle Anfragen, die durch die Skripts, die aus diesen Servern geladen werden vom Repository API als vertrauenswürdig.</span><span class="sxs-lookup"><span data-stu-id="dcd80-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="dcd80-130">Denken Sie daran, die genaue Protokoll, Hostname und Port (falls vorhanden).</span><span class="sxs-lookup"><span data-stu-id="dcd80-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="dcd80-131">Nicht, um zu führen Sie einem Zeichen (/) am Ende Schrägstrich.</span><span class="sxs-lookup"><span data-stu-id="dcd80-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="dcd80-132">Mehrere Einträge können durch Kommas getrennt angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="dcd80-132">Multiple entries can be specified by separating with commas.</span></span>
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


