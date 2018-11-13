---
title: Problembehandlung bei Statistiken Manager für Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Zusammenfassung: Lesen Sie dieses Thema, um die Bereitstellung von Statistiken Manager für Skype für Business Server zu beheben.'
ms.openlocfilehash: 3a0bb2530e0b19685f28a747660e59b1fceec4e8
ms.sourcegitcommit: 8536a34cb13d40b30f84d95e6df10542ef85c36d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26292983"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="d4452-103">Problembehandlung bei Statistiken Manager für Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="d4452-103">Troubleshoot Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="d4452-104">**Zusammenfassung:** Lesen Sie dieses Thema, um die Bereitstellung von Statistiken Manager für Skype für Business Server zu beheben.</span><span class="sxs-lookup"><span data-stu-id="d4452-104">**Summary:** Read this topic to troubleshoot your deployment of Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="d4452-105">In diesem Thema wird beschrieben, wie für die Problembehandlung bei der Bereitstellung von Statistiken-Manager mit der Beschreibung der Ereignisse, die möglicherweise im Ereignisprotokoll Anwendung angezeigt, und die entsprechenden Aktionen, die Sie ergreifen können, das Ereignis zu beheben.</span><span class="sxs-lookup"><span data-stu-id="d4452-105">This topic describes how to troubleshoot your Statistics Manager deployment by describing events you might see in the application event log, and appropriate actions you might take to rectify the event.</span></span> <span data-ttu-id="d4452-106">Dieses Thema enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="d4452-106">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="d4452-107">Agent-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="d4452-107">Agent events</span></span>](troubleshoot.md#BKMK_Agent)
    
- [<span data-ttu-id="d4452-108">Listener-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="d4452-108">Listener events</span></span>](troubleshoot.md#BKMK_Listener)
    
- [<span data-ttu-id="d4452-109">Websiteprobleme</span><span class="sxs-lookup"><span data-stu-id="d4452-109">Website issues</span></span>](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a><span data-ttu-id="d4452-110">Agent-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="d4452-110">Agent events</span></span>
<span data-ttu-id="d4452-111"><a name="BKMK_Agent"> </a></span><span class="sxs-lookup"><span data-stu-id="d4452-111"></span></span>

- <span data-ttu-id="d4452-112">**1000** – Prozessor-Limiter (Auftragsobjekt) kann nicht eingerichtet werden – unbekannte Ursache</span><span class="sxs-lookup"><span data-stu-id="d4452-112">**1000** — Unable to setup processor limiter (Job Object) — Unknown reason</span></span>
    
- <span data-ttu-id="d4452-113">**1001** – Prozess eingeschränkt ist nicht zulässig für den Prozess (möglicherweise bereits in einem Auftrag-Objekt)</span><span class="sxs-lookup"><span data-stu-id="d4452-113">**1001** — Process limiting isn't allowed on the process (probably already inside a Job Object)</span></span>
    
    <span data-ttu-id="d4452-114">Der Agent wird innerhalb eines Windows-Auftragsobjekts ausgeführt, um automatisch dessen Speicherbedarf zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="d4452-114">The Agent runs inside of a Windows Job Object to automatically limit its memory footprint.</span></span> <span data-ttu-id="d4452-115">Falls der Agent nicht gestartet wird und diese Ereigniseinträge im Ereignisprotokoll zu finden sind, kann das Auftragsobjekt auf dem Server nicht instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="d4452-115">If the agent will not start and these event entries are present in the event log, the Job Object is not able to be instantiated on the server.</span></span> <span data-ttu-id="d4452-116">Um das Problem zu umgehen, kann die obere Speicherbegrenzung aufgehoben werden, indem ein Wert in der Konfigurationsdatei geändert wird:</span><span class="sxs-lookup"><span data-stu-id="d4452-116">To work around this, the upper memory limit can be removed by changing a value in the config file:</span></span>
    
  ```
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    <span data-ttu-id="d4452-117">Suchen Sie nach "MaxProcessMemoryMB", und ändern Sie den Wert auf "0" wie dargestellt:</span><span class="sxs-lookup"><span data-stu-id="d4452-117">Search for "MaxProcessMemoryMB" and change the value to "0" as shown:</span></span>
    
  ```
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > <span data-ttu-id="d4452-118">Wenn diese Änderung vorgenommen wurde, wird der Agent im Allgemeinen weiterhin nutzen \< 100 MB Arbeitsspeicher, jedoch es nicht erzwingen auf 300 MB beschränkt werden wie der Standardwert ist.</span><span class="sxs-lookup"><span data-stu-id="d4452-118">If this change is made, the Agent will generally still consume \< 100 MB of memory, however it will not be forcefully limited to 300 MB as is the default.</span></span> <span data-ttu-id="d4452-119">Wenn diese Änderung vorgenommen wird, ist zu empfehlen, den Speicherverbrauch genau im Auge zu behalten, um sicherzustellen, dass der Agent nicht sehr viel Speicher auf seinem Hostcomputer in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="d4452-119">If this change is made, we recommend closely monitoring memory usage to ensure the Agent does not consume a large amount of memory on its host machine.</span></span> 
  
- <span data-ttu-id="d4452-120">**2000** – Fehler bei der Clientinitialisierung</span><span class="sxs-lookup"><span data-stu-id="d4452-120">**2000** — Client initialization failure</span></span>
    
- <span data-ttu-id="d4452-121">**2001** – Unter keiner Quell-IP konnte eine Verbindung mit dem Dienst hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d4452-121">**2001**— No connection could be made to the service on any source IP</span></span>
    
    <span data-ttu-id="d4452-122">Wenn der Agent keine Verbindung zum Listener-Computer herstellen kann, überprüfen Sie die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="d4452-122">If the Agent cannot connect to the Listener computer, check the following:</span></span>
    
1. <span data-ttu-id="d4452-123">Stellen Sie sicher, dass der Listener-Dienst auf dem Listener-Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d4452-123">Ensure the Listener service is running on the Listener computer.</span></span> <span data-ttu-id="d4452-124">Ist das nicht der Fall, stellen Sie sicher, dass Redis auf diesem Server ausgeführt wird, und starten Sie anschließend den Listener-Dienst neu.</span><span class="sxs-lookup"><span data-stu-id="d4452-124">If not, ensure Redis is running on that server and then restart the Listener service.</span></span>
    
    <span data-ttu-id="d4452-125">Überprüfen Sie das Ereignisprotokoll Statistiken-Manager auf dem Computer Listener, um sicherzustellen, dass es sind keine Probleme mit den Statistiken Manager Listener-Dienst selbst.</span><span class="sxs-lookup"><span data-stu-id="d4452-125">Check the Statistics Manager event log on the Listener computer to ensure there are no issues with the Statistics Manager Listener service itself.</span></span>
    
2. <span data-ttu-id="d4452-126">Verwenden Sie ein Connectivity Tool wie Telnet, um die Verbindung vom Agent- zum Listener-Computer auf dem richtigen Port zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d4452-126">Use a connectivity tool such as telnet to verify connectivity from the Agent computer to the Listener on the correct port.</span></span>
    
    <span data-ttu-id="d4452-127">Ist diese Verbindung nicht gegeben, stellen Sie sicher, dass die Firewallregel für eingehenden Verkehr für die Art von Netzwerk aktiviert ist, mit dem der Listener-Computer verbunden ist (privat/öffentlich/Domäne).</span><span class="sxs-lookup"><span data-stu-id="d4452-127">If not, make sure the incoming firewall rule is enabled on the Listener computer for the network type that the Listener computer is connected to (private/public/domain).</span></span> <span data-ttu-id="d4452-128">Wenn der Listener-Computer nicht Mitglied einer Domäne ist, im Netzwerk werden möglicherweise als öffentliche aufgelistet und in diesem Fall die Firewall-Regeln mit Statistiken Manager installiert standardmäßig nicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="d4452-128">If the Listener computer is not joined to a domain, the network may be listed as public and in that case the firewall rules installed with Statistics Manager will not apply by default.</span></span>
    
- <span data-ttu-id="d4452-129">**4000** – Fehler beim Herunterladen von Serverinformationen vom Listener-Computer (unbekannte Ursache)</span><span class="sxs-lookup"><span data-stu-id="d4452-129">**4000** — Failure to download Server Info from Listener (unknown reason)</span></span>
    
  - <span data-ttu-id="d4452-130">**4001** – Server in Listener-Topologie nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="d4452-130">**4001** — Server Not Found in Listener Topology</span></span>
    
    <span data-ttu-id="d4452-131">Dieser Fehler tritt auf, wenn der Server erfolgreich eine mit dem Listener Verbindung, aber der Server nicht auf die Topologie in der Listener Cache hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="d4452-131">This error will occur if the server is successfully connecting to the Listener, but the server was not added to the topology in the Listener's cache.</span></span> <span data-ttu-id="d4452-132">Lösungsmöglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="d4452-132">Resolution options:</span></span>
    
  - <span data-ttu-id="d4452-p107">	Stellen Sie sicher, dass Sie die Anweisungen für den Import der Topologie befolgt haben. Siehe auch [Import the topology](deploy.md#BKMK_ImportTopology).  </span><span class="sxs-lookup"><span data-stu-id="d4452-p107">Make sure you followed the instructions for importing the topology. See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span> 
    
  - <span data-ttu-id="d4452-135">Wenn sich der Agent auf einem Server befindet, der in der Topologie nicht aufgeführt ist (zum Beispiel die Knoten in einem SQL-„AlwaysOn“-Cluster), müssen Sie den Agent manuell hinzufügen, indem Sie die Anleitungen in [Import the topology](deploy.md#BKMK_ImportTopology) ausführen.</span><span class="sxs-lookup"><span data-stu-id="d4452-135">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="d4452-136">**4002** – Ungültiges Listener-Kennwort</span><span class="sxs-lookup"><span data-stu-id="d4452-136">**4002** — Invalid Listener Password</span></span>
    
    <span data-ttu-id="d4452-137">Das verschlüsselte Kennwort, das der Agent zu verwenden versucht, stimmt nicht mit dem Servicekennwort auf dem Listener selbst überein.</span><span class="sxs-lookup"><span data-stu-id="d4452-137">The encrypted password that the agent is attempting to use does not match the service password on the Listener itself.</span></span> <span data-ttu-id="d4452-138">Deinstallieren Sie den Agent und installieren Sie ihn neu, indem Sie dabei das richtige Servicekennwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4452-138">Uninstall the Agent and re-install it using the correct service password.</span></span>
    
  - <span data-ttu-id="d4452-139">**4003** – Zertifikatfingerabdruck-Konflikt</span><span class="sxs-lookup"><span data-stu-id="d4452-139">**4003** — Certificate Thumbprint Mismatch</span></span>
    
    <span data-ttu-id="d4452-140">Den Fingerabdruck des Zertifikats an den Agent bei der Installation angegeben nicht übereinstimmt, die der Fingerabdruck des Zertifikats dem Listener derzeit verwendet wird und daher die Verbindung werden abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="d4452-140">The certificate thumbprint given to the Agent at install time does not match the thumbprint on the certificate the Listener is currently using and therefore the connection will be refused.</span></span> <span data-ttu-id="d4452-141">Deinstallieren Sie den Agent, und installieren Sie ihn mithilfe des richtigen Zertifikatfingerabdrucks neu.</span><span class="sxs-lookup"><span data-stu-id="d4452-141">Uninstall the Agent and re-install it using the correct certificate thumbprint.</span></span>
    
  - <span data-ttu-id="d4452-142">**4004** – Ungültige Antwort oder HttpStatusCode ungültig</span><span class="sxs-lookup"><span data-stu-id="d4452-142">**4004** — Invalid Response or HttpStatusCode</span></span>
    
    <span data-ttu-id="d4452-143">Der Listener reagiert nicht mit einem erwarteten Status.  </span><span class="sxs-lookup"><span data-stu-id="d4452-143">The Listener is not responding with an expected status.</span></span> 
    
  - <span data-ttu-id="d4452-144">Läuft die Verbindung über einen Proxy, überprüfen Sie die Proxy-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="d4452-144">If the connection is proxied, check the proxy configuration.</span></span>
    
  - <span data-ttu-id="d4452-145">Überprüfen des Computers Listener StatsMan Protokoll bei Problemen mit der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="d4452-145">Check the Listener computer's StatsMan log for issues with its configuration.</span></span>
    
  - <span data-ttu-id="d4452-146">**4005** – XML-Deserialisierung nicht möglich</span><span class="sxs-lookup"><span data-stu-id="d4452-146">**4005** — Couldn't de-serialize the XML</span></span>
    
    <span data-ttu-id="d4452-147">Die Serverinformationen auf dem Listener-Server sind beschädigt oder es gibt möglicherweise einen Versionskonflikt zwischen dem Agent und dem Listener-Computer.</span><span class="sxs-lookup"><span data-stu-id="d4452-147">The server info on the Listener server is corrupt or there may be a version mismatch between the Agent and the Listener computers.</span></span> <span data-ttu-id="d4452-148">Stellen Sie sicher, dass die Versionen übereinstimmen und überprüfen Sie das Listener-Ereignisprotokoll auf Probleme.</span><span class="sxs-lookup"><span data-stu-id="d4452-148">Ensure the versions match and check the Listener event log for issues.</span></span>
    
## <a name="listener-events"></a><span data-ttu-id="d4452-149">Listener-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="d4452-149">Listener events</span></span>
<span data-ttu-id="d4452-150"><a name="BKMK_Listener"> </a></span><span class="sxs-lookup"><span data-stu-id="d4452-150"></span></span>

- <span data-ttu-id="d4452-151">**10000** – Startfehler aus unbekannten Gründen (nicht zu beheben; in der Folge stellt der Dienst die Arbeit ein oder stürzt ab)</span><span class="sxs-lookup"><span data-stu-id="d4452-151">**10000** — Startup failure Unknown reason (these are unrecoverable and the service will stop/crash as a result)</span></span>
    
  - <span data-ttu-id="d4452-152">**10001** – Konfigurationsproblem</span><span class="sxs-lookup"><span data-stu-id="d4452-152">**10001** — Configuration problem</span></span>
    
    <span data-ttu-id="d4452-153">Im Allgemeinen tritt dieses Problem auf, wenn die Datei [listener_install_location]\PerfAgentListener.exe.config von Hand geändert wurde und von der Anwendung nicht mehr gelesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="d4452-153">Generally this will occur when the [listener_install_location]\PerfAgentListener.exe.config file has been modified by hand and cannot be read by the application.</span></span>
    
  - <span data-ttu-id="d4452-154">**10002** – HTTP-Listener-Initialisierungsfehler</span><span class="sxs-lookup"><span data-stu-id="d4452-154">**10002** — HTTP Listener initialization error</span></span>
    
    <span data-ttu-id="d4452-155">Dieses Ereignis wird im Allgemeinen protokolliert, wenn die URL-ACL bei der Installation nicht ordnungsgemäß eingerichtet wurde oder wenn das SSL-Zertifikat ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="d4452-155">This event will generally be logged when the URL ACL has not been set properly during installation or the SSL Cert is invalid.</span></span> <span data-ttu-id="d4452-156">Stellen Sie sicher, dass das Zertifikat in Ihrer Konfiguration gültig ist.</span><span class="sxs-lookup"><span data-stu-id="d4452-156">Ensure the certificate in your configuration is valid.</span></span> <span data-ttu-id="d4452-157">Ist das der Fall, installieren Sie den Listener gemäß den Anweisungen in [Deploy Statistics Manager](deploy.md#BKMK_Deploy) neu.</span><span class="sxs-lookup"><span data-stu-id="d4452-157">If it is, reinstall the Listener according to the instructions in [Deploy Statistics Manager](deploy.md#BKMK_Deploy).</span></span>
    
  - <span data-ttu-id="d4452-158">**10003** – Redis-Fehler</span><span class="sxs-lookup"><span data-stu-id="d4452-158">**10003** — Redis failure</span></span>
    
  - <span data-ttu-id="d4452-159">**10004** – Cache-Infrastruktur-Fehler</span><span class="sxs-lookup"><span data-stu-id="d4452-159">**10004** — Caching infrastructure failure</span></span>
    
  - <span data-ttu-id="d4452-160">**10007** – Einstellungen (in Redis gespeichert)</span><span class="sxs-lookup"><span data-stu-id="d4452-160">**10007** — Settings (stored in redis)</span></span>
    
    <span data-ttu-id="d4452-161">Der Listener konnte keinen Kontakt zu Redis herstellen oder keine wohlgeformten Daten aus dem Cache abrufen und deshalb nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="d4452-161">The Listener could not contact Redis or retrieve well-formed data from the cache and could not start.</span></span> <span data-ttu-id="d4452-162">Stellen Sie sicher, dass der Redis-Dienst auf dem Server gestartet und ordnungsgemäß konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="d4452-162">Ensure the Redis service is started and configured properly on the server.</span></span>
    
  - <span data-ttu-id="d4452-163">**10005** – Abrufen/Analysieren von Serverinformationen</span><span class="sxs-lookup"><span data-stu-id="d4452-163">**10005** — Server info retrieval/parsing</span></span>
    
    <span data-ttu-id="d4452-164">Die Topologieinformationen im Redis-Cache sind ungültig.</span><span class="sxs-lookup"><span data-stu-id="d4452-164">The topology information in the Redis cache is invalid.</span></span> <span data-ttu-id="d4452-165">Versuchen Sie zunächst, Redis und den Listener neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="d4452-165">First, attempt to restart Redis and the Listener.</span></span> <span data-ttu-id="d4452-166">Wenn der Fehler weiterhin besteht, schlagen Sie unter [Import the topology](deploy.md#BKMK_ImportTopology) nach, um die Topologiedaten neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d4452-166">If the error persists, see [Import the topology](deploy.md#BKMK_ImportTopology) to recreate the topology data.</span></span>
    
- <span data-ttu-id="d4452-167">**10100** – Redis-PING-Ausfall</span><span class="sxs-lookup"><span data-stu-id="d4452-167">**10100** — Redis PING outage</span></span>
    
  - <span data-ttu-id="d4452-168">**10101** – Fortgesetzter Redis-PING-Ausfall (alle 60 Sekunden)</span><span class="sxs-lookup"><span data-stu-id="d4452-168">**10101** — Redis PING continued outage (every 60 seconds)</span></span>
    
  - <span data-ttu-id="d4452-169">**30100** – Redis-PING-Ausfall wiederhergestellt</span><span class="sxs-lookup"><span data-stu-id="d4452-169">**30100** — Redis PING outage restored</span></span>
    
    <span data-ttu-id="d4452-170">Diese Fehler werden protokolliert, wenn der Listener keine Verbindung zu Redis herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="d4452-170">These will be logged when the Listener cannot connect to Redis.</span></span> <span data-ttu-id="d4452-171">Stellen Sie sicher, dass Redis gestartet ist und dass Netzwerkkonnektivität zwischen Listener und Redis zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="d4452-171">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="d4452-172">**10200** – Redis-Write-Ausfall</span><span class="sxs-lookup"><span data-stu-id="d4452-172">**10200** — Redis Write outage</span></span>
    
  - <span data-ttu-id="d4452-173">**10201** – Fortgesetzter Redis-Write-Ausfall (alle 60 Sekunden)</span><span class="sxs-lookup"><span data-stu-id="d4452-173">**10201** — Redis Write outage continued (every 60 seconds)</span></span>
    
  - <span data-ttu-id="d4452-174">**30100** – Redis-Write-Ausfall gelöst</span><span class="sxs-lookup"><span data-stu-id="d4452-174">**30100** — Redis Write outage resolved</span></span>
    
    <span data-ttu-id="d4452-175">Diese Fehler werden protokolliert, wenn der Listener keine Verbindung zum Redis-Cache herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="d4452-175">These will be logged when the Listener cannot write to the Redis cache.</span></span> <span data-ttu-id="d4452-176">Stellen Sie sicher, dass Redis gestartet ist und dass Netzwerkkonnektivität zwischen Listener und Redis zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="d4452-176">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="d4452-177">**30000** – Erfolgreich gestartet</span><span class="sxs-lookup"><span data-stu-id="d4452-177">**30000** — Successfully started</span></span>
    
    <span data-ttu-id="d4452-178">Wird bei jedem Start des Listeners protokolliert.</span><span class="sxs-lookup"><span data-stu-id="d4452-178">Logged each time the Listener is started.</span></span>
    
- <span data-ttu-id="d4452-179">**22000** – Initialisierung von Statistiken Manager-Agent erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="d4452-179">**22000** — Initialization of Statistics Manager Agent succeeded.</span></span>
    
- <span data-ttu-id="d4452-180">**23000** – Initialisierung von „EventLogQueryManager“ war erfolgreich (beim ersten Mal oder nach Fehlversuch).</span><span class="sxs-lookup"><span data-stu-id="d4452-180">**23000** — Initialization of EventLogQueryManager succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="d4452-181">**24000** – Initialisierung von „serverinfo“ war erfolgreich (beim ersten Mal oder nach Fehlversuch).</span><span class="sxs-lookup"><span data-stu-id="d4452-181">**24000** — Initialization of serverinfo succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="d4452-182">**25000** – Listener ist nach Sendefehlversuch (oder erstem erfolgreichen Senden) wieder online.</span><span class="sxs-lookup"><span data-stu-id="d4452-182">**25000** — Listener is back online after failing to post (or first successful post)</span></span>
    
- <span data-ttu-id="d4452-183">**5000** – Offlinestart des Listeners für das Senden von Daten</span><span class="sxs-lookup"><span data-stu-id="d4452-183">**5000** — Start of listener offline for posting data</span></span>
    
- <span data-ttu-id="d4452-184">**5001** – Listener ist für längere Zeit weiterhin offline.</span><span class="sxs-lookup"><span data-stu-id="d4452-184">**5001** — Listener is still offline for an extended period</span></span>
    
    <span data-ttu-id="d4452-185">Diese Ereignisse können bei Überwachungs-/Benachrichtigungs-/Löschproblemen nützlich sein.</span><span class="sxs-lookup"><span data-stu-id="d4452-185">These events can be useful for monitoring/alerting/clearing issues.</span></span>
    
## <a name="website-issues"></a><span data-ttu-id="d4452-186">Websiteprobleme</span><span class="sxs-lookup"><span data-stu-id="d4452-186">Website issues</span></span>
<span data-ttu-id="d4452-187"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="d4452-187"></span></span>

- <span data-ttu-id="d4452-188">Sich wiederholende Anmeldung, eingabeaufforderungen in Chrome – dies wurde ein Fehler, der in Version 1.1 aufgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="d4452-188">Repetitive login prompts in Chrome - this was a bug that has been resolved in version 1.1.</span></span> <span data-ttu-id="d4452-189">Stellen Sie sicher, dass Sie auf die neueste Version von Statistiken Manager aktualisiert haben, wenn Sie wiederholt Anmeldung Anweisungen im Chrome-Browsers angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d4452-189">Be sure you have upgraded to the latest version of Statistics Manager if you are seeing repeated login prompts in the Chrome browser.</span></span> <span data-ttu-id="d4452-190">Folgendermaßen können Sie feststellen, welche Version der Website Sie ausführen:</span><span class="sxs-lookup"><span data-stu-id="d4452-190">To verify the version of the website you are running:</span></span>
    
  - <span data-ttu-id="d4452-191">	Öffnen Sie im Datei-Explorer (Standardverzeichnis).</span><span class="sxs-lookup"><span data-stu-id="d4452-191">In File Explorer, open (default directory)</span></span>
    
  - <span data-ttu-id="d4452-192">Klicken Sie mit der rechten Maustaste auf „StatsManHubWebSite.dll“ und lassen Sie die entsprechenden Eigenschaften anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d4452-192">Right click on StatsManHubWebSite.dll and view its properties.</span></span>
    
  - <span data-ttu-id="d4452-193">Wenn ein Computer in der KHI-Querformatansicht oder der Zählerangabenansicht nicht gefunden werden kann, stellen Sie sicher, dass der Computer Mitglied einer Website und eines Pools ist.</span><span class="sxs-lookup"><span data-stu-id="d4452-193">If a computer cannot be found in the KHI Landscape view or the Counter Details view, make sure it is a member of a Site and a Pool.</span></span> <span data-ttu-id="d4452-194">Ist er das nicht, taucht er in diesen Ansichten auch nicht auf.</span><span class="sxs-lookup"><span data-stu-id="d4452-194">If it is not, it will not appear in those views.</span></span> <span data-ttu-id="d4452-195">Mehr über die Definition einer Website und eines Pools für einen Server in der Topologie erfahren Sie unter [Import the topology](deploy.md#BKMK_ImportTopology).</span><span class="sxs-lookup"><span data-stu-id="d4452-195">For information about defining a site and pool for a server in the topology, see [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="d4452-196">Die Produktversion wird unter den Beschreibungsangaben angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d4452-196">The product version will be shown in the Description details.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="d4452-197">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d4452-197">For more information</span></span>
<span data-ttu-id="d4452-198"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="d4452-198"></span></span>

<span data-ttu-id="d4452-199">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="d4452-199">For more information, see the following:</span></span>
  
- [<span data-ttu-id="d4452-200">Planen der Business Server für den Statistiken-Manager für Skype</span><span class="sxs-lookup"><span data-stu-id="d4452-200">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="d4452-201">Bereitstellen von Statistiken Manager für Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="d4452-201">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="d4452-202">Aktualisieren von Statistiken Manager für Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="d4452-202">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
    
- [<span data-ttu-id="d4452-203">Skype for Business Server Statistics Manager-Blog</span><span class="sxs-lookup"><span data-stu-id="d4452-203">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/dodeitte/2015/10/24/skype-for-business-server-real-time-statistics-manager)
    

