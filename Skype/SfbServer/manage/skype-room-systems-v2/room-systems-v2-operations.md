---
title: Skype-Chatroom-Systemen v2 Wartung und Betrieb
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Lesen Sie in diesem Thema, um Informationen zur Verwaltung von Skype Raum Systemen v2, der nächsten Generation Skype Raum Systeme zu erfahren.
ms.openlocfilehash: 29c3af2b73f9a8b1277abdc6a47afeb69cb26ef2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889322"
---
# <a name="skype-room-systems-v2-maintenance-and-operations"></a><span data-ttu-id="b4090-103">Skype-Chatroom-Systemen v2 Wartung und Betrieb</span><span class="sxs-lookup"><span data-stu-id="b4090-103">Skype Room Systems v2 maintenance and operations</span></span> 
 
<span data-ttu-id="b4090-104">Lesen Sie in diesem Thema, um Informationen zur Verwaltung von Skype Raum Systemen v2, der nächsten Generation Skype Raum Systeme zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="b4090-104">Read this topic to learn about management of Skype Room Systems v2, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="b4090-105">Skype-Chatroom-Systemen v2 ist Microsofts neueste konferenzlösung entwickelt, um Ihre Besprechungsraum in einer umfassenden, gemeinsame Skype Business wünschen umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="b4090-105">Skype Room Systems v2 is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative Skype for Business experience.</span></span> <span data-ttu-id="b4090-106">Die Benutzer finden sich dank der vertrauten Benutzeroberfläche von Skype for Business schnell zurecht, und IT-Administratoren werden die Skype-Besprechungs-App für Windows 10 aufgrund der einfachen Bereitstellung und Verwaltung zu schätzen wissen.</span><span class="sxs-lookup"><span data-stu-id="b4090-106">Users will enjoy its familiar Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="b4090-107">Skype Raum Systemen v2 dient zur Nutzung von vorhandenen Ausrüstung, wie Bereiche der LCD-Anzeige zur Erleichterung der Installation in Ihrem Besprechungsraum Skype für Unternehmen eingefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b4090-107">Skype Room Systems v2 is designed to leverage existing equipment like LCD panels for ease of installation to bring Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="b4090-108">Zusätzliche Konfiguration ist Remoteverwaltung möglich mit Microsoft Azure Monitor gemäß [Planung Skype Raum v2 systemverwaltung mit Azure Monitor](../../plan-your-deployment/clients-and-devices/azure-monitor.md), [Bereitstellen Skype Raum v2 systemverwaltung mit Azure Monitor](../../deploy/deploy-clients/azure-monitor.md), [Verwalten Skype-Chatroom-Systemen v2 Geräte mit Azure Monitor](azure-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="b4090-108">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Skype Room Systems v2 management with Azure Monitor](../../plan-your-deployment/clients-and-devices/azure-monitor.md), [Deploy Skype Room Systems v2 management with Azure Monitor](../../deploy/deploy-clients/azure-monitor.md), [Manage Skype Room Systems v2 devices with Azure Monitor](azure-monitor.md).</span></span> <span data-ttu-id="b4090-109">///Sie können auch [Manage a Skype Room Systems v2 console settings remotely with an XML configuration file](xml-config-file.md), was die Anwendung des benutzerdefinierten Anzeigedesigns beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="b4090-109">You may also [Manage a Skype Room Systems v2 console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-skype-room-systems-v2"></a><span data-ttu-id="b4090-110">Erfassen von Protokollen in Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="b4090-110">Collecting logs on Skype Room Systems v2</span></span>
<span data-ttu-id="b4090-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="b4090-111"></span></span>

<span data-ttu-id="b4090-112">Um die Protokolle gespeichert werden, müssen Sie das Protokoll Auflistung Skript aufrufen, das mit der Skype Raum Systemen v2-app verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b4090-112">To collect logs, you must invoke the log collection script that ships with the Skype Room Systems v2 app.</span></span> <span data-ttu-id="b4090-113">Starten Sie im Administratormodus eine Eingabeaufforderung mit erhöhten Rechten, und geben Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="b4090-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="b4090-114">Die Protokolle werden als ZIP-Datei in c:\rigel ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b4090-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="b4090-115">Anzeigeeinstellungen vorne im Raum</span><span class="sxs-lookup"><span data-stu-id="b4090-115">Front of Room Display Settings</span></span>
<span data-ttu-id="b4090-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="b4090-116"></span></span>

<span data-ttu-id="b4090-117">Konfigurieren Sie den Bildschirm vorne im Raum für den Modus „Erweitert“.</span><span class="sxs-lookup"><span data-stu-id="b4090-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="b4090-118">Dadurch wird die Konsole sicherstellen, dass, die Benutzeroberfläche auf, die anzeigen nicht dupliziert werden, wenn Sie die Anzeige schalten.</span><span class="sxs-lookup"><span data-stu-id="b4090-118">Doing so will ensure that the console UI is not duplicated on that display when you cycle power on the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b4090-119">Ein Consumer TV als Front Raum Anzeige Anforderungen für den Support/HDMI das Consumer Electronics Steuerelement (CEC)-Feature aktivieren, damit er automatisch an eine aktive Bildquelle aus dem Standbymodus wechseln kann.</span><span class="sxs-lookup"><span data-stu-id="b4090-119">A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode.</span></span> <span data-ttu-id="b4090-120">Dieses Feature wird auf alle TV-Geräte nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b4090-120">This feature is not supported on all TVs.</span></span> 
  
## <a name="skype-room-systems-v2-reset-factory-restore"></a><span data-ttu-id="b4090-121">Zurücksetzen von Skype Room Systems v2 (Zurücksetzung auf Werkseinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b4090-121">Skype Room Systems v2 Reset (Factory Restore)</span></span>
<span data-ttu-id="b4090-122"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="b4090-122"></span></span>

<span data-ttu-id="b4090-123">Wenn Skype Raum Systemen v2 ebenfalls nicht ausgeführt wird, möglicherweise ausführen Herstellerstandard zurücksetzen helfen.</span><span class="sxs-lookup"><span data-stu-id="b4090-123">If Skype Room Systems v2 isn't running well, performing a factory reset might help.</span></span> <span data-ttu-id="b4090-124">Dies ist möglich, in der app Einstellungen auf der Registerkarte **Wiederherstellen** unter **diesem PC zurücksetzen**, wählen Sie **Erste Schritte**, und klicken Sie dann **Alles entfernen**.</span><span class="sxs-lookup"><span data-stu-id="b4090-124">This can be done in the Settings app on the **Recovery** tab. Beneath **Reset this PC**, select **Get started**, and then **Remove everything**.</span></span> <span data-ttu-id="b4090-125">Führen Sie die verbleibenden aufforderungen, um das Gerät zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="b4090-125">Follow the remaining prompts to reset the device.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b4090-126">Es ist ein bekanntes Problem, in dem die Skype Raum Systemen v2 verwendet werden kann nicht mehr verwendet werden, wenn die Option **Meine Dateien - Apps entfernt und Einstellungen, beibehalten werden sollen, jedoch bleibt Ihre persönlichen Dateien** während des Aktivierungsvorgangs zurücksetzen ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="b4090-126">There is a known issue where the Skype Room Systems v2 can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="b4090-127">Führen Sie _nicht_ verwenden Sie diese Option.</span><span class="sxs-lookup"><span data-stu-id="b4090-127">Do _not_ use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="b4090-128">Unterstützte Remoteoptionen</span><span class="sxs-lookup"><span data-stu-id="b4090-128">Supported Remote Options</span></span>
<span data-ttu-id="b4090-129"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="b4090-129"></span></span>

<span data-ttu-id="b4090-130">In der folgenden Tabelle sind die möglichen Remotevorgänge und die Methoden zusammengefasst, die Sie für diese Vorgänge verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b4090-130">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="b4090-131">\*\*Arbeitsgruppe \*\*</span><span class="sxs-lookup"><span data-stu-id="b4090-131">**Workgroup**</span></span>|<span data-ttu-id="b4090-132">**Nicht Mitglied einer Domäne**</span><span class="sxs-lookup"><span data-stu-id="b4090-132">**Not domain joined**</span></span>|<span data-ttu-id="b4090-133">**Mitglied einer Domäne**</span><span class="sxs-lookup"><span data-stu-id="b4090-133">**Domain joined**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b4090-134">Neustart</span><span class="sxs-lookup"><span data-stu-id="b4090-134">Restart</span></span>  <br/> |<span data-ttu-id="b4090-135">Remotedesktop</span><span class="sxs-lookup"><span data-stu-id="b4090-135">Remote desktop</span></span>  <br/> <span data-ttu-id="b4090-136">Remote-Powershell</span><span class="sxs-lookup"><span data-stu-id="b4090-136">Remote Powershell</span></span>  <br/> |<span data-ttu-id="b4090-137">Remotedesktop (Weitere Konfiguration erforderlich)</span><span class="sxs-lookup"><span data-stu-id="b4090-137">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="b4090-138">Remote-Powershell (Weitere Konfiguration erforderlich)</span><span class="sxs-lookup"><span data-stu-id="b4090-138">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="b4090-139">SCCM</span><span class="sxs-lookup"><span data-stu-id="b4090-139">SCCM</span></span>  <br/> |
|<span data-ttu-id="b4090-140">Betriebssystemupdate</span><span class="sxs-lookup"><span data-stu-id="b4090-140">Update OS</span></span>  <br/> |<span data-ttu-id="b4090-141">Windows Update</span><span class="sxs-lookup"><span data-stu-id="b4090-141">Windows Update</span></span>  <br/> |<span data-ttu-id="b4090-142">Windows Update</span><span class="sxs-lookup"><span data-stu-id="b4090-142">Windows Update</span></span>  <br/> <span data-ttu-id="b4090-143">WSUS</span><span class="sxs-lookup"><span data-stu-id="b4090-143">WSUS</span></span>  <br/> |
|<span data-ttu-id="b4090-144">App-Update</span><span class="sxs-lookup"><span data-stu-id="b4090-144">App update</span></span>  <br/> |<span data-ttu-id="b4090-145">Windows Store</span><span class="sxs-lookup"><span data-stu-id="b4090-145">Windows Store</span></span>  <br/> |<span data-ttu-id="b4090-146">Windows Store</span><span class="sxs-lookup"><span data-stu-id="b4090-146">Windows Store</span></span>  <br/> <span data-ttu-id="b4090-147">SCCM</span><span class="sxs-lookup"><span data-stu-id="b4090-147">SCCM</span></span>  <br/> |
|<span data-ttu-id="b4090-148">Skype-Kontokonfiguration</span><span class="sxs-lookup"><span data-stu-id="b4090-148">Skype Account Config</span></span>  <br/> |<span data-ttu-id="b4090-149">Zurzeit nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="b4090-149">Not currently supported</span></span>  <br/> |<span data-ttu-id="b4090-150">Zurzeit nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="b4090-150">Not currently supported</span></span>  <br/> |
|<span data-ttu-id="b4090-151">Zugriff auf Protokolle</span><span class="sxs-lookup"><span data-stu-id="b4090-151">Access logs</span></span>  <br/> |<span data-ttu-id="b4090-152">Zurzeit nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="b4090-152">Not currently supported</span></span>  <br/> |<span data-ttu-id="b4090-153">Zurzeit nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="b4090-153">Not currently supported</span></span>  <br/> |
   
## <a name="configuring-group-policy-for-skype-room-systems-v2"></a><span data-ttu-id="b4090-154">Konfigurieren von Gruppenrichtlinie für Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="b4090-154">Configuring Group Policy for Skype Room Systems v2</span></span>
<span data-ttu-id="b4090-155"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="b4090-155"></span></span>

<span data-ttu-id="b4090-156">In diesem Abschnitt werden die Systemeinstellungen, von denen Skype Raum Systemen v2 abhängt, ordnungsgemäß behandelt.</span><span class="sxs-lookup"><span data-stu-id="b4090-156">This section covers system settings that Skype Room Systems v2 depends on to function properly.</span></span> <span data-ttu-id="b4090-157">Wenn v2 Skype Raum Systeme mit einer Domäne verknüpft wird, stellen Sie sicher, dass Ihre Gruppenrichtlinien die Einstellungen in der folgenden Tabelle außer Kraft setzen nicht.</span><span class="sxs-lookup"><span data-stu-id="b4090-157">When joining Skype Room Systems v2 to a domain, ensure that your group policy doesn't override the settings in the following table.</span></span>
  

|<span data-ttu-id="b4090-158">**Einstellung**</span><span class="sxs-lookup"><span data-stu-id="b4090-158">**Setting**</span></span>|<span data-ttu-id="b4090-159">**Ermöglicht**</span><span class="sxs-lookup"><span data-stu-id="b4090-159">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b4090-160">HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon automatische Anmeldung = (REG_SZ) 1</span><span class="sxs-lookup"><span data-stu-id="b4090-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span></span>  <br/> |<span data-ttu-id="b4090-161">Ermöglicht das Skype Raum Systemen v2 starten</span><span class="sxs-lookup"><span data-stu-id="b4090-161">Enables Skype Room Systems v2 to boot up</span></span>  <br/> |
|<span data-ttu-id="b4090-162">Strom-Management -\> AC, deaktivieren Sie auf Bildschirm nach 10 Minuten</span><span class="sxs-lookup"><span data-stu-id="b4090-162">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="b4090-163">Strom-Management -\> auf AC, setzen Sie nie System in den Energiesparmodus</span><span class="sxs-lookup"><span data-stu-id="b4090-163">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="b4090-164">Skype-Chatroom-Systemen v2 angefügte zeigt deaktivieren und Reaktivieren von automatisch aktiviert</span><span class="sxs-lookup"><span data-stu-id="b4090-164">Enables Skype Room Systems v2 to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="b4090-165">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="b4090-165">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="b4090-166">Oder entsprechende Möglichkeit zum Deaktivieren des Kennwortablaufs für das lokale Konto.</span><span class="sxs-lookup"><span data-stu-id="b4090-166">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="b4090-167">Wird dies nicht ausgeführt, kann bei der Anmeldung des Skype-Kontos aufgrund eines abgelaufenen Kennworts ein Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="b4090-167">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="b4090-168">Beachten Sie, dass sich dies auf alle lokalen Konten auf dem Computer auswirkt, sodass bei Nichtfestlegung dieser Einstellung auch das Administratorkonto ablaufen kann.</span><span class="sxs-lookup"><span data-stu-id="b4090-168">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="b4090-169">Ermöglicht die ständige Anmeldung des Skype-Kontos</span><span class="sxs-lookup"><span data-stu-id="b4090-169">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="b4090-170">Übertragen von Dateien mithilfe von Gruppenrichtlinien wird unter [Konfigurieren einer Dateielement](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)erläutert.</span><span class="sxs-lookup"><span data-stu-id="b4090-170">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="b4090-171">Remoteverwaltung mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4090-171">Remote Management using PowerShell</span></span>
<span data-ttu-id="b4090-172"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="b4090-172"></span></span>

<span data-ttu-id="b4090-173">Sie können die folgenden Verwaltungsvorgänge Remote mithilfe von PowerShell ausführen (siehe Tabelle unten für Skriptbeispiele):</span><span class="sxs-lookup"><span data-stu-id="b4090-173">You can perform the following management operations remotely by using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="b4090-174">Abrufen von angeschlossenen Geräten</span><span class="sxs-lookup"><span data-stu-id="b4090-174">Get attached devices</span></span>
    
- <span data-ttu-id="b4090-175">Abrufen des App-Status</span><span class="sxs-lookup"><span data-stu-id="b4090-175">Get app status</span></span>
    
- <span data-ttu-id="b4090-176">Abrufen von Systeminformationen</span><span class="sxs-lookup"><span data-stu-id="b4090-176">Get system info</span></span>
    
- <span data-ttu-id="b4090-177">Neustart des Systems</span><span class="sxs-lookup"><span data-stu-id="b4090-177">Reboot system</span></span>
    
- <span data-ttu-id="b4090-178">Abrufen von Protokollen</span><span class="sxs-lookup"><span data-stu-id="b4090-178">Retrieve logs</span></span>
    
- <span data-ttu-id="b4090-179">Übertragen von Dateien (einer Domäne gehörenden Skype Raum Systemen v2 erforderlich)</span><span class="sxs-lookup"><span data-stu-id="b4090-179">Transfer files (requires a domain-joined Skype Room Systems v2)</span></span>
    
> [!NOTE]
> <span data-ttu-id="b4090-180">Diese Funktion ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b4090-180">This functionality is off by default.</span></span> <span data-ttu-id="b4090-181">Sie müssen zum Ausführen der folgenden Vorgänge remote-PowerShell für Ihre Umgebung für das Skype Raum Systemen v2 System aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b4090-181">You need to enable remote PowerShell for your environment on the Skype Room Systems v2 system to perform the operations below.</span></span> <span data-ttu-id="b4090-182">Finden Sie in der Dokumentation auf **[Enable-psremoting sieht](https://technet.microsoft.com/library/hh849694.aspx)** für Informationen zur Verwendung von remote-PowerShell aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b4090-182">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** for information about how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="b4090-183">Sie können Remote-PowerShell beispielsweise wie folgt aktivieren:</span><span class="sxs-lookup"><span data-stu-id="b4090-183">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="b4090-184">Melden Sie sich als Administrator auf einem Gerät mit Skype Raum Systemen v2.</span><span class="sxs-lookup"><span data-stu-id="b4090-184">Sign in as Admin on a Skype Room Systems v2 device.</span></span>
    
2. <span data-ttu-id="b4090-185">Öffnen Sie eine PowerShell-Eingabeaufforderung mit erhöhten Rechten.</span><span class="sxs-lookup"><span data-stu-id="b4090-185">Open an elevated PowerShell command prompt.</span></span>
    
3. <span data-ttu-id="b4090-186">Geben Sie den folgenden Befehl ein: Enable-PSRemoting -force</span><span class="sxs-lookup"><span data-stu-id="b4090-186">Enter the following command: Enable-PSRemoting -force</span></span>
    
<span data-ttu-id="b4090-187">So führen Sie einen Verwaltungsvorgang durch:</span><span class="sxs-lookup"><span data-stu-id="b4090-187">To perform a management operation:</span></span>
  
1. <span data-ttu-id="b4090-188">Melden Sie sich an einem Computer mit den Anmeldeinformationen des Kontos, die Berechtigung zum Ausführen von PowerShell-Befehlen auf einem Gerät mit Skype Raum Systemen v2.</span><span class="sxs-lookup"><span data-stu-id="b4090-188">Sign in to a PC with account credentials that have permission to run PowerShell commands on a Skype Room Systems v2 device.</span></span>
    
2. <span data-ttu-id="b4090-189">Öffnen Sie eine reguläre PowerShell-Eingabeaufforderung auf dem PC.</span><span class="sxs-lookup"><span data-stu-id="b4090-189">Open a regular PowerShell command prompt on the PC.</span></span>
    
3. <span data-ttu-id="b4090-190">Kopieren Sie den Befehlstext aus der folgenden Tabelle, und fügen Sie ihn an der Eingabeaufforderung ein.</span><span class="sxs-lookup"><span data-stu-id="b4090-190">Copy the command text from the table below and paste it at the prompt.</span></span>
    
4. <span data-ttu-id="b4090-191">Ersetzen Sie `<Device fqdn>` Felder mit den Werten des FQDN für Ihre Umgebung geeignet.</span><span class="sxs-lookup"><span data-stu-id="b4090-191">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
    
5. <span data-ttu-id="b4090-192">Ersetzen Sie \* \<Pfad\> \* mit den Dateinamen und den lokalen Pfad der master SkypeSettings.xml-Konfigurationsdatei (oder Bild Design).</span><span class="sxs-lookup"><span data-stu-id="b4090-192">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="b4090-193">Abzurufenden angeschlossene Geräte</span><span class="sxs-lookup"><span data-stu-id="b4090-193">To Get Attached Devices</span></span>
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="b4090-194">Abrufen des App-Status</span><span class="sxs-lookup"><span data-stu-id="b4090-194">Get App Status</span></span>
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="b4090-195">Abrufen von Systeminformationen</span><span class="sxs-lookup"><span data-stu-id="b4090-195">Get System Info</span></span>
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="b4090-196">Neustart des Systems</span><span class="sxs-lookup"><span data-stu-id="b4090-196">Reboot System</span></span>
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="b4090-197">Abrufen von Protokollen</span><span class="sxs-lookup"><span data-stu-id="b4090-197">Retrieve Logs</span></span>
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="b4090-198">Drücken Sie eine XML-Konfigurationsdatei (oder Grafik Design)</span><span class="sxs-lookup"><span data-stu-id="b4090-198">Push an XML configuration file (or theme graphic)</span></span>
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="b4090-199">Softwareupdates</span><span class="sxs-lookup"><span data-stu-id="b4090-199">Software updates</span></span>
<span data-ttu-id="b4090-200"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="b4090-200"></span></span>

<span data-ttu-id="b4090-201">Standardmäßig versucht Skype Raum Systemen v2 zum Verbinden mit den Windows Store zum Abrufen der neuesten Version von Skype Raum v2 Systemsoftware, damit das Gerät regulären Internetzugriff erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b4090-201">By default, Skype Room Systems v2 attempts to connect to the Windows Store to get the latest version of Skype Room Systems v2 software, so the device will require regular internet access.</span></span> <span data-ttu-id="b4090-202">Kontaktaufnahme mit Microsoft Support-Probleme, werden Sie sicher, dass das Skype Raum Systemen v2-Gerät mit der neuesten Version der app geladen wird.</span><span class="sxs-lookup"><span data-stu-id="b4090-202">Before contacting Microsoft with support issues, be sure the Skype Room Systems v2 device is loaded with the latest version of the app.</span></span>
  
<span data-ttu-id="b4090-203">In der Standardeinstellung Skype Raum Systeme v2 stellt eine Verbindung mit Windows Update Betriebssystem abgerufen und USB-Peripheriegeräte Firmwareupdates und installiert diese außerhalb der Geschäftszeiten konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="b4090-203">By default, Skype Room Systems v2 connects to Windows Update to retrieve operating system and USB peripheral device firmware updates, and installs them outside of configured business hours.</span></span> <span data-ttu-id="b4090-204">Sie können Geschäftszeiten konfigurieren, indem Sie sich beim Administratorkonto anmelden und die Einstellungen-App ausführen.</span><span class="sxs-lookup"><span data-stu-id="b4090-204">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="b4090-205">Wenn Sie Updates manuell verwalten möchten, und nicht im normale Verfahren für eine [Microsoft Store for Business](https://businessstore.microsoft.com/store) zu [verteilen offline-apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)haben, können Sie die entsprechende APPX Datei und Abhängigkeiten in [Deployment Kit](https://go.microsoft.com/fwlink/?linkid=851168) (aus abrufen. die Anweisungen zum [Konfigurieren einer Skype Raum Systemen v2 Konsole](../../deploy/deploy-clients/console.md)) mit SCCM verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b4090-205">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/store) to [Distribute offline apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Skype Room Systems v2 console](../../deploy/deploy-clients/console.md)) that can be used with SCCM.</span></span> <span data-ttu-id="b4090-206">Die Deployment Kit-Version Positionen davor befindet hinter der Store-Version, damit es immer den neuesten Build möglicherweise nicht übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="b4090-206">The deployment kit release lags behind the store release, so it might not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="b4090-207">Aktualisieren von Powershell</span><span class="sxs-lookup"><span data-stu-id="b4090-207">To update using Powershell</span></span>

1. <span data-ttu-id="b4090-208">Extrahieren Sie das Paket aus der Installation die [MSI-Datei](https://go.microsoft.com/fwlink/?linkid=851168) zu einer Freigabe das Gerät, die zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="b4090-208">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a share the device can access.</span></span>
    
2. <span data-ttu-id="b4090-209">Führen Sie das folgende Skript für die Skype Raum Systemen v2-Geräte ändern \<freigeben\> freigeben als Antwort auf das Gerät:</span><span class="sxs-lookup"><span data-stu-id="b4090-209">Run the following script targeting the Skype Room Systems v2 devices, changing \<share\> to the device share as appropriate:</span></span>
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="b4090-210">Administratormodus und Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="b4090-210">Admin mode and device management</span></span>
<span data-ttu-id="b4090-211"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="b4090-211"></span></span>

<span data-ttu-id="b4090-212">Einige Managementfunktionen, wie die manuelle Installation eines privaten Zertifizierungsstellenzertifikats erfordern das Vorhandensein des Surface Pro Geräts im Admin-Modus.</span><span class="sxs-lookup"><span data-stu-id="b4090-212">Some management functions, like manually installing a private CA certificate, require placing the Surface Pro device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-is-running"></a><span data-ttu-id="b4090-213">Wechsel in Administratormodus und zurück, wenn die Skype Raum Systemen v2 app ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="b4090-213">Switching to Admin Mode and back when the Skype Room Systems v2 app is running</span></span>

1. <span data-ttu-id="b4090-214">Alle laufenden Anrufe Auflegen, und klicken Sie auf der Startseite zurück.</span><span class="sxs-lookup"><span data-stu-id="b4090-214">Hang up any ongoing calls, and return to the home screen.</span></span>
    
2. <span data-ttu-id="b4090-215">Wählen Sie das Zahnradsymbol und rufen Sie das Menü (Optionen sind **Einstellungen**, **Eingabehilfen**und **Gerät neu starten** ).</span><span class="sxs-lookup"><span data-stu-id="b4090-215">Select the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
    
3. <span data-ttu-id="b4090-216">Wählen Sie **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="b4090-216">Select **Settings**.</span></span>
    
4. <span data-ttu-id="b4090-217">Geben Sie das Administratorkennwort ein.</span><span class="sxs-lookup"><span data-stu-id="b4090-217">Enter the Administrator Password.</span></span> <span data-ttu-id="b4090-218">Der Setupbildschirm wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b4090-218">The Setup screen will appear.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b4090-219">Wenn das Gerät in die Domäne eingebundener nicht ist, wird das lokale Administratorkonto (Benutzername "Admin") in der Standardeinstellung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b4090-219">If the device isn't domain-joined, the local administrative account (username "Admin") will be used by default.</span></span> <span data-ttu-id="b4090-220">Das Standard-Kennwort für dieses Konto ist 'Sfb', aber es wird empfohlen, dass Ihre Organisation dies für aus Sicherheitsgründen so bald wie möglich zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b4090-220">The default password for this account is 'sfb' but it is recommended that your organization change this for security reasons as soon as possible.</span></span> <span data-ttu-id="b4090-221">Wenn der Computer Mitglied einer Domäne ist, können Sie sich mit einem Domänenkonto entsprechend berechtigten anmelden.</span><span class="sxs-lookup"><span data-stu-id="b4090-221">If the machine is domain-joined, you can sign in with an appropriately privileged domain account.</span></span> 
  
5. <span data-ttu-id="b4090-222">Wählen Sie **Windows-Einstellungen** in der linken Spalte aus.</span><span class="sxs-lookup"><span data-stu-id="b4090-222">Select **Windows Settings** in the left column.</span></span>
    
6. <span data-ttu-id="b4090-223">Wählen Sie **Zu Administratoranmeldung wechseln** aus.</span><span class="sxs-lookup"><span data-stu-id="b4090-223">Choose **Go to Admin Sign-in**.</span></span>
    
7. <span data-ttu-id="b4090-224">Geben Sie das Administratorkennwort ein.</span><span class="sxs-lookup"><span data-stu-id="b4090-224">Enter the Administrator Password.</span></span> <span data-ttu-id="b4090-225">Daraufhin wird die App ordnungsgemäß abgemeldet, und Sie gelangen zum Windows-Anmeldebildschirm.</span><span class="sxs-lookup"><span data-stu-id="b4090-225">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
    
8. <span data-ttu-id="b4090-226">Melden Sie sich mit Ihren Administratoranmeldeinformationen beim Desktop an.</span><span class="sxs-lookup"><span data-stu-id="b4090-226">Log in to the desktop with your administrative credentials.</span></span> <span data-ttu-id="b4090-227">Sie müssen die erforderlichen Berechtigungen zum Verwalten des Geräts.</span><span class="sxs-lookup"><span data-stu-id="b4090-227">You'll have the necessary privileges to manage the device.</span></span>
    
9. <span data-ttu-id="b4090-228">Führen Sie die notwendigen Administratoraufgaben aus.</span><span class="sxs-lookup"><span data-stu-id="b4090-228">Perform the necessary administrative tasks.</span></span>
    
10. <span data-ttu-id="b4090-229">Melden Sie sich bei Ihrem Administratorkonto ab.</span><span class="sxs-lookup"><span data-stu-id="b4090-229">Sign out from the Admin account.</span></span>
    
11. <span data-ttu-id="b4090-230">Zur Skype Raum Systemen v2 durch Auswählen des Benutzer Konto-Symbols auf der linken Seite des Bildschirms und anschließend **Skype**zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="b4090-230">Return to Skype Room Systems v2 by selecting the user account icon on the far left side of the screen and then selecting **Skype**.</span></span>
    
    <span data-ttu-id="b4090-231">Wenn der Benutzer **Skype** nicht aufgeführt ist, möglicherweise müssen Sie wählen Sie **Benutzer** aus, und geben **. \skype** als den Benutzernamen und das anmelden.</span><span class="sxs-lookup"><span data-stu-id="b4090-231">If the **Skype** user is not listed, you might have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
<span data-ttu-id="b4090-232">Die Konsole ist nun wieder in den normalen Betrieb-Modus. Das folgende Verfahren benötigen Sie eine Tastatur auf das Gerät anfügen, falls noch nicht angefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="b4090-232">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-crashes"></a><span data-ttu-id="b4090-233">Wechsel in Administratormodus und zurück, wenn die Skype Raum Systemen v2 app stürzt ab</span><span class="sxs-lookup"><span data-stu-id="b4090-233">Switching to Admin Mode and back when the Skype Room Systems v2 app crashes</span></span>

1. <span data-ttu-id="b4090-234">Drücken Sie fünf Mal schnell hintereinander die WINDOWS-TASTE.</span><span class="sxs-lookup"><span data-stu-id="b4090-234">Press the Windows key five times in rapid succession.</span></span> <span data-ttu-id="b4090-235">Daraufhin gelangen Sie zum Windows-Anmeldebildschirm.</span><span class="sxs-lookup"><span data-stu-id="b4090-235">This will bring you to the Windows logon screen.</span></span> 
    
2. <span data-ttu-id="b4090-236">Melden Sie sich mit Ihren Administratoranmeldeinformationen beim Desktop an.</span><span class="sxs-lookup"><span data-stu-id="b4090-236">Log in to the desktop with your administrative credentials.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b4090-237">Diese Methode nicht melden Sie sich den Skype-Benutzer oder die app ordnungsgemäß beendet, aber verwenden Sie es, wenn die app wurde nicht mehr reagiert und die andere Methode war nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b4090-237">This method doesn't log the Skype user off or gracefully terminate the app, but you'd use it if the app wasn't responding and the other method wasn't available.</span></span> 
  
3. <span data-ttu-id="b4090-238">Führen Sie die notwendigen Administratoraufgaben aus.</span><span class="sxs-lookup"><span data-stu-id="b4090-238">Perform the necessary administrative tasks.</span></span>
    
4. <span data-ttu-id="b4090-239">Starten Sie den Computer, wenn Sie fertig sind.</span><span class="sxs-lookup"><span data-stu-id="b4090-239">Restart the machine when you're finished.</span></span>
    
   <span data-ttu-id="b4090-240">Die Konsole wird neu gestartet, in den normalen Betrieb-Modus, die Skype Raum Systemen v2 app ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b4090-240">The console restarts into its normal operation mode, running the Skype Room Systems v2 app.</span></span> <span data-ttu-id="b4090-241">Sie können die Tastatur entfernen, wenn es angefügt wurde, damit Sie dieses Verfahren ausführen können.</span><span class="sxs-lookup"><span data-stu-id="b4090-241">You can remove the keyboard, if it was attached to allow you to perform this procedure.</span></span>
   ## <a name="troubleshooting-tips"></a><span data-ttu-id="b4090-242">Tipps zur Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="b4090-242">Troubleshooting tips</span></span>
   <span data-ttu-id="b4090-243"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="b4090-243"></span></span>

- <span data-ttu-id="b4090-244">Besprechungsanfragen möglicherweise nicht angezeigt, wenn über Domänengrenzen hinweg (beispielsweise zwischen zwei Unternehmen) gesendet.</span><span class="sxs-lookup"><span data-stu-id="b4090-244">Meeting invitations might not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="b4090-245">In solchen Fällen sollten die IT-Administratoren, ob externe Benutzer zum Planen einer Besprechung zugelassen entscheiden.</span><span class="sxs-lookup"><span data-stu-id="b4090-245">In such cases, IT admins should decide whether to allow external users to schedule a meeting.</span></span>
    
- <span data-ttu-id="b4090-246">Exchange AutoDiscover leitet über Exchange 2010 unterstützt keine Skype Raum Systemen v2.</span><span class="sxs-lookup"><span data-stu-id="b4090-246">Skype Room Systems v2 doesn't support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
    
- <span data-ttu-id="b4090-247">Im Allgemeinen ist es ratsam für IT-Administratoren, die alle audioendpunkte deaktivieren, die er nicht verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="b4090-247">In general, it's a good practice for IT admins to disable any audio endpoints they don't intend to use.</span></span>
    
- <span data-ttu-id="b4090-248">Falls ein Spiegelbild in der Raumvorschau angezeigt wird, kann der IT-Administrator dies korrigieren, indem die Stromversorgung der Kamera angestellt wird oder die Bildausrichtung mit der Fernsteuerung der Kamera gekippt wird.</span><span class="sxs-lookup"><span data-stu-id="b4090-248">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
    
- <span data-ttu-id="b4090-249">Es ist bekannt, dass der Zugang zum Konsolentouchscreen verloren gehen kann.</span><span class="sxs-lookup"><span data-stu-id="b4090-249">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="b4090-250">In solchen Fällen wird durch einen Neustart des Systems der Skype Raum Systemen v2 manchmal das Problem behoben.</span><span class="sxs-lookup"><span data-stu-id="b4090-250">In such cases, the issue is sometimes resolved by restarting the Skype Room Systems v2 system.</span></span>
    
- <span data-ttu-id="b4090-251">Beim Verbinden eines PCs mit der Konsole über verkabelte Erfassung kann ein Verlust der lokalen Audiodaten auftreten.</span><span class="sxs-lookup"><span data-stu-id="b4090-251">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="b4090-252">Das Problem mit der Wiedergabe der lokalen Audiodaten kann in diesem Fall durch einen Neustart des PCs gelöst werden.</span><span class="sxs-lookup"><span data-stu-id="b4090-252">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    
