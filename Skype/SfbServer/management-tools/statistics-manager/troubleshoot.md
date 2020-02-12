---
title: Behandeln von Problemen im Zusammenhang mit Statistics Manager für Skype for Business Server
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
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Zusammenfassung: Lesen Sie dieses Thema, um die Bereitstellung von Statistics Manager für Skype for Business Server zu beheben.'
ms.openlocfilehash: 12b6176e64d034d94e8a6ad86e748c1906f9c0c5
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888874"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="eedd2-103">Behandeln von Problemen im Zusammenhang mit Statistics Manager für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="eedd2-103">Troubleshoot Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="eedd2-104">**Zusammenfassung:** Lesen Sie dieses Thema, um die Bereitstellung von Statistics Manager für Skype for Business Server zu beheben.</span><span class="sxs-lookup"><span data-stu-id="eedd2-104">**Summary:** Read this topic to troubleshoot your deployment of Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="eedd2-105">In diesem Thema wird beschrieben, wie Sie eine Problembehandlung für Ihre Statistik-Manager-Bereitstellung durchführen, indem Sie Ereignisse beschreiben, die möglicherweise im Anwendungsereignisprotokoll angezeigt werden, und geeignete Aktionen zum Beheben des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="eedd2-105">This topic describes how to troubleshoot your Statistics Manager deployment by describing events you might see in the application event log, and appropriate actions you might take to rectify the event.</span></span> <span data-ttu-id="eedd2-106">Dieses Thema enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="eedd2-106">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="eedd2-107">Agent-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="eedd2-107">Agent events</span></span>](troubleshoot.md#BKMK_Agent)
    
- [<span data-ttu-id="eedd2-108">Listener-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="eedd2-108">Listener events</span></span>](troubleshoot.md#BKMK_Listener)
    
- [<span data-ttu-id="eedd2-109">Websiteprobleme</span><span class="sxs-lookup"><span data-stu-id="eedd2-109">Website issues</span></span>](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a><span data-ttu-id="eedd2-110">Agent-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="eedd2-110">Agent events</span></span>
<span data-ttu-id="eedd2-111"><a name="BKMK_Agent"> </a></span><span class="sxs-lookup"><span data-stu-id="eedd2-111"><a name="BKMK_Agent"> </a></span></span>

- <span data-ttu-id="eedd2-112">**1000** – Prozessor-Limiter (Auftragsobjekt) kann nicht eingerichtet werden – unbekannte Ursache</span><span class="sxs-lookup"><span data-stu-id="eedd2-112">**1000** — Unable to setup processor limiter (Job Object) — Unknown reason</span></span>
    
- <span data-ttu-id="eedd2-113">**1001** – die Prozess Begrenzung ist für den Prozess (wahrscheinlich bereits in einem Auftragsobjekt) nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="eedd2-113">**1001** — Process limiting isn't allowed on the process (probably already inside a Job Object)</span></span>
    
    <span data-ttu-id="eedd2-114">Der Agent wird innerhalb eines Windows-Auftragsobjekts ausgeführt, um automatisch dessen Speicherbedarf zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="eedd2-114">The Agent runs inside of a Windows Job Object to automatically limit its memory footprint.</span></span> <span data-ttu-id="eedd2-115">Falls der Agent nicht gestartet wird und diese Ereigniseinträge im Ereignisprotokoll zu finden sind, kann das Auftragsobjekt auf dem Server nicht instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="eedd2-115">If the agent will not start and these event entries are present in the event log, the Job Object is not able to be instantiated on the server.</span></span> <span data-ttu-id="eedd2-116">Um das Problem zu umgehen, kann die obere Speicherbegrenzung aufgehoben werden, indem ein Wert in der Konfigurationsdatei geändert wird:</span><span class="sxs-lookup"><span data-stu-id="eedd2-116">To work around this, the upper memory limit can be removed by changing a value in the config file:</span></span>
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    <span data-ttu-id="eedd2-117">Suchen Sie nach "MaxProcessMemoryMB", und ändern Sie den Wert in "0" (siehe Abbildung):</span><span class="sxs-lookup"><span data-stu-id="eedd2-117">Search for "MaxProcessMemoryMB" and change the value to "0" as shown:</span></span>
    
  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > <span data-ttu-id="eedd2-118">Wenn diese Änderung vorgenommen wird, beansprucht \< der Agent in der Regel weiterhin 100 MB Arbeitsspeicher, wird jedoch nicht zwangsweise auf 300 MB limitiert, wie es der Standardwert ist.</span><span class="sxs-lookup"><span data-stu-id="eedd2-118">If this change is made, the Agent will generally still consume \< 100 MB of memory, however it will not be forcefully limited to 300 MB as is the default.</span></span> <span data-ttu-id="eedd2-119">Wenn diese Änderung vorgenommen wird, ist zu empfehlen, den Speicherverbrauch genau im Auge zu behalten, um sicherzustellen, dass der Agent nicht sehr viel Speicher auf seinem Hostcomputer in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="eedd2-119">If this change is made, we recommend closely monitoring memory usage to ensure the Agent does not consume a large amount of memory on its host machine.</span></span> 
  
- <span data-ttu-id="eedd2-120">**2000** – Fehler bei der Clientinitialisierung</span><span class="sxs-lookup"><span data-stu-id="eedd2-120">**2000** — Client initialization failure</span></span>
    
- <span data-ttu-id="eedd2-121">**2001** – Unter keiner Quell-IP konnte eine Verbindung mit dem Dienst hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="eedd2-121">**2001**— No connection could be made to the service on any source IP</span></span>
    
    <span data-ttu-id="eedd2-122">Wenn der Agent keine Verbindung zum Listener-Computer herstellen kann, überprüfen Sie die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="eedd2-122">If the Agent cannot connect to the Listener computer, check the following:</span></span>
    
    1. <span data-ttu-id="eedd2-123">Stellen Sie sicher, dass der Listener-Dienst auf dem Listener-Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="eedd2-123">Ensure the Listener service is running on the Listener computer.</span></span> <span data-ttu-id="eedd2-124">Ist das nicht der Fall, stellen Sie sicher, dass Redis auf diesem Server ausgeführt wird, und starten Sie anschließend den Listener-Dienst neu.</span><span class="sxs-lookup"><span data-stu-id="eedd2-124">If not, ensure Redis is running on that server and then restart the Listener service.</span></span>
        
        <span data-ttu-id="eedd2-125">Überprüfen Sie das Ereignisprotokoll des Statistik-Managers auf dem Listener-Computer, um sicherzustellen, dass es keine Probleme mit dem Listen Dienst des Statistik-Managers selbst gibt.</span><span class="sxs-lookup"><span data-stu-id="eedd2-125">Check the Statistics Manager event log on the Listener computer to ensure there are no issues with the Statistics Manager Listener service itself.</span></span>
        
    2. <span data-ttu-id="eedd2-126">Verwenden Sie ein Connectivity Tool wie Telnet, um die Verbindung vom Agent- zum Listener-Computer auf dem richtigen Port zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="eedd2-126">Use a connectivity tool such as telnet to verify connectivity from the Agent computer to the Listener on the correct port.</span></span>
        
        <span data-ttu-id="eedd2-127">Ist diese Verbindung nicht gegeben, stellen Sie sicher, dass die Firewallregel für eingehenden Verkehr für die Art von Netzwerk aktiviert ist, mit dem der Listener-Computer verbunden ist (privat/öffentlich/Domäne).</span><span class="sxs-lookup"><span data-stu-id="eedd2-127">If not, make sure the incoming firewall rule is enabled on the Listener computer for the network type that the Listener computer is connected to (private/public/domain).</span></span> <span data-ttu-id="eedd2-128">Wenn der Listener-Computer nicht mit einer Domäne verbunden ist, wird das Netzwerk möglicherweise als "öffentlich" aufgeführt, und in diesem Fall gelten die mit Statistik-Manager installierten Firewallregeln nicht standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="eedd2-128">If the Listener computer is not joined to a domain, the network may be listed as public and in that case the firewall rules installed with Statistics Manager will not apply by default.</span></span>
    
- <span data-ttu-id="eedd2-129">**4000** – Fehler beim Herunterladen von Serverinformationen vom Listener-Computer (unbekannte Ursache)</span><span class="sxs-lookup"><span data-stu-id="eedd2-129">**4000** — Failure to download Server Info from Listener (unknown reason)</span></span>
    
  - <span data-ttu-id="eedd2-130">**4001** – Server in Listener-Topologie nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="eedd2-130">**4001** — Server Not Found in Listener Topology</span></span>
    
    <span data-ttu-id="eedd2-131">Dieser Fehler tritt auf, wenn der Server erfolgreich eine Verbindung mit dem Listener herstellt, der Server jedoch nicht zur Topologie im Cache des Listener hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="eedd2-131">This error will occur if the server is successfully connecting to the Listener, but the server was not added to the topology in the Listener's cache.</span></span> <span data-ttu-id="eedd2-132">Lösungsmöglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="eedd2-132">Resolution options:</span></span>
    
  - <span data-ttu-id="eedd2-p107">	Stellen Sie sicher, dass Sie die Anweisungen für den Import der Topologie befolgt haben. Siehe auch [Import the topology](deploy.md#BKMK_ImportTopology).  </span><span class="sxs-lookup"><span data-stu-id="eedd2-p107">Make sure you followed the instructions for importing the topology. See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span> 
    
  - <span data-ttu-id="eedd2-135">Wenn sich der Agent auf einem Server befindet, der in der Topologie nicht aufgeführt ist (zum Beispiel die Knoten in einem SQL-„AlwaysOn“-Cluster), müssen Sie den Agent manuell hinzufügen, indem Sie die Anleitungen in [Import the topology](deploy.md#BKMK_ImportTopology) ausführen.</span><span class="sxs-lookup"><span data-stu-id="eedd2-135">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="eedd2-136">**4002** – Ungültiges Listener-Kennwort</span><span class="sxs-lookup"><span data-stu-id="eedd2-136">**4002** — Invalid Listener Password</span></span>
    
    <span data-ttu-id="eedd2-137">Das verschlüsselte Kennwort, das der Agent zu verwenden versucht, stimmt nicht mit dem Servicekennwort auf dem Listener selbst überein.</span><span class="sxs-lookup"><span data-stu-id="eedd2-137">The encrypted password that the agent is attempting to use does not match the service password on the Listener itself.</span></span> <span data-ttu-id="eedd2-138">Deinstallieren Sie den Agent und installieren Sie ihn neu, indem Sie dabei das richtige Servicekennwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="eedd2-138">Uninstall the Agent and re-install it using the correct service password.</span></span>
    
  - <span data-ttu-id="eedd2-139">**4003** – Zertifikatfingerabdruck-Konflikt</span><span class="sxs-lookup"><span data-stu-id="eedd2-139">**4003** — Certificate Thumbprint Mismatch</span></span>
    
    <span data-ttu-id="eedd2-140">Der für den Agenten während der Installationszeit angegebene Fingerabdruck des Zertifikats entspricht nicht dem Fingerabdruck des Zertifikats, das der Listener zurzeit verwendet, und daher wird die Verbindung abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="eedd2-140">The certificate thumbprint given to the Agent at install time does not match the thumbprint on the certificate the Listener is currently using and therefore the connection will be refused.</span></span> <span data-ttu-id="eedd2-141">Deinstallieren Sie den Agenten, und installieren Sie ihn mit dem richtigen Fingerabdruck des Zertifikats erneut.</span><span class="sxs-lookup"><span data-stu-id="eedd2-141">Uninstall the Agent and re-install it using the correct certificate thumbprint.</span></span>
    
  - <span data-ttu-id="eedd2-142">**4004** – Ungültige Antwort oder HttpStatusCode ungültig</span><span class="sxs-lookup"><span data-stu-id="eedd2-142">**4004** — Invalid Response or HttpStatusCode</span></span>
    
    <span data-ttu-id="eedd2-143">Der Listener reagiert nicht mit einem erwarteten Status.  </span><span class="sxs-lookup"><span data-stu-id="eedd2-143">The Listener is not responding with an expected status.</span></span> 
    
  - <span data-ttu-id="eedd2-144">Läuft die Verbindung über einen Proxy, überprüfen Sie die Proxy-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="eedd2-144">If the connection is proxied, check the proxy configuration.</span></span>
    
  - <span data-ttu-id="eedd2-145">Überprüfen Sie das Statistik Protokoll des Listener-Computers auf Probleme mit der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="eedd2-145">Check the Listener computer's StatsMan log for issues with its configuration.</span></span>
    
  - <span data-ttu-id="eedd2-146">**4005** – XML-Deserialisierung nicht möglich</span><span class="sxs-lookup"><span data-stu-id="eedd2-146">**4005** — Couldn't de-serialize the XML</span></span>
    
    <span data-ttu-id="eedd2-147">Die Serverinformationen auf dem Listener-Server sind beschädigt oder es gibt möglicherweise einen Versionskonflikt zwischen dem Agent und dem Listener-Computer.</span><span class="sxs-lookup"><span data-stu-id="eedd2-147">The server info on the Listener server is corrupt or there may be a version mismatch between the Agent and the Listener computers.</span></span> <span data-ttu-id="eedd2-148">Stellen Sie sicher, dass die Versionen übereinstimmen und überprüfen Sie das Listener-Ereignisprotokoll auf Probleme.</span><span class="sxs-lookup"><span data-stu-id="eedd2-148">Ensure the versions match and check the Listener event log for issues.</span></span>
    
## <a name="listener-events"></a><span data-ttu-id="eedd2-149">Listener-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="eedd2-149">Listener events</span></span>
<span data-ttu-id="eedd2-150"><a name="BKMK_Listener"> </a></span><span class="sxs-lookup"><span data-stu-id="eedd2-150"><a name="BKMK_Listener"> </a></span></span>

- <span data-ttu-id="eedd2-151">**10000** – Startfehler aus unbekannten Gründen (nicht zu beheben; in der Folge stellt der Dienst die Arbeit ein oder stürzt ab)</span><span class="sxs-lookup"><span data-stu-id="eedd2-151">**10000** — Startup failure Unknown reason (these are unrecoverable and the service will stop/crash as a result)</span></span>
    
  - <span data-ttu-id="eedd2-152">**10001** – Konfigurationsproblem</span><span class="sxs-lookup"><span data-stu-id="eedd2-152">**10001** — Configuration problem</span></span>
    
    <span data-ttu-id="eedd2-153">Im Allgemeinen tritt dieses Problem auf, wenn die Datei [listener_install_location]\PerfAgentListener.exe.config von Hand geändert wurde und von der Anwendung nicht mehr gelesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="eedd2-153">Generally this will occur when the [listener_install_location]\PerfAgentListener.exe.config file has been modified by hand and cannot be read by the application.</span></span>
    
  - <span data-ttu-id="eedd2-154">**10002** – HTTP-Listener-Initialisierungsfehler</span><span class="sxs-lookup"><span data-stu-id="eedd2-154">**10002** — HTTP Listener initialization error</span></span>
    
    <span data-ttu-id="eedd2-155">Dieses Ereignis wird im Allgemeinen protokolliert, wenn die URL-ACL bei der Installation nicht ordnungsgemäß eingerichtet wurde oder wenn das SSL-Zertifikat ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="eedd2-155">This event will generally be logged when the URL ACL has not been set properly during installation or the SSL Cert is invalid.</span></span> <span data-ttu-id="eedd2-156">Stellen Sie sicher, dass das Zertifikat in Ihrer Konfiguration gültig ist.</span><span class="sxs-lookup"><span data-stu-id="eedd2-156">Ensure the certificate in your configuration is valid.</span></span> <span data-ttu-id="eedd2-157">Ist das der Fall, installieren Sie den Listener gemäß den Anweisungen in [Deploy Statistics Manager](deploy.md#BKMK_Deploy) neu.</span><span class="sxs-lookup"><span data-stu-id="eedd2-157">If it is, reinstall the Listener according to the instructions in [Deploy Statistics Manager](deploy.md#BKMK_Deploy).</span></span>
    
  - <span data-ttu-id="eedd2-158">**10003** – Redis-Fehler</span><span class="sxs-lookup"><span data-stu-id="eedd2-158">**10003** — Redis failure</span></span>
    
  - <span data-ttu-id="eedd2-159">**10004** – Cache-Infrastruktur-Fehler</span><span class="sxs-lookup"><span data-stu-id="eedd2-159">**10004** — Caching infrastructure failure</span></span>
    
  - <span data-ttu-id="eedd2-160">**10007** – Einstellungen (in Redis gespeichert)</span><span class="sxs-lookup"><span data-stu-id="eedd2-160">**10007** — Settings (stored in redis)</span></span>
    
    <span data-ttu-id="eedd2-161">Der Listener konnte keinen Kontakt zu Redis herstellen oder keine wohlgeformten Daten aus dem Cache abrufen und deshalb nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="eedd2-161">The Listener could not contact Redis or retrieve well-formed data from the cache and could not start.</span></span> <span data-ttu-id="eedd2-162">Stellen Sie sicher, dass der Redis-Dienst auf dem Server gestartet und ordnungsgemäß konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="eedd2-162">Ensure the Redis service is started and configured properly on the server.</span></span>
    
  - <span data-ttu-id="eedd2-163">**10005** – Abrufen/Analysieren von Serverinformationen</span><span class="sxs-lookup"><span data-stu-id="eedd2-163">**10005** — Server info retrieval/parsing</span></span>
    
    <span data-ttu-id="eedd2-164">Die Topologieinformationen im Redis-Cache sind ungültig.</span><span class="sxs-lookup"><span data-stu-id="eedd2-164">The topology information in the Redis cache is invalid.</span></span> <span data-ttu-id="eedd2-165">Versuchen Sie zunächst, Redis und den Listener neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="eedd2-165">First, attempt to restart Redis and the Listener.</span></span> <span data-ttu-id="eedd2-166">Wenn der Fehler weiterhin besteht, schlagen Sie unter [Import the topology](deploy.md#BKMK_ImportTopology) nach, um die Topologiedaten neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eedd2-166">If the error persists, see [Import the topology](deploy.md#BKMK_ImportTopology) to recreate the topology data.</span></span>
    
- <span data-ttu-id="eedd2-167">**10100** – Redis-PING-Ausfall</span><span class="sxs-lookup"><span data-stu-id="eedd2-167">**10100** — Redis PING outage</span></span>
    
  - <span data-ttu-id="eedd2-168">**10101** – Fortgesetzter Redis-PING-Ausfall (alle 60 Sekunden)</span><span class="sxs-lookup"><span data-stu-id="eedd2-168">**10101** — Redis PING continued outage (every 60 seconds)</span></span>
    
  - <span data-ttu-id="eedd2-169">**30100** – Redis-PING-Ausfall wiederhergestellt</span><span class="sxs-lookup"><span data-stu-id="eedd2-169">**30100** — Redis PING outage restored</span></span>
    
    <span data-ttu-id="eedd2-170">Diese Fehler werden protokolliert, wenn der Listener keine Verbindung zu Redis herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="eedd2-170">These will be logged when the Listener cannot connect to Redis.</span></span> <span data-ttu-id="eedd2-171">Stellen Sie sicher, dass Redis gestartet ist und dass Netzwerkkonnektivität zwischen Listener und Redis zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="eedd2-171">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="eedd2-172">**10200** – Redis-Write-Ausfall</span><span class="sxs-lookup"><span data-stu-id="eedd2-172">**10200** — Redis Write outage</span></span>
    
  - <span data-ttu-id="eedd2-173">**10201** – Fortgesetzter Redis-Write-Ausfall (alle 60 Sekunden)</span><span class="sxs-lookup"><span data-stu-id="eedd2-173">**10201** — Redis Write outage continued (every 60 seconds)</span></span>
    
  - <span data-ttu-id="eedd2-174">**30100** – Redis-Write-Ausfall gelöst</span><span class="sxs-lookup"><span data-stu-id="eedd2-174">**30100** — Redis Write outage resolved</span></span>
    
    <span data-ttu-id="eedd2-175">Diese Fehler werden protokolliert, wenn der Listener keine Verbindung zum Redis-Cache herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="eedd2-175">These will be logged when the Listener cannot write to the Redis cache.</span></span> <span data-ttu-id="eedd2-176">Stellen Sie sicher, dass Redis gestartet ist und dass Netzwerkkonnektivität zwischen Listener und Redis zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="eedd2-176">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="eedd2-177">**30000** – Erfolgreich gestartet</span><span class="sxs-lookup"><span data-stu-id="eedd2-177">**30000** — Successfully started</span></span>
    
    <span data-ttu-id="eedd2-178">Wird bei jedem Start des Listeners protokolliert.</span><span class="sxs-lookup"><span data-stu-id="eedd2-178">Logged each time the Listener is started.</span></span>
    
- <span data-ttu-id="eedd2-179">**22000** – die Initialisierung des Statistik-Manager-Agents war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="eedd2-179">**22000** — Initialization of Statistics Manager Agent succeeded.</span></span>
    
- <span data-ttu-id="eedd2-180">**23000** – Initialisierung von „EventLogQueryManager“ war erfolgreich (beim ersten Mal oder nach Fehlversuch).</span><span class="sxs-lookup"><span data-stu-id="eedd2-180">**23000** — Initialization of EventLogQueryManager succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="eedd2-181">**24000** – Initialisierung von „serverinfo“ war erfolgreich (beim ersten Mal oder nach Fehlversuch).</span><span class="sxs-lookup"><span data-stu-id="eedd2-181">**24000** — Initialization of serverinfo succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="eedd2-182">**25000** – Listener ist nach Sendefehlversuch (oder erstem erfolgreichen Senden) wieder online.</span><span class="sxs-lookup"><span data-stu-id="eedd2-182">**25000** — Listener is back online after failing to post (or first successful post)</span></span>
    
- <span data-ttu-id="eedd2-183">**5000** – Offlinestart des Listeners für das Senden von Daten</span><span class="sxs-lookup"><span data-stu-id="eedd2-183">**5000** — Start of listener offline for posting data</span></span>
    
- <span data-ttu-id="eedd2-184">**5001** – Listener ist für längere Zeit weiterhin offline.</span><span class="sxs-lookup"><span data-stu-id="eedd2-184">**5001** — Listener is still offline for an extended period</span></span>
    
    <span data-ttu-id="eedd2-185">Diese Ereignisse können bei Überwachungs-/Benachrichtigungs-/Löschproblemen nützlich sein.</span><span class="sxs-lookup"><span data-stu-id="eedd2-185">These events can be useful for monitoring/alerting/clearing issues.</span></span>
    
## <a name="website-issues"></a><span data-ttu-id="eedd2-186">Websiteprobleme</span><span class="sxs-lookup"><span data-stu-id="eedd2-186">Website issues</span></span>
<span data-ttu-id="eedd2-187"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="eedd2-187"><a name="BKMK_Website"> </a></span></span>

- <span data-ttu-id="eedd2-188">Wiederholte Anmeldeaufforderung in Chrome – Dies war ein Fehler, der in Version 1,1 aufgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="eedd2-188">Repetitive login prompts in Chrome - this was a bug that has been resolved in version 1.1.</span></span> <span data-ttu-id="eedd2-189">Stellen Sie sicher, dass Sie auf die neueste Version des Statistik-Managers aktualisiert haben, wenn im Chrome-Browser wiederholte Anmeldeaufforderungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="eedd2-189">Be sure you have upgraded to the latest version of Statistics Manager if you are seeing repeated login prompts in the Chrome browser.</span></span> <span data-ttu-id="eedd2-190">Folgendermaßen können Sie feststellen, welche Version der Website Sie ausführen:</span><span class="sxs-lookup"><span data-stu-id="eedd2-190">To verify the version of the website you are running:</span></span>
    
  - <span data-ttu-id="eedd2-191">	Öffnen Sie im Datei-Explorer (Standardverzeichnis).</span><span class="sxs-lookup"><span data-stu-id="eedd2-191">In File Explorer, open (default directory)</span></span>
    
  - <span data-ttu-id="eedd2-192">Klicken Sie mit der rechten Maustaste auf „StatsManHubWebSite.dll“ und lassen Sie die entsprechenden Eigenschaften anzeigen.</span><span class="sxs-lookup"><span data-stu-id="eedd2-192">Right click on StatsManHubWebSite.dll and view its properties.</span></span>
    
  - <span data-ttu-id="eedd2-193">Wenn ein Computer in der KHI-Querformatansicht oder der Zählerangabenansicht nicht gefunden werden kann, stellen Sie sicher, dass der Computer Mitglied einer Website und eines Pools ist.</span><span class="sxs-lookup"><span data-stu-id="eedd2-193">If a computer cannot be found in the KHI Landscape view or the Counter Details view, make sure it is a member of a Site and a Pool.</span></span> <span data-ttu-id="eedd2-194">Ist er das nicht, taucht er in diesen Ansichten auch nicht auf.</span><span class="sxs-lookup"><span data-stu-id="eedd2-194">If it is not, it will not appear in those views.</span></span> <span data-ttu-id="eedd2-195">Mehr über die Definition einer Website und eines Pools für einen Server in der Topologie erfahren Sie unter [Import the topology](deploy.md#BKMK_ImportTopology).</span><span class="sxs-lookup"><span data-stu-id="eedd2-195">For information about defining a site and pool for a server in the topology, see [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="eedd2-196">Die Produktversion wird unter den Beschreibungsangaben angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eedd2-196">The product version will be shown in the Description details.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="eedd2-197">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eedd2-197">For more information</span></span>
<span data-ttu-id="eedd2-198"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="eedd2-198"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="eedd2-199">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="eedd2-199">For more information, see the following:</span></span>
  
- [<span data-ttu-id="eedd2-200">Planen von Statistics Manager für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="eedd2-200">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="eedd2-201">Bereitstellen von Statistics Manager für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="eedd2-201">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="eedd2-202">Aktualisieren von Statistics Manager für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="eedd2-202">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
