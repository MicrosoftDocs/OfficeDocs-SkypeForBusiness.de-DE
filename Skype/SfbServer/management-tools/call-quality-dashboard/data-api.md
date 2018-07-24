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
ms.openlocfilehash: 293844d253e70e291c063d2af64226abaed3c9d9
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21011078"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server-2015"></a><span data-ttu-id="770d0-104">Daten-API für Anruf Qualitätsdashboard (CQD) in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="770d0-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="770d0-105">**Zusammenfassung:** Informationen Sie zu den Rata API für Anrufqualität Dashboard.</span><span class="sxs-lookup"><span data-stu-id="770d0-105">**Summary:** Learn about the Rata API for Call Quality Dashboard.</span></span> <span data-ttu-id="770d0-106">Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="770d0-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="770d0-107">Die Daten-API ermöglicht den programmgesteuerten Zugriff für die Qualitätsdashboard Aufrufen für Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="770d0-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server 2015.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="770d0-108">Daten-API für die Qualitätsdashboard Anruf</span><span class="sxs-lookup"><span data-stu-id="770d0-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="770d0-109">Die Daten-API bietet eine Abfrageschnittstelle an den QoE-Cube.</span><span class="sxs-lookup"><span data-stu-id="770d0-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="770d0-110">Die Daten-API ist eine REST-API für die Arbeit mit mehrdimensionale Datenbank, die basierend auf angegebenen Dimensionen und Filter aggregierte QoE-Metriken bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="770d0-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="770d0-111">In der folgenden Tabelle sind die REST-Vorgänge enthalten.</span><span class="sxs-lookup"><span data-stu-id="770d0-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="770d0-112">**Vorgang**</span><span class="sxs-lookup"><span data-stu-id="770d0-112">**Operation**</span></span>|<span data-ttu-id="770d0-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="770d0-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="770d0-114">Abrufen von Cubes</span><span class="sxs-lookup"><span data-stu-id="770d0-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="770d0-115">Rufen Sie die Liste der verfügbaren Dimensionen und Maßeinheiten an.</span><span class="sxs-lookup"><span data-stu-id="770d0-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="770d0-116">Abrufen von Dimensionselementen</span><span class="sxs-lookup"><span data-stu-id="770d0-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="770d0-117">Dimensionselemente Abrufvorgang gibt die Liste der Mitglieder einer bestimmten Dimension zurück.</span><span class="sxs-lookup"><span data-stu-id="770d0-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="770d0-118">Es auch bieten die Möglichkeit zum Filtern der Memberliste und erhalten Sie eine Teilmenge die Leitung Übertragung Kosten zu senken.</span><span class="sxs-lookup"><span data-stu-id="770d0-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="770d0-119">Ausführen der Abfrage</span><span class="sxs-lookup"><span data-stu-id="770d0-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="770d0-120">Führen Sie Abfrage Vorgang die Möglichkeit zum Ausführen einer Abfrage für den Cube basierend auf angegebenen Dimensionen, Maßeinheiten und Filter bietet und wieder zurückgeben Sie die Daten.</span><span class="sxs-lookup"><span data-stu-id="770d0-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="770d0-121">Cache löschen</span><span class="sxs-lookup"><span data-stu-id="770d0-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="770d0-122">Löschvorgang Cache löscht den Cache auf dem Server für Abfragen und Daten.</span><span class="sxs-lookup"><span data-stu-id="770d0-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="770d0-123">Dadurch wird den Cache zurückgesetzt, und wir erhalten neue Daten vom QoE-Cube später für neue Anfragen.</span><span class="sxs-lookup"><span data-stu-id="770d0-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="770d0-124">Integration Protokoll abrufen</span><span class="sxs-lookup"><span data-stu-id="770d0-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="770d0-125">Möchten Sie Integration Protokoll Operation gibt eine Liste der Protokolleinträge, beschreibt die Aktivitäten in QoE-Cube zurück, Verarbeitung erhalten.</span><span class="sxs-lookup"><span data-stu-id="770d0-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="770d0-126">Abrufen von Integrationsdaten der letzten</span><span class="sxs-lookup"><span data-stu-id="770d0-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="770d0-127">Rufen Sie die letzten von Integrationsdaten aus dem Cube.</span><span class="sxs-lookup"><span data-stu-id="770d0-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="770d0-128">**Cross-Origin Resource Sharing (CORS)-Unterstützung für Daten-API**</span><span class="sxs-lookup"><span data-stu-id="770d0-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="770d0-129">Daten-API unterstützt Cross-Origin Resource Sharing (CORS).</span><span class="sxs-lookup"><span data-stu-id="770d0-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="770d0-130">CORS ist ein HTTP-Feature, mit dem eine Webanwendung in einer Domäne mit Zugriff auf Ressourcen in einer anderen Domäne.</span><span class="sxs-lookup"><span data-stu-id="770d0-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="770d0-131">Webbrowser implementieren eine Einschränkung für die Sicherheit als [Same Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same Origin Policy, die verhindert, eine Webseite nicht Aufrufen von APIs in einer anderen Domäne dass bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="770d0-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="770d0-132">CORS bietet auf sichere Weise zu einer Domäne (der Ursprungsdomäne) in einer anderen Domäne APIs aufrufen können.</span><span class="sxs-lookup"><span data-stu-id="770d0-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="770d0-133">Informationen finden Sie die [Spezifikation CORS](https://www.w3.org/TR/cors/) auf CORS.</span><span class="sxs-lookup"><span data-stu-id="770d0-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="770d0-134">**Aktivieren von CORS für Daten-API**</span><span class="sxs-lookup"><span data-stu-id="770d0-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="770d0-135">Das folgende ist ein Auszug aus Daten-API "Web.config", mit zwei Domänen, die in CorsTrustedOrigin Anwendungseinstellungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="770d0-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="770d0-136">Alle Anfragen, die durch die Skripts, die aus diesen Servern geladen werden Daten-API vertraut.</span><span class="sxs-lookup"><span data-stu-id="770d0-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="770d0-137">Denken Sie daran, die genaue Protokoll, Hostname und Port (falls vorhanden).</span><span class="sxs-lookup"><span data-stu-id="770d0-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="770d0-138">Nicht, um zu führen Sie einem Zeichen (/) am Ende Schrägstrich.</span><span class="sxs-lookup"><span data-stu-id="770d0-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="770d0-139">Mehrere Einträge können durch Kommas getrennt angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="770d0-139">Multiple entries can be specified by separating with commas.</span></span>
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


