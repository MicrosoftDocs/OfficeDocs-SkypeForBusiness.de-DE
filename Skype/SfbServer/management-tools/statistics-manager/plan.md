---
title: Plan for Statistics Manager for Skype for Business Server 2015
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
description: 'Zusammenfassung: Lesen Sie in diesem Thema, um Informationen zu Statistiken Manager für Skype für Business Server 2015 zu erfahren.'
ms.openlocfilehash: de4f2bedcbd03191b852366504423ebb031cf5f1
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294479"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server-2015"></a><span data-ttu-id="145b6-103">Plan for Statistics Manager for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="145b6-103">Plan for Statistics Manager for Skype for Business Server 2015</span></span>

<span data-ttu-id="145b6-104">**Zusammenfassung:** Lesen Sie in diesem Thema, um Informationen zu Statistiken Manager für Skype für Business Server 2015 zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="145b6-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server 2015.</span></span>

 <span data-ttu-id="145b6-105">Statistiken-Manager für Skype für Business Server ist ein leistungsfähiges Tool, das Sie zum Anzeigen von Skype für Business Server Integrität und Leistung von Daten in Echtzeit ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="145b6-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="145b6-106">Sie können Leistungsdaten auf Hunderten von Servern kurzen Abständen Abfragen und sofort Anzeigen der Ergebnisse auf der Website Statistiken-Managers.</span><span class="sxs-lookup"><span data-stu-id="145b6-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="145b6-107">Statistiken-Manager können Sie laufende Leistungsprobleme identifizieren, zeigen Sie die Ergebnisse einer geplanten Änderung für Ihre Umgebung, Nachverfolgen von Ausfällen Auflösung und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="145b6-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="145b6-108">Sofort einsetzbar Statistiken Manager wird mit der Key Health Indicator (KHI) Schwellenwerte konfiguriert und eindeutige Bedürfnisse Ihrer Bereitstellung angepasst werden können.</span><span class="sxs-lookup"><span data-stu-id="145b6-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="145b6-109">Sie können Statistiken Manager in einer lokalen Bereitstellung bereitstellen, in denen ein einzelner Server alle serverseitigen Statistiken Manager Komponenten hostet.</span><span class="sxs-lookup"><span data-stu-id="145b6-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="145b6-110">Weitere Informationen zum Bereitstellen von Statistiken-Manager finden Sie unter [Bereitstellen von Statistiken Manager für Skype für Business Server 2015](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="145b6-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server 2015](deploy.md).</span></span> <span data-ttu-id="145b6-111">Wenn Sie bereits über eine vorhandene Bereitstellung von Statistiken Manager verfügen, aber Sie noch nicht, Version 1.1 aktualisiert haben, finden Sie unter [Was ist neu in Version 1.1](plan.md#BKMK_WhatsNew) und [Statistiken-Manager für Skype für Business Server 2015 aktualisieren](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="145b6-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 1.1, see [What's new in Release 1.1](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server 2015](upgrade.md).</span></span>

<span data-ttu-id="145b6-112">Dieses Thema enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="145b6-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="145b6-113">Features und Funktionen</span><span class="sxs-lookup"><span data-stu-id="145b6-113">Features and capabilities</span></span>](https://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Features)

- [<span data-ttu-id="145b6-114">Was ist neu in Version 1.1</span><span class="sxs-lookup"><span data-stu-id="145b6-114">What's new in Release 1.1</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="145b6-115">Komponenten</span><span class="sxs-lookup"><span data-stu-id="145b6-115">Components</span></span>](https://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Components)

- [<span data-ttu-id="145b6-116">Lokale Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="145b6-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="145b6-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="145b6-117">Requirements</span></span>](https://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Requirements)

- [<span data-ttu-id="145b6-118">Hinweise zur Sicherheit</span><span class="sxs-lookup"><span data-stu-id="145b6-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="145b6-119">Features und Funktionen</span><span class="sxs-lookup"><span data-stu-id="145b6-119">Features and capabilities</span></span>
<span data-ttu-id="145b6-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="145b6-120"></span></span>

<span data-ttu-id="145b6-121">Statistiken-Manager können Sie:</span><span class="sxs-lookup"><span data-stu-id="145b6-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="145b6-122">Unformatierte Daten für alle Server in Echtzeit anzeigen.</span><span class="sxs-lookup"><span data-stu-id="145b6-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="145b6-123">(Daten ist eine sehr hohe Fehlerrate bei ermittelt und in weniger als einer Sekunde an die Website gesendet).</span><span class="sxs-lookup"><span data-stu-id="145b6-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="145b6-124">Von Anzeigedaten, die für eine bestimmte Rolle zusammengesetzt wird; beispielsweise Front-End-Server, Vermittlungsserver, Edge-Server und So weiter.</span><span class="sxs-lookup"><span data-stu-id="145b6-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="145b6-125">Nach unten zum Anzeigen von Daten für bestimmte Standorte, bestimmte Pools innerhalb der Website, und klicken Sie dann auf bestimmten Servern innerhalb des Pools der Drilldown erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="145b6-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="145b6-126">Erstellen Sie benutzerdefinierte Diagramme, sodass sich entschieden, dass die Leistungsindikatoren standardmäßig angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="145b6-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="145b6-127">Zoomen und Schwenken auf sowohl die X - und y-Achse oder auf der x-Achse nur.</span><span class="sxs-lookup"><span data-stu-id="145b6-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="145b6-128">Verwenden Sie Datumsbereiche oder Punkt in der Zeit zum Filtern von Daten an.</span><span class="sxs-lookup"><span data-stu-id="145b6-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="145b6-129">Ansicht basierend auf Leistung hergestellt Key Health Indikatoren (KHIs).</span><span class="sxs-lookup"><span data-stu-id="145b6-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="145b6-130">KHIs stellt eine Auflistung von Leistungsindikatoren mit einem fehlerfreien definierten Bereich.</span><span class="sxs-lookup"><span data-stu-id="145b6-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="145b6-131">Zeigen Sie detaillierte Metriken für die einzelnen Indikatoren.</span><span class="sxs-lookup"><span data-stu-id="145b6-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="145b6-132">Vergleichen der Daten in mehrere Auffüllungen oder Server.</span><span class="sxs-lookup"><span data-stu-id="145b6-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="145b6-133">Anzeigen von Berichten latente Leistungsindikator Agents zu identifizieren, die nicht die aktuelle Daten mit dem Dashboard-Dienst reporting sind.</span><span class="sxs-lookup"><span data-stu-id="145b6-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="145b6-134">Speichern Sie eine bestimmte Instanz von Diagrammdaten in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="145b6-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="145b6-135">Ansicht KHIs in Echtzeit, einschließlich Updates.</span><span class="sxs-lookup"><span data-stu-id="145b6-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="145b6-136">Wenn die Ansicht Historie aktiviert ist, werden nur neue Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="145b6-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="145b6-137">Alle KHIs gleichzeitig anzeigen</span><span class="sxs-lookup"><span data-stu-id="145b6-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="145b6-138">Zeigen Sie KHIs an, indem Sie Server (Querformat anzeigen)</span><span class="sxs-lookup"><span data-stu-id="145b6-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="145b6-139">KHI Ansichtsdefinitionen</span><span class="sxs-lookup"><span data-stu-id="145b6-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-11"></a><span data-ttu-id="145b6-140">Was ist neu in Version 1.1</span><span class="sxs-lookup"><span data-stu-id="145b6-140">What's new in Release 1.1</span></span>
<span data-ttu-id="145b6-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="145b6-141"></span></span>

<span data-ttu-id="145b6-142">Im folgenden wird beschrieben, was ist neu in Version 1.1.</span><span class="sxs-lookup"><span data-stu-id="145b6-142">The following describes what's new in Release 1.1.</span></span> <span data-ttu-id="145b6-143">Wenn Sie eine vorhandene Bereitstellung von Statistiken Manager und Sie noch nicht aktualisiert haben, finden Sie unter [Upgrade-Statistiken-Manager für Skype für Business Server 2015](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="145b6-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server 2015](upgrade.md).</span></span>

- <span data-ttu-id="145b6-144">Szenario Ansichten wurden für Edgemedien, Fabric-Zustand, Failover und Registrierung Szenarien hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="145b6-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="145b6-145">Befehlszeile PerfAgentStorageManager.exe (mit dem Listener installiert) können jetzt Leistungsindikatordaten als eine CSV-Datei exportieren.</span><span class="sxs-lookup"><span data-stu-id="145b6-145">Command line PerfAgentStorageManager.exe (installed with the Listener) can now export counter data as a CSV.</span></span>

- <span data-ttu-id="145b6-146">Viele neue Leistungsindikatoren für SQL Server, Windows Fabric-Indikatoren mehr, weitere Skype für Leistungsindikatoren für die Business hinzugefügt wurden und so weiter.</span><span class="sxs-lookup"><span data-stu-id="145b6-146">Many new counters have been added for SQL servers, more Windows Fabric counters, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="145b6-147">Watcher-Knoten-Integration für den Statistiken Manager-Agent - Wenn der Agent, auf einem Watcher-Knoten installiert ist wird synthetische Transaktion Statistiken als Leistungsindikatoren zu Statistiken Manager gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="145b6-147">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="145b6-148">Zahlreiche Verbesserung der Zuverlässigkeit und Leistung.</span><span class="sxs-lookup"><span data-stu-id="145b6-148">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="145b6-149">So überprüfen Sie die Version der Website für die Statistiken Manager ausgeführte:</span><span class="sxs-lookup"><span data-stu-id="145b6-149">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="145b6-150">Öffnen Sie im Datei-Explorer (Standardverzeichnis) C:\Program Files\Skype für Business Server StatsMan WebSite\bin</span><span class="sxs-lookup"><span data-stu-id="145b6-150">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="145b6-151">Klicken Sie mit der rechten Maustaste auf StatsManHubWebSite.dll und zeigen deren Eigenschaften an</span><span class="sxs-lookup"><span data-stu-id="145b6-151">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="145b6-152">Die Produktversion wird unter den Beschreibungsangaben angezeigt.</span><span class="sxs-lookup"><span data-stu-id="145b6-152">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="145b6-153">Komponenten</span><span class="sxs-lookup"><span data-stu-id="145b6-153">Components</span></span>
<span data-ttu-id="145b6-154"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="145b6-154"></span></span>

<span data-ttu-id="145b6-155">Statistiken Manager besteht aus den folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="145b6-155">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="145b6-156">**Agent.**</span><span class="sxs-lookup"><span data-stu-id="145b6-156">**Agent.**</span></span> <span data-ttu-id="145b6-157">Ein lightweight-Agent, der auf jedem überwachten Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="145b6-157">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="145b6-158">Der Agent ermöglicht Abruf von Leistungsindikatoren mit lokalen Aggregation konfigurierbar hohes Maß an.</span><span class="sxs-lookup"><span data-stu-id="145b6-158">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="145b6-159">**Listener.**</span><span class="sxs-lookup"><span data-stu-id="145b6-159">**Listener.**</span></span> <span data-ttu-id="145b6-160">API des Servers, der Daten von allen Agents empfängt und aggregiert Daten über Auffüllungen.</span><span class="sxs-lookup"><span data-stu-id="145b6-160">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="145b6-161">**Hub.**</span><span class="sxs-lookup"><span data-stu-id="145b6-161">**Hub.**</span></span> <span data-ttu-id="145b6-162">Bildet die Client-API für das System, auf den Web-Servern ausgeführt wird, und bietet Echtzeitdaten-Updates für Clients, die über die Website verbunden.</span><span class="sxs-lookup"><span data-stu-id="145b6-162">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="145b6-163">(Der Hub wird automatisch als Teil der Website MSI-Datei installiert).</span><span class="sxs-lookup"><span data-stu-id="145b6-163">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="145b6-164">**Website.**</span><span class="sxs-lookup"><span data-stu-id="145b6-164">**Website.**</span></span> <span data-ttu-id="145b6-165">Eine Benutzeroberfläche, die allen im System verfügbaren Features zusammen abruft.</span><span class="sxs-lookup"><span data-stu-id="145b6-165">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="145b6-166">Darüber hinaus erfordert Statistiken Manager **Redis**, einem Öffnen einer Führungslinie basieren Daten Struktur Server für das Zwischenspeichern im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="145b6-166">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="145b6-167">Weitere Informationen zum Herunterladen von Redis finden Sie unter [Bereitstellen von Statistiken Manager](deploy.md#BKMK_Deploy) .</span><span class="sxs-lookup"><span data-stu-id="145b6-167">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="145b6-168">Lokale Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="145b6-168">On-premises deployment</span></span>
<span data-ttu-id="145b6-169"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="145b6-169"></span></span>

<span data-ttu-id="145b6-170">In einer lokalen Bereitstellung hostet ein einzelnes Servers alle Statistiken Manager serverseitige Komponenten.</span><span class="sxs-lookup"><span data-stu-id="145b6-170">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="145b6-171">Das folgende Diagramm zeigt eine lokale Bereitstellung, in der die Statistiken-Manager-Website, Hub, Listener und Redis Zwischenspeichern System auf einem einzigen Computer gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="145b6-171">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="145b6-172">Statistiken Manager überwacht drei Skype für Unternehmensserver, von denen jedes einen einzelnen Agent übertragen von Daten an den Listener haben.</span><span class="sxs-lookup"><span data-stu-id="145b6-172">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="145b6-173">Benutzer Verbinden mit einer einzelnen Website alle vom Statistiken Manager aggregierte Daten anzeigen:</span><span class="sxs-lookup"><span data-stu-id="145b6-173">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![Stats Manager – lokale Bereitstellung](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="145b6-175">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="145b6-175">Requirements</span></span>
<span data-ttu-id="145b6-176"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="145b6-176"></span></span>

<span data-ttu-id="145b6-177">Sie müssen die folgenden Anforderungen Software, Netzwerk und Hardware berücksichtigen Sie vor der Bereitstellung von Statistiken-Manager.</span><span class="sxs-lookup"><span data-stu-id="145b6-177">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="145b6-178">Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="145b6-178">Software requirements</span></span>

- <span data-ttu-id="145b6-179">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="145b6-179">Windows Server 2012 R2</span></span>

- <span data-ttu-id="145b6-180">IIS (automatisch installiert)</span><span class="sxs-lookup"><span data-stu-id="145b6-180">IIS (automatically installed)</span></span>

- <span data-ttu-id="145b6-181">Redis</span><span class="sxs-lookup"><span data-stu-id="145b6-181">Redis</span></span>

- <span data-ttu-id="145b6-182">Statistiken-Manager-Dienste (automatisch installiert)</span><span class="sxs-lookup"><span data-stu-id="145b6-182">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="145b6-183">PSExec - remote-Agent-Bereitstellung Aktionen erforderlich</span><span class="sxs-lookup"><span data-stu-id="145b6-183">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="145b6-184">.NET 4.5 (mit 2012 R2 enthalten) – erforderlich für serverseitige Komponenten</span><span class="sxs-lookup"><span data-stu-id="145b6-184">.NET 4.5 (included with 2012 R2) - Required for server-side components</span></span>

- <span data-ttu-id="145b6-185">.NET 4.0 - für Agents erforderlich</span><span class="sxs-lookup"><span data-stu-id="145b6-185">.NET 4.0 - Required for agents</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="145b6-186">Netzwerkanforderungen</span><span class="sxs-lookup"><span data-stu-id="145b6-186">Networking requirements</span></span>


|<span data-ttu-id="145b6-187">**Hosting-server**</span><span class="sxs-lookup"><span data-stu-id="145b6-187">**Hosting server**</span></span>|<span data-ttu-id="145b6-188">**Agents**</span><span class="sxs-lookup"><span data-stu-id="145b6-188">**Agents**</span></span>|<span data-ttu-id="145b6-189">**Listener**</span><span class="sxs-lookup"><span data-stu-id="145b6-189">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="145b6-190">Minimale Gigabit Vollduplex Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="145b6-190">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="145b6-191">Ausgehende TCP-Port 8443 (anpassbar Portnummer) mit dem Listener kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="145b6-191">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="145b6-192">Der Überwachungsport muss auf allen Servern identisch sein.</span><span class="sxs-lookup"><span data-stu-id="145b6-192">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="145b6-193">Eingehende TCP-Port 80 oder 443 geöffnet, auf die Website zu hosten.</span><span class="sxs-lookup"><span data-stu-id="145b6-193">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="145b6-194">Eingehende TCP-Port 8443 (anpassbar Portnummer) für die Agents Daten mit ihm austauschen.</span><span class="sxs-lookup"><span data-stu-id="145b6-194">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="145b6-195">Während der Installation werden Firewallports für den Listener und die Website automatisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="145b6-195">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="145b6-196">Für die Agents wird die Installation davon ausgegangen, dass ausgehende TCP-Verbindungen standardmäßig zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="145b6-196">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="145b6-197">Hardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="145b6-197">Hardware requirements</span></span>

<span data-ttu-id="145b6-198">In einer lokalen Bereitstellung, in dem ein einzelner Server gehostet alle Statistiken Manager serverseitige Komponenten eines Servers mit 16 GB RAM und 4 wird CPU sollte in der Lage, durchschnittlich etwa 150 Samples pro Sekunde unterstützen.</span><span class="sxs-lookup"><span data-stu-id="145b6-198">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="145b6-199">Um festzustellen, wie viele Leistungsindikatoren-Agents unterstützt werden können, verwenden Sie die folgende Berechnung aus:</span><span class="sxs-lookup"><span data-stu-id="145b6-199">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="145b6-200">100 Server \*80 Leistungsindikatoren \* 1 Beispiel pro Minute pro Agent / 60 Sekunden = ~ 133 Samples pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="145b6-200">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="145b6-201">Hinweise zur Sicherheit</span><span class="sxs-lookup"><span data-stu-id="145b6-201">Security considerations</span></span>
<span data-ttu-id="145b6-202"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="145b6-202"></span></span>

<span data-ttu-id="145b6-203">Der gesamte Datenverkehr zwischen Servern wird verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="145b6-203">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="145b6-204">Verschlüsselten HTTPS-Datenverkehr wird über Port 8443 (standardmäßig) vom Agent an den Listener Server gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="145b6-204">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="145b6-205">Der Agent prüft den Fingerabdruck des SSL auf dem Server, um sicherzustellen, dass der Server Listener der erwarteten Empfänger ist.</span><span class="sxs-lookup"><span data-stu-id="145b6-205">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="145b6-206">Beachten Sie, dass der Agent bei Zertifikaten die Fingerabdruck-Verifizierung verwendet (anstatt der Kettenverifizierung).</span><span class="sxs-lookup"><span data-stu-id="145b6-206">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="145b6-207">Er führt keine vollständige Verifizierung von Zertifikaten durch, weil es möglich ist, selbstsignierte Zertifikate zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="145b6-207">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="145b6-208">Nachdem der Agent einverstanden ist der Listener authentisch ist, ein Kennwort wird vom Agent, die dann vom Listener überprüft wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="145b6-208">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="145b6-209">Der Agent beginnt Leistungsdaten über die Verbindung an den Listener übertragen.</span><span class="sxs-lookup"><span data-stu-id="145b6-209">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="145b6-210">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="145b6-210">For more information</span></span>
<span data-ttu-id="145b6-211"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="145b6-211"></span></span>

<span data-ttu-id="145b6-212">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="145b6-212">For more information, see the following:</span></span>

- [<span data-ttu-id="145b6-213">Deploy Statistics Manager for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="145b6-213">Deploy Statistics Manager for Skype for Business Server 2015</span></span>](deploy.md)

- [<span data-ttu-id="145b6-214">Upgrade Statistics Manager for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="145b6-214">Upgrade Statistics Manager for Skype for Business Server 2015</span></span>](upgrade.md)

- [<span data-ttu-id="145b6-215">Troubleshoot Statistics Manager for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="145b6-215">Troubleshoot Statistics Manager for Skype for Business Server 2015</span></span>](troubleshoot.md)

- [<span data-ttu-id="145b6-216">Blog zu Statistics Manager für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="145b6-216">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/skypestatsman/)


