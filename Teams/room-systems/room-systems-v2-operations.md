---
title: Wartung und Betrieb von Microsoft Teams-Räumen
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection: M365-voice
localization_priority: Normal
description: Lesen Sie dieses Thema, um mehr über die Verwaltung von Microsoft Teams rooms, der nächsten Generation von Skype Room-Systemen, zu erfahren.
ms.openlocfilehash: 601e9e31f6a874d84dae6f4a3b44c26324a7b6f3
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427943"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a><span data-ttu-id="a2ba8-103">Wartung und Betrieb von Microsoft Teams-Räumen</span><span class="sxs-lookup"><span data-stu-id="a2ba8-103">Microsoft Teams Rooms maintenance and operations</span></span> 
 
<span data-ttu-id="a2ba8-104">Lesen Sie dieses Thema, um mehr über die Verwaltung von Microsoft Teams rooms, der nächsten Generation von Skype Room-Systemen, zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-104">Read this topic to learn about management of Microsoft Teams Rooms, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="a2ba8-105">Microsoft Teams Rooms ist die neueste Konferenzlösung von Microsoft, die ihren Besprechungsraum in eine umfassende, kollaborative Umgebung verwandeln soll.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-105">Microsoft Teams Rooms is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative experience.</span></span> <span data-ttu-id="a2ba8-106">Die Benutzer können Ihre vertrauten Microsoft Teams oder Skype for Business-Benutzeroberfläche nutzen, und IT-Administratoren schätzen eine einfach bereitgestellte und verwaltete Windows 10 Skype-Besprechungs-app.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-106">Users will enjoy its familiar Microsoft Teams or Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="a2ba8-107">Microsoft Teams rooms wurde entwickelt, um vorhandene Geräte wie LCD-Panels zur Vereinfachung der Installation zu nutzen, um Microsoft Teams oder Skype for Business in ihren Besprechungsraum zu bringen.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-107">Microsoft Teams Rooms is designed to leverage existing equipment like LCD panels for ease of installation to bring Microsoft Teams or Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="a2ba8-108">Mit zusätzlicher Konfiguration ist die Remoteverwaltung mithilfe von Microsoft Azure Monitor möglich, wie in [Plan Microsoft Teams rooms Management with Azure Monitor](azure-monitor-plan.md)beschrieben, [Bereitstellen von Microsoft Teams rooms Management mit Azure Monitor](azure-monitor-deploy.md), [Manage Microsoft Teams rooms-Geräte mit Azure Monitor](azure-monitor-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="a2ba8-108">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md), [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-deploy.md).</span></span> <span data-ttu-id="a2ba8-109">Sie können die [Konsoleneinstellungen für Microsoft Teams rooms auch Remote mit einer XML-Konfigurationsdatei verwalten](xml-config-file.md), die das Anwenden eines benutzerdefinierten Anzeige Designs umfasst.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-109">You may also [Manage Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a><span data-ttu-id="a2ba8-110">Sammeln von Protokollen in Microsoft Teams-Räumen</span><span class="sxs-lookup"><span data-stu-id="a2ba8-110">Collecting logs on Microsoft Teams Rooms</span></span>
<span data-ttu-id="a2ba8-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="a2ba8-111"></span></span>

<span data-ttu-id="a2ba8-112">Zum Sammeln von Protokollen müssen Sie das Protokoll Sammlungs Skript aufrufen, das mit der Microsoft Teams rooms-App ausgeliefert wird.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-112">To collect logs, you must invoke the log collection script that ships with the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="a2ba8-113">Starten Sie im Administratormodus eine Eingabeaufforderung mit erhöhten Rechten, und geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="a2ba8-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="a2ba8-114">Die Protokolle werden in c:\rigel. als ZIP-Datei ausgegeben</span><span class="sxs-lookup"><span data-stu-id="a2ba8-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="a2ba8-115">Anzeigeeinstellungen vorne im Raum</span><span class="sxs-lookup"><span data-stu-id="a2ba8-115">Front of Room Display Settings</span></span>
<span data-ttu-id="a2ba8-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="a2ba8-116"></span></span>

<span data-ttu-id="a2ba8-117">Konfigurieren Sie den Bildschirm vorne im Raum für den Modus „Erweitert“.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="a2ba8-118">Auf diese Weise wird sichergestellt, dass die Konsolen-Benutzeroberfläche nicht auf dieser Anzeige dupliziert wird, wenn Sie die Anzeige auf dem Bildschirm ausschalten.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-118">Doing so will ensure that the console UI is not duplicated on that display when you cycle power on the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a2ba8-119">Ein Consumer-TV, der als eine Anzeige vorne im Raum verwendet wird, muss das Feature „Consumer Electronics Control (CEC)“ von HDMI unterstützen/aktivieren, sodass ein automatischer Wechsel zu einer aktiven Videoquelle aus dem Standbymodus möglich ist.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-119">A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode.</span></span> <span data-ttu-id="a2ba8-120">Dieses Feature wird nicht auf allen TVs unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-120">This feature is not supported on all TVs.</span></span> 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a><span data-ttu-id="a2ba8-121">Microsoft Teams rooms Reset (Factory Restore)</span><span class="sxs-lookup"><span data-stu-id="a2ba8-121">Microsoft Teams Rooms Reset (Factory Restore)</span></span>
<span data-ttu-id="a2ba8-122"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="a2ba8-122"></span></span>

<span data-ttu-id="a2ba8-123">Wenn die Microsoft Teams-Räume nicht gut ausgeführt werden, kann es hilfreich sein, einen Factory-Reset durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-123">If Microsoft Teams Rooms isn't running well, performing a factory reset might help.</span></span> <span data-ttu-id="a2ba8-124">Dies kann in der Einstellungs-APP auf der Registerkarte " **Wiederherstellung** " erfolgen. Klicken Sie unter " **diesen PC zurücksetzen**" auf " **Erste Schritte**" und dann auf " **Alle entfernen**".</span><span class="sxs-lookup"><span data-stu-id="a2ba8-124">This can be done in the Settings app on the **Recovery** tab. Beneath **Reset this PC**, select **Get started**, and then **Remove everything**.</span></span> <span data-ttu-id="a2ba8-125">Folgen Sie den restlichen Eingabeaufforderungen, um das Gerät zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-125">Follow the remaining prompts to reset the device.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a2ba8-126">Es gibt ein bekanntes Problem, bei dem die Microsoft Teams-Räume unbrauchbar werden können, wenn die Option **meine Dateien beibehalten-apps und Einstellungen entfernt, aber Ihre persönlichen Dateien beibehalten** aktiviert ist, während des Windows-Reset-Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-126">There is a known issue where the Microsoft Teams Rooms can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="a2ba8-127">Verwenden Sie diese Option _nicht_ .</span><span class="sxs-lookup"><span data-stu-id="a2ba8-127">Do _not_ use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="a2ba8-128">Unterstützte Remoteoptionen</span><span class="sxs-lookup"><span data-stu-id="a2ba8-128">Supported Remote Options</span></span>
<span data-ttu-id="a2ba8-129"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="a2ba8-129"></span></span>

<span data-ttu-id="a2ba8-130">In der folgenden Tabelle sind die möglichen Remotevorgänge und die Methoden zusammengefasst, die Sie für diese Vorgänge verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-130">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="a2ba8-131">\*\*Arbeitsgruppe \*\*</span><span class="sxs-lookup"><span data-stu-id="a2ba8-131">**Workgroup**</span></span>|<span data-ttu-id="a2ba8-132">**Nicht Mitglied einer Domäne**</span><span class="sxs-lookup"><span data-stu-id="a2ba8-132">**Not domain joined**</span></span>|<span data-ttu-id="a2ba8-133">**Mitglied einer Domäne**</span><span class="sxs-lookup"><span data-stu-id="a2ba8-133">**Domain joined**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a2ba8-134">Neustart</span><span class="sxs-lookup"><span data-stu-id="a2ba8-134">Restart</span></span>  <br/> |<span data-ttu-id="a2ba8-135">Remotedesktop</span><span class="sxs-lookup"><span data-stu-id="a2ba8-135">Remote desktop</span></span>  <br/> <span data-ttu-id="a2ba8-136">Remote-Powershell</span><span class="sxs-lookup"><span data-stu-id="a2ba8-136">Remote Powershell</span></span>  <br/> |<span data-ttu-id="a2ba8-137">Remote Desktop (erfordert weitere Konfiguration)</span><span class="sxs-lookup"><span data-stu-id="a2ba8-137">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="a2ba8-138">Remote-PowerShell (weitere Konfiguration erforderlich)</span><span class="sxs-lookup"><span data-stu-id="a2ba8-138">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="a2ba8-139">SCCM</span><span class="sxs-lookup"><span data-stu-id="a2ba8-139">SCCM</span></span>  <br/> |
|<span data-ttu-id="a2ba8-140">Betriebssystemupdate</span><span class="sxs-lookup"><span data-stu-id="a2ba8-140">Update OS</span></span>  <br/> |<span data-ttu-id="a2ba8-141">Windows Update</span><span class="sxs-lookup"><span data-stu-id="a2ba8-141">Windows Update</span></span>  <br/> |<span data-ttu-id="a2ba8-142">Windows Update</span><span class="sxs-lookup"><span data-stu-id="a2ba8-142">Windows Update</span></span>  <br/> <span data-ttu-id="a2ba8-143">WSUS</span><span class="sxs-lookup"><span data-stu-id="a2ba8-143">WSUS</span></span>  <br/> |
|<span data-ttu-id="a2ba8-144">App-Update</span><span class="sxs-lookup"><span data-stu-id="a2ba8-144">App update</span></span>  <br/> |<span data-ttu-id="a2ba8-145">Windows Store</span><span class="sxs-lookup"><span data-stu-id="a2ba8-145">Windows Store</span></span>  <br/> |<span data-ttu-id="a2ba8-146">Windows Store</span><span class="sxs-lookup"><span data-stu-id="a2ba8-146">Windows Store</span></span>  <br/> <span data-ttu-id="a2ba8-147">SCCM</span><span class="sxs-lookup"><span data-stu-id="a2ba8-147">SCCM</span></span>  <br/> |
|<span data-ttu-id="a2ba8-148">Skype-Kontokonfiguration</span><span class="sxs-lookup"><span data-stu-id="a2ba8-148">Skype Account Config</span></span>  <br/> |<span data-ttu-id="a2ba8-149">Zurzeit nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="a2ba8-149">Not currently supported</span></span>  <br/> |<span data-ttu-id="a2ba8-150">Zurzeit nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="a2ba8-150">Not currently supported</span></span>  <br/> |
|<span data-ttu-id="a2ba8-151">Zugriff auf Protokolle</span><span class="sxs-lookup"><span data-stu-id="a2ba8-151">Access logs</span></span>  <br/> |<span data-ttu-id="a2ba8-152">Zurzeit nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="a2ba8-152">Not currently supported</span></span>  <br/> |<span data-ttu-id="a2ba8-153">Zurzeit nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="a2ba8-153">Not currently supported</span></span>  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a><span data-ttu-id="a2ba8-154">Konfigurieren von Gruppenrichtlinien für Microsoft Teams-Chatrooms</span><span class="sxs-lookup"><span data-stu-id="a2ba8-154">Configuring Group Policy for Microsoft Teams Rooms</span></span>
<span data-ttu-id="a2ba8-155"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="a2ba8-155"></span></span>

<span data-ttu-id="a2ba8-156">Dieser Abschnitt behandelt die Systemeinstellungen, von denen Microsoft Teams-Räume abhängig sind, um ordnungsgemäß zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-156">This section covers system settings that Microsoft Teams Rooms depends on to function properly.</span></span> <span data-ttu-id="a2ba8-157">Wenn Sie Microsoft Teams-Räumen eine Domäne hinzugefügt haben, stellen Sie sicher, dass Ihre Gruppenrichtlinie die Einstellungen in der folgenden Tabelle nicht außer Kraft setzt.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-157">When joining Microsoft Teams Rooms to a domain, ensure that your group policy doesn't override the settings in the following table.</span></span>
  

|<span data-ttu-id="a2ba8-158">**Einstellung**</span><span class="sxs-lookup"><span data-stu-id="a2ba8-158">**Setting**</span></span>|<span data-ttu-id="a2ba8-159">**Ermöglicht**</span><span class="sxs-lookup"><span data-stu-id="a2ba8-159">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a2ba8-160">HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span><span class="sxs-lookup"><span data-stu-id="a2ba8-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span></span>  <br/> |<span data-ttu-id="a2ba8-161">Ermöglicht das Starten von Microsoft Teams-Räumen</span><span class="sxs-lookup"><span data-stu-id="a2ba8-161">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="a2ba8-162">Power Management-\> auf AC, schalten Sie den Bildschirm nach 10 Minuten aus.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-162">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="a2ba8-163">Power Management-\> auf AC, niemals System in den Standbymodus versetzen</span><span class="sxs-lookup"><span data-stu-id="a2ba8-163">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="a2ba8-164">Ermöglicht Microsoft Teams-Räumen, die angefügten anzeigen zu deaktivieren und automatisch zu aktivieren</span><span class="sxs-lookup"><span data-stu-id="a2ba8-164">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="a2ba8-165">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="a2ba8-165">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="a2ba8-166">Oder entsprechende Möglichkeit zum Deaktivieren des Kennwortablaufs für das lokale Konto.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-166">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="a2ba8-167">Wird dies nicht ausgeführt, kann bei der Anmeldung des Skype-Kontos aufgrund eines abgelaufenen Kennworts ein Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-167">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="a2ba8-168">Beachten Sie, dass sich dies auf alle lokalen Konten auf dem Computer auswirkt, sodass bei Nichtfestlegung dieser Einstellung auch das Administratorkonto ablaufen kann.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-168">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="a2ba8-169">Ermöglicht die ständige Anmeldung des Skype-Kontos</span><span class="sxs-lookup"><span data-stu-id="a2ba8-169">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="a2ba8-170">Das Übertragen von Dateien mithilfe von Gruppenrichtlinien wird unter [Konfigurieren eines Dateielements](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)erläutert.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-170">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="a2ba8-171">Wenn das Gerät von Microsoft Teams Rooms mit der nächsten Version von Windows 10 kompatibel ist, wird das Gerät automatisch auf die nächste Version über Windows Update aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-171">When Microsoft Teams Rooms device is compatible with the next version of Windows 10 OS, the device automatically updates to the next version through Windows Update.</span></span> <span data-ttu-id="a2ba8-172">Microsoft Teams rooms-Gerät sollte nicht manuell auf die nächste Version von Windows 10 aktualisiert werden oder über die Aktivierung von Windows Update for Business (WUFB)-Gruppenrichtlinien "wählen Sie die Windows-Bereitschaftsstufe für die Updates aus, die Sie empfangen möchten" und "wählen Sie aus, wann die Vorschau erstellt und Funktions Updates werden über das Gruppenrichtlinienobjekt empfangen.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-172">Microsoft Teams Rooms device should not be upgraded to next release of Windows 10 manually or via enabling Windows Update for Business (WUFB) group policies “Select the Windows readiness level for the updates you want to receive” and "Select when Preview Builds and Feature Updates are received" through GPO.</span></span> <span data-ttu-id="a2ba8-173">Auf einem Gerät mit aktivierten Gruppenrichtlinien ist bekannt, dass es Probleme mit dem Windows 10-Betriebssystemupdate durch die Microsoft Teams rooms-App gibt.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-173">A device with these group policies enabled is known to run into issues with Windows 10 OS update by Microsoft Teams Rooms app.</span></span>

## <a name="remote-management-using-powershell"></a><span data-ttu-id="a2ba8-174">Remoteverwaltung mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2ba8-174">Remote Management using PowerShell</span></span>
<span data-ttu-id="a2ba8-175"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="a2ba8-175"></span></span>

<span data-ttu-id="a2ba8-176">Sie können die folgenden Verwaltungsvorgänge Remote mithilfe von PowerShell ausführen (in der folgenden Tabelle finden Sie Skriptbeispiele):</span><span class="sxs-lookup"><span data-stu-id="a2ba8-176">You can perform the following management operations remotely by using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="a2ba8-177">Abrufen von angeschlossenen Geräten</span><span class="sxs-lookup"><span data-stu-id="a2ba8-177">Get attached devices</span></span>
    
- <span data-ttu-id="a2ba8-178">Abrufen des App-Status</span><span class="sxs-lookup"><span data-stu-id="a2ba8-178">Get app status</span></span>
    
- <span data-ttu-id="a2ba8-179">Abrufen von Systeminformationen</span><span class="sxs-lookup"><span data-stu-id="a2ba8-179">Get system info</span></span>
    
- <span data-ttu-id="a2ba8-180">Neustart des Systems</span><span class="sxs-lookup"><span data-stu-id="a2ba8-180">Reboot system</span></span>
    
- <span data-ttu-id="a2ba8-181">Abrufen von Protokollen</span><span class="sxs-lookup"><span data-stu-id="a2ba8-181">Retrieve logs</span></span>
    
- <span data-ttu-id="a2ba8-182">Übertragen von Dateien (erfordert einen Domänenbeitritt zu Microsoft Teams-Räumen)</span><span class="sxs-lookup"><span data-stu-id="a2ba8-182">Transfer files (requires a domain-joined Microsoft Teams Rooms)</span></span>
    
> [!NOTE]
> <span data-ttu-id="a2ba8-183">Diese Funktion ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-183">This functionality is off by default.</span></span> <span data-ttu-id="a2ba8-184">Sie müssen die Remote-PowerShell für Ihre Umgebung im Microsoft Teams rooms-System aktivieren, um die folgenden Vorgänge auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-184">You need to enable remote PowerShell for your environment on the Microsoft Teams Rooms system to perform the operations below.</span></span> <span data-ttu-id="a2ba8-185">Informationen zum Aktivieren von Remote-PowerShell finden Sie in der Dokumentation zu **[enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** .</span><span class="sxs-lookup"><span data-stu-id="a2ba8-185">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** for information about how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="a2ba8-186">Sie können Remote-PowerShell beispielsweise wie folgt aktivieren:</span><span class="sxs-lookup"><span data-stu-id="a2ba8-186">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="a2ba8-187">Anmelden als Administrator auf einem Microsoft Teams rooms-Gerät.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-187">Sign in as Admin on a Microsoft Teams Rooms device.</span></span>
    
2. <span data-ttu-id="a2ba8-188">Öffnen Sie eine erweiterte PowerShell-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-188">Open an elevated PowerShell command prompt.</span></span>
    
3. <span data-ttu-id="a2ba8-189">Geben Sie den folgenden Befehl ein: Enable-PSRemoting -force</span><span class="sxs-lookup"><span data-stu-id="a2ba8-189">Enter the following command: Enable-PSRemoting -force</span></span>
    
<span data-ttu-id="a2ba8-190">So führen Sie einen Verwaltungsvorgang durch:</span><span class="sxs-lookup"><span data-stu-id="a2ba8-190">To perform a management operation:</span></span>
  
1. <span data-ttu-id="a2ba8-191">Melden Sie sich bei einem PC mit Kontoanmeldeinformationen an, die über die Berechtigung zum Ausführen von PowerShell-Befehlen auf einem Microsoft Teams rooms-Gerät verfügen.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-191">Sign in to a PC with account credentials that have permission to run PowerShell commands on a Microsoft Teams Rooms device.</span></span>
    
2. <span data-ttu-id="a2ba8-192">Öffnen Sie eine reguläre PowerShell-Eingabeaufforderung auf dem PC.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-192">Open a regular PowerShell command prompt on the PC.</span></span>
    
3. <span data-ttu-id="a2ba8-193">Kopieren Sie den Befehlstext aus der folgenden Tabelle, und fügen Sie ihn an der Eingabeaufforderung ein.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-193">Copy the command text from the table below and paste it at the prompt.</span></span>
    
4. <span data-ttu-id="a2ba8-194">Ersetzen `<Device fqdn>` Sie Felder durch FQDN-Werte, die für Ihre Umgebung geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-194">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
    
5. <span data-ttu-id="a2ba8-195">Ersetzen \* \<Sie\> Path\* durch den Dateinamen und den lokalen Pfad der Master-SkypeSettings. XML-Konfigurationsdatei (oder des Design Bilds).</span><span class="sxs-lookup"><span data-stu-id="a2ba8-195">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="a2ba8-196">So erhalten Sie angefügte Geräte</span><span class="sxs-lookup"><span data-stu-id="a2ba8-196">To Get Attached Devices</span></span>
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="a2ba8-197">Abrufen des App-Status</span><span class="sxs-lookup"><span data-stu-id="a2ba8-197">Get App Status</span></span>
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="a2ba8-198">Abrufen von Systeminformationen</span><span class="sxs-lookup"><span data-stu-id="a2ba8-198">Get System Info</span></span>
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="a2ba8-199">Neustart des Systems</span><span class="sxs-lookup"><span data-stu-id="a2ba8-199">Reboot System</span></span>
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="a2ba8-200">Abrufen von Protokollen</span><span class="sxs-lookup"><span data-stu-id="a2ba8-200">Retrieve Logs</span></span>
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="a2ba8-201">Pushen einer XML-Konfigurationsdatei (oder Design Grafik)</span><span class="sxs-lookup"><span data-stu-id="a2ba8-201">Push an XML configuration file (or theme graphic)</span></span>
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="a2ba8-202">Softwareupdates</span><span class="sxs-lookup"><span data-stu-id="a2ba8-202">Software updates</span></span>
<span data-ttu-id="a2ba8-203"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="a2ba8-203"></span></span>

<span data-ttu-id="a2ba8-204">Standardmäßig versucht Microsoft Teams rooms, eine Verbindung mit dem Windows Store herzustellen, um die neueste Version der Microsoft Teams Rooms-Software abzurufen, damit das Gerät normalen Internetzugriff benötigt.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-204">By default, Microsoft Teams Rooms attempts to connect to the Windows Store to get the latest version of Microsoft Teams Rooms software, so the device will require regular internet access.</span></span> <span data-ttu-id="a2ba8-205">Bevor Sie sich mit Microsoft mit Supportproblemen in Verbindung setzen, stellen Sie sicher, dass das Gerät Microsoft Teams Rooms mit der neuesten Version der App geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-205">Before contacting Microsoft with support issues, be sure the Microsoft Teams Rooms device is loaded with the latest version of the app.</span></span>
  
<span data-ttu-id="a2ba8-206">Standardmäßig stellt Microsoft Teams rooms eine Verbindung mit Windows Update her, um Betriebssystem-und USB-Peripheriegeräte-Firmware-Aktualisierungen abzurufen und außerhalb der konfigurierten Geschäftszeiten zu installieren.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-206">By default, Microsoft Teams Rooms connects to Windows Update to retrieve operating system and USB peripheral device firmware updates, and installs them outside of configured business hours.</span></span> <span data-ttu-id="a2ba8-207">Sie können Geschäftszeiten konfigurieren, indem Sie sich beim Administratorkonto anmelden und die Einstellungen-App ausführen.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-207">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="a2ba8-208">Wenn Sie Updates manuell verwalten möchten und dem normalen Verfahren für [Microsoft Store for Business](https://businessstore.microsoft.com/store) zum [Verteilen von Offline-Apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)nicht folgen können, können Sie die entsprechende APPX-Datei und-Abhängigkeiten aus dem [Deployment Kit](https://go.microsoft.com/fwlink/?linkid=851168) erwerben (von die Anweisungen zum [Konfigurieren einer Microsoft Teams rooms-Konsole](console.md)), die mit SCCM verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-208">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/store) to [Distribute offline apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Microsoft Teams Rooms console](console.md)) that can be used with SCCM.</span></span> <span data-ttu-id="a2ba8-209">Das Deployment Kit-Release hinkt hinter der Store-Version zurück, daher ist es möglicherweise nicht immer mit dem neuesten verfügbaren Build identisch.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-209">The deployment kit release lags behind the store release, so it might not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="a2ba8-210">So aktualisieren Sie die Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2ba8-210">To update using Powershell</span></span>

1. <span data-ttu-id="a2ba8-211">Extrahieren Sie das Paket aus der [MSI](https://go.microsoft.com/fwlink/?linkid=851168) -Installationsdatei auf eine Freigabe, auf die das Gerät zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-211">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a share the device can access.</span></span>
    
2. <span data-ttu-id="a2ba8-212">Führen Sie das folgende Skript aus, das auf die Microsoft Teams \<rooms\> -Geräte ausgerichtet ist, und ändern Sie die Freigabe auf die Gerätefreigabe nach Bedarf:</span><span class="sxs-lookup"><span data-stu-id="a2ba8-212">Run the following script targeting the Microsoft Teams Rooms devices, changing \<share\> to the device share as appropriate:</span></span>
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="a2ba8-213">Administratormodus und Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="a2ba8-213">Admin mode and device management</span></span>
<span data-ttu-id="a2ba8-214"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="a2ba8-214"></span></span>

<span data-ttu-id="a2ba8-215">Einige Verwaltungsfunktionen, wie das manuelle Installieren eines privaten Zertifizierungsstellenzertifikats, erfordern das Platzieren des Surface pro-Geräts im Administratormodus.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-215">Some management functions, like manually installing a private CA certificate, require placing the Surface Pro device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a><span data-ttu-id="a2ba8-216">Wechseln zum Administratormodus und zurück, wenn die Microsoft Teams rooms-app ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="a2ba8-216">Switching to Admin Mode and back when the Microsoft Teams Rooms app is running</span></span>

1. <span data-ttu-id="a2ba8-217">Beenden Sie alle laufenden Anrufe, und kehren Sie zum Startbildschirm zurück.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-217">Hang up any ongoing calls, and return to the home screen.</span></span>
    
2. <span data-ttu-id="a2ba8-218">Wählen Sie das Zahnradsymbol aus, und öffnen Sie das Menü (Optionen sind **Einstellungen**, **Barrierefreiheit**und **Gerät neu starten** ).</span><span class="sxs-lookup"><span data-stu-id="a2ba8-218">Select the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
    
3. <span data-ttu-id="a2ba8-219">Wählen Sie **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-219">Select **Settings**.</span></span>
    
4. <span data-ttu-id="a2ba8-220">Geben Sie das Administratorkennwort ein.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-220">Enter the Administrator Password.</span></span> <span data-ttu-id="a2ba8-221">Der Setupbildschirm wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-221">The Setup screen will appear.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a2ba8-222">Wenn das Gerät nicht mit der Domäne verbunden ist, wird standardmäßig das lokale Administratorkonto (Benutzername "Administrator") verwendet.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-222">If the device isn't domain-joined, the local administrative account (username "Admin") will be used by default.</span></span> <span data-ttu-id="a2ba8-223">Das Standardkennwort für dieses Konto ist "SFB", es wird jedoch empfohlen, dass Ihre Organisation dies aus Sicherheitsgründen so schnell wie möglich ändert.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-223">The default password for this account is 'sfb' but it is recommended that your organization change this for security reasons as soon as possible.</span></span> <span data-ttu-id="a2ba8-224">Wenn der Computer mit einer Domäne verbunden ist, können Sie sich mit einem entsprechend privilegierten Domänenkonto anmelden.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-224">If the machine is domain-joined, you can sign in with an appropriately privileged domain account.</span></span> 
  
5. <span data-ttu-id="a2ba8-225">Wählen Sie in der linken Spalte **Windows-Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-225">Select **Windows Settings** in the left column.</span></span>
    
6. <span data-ttu-id="a2ba8-226">Wählen Sie **Zu Administratoranmeldung wechseln** aus.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-226">Choose **Go to Admin Sign-in**.</span></span>
    
7. <span data-ttu-id="a2ba8-227">Geben Sie das Administratorkennwort ein.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-227">Enter the Administrator Password.</span></span> <span data-ttu-id="a2ba8-228">Daraufhin wird die App ordnungsgemäß abgemeldet, und Sie gelangen zum Windows-Anmeldebildschirm.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-228">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
    
8. <span data-ttu-id="a2ba8-229">Melden Sie sich mit Ihren Administratoranmeldeinformationen beim Desktop an.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-229">Log in to the desktop with your administrative credentials.</span></span> <span data-ttu-id="a2ba8-230">Sie verfügen über die erforderlichen Berechtigungen zum Verwalten des Geräts.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-230">You'll have the necessary privileges to manage the device.</span></span>
    
9. <span data-ttu-id="a2ba8-231">Führen Sie die notwendigen Administratoraufgaben aus.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-231">Perform the necessary administrative tasks.</span></span>
    
10. <span data-ttu-id="a2ba8-232">Melden Sie sich bei Ihrem Administratorkonto ab.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-232">Sign out from the Admin account.</span></span>
    
11. <span data-ttu-id="a2ba8-233">Kehren Sie zu Microsoft Teams rooms zurück, indem Sie auf der linken Seite des Bildschirms das Symbol für das Benutzerkonto auswählen und dann **Skype**auswählen.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-233">Return to Microsoft Teams Rooms by selecting the user account icon on the far left side of the screen and then selecting **Skype**.</span></span>
    
    <span data-ttu-id="a2ba8-234">Wenn der **Skype** -Nutzer nicht aufgeführt ist, müssen Sie möglicherweise einen **anderen Benutzer** auswählen und **.\skype** als Benutzernamen eingeben und sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-234">If the **Skype** user is not listed, you might have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
<span data-ttu-id="a2ba8-235">Die Konsole befindet sich nun wieder im normalen Betriebsmodus. Das folgende Verfahren setzt voraus, dass Sie eine Tastatur an das Gerät anfügen, wenn noch keines angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-235">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a><span data-ttu-id="a2ba8-236">Wechseln zum Administratormodus und zurück, wenn die Microsoft Teams rooms-App abstürzt</span><span class="sxs-lookup"><span data-stu-id="a2ba8-236">Switching to Admin Mode and back when the Microsoft Teams Rooms app crashes</span></span>

1. <span data-ttu-id="a2ba8-237">Drücken Sie fünf Mal schnell hintereinander die WINDOWS-TASTE.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-237">Press the Windows key five times in rapid succession.</span></span> <span data-ttu-id="a2ba8-238">Daraufhin gelangen Sie zum Windows-Anmeldebildschirm.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-238">This will bring you to the Windows logon screen.</span></span> 
    
2. <span data-ttu-id="a2ba8-239">Melden Sie sich mit Ihren Administratoranmeldeinformationen beim Desktop an.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-239">Log in to the desktop with your administrative credentials.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a2ba8-240">Bei dieser Methode wird der Skype-Benutzer nicht abgemeldet oder die APP nicht ordnungsgemäß beendet, aber Sie würden ihn verwenden, wenn die APP nicht antwortete und die andere Methode nicht verfügbar war.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-240">This method doesn't log the Skype user off or gracefully terminate the app, but you'd use it if the app wasn't responding and the other method wasn't available.</span></span> 
  
3. <span data-ttu-id="a2ba8-241">Führen Sie die notwendigen Administratoraufgaben aus.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-241">Perform the necessary administrative tasks.</span></span>
    
4. <span data-ttu-id="a2ba8-242">Starten Sie den Computer neu, wenn Sie fertig sind.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-242">Restart the machine when you're finished.</span></span>
    
   <span data-ttu-id="a2ba8-243">Die Konsole wird im normalen Betriebsmodus neu gestartet, wobei die Microsoft Teams rooms-app ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-243">The console restarts into its normal operation mode, running the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="a2ba8-244">Sie können die Tastatur entfernen, wenn Sie angefügt wurde, um dieses Verfahren ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-244">You can remove the keyboard, if it was attached to allow you to perform this procedure.</span></span>
   ## <a name="troubleshooting-tips"></a><span data-ttu-id="a2ba8-245">Tipps zur Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="a2ba8-245">Troubleshooting tips</span></span>
   <span data-ttu-id="a2ba8-246"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="a2ba8-246"></span></span>

- <span data-ttu-id="a2ba8-247">Besprechungseinladungen werden möglicherweise nicht angezeigt, wenn Sie über Domänengrenzen hinweg gesendet werden (beispielsweise zwischen zwei Unternehmen).</span><span class="sxs-lookup"><span data-stu-id="a2ba8-247">Meeting invitations might not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="a2ba8-248">In solchen Fällen sollten IT-Administratoren entscheiden, ob Sie externen Benutzern das Planen einer Besprechung gestatten möchten.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-248">In such cases, IT admins should decide whether to allow external users to schedule a meeting.</span></span>
    
- <span data-ttu-id="a2ba8-249">Microsoft Teams rooms unterstützt keine Exchange-Auto Ermittlungs Umleitungen über Exchange 2010.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-249">Microsoft Teams Rooms doesn't support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
    
- <span data-ttu-id="a2ba8-250">Im Allgemeinen empfiehlt es sich, dass IT-Administratoren alle audiopunkte deaktivieren, die Sie nicht verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-250">In general, it's a good practice for IT admins to disable any audio endpoints they don't intend to use.</span></span>
    
- <span data-ttu-id="a2ba8-251">Falls ein Spiegelbild in der Raumvorschau angezeigt wird, kann der IT-Administrator dies korrigieren, indem die Stromversorgung der Kamera angestellt wird oder die Bildausrichtung mit der Fernsteuerung der Kamera gekippt wird.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-251">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
    
- <span data-ttu-id="a2ba8-252">Es ist bekannt, dass der Zugang zum Konsolentouchscreen verloren gehen kann.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-252">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="a2ba8-253">In diesem Fall wird das Problem manchmal durch einen Neustart des Microsoft Teams rooms-Systems behoben.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-253">In such cases, the issue is sometimes resolved by restarting the Microsoft Teams Rooms system.</span></span>
    
- <span data-ttu-id="a2ba8-254">Beim Verbinden eines PCs mit der Konsole über verkabelte Erfassung kann ein Verlust der lokalen Audiodaten auftreten.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-254">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="a2ba8-255">Das Problem mit der Wiedergabe der lokalen Audiodaten kann in diesem Fall durch einen Neustart des PCs gelöst werden.</span><span class="sxs-lookup"><span data-stu-id="a2ba8-255">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    
