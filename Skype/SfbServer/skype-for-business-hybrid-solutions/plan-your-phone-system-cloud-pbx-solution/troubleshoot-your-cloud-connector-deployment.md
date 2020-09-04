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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Problembehandlung bei der Cloud Connector Edition-Bereitstellung.
ms.openlocfilehash: 7a1caea67c5b5899c2dc0909ef771a57c7c50389
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359331"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="c36c6-103">Problembehandlung bei Ihrer Cloud Connector-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="c36c6-103">Troubleshoot your Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="c36c6-104">Die Cloud Connector-Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online zurückgezogen.</span><span class="sxs-lookup"><span data-stu-id="c36c6-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="c36c6-105">Nachdem Ihre Organisation ein Upgrade auf Microsoft Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonie-Netzwerk mithilfe des [direkten Routings](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)mit Microsoft Teams verbinden.</span><span class="sxs-lookup"><span data-stu-id="c36c6-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="c36c6-106">Problembehandlung bei der Cloud Connector Edition-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="c36c6-106">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="c36c6-107">In diesem Thema werden Lösungen für häufige Probleme mit Cloud Connector Edition-Bereitstellungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c36c6-107">This topic describes solutions to common issues with Cloud Connector Edition deployments.</span></span> <span data-ttu-id="c36c6-108">Wenn Probleme mit Anrufen von und über das Telefon Festnetz (Public Switched Telephone Network, PSTN) auftreten, können Sie anhand der in diesem Thema beschriebenen Lösungen nachforschen.</span><span class="sxs-lookup"><span data-stu-id="c36c6-108">If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="c36c6-109">Cloud Connector bietet integrierte Mechanismen zum automatischen Beheben von Problemen.</span><span class="sxs-lookup"><span data-stu-id="c36c6-109">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="c36c6-110">Ein automatischer Erkennungsprozess sucht nach potenziellen Problemen mit den Cloud Connector-Appliances und führt, wenn möglich, Korrekturmaßnahmen durch, um diese Probleme zu beheben, ohne dass ein Administratoreingriff erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c36c6-110">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="c36c6-111">Der Erkennungsprozess funktioniert wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c36c6-111">The detection process works as follows:</span></span>
  
- <span data-ttu-id="c36c6-112">**Erkennungssequenz:** Der Cloud Connector-Verwaltungsdienst führt einen Prozess alle 60 Sekunden aus, um festzustellen, ob eine Appliance nicht aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="c36c6-112">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="c36c6-113">In Cloud Connector Version 2,0 und höher verwendet der Erkennungsprozess den Skype for Business Corpnet-Switch, um PowerShell-Verbindungen mit den Cloud Connector-Computern herzustellen. für frühere Versionen von 2,0 wird im Erkennungsprozess der Cloud Connector-Verwaltungs Switch verwendet.</span><span class="sxs-lookup"><span data-stu-id="c36c6-113">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c36c6-114">Damit die automatische Wiederherstellung erfolgreich ausgeführt werden kann, muss die Netzwerkverbindung zwischen dem Host und den virtuellen Computern über den Host Netzwerk Switch erfolgen.</span><span class="sxs-lookup"><span data-stu-id="c36c6-114">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="c36c6-115">Stellen Sie sicher, dass Sie die Netzwerkkonnektivität überprüfen, um sicherzustellen, dass die automatische Erkennung und Wiederherstellung erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="c36c6-115">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="c36c6-116">**Überwachung:** Die folgenden Dienste werden in Cloud Connector, Version 2,0 und höher, überwacht:</span><span class="sxs-lookup"><span data-stu-id="c36c6-116">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="c36c6-117">Virtuelle Computer sind nicht mit den Cloud Connector-Unternehmens-oder Internet-Switches verbunden</span><span class="sxs-lookup"><span data-stu-id="c36c6-117">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="c36c6-118">Virtuelle Computer befinden sich in einem gespeicherten oder gestoppten Status</span><span class="sxs-lookup"><span data-stu-id="c36c6-118">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="c36c6-119">Dienste für den zentralen Verwaltungs Server: Replikat, Master</span><span class="sxs-lookup"><span data-stu-id="c36c6-119">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="c36c6-120">Vermittlungsserver Dienste: Replica, RTCSRV und MEDSVC</span><span class="sxs-lookup"><span data-stu-id="c36c6-120">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="c36c6-121">Edgeserver Dienste: Replica, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="c36c6-121">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="c36c6-122">Eingehende Firewallregeln sind für CS RTCSRV auf dem Edgeserver, CS RTCMEDSRV auf dem Vermittlungsserver, deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c36c6-122">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="c36c6-123">In Cloud Connector, Version 1.4.2, werden nur die folgenden Dienste überwacht:</span><span class="sxs-lookup"><span data-stu-id="c36c6-123">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="c36c6-124">Vermittlungsserver Dienste: RTCSRV und MEDSVC</span><span class="sxs-lookup"><span data-stu-id="c36c6-124">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="c36c6-125">Edgeserver Dienst: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="c36c6-125">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="c36c6-126">**Wiederherstellungsprozess:** Wenn überwachte Dienste nicht verfügbar sind, wird eine Appliance markiert, und die Dienste werden angehalten und manuell markiert, bis alle Probleme gelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="c36c6-126">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="c36c6-127">Dadurch wird verhindert, dass Anrufe an eine Appliance weitergeleitet werden, die zu Anruf Fehlern führen können.</span><span class="sxs-lookup"><span data-stu-id="c36c6-127">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="c36c6-128">Der Cloud Connector-Verwaltungsdienst führt die automatische Wiederherstellung wie folgt erneut aus.</span><span class="sxs-lookup"><span data-stu-id="c36c6-128">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="c36c6-129">Das anfängliche Wiederholungsintervall beträgt alle zehn Sekunden mit einer maximalen Intervallzeit von einer Stunde.</span><span class="sxs-lookup"><span data-stu-id="c36c6-129">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="c36c6-130">Für die ersten drei Wiederherstellungsversuche beträgt die Intervallzeit 10 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="c36c6-130">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="c36c6-131">Ab dem vierten Wiederholungsversuch nimmt die Intervallzeit um das Zweifache der vorherigen Intervallzeit zu.</span><span class="sxs-lookup"><span data-stu-id="c36c6-131">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="c36c6-132">Beispielsweise wird der vierte Wiederholungsversuch in 20 Sekunden, dem fünften in 40 Sekunden usw. ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c36c6-132">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="c36c6-133">Wenn die maximale Intervallzeit von einer Stunde erreicht wird, werden Wiederholungsversuche einmal pro Stunde fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="c36c6-133">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="c36c6-134">Wenn die Wiederherstellung erfolgreich ist, werden die Intervall-und Wiederholungszähler auf Ihre anfänglichen Werte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c36c6-134">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="c36c6-135">Wenn der Verwaltungsdienst neu gestartet wird, werden das Intervall und die Wiederholungsanzahl auf die ursprünglichen Werte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="c36c6-135">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="c36c6-136">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="c36c6-136">Troubleshooting</span></span>

<span data-ttu-id="c36c6-137">Im folgenden finden Sie Lösungen zu häufig auftretenden Problemen:</span><span class="sxs-lookup"><span data-stu-id="c36c6-137">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="c36c6-138">**Problem: die Bereitstellung schlägt fehl oder reagiert nicht mehr, wenn die Bereitstellungsskripts ausgeführt werden. Nach der Anmeldung bei den einzelnen VM-Daten ist die IP-Adresse für die Verwaltungs-/interne/externe NIC nicht vorhanden oder falsch.**</span><span class="sxs-lookup"><span data-stu-id="c36c6-138">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="c36c6-139">**Lösung:** Dieses Problem kann nicht automatisch aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="c36c6-139">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="c36c6-140">NICs können während der Ausführung nicht zu VMS hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c36c6-140">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="c36c6-141">Beenden Sie diese VMs in Hyper-v Manager, und führen Sie dann die folgenden Cmdlets aus:</span><span class="sxs-lookup"><span data-stu-id="c36c6-141">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="c36c6-142">**Problem: Nachdem der Active Directory Server und die Gesamtstruktur installiert wurden, wurde der CMS-Server und/oder Vermittlungsserver der Domäne nicht ordnungsgemäß hinzugefügt.**</span><span class="sxs-lookup"><span data-stu-id="c36c6-142">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="c36c6-143">**Lösung:** Führen Sie die folgenden Schritte aus, um dieses Problem zu beheben:</span><span class="sxs-lookup"><span data-stu-id="c36c6-143">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="c36c6-144">Melden Sie sich am Active Directory Server an, und überprüfen Sie, ob die Domäne ordnungsgemäß erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c36c6-144">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="c36c6-145">Melden Sie sich beim CMS/Vermittlungsserver an, und stellen Sie sicher, dass auf der Corpnet-NIC eine gültige IP-Adresse zugewiesen ist und dass gültige statische IP-Adressen und DNS als IP-Adresse des Ad-Servers konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="c36c6-145">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="c36c6-146">Melden Sie sich beim CMS/Vermittlungsserver an, und öffnen Sie eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="c36c6-146">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="c36c6-147">Stellen Sie sicher, dass Sie den FQDN und die IP-Adresse des Active Directory Servers pingen können.</span><span class="sxs-lookup"><span data-stu-id="c36c6-147">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="c36c6-148">Wenn dies nicht der Fall ist, liegt möglicherweise ein IP-Adresskonflikt vor.</span><span class="sxs-lookup"><span data-stu-id="c36c6-148">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="c36c6-149">Versuchen Sie, eine neue IP für Active Directory zuzuweisen und DNS auf dem CMS/Vermittlungsserver entsprechend zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="c36c6-149">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="c36c6-150">**Problem: Sie erhalten die folgende Fehlermeldung "Remove-VMSwitch: failed beim Entfernen des virtuellen Ethernet-Switches". Der virtuelle Switch ' Cloud Connector Management Switch ' kann nicht gelöscht werden, da er von virtuellen Computern verwendet oder untergeordneten Pools zugewiesen wird. "**</span><span class="sxs-lookup"><span data-stu-id="c36c6-150">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="c36c6-151">**Lösung:** Der "Cloud Connector-Verwaltungs Switch" wurde nach der Bereitstellung nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c36c6-151">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="c36c6-152">Wenn Sie diesen Fehler getroffen haben, wechseln Sie zu Hyper-v-Manager, und stellen Sie sicher, dass noch kein virtueller Computer verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="c36c6-152">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="c36c6-153">Wenn noch virtuelle Computer angeschlossen sind, trennen Sie Sie, und löschen Sie den Verwaltungs Switch.</span><span class="sxs-lookup"><span data-stu-id="c36c6-153">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="c36c6-154">Wenn der Verwaltungs Switch immer noch nicht gelöscht werden kann, starten Sie den Hostserver neu, und versuchen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="c36c6-154">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="c36c6-155">**Problem: Sie erhalten die folgende Fehlermeldung "Dienst RTCMRAUTH konnte nicht gestartet werden. Stellen Sie sicher, dass der Dienst nicht deaktiviert ist. "**</span><span class="sxs-lookup"><span data-stu-id="c36c6-155">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c36c6-156">Dieses Problem bezieht sich nur auf Cloud Connector-Versionen früher als 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="c36c6-156">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="c36c6-157">Der Fehler beim starten könnte auch daran liegen, dass dieser Front-End-Server zuvor einen Failover durchführen konnte (bei einem Computer Failover).</span><span class="sxs-lookup"><span data-stu-id="c36c6-157">The failure to start could also be because this Front End server was previously failed over (using computer fail over).</span></span> <span data-ttu-id="c36c6-158">Wenn dies der Fall ist, rufen Sie Fail Back (using Computer Fail Back) auf.</span><span class="sxs-lookup"><span data-stu-id="c36c6-158">If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="c36c6-159">**Lösung:** Dieses Problem tritt auf einem Edgeserver auf, wenn das Zertifikat der Stammzertifizierungsstelle oder das Zertifikat der Zwischenzertifizierungsstelle nicht vom Edgeserver als vertrauenswürdig eingestuft wird.</span><span class="sxs-lookup"><span data-stu-id="c36c6-159">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server.</span></span> <span data-ttu-id="c36c6-160">Selbst wenn das externe Zertifikat importiert werden kann, die Zertifikatkette jedoch beschädigt ist.</span><span class="sxs-lookup"><span data-stu-id="c36c6-160">Even if the external certificate can be imported but the certificate chain is broken.</span></span> <span data-ttu-id="c36c6-161">Unter dieser Bedingung kann der RTCMRAUTH-und/oder der RTCSRV-Dienst nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="c36c6-161">Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="c36c6-162">Importieren Sie das Zertifikat der Stammzertifizierungsstelle und alle Zertifikate der Zwischenzertifizierungsstelle Ihres externen Zertifikats manuell in das Edgeserver, und starten Sie dann den Edgeserver neu.</span><span class="sxs-lookup"><span data-stu-id="c36c6-162">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server.</span></span> <span data-ttu-id="c36c6-163">Nachdem Sie die RTCMRAUTH-und RTCSRV-Dienste im Edgeserver gestartet haben, kehren Sie zu Ihrem Host Server zurück, starten Sie eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus, um zur neuen Bereitstellung zu wechseln:</span><span class="sxs-lookup"><span data-stu-id="c36c6-163">After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="c36c6-164">**Problem: der Hostserver wurde neu gestartet, als Windows-Updates angewendet wurden, und Anrufe, die vom Server gewartet werden, schlagen fehl.**</span><span class="sxs-lookup"><span data-stu-id="c36c6-164">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="c36c6-165">**Lösung:** Wenn Sie eine Umgebung mit hoher Verfügbarkeit bereitgestellt haben, stellt Microsoft ein Cmdlet zur Verfügung, mit dem ein Hostcomputer (Bereitstellungs Instanz) bei der manuellen Überprüfung und Installation von Windows Update in die oder aus der aktuellen Topologie gebracht werden kann.</span><span class="sxs-lookup"><span data-stu-id="c36c6-165">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="c36c6-166">Führen Sie die folgenden Schritte aus, um dies zu erreichen:</span><span class="sxs-lookup"><span data-stu-id="c36c6-166">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="c36c6-167">Starten Sie auf dem Hostserver eine PowerShell-Konsole als Administrator, und führen Sie dann Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="c36c6-167">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="c36c6-168">Suchen Sie nach Updates, und installieren Sie alle verfügbaren.</span><span class="sxs-lookup"><span data-stu-id="c36c6-168">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="c36c6-169">Führen Sie in der PowerShell-Konsole das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="c36c6-169">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="c36c6-170">**Problem: Wenn ein Anruf von einem Skype for Business-Client mit einer PSTN-Nummer getätigt wird, kann der Anruf nicht durch einladen einer anderen PSTN-Nummer zu einer Konferenz eskaliert werden.**</span><span class="sxs-lookup"><span data-stu-id="c36c6-170">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="c36c6-171">**Lösung:** Informationen zum Beheben dieses Problems finden Sie unter [configure Online Hybrid Vermittlungsserver Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span><span class="sxs-lookup"><span data-stu-id="c36c6-171">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="c36c6-172">**Problem: bei der Installation von Active Directory Server wird eine Warnmeldung zu Windows Update angezeigt – "automatische Windows-Updates sind nicht aktiviert. Aktivieren Sie Windows Update, um sicherzustellen, dass die neu installierte Rolle oder das Feature automatisch aktualisiert wird. "**</span><span class="sxs-lookup"><span data-stu-id="c36c6-172">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="c36c6-173">**Lösung:** Starten Sie eine Remote PowerShell-Mandanten Sitzung mit Skype for Business Mandanten-Administratoranmeldeinformationen, und führen Sie dann das folgende Cmdlet aus, um die _EnableAutoUpdate_ -Konfiguration Ihrer Website zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="c36c6-173">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="c36c6-174">Wenn  _EnableAutoUpdate_ auf **true**festgelegt ist, können Sie diese Warnmeldung gefahrlos ignorieren, da der CCEManagement-Dienst das herunterladen und Installieren von Windows-Updates für virtuelle Computer und den Hostserver übernimmt.</span><span class="sxs-lookup"><span data-stu-id="c36c6-174">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="c36c6-175">Wenn  _EnableAutoUpdate_ auf **false**festgelegt ist, führen Sie das folgende Cmdlet aus, um es auf **true**festzulegen.</span><span class="sxs-lookup"><span data-stu-id="c36c6-175">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="c36c6-176">Alternativ können Sie auch manuell nach Updates suchen und diese installieren.</span><span class="sxs-lookup"><span data-stu-id="c36c6-176">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="c36c6-177">Informationen dazu finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c36c6-177">See the next section.</span></span>
    
- <span data-ttu-id="c36c6-178">**Problem: Sie erhalten eine Fehlermeldung: die Appliance kann nicht registriert werden, da Ihre aktuelle Eingabe/Konfiguration oder oder oder \<SiteName\> \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> Konflikte mit vorhandenen Appliances (s) auftreten. Entfernen Sie die Konflikt-Appliance oder aktualisieren Sie Ihre Eingabe/Konfigurationsinformationen, und registrieren Sie sich dann erneut. ' beim Ausführen von Register-ccappliance ", um die aktuelle Appliance online zu registrieren.**</span><span class="sxs-lookup"><span data-stu-id="c36c6-178">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="c36c6-179">**Lösung:** Werte für das \<ApplianceName\> \<Mediation Server FQDN\> und \<Mediation Server IP Address\> müssen eindeutig sein und nur für eine Appliance-Registrierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c36c6-179">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="c36c6-180">Standardmäßig \<ApplianceName\> stammt aus dem Hostnamen.</span><span class="sxs-lookup"><span data-stu-id="c36c6-180">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="c36c6-181">\<Mediation Server FQDN\> und \<Mediation Server IP Address\> in der Konfigurations-ini-Datei definiert.</span><span class="sxs-lookup"><span data-stu-id="c36c6-181">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="c36c6-182">Verwenden Sie beispielsweise (Appliancename = MyserverNew, Vermittlungsserver FQDN = ms. contoso. com, Vermittlungsserver IP Address = 10.10.10.10), um sich auf Sitename = mysite zu registrieren, aber wenn es eine registrierte Appliance gibt (Appliancename = MyServer, Vermittlungsserver FQDN = ms. contoso. com, Vermittlungsserver IP Address = 10.10.10.10), haben Sie den Konflikt.</span><span class="sxs-lookup"><span data-stu-id="c36c6-182">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="c36c6-183">Überprüfen Sie zuerst die CloudConnector.ini Datei im Abschnitt ApplianceRoot Directory.</span><span class="sxs-lookup"><span data-stu-id="c36c6-183">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="c36c6-184">Sie erhalten \<SiteName\> , \<Mediation Server FQDN\> und \<Mediation Server IP Address\> Werte in der Datei.</span><span class="sxs-lookup"><span data-stu-id="c36c6-184">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="c36c6-185">\<ApplianceName\> ist der Name des Hostservers.</span><span class="sxs-lookup"><span data-stu-id="c36c6-185">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="c36c6-186">Starten Sie als zweites die mandantenfähige Remote-PowerShell mit Ihren Skype for Business Mandanten-Administratoranmeldeinformationen, und führen Sie dann das folgende Cmdlet aus, um die registrierten Appliances zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c36c6-186">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="c36c6-187">Nachdem Sie Konflikte identifiziert haben, können Sie entweder die CloudConnector.ini Datei mit Informationen aktualisieren, die mit der registrierten Appliance übereinstimmen, oder die Registrierung der vorhandenen Appliance aufheben, um die Konflikte zu lösen.</span><span class="sxs-lookup"><span data-stu-id="c36c6-187">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="c36c6-188">**Problem: das Get-CcRunningVersion-Cmdlet gibt einen leeren Wert zurück, wenn auf dem Host eine bereitgestellte Appliance installiert ist.**</span><span class="sxs-lookup"><span data-stu-id="c36c6-188">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="c36c6-189">**Lösung:** Dies kann passieren, wenn Sie ein Upgrade von 1.3.4 oder 1.3.8 auf 1.4.1 durchführen.</span><span class="sxs-lookup"><span data-stu-id="c36c6-189">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="c36c6-190">Nachdem Sie die Version 1.4.1 mit der MSI-Installation installiert haben, müssen Sie ausgeführt werden, `Register-CcAppliance` bevor Sie ein anderes Cmdlet ausführen.</span><span class="sxs-lookup"><span data-stu-id="c36c6-190">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="c36c6-191">`Register-CcAppliance` die module.ini Datei wird von%USERPROFILE%\CloudConnector zu%ProgramData%\CloudConnector. migriert.</span><span class="sxs-lookup"><span data-stu-id="c36c6-191">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="c36c6-192">Wenn Sie ihn verpasst haben, wird ein neuer module.ini im Ordner%ProgramData%\CloudConnector erstellt, und die Informationen zur ausgeführten/Sicherungsversion für 1.3.4 oder 1.3.8 werden ersetzt.</span><span class="sxs-lookup"><span data-stu-id="c36c6-192">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="c36c6-193">Vergleichen Sie module.ini Dateien im Ordner%UserProfile%\CloudConnector und%ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="c36c6-193">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="c36c6-194">Wenn es Unterschiede gibt, löschen Sie die module.ini Datei in%ProgramData%\CloudConnector, und führen Sie eine erneute Ausführung aus  `Register-CcAppliance` .</span><span class="sxs-lookup"><span data-stu-id="c36c6-194">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="c36c6-195">Sie können die Datei auch manuell in die richtige Ausführungs-und Sicherungsversion ändern.</span><span class="sxs-lookup"><span data-stu-id="c36c6-195">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="c36c6-196">**Problem: Nachdem Sie das Switch-CcVersion-Cmdlet ausgeführt haben, um zu einer älteren Version zu wechseln, die sich von der aktuellen Skriptversion unterscheidet, gibt es keine Unterstützung für hohe Verfügbarkeit für diese alte Version.**</span><span class="sxs-lookup"><span data-stu-id="c36c6-196">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="c36c6-197">**Lösung:** Sie haben beispielsweise ein Upgrade von 1.4.1 auf 1.4.2 durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="c36c6-197">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="c36c6-198">Ihre aktuelle Skriptversion, die durch Ausführen bestimmt werden kann `Get-CcVersion` , und die laufende Version, die durch Ausführen bestimmt werden kann,  `Get-CcRunningVersion` sind beide 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="c36c6-198">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="c36c6-199">Wenn Sie zu diesem Zeitpunkt ausführen, `Switch-CcVersion` um die ausgeführte Version wieder auf 1.4.1 umzuschalten, wird keine Unterstützung für hohe Verfügbarkeit für diese alte Version verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="c36c6-199">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="c36c6-200">Um eine vollständige Unterstützung für hohe Verfügbarkeit zu erhalten, wechseln Sie zurück zu 1.4.2, sodass die laufende Version und die Skriptversion identisch sind.</span><span class="sxs-lookup"><span data-stu-id="c36c6-200">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same.</span></span> <span data-ttu-id="c36c6-201">Wenn Probleme mit ihrer 1.4.2-Bereitstellung auftreten, deinstallieren Sie Sie, und installieren Sie Sie so bald wie möglich neu.</span><span class="sxs-lookup"><span data-stu-id="c36c6-201">If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="c36c6-202">**Problem: Zertifikat Zertifizierungsstellenzertifikate oder interne Zertifikate, die für zentraler Verwaltungsspeicher, Vermittlungsserver und Edgeserver ausgestellt wurden, sind nahezu abgelaufen oder werden kompromittiert.**</span><span class="sxs-lookup"><span data-stu-id="c36c6-202">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="c36c6-203">**Lösung:** Skype for Business Zertifizierungsstellenzertifikate sind fünf Jahre gültig.</span><span class="sxs-lookup"><span data-stu-id="c36c6-203">**Resolution:** Skype for Business certification authority certificates are valid for five years.</span></span> <span data-ttu-id="c36c6-204">Interne Zertifikate, die für die zentraler Verwaltungsspeicher, Vermittlungsserver und Edgeserver ausgestellt wurden, gelten für zwei Jahre.</span><span class="sxs-lookup"><span data-stu-id="c36c6-204">Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c36c6-205">In Cloud Connector Version 2,0 und höher wurde das Cmdlet Renew-ccservercertificate "in Update-ccservercertificate" geändert, und das Cmdlet Renew-cccacertificate "wurde in Update-cccacertificate" geändert.</span><span class="sxs-lookup"><span data-stu-id="c36c6-205">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="c36c6-206">Wenn die für zentraler Verwaltungsspeicher, Vermittlungsserver und Edgeserver ausgestellten internen Zertifikate nahezu abgelaufen sind oder kompromittiert sind, führen Sie das Cmdlet Renew-ccservercertificate "oder Update-ccservercertificate" aus, um Ihre Zertifikate zu erneuern.</span><span class="sxs-lookup"><span data-stu-id="c36c6-206">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="c36c6-207">Wenn Zertifizierungsstellenzertifikate kurz vor dem Ablauf sind, führen Sie das Cmdlet Renew-cccacertificate "oder Update-cccacertificate" aus, um Ihre Zertifikate zu erneuern.</span><span class="sxs-lookup"><span data-stu-id="c36c6-207">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="c36c6-208">**Wenn Zertifizierungsstellenzertifikate kompromittiert sind und nur eine Appliance am Standort vorhanden ist,** führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c36c6-208">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="c36c6-209">Führen Sie das Cmdlet Enter-CCUpdate "aus, um die Dienste zu entladen und die Appliance in den Wartungsmodus zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="c36c6-209">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="c36c6-210">Führen Sie die folgenden Cmdlets aus, um neue Zertifizierungsstellenzertifikate und alle internen Serverzertifikate zurückzusetzen und zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="c36c6-210">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="c36c6-211">Für Cloud Connector-Versionen vor 2,0:</span><span class="sxs-lookup"><span data-stu-id="c36c6-211">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="c36c6-212">Oder für Cloud Connector Release 2,0 und höher:</span><span class="sxs-lookup"><span data-stu-id="c36c6-212">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="c36c6-213">Wenn TLS zwischen dem Gateway und dem Vermittlungsserver verwendet wird, führen Sie das Cmdlet Export-CcRootCertificate aus der Appliance aus, und installieren Sie dann das exportierte Zertifikat in ihren PSTN-Gateways.</span><span class="sxs-lookup"><span data-stu-id="c36c6-213">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="c36c6-214">Möglicherweise müssen Sie das Zertifikat auch erneut auf dem Gateway ausgeben.</span><span class="sxs-lookup"><span data-stu-id="c36c6-214">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="c36c6-215">Führen Sie das Cmdlet Exit-CCUpdate "aus, um die Dienste zu starten und den Wartungsmodus zu beenden.</span><span class="sxs-lookup"><span data-stu-id="c36c6-215">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="c36c6-216">**Wenn Zertifizierungsstellenzertifikate kompromittiert sind und sich an dem Standort mehrere Appliances befinden,** führen Sie die folgenden Schritte auf jeder Appliance am Standort aus.</span><span class="sxs-lookup"><span data-stu-id="c36c6-216">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="c36c6-217">Microsoft empfiehlt, dass Sie diese Schritte während nicht-Spitzennutzungszeiten durchführen.</span><span class="sxs-lookup"><span data-stu-id="c36c6-217">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="c36c6-218">Führen Sie auf der ersten Appliance das Cmdlet Remove-CcCertificationAuthorityFile aus, um die Sicherungsdateien der Zertifizierungsstelle im Verzeichnis zu bereinigen \<SiteRoot\> .</span><span class="sxs-lookup"><span data-stu-id="c36c6-218">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="c36c6-219">Führen Sie das Cmdlet Enter-CCUpdate "aus, um die Dienste zu entladen und die einzelnen Appliances in den Wartungsmodus zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="c36c6-219">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="c36c6-220">Führen Sie auf der ersten Appliance die folgenden Cmdlets aus, um neue Zertifizierungsstellenzertifikate und alle internen Serverzertifikate zurückzusetzen und zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="c36c6-220">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="c36c6-221">Für Cloud Connector-Versionen vor 2,0:</span><span class="sxs-lookup"><span data-stu-id="c36c6-221">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="c36c6-222">Oder für Cloud Connector Release 2,0 und höher:</span><span class="sxs-lookup"><span data-stu-id="c36c6-222">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="c36c6-223">Führen Sie auf der ersten Appliance das folgende Cmdlet aus, um die Zertifizierungsstellen Dateien in den Ordner zu sichern \<SiteRoot\> .</span><span class="sxs-lookup"><span data-stu-id="c36c6-223">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="c36c6-224">Führen Sie auf allen anderen Appliances am selben Standort die folgenden Befehle aus, um die Sicherungsdateien der Zertifizierungsstelle zu nutzen, damit die Appliances alle dasselbe Stammzertifikat verwenden und dann neue Zertifikate anfordern.</span><span class="sxs-lookup"><span data-stu-id="c36c6-224">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="c36c6-225">Wenn TLS zwischen dem Gateway und dem Vermittlungsserver verwendet wird, führen Sie das Cmdlet Export-CcRootCertificate von einer beliebigen Appliance am Standort aus, und installieren Sie dann das exportierte Zertifikat in ihren PSTN-Gateways.</span><span class="sxs-lookup"><span data-stu-id="c36c6-225">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="c36c6-226">Möglicherweise müssen Sie das Zertifikat auch erneut auf dem Gateway ausgeben.</span><span class="sxs-lookup"><span data-stu-id="c36c6-226">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="c36c6-227">Führen Sie das Cmdlet Exit-CCUpdate "aus, um die Dienste zu starten und den Wartungsmodus zu beenden.</span><span class="sxs-lookup"><span data-stu-id="c36c6-227">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="c36c6-228">**Problem: Sie erhalten die folgende Fehlermeldung im Cloud Connector-Verwaltungsdienst Protokoll "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": "cceservice"-Fehler: 0: unerwartete Ausnahme beim Melden von Status an Online: System. Management. Automation. CmdletInvocationException: Anmeldung für den Benutzer ist fehlgeschlagen \<Global Tenant Admin\> . Erstellen Sie ein neues Credential-Objekt, um sicherzustellen, dass Sie den richtigen Benutzernamen und das richtige Kennwort verwendet haben. ---\>**</span><span class="sxs-lookup"><span data-stu-id="c36c6-228">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="c36c6-229">**Lösung:** Die Anmeldeinformationen des globalen Mandanten Administrators von Microsoft 365 oder Office 365 wurden seit der Registrierung der Cloud Connector-Appliance geändert.</span><span class="sxs-lookup"><span data-stu-id="c36c6-229">**Resolution:** The Microsoft 365 or Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="c36c6-230">Um die lokal gespeicherten Anmeldeinformationen in der Cloud Connector-Appliance zu aktualisieren, führen Sie die folgenden von Administrator-PowerShell auf der Host-Appliance aus:</span><span class="sxs-lookup"><span data-stu-id="c36c6-230">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="c36c6-231">**Problem: nach dem Ändern des Kennworts für das Hostserver Konto, das Sie für die Bereitstellung verwendet haben, wird die folgende Fehlermeldung angezeigt: "ConvertTo-SecureString: Key ungültig für die Verwendung in angegebenem Zustand." in%ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log oder beim Ausführen des Cmdlets Get-CcCredential.**</span><span class="sxs-lookup"><span data-stu-id="c36c6-231">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="c36c6-232">**Lösung:** Alle Cloud Connector-Anmeldeinformationen werden in der folgenden Datei gespeichert: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ".</span><span class="sxs-lookup"><span data-stu-id="c36c6-232">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="c36c6-233">Wenn das Kennwort auf dem Hostserver geändert wird, müssen Sie die lokal gespeicherten Anmeldeinformationen aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="c36c6-233">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="c36c6-234">**Wenn Sie Cloud Connector, Version 1.4.2, ausführen, generieren Sie** alle Cloud Connector-Kennwörter mit den folgenden Schritten neu:</span><span class="sxs-lookup"><span data-stu-id="c36c6-234">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="c36c6-235">Starten Sie den Hostserver neu.</span><span class="sxs-lookup"><span data-stu-id="c36c6-235">Restart the host server.</span></span>
    
  2. <span data-ttu-id="c36c6-236">Löschen Sie die folgende Datei: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ".</span><span class="sxs-lookup"><span data-stu-id="c36c6-236">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="c36c6-237">Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie dann "Register-ccappliance"-local "aus, um die Kennwörter nach der Beschreibung erneut einzugeben.</span><span class="sxs-lookup"><span data-stu-id="c36c6-237">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="c36c6-238">Geben Sie dieselben Kennwörter ein, die Sie zuvor für die Cloud Connector-Bereitstellung eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="c36c6-238">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="c36c6-239">**Wenn Sie Cloud Connector, Version 2,0 oder höher, ausführen, generieren Sie** alle Cloud Connector-Kennwörter mit den folgenden Schritten neu:</span><span class="sxs-lookup"><span data-stu-id="c36c6-239">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="c36c6-240">Starten Sie den Hostserver neu.</span><span class="sxs-lookup"><span data-stu-id="c36c6-240">Restart the host server.</span></span>
    
  5. <span data-ttu-id="c36c6-241">Löschen Sie die folgende Datei: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ".</span><span class="sxs-lookup"><span data-stu-id="c36c6-241">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="c36c6-242">Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie dann "Register-ccappliance"-local "aus, um die Kennwörter nach der Beschreibung erneut einzugeben.</span><span class="sxs-lookup"><span data-stu-id="c36c6-242">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="c36c6-243">Wenn die zwischengespeicherte Kennwortdatei mit Cloud Connector Version 1.4.2 generiert wurde, verwenden Sie das "vmadmin"-Kennwort für das "cceservice"-Kennwort, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="c36c6-243">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted.</span></span> <span data-ttu-id="c36c6-244">Geben Sie das gleiche Kennwort ein, das Sie zuvor für die Cloud Connector-Bereitstellung für alle anderen Konten eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="c36c6-244">Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="c36c6-245">Wenn die zwischengespeicherte Kennwortdatei mit dem Cloud Connector Version 1.4.2 generiert wurde und die DomainAdmin-und "vmadmin"-Kennwörter unterschiedlich sind, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="c36c6-245">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="c36c6-246">Führen Sie wie folgt "Sets-CcCredential-AccountType DomainAdmin" aus:</span><span class="sxs-lookup"><span data-stu-id="c36c6-246">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="c36c6-247">Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das "cceservice"-Kennwort verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="c36c6-247">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="c36c6-248">Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das DomainAdmin-Kennwort ein, das Sie zuvor verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="c36c6-248">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="c36c6-249">Wenn die zwischengespeicherte Kennwortdatei mit Cloud Connector Version 2,0 oder höher generiert wurde, verwenden "vmadmin" und DomainAdmin standardmäßig dasselbe Kennwort wie "cceservice".</span><span class="sxs-lookup"><span data-stu-id="c36c6-249">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="c36c6-250">Wenn Sie die DomainAdmin-und "vmadmin"-Kennwörter geändert haben, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="c36c6-250">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="c36c6-251">Führen Sie wie folgt "Sets-CcCredential-AccountType DomainAdmin" aus:</span><span class="sxs-lookup"><span data-stu-id="c36c6-251">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="c36c6-252">Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das Kennwort "cceservice" verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="c36c6-252">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="c36c6-253">Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das DomainAdmin-Kennwort ein, das Sie zuvor verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="c36c6-253">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="c36c6-254">Führen Sie wie folgt "Sets-CcCredential-AccountType" vmadmin "" aus:</span><span class="sxs-lookup"><span data-stu-id="c36c6-254">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="c36c6-255">Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das Kennwort "cceservice" verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="c36c6-255">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="c36c6-256">Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das "vmadmin"-Kennwort ein, das Sie zuvor verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="c36c6-256">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="c36c6-257">**Problem: bei der Cloud Connector-Version 2,1 und höher wird beim Ausführen von Register-ccappliance "oder anderen Cmdlets für die Appliance eine Fehlermeldung wie:" für jedes-Objekt: die Eigenschaft "Common" kann für dieses Objekt nicht gefunden werden angezeigt. Stellen Sie sicher, dass die Eigenschaft vorhanden ist. Unter C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 Char: 14 "**</span><span class="sxs-lookup"><span data-stu-id="c36c6-257">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="c36c6-258">**Lösung:** Für Cloud Connector 2,1 und höher ist .NET Framework 4.6.1 oder höher erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c36c6-258">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="c36c6-259">Aktualisieren Sie .NET Framework auf der Appliance auf Version 4.6.1 oder höher, und führen Sie das Cmdlet (s) erneut aus.</span><span class="sxs-lookup"><span data-stu-id="c36c6-259">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="c36c6-260">**Problem: bei der Cloud Connector Edition 2,1 wird bei der Ausführung von install-ccappliance "eine Fehlermeldung wie die folgende angezeigt:" Fehler beim Installieren der neuen Instanz mit Fehler: "State kann nicht festgelegt werden", da nur Zeichenfolgen als Werte zum Festlegen von XmlNode-Eigenschaften verwendet werden können "**</span><span class="sxs-lookup"><span data-stu-id="c36c6-260">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="c36c6-261">**Lösung:** Fügen Sie in Cloudconnector.ini im Abschnitt [common] die Konfigurationsdatei "State" wie unten hinzu: CountryCode = US State = WA City = Redmond</span><span class="sxs-lookup"><span data-stu-id="c36c6-261">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="c36c6-262">Es ist nicht erforderlich, dass die "State"-Reihe einen Wert aufweist, die "State"-Reihe kann jedoch nicht aus der Cloudconnector.ini Datei entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="c36c6-262">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="c36c6-263">**Problem: Sie erhalten die folgende Fehlermeldung "Dismount-WindowsImage: Dismount-WindowsImage failed. Fehlercode = 0xc1550115 "beim Installieren oder Aktualisieren von Cloud Connector Edition.**</span><span class="sxs-lookup"><span data-stu-id="c36c6-263">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="c36c6-264">**Lösung:** Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie "DISM-Cleanup-WIM" aus.</span><span class="sxs-lookup"><span data-stu-id="c36c6-264">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="c36c6-265">Dadurch werden alle unruhigen Bilder bereinigt.</span><span class="sxs-lookup"><span data-stu-id="c36c6-265">This will clean up all troubled images.</span></span> <span data-ttu-id="c36c6-266">Führen Sie Install-ccappliance "erneut aus, oder warten Sie, bis die Bits automatisch aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="c36c6-266">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="c36c6-267">**Problem: die Bereitstellung der ersten Cloud Connector-Appliance in einer ha-Umgebung schlägt fehl**</span><span class="sxs-lookup"><span data-stu-id="c36c6-267">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="c36c6-268">**Lösung:** Die Schritte, die Sie ausführen, hängen davon ab, warum die Bereitstellung fehlgeschlagen ist:</span><span class="sxs-lookup"><span data-stu-id="c36c6-268">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="c36c6-269">Wenn die erste Cloud Connector-Appliance fehlschlägt und Sie den Grund für den Fehler nicht ermitteln können, müssen Sie die Appliance erst dann erneut installieren, wenn die Bereitstellung erfolgreich war, und dann die anderen Appliances installieren.</span><span class="sxs-lookup"><span data-stu-id="c36c6-269">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="c36c6-270">Wenn bei der ersten Cloud Connector-Appliance ein kleineres Problem auftritt, beispielsweise ein externes Zertifikat, können Sie das Problem möglicherweise beheben, ohne die Appliance erneut zu installieren.</span><span class="sxs-lookup"><span data-stu-id="c36c6-270">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="c36c6-271">Anschließend können Sie die Remote-PowerShell von Mandanten verwenden, um die Bereitstellung wie folgt als erfolgreich zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="c36c6-271">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="c36c6-272">(Wenn die erste Bereitstellung erfolgreich war, können Sie auch die folgenden Schritte verwenden, aber aus irgendeinem Grund kann Cloud Connector die Bereitstellung nicht als Erfolg melden.)</span><span class="sxs-lookup"><span data-stu-id="c36c6-272">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="c36c6-273">Um die Identität (GUID) der ersten Cloud Connector-Appliance abzurufen, führen Sie das Cmdlet Get-CsHybridPSTNAppliance aus.</span><span class="sxs-lookup"><span data-stu-id="c36c6-273">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="c36c6-274">Um die Appliance als erfolgreich bereitgestellt zu markieren, führen Sie das-CsCceApplianceDeploymentStatus wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="c36c6-274">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="c36c6-275">**Problem: Sie müssen Windows-Updates manuell auf dem Hostserver oder auf virtuellen Computern überprüfen und installieren.**</span><span class="sxs-lookup"><span data-stu-id="c36c6-275">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="c36c6-276">**Lösung:** Es wird empfohlen, dass Sie die von Skype for Business Cloud Connector Edition bereitgestellten automatisierten Betriebssystemupdates nutzen.</span><span class="sxs-lookup"><span data-stu-id="c36c6-276">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="c36c6-277">Nachdem eine Appliance für die Online Verwaltung registriert wurde und das automatische Betriebssystemupdate aktiviert ist, werden der Hostserver und die virtuellen Computer Windows-Updates automatisch entsprechend den Einstellungen des Zeitfensters für das Betriebssystemupdate überprüfen und installieren.</span><span class="sxs-lookup"><span data-stu-id="c36c6-277">After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="c36c6-278">Wenn Sie Windows-Updates manuell überprüfen und installieren müssen, befolgen Sie die Schritte in diesem Abschnitt, die für Ihre Art der Bereitstellung gelten.</span><span class="sxs-lookup"><span data-stu-id="c36c6-278">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment.</span></span> <span data-ttu-id="c36c6-279">Sie sollten sowohl den Hostserver als auch die virtuellen Computer, auf denen er ausgeführt wird, gleichzeitig aktualisieren, um die für die Aktualisierungen erforderliche Ausfallzeit zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="c36c6-279">You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="c36c6-280">Wenn Sie dies bevorzugen, können Sie einen WSUS-Server (Windows Server Update Services) verwenden, um Updates für Cloud Connector-Server bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c36c6-280">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers.</span></span> <span data-ttu-id="c36c6-281">Achten Sie darauf, dass Sie das Windows-Update so konfigurieren, dass es **nicht** automatisch installiert wird.</span><span class="sxs-lookup"><span data-stu-id="c36c6-281">Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="c36c6-282">Informationen zum manuellen Aktualisieren Ihrer Cloud Connector-Bereitstellung finden Sie im folgenden Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c36c6-282">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="c36c6-283">**Problem: Wenn Cloud Connector für einen neuen Build aktualisiert wird, werden die Cloud Connector-Cmdlets nicht aktualisiert.**</span><span class="sxs-lookup"><span data-stu-id="c36c6-283">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="c36c6-284">Dies geschieht manchmal, wenn ein PowerShell-Fenster geöffnet bleibt, wenn die automatische Aktualisierung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="c36c6-284">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="c36c6-285">**Lösung:** Um die aktualisierten Cmdlets zu laden, können Sie einen der folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="c36c6-285">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="c36c6-286">Schließen Sie PowerShell in der Cloud Connector-Appliance, und öffnen Sie dann PowerShell erneut.</span><span class="sxs-lookup"><span data-stu-id="c36c6-286">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="c36c6-287">Sie können auch Import-Module "cloudconnector-Force ausführen.</span><span class="sxs-lookup"><span data-stu-id="c36c6-287">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="c36c6-288">**Problem: "der Ausdruck" Stop-CsWindowsService "wird nicht als Name eines Cmdlets, einer Funktion, einer Skriptdatei oder eines benutzbaren Programms erkannt." Fehler beim Versuch, das Enter-CCUpdate "-Cmdlet auszuführen.**</span><span class="sxs-lookup"><span data-stu-id="c36c6-288">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="c36c6-289">**Lösung:** Löschen Sie die $Home \appdata\local\microsoft\windows\powershell\moduleanalysiscache-Datei.</span><span class="sxs-lookup"><span data-stu-id="c36c6-289">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="c36c6-290">Diese Datei wird von PowerShell als Cache von Cmdlets aus Modulen erstellt, die Sie findet, sodass Sie nicht jedes Mal alle Module erneut analysieren müssen, da dies die Dinge wirklich langsam machen würde.</span><span class="sxs-lookup"><span data-stu-id="c36c6-290">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="c36c6-291">Höchstwahrscheinlich gab es einige Dateibeschädigungen, die beim Lesen aus diesem Cache irreführende Ergebnisse für PowerShell bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="c36c6-291">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="c36c6-292">**Problem: "Import-Module" cloudconnector "generiert Fehler" Import-Module: das angegebene Modul "" cloudconnector "wurde nicht geladen, da in keinem Modulverzeichnis eine gültige Moduldatei gefunden wurde."**</span><span class="sxs-lookup"><span data-stu-id="c36c6-292">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="c36c6-293">**Lösung:**</span><span class="sxs-lookup"><span data-stu-id="c36c6-293">**Resolution:**</span></span>
    - <span data-ttu-id="c36c6-294">Überprüfen, ob das "cloudconnector-Modul tatsächlich unter c:\Program Files\WindowsPowerShell\Modules vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="c36c6-294">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="c36c6-295">Nachdem Sie überprüft haben, dass das "cloudconnector-Modul unter diesem Speicherort vorhanden ist, kann die PSModulePath-Umgebungsvariable, die den Pfad zu den Speicherorten der Module speichert, geändert werden:</span><span class="sxs-lookup"><span data-stu-id="c36c6-295">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="c36c6-296">a.</span><span class="sxs-lookup"><span data-stu-id="c36c6-296">a.</span></span> <span data-ttu-id="c36c6-297">Temporäre Änderung: Starten Sie PowerShell als Administrator, und führen Sie den folgenden Befehl aus: $env:P smodulepath = $ENV:P smodulepath + "; C:\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="c36c6-297">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="c36c6-298">b.</span><span class="sxs-lookup"><span data-stu-id="c36c6-298">b.</span></span> <span data-ttu-id="c36c6-299">Für eine beständige Änderung starten Sie PowerShell als Administrator, und führen Sie die folgenden Befehle nacheinander aus: $CurrentValue = [Environment]:: GetEnvironmentVariable ("PSModulePath", "Machine") SetEnvironmentVariable ("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules "," Machine ")</span><span class="sxs-lookup"><span data-stu-id="c36c6-299">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="c36c6-300">Manuelles Installieren von Windows-Updates</span><span class="sxs-lookup"><span data-stu-id="c36c6-300">Install Windows updates manually</span></span>

<span data-ttu-id="c36c6-301">Wenn Sie keine automatischen Updates in Ihrer Umgebung verwenden möchten, führen Sie die folgenden Schritte aus, um Windows-Updates manuell zu überprüfen und anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="c36c6-301">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="c36c6-302">Für die Überprüfung und Installation von Windows-Updates ist möglicherweise ein Serverneustart erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c36c6-302">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="c36c6-303">Wenn ein Hostserver neu gestartet wird, können Benutzer keine Cloud Connector verwenden, um Anrufe zu tätigen oder zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="c36c6-303">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="c36c6-304">Sie können manuell nach Updates suchen und diese installieren, um zu steuern, wann die Updates ausgeführt werden, und dann die Computer bei Bedarf während der Zeit neu starten, die Sie zur Vermeidung von Unterbrechungen der Dienste auswählen.</span><span class="sxs-lookup"><span data-stu-id="c36c6-304">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="c36c6-305">Wenn Sie manuell nach Updates suchen möchten, stellen Sie eine Verbindung zu jedem Hostserver her, und öffnen Sie die **System**Steuerung.</span><span class="sxs-lookup"><span data-stu-id="c36c6-305">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="c36c6-306">Wählen Sie **System and Security \> Windows Update**aus, und verwalten Sie dann die Updates und Serverneustarts entsprechend Ihrer Umgebung.</span><span class="sxs-lookup"><span data-stu-id="c36c6-306">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="c36c6-307">Wenn sich nur eine Appliance am Standort befindet, stellen Sie eine Verbindung zu jedem virtuellen Computer her, und öffnen Sie die **System**Steuerung.</span><span class="sxs-lookup"><span data-stu-id="c36c6-307">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="c36c6-308">Wählen Sie **System and Security \> Windows Update**aus, und konfigurieren Sie dann die Updates und Serverneustarts je nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="c36c6-308">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="c36c6-309">Wenn sich mehr als eine Appliance am Standort befindet, kann der Zugriff auf die Instanz, die aktualisiert und neu gestartet wird, während der Updates nicht von Benutzern erreicht werden.</span><span class="sxs-lookup"><span data-stu-id="c36c6-309">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates.</span></span> <span data-ttu-id="c36c6-310">Benutzer stellen eine Verbindung mit anderen Instanzen in der Bereitstellung her, bis alle virtuellen Computer und alle Skype for Business Dienste auf den virtuellen Computern gestartet werden, nachdem die Updates abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="c36c6-310">Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed.</span></span> <span data-ttu-id="c36c6-311">Um mögliche Dienstunterbrechungen zu vermeiden, können Sie die Instanz aus dem ha-Objekt entfernen, während Sie die Updates anwenden, und diese dann nach Abschluss wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="c36c6-311">To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete.</span></span> <span data-ttu-id="c36c6-312">Gehen Sie hierzu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="c36c6-312">To do so:</span></span>
    
1. <span data-ttu-id="c36c6-313">Öffnen Sie auf jedem Hostserver eine PowerShell-Konsole als Administrator.</span><span class="sxs-lookup"><span data-stu-id="c36c6-313">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="c36c6-314">Entfernen Sie die Instanz mit dem folgenden Cmdlet aus ha:</span><span class="sxs-lookup"><span data-stu-id="c36c6-314">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="c36c6-315">Führen Sie die Schritte für eine einzelne Instanz aus, um die Updates manuell anzuwenden und den virtuellen Computer neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="c36c6-315">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="c36c6-316">Legen Sie die Instanz mit dem folgenden Cmdlet wieder auf ha fest:</span><span class="sxs-lookup"><span data-stu-id="c36c6-316">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="c36c6-317">Für Bereitstellungen mit mehreren Standorten führen Sie die Schritte für einen einzelnen Standort für jeden Standort in der Bereitstellung aus, und wenden Sie gleichzeitig Aktualisierungen auf eine Website an.</span><span class="sxs-lookup"><span data-stu-id="c36c6-317">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="c36c6-318">Tipps für die Installation der Antiviren-Software auf dem Cloud Connector-Hostcomputer</span><span class="sxs-lookup"><span data-stu-id="c36c6-318">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="c36c6-319">Wenn Sie Antivirensoftware auf dem Cloud Connector-Hostcomputer installieren müssen, müssen Sie die folgenden Ausnahmen hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="c36c6-319">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="c36c6-320">Lokales Appliance-Verzeichnis auf jedem Computer.</span><span class="sxs-lookup"><span data-stu-id="c36c6-320">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="c36c6-321">Remote Websiteverzeichnis auf jedem Computer.</span><span class="sxs-lookup"><span data-stu-id="c36c6-321">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="c36c6-322">Das lokale Websiteverzeichnis auf dem Computer hostet den Stammordner der freigegebenen Website.</span><span class="sxs-lookup"><span data-stu-id="c36c6-322">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="c36c6-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="c36c6-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="c36c6-324">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="c36c6-324">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="c36c6-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="c36c6-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="c36c6-326">Der Prozess Microsoft.Rtc.CCE.ManagementService.exe.</span><span class="sxs-lookup"><span data-stu-id="c36c6-326">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
