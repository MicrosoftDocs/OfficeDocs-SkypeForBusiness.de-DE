---
title: Problembehandlung bei Ihrer Cloud Connector-Bereitstellung
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom:
- Strat_SB_Hybrid
- Strat_SB_Hybrid
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Problembehandlung bei der Cloud Connector Edition-Bereitstellung.
ms.openlocfilehash: 1fb4f65c0fefd335865c5babb0e69090ab824908
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="68112-103">Problembehandlung bei Ihrer Cloud Connector-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="68112-103">Troubleshoot your Cloud Connector deployment</span></span>
 
<span data-ttu-id="68112-104">Problembehandlung bei der Cloud Connector Edition-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="68112-104">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="68112-p101">In diesem Thema werden Lösungen für allgemeine Probleme bei Cloud Connector Edition-Bereitstellungen beschrieben. Wenn Probleme mit Anrufen an das und aus dem Telefonfestnetz (Public Switched Telephone Network, PSTN) auftreten, können Sie diese anhand der in diesem Thema beschriebenen Lösungen untersuchen.</span><span class="sxs-lookup"><span data-stu-id="68112-p101">This topic describes solutions to common issues with Cloud Connector Edition deployments. If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="68112-107">Cloud-Connector bietet integrierte Mechanismen zur Problembehebung einige automatisch.</span><span class="sxs-lookup"><span data-stu-id="68112-107">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="68112-108">Ein Prozess, der automatischen Erkennung sucht nach potenziellen Problemen mit der Cloud Connector Appliances und, falls möglich, dauert Maßnahme zum Beheben dieser Probleme ohne Eingriffe Administrator.</span><span class="sxs-lookup"><span data-stu-id="68112-108">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="68112-109">So funktioniert der Erkennungsprozess:</span><span class="sxs-lookup"><span data-stu-id="68112-109">The detection process works as follows:</span></span>
  
- <span data-ttu-id="68112-110">**Erkennung Sequenz:** Der Verwaltung des Connector-Cloud-Dienst ausgeführt wird einen Prozess alle 60 Sekunden, um festzustellen, ob eine Einheit ausgefallen ist.</span><span class="sxs-lookup"><span data-stu-id="68112-110">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="68112-111">In der Cloud Connector, Version 2.0 und höher verwendet der Erkennungsprozess die Skype für Business Corpnet Schalter zum Beschleunigen des PowerShell-Verbindungen mit der Cloud Connector-Computern. für Versionen vor 2.0 verwendet der Erkennungsprozess Schalters Management Cloud-Connector.</span><span class="sxs-lookup"><span data-stu-id="68112-111">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="68112-112">Für die automatische Wiederherstellung erfolgreich ausgeführt werden kann muss Netzwerkkonnektivität zwischen dem Host und dem virtuellen Computer über die Host-Netzwerkswitch vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="68112-112">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="68112-113">Netzwerkkonnektivität, um sicherzustellen, automatische Erkennung überprüfen und die Wiederherstellung erfolgreich ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="68112-113">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="68112-114">**Überwachung:** Die folgenden Dienste werden in der Cloud Connector, Version 2.0 und höher überwacht:</span><span class="sxs-lookup"><span data-stu-id="68112-114">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="68112-115">Virtuelle Computer sind nicht auf die Cloud-Connector im Unternehmen oder virtuelle Switches Internet verbunden</span><span class="sxs-lookup"><span data-stu-id="68112-115">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="68112-116">Virtuelle Computer werden im Status gespeichert oder beendet</span><span class="sxs-lookup"><span data-stu-id="68112-116">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="68112-117">Zentralen Verwaltungsserver Diensten: REPLIKAT, Master-Shape</span><span class="sxs-lookup"><span data-stu-id="68112-117">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="68112-118">Mediation Server-Dienste: REPLIKAT, RTCSRV und MEDSVC</span><span class="sxs-lookup"><span data-stu-id="68112-118">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="68112-119">Edge-Server-Dienste: REPLIKAT, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="68112-119">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="68112-120">Firewall, die Regeln für CS RTCSRV, klicken Sie auf Edgeserver CS RTCMEDSRV auf Vermittlungsserver deaktiviert sind, eingehend</span><span class="sxs-lookup"><span data-stu-id="68112-120">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="68112-121">In der Cloud Connector Version 1.4.2 werden nur die folgenden Dienste überwacht:</span><span class="sxs-lookup"><span data-stu-id="68112-121">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="68112-122">Mediation Server-Dienste: RTCSRV und MEDSVC</span><span class="sxs-lookup"><span data-stu-id="68112-122">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="68112-123">Edge-Server-Dienst: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="68112-123">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="68112-124">**Wiederherstellungsprozess:** Wenn alle überwachten Dienste nach unten sind, eine Einheit nach unten markiert ist, und Dienste beendet und manuelle gekennzeichnet, bis alle Probleme aufgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="68112-124">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="68112-125">Dadurch wird verhindert, dass Anrufe vom routing an ein Gerät, das anruffehlern führen kann.</span><span class="sxs-lookup"><span data-stu-id="68112-125">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="68112-126">Der Cloud Connector-Verwaltungsdienst wird automatische Wiederherstellung wie folgt wiederholen.</span><span class="sxs-lookup"><span data-stu-id="68112-126">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="68112-127">Das ursprüngliche Wiederholungsintervall wird alle zehn Sekunden mit einer maximalen Intervall von einer Stunde.</span><span class="sxs-lookup"><span data-stu-id="68112-127">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="68112-128">Für die ersten drei Wiederherstellungsversuche ist das Intervall 10 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="68112-128">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="68112-129">Die vierte wiederholen beginnend, erhöht zweimal der vorherigen Intervall Interval Time.</span><span class="sxs-lookup"><span data-stu-id="68112-129">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="68112-130">Beispielsweise wird der vierte Wiederholungsversuch treten in 20 Sekunden, das fünfte in 40 Sekunden usw.</span><span class="sxs-lookup"><span data-stu-id="68112-130">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="68112-131">Wenn die maximale Intervall von einer Stunde erreicht ist, werden einmal pro Stunde Wiederholungsversuche fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="68112-131">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="68112-132">Wenn die Wiederherstellung erfolgreich ist, werden die Zähler Intervall und "Wiederholen" auf die Anfangswerte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="68112-132">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="68112-133">Wenn der Verwaltungsdienst gestartet wird, werden die Zähler Intervall und "Wiederholen" auf die Anfangswerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="68112-133">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="68112-134">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="68112-134">Troubleshooting</span></span>

<span data-ttu-id="68112-135">Es folgen Lösungen zu häufig auftretenden Problemen:</span><span class="sxs-lookup"><span data-stu-id="68112-135">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="68112-136">**Problem: Die Bereitstellung schlägt fehl oder reagiert nicht mehr, wenn die Bereitstellungsskripts ausgeführt werden. Nach der Anmeldung bei den einzelnen VMs fehlt die IP-Adresse oder ist falsch für die Verwaltungs-/interne/externe Netzwerkkarte.**</span><span class="sxs-lookup"><span data-stu-id="68112-136">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="68112-137">**Lösung:** Dieses Problem kann nicht automatisch aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="68112-137">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="68112-138">Während der Ausführung der VMs können diesen keine NICs hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="68112-138">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="68112-139">Fahren Sie diese VMs im Hyper-V-Manager herunter und entfernen Sie sie, und führen Sie anschließend die folgenden Cmdlets aus:</span><span class="sxs-lookup"><span data-stu-id="68112-139">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```
  Uninstall-CcAppliance
  ```

  ```
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="68112-140">**Problem: Wenn der Active Directory-Server und der Gesamtstruktur installiert sind, die CMS-Server und/oder Vermittlungsserver der Domäne nicht ordnungsgemäß hinzugefügt.**</span><span class="sxs-lookup"><span data-stu-id="68112-140">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="68112-141">**Lösung:** Um dieses Problem zu beheben, führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="68112-141">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="68112-142">Melden Sie sich beim Active Directory-Server an, und überprüfen Sie, ob die Domäne ordnungsgemäß erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="68112-142">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="68112-143">Melden Sie sich beim CMS bzw. beim Vermittlungsserver an, und überprüfen Sie, ob der Netzwerkkarte des Unternehmensnetzwerks eine gültige IP-Adresse zugewiesen wurde und ob eine gültige statische IP und ein DNS als IP-Adresse des AD-Servers konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="68112-143">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="68112-144">Melden Sie sich an den CMS/Vermittlungsserver, und öffnen Sie ein Eingabeaufforderungsfenster.</span><span class="sxs-lookup"><span data-stu-id="68112-144">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="68112-145">Stellen Sie sicher, dass Sie den FQDN und IP-Adresse des Active Directory-Servers Ping ausführen können.</span><span class="sxs-lookup"><span data-stu-id="68112-145">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="68112-146">Wenn dies nicht möglich ist, kann ein Konflikt der IP-Adresse vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="68112-146">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="68112-147">Versuchen Sie, weisen Sie eine neue IP-Adresse für Active Directory und DNS entsprechend auf dem CMS/Vermittlungsserver zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="68112-147">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="68112-148">**Problem: Sie erhalten die folgende Fehlermeldung "Remove-VMSwitch: Fehler beim virtuellen Ethernet-Switch zu entfernen. Für der virtuelle Switch 'Cloud Connector Management Schalter' kann nicht gelöscht, da sie durch Ausführen von virtuellen Computern verwendet wird, oder in untergeordneten Pools zugewiesen."**</span><span class="sxs-lookup"><span data-stu-id="68112-148">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="68112-149">**Lösung:** "Cloud Connector Management Switch" wurde nach der Bereitstellung nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="68112-149">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="68112-150">Wenn Sie auf diesen Fehler stoßen, gehen Sie zu Hyper-V-Manager und überprüfen Sie, ob nicht noch ein virtueller Computer damit verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="68112-150">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="68112-151">Wenn noch virtuelle Computer verbunden sind, trennen Sie sie und löschen den Verwaltungs-Switch.</span><span class="sxs-lookup"><span data-stu-id="68112-151">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="68112-152">Wenn der Verwaltungs-Switch immer noch nicht gelöscht werden kann, starten Sie den Hostserver neu und versuchen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="68112-152">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="68112-153">**Problem: Sie erhalten die folgende Fehlermeldung angezeigt, "Dienst RTCMRAUTH konnte nicht gestartet. Stellen Sie sicher, dass der Dienst nicht deaktiviert ist."**</span><span class="sxs-lookup"><span data-stu-id="68112-153">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="68112-154">Dieses Problem betrifft nur Cloud Connector-Versionen vor 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="68112-154">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="68112-p110">Der Startfehler kann auch darauf zurückzuführen sein, dass für diesen Front End-Server zuvor ein Failover (Computer-Failover) durchgeführt wurde. In diesem Fall sollten Sie ein Failback (Computer-Failback) starten.</span><span class="sxs-lookup"><span data-stu-id="68112-p110">The failure to start could also be because this Front End server was previously failed over (using computer fail over). If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="68112-p111">**Lösung:** Dieser Fehler tritt auf einem Edgeserver auf, wenn der Edgeserver dem Zertifikat der Stammzertifizierungsstelle oder dem Zertifikat der Zwischenzertifizierungsstelle nicht vertraut. Selbst wenn ein externes Zertifikat importiert werden kann, ist die Zertifizierungskette unterbrochen. Unter dieser Bedingung kann der RTCMRAUTH- bzw. der RTCSRV-Dienst nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="68112-p111">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server. Even if the external certificate can be imported but the certificate chain is broken. Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="68112-p112">Importieren Sie das Zertifikat der Stammzertifizierungsstelle und alle Zertifikate der Zwischenzertifizierungsstelle Ihres externen Zertifikats manuell auf den Edgeserver, und starten Sie den Edgeserver anschließend neu. Wenn die Dienste RTCMRAUTH und RTCSRV auf dem Edgeserver gestartet werden, navigieren Sie zu Ihrem Hostserver, starten Sie eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus, um zur neuen Bereitstellung zu wechseln:</span><span class="sxs-lookup"><span data-stu-id="68112-p112">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server. After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="68112-162">**Problem: Der Hostserver wurde nach dem Anwenden von Windows-Updates neu gestartet, und vom Server verarbeitete Anrufe sind fehlgeschlagen.**</span><span class="sxs-lookup"><span data-stu-id="68112-162">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="68112-163">**Lösung:** Wenn Sie eine hohe Verfügbarkeit-Umgebung bereitgestellt, stellt Microsoft ein Cmdlet, mit denen eine Hostcomputer (Bereitstellung Instanz) verschieben zu oder aus der aktuellen Topologie beim Überprüfen und installieren Sie Windows Update manuell.</span><span class="sxs-lookup"><span data-stu-id="68112-163">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="68112-164">Führen Sie hierzu die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="68112-164">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="68112-165">Starten Sie auf dem Hostserver eine PowerShell-Konsole als Administrator, und führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="68112-165">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
  ```
  Enter-CcUpdate
  ```

2. <span data-ttu-id="68112-166">Suchen und installieren Sie alle verfügbaren Updates.</span><span class="sxs-lookup"><span data-stu-id="68112-166">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="68112-167">Führen Sie in der PowerShell-Konsole das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="68112-167">In the PowerShell console, run the following cmdlet:</span></span>
    
  ```
  Exit-CcUpdate
  ```

- 
    
    <span data-ttu-id="68112-168">**Problem: Wenn ein Anruf über einen Skype for Business-Client mit einer PSTN-Nummer getätigt wird, kann der Anruf nicht durch Einladen einer anderen PSTN-Nummer zu einer Konferenz eskaliert werden.**</span><span class="sxs-lookup"><span data-stu-id="68112-168">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="68112-169">**Lösung:** Zum Beheben dieses Problems finden Sie unter [Konfigurieren von hybridem online Mediation Server-Einstellungen](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span><span class="sxs-lookup"><span data-stu-id="68112-169">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="68112-170">**Problem: Eine Warnmeldung zum Windows-Update wird angezeigt, wenn Sie Active Directory-Server installieren: „Die automatische Aktualisierung von Windows ist nicht aktiviert. Aktivieren Sie "Windows Update", um sicherzustellen, dass die neu installierte Rolle oder das neu installierte Feature automatisch aktualisiert wird.“**</span><span class="sxs-lookup"><span data-stu-id="68112-170">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="68112-171">**Lösung:** Starten einer Mandanten Remote-PowerShell-Sitzung mithilfe der Skype für Business Mandanten-Admin-Anmeldeinformationen, und führen Sie das folgende Cmdlet aus, um die _EnableAutoUpdate_ -Konfiguration Ihrer Website zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="68112-171">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="68112-172">Wenn _EnableAutoUpdate_ auf **True**festgelegt ist, können Sie diese Warnung ignorieren, da der Dienst CCEManagement herunterladen und Installieren von Windows-Updates für virtuelle Computer und den Hostserver behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="68112-172">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="68112-173">Wenn _EnableAutoUpdate_ auf **False**festgelegt ist, führen Sie folgende Cmdlet auf **True**festlegen.</span><span class="sxs-lookup"><span data-stu-id="68112-173">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="68112-p115">Alternativ dazu können Sie Updates manuell suchen und installieren. Informationen hierzu finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="68112-p115">Alternatively, you can manually check for and install updates. See the next section.</span></span>
    
- <span data-ttu-id="68112-176">**Problem: Sie erhalten eine Fehlermeldung angezeigt: Appliance kann nicht registriert werden, da der aktuellen Input-Konfiguration \<SiteName\> oder \<ApplianceName\> oder \<Mediation Server-FQDN\> oder \<Mediation Server-IP-Adresse \> steht in Konflikt mit vorhandenen Einheiten. Entfernen Sie Konflikt Appliance oder aktualisieren Sie Ihre Informationen Input-Konfiguration, und klicken Sie dann erneut zu registrieren. "beim Ausführen von Register-CcAppliance, um aktuelle Appliance online zu registrieren.**</span><span class="sxs-lookup"><span data-stu-id="68112-176">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="68112-177">**Lösung:** Werte für die \<ApplianceName\>, \<Mediation Server-FQDN\> und \<Mediation Server-IP-Adresse\> muss eindeutig und nur für die Registrierung einer Appliance verwendet.</span><span class="sxs-lookup"><span data-stu-id="68112-177">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="68112-178">In der Standardeinstellung \<ApplianceName\> stammen aus den Hostnamen.</span><span class="sxs-lookup"><span data-stu-id="68112-178">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="68112-179">\<Mediation Server-FQDN\> und \<Mediation Server-IP-Adresse\> Konfiguration Ini-Datei definiert.</span><span class="sxs-lookup"><span data-stu-id="68112-179">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="68112-180">Wenn Sie beispielsweise (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) zum Registrieren von SiteName=MySite verwenden, aber eine registrierte Appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) vorhanden ist, tritt ein Konflikt auf.</span><span class="sxs-lookup"><span data-stu-id="68112-180">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="68112-181">Überprüfen Sie zunächst die Datei „CloudConnector.ini“ im ApplianceRoot-Verzeichnisabschnitt.</span><span class="sxs-lookup"><span data-stu-id="68112-181">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="68112-182">Sie erhalten \<SiteName\>, \<Mediation Server-FQDN\> und \<Mediation Server-IP-Adresse\> Werte in der Datei.</span><span class="sxs-lookup"><span data-stu-id="68112-182">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="68112-183">\<ApplianceName\> ist der Hostname der Server.</span><span class="sxs-lookup"><span data-stu-id="68112-183">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="68112-184">Zweitens führen starten Mandanten Remote-PowerShell mit Ihrer Skype für Business Mandanten Administratoranmeldeinformationen, Sie das folgende Cmdlet aus, um die registrierten Einheiten zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="68112-184">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="68112-185">Nach der Überprüfung aller Konflikte können Sie die Datei „CloudConnector.ini“ mit den Informationen aktualisieren, die mit der registrierten Appliance übereinstimmen, oder die Registrierung der vorhandenen Appliance aufheben, um die Konflikte zu beheben.</span><span class="sxs-lookup"><span data-stu-id="68112-185">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```
  Unregister-CsHybridPSTNAppliance -Force
  ```

- 
    
    <span data-ttu-id="68112-186">**Problem: Das Cmdlet Get-CcRunningVersion gibt einen leeren Wert zurück, wenn eine auf dem Host bereitgestellten Appliance vorhanden ist.**</span><span class="sxs-lookup"><span data-stu-id="68112-186">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
    <span data-ttu-id="68112-p118">**Lösung:** Dieser Fall kann eintreten, wenn Sie ein Upgrade von 1.3.4 oder 1.3.8 auf 1.4.1 durchführen. Nach der Installation von Version 1.4.1 mit der MSI-Datei müssen Sie `Register-CcAppliance` ausführen, bevor Sie ein anderes Cmdlet ausführen. `Register-CcAppliance` migriert die module.ini-Datei von %UserProfile%\CloudConnector auf %ProgramData%\CloudConnector. Wenn Sie diesen Vorgang nicht durchführen, wird eine neue module.ini-Datei im Ordner %ProgramData%\CloudConnector erstellt, und die Informationen der laufenden bzw. der Sicherungsversion für 1.3.4 oder 1.3.8 werden ersetzt.</span><span class="sxs-lookup"><span data-stu-id="68112-p118">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1. After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet. `Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector. If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
    <span data-ttu-id="68112-191">Vergleichen Sie die Dateien im Ordner %UserProfile%\CloudConnector und %ProgramData%\CloudConnector module.ini.</span><span class="sxs-lookup"><span data-stu-id="68112-191">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="68112-192">Wenn Unterschiede vorhanden sind, löschen Sie die Datei module.ini in %ProgramData%\CloudConnector und erneut ausführen `Register-CcAppliance`.</span><span class="sxs-lookup"><span data-stu-id="68112-192">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="68112-193">Sie können auch die Datei manuell fest, um die korrekte Ausführung und Sicherungsversion ändern.</span><span class="sxs-lookup"><span data-stu-id="68112-193">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="68112-194">**Problem: Nach der Ausführung des Switch-CcVersion-Cmdlets, um eine ältere Version wechseln, der aktuelle Version des Skripts unterscheidet, wird keine hohe Verfügbarkeit unterstützt für die alte Version.**</span><span class="sxs-lookup"><span data-stu-id="68112-194">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="68112-195">**Lösung:** Sie haben beispielsweise von 1.4.1 auf 1.4.2 aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="68112-195">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="68112-196">Die aktuelle Skriptversion, die durch Ausführen von ermittelt werden kann `Get-CcVersion`, und Ihre ausgeführt wird, die durch Ausführen von ermittelt werden kann `Get-CcRunningVersion` sind beide 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="68112-196">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="68112-197">Wenn Sie zu diesem Zeitpunkt `Switch-CcVersion` ausführen, um die zurzeit ausgeführte Version auf Version 1.4.1 zurückzusetzen, wird hohe Verfügbarkeit für diese ältere Version nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="68112-197">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="68112-p121">Um die vollständige Unterstützung von hoher Verfügbarkeit zu erhalten, müssen Sie zurück zu Version 1.4.2 wechseln, damit die zurzeit ausgeführte Version mit der Skriptversion übereinstimmt. Wenn bei Ihrer 1.4.2-Bereitstellung Probleme auftreten, deinstallieren Sie die Version, und installieren Sie sie umgehend neu.</span><span class="sxs-lookup"><span data-stu-id="68112-p121">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same. If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="68112-200">**Problem: Zertifizierungsstellenzertifikate oder interne Zertifikate, die für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver ausgestellt wurden, laufen in Kürze ab oder sind kompromittiert.**</span><span class="sxs-lookup"><span data-stu-id="68112-200">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="68112-p122">**Lösung:** Zertifizierungsstellenzertifikate für Skype for Business sind fünf Jahre lang gültig. Für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver ausgestellte interne Zertifikate sind zwei Jahre lang gültig.</span><span class="sxs-lookup"><span data-stu-id="68112-p122">**Resolution:** Skype for Business certification authority certificates are valid for five years. Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="68112-203">In der Cloud Connector, Version 2.0 und höher das Erneuern CcServerCertificate-Cmdlet Update-CcServerCertificate geändert hat, und das Erneuern CcCACertificate-Cmdlet Update-CcCACertificate geändert hat.</span><span class="sxs-lookup"><span data-stu-id="68112-203">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="68112-204">Wenn interne Zertifikaten für den zentralen Verwaltungsspeicher, Vermittlungsserver und Edge-Server in der Nähe Ablauf sind oder gefährdet ist, führen Sie die erneuern CcServerCertificate oder Update-CcServerCertificate-Cmdlet, um Ihre Zertifikate zu erneuern.</span><span class="sxs-lookup"><span data-stu-id="68112-204">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="68112-205">Wenn Zertifikate von Zertifizierungsstellen in Ihrer Nähe Ablauf sind, führen Sie das Erneuern CcCACertificate oder Update-CcCACertificate-Cmdlet, um Ihre Zertifikate erneuern.</span><span class="sxs-lookup"><span data-stu-id="68112-205">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="68112-206">**Wenn Zertifikate von Zertifizierungsstellen sind beschädigt, und es nur ein einziges Gerät in der Website ist** ausführen die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="68112-206">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="68112-207">Führen Sie das Cmdlet „Enter-CcUpdate“ aus, um Dienste auszugleichen und die Appliance in den Wartungsmodus zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="68112-207">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
    
2. <span data-ttu-id="68112-208">Führen Sie die folgenden Cmdlets aus, um die Zertifizierungsstellenzertifikate und alle internen Serverzertifikate zurückzusetzen und neu zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="68112-208">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="68112-209">Cloud-Connector-Versionen vor 2.0:</span><span class="sxs-lookup"><span data-stu-id="68112-209">For Cloud Connector releases before 2.0:</span></span>
    
  ```
  Reset-CcCACertificate 
Renew-CcServerCertificate 
Remove-CcLegacyServerCertificate 

  ```

    <span data-ttu-id="68112-210">Oder Cloud Connector, Version 2.0 und höher:</span><span class="sxs-lookup"><span data-stu-id="68112-210">Or for Cloud Connector release 2.0 and later:</span></span>
    
  ```
  Reset-CcCACertificate 
Update-CcServerCertificate 
Remove-CcLegacyServerCertificate 

  ```

3. <span data-ttu-id="68112-211">Führen Sie das Cmdlet „Exit-CcUpdate“ aus, um Dienste zu starten und den Wartungsmodus zu beenden.</span><span class="sxs-lookup"><span data-stu-id="68112-211">Run the Exit-CcUpdate cmdlet to start services and and exit maintenance mode.</span></span>
    
4. <span data-ttu-id="68112-212">Führen Sie das Cmdlet Export-CcRootCertificate für die lokale Datei in der Einheit, und klicken Sie dann kopieren Sie, und installieren Sie das exportierte Zertifikat zu PSTN-Gateways.</span><span class="sxs-lookup"><span data-stu-id="68112-212">Run the Export-CcRootCertificate cmdlet on the local file in the appliance, and then copy and install the exported certificate to your PSTN gateways.</span></span>
    
    <span data-ttu-id="68112-213">Führen Sie folgende Schritte für jede Anwendung in der Website, **Wenn Zertifikate von Zertifizierungsstellen sind beschädigt, und es mehrere Einheiten auf der Website gibt** .</span><span class="sxs-lookup"><span data-stu-id="68112-213">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="68112-214">Microsoft empfiehlt, dass Sie diese Schritte nicht spitzenauslastung Zeiten ausführen.</span><span class="sxs-lookup"><span data-stu-id="68112-214">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
  - <span data-ttu-id="68112-215">Führen Sie auf der ersten Appliance das Cmdlet Remove-CcCertificationAuthorityFile zum Bereinigen von der Zertifizierungsstelle Sichern von Dateien in die \<SiteRoot\> Directory.</span><span class="sxs-lookup"><span data-stu-id="68112-215">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>
    
  - <span data-ttu-id="68112-216">Führen Sie das Cmdlet EINGABETASTE CcUpdate abzuleiten Dienste, und platzieren Sie jede Anwendung im Wartungsmodus aus.</span><span class="sxs-lookup"><span data-stu-id="68112-216">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>
    
  - <span data-ttu-id="68112-217">Führen Sie die folgenden Cmdlets aus, um die Zertifizierungsstellenzertifikate und alle internen Serverzertifikate zurückzusetzen und neu zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="68112-217">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="68112-218">Cloud-Connector-Versionen vor 2.0:</span><span class="sxs-lookup"><span data-stu-id="68112-218">For Cloud Connector releases before 2.0:</span></span>
    
  ```
  Reset-CcCACertificate
Renew-CcServerCertificate
Remove-CcLegacyServerCertificate 

  ```

    <span data-ttu-id="68112-219">Oder Cloud Connector, Version 2.0 und höher:</span><span class="sxs-lookup"><span data-stu-id="68112-219">Or for Cloud Connector release 2.0 and later:</span></span>
    
  ```
  Reset-CcCACertificate
Update-CcServerCertificate
Remove-CcLegacyServerCertificate 

  ```

  - <span data-ttu-id="68112-220">Führen Sie auf der ersten Appliance So sichern Sie die Zertifizierungsstellen-Dateien in das folgende Cmdlet der \<SiteRoot\> Ordner.</span><span class="sxs-lookup"><span data-stu-id="68112-220">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span> <span data-ttu-id="68112-221">Auf allen anderen Einheiten am gleichen Standort später mit dem Cmdlet Reset-CcCACertificate nutzen die Sicherungsdateien der Zertifizierungsstelle automatisch und Appliances verwendet das-Stammzertifikat.</span><span class="sxs-lookup"><span data-stu-id="68112-221">Later, on all other appliances in the same site, the Reset-CcCACertificate cmdlet will consume the CA backup files automatically and appliances will use the same root certificate.</span></span>
    
  ```
  Backup-CcCertificationAuthority
  ```

  - <span data-ttu-id="68112-222">Führen Sie das Exit-CcUpdate-Cmdlet, um Dienste starten und Beenden im Wartungsmodus befindet.</span><span class="sxs-lookup"><span data-stu-id="68112-222">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 
    
  - <span data-ttu-id="68112-223">Wenn TLS zwischen dem Gateway und dem Vermittlungsserver verwendet wird, führen Sie das Cmdlet Export-CcRootCertificate aus jeder Anwendung auf der Website, und installieren Sie das exportierte Zertifikat auf PSTN-Gateways.</span><span class="sxs-lookup"><span data-stu-id="68112-223">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> 
    
- <span data-ttu-id="68112-224">**Problem: Erhalten Sie die folgende Fehlermeldung angezeigt, in der Cloud Connector Management Service-Protokoll, "C:\Programme\Microsoft Files\Skype für Business Cloud Connector Edition\ManagementService\CceManagementService.log": Fehler CceService: 0: Unerwartete Ausnahme beim Statusberichte zu online: System.Management.Automation.CmdletInvocationException: Fehler bei der Anmeldung für den Benutzer \<globaler Administrator\>. Erstellen Sie ein neues Credential-Objekt, und stellen Sie sicher, dass Sie den richtigen Benutzernamen und das Kennwort verwendet haben. ---\>**</span><span class="sxs-lookup"><span data-stu-id="68112-224">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="68112-225">**Lösung:** Die Office 365-Mandanten globale Administratorinformationen wurden geändert, seit die Cloud Connector Appliance registriert wurde.</span><span class="sxs-lookup"><span data-stu-id="68112-225">**Resolution:** The Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="68112-226">Führen Sie zum Aktualisieren der lokal gespeicherten Anmeldeinformationen für die Cloud Connector Appliance Folgendes über Administrator PowerShell in der Host-Anwendung:</span><span class="sxs-lookup"><span data-stu-id="68112-226">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```
  Set-CcCredential -AccountType TenantAdmin
  ```

- 
    
    <span data-ttu-id="68112-227">**Problem: Nachdem Sie das Kennwort für das Host-Server-Konto Sie für die Bereitstellung verwendet ändern, Sie erhalten Sie die folgende Fehlermeldung angezeigt: "ConvertTo-SecureString: Schlüssel ist nicht gültig für die Verwendung in angegebenen Zustand." in %ProgramFiles%\Skype für Business Cloud-Connector Edition\ManagementService\CceManagementService.log oder beim Ausführen des Cmdlets Get-CcCredential.**</span><span class="sxs-lookup"><span data-stu-id="68112-227">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="68112-228">**Lösung:** Alle Cloud Connector Anmeldeinformationen werden in der folgenden Datei gespeichert: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ".</span><span class="sxs-lookup"><span data-stu-id="68112-228">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="68112-229">Wenn das Kennwort für den Hostserver geändert wird, müssen Sie die lokal gespeicherten Anmeldeinformationen aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="68112-229">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="68112-230">**Wenn Sie Cloud Connector Version 1.4.2 ausführen** generieren aller Cloud Connector-Kennwörter folgende Schritte neu:</span><span class="sxs-lookup"><span data-stu-id="68112-230">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
1. <span data-ttu-id="68112-231">Starten Sie den Hostserver neu.</span><span class="sxs-lookup"><span data-stu-id="68112-231">Restart the host server.</span></span>
    
2. <span data-ttu-id="68112-232">Löschen Sie die folgende Datei: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ".</span><span class="sxs-lookup"><span data-stu-id="68112-232">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
3. <span data-ttu-id="68112-233">Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie "Register-CcAppliance-lokale" die Kennwörter die Beschreibung nach erneut eingeben.</span><span class="sxs-lookup"><span data-stu-id="68112-233">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="68112-234">Geben Sie die gleichen Kennwörter eingegebene vor dem für die Bereitstellung von Cloud-Connector ein.</span><span class="sxs-lookup"><span data-stu-id="68112-234">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
    <span data-ttu-id="68112-235">**Wenn Sie Cloud Connector, Version 2.0 oder höher, ausführen** neu zu generieren aller Cloud Connector Kennwörter folgende Schritte:</span><span class="sxs-lookup"><span data-stu-id="68112-235">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
1. <span data-ttu-id="68112-236">Starten Sie den Hostserver neu.</span><span class="sxs-lookup"><span data-stu-id="68112-236">Restart the host server.</span></span>
    
2. <span data-ttu-id="68112-237">Löschen Sie die folgende Datei: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ".</span><span class="sxs-lookup"><span data-stu-id="68112-237">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
3. <span data-ttu-id="68112-238">Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie "Register-CcAppliance-lokale" die Kennwörter die Beschreibung nach erneut eingeben.</span><span class="sxs-lookup"><span data-stu-id="68112-238">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="68112-p127">Wenn die zwischengespeicherte Kennwortdatei mit Cloud Connector, Version 1.4.2, generiert wurde, verwenden Sie das „VMAdmin“-Kennwort als „CceService“-Kennwort, wenn Sie danach gefragt werden. Geben Sie das gleiche Kennwort ein, das Sie vor der Cloud Connector-Bereitstellung für alle anderen Konten eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="68112-p127">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted. Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
    <span data-ttu-id="68112-241">Wenn die zwischengespeicherte Kennwortdatei mit Cloud Connector, Version 1.4.2, generiert wurde und die Kennwörter von „DomainAdmin“ und „VMAdmin“ nicht übereinstimmen, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="68112-241">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
1. <span data-ttu-id="68112-242">Führen Sie „Set-CcCredential -AccountType DomainAdmin“ wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="68112-242">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="68112-243">Wenn Sie zur Eingabe der alten Anmeldeinformationen für das Konto aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das „CceService“-Kennwort verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="68112-243">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="68112-244">Wenn Sie zur Eingabe der neuen Anmeldeinformationen für das Konto aufgefordert werden, geben Sie das zuvor verwendete Kennwort für „DomainAdmin“ ein.</span><span class="sxs-lookup"><span data-stu-id="68112-244">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
    <span data-ttu-id="68112-245">Die zwischengespeicherten Kennwortdatei mit Cloud-Connector, Version 2.0 oder höher, standardmäßig generiert wurde, verwenden VmAdmin und DomainAdmin "als CceService dasselbe Kennwort.</span><span class="sxs-lookup"><span data-stu-id="68112-245">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="68112-246">Wenn Sie die Kennwörter "DomainAdmin" und VMAdmin geändert haben, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="68112-246">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
1. <span data-ttu-id="68112-247">Führen Sie „Set-CcCredential -AccountType DomainAdmin“ wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="68112-247">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="68112-248">Wenn Sie zur Eingabe der alten Anmeldeinformationen für das Konto aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das „CceService“-Kennwort verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="68112-248">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
2. <span data-ttu-id="68112-249">Wenn Sie zur Eingabe der neuen Anmeldeinformationen für das Konto aufgefordert werden, geben Sie das zuvor verwendete Kennwort für „DomainAdmin“ ein.</span><span class="sxs-lookup"><span data-stu-id="68112-249">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
2. <span data-ttu-id="68112-250">Führen Sie „Set-CcCredential -AccountType VmAdmin“ wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="68112-250">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="68112-251">Wenn Sie zur Eingabe der alten Anmeldeinformationen für das Konto aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das „CceService“-Kennwort verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="68112-251">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
2. <span data-ttu-id="68112-252">Wenn Sie zur Eingabe der neuen Anmeldeinformationen für das Konto aufgefordert werden, geben Sie das zuvor verwendete Kennwort für „VmAdmin“ ein. </span><span class="sxs-lookup"><span data-stu-id="68112-252">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- 
    
    <span data-ttu-id="68112-253">**Problem: Mit Cloud-Connector Version 2.1 oder höher, bei der Ausführung von Register-CcAppliance oder anderen Cmdlets auf der Appliance Sie erhalten eine Fehlermeldung wie etwa: "für jedes Objekt: die Eigenschaft"Common"nicht werden für dieses Objekt gefunden kann. Stellen Sie sicher, dass die Eigenschaft vorhanden ist. Unter C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 Char: 14 "**</span><span class="sxs-lookup"><span data-stu-id="68112-253">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="68112-254">**Lösung:** Cloud-Connector 2.1 und höher erfordert .NET Framework 4.6.1 oder höher.</span><span class="sxs-lookup"><span data-stu-id="68112-254">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="68112-255">Aktualisieren Sie .NET Framework auf die Appliance 4.6.1 Version oder höher, und führen Sie die Cmdlet(s) erneut aus.</span><span class="sxs-lookup"><span data-stu-id="68112-255">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>
    
- <span data-ttu-id="68112-256">**Problem: Sie erhalten die folgende Fehlermeldung "Dismount-WindowsImage: Dismount-WindowsImage ist fehlgeschlagen. Fehlercode = 0xc1550115 "beim Installieren oder Aktualisieren von Cloud-Connector Edition.**</span><span class="sxs-lookup"><span data-stu-id="68112-256">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="68112-257">**Lösung:** Starten Sie eine PowerShell-Konsole als Administrator ausführen "DISM-Cleanup-Wim'".</span><span class="sxs-lookup"><span data-stu-id="68112-257">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="68112-258">Dadurch werden alle Bilder einwandfreien bereinigt werden.</span><span class="sxs-lookup"><span data-stu-id="68112-258">This will clean up all troubled images.</span></span> <span data-ttu-id="68112-259">Install-CcAppliance erneut ausführen oder warten, bis die Bits automatisch aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="68112-259">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="68112-260">**Problem: Die Bereitstellung der ersten Cloud Connector Appliance in einer Umgebung HA fehlschlägt**</span><span class="sxs-lookup"><span data-stu-id="68112-260">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="68112-261">**Lösung:** Die erforderlichen Schritte hängen von den Grund Fehler bei der Bereitstellung:</span><span class="sxs-lookup"><span data-stu-id="68112-261">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="68112-262">Wenn die erste Cloud Connector Appliance fehlschlägt, und Sie nicht die Ursache des Fehlers bestimmen, müssen Sie installieren Sie das Gerät erneut, bis die Bereitstellung erfolgreich ist, und installieren Sie dann den anderen Appliances.</span><span class="sxs-lookup"><span data-stu-id="68112-262">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="68112-263">Schlägt die erste Cloud Connector Appliance eine kleinere Problem, wie ein Problem externes Zertifikat können Sie das Problem zu beheben, ohne das Gerät erneut installieren sein.</span><span class="sxs-lookup"><span data-stu-id="68112-263">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="68112-264">Sie können dann mit Mandanten für remote-PowerShell wie folgt die Bereitstellung als erfolgreich markieren.</span><span class="sxs-lookup"><span data-stu-id="68112-264">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="68112-265">(Sie können auch die folgenden Schritte aus, wenn die erste Bereitstellung erfolgreich war, aber aus irgendeinem Grund Cloud-Connector ein Fehler auftritt, die Bereitstellung als einen Erfolg gemeldet.)</span><span class="sxs-lookup"><span data-stu-id="68112-265">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="68112-266">Wenn die Identität (GUID) der ersten Cloud Connector Appliance erhalten möchten, führen Sie das Cmdlet Get-CsHybridPSTNAppliance.</span><span class="sxs-lookup"><span data-stu-id="68112-266">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="68112-267">Um die Appliance als erfolgreich bereitgestellt zu markieren, führen Sie das Set-CsCceApplianceDeploymentStatus wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="68112-267">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- 
    
    <span data-ttu-id="68112-268">**Problem: Auf dem Hostserver oder den virtuellen Maschinen müssen Sie manuell nach Windows-Updates suchen bzw. diese installieren.**</span><span class="sxs-lookup"><span data-stu-id="68112-268">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
    <span data-ttu-id="68112-p132">**Lösung:** Wir empfehlen Ihnen, dass Sie die Vorteile der automatisierten Betriebssystem-Updates der Skype for Business Cloud Connector Edition nutzen. Nachdem eine Appliance für die Online-Verwaltung registriert und das automatische Update des Betriebssystems aktiviert wurde, werden Windows-Updates vom Hostserver von den virtuellen Maschinen automatisch in Übereinstimmung mit den Windows-Einstellungen der Aktualisierungszeit für das Betriebssystem gesucht und installiert.</span><span class="sxs-lookup"><span data-stu-id="68112-p132">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition. After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
    <span data-ttu-id="68112-p133">Wenn Sie manuell nach Windows-Updates suchen und diese installieren müssen, führen Sie die zu Ihrem Bereitstellungstyp passenden Schritte in diesem Abschnitt durch. Sie sollten das gleichzeitige Update des Hostservers und der darauf ausgeführten virtuellen Maschinen planen, um die bei Updates entstehenden Ausfallzeiten zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="68112-p133">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment. You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
    <span data-ttu-id="68112-p134">Sie können auch einen WSUS (Windows Server Update Services)-Server für die Bereitstellung von Updates für Cloud Connector-Server verwenden. Stellen Sie hierfür nur sicher, dass Sie **nicht** die automatische Installation von Windows-Update konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="68112-p134">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers. Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
    <span data-ttu-id="68112-275">Weitere Informationen zum manuellen Update Ihrer Cloud Connector-Bereitstellung finden Sie im folgenden Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="68112-275">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- 
    
    <span data-ttu-id="68112-276">**Problem: Wenn Cloud Connector auf einen neuen Build aktualisiert werden, werden die Cloud Connector-Cmdlets nicht aktualisiert.**</span><span class="sxs-lookup"><span data-stu-id="68112-276">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="68112-277">In diesem Fall manchmal auf, wenn ein PowerShell-Fenster geöffnet gelassen wird bei der automatischen Aktualisierung.</span><span class="sxs-lookup"><span data-stu-id="68112-277">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
    <span data-ttu-id="68112-278">**Lösung:** Um die aktualisierten Cmdlets zu laden, können Sie entweder die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="68112-278">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
  - <span data-ttu-id="68112-279">Schließen Sie PowerShell in der Cloud Connector-Anwendung, und klicken Sie dann öffnen Sie PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68112-279">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
  - <span data-ttu-id="68112-280">Oder führen Sie Import-Module CloudConnector-Force.</span><span class="sxs-lookup"><span data-stu-id="68112-280">Or, you can run Import-Module CloudConnector -Force.</span></span> 
    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="68112-281">Manuelles Installieren von Windows-updates</span><span class="sxs-lookup"><span data-stu-id="68112-281">Install Windows updates manually</span></span>

<span data-ttu-id="68112-282">Gehen folgendermaßen Sie vor, um zu prüfen, ob und Anwenden von Updates für Windows, wenn Sie nicht automatische Updates in Ihrer Umgebung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="68112-282">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="68112-283">Suchen nach und Installieren von Windows-Updates erfordern möglicherweise einen Neustart des Servers.</span><span class="sxs-lookup"><span data-stu-id="68112-283">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="68112-284">Wenn Sie ein Hostserver neu gestartet wird, werden Benutzer müssen nicht Cloud Connector zu tätigen oder Entgegennehmen von Anrufen verwendet.</span><span class="sxs-lookup"><span data-stu-id="68112-284">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="68112-285">Sie können Aktualisierungen manuell suchen und installieren, um zu steuern, wann die Aktualisierungen erfolgen, und dann die Computer nach Bedarf zu von Ihnen gewählten Zeiten neu starten, um Dienstunterbrechungen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="68112-285">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="68112-286">Stellen Sie für die manuelle Suche nach Updates eine Verbindung zu jedem Hostserver her, und öffnen Sie die **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="68112-286">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="68112-287">Wählen Sie **System und Sicherheit \>Windows Update**, und klicken Sie dann die Updates verwalten und Neustart des Servers als Antwort für Ihre Umgebung.</span><span class="sxs-lookup"><span data-stu-id="68112-287">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="68112-288">Wenn Ihr Standort nur über eine Appliance verfügt, stellen Sie eine Verbindung zu jeder virtuellen Maschine her, und öffnen Sie die **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="68112-288">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="68112-289">Wählen Sie **System und Sicherheit \>Windows Update**, und konfigurieren Sie anschließend die Updates und Neustart des Servers als Antwort.</span><span class="sxs-lookup"><span data-stu-id="68112-289">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="68112-p139">Wenn Ihr Standort über mehrere Appliances verfügt, können Benutzer während des Updates nicht auf die Instanz zugreifen, die gerade aktualisiert und neu gestartet wird. Benutzer stellen eine Verbindung zu anderen Instanzen in der Bereitstellung her, bis alle virtuellen Maschinen und alle Skype for Business-Dienste auf den virtuellen Maschinen nach Abschluss der Updates gestartet werden. Um mögliche Ausfallzeiten zu vermeiden, können Sie beim Anwenden der Updates die Instanz aus HA entfernen und sie nach Abschluss des Vorgangs wiederherstellen. Gehen Sie hierfür wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="68112-p139">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates. Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed. To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete. To do so:</span></span>
    
1. <span data-ttu-id="68112-294">Öffnen Sie auf allen Hostservern eine PowerShell-Konsole als Administrator.</span><span class="sxs-lookup"><span data-stu-id="68112-294">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="68112-295">Entfernen Sie die Instanz mit dem folgenden Cmdlet aus HA:</span><span class="sxs-lookup"><span data-stu-id="68112-295">Remove the instance from HA with the following cmdlet:</span></span>
    
  ```
  Enter-CcUpdate
  ```

3. 
    
    <span data-ttu-id="68112-296">Führen Sie die Schritte für eine einzelne Instanz aus, um die Updates manuell anzuwenden und die virtuelle Maschine neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="68112-296">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="68112-297">Legen Sie die Instanz mit dem folgenden Cmdlet erneut auf HA fest:</span><span class="sxs-lookup"><span data-stu-id="68112-297">Set the instance back to HA with the following cmdlet:</span></span>
    
  ```
  Exit-CcUpdate
  ```

<span data-ttu-id="68112-298">Führen Sie für die Bereitstellungen mit mehreren Standorten die Schritte für einen einzelnen Standort für jeden Standort in der Bereitstellung aus, wobei die Updates jeweils auf einen Standort angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="68112-298">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="68112-299">Tipps bei der Installation von Antivirussoftware auf dem Hostcomputer Cloud-Connector</span><span class="sxs-lookup"><span data-stu-id="68112-299">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="68112-300">Wenn Sie Antivirensoftware auf dem Hostcomputer Cloud Connector installieren möchten, müssen Sie die folgenden Ausnahmen hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="68112-300">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="68112-301">Lokale Appliance-Verzeichnis auf jedem Computer.</span><span class="sxs-lookup"><span data-stu-id="68112-301">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="68112-302">Remote Websiteverzeichnis auf jedem Computer.</span><span class="sxs-lookup"><span data-stu-id="68112-302">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="68112-303">Lokale Websiteverzeichnis auf dem Computer dient als Host den Stammordner für freigegebene Websites.</span><span class="sxs-lookup"><span data-stu-id="68112-303">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="68112-304">%ProgramFiles%\Skype für Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="68112-304">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="68112-305">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="68112-305">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="68112-306">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="68112-306">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="68112-307">Der Vorgang Microsoft.Rtc.CCE.ManagementService.exe.</span><span class="sxs-lookup"><span data-stu-id="68112-307">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
    

