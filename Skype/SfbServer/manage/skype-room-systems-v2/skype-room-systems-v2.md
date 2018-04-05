---
title: Verwalten von Skype Room Systems v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
description: Lesen Sie in diesem Thema, um Informationen zur Verwaltung von Skype Raum Systemen v2, der nächsten Generation Skype Raum Systeme zu erfahren.
ms.openlocfilehash: 562dbeea19fb732caf9348e2bfd632da3579e71a
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2018
---
# <a name="manage-skype-room-systems-v2"></a><span data-ttu-id="ad9b4-103">Verwalten von Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="ad9b4-103">Manage Skype Room Systems v2</span></span>
 
<span data-ttu-id="ad9b4-104">Lesen Sie in diesem Thema, um Informationen zur Verwaltung von Skype Raum Systemen v2, der nächsten Generation Skype Raum Systeme zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-104">Read this topic to learn about management of Skype Room Systems v2, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="ad9b4-105">Skype-Chatroom-Systemen v2 ist Microsofts neueste konferenzlösung entwickelt, um Ihre Besprechungsraum in einer umfassenden, gemeinsame Skype Business wünschen umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-105">Skype Room Systems v2 is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative Skype for Business experience.</span></span> <span data-ttu-id="ad9b4-106">Die Benutzer finden sich dank der vertrauten Benutzeroberfläche von Skype for Business schnell zurecht, und IT-Administratoren werden die Skype-Besprechungs-App für Windows 10 aufgrund der einfachen Bereitstellung und Verwaltung zu schätzen wissen.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-106">Users will enjoy its familiar Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="ad9b4-107">Skype Raum Systemen v2 dient zur Nutzung von vorhandenen Ausrüstung, wie Bereiche der LCD-Anzeige zur Erleichterung der Installation in Ihrem Besprechungsraum Skype für Unternehmen eingefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-107">Skype Room Systems v2 is designed to leverage existing equipment like LCD panels for ease of installation to bring Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="ad9b4-108">Durch zusätzliche Konfiguration kann die Remoteverwaltung Microsoft Operations Management Suite (OMS) verwenden, wie beschrieben in [Planen Skype Raum v2 systemverwaltung mit OMS](../../plan-your-deployment/clients-and-devices/oms-management.md) [Bereitstellen Skype Raum v2 systemverwaltung mit OMS](../../deploy/deploy-clients/with-oms.md)und [Verwalten Skype-Chatroom-Systemen v2 Geräte mit OMS](oms.md).</span><span class="sxs-lookup"><span data-stu-id="ad9b4-108">With additional configuration, remote management is possible using Microsoft Operations Management Suite (OMS) as described in [Plan Skype Room Systems v2 management with OMS](../../plan-your-deployment/clients-and-devices/oms-management.md), [Deploy Skype Room Systems v2 management with OMS](../../deploy/deploy-clients/with-oms.md), and [Manage Skype Room Systems v2 devices with OMS](oms.md).</span></span> <span data-ttu-id="ad9b4-109">Sie können auch [Verwalten einer Skype Raum Systemen v2 Konsolenstamm Remote mit einer XML-Konfigurationsdatei](xml-config-file.md), einschließlich eines Designs benutzerdefinierte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-109">You may also [Manage a Skype Room Systems v2 console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-skype-room-systems-v2"></a><span data-ttu-id="ad9b4-110">Erfassen von Protokollen in Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="ad9b4-110">Collecting logs on Skype Room Systems v2</span></span>
<span data-ttu-id="ad9b4-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="ad9b4-111"></span></span>

<span data-ttu-id="ad9b4-112">Um die Protokolle gespeichert werden, müssen Sie das Protokoll Auflistung Skript aufrufen, das mit der Skype Raum Systemen v2-app verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-112">To collect logs, you must invoke the log collection script that ships with the Skype Room Systems v2 app.</span></span> <span data-ttu-id="ad9b4-113">Starten Sie im Administratormodus eine Eingabeaufforderung mit erhöhten Rechten, und geben Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="ad9b4-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="ad9b4-114">Die Protokolle werden als ZIP-Datei in c:\rigel ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="ad9b4-115">Anzeigeeinstellungen vorne im Raum</span><span class="sxs-lookup"><span data-stu-id="ad9b4-115">Front of Room Display Settings</span></span>
<span data-ttu-id="ad9b4-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="ad9b4-116"></span></span>

<span data-ttu-id="ad9b4-117">Konfigurieren Sie den Bildschirm vorne im Raum für den Modus „Erweitert“.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="ad9b4-118">Dadurch wird sichergestellt, dass die Konsolen-Benutzeroberfläche auf diesem Bildschirm nicht dupliziert wird, wenn er mit Strom versorgt wird.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-118">Doing so will ensure that the console UI is not duplicated on that display when power cycling the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ad9b4-119">Ein Consumer TV als Front Raum Anzeige Anforderungen für den Support/HDMI das Consumer Electronics Steuerelement (CEC)-Feature aktivieren, damit er automatisch an eine aktive Bildquelle aus dem Standbymodus wechseln kann.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-119">A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode.</span></span> <span data-ttu-id="ad9b4-120">Dieses Feature wird auf alle TV-Geräte nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-120">This feature is not supported on all TVs.</span></span> 
  
## <a name="skype-room-systems-v2-reset-factory-restore"></a><span data-ttu-id="ad9b4-121">Zurücksetzen von Skype Room Systems v2 (Zurücksetzung auf Werkseinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ad9b4-121">Skype Room Systems v2 Reset (Factory Restore)</span></span>
<span data-ttu-id="ad9b4-122"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="ad9b4-122"></span></span>

<span data-ttu-id="ad9b4-123">Wenn Skype Raum Systemen v2 ebenfalls nicht ausgeführt wird, kann ein Herstellerstandard ausführen hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-123">If Skype Room Systems v2 isn't running well, performing a factory reset may help.</span></span> <span data-ttu-id="ad9b4-124">Dies kann in der app Einstellungen aus der Registerkarte "Wiederherstellung" unter der Überschrift "Dieser PC zurücksetzen", wählen Sie "Einstieg" gefolgt von "Alles entfernen".</span><span class="sxs-lookup"><span data-stu-id="ad9b4-124">This can be done in the Settings app from the "Recovery" tab. Beneath the "Reset this PC" header, select "Get started" followed by "Remove everything."</span></span> <span data-ttu-id="ad9b4-125">Gehen Sie entsprechend den Eingabeaufforderungen vor, um das Gerät zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-125">Follow the remaining prompts as desired to reset the device.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ad9b4-126">Es ist ein bekanntes Problem, in dem die Skype Raum Systemen v2 verwendet werden kann nicht mehr verwendet werden, wenn die Option "Meine Dateien behalten - Apps und -Einstellungen entfernt, jedoch bleibt Ihre persönlichen Dateien" während des Aktivierungsvorgangs zurücksetzen ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-126">There is a known issue where the Skype Room Systems v2 can become unusable if the "Keep my files - Removes Apps and settings, but keeps your personal files" option is selected during the Windows Reset process.</span></span> <span data-ttu-id="ad9b4-127">Verwenden Sie **nicht** diese Option.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-127">**Do not** use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="ad9b4-128">Unterstützte Remoteoptionen</span><span class="sxs-lookup"><span data-stu-id="ad9b4-128">Supported Remote Options</span></span>
<span data-ttu-id="ad9b4-129"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="ad9b4-129"></span></span>

<span data-ttu-id="ad9b4-130">In der folgenden Tabelle sind die möglichen Remotevorgänge und die Methoden zusammengefasst, die Sie für diese Vorgänge verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-130">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="ad9b4-131">**Arbeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="ad9b4-131">**Workgroup**</span></span>|<span data-ttu-id="ad9b4-132">**Nicht Domäne beitreten**</span><span class="sxs-lookup"><span data-stu-id="ad9b4-132">**Not domain joined**</span></span>|<span data-ttu-id="ad9b4-133">**Domäne beitreten**</span><span class="sxs-lookup"><span data-stu-id="ad9b4-133">**Domain joined**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ad9b4-134">Neustart</span><span class="sxs-lookup"><span data-stu-id="ad9b4-134">Restart</span></span>  <br/> |<span data-ttu-id="ad9b4-135">Remotedesktop</span><span class="sxs-lookup"><span data-stu-id="ad9b4-135">Remote desktop</span></span>  <br/> <span data-ttu-id="ad9b4-136">Remote-Powershell</span><span class="sxs-lookup"><span data-stu-id="ad9b4-136">Remote Powershell</span></span>  <br/> |<span data-ttu-id="ad9b4-137">Remotedesktop (Weitere Konfiguration erforderlich)</span><span class="sxs-lookup"><span data-stu-id="ad9b4-137">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="ad9b4-138">Remote-Powershell (Weitere Konfiguration erforderlich)</span><span class="sxs-lookup"><span data-stu-id="ad9b4-138">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="ad9b4-139">SCCM</span><span class="sxs-lookup"><span data-stu-id="ad9b4-139">SCCM</span></span>  <br/> |
|<span data-ttu-id="ad9b4-140">Betriebssystemupdate</span><span class="sxs-lookup"><span data-stu-id="ad9b4-140">Update OS</span></span>  <br/> |<span data-ttu-id="ad9b4-141">Windows Update</span><span class="sxs-lookup"><span data-stu-id="ad9b4-141">Windows Update</span></span>  <br/> |<span data-ttu-id="ad9b4-142">Windows Update</span><span class="sxs-lookup"><span data-stu-id="ad9b4-142">Windows Update</span></span>  <br/> <span data-ttu-id="ad9b4-143">WSUS</span><span class="sxs-lookup"><span data-stu-id="ad9b4-143">WSUS</span></span>  <br/> |
|<span data-ttu-id="ad9b4-144">App-Update</span><span class="sxs-lookup"><span data-stu-id="ad9b4-144">App update</span></span>  <br/> |<span data-ttu-id="ad9b4-145">Windows Store</span><span class="sxs-lookup"><span data-stu-id="ad9b4-145">Windows Store</span></span>  <br/> |<span data-ttu-id="ad9b4-146">Windows Store</span><span class="sxs-lookup"><span data-stu-id="ad9b4-146">Windows Store</span></span>  <br/> <span data-ttu-id="ad9b4-147">SCCM</span><span class="sxs-lookup"><span data-stu-id="ad9b4-147">SCCM</span></span>  <br/> |
|<span data-ttu-id="ad9b4-148">Skype-Kontokonfiguration</span><span class="sxs-lookup"><span data-stu-id="ad9b4-148">Skype Account Config</span></span>  <br/> |<span data-ttu-id="ad9b4-149">Zurzeit nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="ad9b4-149">Not currently supported</span></span>  <br/> |<span data-ttu-id="ad9b4-150">Zurzeit nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="ad9b4-150">Not currently supported</span></span>  <br/> |
|<span data-ttu-id="ad9b4-151">Zugriff auf Protokolle</span><span class="sxs-lookup"><span data-stu-id="ad9b4-151">Access logs</span></span>  <br/> |<span data-ttu-id="ad9b4-152">Zurzeit nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="ad9b4-152">Not currently supported</span></span>  <br/> |<span data-ttu-id="ad9b4-153">Zurzeit nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="ad9b4-153">Not currently supported</span></span>  <br/> |
   
## <a name="configuring-group-policy-for-skype-room-systems-v2"></a><span data-ttu-id="ad9b4-154">Konfigurieren von Gruppenrichtlinie für Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="ad9b4-154">Configuring Group Policy for Skype Room Systems v2</span></span>
<span data-ttu-id="ad9b4-155"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="ad9b4-155"></span></span>

<span data-ttu-id="ad9b4-156">In diesem Abschnitt werden die Systemeinstellungen, von denen Skype Raum Systemen v2 abhängt, ordnungsgemäß behandelt.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-156">This section covers system settings that Skype Room Systems v2 depends on to function properly.</span></span> <span data-ttu-id="ad9b4-157">Wenn v2 Skype Raum Systeme mit einer Domäne verknüpft wird, stellen Sie sicher, dass Ihre Gruppenrichtlinien die folgenden Einstellungen nicht überschrieben wird:</span><span class="sxs-lookup"><span data-stu-id="ad9b4-157">When joining Skype Room Systems v2 to a domain, please ensure that your group policy does not override the following settings:</span></span>
  

|<span data-ttu-id="ad9b4-158">**Einstellung**</span><span class="sxs-lookup"><span data-stu-id="ad9b4-158">**Setting**</span></span>|<span data-ttu-id="ad9b4-159">**Ermöglicht**</span><span class="sxs-lookup"><span data-stu-id="ad9b4-159">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ad9b4-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AdminAutoLogon = (dword) 1</span><span class="sxs-lookup"><span data-stu-id="ad9b4-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AdminAutoLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="ad9b4-161">Ermöglicht das Skype Raum Systemen v2 starten</span><span class="sxs-lookup"><span data-stu-id="ad9b4-161">Enables Skype Room Systems v2 to boot up</span></span>  <br/> |
|<span data-ttu-id="ad9b4-162">Strom-Management -\> AC, deaktivieren Sie auf Bildschirm nach 10 Minuten</span><span class="sxs-lookup"><span data-stu-id="ad9b4-162">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="ad9b4-163">Strom-Management -\> auf AC, setzen Sie nie System in den Energiesparmodus</span><span class="sxs-lookup"><span data-stu-id="ad9b4-163">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="ad9b4-164">Skype-Chatroom-Systemen v2 angefügte zeigt deaktivieren und Reaktivieren von automatisch aktiviert</span><span class="sxs-lookup"><span data-stu-id="ad9b4-164">Enables Skype Room Systems v2 to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="ad9b4-165">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="ad9b4-165">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="ad9b4-166">Oder entsprechende Möglichkeit zum Deaktivieren des Kennwortablaufs für das lokale Konto.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-166">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="ad9b4-167">Wird dies nicht ausgeführt, kann bei der Anmeldung des Skype-Kontos aufgrund eines abgelaufenen Kennworts ein Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-167">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="ad9b4-168">Beachten Sie, dass sich dies auf alle lokalen Konten auf dem Computer auswirkt, sodass bei Nichtfestlegung dieser Einstellung auch das Administratorkonto ablaufen kann.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-168">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="ad9b4-169">Ermöglicht die ständige Anmeldung des Skype-Kontos</span><span class="sxs-lookup"><span data-stu-id="ad9b4-169">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="ad9b4-170">Übertragen von Dateien mithilfe von Gruppenrichtlinien wird unter [Konfigurieren einer Dateielement](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)erläutert.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-170">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="ad9b4-171">Remoteverwaltung mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad9b4-171">Remote Management using PowerShell</span></span>
<span data-ttu-id="ad9b4-172"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="ad9b4-172"></span></span>

<span data-ttu-id="ad9b4-173">Die folgenden Verwaltungsvorgänge können remote mit PowerShell ausgeführt werden (Skriptbeispiele finden Sie in der Tabelle unten):</span><span class="sxs-lookup"><span data-stu-id="ad9b4-173">You can perform the following management operations remotely using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="ad9b4-174">Abrufen von angeschlossenen Geräten</span><span class="sxs-lookup"><span data-stu-id="ad9b4-174">Get attached devices</span></span>
    
- <span data-ttu-id="ad9b4-175">Abrufen des App-Status</span><span class="sxs-lookup"><span data-stu-id="ad9b4-175">Get app status</span></span>
    
- <span data-ttu-id="ad9b4-176">Abrufen von Systeminformationen</span><span class="sxs-lookup"><span data-stu-id="ad9b4-176">Get system info</span></span>
    
- <span data-ttu-id="ad9b4-177">Neustart des Systems</span><span class="sxs-lookup"><span data-stu-id="ad9b4-177">Reboot system</span></span>
    
- <span data-ttu-id="ad9b4-178">Abrufen von Protokollen</span><span class="sxs-lookup"><span data-stu-id="ad9b4-178">Retrieve logs</span></span>
    
- <span data-ttu-id="ad9b4-179">Übertragen von Dateien (erfordert eine in die Domäne eingebundener Skype Raum Systemen v2)</span><span class="sxs-lookup"><span data-stu-id="ad9b4-179">Transfer files (requires a domain joined Skype Room Systems v2)</span></span>
    
> [!NOTE]
> <span data-ttu-id="ad9b4-180">Diese Funktion ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-180">This functionality is off by default.</span></span> <span data-ttu-id="ad9b4-181">Sie müssen zum Ausführen der folgenden Vorgänge remote-PowerShell für Ihre Umgebung für das Skype Raum Systemen v2 System aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-181">You need to enable remote PowerShell for your environment on the Skype Room Systems v2 system to perform the operations below.</span></span> <span data-ttu-id="ad9b4-182">Finden Sie in der Dokumentation auf **[Enable-psremoting sieht](https://technet.microsoft.com/en-us/library/hh849694.aspx)** für Informationen zum remote-PowerShell aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-182">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/en-us/library/hh849694.aspx)** for information on how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="ad9b4-183">Sie können Remote-PowerShell beispielsweise wie folgt aktivieren:</span><span class="sxs-lookup"><span data-stu-id="ad9b4-183">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="ad9b4-184">Melden Sie sich als Administrator auf einem Gerät mit Skype Raum Systemen v2.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-184">Sign in as Admin on a Skype Room Systems v2 device.</span></span>
    
2. <span data-ttu-id="ad9b4-185">Starten Sie eine PowerShell-Eingabeaufforderung mit erhöhten Rechten.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-185">Launch an elevated PowerShell command prompt.</span></span>
    
3. <span data-ttu-id="ad9b4-186">Geben Sie den folgenden Befehl ein: Enable-psremoting sieht - erzwingen</span><span class="sxs-lookup"><span data-stu-id="ad9b4-186">Enter the following command: Enable-PSRemoting -force</span></span>
    
<span data-ttu-id="ad9b4-187">So führen Sie einen Verwaltungsvorgang durch:</span><span class="sxs-lookup"><span data-stu-id="ad9b4-187">To perform a management operation:</span></span>
  
1. <span data-ttu-id="ad9b4-188">Melden Sie sich bei einem PC mit den Anmeldeinformationen des Kontos, die Berechtigung zum Ausführen von PowerShell-Befehlen auf einem Gerät mit Skype Raum Systemen v2.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-188">Sign into a PC with account credentials that have permission to run PowerShell commands on a Skype Room Systems v2 device.</span></span>
    
2. <span data-ttu-id="ad9b4-189">Starten Sie eine reguläre PowerShell-Eingabeaufforderung auf dem PC.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-189">Launch a regular PowerShell command prompt on your PC.</span></span>
    
3. <span data-ttu-id="ad9b4-190">Kopieren Sie den Befehlstext aus der Tabelle unten, und fügen Sie ihn an der Eingabeaufforderung ein.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-190">Copy the command text from the table below and paste it into the prompt.</span></span>
    
4. <span data-ttu-id="ad9b4-191">Ersetzen Sie `<Device fqdn>` Felder mit den Werten des FQDN für Ihre Umgebung geeignet.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-191">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
    
5. <span data-ttu-id="ad9b4-192">Ersetzen Sie * \<Pfad\> * mit den Dateinamen und den lokalen Pfad der master SkypeSettings.xml-Konfigurationsdatei (oder Bild Design).</span><span class="sxs-lookup"><span data-stu-id="ad9b4-192">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="ad9b4-193">Abzurufenden angeschlossene Geräte</span><span class="sxs-lookup"><span data-stu-id="ad9b4-193">To Get Attached Devices</span></span>
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="ad9b4-194">Abrufen des App-Status</span><span class="sxs-lookup"><span data-stu-id="ad9b4-194">Get App Status</span></span>
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="ad9b4-195">Abrufen von Systeminformationen</span><span class="sxs-lookup"><span data-stu-id="ad9b4-195">Get System Info</span></span>
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="ad9b4-196">Neustart des Systems</span><span class="sxs-lookup"><span data-stu-id="ad9b4-196">Reboot System</span></span>
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="ad9b4-197">Abrufen von Protokollen</span><span class="sxs-lookup"><span data-stu-id="ad9b4-197">Retrieve Logs</span></span>
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="ad9b4-198">(Klicken Sie auf eine XML-Konfigurationsdatei oder auf eine Designgrafik)</span><span class="sxs-lookup"><span data-stu-id="ad9b4-198">Push an XML configuration file or theme graphic)</span></span>
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="ad9b4-199">Softwareupdates</span><span class="sxs-lookup"><span data-stu-id="ad9b4-199">Software updates</span></span>
<span data-ttu-id="ad9b4-200"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="ad9b4-200"></span></span>

<span data-ttu-id="ad9b4-201">Skype Raum Systemen v2 versucht, eine Verbindung herzustellen, an den Windows Store zum Abrufen der neuesten Version von Skype Raum v2 Systemsoftware, damit das Gerät regulären Internetzugriff erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-201">By default, Skype Room Systems v2 will attempt to connect to the Windows Store to get the latest version of Skype Room Systems v2 software, so the device will require regular internet access.</span></span> <span data-ttu-id="ad9b4-202">Stellen Sie sicher, dass das Skype Raum Systemen v2-Gerät mit der neuesten Version der app, geladen wird, bevor Sie sich an Microsoft Support-Probleme.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-202">Be sure the Skype Room Systems v2 device is loaded with the latest version of the app, before contacting Microsoft with support issues.</span></span>
  
<span data-ttu-id="ad9b4-203">Standardmäßig wird Skype Raum Systemen v2 Herstellen einer Verbindung mit Windows Update abrufen OS als auch für USB-Peripheriegeräte Firmware Updates und außerhalb der Geschäftszeiten konfigurierten installieren.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-203">By default, Skype Room Systems v2 will connect to Windows Update to retrieve OS as well as USB peripheral firmware updates and install them outside of configured business hours.</span></span> <span data-ttu-id="ad9b4-204">Sie können Geschäftszeiten konfigurieren, indem Sie sich beim Administratorkonto anmelden und die Einstellungen-App ausführen.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-204">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="ad9b4-205">Wenn Sie Updates manuell verwalten möchten, und nicht im normale Verfahren für eine [Microsoft Store for Business](https://businessstore.microsoft.com/en-us/store) zu [verteilen offline-apps](https://docs.microsoft.com/en-us/microsoft-store/distribute-offline-apps)haben, können Sie die entsprechende APPX Datei und Abhängigkeiten in [Deployment Kit](https://go.microsoft.com/fwlink/?linkid=851168) (aus abrufen. die Anweisungen zum [Konfigurieren einer Skype Raum Systemen v2 Konsole](../../deploy/deploy-clients/console.md)) mit SCCM verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-205">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/en-us/store) to [Distribute offline apps](https://docs.microsoft.com/en-us/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Skype Room Systems v2 console](../../deploy/deploy-clients/console.md)) that can be used with SCCM.</span></span> <span data-ttu-id="ad9b4-206">Die Deployment Kit-Version Positionen davor befindet hinter der Store-Version, damit es nicht immer den neuesten Build überein kann.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-206">The deployment kit release lags behind the store release, so it may not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="ad9b4-207">Aktualisieren von Powershell</span><span class="sxs-lookup"><span data-stu-id="ad9b4-207">To update using Powershell</span></span>

1. <span data-ttu-id="ad9b4-208">Extrahieren Sie das Paket aus der [MSI](https://go.microsoft.com/fwlink/?linkid=851168) -Installation in eine Freigabe für zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-208">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a device accessible share.</span></span>
    
2. <span data-ttu-id="ad9b4-209">Führen Sie das folgende Skript für die Skype Raum Systemen v2-Geräte ändern \<freigeben\> freigeben als Antwort auf das Gerät:</span><span class="sxs-lookup"><span data-stu-id="ad9b4-209">Run the following script targeting the Skype Room Systems v2 devices, changing \<share\> to the device share as appropriate:</span></span>
    
  ```
  Add-AppxPackage -Update -ForceApplicationShutdown -Path \\<share>\Rigel\x64\Ship\AppPackages\*\*.appx -DependencyPath (Get-ChildItem \\<share>\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx | Foreach-Object {$_.FullName}) 

  ```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="ad9b4-210">Administratormodus und Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="ad9b4-210">Admin mode and device management</span></span>
<span data-ttu-id="ad9b4-211"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="ad9b4-211"></span></span>

<span data-ttu-id="ad9b4-212">Für einige Verwaltungsfunktionen, zum Beispiel die manuelle Installation eines privaten Zertifizierungsstellenzertifikats, muss das Surface 4-Gerät in den Administratormodus versetzt werden. </span><span class="sxs-lookup"><span data-stu-id="ad9b4-212">Some management functions, like manually installing a private CA certificate, require placing the Surface 4 device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-is-running"></a><span data-ttu-id="ad9b4-213">Wechsel in Administratormodus und zurück, wenn die Skype Raum Systemen v2 app ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="ad9b4-213">Switching to Admin Mode and back when the Skype Room Systems v2 app is running</span></span>

1. <span data-ttu-id="ad9b4-214">Beenden Sie die aktuellen Anrufe, und kehren Sie zum Startbildschirm zurück.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-214">Hang up any ongoing calls and return to the home screen.</span></span>
    
2. <span data-ttu-id="ad9b4-215">Klicken Sie auf das Zahnradsymbol und rufen Sie das Menü (Optionen sind **Einstellungen**, **Eingabehilfen**und **Gerät neu starten** ).</span><span class="sxs-lookup"><span data-stu-id="ad9b4-215">Click on the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
    
3. <span data-ttu-id="ad9b4-216">Wählen Sie **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-216">Select **Settings**.</span></span>
    
4. <span data-ttu-id="ad9b4-217">Geben Sie das Administratorkennwort ein.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-217">Enter the Administrator Password.</span></span> <span data-ttu-id="ad9b4-218">Der Setupbildschirm wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-218">The Setup screen will appear.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ad9b4-p115">Wenn das Gerät nicht Mitglied einer Domäne ist, wird standardmäßig das lokale Administratorkonto (Benutzername „Admin“) verwendet. Das Standardkennwort für dieses Konto lautet „sfb“. Aus Sicherheitsgründen wird jedoch empfohlen, dieses Kennwort so bald wie möglich zu ändern.
Wenn der Computer Mitglied einer Domäne ist, können Sie sich mit einem Domänenkonto mit entsprechenden Berechtigungen anmelden.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-p115">If the device is not domain joined, the local administrative account (username "Admin") will be used by default. The default password for this account is 'sfb' but it is recommended that your organization change this for security reasons as soon as possible. If the machine is domain joined, you can sign in with an appropriately-privileged domain account.</span></span> 
  
5. <span data-ttu-id="ad9b4-222">Klicken Sie in der linken Spalte auf **Windows-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-222">Click on **Windows Settings** on the left column.</span></span>
    
6. <span data-ttu-id="ad9b4-223">Wählen Sie **Zu Administratoranmeldung wechseln** aus.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-223">Choose **Go to Admin Sign-in**.</span></span>
    
7. <span data-ttu-id="ad9b4-224">Geben Sie das Administratorkennwort ein.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-224">Enter the Administrator Password.</span></span> <span data-ttu-id="ad9b4-225">Daraufhin wird die App ordnungsgemäß abgemeldet, und Sie gelangen zum Windows-Anmeldebildschirm.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-225">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
    
8. <span data-ttu-id="ad9b4-p117">Melden Sie sich mit Ihren Administratoranmeldeinformationen beim Desktop an. Sie verfügen dann über die notwendigen Berechtigungen zum Verwalten des Geräts.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-p117">Log in to the desktop with your administrative credentials. You will have the necessary privileges to manage the device.</span></span>
    
9. <span data-ttu-id="ad9b4-228">Führen Sie die notwendigen Administratoraufgaben aus.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-228">Perform the necessary administrative tasks.</span></span>
    
10. <span data-ttu-id="ad9b4-229">Melden Sie sich bei Ihrem Administratorkonto ab.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-229">Sign out from the Admin account.</span></span>
    
11. <span data-ttu-id="ad9b4-230">Zurück zu Skype Raum Systemen v2, indem Sie das Symbol Benutzer Konto am linken Rand des Bildschirms auswählen, und wählen Sie **Skype**.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-230">Return to Skype Room Systems v2 by selecting the user account icon on the far left of the screen and select **Skype**.</span></span>
    
    <span data-ttu-id="ad9b4-231">Wenn der Benutzer **Skype** nicht aufgeführt ist, müssen Sie möglicherweise wählen Sie **Benutzer** aus, und geben **. \skype** als den Benutzernamen und das anmelden.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-231">If the **Skype** user is not listed, you may have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
 <span data-ttu-id="ad9b4-232">Die Konsole ist nun wieder in den normalen Betrieb-Modus. Das folgende Verfahren benötigen Sie eine Tastatur auf das Gerät anfügen, falls noch nicht angefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-232">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-crashes"></a><span data-ttu-id="ad9b4-233">Wechsel in Administratormodus und zurück, wenn die Skype Raum Systemen v2 app stürzt ab</span><span class="sxs-lookup"><span data-stu-id="ad9b4-233">Switching to Admin Mode and back when the Skype Room Systems v2 app crashes</span></span>

1. <span data-ttu-id="ad9b4-p118">Drücken Sie fünf Mal schnell hintereinander die WINDOWS-TASTE. Daraufhin gelangen Sie zum Windows-Anmeldebildschirm. </span><span class="sxs-lookup"><span data-stu-id="ad9b4-p118">Press the Windows key five times in rapid succession. This will bring you to the Windows logon screen.</span></span> 
    
2. <span data-ttu-id="ad9b4-236">Melden Sie sich mit Ihren Administratoranmeldeinformationen beim Desktop an.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-236">Log into the desktop with your administrative credentials.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ad9b4-237">Bei dieser Methode wird der Skype-Benutzer zwar nicht abgemeldet und die App nicht ordnungsgemäß beendet, aber Sie verwenden diese Methode nur, wenn die App nicht reagiert und die andere Methode nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-237">This method does not log the Skype user off or gracefully terminate the app, but you would only use it if the app was not responding and the other method was not available.</span></span> 
  
3. <span data-ttu-id="ad9b4-238">Führen Sie die notwendigen Administratoraufgaben aus.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-238">Perform the necessary administrative tasks.</span></span>
    
4. <span data-ttu-id="ad9b4-239">Starten Sie den Computer anschließend neu.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-239">Restart the machine when you are finished.</span></span>
    
 <span data-ttu-id="ad9b4-240">Die Konsole wird neu gestartet, in den normalen Betrieb-Modus, die Skype Raum Systemen v2 app ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-240">The console restarts into its normal operation mode, running the Skype Room Systems v2 app.</span></span> <span data-ttu-id="ad9b4-241">Sie können die Tastatur entfernen, wenn Sie sie angeschlossen hatten, um dieses Verfahren ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-241">You may remove the keyboard if it was attached to allow you to perform this procedure.</span></span>
## <a name="troubleshooting-tips"></a><span data-ttu-id="ad9b4-242">Tipps zur Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="ad9b4-242">Troubleshooting tips</span></span>
<span data-ttu-id="ad9b4-243"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="ad9b4-243"></span></span>

- <span data-ttu-id="ad9b4-244">Besprechungseinladungen werden möglicherweise nicht angezeigt, wenn sie über Domänengrenzen hinaus versendet werden (beispielsweise zwischen zwei Unternehmen).</span><span class="sxs-lookup"><span data-stu-id="ad9b4-244">Meeting invitations may not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="ad9b4-245">In diesen Fällen müssen IT-Administratoren entscheiden, ob externe Benutzer eine Besprechung planen dürfen.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-245">In such cases, IT admins should decide whether or not to allow external users to schedule a meeting.</span></span>
    
- <span data-ttu-id="ad9b4-246">Skype-Chatroom-Systemen v2 unterstützt Exchange AutoDiscover leitet über Exchange 2010 nicht.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-246">Skype Room Systems v2 does not support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
    
- <span data-ttu-id="ad9b4-247">Es empfiehlt sich, dass IT-Administratoren nicht verwendete Audioendpunkte deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-247">In general, it is a good practice for IT admins to disable any audio endpoints not intended for use.</span></span>
    
- <span data-ttu-id="ad9b4-248">Falls ein Spiegelbild in der Raumvorschau angezeigt wird, kann der IT-Administrator dies korrigieren, indem die Stromversorgung der Kamera angestellt wird oder die Bildausrichtung mit der Fernsteuerung der Kamera gekippt wird.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-248">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
    
- <span data-ttu-id="ad9b4-249">Es ist bekannt, dass der Zugang zum Konsolentouchscreen verloren gehen kann.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-249">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="ad9b4-250">In solchen Fällen wird durch einen Neustart des Systems der Skype Raum Systemen v2 manchmal das Problem behoben.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-250">In such cases, the issue is sometimes resolved by restarting the Skype Room Systems v2 system.</span></span>
    
- <span data-ttu-id="ad9b4-251">Beim Verbinden eines PCs mit der Konsole über verkabelte Erfassung kann ein Verlust der lokalen Audiodaten auftreten.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-251">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="ad9b4-252">Das Problem mit der Wiedergabe der lokalen Audiodaten kann in diesem Fall durch einen Neustart des PCs gelöst werden.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-252">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ad9b4-253">Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ad9b4-253">See also</span></span>
<span data-ttu-id="ad9b4-254"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="ad9b4-254"></span></span>

#### 

[<span data-ttu-id="ad9b4-255">Planen von Skype Raum Systemen v2</span><span class="sxs-lookup"><span data-stu-id="ad9b4-255">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="ad9b4-256">Bereitstellen von Skype Raum Systemen v2</span><span class="sxs-lookup"><span data-stu-id="ad9b4-256">Deploy Skype Room Systems v2</span></span>](../../deploy/deploy-clients/room-systems-v2.md)
  
[<span data-ttu-id="ad9b4-257">Konfigurieren einer Skype Raum Systemen v2-Konsole</span><span class="sxs-lookup"><span data-stu-id="ad9b4-257">Configure a Skype Room Systems v2 console</span></span>](../../deploy/deploy-clients/console.md)
  
[<span data-ttu-id="ad9b4-258">Verwalten einer Skype Raum v2 Konsole Systemeinstellungen Remote mit einer XML-Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="ad9b4-258">Manage a Skype Room Systems v2 console settings remotely with an XML configuration file</span></span>](xml-config-file.md)

