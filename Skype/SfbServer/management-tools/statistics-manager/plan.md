---
title: Planen von Statistics Manager für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Zusammenfassung: Lesen Sie dieses Thema, um mehr über den Statistik-Manager für Skype for Business Server zu erfahren.'
ms.openlocfilehash: a58ca8ea8ed2d612e00a0705bb28e8d6fe95eb45
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299737"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="9e141-103">Planen von Statistics Manager für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9e141-103">Plan for Statistics Manager for Skype for Business Server</span></span>

<span data-ttu-id="9e141-104">**Zusammenfassung:** In diesem Thema finden Sie Informationen zu Statistics Manager für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9e141-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server.</span></span>

 <span data-ttu-id="9e141-105">Statistics Manager für Skype for Business Server ist ein leistungsfähiges Tool, mit dem Sie Skype for Business Server-Status- und -Leistungsdaten in Echtzeit anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="9e141-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="9e141-106">Sie können Leistungsdaten von Hunderten von Servern innerhalb von Sekunden abfragen und die Ergebnisse unmittelbar auf der Statistics Manager-Website anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9e141-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="9e141-107">Sie können den Statistik-Manager verwenden, um fortlaufende Leistungsprobleme zu erkennen, die Ergebnisse einer geplanten Änderung Ihrer Umgebung anzuzeigen, die Auflösung von Ausfällen zu überwachen und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="9e141-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="9e141-108">Der Statistik-Manager ist mit KHI-Schwellenwerten (Key Health Indicator) konfiguriert und kann an die individuellen Anforderungen Ihrer Bereitstellung angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="9e141-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="9e141-109">Sie können den Statistik-Manager in einer lokalen Bereitstellung bereitstellen, auf der ein einzelner Server alle serverseitigen Statistics Manager-Komponenten hostet.</span><span class="sxs-lookup"><span data-stu-id="9e141-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="9e141-110">Weitere Informationen zum Bereitstellen des Statistik-Managers finden Sie unter [Bereitstellen des Statistik-Managers für Skype for Business Server](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="9e141-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span> <span data-ttu-id="9e141-111">Wenn Sie bereits über eine vorhandene Bereitstellung von Statistik-Manager verfügen, aber noch nicht auf Release 2,0 aktualisiert haben, lesen Sie [Neuerungen in Release 2,0](plan.md#BKMK_WhatsNew) und [Upgrade Statistics Manager für Skype for Business Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="9e141-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

<span data-ttu-id="9e141-112">Dieses Thema enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="9e141-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="9e141-113">Features und Funktionen</span><span class="sxs-lookup"><span data-stu-id="9e141-113">Features and capabilities</span></span>](plan.md#BKMK_Features)

- [<span data-ttu-id="9e141-114">Neuerungen in Version 2,0</span><span class="sxs-lookup"><span data-stu-id="9e141-114">What's new in Release 2.0</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="9e141-115">Komponenten</span><span class="sxs-lookup"><span data-stu-id="9e141-115">Components</span></span>](plan.md#BKMK_Components)

- [<span data-ttu-id="9e141-116">Lokale Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="9e141-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="9e141-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9e141-117">Requirements</span></span>](plan.md#BKMK_Requirements)

- [<span data-ttu-id="9e141-118">Sicherheitsüberlegungen</span><span class="sxs-lookup"><span data-stu-id="9e141-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="9e141-119">Features und Funktionen</span><span class="sxs-lookup"><span data-stu-id="9e141-119">Features and capabilities</span></span>
<span data-ttu-id="9e141-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="9e141-120"></span></span>

<span data-ttu-id="9e141-121">Mit Statistik-Manager können Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="9e141-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="9e141-122">Anzeigen unformatierter Daten für alle Server in Echtzeit.</span><span class="sxs-lookup"><span data-stu-id="9e141-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="9e141-123">(Die Daten werden zu einem sehr günstigen Preis abgetastet und in weniger als einer Sekunde an die Website gesendet.)</span><span class="sxs-lookup"><span data-stu-id="9e141-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="9e141-124">Anzeigen von Daten, die für eine bestimmte Rolle aggregiert sind Beispiel: Front-End-Server, Vermittlungsserver, Edgeserver usw.</span><span class="sxs-lookup"><span data-stu-id="9e141-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="9e141-125">Führen Sie einen Drilldown aus, um Daten für bestimmte Websites, bestimmte Pools innerhalb der Website und dann bestimmte Server im Pool anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9e141-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="9e141-126">Erstellen Sie benutzerdefinierte Diagramme, damit ausgewählte Leistungsindikatoren standardmäßig angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9e141-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="9e141-127">Zoomen und Schwenken Sie auf der x-und y-Achse oder nur auf der x-Achse.</span><span class="sxs-lookup"><span data-stu-id="9e141-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="9e141-128">Verwenden Sie Datumsbereiche oder Zeitpunkte zum Filtern von Daten.</span><span class="sxs-lookup"><span data-stu-id="9e141-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="9e141-129">Zeigen Sie die Serverleistung basierend auf den festgelegten Schlüssel Integritätsindikatoren (KHIs) an.</span><span class="sxs-lookup"><span data-stu-id="9e141-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="9e141-130">KHIs stellen eine Sammlung von Leistungsindikatoren mit einem definierten, gesunden Bereich dar.</span><span class="sxs-lookup"><span data-stu-id="9e141-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="9e141-131">Anzeigen detaillierter Metriken für jeden Leistungsindikator</span><span class="sxs-lookup"><span data-stu-id="9e141-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="9e141-132">Vergleichen Sie Daten auf mehreren Populationen oder Servern.</span><span class="sxs-lookup"><span data-stu-id="9e141-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="9e141-133">Zeigen Sie latente Indikator Berichte an, um Agents zu identifizieren, die keine aktuellen Daten an den dashboarddienst melden.</span><span class="sxs-lookup"><span data-stu-id="9e141-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="9e141-134">Speichern Sie eine bestimmte Instanz von Diagrammdaten in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="9e141-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="9e141-135">Anzeigen von KHIs in Echtzeit, einschließlich Updates.</span><span class="sxs-lookup"><span data-stu-id="9e141-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="9e141-136">Wenn die Verlaufsansicht aktiviert ist, werden nur neue Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9e141-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="9e141-137">Alle KHIs gleichzeitig anzeigen</span><span class="sxs-lookup"><span data-stu-id="9e141-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="9e141-138">Anzeigen von KHIs nach Server (Landschaftsansicht)</span><span class="sxs-lookup"><span data-stu-id="9e141-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="9e141-139">Anzeigen von KHI-Definitionen</span><span class="sxs-lookup"><span data-stu-id="9e141-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-20"></a><span data-ttu-id="9e141-140">Neuerungen in Version 2,0</span><span class="sxs-lookup"><span data-stu-id="9e141-140">What's new in Release 2.0</span></span>
<span data-ttu-id="9e141-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="9e141-141"></span></span>

<span data-ttu-id="9e141-142">Im folgenden wird beschrieben, welche Neuerungen es in Version 2,0 gibt.</span><span class="sxs-lookup"><span data-stu-id="9e141-142">The following describes what's new in Release 2.0.</span></span> <span data-ttu-id="9e141-143">Wenn Sie über eine vorhandene Bereitstellung von Statistics Manager verfügen und noch kein Upgrade durchgeführt haben, lesen Sie [Upgrade Statistics Manager für Skype for Business Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="9e141-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

- <span data-ttu-id="9e141-144">Szenario-Ansichten wurden für Edge-Medien, Fabric-Integrität, Pool-Failover und Registrierungs Szenarien hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9e141-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="9e141-145">Viele neue Zähler wurden für SQL-Server, weitere Skype for Business-Nutzungszähler usw. hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9e141-145">Many new counters have been added for SQL servers, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="9e141-146">Watcher-Knoten Integration für den Statistik-Manager-Agent – Wenn der Agent auf einem Watcher-Knoten installiert ist, werden synthetische Transaktionsstatistiken als Leistungsindikatoren zurück zum Statistik-Manager gemeldet.</span><span class="sxs-lookup"><span data-stu-id="9e141-146">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="9e141-147">Zahlreiche Verbesserungen bei Zuverlässigkeit und Leistung.</span><span class="sxs-lookup"><span data-stu-id="9e141-147">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="9e141-148">So überprüfen Sie die Version der von Ihnen ausgeführten Statistics Manager-Website:</span><span class="sxs-lookup"><span data-stu-id="9e141-148">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="9e141-149">Öffnen Sie im Datei-Explorer (Standardverzeichnis) C:\Program Files\Skype for Business Server-Statistiker WebSite\bin</span><span class="sxs-lookup"><span data-stu-id="9e141-149">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="9e141-150">Klicken Sie mit der rechten Maustaste auf StatsManHubWebSite. dll, und zeigen Sie deren Eigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="9e141-150">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="9e141-151">Die Produktversion wird unter den Beschreibungsangaben angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9e141-151">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="9e141-152">Komponenten</span><span class="sxs-lookup"><span data-stu-id="9e141-152">Components</span></span>
<span data-ttu-id="9e141-153"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="9e141-153"></span></span>

<span data-ttu-id="9e141-154">Der Statistik-Manager besteht aus den folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="9e141-154">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="9e141-155">**Agent.**</span><span class="sxs-lookup"><span data-stu-id="9e141-155">**Agent.**</span></span> <span data-ttu-id="9e141-156">Ein Lightweight-Agent, der auf jedem überwachten Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9e141-156">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="9e141-157">Der Agent ermöglicht die konfigurierbare hochfrequente Abfrage von Leistungsindikatoren mit lokaler Aggregation.</span><span class="sxs-lookup"><span data-stu-id="9e141-157">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="9e141-158">**Listener.**</span><span class="sxs-lookup"><span data-stu-id="9e141-158">**Listener.**</span></span> <span data-ttu-id="9e141-159">Die serverseitige API, die Daten von allen Agents empfängt und Daten über Populationen aggregiert.</span><span class="sxs-lookup"><span data-stu-id="9e141-159">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="9e141-160">**Hub.**</span><span class="sxs-lookup"><span data-stu-id="9e141-160">**Hub.**</span></span> <span data-ttu-id="9e141-161">Fungiert als Client-API für das System, läuft auf dem/den Web-Server (en) und stellt Echtzeit-Datenaktualisierungen für Kunden bereit, die über die Website verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="9e141-161">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="9e141-162">(Der Hub wird automatisch als Teil der Website MSI installiert.)</span><span class="sxs-lookup"><span data-stu-id="9e141-162">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="9e141-163">**Website.**</span><span class="sxs-lookup"><span data-stu-id="9e141-163">**Website.**</span></span> <span data-ttu-id="9e141-164">Eine Benutzeroberfläche, die alle im System verfügbaren Features zusammenzieht.</span><span class="sxs-lookup"><span data-stu-id="9e141-164">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="9e141-165">Darüber hinaus benötigt der Statistik- \*\*\*\* Manager einen Open-Source-Datenstruktur Server mit einem Open-Source-Server für die speicherinterne Zwischenspeicherung.</span><span class="sxs-lookup"><span data-stu-id="9e141-165">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="9e141-166">Weitere Informationen zum Herunterladen von a/a finden Sie unter [Bereitstellen des Statistik-Managers](deploy.md#BKMK_Deploy) .</span><span class="sxs-lookup"><span data-stu-id="9e141-166">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="9e141-167">Lokale Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="9e141-167">On-premises deployment</span></span>
<span data-ttu-id="9e141-168"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="9e141-168"></span></span>

<span data-ttu-id="9e141-169">In einer lokalen Bereitstellung hostet ein einzelner Server alle serverseitigen Statistics Manager-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="9e141-169">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="9e141-170">Das folgende Diagramm zeigt eine lokale Bereitstellung, in der die Statistik-Manager-Website, der Hub-, Listener-und das zwischen Speicherungssystem für das System System auf einem einzelnen Computer gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="9e141-170">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="9e141-171">Der Statistik-Manager überwacht drei Skype for Business-Server, die jeweils über einen einzigen Agentendaten an den Listener übertragen.</span><span class="sxs-lookup"><span data-stu-id="9e141-171">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="9e141-172">Benutzer stellen eine Verbindung mit einer einzelnen Website her, um alle Daten anzuzeigen, die vom Statistik-Manager aggregiert wurden:</span><span class="sxs-lookup"><span data-stu-id="9e141-172">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![Stats Manager – lokale Bereitstellung](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="9e141-174">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="9e141-174">Requirements</span></span>
<span data-ttu-id="9e141-175"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="9e141-175"></span></span>

<span data-ttu-id="9e141-176">Sie müssen die folgenden Software-, Netzwerk-und Hardwareanforderungen Bedenken, bevor Sie den Statistik-Manager bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9e141-176">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="9e141-177">Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="9e141-177">Software requirements</span></span>

- <span data-ttu-id="9e141-178">Windows Server 2016 und 2019</span><span class="sxs-lookup"><span data-stu-id="9e141-178">Windows Server 2016 and 2019</span></span>

- <span data-ttu-id="9e141-179">IIS (automatisch installiert)</span><span class="sxs-lookup"><span data-stu-id="9e141-179">IIS (automatically installed)</span></span>

- <span data-ttu-id="9e141-180">Redis</span><span class="sxs-lookup"><span data-stu-id="9e141-180">Redis</span></span>

- <span data-ttu-id="9e141-181">Statistik-Manager-Dienste (automatisch installiert)</span><span class="sxs-lookup"><span data-stu-id="9e141-181">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="9e141-182">PSExec – erforderlich für die Remote-Agent-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="9e141-182">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="9e141-183">.NET 4,5 (im Lieferumfang von 2012 R2) – erforderlich für Agents und serverseitige Komponenten</span><span class="sxs-lookup"><span data-stu-id="9e141-183">.NET 4.5 (included with 2012 R2) - Required for agents and server-side components</span></span>
- <span data-ttu-id="9e141-184">Herunterladen des [Skype for Business-Servers, Echtzeitstatistik-Manager (64-Bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span><span class="sxs-lookup"><span data-stu-id="9e141-184">Download the [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="9e141-185">Netzwerkanforderungen</span><span class="sxs-lookup"><span data-stu-id="9e141-185">Networking requirements</span></span>


|<span data-ttu-id="9e141-186">**Hostserver**</span><span class="sxs-lookup"><span data-stu-id="9e141-186">**Hosting server**</span></span>|<span data-ttu-id="9e141-187">**Agents**</span><span class="sxs-lookup"><span data-stu-id="9e141-187">**Agents**</span></span>|<span data-ttu-id="9e141-188">**Listener**</span><span class="sxs-lookup"><span data-stu-id="9e141-188">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9e141-189">Minimales Gigabit-Vollduplex-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="9e141-189">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="9e141-190">Ausgehende TCP-Port 8443 (anpassbare Portnummer) für die Kommunikation mit dem Listener.</span><span class="sxs-lookup"><span data-stu-id="9e141-190">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="9e141-191">Der Listener-Port muss auf allen Servern identisch sein.</span><span class="sxs-lookup"><span data-stu-id="9e141-191">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="9e141-192">Der eingehende TCP-Port 80 oder 443 wird geöffnet, um die Website zu hosten.</span><span class="sxs-lookup"><span data-stu-id="9e141-192">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="9e141-193">Eingehenden TCP-Port 8443 (anpassbare Portnummer), damit die Agents damit kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="9e141-193">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="9e141-194">Während der Installation werden Firewall-Ports für den Listener und die Website automatisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="9e141-194">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="9e141-195">Bei den Agents geht die Installation davon aus, dass ausgehende TCP-Verbindungen standardmäßig zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="9e141-195">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="9e141-196">Hardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="9e141-196">Hardware requirements</span></span>

<span data-ttu-id="9e141-197">In einer lokalen Bereitstellung, in der ein einzelner Server alle serverseitigen Statistiken-Manager-Komponenten hostet, sollte ein Server mit 16 GB Arbeitsspeicher und 4 CPUs in der Lage sein, durchschnittlich etwa 150-Beispiele pro Sekunde zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9e141-197">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="9e141-198">Verwenden Sie die folgende Berechnung, um zu ermitteln, wie viele Leistungsindikatoren/Agents Sie unterstützen können:</span><span class="sxs-lookup"><span data-stu-id="9e141-198">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="9e141-199">100 Server \*80 Counter \* 1 Sample pro Minute von jedem Agenten/60 Sekunden = ~ 133 Samples pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="9e141-199">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="9e141-200">Sicherheitsüberlegungen</span><span class="sxs-lookup"><span data-stu-id="9e141-200">Security considerations</span></span>
<span data-ttu-id="9e141-201"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="9e141-201"></span></span>

<span data-ttu-id="9e141-202">Der gesamte Datenverkehr zwischen Servern ist verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="9e141-202">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="9e141-203">Verschlüsselter HTTPS-Datenverkehr wird über Port 8443 (standardmäßig) vom Agent an den Listener-Server gesendet.</span><span class="sxs-lookup"><span data-stu-id="9e141-203">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="9e141-204">Der Agent überprüft den SSL-Fingerabdruck auf dem Server, um sicherzustellen, dass der Listener-Server der erwartete Empfänger ist.</span><span class="sxs-lookup"><span data-stu-id="9e141-204">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="9e141-205">Beachten Sie, dass der Agent bei Zertifikaten die Fingerabdruck-Verifizierung verwendet (anstatt der Kettenverifizierung).</span><span class="sxs-lookup"><span data-stu-id="9e141-205">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="9e141-206">Er führt keine vollständige Verifizierung von Zertifikaten durch, weil es möglich ist, selbstsignierte Zertifikate zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9e141-206">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="9e141-207">Nachdem der Agent erfüllt ist, ist der Listener echt, ein Kennwort wird vom Agenten angezeigt, der dann vom Listener überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="9e141-207">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="9e141-208">Der Agent beginnt mit der Übertragung von Leistungsdaten über die Verbindung mit dem Listener.</span><span class="sxs-lookup"><span data-stu-id="9e141-208">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="9e141-209">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9e141-209">For more information</span></span>
<span data-ttu-id="9e141-210"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="9e141-210"></span></span>

<span data-ttu-id="9e141-211">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="9e141-211">For more information, see the following:</span></span>

- [<span data-ttu-id="9e141-212">Bereitstellen von Statistics Manager für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9e141-212">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)

- [<span data-ttu-id="9e141-213">Aktualisieren von Statistics Manager für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9e141-213">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)

- [<span data-ttu-id="9e141-214">Behandeln von Problemen im Zusammenhang mit Statistics Manager für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9e141-214">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
