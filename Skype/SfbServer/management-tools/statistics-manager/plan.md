---
title: Planen der Business Server für den Statistiken-Manager für Skype
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 5/23/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Zusammenfassung: Lesen Sie in diesem Thema, um Informationen zu Statistiken Manager für Skype für Business Server zu erfahren.'
ms.openlocfilehash: a7cd9fd3dd3eff7f1c9b0326d45475f95f9a909c
ms.sourcegitcommit: 8a6bf02958436fcdeed336f09079bd3827e2fccb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2018
ms.locfileid: "26283201"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="69f7c-103">Planen der Business Server für den Statistiken-Manager für Skype</span><span class="sxs-lookup"><span data-stu-id="69f7c-103">Plan for Statistics Manager for Skype for Business Server</span></span>

<span data-ttu-id="69f7c-104">**Zusammenfassung:** Lesen Sie in diesem Thema, um Informationen zu Statistiken Manager für Skype für Business Server zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="69f7c-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server.</span></span>

 <span data-ttu-id="69f7c-105">Statistiken-Manager für Skype für Business Server ist ein leistungsfähiges Tool, das Sie zum Anzeigen von Skype für Business Server Integrität und Leistung von Daten in Echtzeit ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="69f7c-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="69f7c-106">Sie können Leistungsdaten auf Hunderten von Servern kurzen Abständen Abfragen und sofort Anzeigen der Ergebnisse auf der Website Statistiken-Managers.</span><span class="sxs-lookup"><span data-stu-id="69f7c-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="69f7c-107">Statistiken-Manager können Sie laufende Leistungsprobleme identifizieren, zeigen Sie die Ergebnisse einer geplanten Änderung für Ihre Umgebung, Nachverfolgen von Ausfällen Auflösung und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="69f7c-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="69f7c-108">Sofort einsetzbar Statistiken Manager wird mit der Key Health Indicator (KHI) Schwellenwerte konfiguriert und eindeutige Bedürfnisse Ihrer Bereitstellung angepasst werden können.</span><span class="sxs-lookup"><span data-stu-id="69f7c-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="69f7c-109">Sie können Statistiken Manager in einer lokalen Bereitstellung bereitstellen, in denen ein einzelner Server alle serverseitigen Statistiken Manager Komponenten hostet.</span><span class="sxs-lookup"><span data-stu-id="69f7c-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="69f7c-110">Weitere Informationen zum Bereitstellen von Statistiken-Manager finden Sie unter [Bereitstellen von Statistiken Manager für Skype für Business Server](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="69f7c-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span> <span data-ttu-id="69f7c-111">Wenn Sie bereits über eine vorhandene Bereitstellung von Statistiken Manager verfügen, aber Sie noch nicht, Version 2.0 aktualisiert haben, finden Sie unter [Was ist neu in der Version 2.0](plan.md#BKMK_WhatsNew) und [Statistiken-Manager für Skype für Business Server aktualisieren](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="69f7c-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

<span data-ttu-id="69f7c-112">Dieses Thema enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="69f7c-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="69f7c-113">Features und Funktionen</span><span class="sxs-lookup"><span data-stu-id="69f7c-113">Features and capabilities</span></span>](https://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Features)

- [<span data-ttu-id="69f7c-114">Was ist neu in der Version 2.0</span><span class="sxs-lookup"><span data-stu-id="69f7c-114">What's new in Release 2.0</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="69f7c-115">Komponenten</span><span class="sxs-lookup"><span data-stu-id="69f7c-115">Components</span></span>](https://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Components)

- [<span data-ttu-id="69f7c-116">Lokale Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="69f7c-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="69f7c-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="69f7c-117">Requirements</span></span>](https://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Requirements)

- [<span data-ttu-id="69f7c-118">Hinweise zur Sicherheit</span><span class="sxs-lookup"><span data-stu-id="69f7c-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="69f7c-119">Features und Funktionen</span><span class="sxs-lookup"><span data-stu-id="69f7c-119">Features and capabilities</span></span>
<span data-ttu-id="69f7c-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="69f7c-120"></span></span>

<span data-ttu-id="69f7c-121">Statistiken-Manager können Sie:</span><span class="sxs-lookup"><span data-stu-id="69f7c-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="69f7c-122">Unformatierte Daten für alle Server in Echtzeit anzeigen.</span><span class="sxs-lookup"><span data-stu-id="69f7c-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="69f7c-123">(Daten ist eine sehr hohe Fehlerrate bei ermittelt und in weniger als einer Sekunde an die Website gesendet).</span><span class="sxs-lookup"><span data-stu-id="69f7c-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="69f7c-124">Von Anzeigedaten, die für eine bestimmte Rolle zusammengesetzt wird; beispielsweise Front-End-Server, Vermittlungsserver, Edge-Server und So weiter.</span><span class="sxs-lookup"><span data-stu-id="69f7c-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="69f7c-125">Nach unten zum Anzeigen von Daten für bestimmte Standorte, bestimmte Pools innerhalb der Website, und klicken Sie dann auf bestimmten Servern innerhalb des Pools der Drilldown erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="69f7c-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="69f7c-126">Erstellen Sie benutzerdefinierte Diagramme, sodass sich entschieden, dass die Leistungsindikatoren standardmäßig angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="69f7c-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="69f7c-127">Zoomen und Schwenken auf sowohl die X - und y-Achse oder auf der x-Achse nur.</span><span class="sxs-lookup"><span data-stu-id="69f7c-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="69f7c-128">Verwenden Sie Datumsbereiche oder Punkt in der Zeit zum Filtern von Daten an.</span><span class="sxs-lookup"><span data-stu-id="69f7c-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="69f7c-129">Ansicht basierend auf Leistung hergestellt Key Health Indikatoren (KHIs).</span><span class="sxs-lookup"><span data-stu-id="69f7c-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="69f7c-130">KHIs stellt eine Auflistung von Leistungsindikatoren mit einem fehlerfreien definierten Bereich.</span><span class="sxs-lookup"><span data-stu-id="69f7c-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="69f7c-131">Zeigen Sie detaillierte Metriken für die einzelnen Indikatoren.</span><span class="sxs-lookup"><span data-stu-id="69f7c-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="69f7c-132">Vergleichen der Daten in mehrere Auffüllungen oder Server.</span><span class="sxs-lookup"><span data-stu-id="69f7c-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="69f7c-133">Anzeigen von Berichten latente Leistungsindikator Agents zu identifizieren, die nicht die aktuelle Daten mit dem Dashboard-Dienst reporting sind.</span><span class="sxs-lookup"><span data-stu-id="69f7c-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="69f7c-134">Speichern Sie eine bestimmte Instanz von Diagrammdaten in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="69f7c-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="69f7c-135">Ansicht KHIs in Echtzeit, einschließlich Updates.</span><span class="sxs-lookup"><span data-stu-id="69f7c-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="69f7c-136">Wenn die Ansicht Historie aktiviert ist, werden nur neue Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69f7c-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="69f7c-137">Alle KHIs gleichzeitig anzeigen</span><span class="sxs-lookup"><span data-stu-id="69f7c-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="69f7c-138">Zeigen Sie KHIs an, indem Sie Server (Querformat anzeigen)</span><span class="sxs-lookup"><span data-stu-id="69f7c-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="69f7c-139">KHI Ansichtsdefinitionen</span><span class="sxs-lookup"><span data-stu-id="69f7c-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-20"></a><span data-ttu-id="69f7c-140">Was ist neu in der Version 2.0</span><span class="sxs-lookup"><span data-stu-id="69f7c-140">What's new in Release 2.0</span></span>
<span data-ttu-id="69f7c-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="69f7c-141"></span></span>

<span data-ttu-id="69f7c-142">Im folgenden wird beschrieben, was ist neu in der Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="69f7c-142">The following describes what's new in Release 2.0.</span></span> <span data-ttu-id="69f7c-143">Wenn Sie eine vorhandene Bereitstellung von Statistiken Manager und Sie noch nicht aktualisiert haben, finden Sie unter [Statistics-Manager für Skype für Business Server aktualisieren](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="69f7c-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

- <span data-ttu-id="69f7c-144">Szenario Ansichten wurden für Edgemedien, Fabric-Zustand, Failover und Registrierung Szenarien hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="69f7c-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="69f7c-145">Viele neue Leistungsindikatoren für SQL Server, weitere Skype für Leistungsindikatoren für die Business hinzugefügt wurden und so weiter.</span><span class="sxs-lookup"><span data-stu-id="69f7c-145">Many new counters have been added for SQL servers, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="69f7c-146">Watcher-Knoten-Integration für den Statistiken Manager-Agent - Wenn der Agent, auf einem Watcher-Knoten installiert ist wird synthetische Transaktion Statistiken als Leistungsindikatoren zu Statistiken Manager gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="69f7c-146">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="69f7c-147">Zahlreiche Verbesserung der Zuverlässigkeit und Leistung.</span><span class="sxs-lookup"><span data-stu-id="69f7c-147">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="69f7c-148">So überprüfen Sie die Version der Website für die Statistiken Manager ausgeführte:</span><span class="sxs-lookup"><span data-stu-id="69f7c-148">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="69f7c-149">Öffnen Sie im Datei-Explorer (Standardverzeichnis) C:\Program Files\Skype für Business Server StatsMan WebSite\bin</span><span class="sxs-lookup"><span data-stu-id="69f7c-149">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="69f7c-150">Klicken Sie mit der rechten Maustaste auf StatsManHubWebSite.dll und zeigen deren Eigenschaften an</span><span class="sxs-lookup"><span data-stu-id="69f7c-150">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="69f7c-151">Die Produktversion wird unter den Beschreibungsangaben angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69f7c-151">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="69f7c-152">Komponenten</span><span class="sxs-lookup"><span data-stu-id="69f7c-152">Components</span></span>
<span data-ttu-id="69f7c-153"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="69f7c-153"></span></span>

<span data-ttu-id="69f7c-154">Statistiken Manager besteht aus den folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="69f7c-154">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="69f7c-155">**Agent.**</span><span class="sxs-lookup"><span data-stu-id="69f7c-155">**Agent.**</span></span> <span data-ttu-id="69f7c-156">Ein lightweight-Agent, der auf jedem überwachten Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="69f7c-156">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="69f7c-157">Der Agent ermöglicht Abruf von Leistungsindikatoren mit lokalen Aggregation konfigurierbar hohes Maß an.</span><span class="sxs-lookup"><span data-stu-id="69f7c-157">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="69f7c-158">**Listener.**</span><span class="sxs-lookup"><span data-stu-id="69f7c-158">**Listener.**</span></span> <span data-ttu-id="69f7c-159">API des Servers, der Daten von allen Agents empfängt und aggregiert Daten über Auffüllungen.</span><span class="sxs-lookup"><span data-stu-id="69f7c-159">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="69f7c-160">**Hub.**</span><span class="sxs-lookup"><span data-stu-id="69f7c-160">**Hub.**</span></span> <span data-ttu-id="69f7c-161">Bildet die Client-API für das System, auf den Web-Servern ausgeführt wird, und bietet Echtzeitdaten-Updates für Clients, die über die Website verbunden.</span><span class="sxs-lookup"><span data-stu-id="69f7c-161">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="69f7c-162">(Der Hub wird automatisch als Teil der Website MSI-Datei installiert).</span><span class="sxs-lookup"><span data-stu-id="69f7c-162">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="69f7c-163">**Website.**</span><span class="sxs-lookup"><span data-stu-id="69f7c-163">**Website.**</span></span> <span data-ttu-id="69f7c-164">Eine Benutzeroberfläche, die allen im System verfügbaren Features zusammen abruft.</span><span class="sxs-lookup"><span data-stu-id="69f7c-164">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="69f7c-165">Darüber hinaus erfordert Statistiken Manager **Redis**, einem Öffnen einer Führungslinie basieren Daten Struktur Server für das Zwischenspeichern im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="69f7c-165">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="69f7c-166">Weitere Informationen zum Herunterladen von Redis finden Sie unter [Bereitstellen von Statistiken Manager](deploy.md#BKMK_Deploy) .</span><span class="sxs-lookup"><span data-stu-id="69f7c-166">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="69f7c-167">Lokale Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="69f7c-167">On-premises deployment</span></span>
<span data-ttu-id="69f7c-168"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="69f7c-168"></span></span>

<span data-ttu-id="69f7c-169">In einer lokalen Bereitstellung hostet ein einzelnes Servers alle Statistiken Manager serverseitige Komponenten.</span><span class="sxs-lookup"><span data-stu-id="69f7c-169">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="69f7c-170">Das folgende Diagramm zeigt eine lokale Bereitstellung, in der die Statistiken-Manager-Website, Hub, Listener und Redis Zwischenspeichern System auf einem einzigen Computer gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="69f7c-170">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="69f7c-171">Statistiken Manager überwacht drei Skype für Unternehmensserver, von denen jedes einen einzelnen Agent übertragen von Daten an den Listener haben.</span><span class="sxs-lookup"><span data-stu-id="69f7c-171">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="69f7c-172">Benutzer Verbinden mit einer einzelnen Website alle vom Statistiken Manager aggregierte Daten anzeigen:</span><span class="sxs-lookup"><span data-stu-id="69f7c-172">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![Stats Manager – lokale Bereitstellung](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="69f7c-174">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="69f7c-174">Requirements</span></span>
<span data-ttu-id="69f7c-175"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="69f7c-175"></span></span>

<span data-ttu-id="69f7c-176">Sie müssen die folgenden Anforderungen Software, Netzwerk und Hardware berücksichtigen Sie vor der Bereitstellung von Statistiken-Manager.</span><span class="sxs-lookup"><span data-stu-id="69f7c-176">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="69f7c-177">Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="69f7c-177">Software requirements</span></span>

- <span data-ttu-id="69f7c-178">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="69f7c-178">Windows Server 2012 R2</span></span>

- <span data-ttu-id="69f7c-179">IIS (automatisch installiert)</span><span class="sxs-lookup"><span data-stu-id="69f7c-179">IIS (automatically installed)</span></span>

- <span data-ttu-id="69f7c-180">Redis</span><span class="sxs-lookup"><span data-stu-id="69f7c-180">Redis</span></span>

- <span data-ttu-id="69f7c-181">Statistiken-Manager-Dienste (automatisch installiert)</span><span class="sxs-lookup"><span data-stu-id="69f7c-181">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="69f7c-182">PSExec - remote-Agent-Bereitstellung Aktionen erforderlich</span><span class="sxs-lookup"><span data-stu-id="69f7c-182">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="69f7c-183">.NET 4.5 (mit 2012 R2 enthalten) - Agents und serverseitige Komponenten erforderlich</span><span class="sxs-lookup"><span data-stu-id="69f7c-183">.NET 4.5 (included with 2012 R2) - Required for agents and server-side components</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="69f7c-184">Netzwerkanforderungen</span><span class="sxs-lookup"><span data-stu-id="69f7c-184">Networking requirements</span></span>


|<span data-ttu-id="69f7c-185">**Hosting-server**</span><span class="sxs-lookup"><span data-stu-id="69f7c-185">**Hosting server**</span></span>|<span data-ttu-id="69f7c-186">**Agents**</span><span class="sxs-lookup"><span data-stu-id="69f7c-186">**Agents**</span></span>|<span data-ttu-id="69f7c-187">**Listener**</span><span class="sxs-lookup"><span data-stu-id="69f7c-187">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="69f7c-188">Minimale Gigabit Vollduplex Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="69f7c-188">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="69f7c-189">Ausgehende TCP-Port 8443 (anpassbar Portnummer) mit dem Listener kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="69f7c-189">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="69f7c-190">Der Überwachungsport muss auf allen Servern identisch sein.</span><span class="sxs-lookup"><span data-stu-id="69f7c-190">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="69f7c-191">Eingehende TCP-Port 80 oder 443 geöffnet, auf die Website zu hosten.</span><span class="sxs-lookup"><span data-stu-id="69f7c-191">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="69f7c-192">Eingehende TCP-Port 8443 (anpassbar Portnummer) für die Agents Daten mit ihm austauschen.</span><span class="sxs-lookup"><span data-stu-id="69f7c-192">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="69f7c-193">Während der Installation werden Firewallports für den Listener und die Website automatisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="69f7c-193">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="69f7c-194">Für die Agents wird die Installation davon ausgegangen, dass ausgehende TCP-Verbindungen standardmäßig zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="69f7c-194">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="69f7c-195">Hardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="69f7c-195">Hardware requirements</span></span>

<span data-ttu-id="69f7c-196">In einer lokalen Bereitstellung, in dem ein einzelner Server gehostet alle Statistiken Manager serverseitige Komponenten eines Servers mit 16 GB RAM und 4 wird CPU sollte in der Lage, durchschnittlich etwa 150 Samples pro Sekunde unterstützen.</span><span class="sxs-lookup"><span data-stu-id="69f7c-196">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="69f7c-197">Um festzustellen, wie viele Leistungsindikatoren-Agents unterstützt werden können, verwenden Sie die folgende Berechnung aus:</span><span class="sxs-lookup"><span data-stu-id="69f7c-197">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="69f7c-198">100 Server \*80 Leistungsindikatoren \* 1 Beispiel pro Minute pro Agent / 60 Sekunden = ~ 133 Samples pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="69f7c-198">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="69f7c-199">Hinweise zur Sicherheit</span><span class="sxs-lookup"><span data-stu-id="69f7c-199">Security considerations</span></span>
<span data-ttu-id="69f7c-200"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="69f7c-200"></span></span>

<span data-ttu-id="69f7c-201">Der gesamte Datenverkehr zwischen Servern wird verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="69f7c-201">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="69f7c-202">Verschlüsselten HTTPS-Datenverkehr wird über Port 8443 (standardmäßig) vom Agent an den Listener Server gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="69f7c-202">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="69f7c-203">Der Agent prüft den Fingerabdruck des SSL auf dem Server, um sicherzustellen, dass der Server Listener der erwarteten Empfänger ist.</span><span class="sxs-lookup"><span data-stu-id="69f7c-203">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="69f7c-204">Beachten Sie, dass der Agent bei Zertifikaten die Fingerabdruck-Verifizierung verwendet (anstatt der Kettenverifizierung).</span><span class="sxs-lookup"><span data-stu-id="69f7c-204">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="69f7c-205">Er führt keine vollständige Verifizierung von Zertifikaten durch, weil es möglich ist, selbstsignierte Zertifikate zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="69f7c-205">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="69f7c-206">Nachdem der Agent einverstanden ist der Listener authentisch ist, ein Kennwort wird vom Agent, die dann vom Listener überprüft wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69f7c-206">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="69f7c-207">Der Agent beginnt Leistungsdaten über die Verbindung an den Listener übertragen.</span><span class="sxs-lookup"><span data-stu-id="69f7c-207">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="69f7c-208">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="69f7c-208">For more information</span></span>
<span data-ttu-id="69f7c-209"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="69f7c-209"></span></span>

<span data-ttu-id="69f7c-210">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="69f7c-210">For more information, see the following:</span></span>

- [<span data-ttu-id="69f7c-211">Bereitstellen von Statistiken Manager für Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="69f7c-211">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)

- [<span data-ttu-id="69f7c-212">Aktualisieren von Statistiken Manager für Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="69f7c-212">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)

- [<span data-ttu-id="69f7c-213">Problembehandlung bei Statistiken Manager für Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="69f7c-213">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)

- [<span data-ttu-id="69f7c-214">Skype for Business Server Statistics Manager-Blog</span><span class="sxs-lookup"><span data-stu-id="69f7c-214">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/skypestatsman/)


