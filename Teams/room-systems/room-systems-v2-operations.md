---
title: Wartung und Betrieb von Microsoft Teams-Räumen
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
ms.collection: M365-voice
localization_priority: Normal
description: Lesen Sie dieses Thema, um mehr über die Verwaltung von Microsoft Teams rooms, der nächsten Generation von Skype Room-Systemen, zu erfahren.
ms.openlocfilehash: b32ac786c7c039bd1eaab060e12b7141a8d8cf72
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288563"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a><span data-ttu-id="801bc-103">Wartung und Betrieb von Microsoft Teams-Räumen</span><span class="sxs-lookup"><span data-stu-id="801bc-103">Microsoft Teams Rooms maintenance and operations</span></span> 
 
<span data-ttu-id="801bc-104">Lesen Sie dieses Thema, um mehr über die Verwaltung von Microsoft Teams rooms, der nächsten Generation von Skype Room-Systemen, zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="801bc-104">Read this topic to learn about management of Microsoft Teams Rooms, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="801bc-105">Microsoft Teams Rooms ist die neueste Konferenzlösung von Microsoft, die ihren Besprechungsraum in eine umfassende, kollaborative Umgebung verwandeln soll.</span><span class="sxs-lookup"><span data-stu-id="801bc-105">Microsoft Teams Rooms is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative experience.</span></span> <span data-ttu-id="801bc-106">Die Benutzer können Ihre vertrauten Microsoft Teams oder Skype for Business-Benutzeroberfläche nutzen, und IT-Administratoren schätzen eine einfach bereitgestellte und verwaltete Windows 10 Skype-Besprechungs-app.</span><span class="sxs-lookup"><span data-stu-id="801bc-106">Users will enjoy its familiar Microsoft Teams or Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="801bc-107">Microsoft Teams rooms wurde entwickelt, um vorhandene Geräte wie LCD-Panels zur Vereinfachung der Installation zu nutzen, um Microsoft Teams oder Skype for Business in ihren Besprechungsraum zu bringen.</span><span class="sxs-lookup"><span data-stu-id="801bc-107">Microsoft Teams Rooms is designed to leverage existing equipment like LCD panels for ease of installation to bring Microsoft Teams or Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="801bc-108">Mit zusätzlicher Konfiguration ist die Remoteverwaltung mithilfe von Microsoft Azure Monitor möglich, wie in [Plan Microsoft Teams rooms Management with Azure Monitor](azure-monitor-plan.md)beschrieben, [Bereitstellen von Microsoft Teams rooms Management mit Azure Monitor](azure-monitor-deploy.md), [Manage Microsoft Teams rooms-Geräte mit Azure Monitor](azure-monitor-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="801bc-108">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md), [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-deploy.md).</span></span> <span data-ttu-id="801bc-109">Sie können die [Konsoleneinstellungen für Microsoft Teams rooms auch Remote mit einer XML-Konfigurationsdatei verwalten](xml-config-file.md), die das Anwenden eines benutzerdefinierten Anzeige Designs umfasst.</span><span class="sxs-lookup"><span data-stu-id="801bc-109">You may also [Manage Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a><span data-ttu-id="801bc-110">Sammeln von Protokollen in Microsoft Teams-Räumen</span><span class="sxs-lookup"><span data-stu-id="801bc-110">Collecting logs on Microsoft Teams Rooms</span></span>
<span data-ttu-id="801bc-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="801bc-111"></span></span>

<span data-ttu-id="801bc-112">Zum Sammeln von Protokollen müssen Sie das Protokoll Sammlungs Skript aufrufen, das mit der Microsoft Teams rooms-App ausgeliefert wird.</span><span class="sxs-lookup"><span data-stu-id="801bc-112">To collect logs, you must invoke the log collection script that ships with the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="801bc-113">Starten Sie im Administratormodus eine Eingabeaufforderung mit erhöhten Rechten, und geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="801bc-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="801bc-114">Die Protokolle werden in c:\rigel. als ZIP-Datei ausgegeben</span><span class="sxs-lookup"><span data-stu-id="801bc-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="801bc-115">Anzeigeeinstellungen vorne im Raum</span><span class="sxs-lookup"><span data-stu-id="801bc-115">Front of Room Display Settings</span></span>
<span data-ttu-id="801bc-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="801bc-116"></span></span>

<span data-ttu-id="801bc-117">Konfigurieren Sie den Bildschirm vorne im Raum für den Modus „Erweitert“.</span><span class="sxs-lookup"><span data-stu-id="801bc-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="801bc-118">Auf diese Weise wird sichergestellt, dass die Konsolen-Benutzeroberfläche nicht auf dieser Anzeige dupliziert wird, wenn Sie die Anzeige auf dem Bildschirm ausschalten.</span><span class="sxs-lookup"><span data-stu-id="801bc-118">Doing so will ensure that the console UI is not duplicated on that display when you cycle power on the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="801bc-119">Ein Consumer-TV, der als eine Anzeige vorne im Raum verwendet wird, muss das Feature „Consumer Electronics Control (CEC)“ von HDMI unterstützen/aktivieren, sodass ein automatischer Wechsel zu einer aktiven Videoquelle aus dem Standbymodus möglich ist.</span><span class="sxs-lookup"><span data-stu-id="801bc-119">A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode.</span></span> <span data-ttu-id="801bc-120">Dieses Feature wird nicht auf allen TVs unterstützt.</span><span class="sxs-lookup"><span data-stu-id="801bc-120">This feature is not supported on all TVs.</span></span> 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a><span data-ttu-id="801bc-121">Microsoft Teams rooms Reset (Factory Restore)</span><span class="sxs-lookup"><span data-stu-id="801bc-121">Microsoft Teams Rooms Reset (Factory Restore)</span></span>
<span data-ttu-id="801bc-122"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="801bc-122"></span></span>

<span data-ttu-id="801bc-123">Wenn die Microsoft Teams-Räume nicht gut ausgeführt werden, kann es hilfreich sein, einen Factory-Reset durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="801bc-123">If Microsoft Teams Rooms isn't running well, performing a factory reset might help.</span></span> <span data-ttu-id="801bc-124">Dies kann in der Einstellungs-APP auf der Registerkarte " **Wiederherstellung** " erfolgen. Klicken Sie unter " **diesen PC zurücksetzen**" auf " **Erste Schritte**" und dann auf " **Alle entfernen**".</span><span class="sxs-lookup"><span data-stu-id="801bc-124">This can be done in the Settings app on the **Recovery** tab. Beneath **Reset this PC**, select **Get started**, and then **Remove everything**.</span></span> <span data-ttu-id="801bc-125">Folgen Sie den restlichen Eingabeaufforderungen, um das Gerät zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="801bc-125">Follow the remaining prompts to reset the device.</span></span>
  
> [!NOTE]
> <span data-ttu-id="801bc-126">Es gibt ein bekanntes Problem, bei dem die Microsoft Teams-Räume unbrauchbar werden können, wenn die Option **meine Dateien beibehalten-apps und Einstellungen entfernt, aber Ihre persönlichen Dateien beibehalten** aktiviert ist, während des Windows-Reset-Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="801bc-126">There is a known issue where the Microsoft Teams Rooms can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="801bc-127">Verwenden Sie diese Option _nicht_ .</span><span class="sxs-lookup"><span data-stu-id="801bc-127">Do _not_ use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="801bc-128">Unterstützte Remoteoptionen</span><span class="sxs-lookup"><span data-stu-id="801bc-128">Supported Remote Options</span></span>
<span data-ttu-id="801bc-129"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="801bc-129"></span></span>

<span data-ttu-id="801bc-130">In der folgenden Tabelle sind die möglichen Remotevorgänge und die Methoden zusammengefasst, die Sie für diese Vorgänge verwenden können.</span><span class="sxs-lookup"><span data-stu-id="801bc-130">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="801bc-131">\*\*Arbeitsgruppe \*\*</span><span class="sxs-lookup"><span data-stu-id="801bc-131">**Workgroup**</span></span>|<span data-ttu-id="801bc-132">**Nicht Mitglied einer Domäne**</span><span class="sxs-lookup"><span data-stu-id="801bc-132">**Not domain joined**</span></span>|<span data-ttu-id="801bc-133">**Mitglied einer Domäne**</span><span class="sxs-lookup"><span data-stu-id="801bc-133">**Domain joined**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="801bc-134">Neustart</span><span class="sxs-lookup"><span data-stu-id="801bc-134">Restart</span></span>  <br/> |<span data-ttu-id="801bc-135">Remotedesktop</span><span class="sxs-lookup"><span data-stu-id="801bc-135">Remote desktop</span></span>  <br/> <span data-ttu-id="801bc-136">Remote-Powershell</span><span class="sxs-lookup"><span data-stu-id="801bc-136">Remote Powershell</span></span>  <br/> |<span data-ttu-id="801bc-137">Remote Desktop (erfordert weitere Konfiguration)</span><span class="sxs-lookup"><span data-stu-id="801bc-137">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="801bc-138">Remote-PowerShell (weitere Konfiguration erforderlich)</span><span class="sxs-lookup"><span data-stu-id="801bc-138">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="801bc-139">SCCM</span><span class="sxs-lookup"><span data-stu-id="801bc-139">SCCM</span></span>  <br/> |
|<span data-ttu-id="801bc-140">Betriebssystemupdate</span><span class="sxs-lookup"><span data-stu-id="801bc-140">Update OS</span></span>  <br/> |<span data-ttu-id="801bc-141">Windows Update</span><span class="sxs-lookup"><span data-stu-id="801bc-141">Windows Update</span></span>  <br/> |<span data-ttu-id="801bc-142">Windows Update</span><span class="sxs-lookup"><span data-stu-id="801bc-142">Windows Update</span></span>  <br/> <span data-ttu-id="801bc-143">WSUS</span><span class="sxs-lookup"><span data-stu-id="801bc-143">WSUS</span></span>  <br/> |
|<span data-ttu-id="801bc-144">App-Update</span><span class="sxs-lookup"><span data-stu-id="801bc-144">App update</span></span>  <br/> |<span data-ttu-id="801bc-145">Windows Store</span><span class="sxs-lookup"><span data-stu-id="801bc-145">Windows Store</span></span>  <br/> |<span data-ttu-id="801bc-146">Windows Store</span><span class="sxs-lookup"><span data-stu-id="801bc-146">Windows Store</span></span>  <br/> <span data-ttu-id="801bc-147">SCCM</span><span class="sxs-lookup"><span data-stu-id="801bc-147">SCCM</span></span>  <br/> |
|<span data-ttu-id="801bc-148">Skype-Kontokonfiguration</span><span class="sxs-lookup"><span data-stu-id="801bc-148">Skype Account Config</span></span>  <br/> |<span data-ttu-id="801bc-149">Zurzeit nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="801bc-149">Not currently supported</span></span>  <br/> |<span data-ttu-id="801bc-150">Zurzeit nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="801bc-150">Not currently supported</span></span>  <br/> |
|<span data-ttu-id="801bc-151">Zugriff auf Protokolle</span><span class="sxs-lookup"><span data-stu-id="801bc-151">Access logs</span></span>  <br/> |<span data-ttu-id="801bc-152">Zurzeit nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="801bc-152">Not currently supported</span></span>  <br/> |<span data-ttu-id="801bc-153">Zurzeit nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="801bc-153">Not currently supported</span></span>  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a><span data-ttu-id="801bc-154">Konfigurieren von Gruppenrichtlinien für Microsoft Teams-Chatrooms</span><span class="sxs-lookup"><span data-stu-id="801bc-154">Configuring Group Policy for Microsoft Teams Rooms</span></span>
<span data-ttu-id="801bc-155"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="801bc-155"></span></span>

<span data-ttu-id="801bc-156">Dieser Abschnitt behandelt die Systemeinstellungen, von denen Microsoft Teams-Räume abhängig sind, um ordnungsgemäß zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="801bc-156">This section covers system settings that Microsoft Teams Rooms depends on to function properly.</span></span> <span data-ttu-id="801bc-157">Wenn Sie Microsoft Teams-Räumen eine Domäne hinzugefügt haben, stellen Sie sicher, dass Ihre Gruppenrichtlinie die Einstellungen in der folgenden Tabelle nicht außer Kraft setzt.</span><span class="sxs-lookup"><span data-stu-id="801bc-157">When joining Microsoft Teams Rooms to a domain, ensure that your group policy doesn't override the settings in the following table.</span></span>
  

|<span data-ttu-id="801bc-158">**Einstellung**</span><span class="sxs-lookup"><span data-stu-id="801bc-158">**Setting**</span></span>|<span data-ttu-id="801bc-159">**Ermöglicht**</span><span class="sxs-lookup"><span data-stu-id="801bc-159">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="801bc-160">HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span><span class="sxs-lookup"><span data-stu-id="801bc-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span></span>  <br/> |<span data-ttu-id="801bc-161">Ermöglicht das Starten von Microsoft Teams-Räumen</span><span class="sxs-lookup"><span data-stu-id="801bc-161">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="801bc-162">Power Management-\> auf AC, schalten Sie den Bildschirm nach 10 Minuten aus.</span><span class="sxs-lookup"><span data-stu-id="801bc-162">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="801bc-163">Power Management-\> auf AC, niemals System in den Standbymodus versetzen</span><span class="sxs-lookup"><span data-stu-id="801bc-163">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="801bc-164">Ermöglicht Microsoft Teams-Räumen, die angefügten anzeigen zu deaktivieren und automatisch zu aktivieren</span><span class="sxs-lookup"><span data-stu-id="801bc-164">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="801bc-165">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="801bc-165">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="801bc-166">Oder entsprechende Möglichkeit zum Deaktivieren des Kennwortablaufs für das lokale Konto.</span><span class="sxs-lookup"><span data-stu-id="801bc-166">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="801bc-167">Wird dies nicht ausgeführt, kann bei der Anmeldung des Skype-Kontos aufgrund eines abgelaufenen Kennworts ein Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="801bc-167">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="801bc-168">Beachten Sie, dass sich dies auf alle lokalen Konten auf dem Computer auswirkt, sodass bei Nichtfestlegung dieser Einstellung auch das Administratorkonto ablaufen kann.</span><span class="sxs-lookup"><span data-stu-id="801bc-168">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="801bc-169">Ermöglicht die ständige Anmeldung des Skype-Kontos</span><span class="sxs-lookup"><span data-stu-id="801bc-169">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="801bc-170">Das Übertragen von Dateien mithilfe von Gruppenrichtlinien wird unter [Konfigurieren eines Dateielements](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)erläutert.</span><span class="sxs-lookup"><span data-stu-id="801bc-170">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="801bc-171">Remoteverwaltung mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="801bc-171">Remote Management using PowerShell</span></span>
<span data-ttu-id="801bc-172"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="801bc-172"></span></span>

<span data-ttu-id="801bc-173">Sie können die folgenden Verwaltungsvorgänge Remote mithilfe von PowerShell ausführen (in der folgenden Tabelle finden Sie Skriptbeispiele):</span><span class="sxs-lookup"><span data-stu-id="801bc-173">You can perform the following management operations remotely by using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="801bc-174">Abrufen von angeschlossenen Geräten</span><span class="sxs-lookup"><span data-stu-id="801bc-174">Get attached devices</span></span>
    
- <span data-ttu-id="801bc-175">Abrufen des App-Status</span><span class="sxs-lookup"><span data-stu-id="801bc-175">Get app status</span></span>
    
- <span data-ttu-id="801bc-176">Abrufen von Systeminformationen</span><span class="sxs-lookup"><span data-stu-id="801bc-176">Get system info</span></span>
    
- <span data-ttu-id="801bc-177">Neustart des Systems</span><span class="sxs-lookup"><span data-stu-id="801bc-177">Reboot system</span></span>
    
- <span data-ttu-id="801bc-178">Abrufen von Protokollen</span><span class="sxs-lookup"><span data-stu-id="801bc-178">Retrieve logs</span></span>
    
- <span data-ttu-id="801bc-179">Übertragen von Dateien (erfordert einen Domänenbeitritt zu Microsoft Teams-Räumen)</span><span class="sxs-lookup"><span data-stu-id="801bc-179">Transfer files (requires a domain-joined Microsoft Teams Rooms)</span></span>
    
> [!NOTE]
> <span data-ttu-id="801bc-180">Diese Funktion ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="801bc-180">This functionality is off by default.</span></span> <span data-ttu-id="801bc-181">Sie müssen die Remote-PowerShell für Ihre Umgebung im Microsoft Teams rooms-System aktivieren, um die folgenden Vorgänge auszuführen.</span><span class="sxs-lookup"><span data-stu-id="801bc-181">You need to enable remote PowerShell for your environment on the Microsoft Teams Rooms system to perform the operations below.</span></span> <span data-ttu-id="801bc-182">Informationen zum Aktivieren von Remote-PowerShell finden Sie in der Dokumentation zu **[enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** .</span><span class="sxs-lookup"><span data-stu-id="801bc-182">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** for information about how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="801bc-183">Sie können Remote-PowerShell beispielsweise wie folgt aktivieren:</span><span class="sxs-lookup"><span data-stu-id="801bc-183">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="801bc-184">Anmelden als Administrator auf einem Microsoft Teams rooms-Gerät.</span><span class="sxs-lookup"><span data-stu-id="801bc-184">Sign in as Admin on a Microsoft Teams Rooms device.</span></span>
    
2. <span data-ttu-id="801bc-185">Öffnen Sie eine erweiterte PowerShell-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="801bc-185">Open an elevated PowerShell command prompt.</span></span>
    
3. <span data-ttu-id="801bc-186">Geben Sie den folgenden Befehl ein: Enable-PSRemoting -force</span><span class="sxs-lookup"><span data-stu-id="801bc-186">Enter the following command: Enable-PSRemoting -force</span></span>
    
<span data-ttu-id="801bc-187">So führen Sie einen Verwaltungsvorgang durch:</span><span class="sxs-lookup"><span data-stu-id="801bc-187">To perform a management operation:</span></span>
  
1. <span data-ttu-id="801bc-188">Melden Sie sich bei einem PC mit Kontoanmeldeinformationen an, die über die Berechtigung zum Ausführen von PowerShell-Befehlen auf einem Microsoft Teams rooms-Gerät verfügen.</span><span class="sxs-lookup"><span data-stu-id="801bc-188">Sign in to a PC with account credentials that have permission to run PowerShell commands on a Microsoft Teams Rooms device.</span></span>
    
2. <span data-ttu-id="801bc-189">Öffnen Sie eine reguläre PowerShell-Eingabeaufforderung auf dem PC.</span><span class="sxs-lookup"><span data-stu-id="801bc-189">Open a regular PowerShell command prompt on the PC.</span></span>
    
3. <span data-ttu-id="801bc-190">Kopieren Sie den Befehlstext aus der folgenden Tabelle, und fügen Sie ihn an der Eingabeaufforderung ein.</span><span class="sxs-lookup"><span data-stu-id="801bc-190">Copy the command text from the table below and paste it at the prompt.</span></span>
    
4. <span data-ttu-id="801bc-191">Ersetzen `<Device fqdn>` Sie Felder durch FQDN-Werte, die für Ihre Umgebung geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="801bc-191">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
    
5. <span data-ttu-id="801bc-192">Ersetzen \* \<Sie\> Path\* durch den Dateinamen und den lokalen Pfad der Master-SkypeSettings. XML-Konfigurationsdatei (oder des Design Bilds).</span><span class="sxs-lookup"><span data-stu-id="801bc-192">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="801bc-193">So erhalten Sie angefügte Geräte</span><span class="sxs-lookup"><span data-stu-id="801bc-193">To Get Attached Devices</span></span>
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="801bc-194">Abrufen des App-Status</span><span class="sxs-lookup"><span data-stu-id="801bc-194">Get App Status</span></span>
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="801bc-195">Abrufen von Systeminformationen</span><span class="sxs-lookup"><span data-stu-id="801bc-195">Get System Info</span></span>
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="801bc-196">Neustart des Systems</span><span class="sxs-lookup"><span data-stu-id="801bc-196">Reboot System</span></span>
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="801bc-197">Abrufen von Protokollen</span><span class="sxs-lookup"><span data-stu-id="801bc-197">Retrieve Logs</span></span>
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="801bc-198">Pushen einer XML-Konfigurationsdatei (oder Design Grafik)</span><span class="sxs-lookup"><span data-stu-id="801bc-198">Push an XML configuration file (or theme graphic)</span></span>
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="801bc-199">Softwareupdates</span><span class="sxs-lookup"><span data-stu-id="801bc-199">Software updates</span></span>
<span data-ttu-id="801bc-200"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="801bc-200"></span></span>

<span data-ttu-id="801bc-201">Standardmäßig versucht Microsoft Teams rooms, eine Verbindung mit dem Windows Store herzustellen, um die neueste Version der Microsoft Teams Rooms-Software abzurufen, damit das Gerät normalen Internetzugriff benötigt.</span><span class="sxs-lookup"><span data-stu-id="801bc-201">By default, Microsoft Teams Rooms attempts to connect to the Windows Store to get the latest version of Microsoft Teams Rooms software, so the device will require regular internet access.</span></span> <span data-ttu-id="801bc-202">Bevor Sie sich mit Microsoft mit Supportproblemen in Verbindung setzen, stellen Sie sicher, dass das Gerät Microsoft Teams Rooms mit der neuesten Version der App geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="801bc-202">Before contacting Microsoft with support issues, be sure the Microsoft Teams Rooms device is loaded with the latest version of the app.</span></span>
  
<span data-ttu-id="801bc-203">Standardmäßig stellt Microsoft Teams rooms eine Verbindung mit Windows Update her, um Betriebssystem-und USB-Peripheriegeräte-Firmware-Aktualisierungen abzurufen und außerhalb der konfigurierten Geschäftszeiten zu installieren.</span><span class="sxs-lookup"><span data-stu-id="801bc-203">By default, Microsoft Teams Rooms connects to Windows Update to retrieve operating system and USB peripheral device firmware updates, and installs them outside of configured business hours.</span></span> <span data-ttu-id="801bc-204">Sie können Geschäftszeiten konfigurieren, indem Sie sich beim Administratorkonto anmelden und die Einstellungen-App ausführen.</span><span class="sxs-lookup"><span data-stu-id="801bc-204">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="801bc-205">Wenn Sie Updates manuell verwalten möchten und dem normalen Verfahren für [Microsoft Store for Business](https://businessstore.microsoft.com/store) zum [Verteilen von Offline-Apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)nicht folgen können, können Sie die entsprechende APPX-Datei und-Abhängigkeiten aus dem [Deployment Kit](https://go.microsoft.com/fwlink/?linkid=851168) erwerben (von die Anweisungen zum [Konfigurieren einer Microsoft Teams rooms-Konsole](console.md)), die mit SCCM verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="801bc-205">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/store) to [Distribute offline apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Microsoft Teams Rooms console](console.md)) that can be used with SCCM.</span></span> <span data-ttu-id="801bc-206">Das Deployment Kit-Release hinkt hinter der Store-Version zurück, daher ist es möglicherweise nicht immer mit dem neuesten verfügbaren Build identisch.</span><span class="sxs-lookup"><span data-stu-id="801bc-206">The deployment kit release lags behind the store release, so it might not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="801bc-207">So aktualisieren Sie die Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="801bc-207">To update using Powershell</span></span>

1. <span data-ttu-id="801bc-208">Extrahieren Sie das Paket aus der [MSI](https://go.microsoft.com/fwlink/?linkid=851168) -Installationsdatei auf eine Freigabe, auf die das Gerät zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="801bc-208">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a share the device can access.</span></span>
    
2. <span data-ttu-id="801bc-209">Führen Sie das folgende Skript aus, das auf die Microsoft Teams \<rooms\> -Geräte ausgerichtet ist, und ändern Sie die Freigabe auf die Gerätefreigabe nach Bedarf:</span><span class="sxs-lookup"><span data-stu-id="801bc-209">Run the following script targeting the Microsoft Teams Rooms devices, changing \<share\> to the device share as appropriate:</span></span>
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="801bc-210">Administratormodus und Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="801bc-210">Admin mode and device management</span></span>
<span data-ttu-id="801bc-211"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="801bc-211"></span></span>

<span data-ttu-id="801bc-212">Einige Verwaltungsfunktionen, wie das manuelle Installieren eines privaten Zertifizierungsstellenzertifikats, erfordern das Platzieren des Surface pro-Geräts im Administratormodus.</span><span class="sxs-lookup"><span data-stu-id="801bc-212">Some management functions, like manually installing a private CA certificate, require placing the Surface Pro device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a><span data-ttu-id="801bc-213">Wechseln zum Administratormodus und zurück, wenn die Microsoft Teams rooms-app ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="801bc-213">Switching to Admin Mode and back when the Microsoft Teams Rooms app is running</span></span>

1. <span data-ttu-id="801bc-214">Beenden Sie alle laufenden Anrufe, und kehren Sie zum Startbildschirm zurück.</span><span class="sxs-lookup"><span data-stu-id="801bc-214">Hang up any ongoing calls, and return to the home screen.</span></span>
    
2. <span data-ttu-id="801bc-215">Wählen Sie das Zahnradsymbol aus, und öffnen Sie das Menü (Optionen sind **Einstellungen**, **Barrierefreiheit**und **Gerät neu starten** ).</span><span class="sxs-lookup"><span data-stu-id="801bc-215">Select the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
    
3. <span data-ttu-id="801bc-216">Wählen Sie **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="801bc-216">Select **Settings**.</span></span>
    
4. <span data-ttu-id="801bc-217">Geben Sie das Administratorkennwort ein.</span><span class="sxs-lookup"><span data-stu-id="801bc-217">Enter the Administrator Password.</span></span> <span data-ttu-id="801bc-218">Der Setupbildschirm wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="801bc-218">The Setup screen will appear.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="801bc-219">Wenn das Gerät nicht mit der Domäne verbunden ist, wird standardmäßig das lokale Administratorkonto (Benutzername "Administrator") verwendet.</span><span class="sxs-lookup"><span data-stu-id="801bc-219">If the device isn't domain-joined, the local administrative account (username "Admin") will be used by default.</span></span> <span data-ttu-id="801bc-220">Das Standardkennwort für dieses Konto ist "SFB", es wird jedoch empfohlen, dass Ihre Organisation dies aus Sicherheitsgründen so schnell wie möglich ändert.</span><span class="sxs-lookup"><span data-stu-id="801bc-220">The default password for this account is 'sfb' but it is recommended that your organization change this for security reasons as soon as possible.</span></span> <span data-ttu-id="801bc-221">Wenn der Computer mit einer Domäne verbunden ist, können Sie sich mit einem entsprechend privilegierten Domänenkonto anmelden.</span><span class="sxs-lookup"><span data-stu-id="801bc-221">If the machine is domain-joined, you can sign in with an appropriately privileged domain account.</span></span> 
  
5. <span data-ttu-id="801bc-222">Wählen Sie in der linken Spalte **Windows-Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="801bc-222">Select **Windows Settings** in the left column.</span></span>
    
6. <span data-ttu-id="801bc-223">Wählen Sie **Zu Administratoranmeldung wechseln** aus.</span><span class="sxs-lookup"><span data-stu-id="801bc-223">Choose **Go to Admin Sign-in**.</span></span>
    
7. <span data-ttu-id="801bc-224">Geben Sie das Administratorkennwort ein.</span><span class="sxs-lookup"><span data-stu-id="801bc-224">Enter the Administrator Password.</span></span> <span data-ttu-id="801bc-225">Daraufhin wird die App ordnungsgemäß abgemeldet, und Sie gelangen zum Windows-Anmeldebildschirm.</span><span class="sxs-lookup"><span data-stu-id="801bc-225">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
    
8. <span data-ttu-id="801bc-226">Melden Sie sich mit Ihren Administratoranmeldeinformationen beim Desktop an.</span><span class="sxs-lookup"><span data-stu-id="801bc-226">Log in to the desktop with your administrative credentials.</span></span> <span data-ttu-id="801bc-227">Sie verfügen über die erforderlichen Berechtigungen zum Verwalten des Geräts.</span><span class="sxs-lookup"><span data-stu-id="801bc-227">You'll have the necessary privileges to manage the device.</span></span>
    
9. <span data-ttu-id="801bc-228">Führen Sie die notwendigen Administratoraufgaben aus.</span><span class="sxs-lookup"><span data-stu-id="801bc-228">Perform the necessary administrative tasks.</span></span>
    
10. <span data-ttu-id="801bc-229">Melden Sie sich bei Ihrem Administratorkonto ab.</span><span class="sxs-lookup"><span data-stu-id="801bc-229">Sign out from the Admin account.</span></span>
    
11. <span data-ttu-id="801bc-230">Kehren Sie zu Microsoft Teams rooms zurück, indem Sie auf der linken Seite des Bildschirms das Symbol für das Benutzerkonto auswählen und dann **Skype**auswählen.</span><span class="sxs-lookup"><span data-stu-id="801bc-230">Return to Microsoft Teams Rooms by selecting the user account icon on the far left side of the screen and then selecting **Skype**.</span></span>
    
    <span data-ttu-id="801bc-231">Wenn der **Skype** -Nutzer nicht aufgeführt ist, müssen Sie möglicherweise einen **anderen Benutzer** auswählen und **.\skype** als Benutzernamen eingeben und sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="801bc-231">If the **Skype** user is not listed, you might have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
<span data-ttu-id="801bc-232">Die Konsole befindet sich nun wieder im normalen Betriebsmodus. Das folgende Verfahren setzt voraus, dass Sie eine Tastatur an das Gerät anfügen, wenn noch keines angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="801bc-232">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a><span data-ttu-id="801bc-233">Wechseln zum Administratormodus und zurück, wenn die Microsoft Teams rooms-App abstürzt</span><span class="sxs-lookup"><span data-stu-id="801bc-233">Switching to Admin Mode and back when the Microsoft Teams Rooms app crashes</span></span>

1. <span data-ttu-id="801bc-234">Drücken Sie fünf Mal schnell hintereinander die WINDOWS-TASTE.</span><span class="sxs-lookup"><span data-stu-id="801bc-234">Press the Windows key five times in rapid succession.</span></span> <span data-ttu-id="801bc-235">Daraufhin gelangen Sie zum Windows-Anmeldebildschirm.</span><span class="sxs-lookup"><span data-stu-id="801bc-235">This will bring you to the Windows logon screen.</span></span> 
    
2. <span data-ttu-id="801bc-236">Melden Sie sich mit Ihren Administratoranmeldeinformationen beim Desktop an.</span><span class="sxs-lookup"><span data-stu-id="801bc-236">Log in to the desktop with your administrative credentials.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="801bc-237">Bei dieser Methode wird der Skype-Benutzer nicht abgemeldet oder die APP nicht ordnungsgemäß beendet, aber Sie würden ihn verwenden, wenn die APP nicht antwortete und die andere Methode nicht verfügbar war.</span><span class="sxs-lookup"><span data-stu-id="801bc-237">This method doesn't log the Skype user off or gracefully terminate the app, but you'd use it if the app wasn't responding and the other method wasn't available.</span></span> 
  
3. <span data-ttu-id="801bc-238">Führen Sie die notwendigen Administratoraufgaben aus.</span><span class="sxs-lookup"><span data-stu-id="801bc-238">Perform the necessary administrative tasks.</span></span>
    
4. <span data-ttu-id="801bc-239">Starten Sie den Computer neu, wenn Sie fertig sind.</span><span class="sxs-lookup"><span data-stu-id="801bc-239">Restart the machine when you're finished.</span></span>
    
   <span data-ttu-id="801bc-240">Die Konsole wird im normalen Betriebsmodus neu gestartet, wobei die Microsoft Teams rooms-app ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="801bc-240">The console restarts into its normal operation mode, running the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="801bc-241">Sie können die Tastatur entfernen, wenn Sie angefügt wurde, um dieses Verfahren ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="801bc-241">You can remove the keyboard, if it was attached to allow you to perform this procedure.</span></span>
   ## <a name="troubleshooting-tips"></a><span data-ttu-id="801bc-242">Tipps zur Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="801bc-242">Troubleshooting tips</span></span>
   <span data-ttu-id="801bc-243"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="801bc-243"></span></span>

- <span data-ttu-id="801bc-244">Besprechungseinladungen werden möglicherweise nicht angezeigt, wenn Sie über Domänengrenzen hinweg gesendet werden (beispielsweise zwischen zwei Unternehmen).</span><span class="sxs-lookup"><span data-stu-id="801bc-244">Meeting invitations might not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="801bc-245">In solchen Fällen sollten IT-Administratoren entscheiden, ob Sie externen Benutzern das Planen einer Besprechung gestatten möchten.</span><span class="sxs-lookup"><span data-stu-id="801bc-245">In such cases, IT admins should decide whether to allow external users to schedule a meeting.</span></span>
    
- <span data-ttu-id="801bc-246">Microsoft Teams rooms unterstützt keine Exchange-Auto Ermittlungs Umleitungen über Exchange 2010.</span><span class="sxs-lookup"><span data-stu-id="801bc-246">Microsoft Teams Rooms doesn't support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
    
- <span data-ttu-id="801bc-247">Im Allgemeinen empfiehlt es sich, dass IT-Administratoren alle audiopunkte deaktivieren, die Sie nicht verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="801bc-247">In general, it's a good practice for IT admins to disable any audio endpoints they don't intend to use.</span></span>
    
- <span data-ttu-id="801bc-248">Falls ein Spiegelbild in der Raumvorschau angezeigt wird, kann der IT-Administrator dies korrigieren, indem die Stromversorgung der Kamera angestellt wird oder die Bildausrichtung mit der Fernsteuerung der Kamera gekippt wird.</span><span class="sxs-lookup"><span data-stu-id="801bc-248">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
    
- <span data-ttu-id="801bc-249">Es ist bekannt, dass der Zugang zum Konsolentouchscreen verloren gehen kann.</span><span class="sxs-lookup"><span data-stu-id="801bc-249">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="801bc-250">In diesem Fall wird das Problem manchmal durch einen Neustart des Microsoft Teams rooms-Systems behoben.</span><span class="sxs-lookup"><span data-stu-id="801bc-250">In such cases, the issue is sometimes resolved by restarting the Microsoft Teams Rooms system.</span></span>
    
- <span data-ttu-id="801bc-251">Beim Verbinden eines PCs mit der Konsole über verkabelte Erfassung kann ein Verlust der lokalen Audiodaten auftreten.</span><span class="sxs-lookup"><span data-stu-id="801bc-251">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="801bc-252">Das Problem mit der Wiedergabe der lokalen Audiodaten kann in diesem Fall durch einen Neustart des PCs gelöst werden.</span><span class="sxs-lookup"><span data-stu-id="801bc-252">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    
