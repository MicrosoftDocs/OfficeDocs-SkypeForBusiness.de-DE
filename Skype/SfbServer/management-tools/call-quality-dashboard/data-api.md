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
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="19041-104">Daten-API für Anruf Qualitäts Dashboard (CQD) in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="19041-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="19041-105">**Zusammenfassung:** Informieren Sie sich über die Daten-API für die Anrufqualität.</span><span class="sxs-lookup"><span data-stu-id="19041-105">**Summary:** Learn about the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="19041-106">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="19041-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="19041-107">Die Daten-API bietet programmgesteuerten Zugriff für das Anruf Qualitäts Dashboard für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="19041-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="19041-108">Daten-API für Anruf Qualitäts Dashboard</span><span class="sxs-lookup"><span data-stu-id="19041-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="19041-109">Die Daten-API bietet eine Abfrageschnittstelle für den QoE-Cube.</span><span class="sxs-lookup"><span data-stu-id="19041-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="19041-110">Die Daten-API ist eine Ruhe-API für die Arbeit mit mehrdimensionaler Datenbank, die aggregierte QoE-Metriken basierend auf angegebenen Dimensionen und Filtern bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="19041-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="19041-111">Die übrigen Vorgänge sind in der folgenden Tabelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="19041-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="19041-112">**Vorgang**</span><span class="sxs-lookup"><span data-stu-id="19041-112">**Operation**</span></span>|<span data-ttu-id="19041-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="19041-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="19041-114">Abrufen von Cubes</span><span class="sxs-lookup"><span data-stu-id="19041-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="19041-115">Rufen Sie die Liste der verfügbaren Dimensionen und Maße ab.</span><span class="sxs-lookup"><span data-stu-id="19041-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="19041-116">Abrufen von Dimensionselementen</span><span class="sxs-lookup"><span data-stu-id="19041-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="19041-117">Der Vorgang zum Abrufen von Dimensionselementen gibt die Liste der Elemente einer bestimmten Dimension zurück.</span><span class="sxs-lookup"><span data-stu-id="19041-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="19041-118">Darüber hinaus können Sie die Mitgliederliste Filtern und eine Teilmenge abrufen, um die Übertragungskosten zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="19041-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="19041-119">Ausführen von Abfragen</span><span class="sxs-lookup"><span data-stu-id="19041-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="19041-120">Abfragevorgang ausführen bietet die Möglichkeit, eine Abfrage auf dem Cube basierend auf angegebenen Dimensionen, Maßen und Filtern auszuführen und die Daten zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="19041-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="19041-121">Leeren des Caches</span><span class="sxs-lookup"><span data-stu-id="19041-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="19041-122">Löschen des Cache Vorgangs löscht den Cache auf dem Server für Abfragen und Daten.</span><span class="sxs-lookup"><span data-stu-id="19041-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="19041-123">Dadurch wird der Cache zurückgesetzt, und wir erhalten neue Daten aus dem QoE-Cube später für neue Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="19041-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="19041-124">Abrufen des Integrationsprotokolls</span><span class="sxs-lookup"><span data-stu-id="19041-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="19041-125">Der Vorgang "Integrationsprotokoll abrufen" gibt eine Liste der Protokolleinträge zurück, die die Aktivitäten in der QoE-Cube-Verarbeitung beschreiben.</span><span class="sxs-lookup"><span data-stu-id="19041-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="19041-126">Abrufen der letzten Integrationsdaten</span><span class="sxs-lookup"><span data-stu-id="19041-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="19041-127">Abrufen der letzten Integrationsdaten aus dem Cube</span><span class="sxs-lookup"><span data-stu-id="19041-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="19041-128">**CORS-Unterstützung für die Daten-API**</span><span class="sxs-lookup"><span data-stu-id="19041-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="19041-129">Die Daten-API unterstützt die übergreifende Ressourcenfreigabe (CORS).</span><span class="sxs-lookup"><span data-stu-id="19041-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="19041-130">CORS ist ein HTTP-Feature, mit dem eine Webanwendung, die unter einer Domäne ausgeführt wird, auf Ressourcen in einer anderen Domäne zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="19041-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="19041-131">Webbrowser implementieren eine Sicherheitseinschränkung, die als identische [Ursprungs](https://www.w3.org/Security/wiki/Same_Origin_Policy) Richtlinie bekannt ist, die verhindert, dass eine Webseite APIs in einer anderen Domäne aufruft.</span><span class="sxs-lookup"><span data-stu-id="19041-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="19041-132">CORS bietet eine sichere Möglichkeit, um eine Domäne (die Ursprungsdomäne) zu ermöglichen, APIs in einer anderen Domäne aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="19041-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="19041-133">Details zu CORS finden Sie in der [CORS-Spezifikation](https://www.w3.org/TR/cors/) .</span><span class="sxs-lookup"><span data-stu-id="19041-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="19041-134">**Aktivieren von CORS für die Daten-API**</span><span class="sxs-lookup"><span data-stu-id="19041-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="19041-135">Der folgende Code ist ein Auszug aus der Daten-API Web. config mit zwei in corsTrustedOrigin-Anwendungseinstellungen aufgelisteten Domänen.</span><span class="sxs-lookup"><span data-stu-id="19041-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="19041-136">Alle Anforderungen der Skripts, die von diesen Servern geladen wurden, werden von der Daten-API als vertrauenswürdig eingestuft.</span><span class="sxs-lookup"><span data-stu-id="19041-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="19041-137">Denken Sie daran, das exakte Protokoll, den Hostnamen und den Port (sofern vorhanden) einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="19041-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="19041-138">Setzen Sie am Ende keine Schrägstriche (/) ein.</span><span class="sxs-lookup"><span data-stu-id="19041-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="19041-139">Mehrere Einträge können durch Kommas getrennt angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="19041-139">Multiple entries can be specified by separating with commas.</span></span>
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


