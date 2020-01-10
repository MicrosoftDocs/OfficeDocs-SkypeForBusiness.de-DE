---
title: Problembehandlung bei Ihrer Cloud Connector-Bereitstellung
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Problembehandlung bei der Cloud Connector Edition-Bereitstellung.
ms.openlocfilehash: 3edc67d5887c21543e4cbb01a6057a0c657e95e3
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002075"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="7978e-103">Problembehandlung bei Ihrer Cloud Connector-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="7978e-103">Troubleshoot your Cloud Connector deployment</span></span>
 
<span data-ttu-id="7978e-104">Problembehandlung bei der Cloud Connector Edition-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="7978e-104">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="7978e-p101">In diesem Thema werden Lösungen für allgemeine Probleme bei Cloud Connector Edition-Bereitstellungen beschrieben. Wenn Probleme mit Anrufen an das und aus dem Telefonfestnetz (Public Switched Telephone Network, PSTN) auftreten, können Sie diese anhand der in diesem Thema beschriebenen Lösungen untersuchen.</span><span class="sxs-lookup"><span data-stu-id="7978e-p101">This topic describes solutions to common issues with Cloud Connector Edition deployments. If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="7978e-107">Cloud Connector bietet integrierte Mechanismen zum automatischen beheben einiger Probleme.</span><span class="sxs-lookup"><span data-stu-id="7978e-107">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="7978e-108">Ein automatischer Erkennungsprozess sucht nach potenziellen Problemen mit den Cloud Connector-Appliances und führt, wenn möglich, Korrekturmaßnahmen zur Behebung dieser Probleme durch, ohne dass ein Administratoreingriff erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="7978e-108">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="7978e-109">So funktioniert der Erkennungsprozess:</span><span class="sxs-lookup"><span data-stu-id="7978e-109">The detection process works as follows:</span></span>
  
- <span data-ttu-id="7978e-110">**Erkennungsreihenfolge:** Der Cloud Connector-Verwaltungsdienst führt einen Prozess alle 60 Sekunden durch, um festzustellen, ob eine Appliance ausgefallen ist.</span><span class="sxs-lookup"><span data-stu-id="7978e-110">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="7978e-111">In der Cloud Connector-Version 2,0 und höher verwendet der Erkennungsprozess den Skype for Business-Corpnet-Schalter zum Herstellen von PowerShell-Verbindungen mit den Cloud Connector-Computern. bei früheren Versionen von 2,0 verwendet der Erkennungsprozess den Cloud Connector-Verwaltungs Schalter.</span><span class="sxs-lookup"><span data-stu-id="7978e-111">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7978e-112">Damit die automatische Wiederherstellung erfolgreich ausgeführt werden kann, muss die Netzwerkverbindung zwischen dem Host und den virtuellen Computern über den Host Netzwerkschalter erfolgen.</span><span class="sxs-lookup"><span data-stu-id="7978e-112">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="7978e-113">Überprüfen Sie die Netzwerkkonnektivität, um sicherzustellen, dass die automatische Erkennung und Wiederherstellung erfolgreich ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="7978e-113">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="7978e-114">**Überwachung:** Die folgenden Dienste werden in Cloud Connector, Version 2,0 und höher, überwacht:</span><span class="sxs-lookup"><span data-stu-id="7978e-114">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="7978e-115">Virtuelle Computer sind nicht mit dem Cloud Connector verbunden. virtuelle Switches für Unternehmen oder Internet</span><span class="sxs-lookup"><span data-stu-id="7978e-115">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="7978e-116">Virtuelle Computer befinden sich in einem gespeicherten oder gestoppten Status</span><span class="sxs-lookup"><span data-stu-id="7978e-116">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="7978e-117">Zentrale Verwaltungs Server Dienste: Replikat, Master</span><span class="sxs-lookup"><span data-stu-id="7978e-117">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="7978e-118">Vermittlungs Server Dienste: Replikat, RTCSRV und MEDSVC</span><span class="sxs-lookup"><span data-stu-id="7978e-118">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="7978e-119">Edge-Server Dienste: Replikat, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="7978e-119">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="7978e-120">Eingehende Firewallregeln sind für CS RTCSRV on Edge Server, CS RTCMEDSRV auf dem Vermittlungsserver deaktiviert</span><span class="sxs-lookup"><span data-stu-id="7978e-120">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="7978e-121">In der Cloud Connector-Version 1.4.2 werden nur die folgenden Dienste überwacht:</span><span class="sxs-lookup"><span data-stu-id="7978e-121">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="7978e-122">Vermittlungs Server Dienste: RTCSRV und MEDSVC</span><span class="sxs-lookup"><span data-stu-id="7978e-122">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="7978e-123">Edge-Server Dienst: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="7978e-123">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="7978e-124">**Wiederherstellungsprozess:** Wenn überwachte Dienste ausgefallen sind, wird eine Appliance markiert, und Dienste werden angehalten und manuell markiert, bis alle Probleme behoben werden können.</span><span class="sxs-lookup"><span data-stu-id="7978e-124">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="7978e-125">Dadurch wird verhindert, dass Anrufe an eine Appliance weitergeleitet werden, die zu Anruf Fehlern führen kann.</span><span class="sxs-lookup"><span data-stu-id="7978e-125">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="7978e-126">Der Cloud Connector-Verwaltungsdienst führt die automatische Wiederherstellung wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="7978e-126">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="7978e-127">Das anfängliche Wiederholungsintervall beträgt alle zehn Sekunden mit einer maximalen Intervallzeit von einer Stunde.</span><span class="sxs-lookup"><span data-stu-id="7978e-127">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="7978e-128">Bei den ersten drei Wiederherstellungsversuchen beträgt die Intervallzeit 10 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="7978e-128">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="7978e-129">Ab der vierten Wiederholung nimmt die Intervallzeit um das Zweifache der vorherigen Intervallzeit zu.</span><span class="sxs-lookup"><span data-stu-id="7978e-129">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="7978e-130">Der vierte Versuch wird beispielsweise in 20 Sekunden, der fünfte in 40 Sekunden usw. erfolgen.</span><span class="sxs-lookup"><span data-stu-id="7978e-130">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="7978e-131">Wenn die maximale Intervallzeit von einer Stunde erreicht ist, werden die Wiederholungsversuche einmal pro Stunde fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="7978e-131">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="7978e-132">Wenn die Wiederherstellung erfolgreich ist, werden das Intervall und die Wiederholungsanzahl auf die Anfangswerte festgesetzt.</span><span class="sxs-lookup"><span data-stu-id="7978e-132">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="7978e-133">Wenn der Verwaltungsdienst neu gestartet wird, werden das Intervall und die Wiederholungsanzahl auf die anfänglichen Werte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="7978e-133">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="7978e-134">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="7978e-134">Troubleshooting</span></span>

<span data-ttu-id="7978e-135">Im folgenden finden Sie Lösungen für häufig auftretende Probleme:</span><span class="sxs-lookup"><span data-stu-id="7978e-135">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="7978e-136">**Problem: Die Bereitstellung schlägt fehl oder reagiert nicht mehr bei Ausführung von Bereitstellungsskripten. Nach der Anmeldung bei den einzelnen VMs fehlt die IP-Adresse oder passt nicht zur Verwaltungs-, internen bzw. externen NIC.**</span><span class="sxs-lookup"><span data-stu-id="7978e-136">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="7978e-137">**Auflösung:** Dieses Problem kann nicht automatisch aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="7978e-137">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="7978e-138">Während der Ausführung der VMs können diesen keine NICs hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7978e-138">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="7978e-139">Fahren Sie diese VMs im Hyper-V-Manager herunter und entfernen Sie sie, und führen Sie anschließend die folgenden Cmdlets aus:</span><span class="sxs-lookup"><span data-stu-id="7978e-139">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="7978e-140">**Problem: Nach der Installation von Active Directory (AD) und der Gesamtstruktur wurde der CMS-Server bzw. der Vermittlungsserver nicht ordnungsgemäß zur Domäne hinzugefügt.**</span><span class="sxs-lookup"><span data-stu-id="7978e-140">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="7978e-141">**Lösung:** Um dieses Problem zu beheben, führen Sie die folgenden Schritte durch:</span><span class="sxs-lookup"><span data-stu-id="7978e-141">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="7978e-142">Melden Sie sich beim Active Directory-Server an, und überprüfen Sie, ob die Domäne ordnungsgemäß erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7978e-142">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="7978e-143">Melden Sie sich beim CMS bzw. beim Vermittlungsserver an, und überprüfen Sie, ob der Netzwerkkarte des Unternehmensnetzwerks eine gültige IP-Adresse zugewiesen wurde und ob eine gültige statische IP und ein DNS als IP-Adresse des AD-Servers konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="7978e-143">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="7978e-144">Melden Sie sich beim CMS/Mediation-Server an, und öffnen Sie eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="7978e-144">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="7978e-145">Stellen Sie sicher, dass Sie den FQDN und die IP-Adresse des Active Directory-Servers anpingen können.</span><span class="sxs-lookup"><span data-stu-id="7978e-145">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="7978e-146">Wenn dies nicht möglich ist, kann es zu einem IP-Adressenkonflikt kommen.</span><span class="sxs-lookup"><span data-stu-id="7978e-146">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="7978e-147">Versuchen Sie, eine neue IP für Active Directory zuzuweisen und DNS auf dem CMS/Mediation-Server entsprechend zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7978e-147">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="7978e-148">**Problem: Es wird die folgende Fehlermeldung angezeigt: "Remove-VMSwitch: Fehler beim Entfernen des virtuellen Ethernet-Switches. Der virtuelle Schalter "Cloud Connector-Verwaltungs Schalter" kann nicht gelöscht werden, da er von virtuellen Computern oder untergeordneten Pools verwendet wird. "**</span><span class="sxs-lookup"><span data-stu-id="7978e-148">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="7978e-149">**Auflösung:** Der "Cloud Connector-Verwaltungs Schalter" wurde nach der Bereitstellung nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="7978e-149">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="7978e-150">Wenn dieser Fehler auftritt, navigieren Sie zum Hyper-V-Manager, und stellen Sie sicher, dass keine andere virtuelle Maschine verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="7978e-150">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="7978e-151">Wenn nach wie vor virtuelle Maschinen verbunden sind, trennen Sie sie, und löschen Sie den Management-Switch.</span><span class="sxs-lookup"><span data-stu-id="7978e-151">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="7978e-152">Wenn der Management-Switch nicht gelöscht werden kann, starten Sie den Hostserver neu, und versuchen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="7978e-152">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="7978e-153">**Problem: Es wird die folgende Fehlermeldung angezeigt: "Dienst RTCMRAUTH konnte nicht gestartet werden. Vergewissern Sie sich, dass der Dienst nicht deaktiviert ist. "**</span><span class="sxs-lookup"><span data-stu-id="7978e-153">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7978e-154">Dieses Problem gilt nur für Cloud Connector-Versionen, die älter als 1.4.2 sind.</span><span class="sxs-lookup"><span data-stu-id="7978e-154">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="7978e-p110">Der Startfehler kann auch darauf zurückzuführen sein, dass für diesen Front End-Server zuvor ein Failover (Computer-Failover) durchgeführt wurde. In diesem Fall sollten Sie ein Failback (Computer-Failback) starten.</span><span class="sxs-lookup"><span data-stu-id="7978e-p110">The failure to start could also be because this Front End server was previously failed over (using computer fail over). If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="7978e-p111">**Lösung:** Dieser Fehler tritt auf einem Edgeserver auf, wenn der Edgeserver dem Zertifikat der Stammzertifizierungsstelle oder dem Zertifikat der Zwischenzertifizierungsstelle nicht vertraut. Selbst wenn ein externes Zertifikat importiert werden kann, ist die Zertifizierungskette unterbrochen. Unter dieser Bedingung kann der RTCMRAUTH- bzw. der RTCSRV-Dienst nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="7978e-p111">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server. Even if the external certificate can be imported but the certificate chain is broken. Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="7978e-p112">Importieren Sie das Zertifikat der Stammzertifizierungsstelle und alle Zertifikate der Zwischenzertifizierungsstelle Ihres externen Zertifikats manuell auf den Edgeserver, und starten Sie den Edgeserver anschließend neu. Wenn die Dienste RTCMRAUTH und RTCSRV auf dem Edgeserver gestartet werden, navigieren Sie zu Ihrem Hostserver, starten Sie eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus, um zur neuen Bereitstellung zu wechseln:</span><span class="sxs-lookup"><span data-stu-id="7978e-p112">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server. After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="7978e-162">**Problem: Der Hostserver wurde nach dem Anwenden von Windows-Updates neu gestartet, und vom Server verarbeitete Anrufe sind fehlgeschlagen.**</span><span class="sxs-lookup"><span data-stu-id="7978e-162">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="7978e-p113">**Lösung:** Wenn Sie eine Umgebung mit hoher Verfügbarkeit bereitgestellt haben und ein Windows-Update manuell überprüfen und installieren, können Sie mit einem von Microsoft angebotenen Cmdlet einen Hostcomputer (Bereitstellungsinstanz) in die aktuelle Topologie oder aus der aktuellen Topologie verschieben. Führen Sie hierzu die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="7978e-p113">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually. Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="7978e-165">Starten Sie auf dem Hostserver eine PowerShell-Konsole als Administrator, und führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="7978e-165">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="7978e-166">Suchen und installieren Sie alle verfügbaren Updates.</span><span class="sxs-lookup"><span data-stu-id="7978e-166">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="7978e-167">Führen Sie in der PowerShell-Konsole das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="7978e-167">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="7978e-168">**Problem: Wenn ein Anruf über einen Skype for Business-Client mit einer PSTN-Nummer getätigt wird, kann der Anruf nicht durch Einladen einer anderen PSTN-Nummer zu einer Konferenz eskaliert werden.**</span><span class="sxs-lookup"><span data-stu-id="7978e-168">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="7978e-169">**Auflösung:** Informationen zum Beheben dieses Problems finden Sie unter Konfigurieren von Einstellungen für den [Hybriden Online-Vermittlungs Server](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span><span class="sxs-lookup"><span data-stu-id="7978e-169">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="7978e-170">**Problem: Eine Warnmeldung zum Windows-Update wird angezeigt, wenn Sie Active Directory-Server installieren: „Die automatische Aktualisierung von Windows ist nicht aktiviert. Aktivieren Sie "Windows Update", um sicherzustellen, dass die neu installierte Rolle oder das neu installierte Feature automatisch aktualisiert wird.“**</span><span class="sxs-lookup"><span data-stu-id="7978e-170">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="7978e-171">**Auflösung:** Starten Sie eine Mandanten-Remote-PowerShell-Sitzung unter Verwendung von Skype for Business-Administratoranmeldeinformationen, und führen Sie dann das folgende Cmdlet aus, um die _EnableAutoUpdate_ -Konfiguration Ihrer Website zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="7978e-171">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="7978e-172">Wenn _EnableAutoUpdate_ auf " **true**" festgelegt ist, können Sie diese Warnmeldung bedenkenlos ignorieren, da der CCEManagement-Dienst das herunterladen und Installieren von Windows-Updates für virtuelle Computer und den Hostserver übernimmt.</span><span class="sxs-lookup"><span data-stu-id="7978e-172">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="7978e-173">Wenn _EnableAutoUpdate_ auf **false**festgelegt ist, führen Sie das folgende Cmdlet aus, um es auf **true**festzulegen.</span><span class="sxs-lookup"><span data-stu-id="7978e-173">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="7978e-174">Alternativ dazu können Sie Updates manuell suchen und installieren.</span><span class="sxs-lookup"><span data-stu-id="7978e-174">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="7978e-175">Informationen hierzu finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="7978e-175">See the next section.</span></span>
    
- <span data-ttu-id="7978e-176">**Problem: Es wird eine Fehlermeldung angezeigt: die Appliance kann nicht registriert werden, da \<Ihre\> aktuelle \<Eingabe/\> Konfiguration \<Sitename oder\> Appliancename oder Mediation Server-FQDN oder \<die IP-Adresse\> des Vermittlungsservers Konflikte mit der vorhandenen Appliance (n) verursacht. Entfernen Sie die Konflikt Appliance, oder aktualisieren Sie Ihre Eingabe/Konfigurationsinformationen, und registrieren Sie sich dann erneut. "Wenn Sie Register-CcAppliance ausführen, um die aktuelle Appliance online zu registrieren.**</span><span class="sxs-lookup"><span data-stu-id="7978e-176">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="7978e-177">**Auflösung:** Werte für die \<IP-\>Adresse \<\> Appliancename,\> Vermittlungsserver-FQDN und \<Vermittlungsserver müssen eindeutig sein und nur für eine Appliance-Registrierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7978e-177">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="7978e-178">Standardmäßig\> stammt \<Appliancename aus dem Host-Namen.</span><span class="sxs-lookup"><span data-stu-id="7978e-178">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="7978e-179">\<Der in der\> Konfigurations \<-ini-Datei\> definierte IP-Adresse des Mediation Server-FQDN und des Vermittlungsservers.</span><span class="sxs-lookup"><span data-stu-id="7978e-179">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="7978e-180">Wenn Sie beispielsweise (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) zum Registrieren von SiteName=MySite verwenden, aber eine registrierte Appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) vorhanden ist, tritt ein Konflikt auf.</span><span class="sxs-lookup"><span data-stu-id="7978e-180">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="7978e-181">Überprüfen Sie zunächst die Datei „CloudConnector.ini“ im ApplianceRoot-Verzeichnisabschnitt.</span><span class="sxs-lookup"><span data-stu-id="7978e-181">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="7978e-182">Sie \<erhalten in der\>Datei \<Sitename-\> , \<Vermittlungsserver-\> FQDN und Vermittlungsserver-IP-Adresswerte.</span><span class="sxs-lookup"><span data-stu-id="7978e-182">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="7978e-183">\<Appliancename\> ist der Name Ihres Hostservers.</span><span class="sxs-lookup"><span data-stu-id="7978e-183">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="7978e-184">Starten Sie anschließend Mandanten-Remote-PowerShell mit Ihren Skype for Business-Administratoranmeldeinformationen, und führen Sie dann das folgende Cmdlet aus, um die registrierten Appliances zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7978e-184">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="7978e-185">Nach der Überprüfung aller Konflikte können Sie die Datei „CloudConnector.ini“ mit den Informationen aktualisieren, die mit der registrierten Appliance übereinstimmen, oder die Registrierung der vorhandenen Appliance aufheben, um die Konflikte zu beheben.</span><span class="sxs-lookup"><span data-stu-id="7978e-185">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="7978e-186">**Problem: das Cmdlet "Get-CcRunningVersion" gibt einen leeren Wert zurück, wenn eine bereitgestellte Appliance auf dem Host ausgeführt wird.**</span><span class="sxs-lookup"><span data-stu-id="7978e-186">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="7978e-187">**Auflösung:** Dies kann passieren, wenn Sie ein Upgrade von 1.3.4 oder 1.3.8 auf 1.4.1 durchführen.</span><span class="sxs-lookup"><span data-stu-id="7978e-187">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="7978e-188">Nachdem Sie Version 1.4.1 mit der MSI-Version installiert haben, müssen `Register-CcAppliance` Sie vor dem Ausführen eines anderen Cmdlets ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7978e-188">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="7978e-189">`Register-CcAppliance`migriert die Datei "Module. ini" von%USERPROFILE%\CloudConnector zu%ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="7978e-189">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="7978e-190">Wenn Sie Sie verpasst haben, wird im Ordner%ProgramData%\CloudConnector eine neue Modul. ini erstellt, und die Informationen zum Ausführen/Sichern der Version für 1.3.4 oder 1.3.8 werden ersetzt.</span><span class="sxs-lookup"><span data-stu-id="7978e-190">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="7978e-191">Vergleichen Sie Modul. ini-Dateien in%USERPROFILE%\CloudConnector und%ProgramData%\CloudConnector-Ordner.</span><span class="sxs-lookup"><span data-stu-id="7978e-191">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="7978e-192">Wenn es Unterschiede gibt, löschen Sie die Datei Modul. ini in `Register-CcAppliance`%ProgramData%\CloudConnector, und führen Sie eine erneute Ausführung aus.</span><span class="sxs-lookup"><span data-stu-id="7978e-192">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="7978e-193">Sie können die Datei auch manuell auf die richtige Ausführungs-und Sicherungsversion ändern.</span><span class="sxs-lookup"><span data-stu-id="7978e-193">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="7978e-194">**Problem: Nachdem Sie das Cmdlet Switch-CcVersion ausgeführt haben, um zu einer älteren Version zu wechseln, die sich von der aktuellen Skriptversion unterscheidet, gibt es keine Unterstützung für hohe Verfügbarkeit für diese alte Version.**</span><span class="sxs-lookup"><span data-stu-id="7978e-194">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="7978e-195">**Auflösung:** Sie haben beispielsweise ein Upgrade von 1.4.1 auf 1.4.2 durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="7978e-195">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="7978e-196">Ihre aktuelle Skriptversion, die durch ausgeführt werden kann `Get-CcVersion`, und die ausgeführte Version, die durch Ausführen `Get-CcRunningVersion` bestimmt werden kann, sind beide 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="7978e-196">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="7978e-197">Wenn Sie `Switch-CcVersion` die ausgeführte Version zu diesem Zeitpunkt wieder auf 1.4.1 umschalten, gibt es keine Unterstützung für hohe Verfügbarkeit für diese alte Version.</span><span class="sxs-lookup"><span data-stu-id="7978e-197">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="7978e-p121">Um die vollständige Unterstützung von hoher Verfügbarkeit zu erhalten, müssen Sie zurück zu Version 1.4.2 wechseln, damit die zurzeit ausgeführte Version mit der Skriptversion übereinstimmt. Wenn bei Ihrer 1.4.2-Bereitstellung Probleme auftreten, deinstallieren Sie die Version, und installieren Sie sie umgehend neu.</span><span class="sxs-lookup"><span data-stu-id="7978e-p121">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same. If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="7978e-200">**Problem: Zertifizierungsstellenzertifikate oder interne Zertifikate, die für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver ausgestellt wurden, laufen in Kürze ab oder sind kompromittiert.**</span><span class="sxs-lookup"><span data-stu-id="7978e-200">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="7978e-p122">**Lösung:** Zertifizierungsstellenzertifikate für Skype for Business sind fünf Jahre lang gültig. Für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver ausgestellte interne Zertifikate sind zwei Jahre lang gültig.</span><span class="sxs-lookup"><span data-stu-id="7978e-p122">**Resolution:** Skype for Business certification authority certificates are valid for five years. Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7978e-203">In der Cloud Connector-Version 2,0 und höher wurde das Cmdlet Renew-CcServerCertificate in Update-CcServerCertificate geändert, und das Cmdlet Renew-CcCACertificate wurde in Update-CcCACertificate geändert.</span><span class="sxs-lookup"><span data-stu-id="7978e-203">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="7978e-204">Wenn interne Zertifikate, die für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver ausgestellt wurden, nahezu abgelaufen sind oder gefährdet sind, führen Sie das Cmdlet Renew-CcServerCertificate oder Update-CcServerCertificate aus, um Ihre Zertifikate zu erneuern.</span><span class="sxs-lookup"><span data-stu-id="7978e-204">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="7978e-205">Wenn Zertifikate der Zertifizierungsstelle nahezu abgelaufen sind, führen Sie das Cmdlet Renew-CcCACertificate oder Update-CcCACertificate aus, um Ihre Zertifikate zu erneuern.</span><span class="sxs-lookup"><span data-stu-id="7978e-205">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="7978e-206">Führen Sie die folgenden Schritte aus **, wenn Zertifikate der Zertifizierungsstelle kompromittiert werden und nur eine Appliance auf der Website vorhanden ist** :</span><span class="sxs-lookup"><span data-stu-id="7978e-206">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="7978e-207">Führen Sie das Cmdlet „Enter-CcUpdate“ aus, um Dienste auszugleichen und die Appliance in den Wartungsmodus zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="7978e-207">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="7978e-208">Führen Sie die folgenden Cmdlets aus, um die Zertifizierungsstellenzertifikate und alle internen Serverzertifikate zurückzusetzen und neu zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="7978e-208">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="7978e-209">Für Cloud Connector-Versionen vor 2,0:</span><span class="sxs-lookup"><span data-stu-id="7978e-209">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="7978e-210">Oder für Cloud Connector Release 2,0 und höher:</span><span class="sxs-lookup"><span data-stu-id="7978e-210">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="7978e-211">Wenn TLS zwischen dem Gateway und dem Vermittlungs Server verwendet wird, führen Sie das Cmdlet Export-CcRootCertificate von der Appliance aus, und installieren Sie dann das exportierte Zertifikat für Ihre PSTN-Gateways.</span><span class="sxs-lookup"><span data-stu-id="7978e-211">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="7978e-212">Möglicherweise müssen Sie das Zertifikat auch erneut auf Ihrem Gateway ausgeben.</span><span class="sxs-lookup"><span data-stu-id="7978e-212">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="7978e-213">Führen Sie das Cmdlet Exit-CcUpdate aus, um Dienste zu starten und den Wartungsmodus zu beenden.</span><span class="sxs-lookup"><span data-stu-id="7978e-213">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="7978e-214">**Wenn Zertifikate der Zertifizierungsstelle kompromittiert werden und mehrere Appliances auf der Website vorhanden sind,** führen Sie die folgenden Schritte auf jeder Appliance auf der Website aus.</span><span class="sxs-lookup"><span data-stu-id="7978e-214">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="7978e-215">Microsoft empfiehlt, dass Sie diese Schritte während der Verwendung außerhalb der Spitzenzeiten durchführen.</span><span class="sxs-lookup"><span data-stu-id="7978e-215">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="7978e-216">Führen Sie auf der ersten Appliance das Cmdlet Remove-CcCertificationAuthorityFile aus, um die Sicherungsdateien der Zertifizierungs \<Stelle\> im Verzeichnis SiteRoot zu bereinigen.</span><span class="sxs-lookup"><span data-stu-id="7978e-216">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="7978e-217">Führen Sie das Cmdlet "Enter-CcUpdate" aus, um Dienste zu entladen und jede Appliance in den Wartungsmodus zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="7978e-217">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="7978e-218">Führen Sie auf der ersten Appliance die folgenden Cmdlets aus, um neue Zertifizierungsstellenzertifikate und alle internen Serverzertifikate zurückzusetzen und zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="7978e-218">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="7978e-219">Für Cloud Connector-Versionen vor 2,0:</span><span class="sxs-lookup"><span data-stu-id="7978e-219">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="7978e-220">Oder für Cloud Connector Release 2,0 und höher:</span><span class="sxs-lookup"><span data-stu-id="7978e-220">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="7978e-221">Führen Sie auf der ersten Appliance das folgende Cmdlet aus, um die ca-Dateien im \<SiteRoot\> -Ordner zu sichern.</span><span class="sxs-lookup"><span data-stu-id="7978e-221">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="7978e-222">Führen Sie auf allen anderen Appliances am gleichen Standort die folgenden Befehle aus, um die Sicherungsdateien der ca zu nutzen, damit die Appliances alle dasselbe Stammzertifikat verwenden und dann neue Zertifikate anfordern.</span><span class="sxs-lookup"><span data-stu-id="7978e-222">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="7978e-223">Wenn TLS zwischen dem Gateway und dem Vermittlungs Server verwendet wird, führen Sie das Cmdlet Export-CcRootCertificate von einer beliebigen Appliance auf der Website aus, und installieren Sie dann das exportierte Zertifikat für Ihre PSTN-Gateways.</span><span class="sxs-lookup"><span data-stu-id="7978e-223">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="7978e-224">Möglicherweise müssen Sie das Zertifikat auch erneut auf Ihrem Gateway ausgeben.</span><span class="sxs-lookup"><span data-stu-id="7978e-224">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="7978e-225">Führen Sie das Cmdlet Exit-CcUpdate aus, um Dienste zu starten und den Wartungsmodus zu beenden.</span><span class="sxs-lookup"><span data-stu-id="7978e-225">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="7978e-226">**Problem: die folgende Fehlermeldung wird im Cloud Connector-Verwaltungsdienst Protokoll "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log" angezeigt: CceService-Fehler: 0: unerwartete Ausnahme beim Melden des Status Online: System. Management. Automation. CmdletInvocationException: Anmeldung für den globalen mandantenadministrator \<\>des Benutzers fehlgeschlagen. Erstellen Sie ein neues Anmeldeinformationsobjekt, indem Sie sicherstellen, dass Sie den richtigen Benutzernamen und das richtige Kennwort verwendet haben. ---\>**</span><span class="sxs-lookup"><span data-stu-id="7978e-226">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="7978e-227">**Auflösung:** Die Office 365-Administratoranmeldeinformationen für globale Mandanten wurden geändert, seit die Cloud Connector-Appliance registriert wurde.</span><span class="sxs-lookup"><span data-stu-id="7978e-227">**Resolution:** The Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="7978e-228">Wenn Sie die lokal gespeicherten Anmeldeinformationen auf der Cloud Connector-Appliance aktualisieren möchten, führen Sie die folgenden Schritte über die Administrator-PowerShell auf der Host-Appliance aus:</span><span class="sxs-lookup"><span data-stu-id="7978e-228">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="7978e-229">**Problem: Nachdem Sie das Kennwort für das Hostserver Konto geändert haben, das Sie für die Bereitstellung verwendet haben, wird die folgende Fehlermeldung angezeigt: "ConvertTo-SecureString: Key ist nicht gültig für die Verwendung im angegebenen Zustand." in%ProgramFiles%\Skype for Business-Cloud-Connector Edition\ManagementService\CceManagementService.log oder während der Ausführung des Cmdlets Get-CcCredential.**</span><span class="sxs-lookup"><span data-stu-id="7978e-229">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="7978e-230">**Auflösung:** Alle Anmeldeinformationen für den Cloud Connector werden in der folgenden Datei gespeichert: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="7978e-230">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="7978e-231">Wenn sich das Kennwort auf dem Hostserver ändert, müssen Sie die lokal gespeicherten Anmeldeinformationen aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7978e-231">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="7978e-232">**Wenn Sie Cloud Connector, Version 1.4.2, ausführen**, generieren Sie mit den folgenden Schritten alle Cloud Connector-Kennwörter neu:</span><span class="sxs-lookup"><span data-stu-id="7978e-232">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="7978e-233">Starten Sie den Hostserver neu.</span><span class="sxs-lookup"><span data-stu-id="7978e-233">Restart the host server.</span></span>
    
  2. <span data-ttu-id="7978e-234">Löschen Sie die folgende Datei: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="7978e-234">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="7978e-235">Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie dann "Register-CcAppliance-local" aus, um die Kennwörter, die der Beschreibung folgen, erneut einzugeben.</span><span class="sxs-lookup"><span data-stu-id="7978e-235">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="7978e-236">Geben Sie die gleichen Kennwörter ein, die Sie vor der Cloud Connector-Bereitstellung eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="7978e-236">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="7978e-237">**Wenn Sie Cloud Connector, Version 2,0 oder höher, ausführen, müssen Sie** alle Cloud Connector-Kennwörter erneut erstellen, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="7978e-237">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="7978e-238">Starten Sie den Hostserver neu.</span><span class="sxs-lookup"><span data-stu-id="7978e-238">Restart the host server.</span></span>
    
  5. <span data-ttu-id="7978e-239">Löschen Sie die folgende Datei: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="7978e-239">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="7978e-240">Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie dann "Register-CcAppliance-local" aus, um die Kennwörter, die der Beschreibung folgen, erneut einzugeben.</span><span class="sxs-lookup"><span data-stu-id="7978e-240">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="7978e-p128">Wenn die zwischengespeicherte Kennwortdatei mit Cloud Connector, Version 1.4.2, generiert wurde, verwenden Sie das „VMAdmin“-Kennwort als „CceService“-Kennwort, wenn Sie danach gefragt werden. Geben Sie das gleiche Kennwort ein, das Sie vor der Cloud Connector-Bereitstellung für alle anderen Konten eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="7978e-p128">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted. Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="7978e-243">Wenn die zwischengespeicherte Kennwortdatei mit Cloud Connector, Version 1.4.2, generiert wurde und die Kennwörter von „DomainAdmin“ und „VMAdmin“ nicht übereinstimmen, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="7978e-243">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="7978e-244">Führen Sie „Set-CcCredential -AccountType DomainAdmin“ wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="7978e-244">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="7978e-245">Wenn Sie zur Eingabe der alten Anmeldeinformationen für das Konto aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das „CceService“-Kennwort verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="7978e-245">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="7978e-246">Wenn Sie zur Eingabe der neuen Anmeldeinformationen für das Konto aufgefordert werden, geben Sie das zuvor verwendete Kennwort für „DomainAdmin“ ein.</span><span class="sxs-lookup"><span data-stu-id="7978e-246">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="7978e-247">Wenn die zwischengespeicherte Kennwortdatei mit Cloud Connector, Version 2,0 oder höher, generiert wurde, verwenden VmAdmin und DomainAdmin standardmäßig dasselbe Kennwort wie CceService.</span><span class="sxs-lookup"><span data-stu-id="7978e-247">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="7978e-248">Wenn Sie die Kennwörter für „DomainAdmin“ und „VMAdmin“ geändert haben, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="7978e-248">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="7978e-249">Führen Sie „Set-CcCredential -AccountType DomainAdmin“ wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="7978e-249">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="7978e-250">Wenn Sie zur Eingabe der alten Anmeldeinformationen für das Konto aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das „CceService“-Kennwort verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="7978e-250">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="7978e-251">Wenn Sie zur Eingabe der neuen Anmeldeinformationen für das Konto aufgefordert werden, geben Sie das zuvor verwendete Kennwort für „DomainAdmin“ ein.</span><span class="sxs-lookup"><span data-stu-id="7978e-251">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="7978e-252">Führen Sie „Set-CcCredential -AccountType VmAdmin“ wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="7978e-252">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="7978e-253">Wenn Sie zur Eingabe der alten Anmeldeinformationen für das Konto aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das „CceService“-Kennwort verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="7978e-253">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="7978e-254">Wenn Sie zur Eingabe der neuen Anmeldeinformationen für das Konto aufgefordert werden, geben Sie das zuvor verwendete Kennwort für „VmAdmin“ ein. </span><span class="sxs-lookup"><span data-stu-id="7978e-254">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="7978e-255">**Problem: beim Ausführen von Register-CcAppliance-oder anderen Cmdlets auf der Appliance mit Cloud Connector Version 2,1 und höher erhalten Sie eine Fehlermeldung wie "für jedes-Objekt: die Eigenschaft" Common "kann für dieses Objekt nicht gefunden werden. Überprüfen Sie, ob die Eigenschaft vorhanden ist. Unter C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 Char: 14 "**</span><span class="sxs-lookup"><span data-stu-id="7978e-255">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="7978e-256">**Auflösung:** Für Cloud Connector 2,1 und höher ist .NET Framework 4.6.1 oder höher erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7978e-256">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="7978e-257">Aktualisieren Sie .NET Framework auf der Appliance auf Version 4.6.1 oder höher, und führen Sie das Cmdlet (s) erneut aus.</span><span class="sxs-lookup"><span data-stu-id="7978e-257">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="7978e-258">**Problem: bei der Cloud Connector Edition 2,1 wird beim Ausführen von CcAppliance eine Fehlermeldung wie die folgende angezeigt: "Fehler beim Installieren einer neuen Instanz mit Fehler:" Status "kann nicht festgesetzt werden, da nur Zeichenfolgen als Werte zum Einrichten von XmlNode-Eigenschaften verwendet werden können"**</span><span class="sxs-lookup"><span data-stu-id="7978e-258">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="7978e-259">**Auflösung:** Fügen Sie in Cloudconnector. ini unter dem Abschnitt [common] die Konfiguration "State" wie folgt hinzu: CountryCode = US-Bundesland = WA City = Redmond</span><span class="sxs-lookup"><span data-stu-id="7978e-259">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="7978e-260">Es ist nicht zwingend erforderlich, dass die Zeile "Zustand" über einen Wert verfügt, aber die Zeile "Zustand" kann nicht aus der Datei "Cloudconnector. ini" entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="7978e-260">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="7978e-261">**Problem: Es wird die folgende Fehlermeldung "Dismount-WindowsImage: Dismount-WindowsImage Fehler" angezeigt. Fehlercode = 0xc1550115 "beim Installieren oder Aktualisieren von Cloud Connector Edition.**</span><span class="sxs-lookup"><span data-stu-id="7978e-261">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="7978e-262">**Auflösung:** Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie "DISM-Cleanup-WIM" aus.</span><span class="sxs-lookup"><span data-stu-id="7978e-262">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="7978e-263">Damit werden alle von dem Problem betroffenen Images bereinigt.</span><span class="sxs-lookup"><span data-stu-id="7978e-263">This will clean up all troubled images.</span></span> <span data-ttu-id="7978e-264">Führen Sie „Install-CcAppliance“ erneut aus, oder warten Sie, bis die Bits automatisch aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="7978e-264">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="7978e-265">**Problem: die Bereitstellung der ersten Cloud Connector-Appliance in einer ha-Umgebung schlägt fehl**</span><span class="sxs-lookup"><span data-stu-id="7978e-265">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="7978e-266">**Auflösung:** Welche Schritte Sie ausführen, hängt von dem Grund ab, warum die Bereitstellung fehlgeschlagen ist:</span><span class="sxs-lookup"><span data-stu-id="7978e-266">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="7978e-267">Wenn die erste Cloud Connector-Appliance fehlschlägt und Sie den Grund für den Fehler nicht ermitteln können, müssen Sie die Appliance erneut installieren, bis die Bereitstellung erfolgreich ist, und dann die anderen Appliances installieren.</span><span class="sxs-lookup"><span data-stu-id="7978e-267">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="7978e-268">Wenn die erste Cloud Connector-Appliance mit einem kleineren Problem wie einem externen Zertifikat Fehler fehlschlägt, können Sie das Problem möglicherweise beheben, ohne die Appliance erneut installieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="7978e-268">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="7978e-269">Sie können dann mithilfe der Mandanten-Remote-PowerShell die Bereitstellung wie folgt als erfolgreich kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="7978e-269">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="7978e-270">(Sie können auch die folgenden Schritte ausführen, wenn die erste Bereitstellung erfolgreich war, aber aus irgendeinem Grund kann Cloud Connector die Bereitstellung nicht als Erfolg melden.)</span><span class="sxs-lookup"><span data-stu-id="7978e-270">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="7978e-271">Führen Sie das Cmdlet "Get-CsHybridPSTNAppliance" aus, um die Identität (GUID) der ersten Cloud Connector-Appliance abzurufen.</span><span class="sxs-lookup"><span data-stu-id="7978e-271">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="7978e-272">Wenn Sie die Appliance als erfolgreich bereitgestellt markieren möchten, führen Sie die CsCceApplianceDeploymentStatus wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="7978e-272">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="7978e-273">**Problem: Auf dem Hostserver oder den virtuellen Maschinen müssen Sie manuell nach Windows-Updates suchen bzw. diese installieren.**</span><span class="sxs-lookup"><span data-stu-id="7978e-273">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="7978e-p133">**Lösung:** Wir empfehlen Ihnen, dass Sie die Vorteile der automatisierten Betriebssystem-Updates der Skype for Business Cloud Connector Edition nutzen. Nachdem eine Appliance für die Online-Verwaltung registriert und das automatische Update des Betriebssystems aktiviert wurde, werden Windows-Updates vom Hostserver von den virtuellen Maschinen automatisch in Übereinstimmung mit den Windows-Einstellungen der Aktualisierungszeit für das Betriebssystem gesucht und installiert.</span><span class="sxs-lookup"><span data-stu-id="7978e-p133">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition. After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="7978e-p134">Wenn Sie manuell nach Windows-Updates suchen und diese installieren müssen, führen Sie die zu Ihrem Bereitstellungstyp passenden Schritte in diesem Abschnitt durch. Sie sollten das gleichzeitige Update des Hostservers und der darauf ausgeführten virtuellen Maschinen planen, um die bei Updates entstehenden Ausfallzeiten zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="7978e-p134">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment. You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="7978e-p135">Sie können auch einen WSUS (Windows Server Update Services)-Server für die Bereitstellung von Updates für Cloud Connector-Server verwenden. Stellen Sie hierfür nur sicher, dass Sie **nicht** die automatische Installation von Windows-Update konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7978e-p135">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers. Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="7978e-280">Weitere Informationen zum manuellen Update Ihrer Cloud Connector-Bereitstellung finden Sie im folgenden Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="7978e-280">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="7978e-281">**Problem: beim Aktualisieren des Cloud Connectors für einen neuen Build werden die Cmdlets für den Cloud Connector nicht aktualisiert.**</span><span class="sxs-lookup"><span data-stu-id="7978e-281">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="7978e-282">Dies geschieht manchmal, wenn ein PowerShell-Fenster geöffnet bleibt, wenn die automatische Aktualisierung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="7978e-282">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="7978e-283">**Auflösung:** Zum Laden der aktualisierten Cmdlets können Sie einen der folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="7978e-283">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="7978e-284">Schließen Sie PowerShell auf der Cloud Connector-Appliance, und öffnen Sie PowerShell erneut.</span><span class="sxs-lookup"><span data-stu-id="7978e-284">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="7978e-285">Sie können auch Import-Module CloudConnector-Force ausführen.</span><span class="sxs-lookup"><span data-stu-id="7978e-285">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="7978e-286">**Problem: "der Begriff" Stop-CsWindowsService "wird nicht als Name eines Cmdlets, einer Funktion, einer Skriptdatei oder eines bedienbaren Programms erkannt." Fehler beim Versuch, das Cmdlet "Enter-CcUpdate" auszuführen.**</span><span class="sxs-lookup"><span data-stu-id="7978e-286">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="7978e-287">**Auflösung:** Löschen Sie die $Home \appdata\local\microsoft\windows\powershell\moduleanalysiscache-Datei.</span><span class="sxs-lookup"><span data-stu-id="7978e-287">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="7978e-288">PowerShell erstellt diese Datei als einen Cache von Cmdlets von Modulen, die Sie findet, damit Sie nicht jedes Mal alle Module neu analysieren muss, da sich die Dinge wirklich verlangsamen würden.</span><span class="sxs-lookup"><span data-stu-id="7978e-288">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="7978e-289">Höchstwahrscheinlich gab es einige Dateibeschädigungen, die bei der Wiedergabe aus diesem Cache irreführende Ergebnisse für PowerShell bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="7978e-289">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="7978e-290">**Problem: "Import-Module CloudConnector" generiert Fehler "Import-Module: das angegebene Modul" CloudConnector "wurde nicht geladen, da in einem Modulverzeichnis keine gültige Moduldatei gefunden wurde."**</span><span class="sxs-lookup"><span data-stu-id="7978e-290">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="7978e-291">**Lösung:**</span><span class="sxs-lookup"><span data-stu-id="7978e-291">**Resolution:**</span></span>
    - <span data-ttu-id="7978e-292">Überprüfen Sie, ob das CloudConnector-Modul in der Tat unter c:\Program Files\WindowsPowerShell\Modules vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7978e-292">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="7978e-293">Nach dem überprüfen, ob das CloudConnector-Modul unter diesem Speicherort vorhanden ist, kann die PSModulePath-Umgebungsvariable, die den Pfad zu den Speicherorten der Module speichert, geändert werden:</span><span class="sxs-lookup"><span data-stu-id="7978e-293">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="7978e-294">a.</span><span class="sxs-lookup"><span data-stu-id="7978e-294">a.</span></span> <span data-ttu-id="7978e-295">Temporäre Änderung: Starten Sie PowerShell als Administrator, und führen Sie den folgenden Befehl aus: $env:P smodulepath = $ENV:P smodulepath + "; C:\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="7978e-295">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="7978e-296">b.</span><span class="sxs-lookup"><span data-stu-id="7978e-296">b.</span></span> <span data-ttu-id="7978e-297">Starten Sie für eine dauerhafte Änderung PowerShell als Administrator, und führen Sie die folgenden Befehle einzeln aus: $CurrentValue = [Umgebung]:: GetEnvironmentVariable ("PSModulePath"; "Machine") SetEnvironmentVariable ("PSModulePath"; $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules "," Machine ")</span><span class="sxs-lookup"><span data-stu-id="7978e-297">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="7978e-298">Manuelles Installieren von Windows-Updates</span><span class="sxs-lookup"><span data-stu-id="7978e-298">Install Windows updates manually</span></span>

<span data-ttu-id="7978e-299">Wenn Sie keine automatischen Updates in Ihrer Umgebung verwenden möchten, führen Sie die folgenden Schritte aus, um Windows-Updates manuell zu überprüfen und anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="7978e-299">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="7978e-300">Für das überprüfen und Installieren von Windows-Updates ist möglicherweise ein Serverneustart erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7978e-300">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="7978e-301">Wenn ein Hostserver neu gestartet wird, können Benutzer keinen Cloud Connector verwenden, um Anrufe zu tätigen oder zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="7978e-301">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="7978e-302">Sie können Aktualisierungen manuell suchen und installieren, um zu steuern, wann die Aktualisierungen erfolgen, und dann die Computer nach Bedarf zu von Ihnen gewählten Zeiten neu starten, um Dienstunterbrechungen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="7978e-302">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="7978e-303">Stellen Sie für die manuelle Suche nach Updates eine Verbindung zu jedem Hostserver her, und öffnen Sie die **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="7978e-303">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="7978e-304">Wählen Sie **System- \>und Sicherheitseinstellungen für Windows Update**aus, und verwalten Sie die Updates und Serverneustarts entsprechend Ihrer Umgebung.</span><span class="sxs-lookup"><span data-stu-id="7978e-304">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="7978e-305">Wenn Ihr Standort nur über eine Appliance verfügt, stellen Sie eine Verbindung zu jeder virtuellen Maschine her, und öffnen Sie die **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="7978e-305">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="7978e-306">Wählen Sie **System und \>Sicherheit Windows Update**aus, und konfigurieren Sie dann die Updates und Serverneustarts entsprechend.</span><span class="sxs-lookup"><span data-stu-id="7978e-306">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="7978e-p143">Wenn Ihr Standort über mehrere Appliances verfügt, können Benutzer während des Updates nicht auf die Instanz zugreifen, die gerade aktualisiert und neu gestartet wird. Benutzer stellen eine Verbindung zu anderen Instanzen in der Bereitstellung her, bis alle virtuellen Maschinen und alle Skype for Business-Dienste auf den virtuellen Maschinen nach Abschluss der Updates gestartet werden. Um mögliche Ausfallzeiten zu vermeiden, können Sie beim Anwenden der Updates die Instanz aus HA entfernen und sie nach Abschluss des Vorgangs wiederherstellen. Gehen Sie hierfür wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="7978e-p143">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates. Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed. To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete. To do so:</span></span>
    
1. <span data-ttu-id="7978e-311">Öffnen Sie auf allen Hostservern eine PowerShell-Konsole als Administrator.</span><span class="sxs-lookup"><span data-stu-id="7978e-311">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="7978e-312">Entfernen Sie die Instanz mit dem folgenden Cmdlet aus HA:</span><span class="sxs-lookup"><span data-stu-id="7978e-312">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="7978e-313">Führen Sie die Schritte für eine einzelne Instanz aus, um die Updates manuell anzuwenden und die virtuelle Maschine neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="7978e-313">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="7978e-314">Legen Sie die Instanz mit dem folgenden Cmdlet erneut auf HA fest:</span><span class="sxs-lookup"><span data-stu-id="7978e-314">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="7978e-315">Führen Sie für die Bereitstellungen mit mehreren Standorten die Schritte für einen einzelnen Standort für jeden Standort in der Bereitstellung aus, wobei die Updates jeweils auf einen Standort angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="7978e-315">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="7978e-316">Tipps für die Installation von Antivirus-Software auf dem Cloud Connector-Hostcomputer</span><span class="sxs-lookup"><span data-stu-id="7978e-316">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="7978e-317">Wenn Sie Antivirus-Software auf dem Cloud Connector-Hostcomputer installieren müssen, müssen Sie die folgenden Ausnahmen hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="7978e-317">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="7978e-318">Lokales Appliance-Verzeichnis auf jedem Computer.</span><span class="sxs-lookup"><span data-stu-id="7978e-318">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="7978e-319">Remote-Websiteverzeichnis auf jedem Computer.</span><span class="sxs-lookup"><span data-stu-id="7978e-319">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="7978e-320">Lokales Websiteverzeichnis auf dem Computer hostet den Stammordner der freigegebenen Website.</span><span class="sxs-lookup"><span data-stu-id="7978e-320">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="7978e-321">%ProgramFiles%\Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="7978e-321">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="7978e-322">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="7978e-322">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="7978e-323">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="7978e-323">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="7978e-324">Der Prozess Microsoft. RTC. CCE. Managementservice. exe.</span><span class="sxs-lookup"><span data-stu-id="7978e-324">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
