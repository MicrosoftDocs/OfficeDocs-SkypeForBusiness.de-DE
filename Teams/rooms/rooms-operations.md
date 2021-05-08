---
title: Microsoft Teams-Räume und Vorgänge
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: In diesem Thema erfahren Sie mehr über die Verwaltung Microsoft Teams-Räume, der nächsten Generation Skype Raumsysteme.
ms.openlocfilehash: 52234f72c380c4f5af8f47fff51998fa8c3d1459
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117433"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Microsoft Teams-Räume und Vorgänge 
 
In diesem Thema erfahren Sie mehr über die Verwaltung Microsoft Teams-Räume, der nächsten Generation Skype Raumsysteme.
  
Microsoft Teams-Räume ist die neueste Konferenzlösung von Microsoft, mit der Sie Ihren Besprechungsraum in eine umfassende, zusammenarbeitsreiche Umgebung verwandeln können. Die Benutzer werden von der vertrauten Benutzeroberfläche Microsoft Teams der Skype for Business profitieren, und IT-Administratoren werden eine einfach bereitgestellte und verwaltete App Windows 10 Skype-Besprechung schätzen. Microsoft Teams-Räume ist so konzipiert, dass vorhandene Geräte wie BEISPIELSWEISE-PANELS für eine einfache Installation genutzt werden können, um Microsoft Teams oder Skype for Business In Besprechungsraum zu bringen.
  
Mit zusätzlicher Konfiguration ist die Remoteverwaltung mithilfe des Microsoft Azure-Monitors möglich, wie unter Planen der [Microsoft Teams-Räume-Verwaltung](azure-monitor-plan.md)mit Azure Monitor , Bereitstellen der Microsoft Teams-Räume-Verwaltung mit [Azure Monitor](azure-monitor-deploy.md)und Verwalten von Microsoft Teams-Räume-Geräten mit [Azure Monitor](azure-monitor-deploy.md)beschrieben. Sie können die Konsoleneinstellungen Microsoft Teams-Räume auch remote mit einer [XML-Konfigurationsdatei](xml-config-file.md)verwalten, die das Anwenden eines benutzerdefinierten Anzeigedesigns umfasst. 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Sammeln von Protokollen für Microsoft Teams-Räume
<a name="Logs"> </a>

Zum Erfassen von Protokollen müssen Sie das Protokollsammlungsskript aufrufen, das in der App Microsoft Teams-Räume wird. Starten Sie im Administratormodus eine Eingabeaufforderung mit erhöhten Rechten, und gibt den folgenden Befehl aus:
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Die Protokolle werden als ZIP-Datei in "c:\rigel" ausgegeben.
  
## <a name="front-of-room-display-settings"></a>Anzeigeeinstellungen vorne im Raum
<a name="Display"> </a>

Konfigurieren Sie den Bildschirm vorne im Raum für den Modus „Erweitert“. Dadurch wird sichergestellt, dass die Konsolen-UI auf dieser Anzeige nicht dupliziert wird, wenn der Strom auf dem Display ein/aus geht.
  
> [!NOTE]
> Wenn Sie möchten, dass die Anzeige vor dem Raum automatisch zu einer aktiven Videoquelle (z. B. einer MTR-Konsole) wechselt, wenn die Quelle aus dem Standbymodus reaktiviert wird, müssen bestimmte Bedingungen erfüllt sein. Dieses Feature ist optional, wird aber von Microsoft Teams-Räume unterstützt, sofern die zugrunde liegende Hardware das Feature unterstützt. Ein Consumer-TV, das als Front-Of-Room-Anzeige verwendet wird, muss die HDMI-Funktion (Consumer Electronics Control) für Consumer Electronics Control (CEC) unterstützen.  Je nach ausgewählter Docking-Station oder Konsole (die CEC möglicherweise nicht unterstützt, finden Sie in der Dokumentation zum Support des Herstellers) kann ein Controller wie [HD-TX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) von Crestron oder [Exppe HD CTL 100](https://www.extron.com/article/hdctl100ad) von Ex selbst erforderlich sein, um das gewünschte Verhalten zu ermöglichen. 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Microsoft Teams-Räume Zurücksetzen (Werkswiederherstellung)
<a name="Reset"> </a>

Wenn Microsoft Teams-Räume nicht gut ausgeführt wird, kann ein Zurücksetzen auf Werkseinstellungen hilfreich sein. Verwenden Sie dazu [](recovery-tool.md) das Tool Microsoft Teams Raumwiederherstellungstool, und folgen Sie den Anweisungen zur Wiederherstellung auf Werkseinstellungen.

> [!NOTE]
> Es gibt ein bekanntes Problem, bei dem das Microsoft Teams-Räume nicht mehr verwendet werden kann, wenn die Option Meine Dateien behalten – Apps und Einstellungen entfernen, aber ihre persönlichen Dateien beibehalten während des **Vorgangs** "Zurücksetzen Windows aktiviert ist. Verwenden *Sie* diese Option nicht.
  
## <a name="supported-remote-options"></a>Unterstützte Remoteoptionen
<a name="RemoteOptions"> </a>

In der folgenden Tabelle sind die möglichen Remotevorgänge und die Methoden zusammengefasst, die Sie für diese Vorgänge verwenden können.
  

|Arbeitsgruppe |Nicht Mitglied einer Domäne|Mitglied einer Domäne|
|:-----|:-----|:-----|
|Neustart  <br/> |Teams Admin Center  <br/> Remotedesktop  <br/> Remote-Powershell  <br/> | <br/>Remotedesktop (erfordert weitere Konfiguration)  <br/> Remote-Powershell (erfordert weitere Konfiguration)  <br/> Configuration Manager  <br/> |
|Betriebssystemupdate  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|App-Update  <br/> |Windows Store  <br/> |Windows Store  <br/> Configuration Manager  <br/> |
|Kontokonfiguration  <br/> |Teams Admin Center  <br/> |Teams Admin Center  <br/> |
|Zugriff auf Protokolle  <br/> |Teams Admin Center  <br/> |Teams Admin Center <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Konfigurieren von Gruppenrichtlinien für Microsoft Teams-Räume
<a name="GroupPolicy"> </a>

Dieser Abschnitt befasst sich mit den Systemeinstellungen, Microsoft Teams-Räume, damit sie ordnungsgemäß funktionieren. Stellen Sie beim Microsoft Teams-Räume einer Domäne sicher, dass Ihre Gruppenrichtlinie die Einstellungen in der folgenden Tabelle nicht außer Kraft setzt.
  

|Einstellung|Lässt zu|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Ermöglicht Microsoft Teams-Räume starten  <br/> |
|Power Management – \> Netzstrom, Bildschirm nach 10 Minuten ausschalten  <br/> Power Management – \> Schalten Sie die Stromversorgung ein, und legen Sie das System nie in den Ruhezustand  <br/> |Ermöglicht Microsoft Teams-Räume, angefügte Anzeigen auszuschalten und automatisch zu reaktivierungen.  <br/> |
|net accounts /maxpwage:unlimited  <br/> Oder entsprechende Möglichkeit zum Deaktivieren des Kennwortablaufs für das lokale Konto. Wird dies nicht ausgeführt, kann bei der Anmeldung des Skype-Kontos aufgrund eines abgelaufenen Kennworts ein Fehler auftreten. Beachten Sie, dass sich dies auf alle lokalen Konten auf dem Computer auswirkt, sodass bei Nichtfestlegung dieser Einstellung auch das Administratorkonto ablaufen kann.   <br/> |Ermöglicht die ständige Anmeldung des Skype-Kontos  <br/> |
   
Das Übertragen von Dateien mithilfe von Gruppenrichtlinien wird unter [Konfigurieren eines Dateielements erläutert.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772536(v=ws.11))

> [!NOTE]
> Wenn Microsoft Teams-Räume Gerät mit der nächsten Version von Windows 10 Os kompatibel ist, wird das Gerät über Windows Update automatisch auf die Windows aktualisiert. Microsoft Teams-Räume-Gerät sollte nicht manuell oder über die Aktivierung der Gruppenrichtlinien von Windows Update for Business (WUFB) "Select the Windows readiness level for the updates you want to receive" oder "Select when Preview Builds and Feature Updates are received" (Auswählen, wann Vorschaubuilds und Featureupdates empfangen werden) über das Gruppenrichtlinienobjekt auf die nächste Version von Windows 10 aktualisiert werden. Bei einem Gerät mit diesen Gruppenrichtlinien ist bekannt, dass es zu Problemen mit Windows 10 betriebssystemupdate einer Microsoft Teams-Räume kommt.

## <a name="remote-management-using-powershell"></a>Remoteverwaltung mit PowerShell
<a name="RemotePS"> </a>

Sie können die folgenden Verwaltungsvorgänge remote mithilfe von PowerShell ausführen (Skriptbeispiele finden Sie in der folgenden Tabelle):
  
- Abrufen von angeschlossenen Geräten
- Abrufen des App-Status
- Abrufen von Systeminformationen
- Neustart des Systems
- Abrufen von Protokollen
- Übertragen von Dateien (erfordert ein Domänen-Mitglied Microsoft Teams-Räume)
    
> [!NOTE]
> Diese Funktion ist standardmäßig deaktiviert. Sie müssen Remote-PowerShell für Ihre Umgebung auf dem Microsoft Teams-Räume aktivieren, um die folgenden Vorgänge ausführen zu können. Informationen zum Aktivieren von Remote-PowerShell finden Sie in der Dokumentation zum Aktivieren von **[PSRemoting.](/powershell/module/microsoft.powershell.core/enable-psremoting)**
  
Sie können Remote-PowerShell beispielsweise wie folgt aktivieren:
  
1. Melden Sie sich auf einem mobilen Microsoft Teams-Räume als Administrator an.
2. Öffnen Sie eine PowerShell-Eingabeaufforderung mit erhöhten Rechten.
3. Geben Sie den folgenden Befehl ein: `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. Öffnen Sie die lokale  Sicherheitsrichtlinie, und fügen Sie die Sicherheitsgruppe Administratoren zu Einstellungen Lokale Richtlinien Benutzerrechtezuweisung Zugriff auf diesen Computer  >    >    >  **aus dem Netzwerk hinzu.**

So führen Sie einen Verwaltungsvorgang durch:
  
1. Melden Sie sich bei einem PC mit Kontoanmeldeinformationen an, die über die Berechtigung zum Ausführen von PowerShell-Befehlen auf einem Microsoft Teams-Räume verfügen.
2. Öffnen Sie eine normale PowerShell-Eingabeaufforderung auf dem PC.
3. Kopieren Sie den Befehlstext aus der nachstehenden Tabelle, und fügen Sie ihn an der Eingabeaufforderung ein.
4. Ersetzen  `<Device fqdn>` Sie Felder durch FQDN-Werte, die Ihrer Umgebung angemessen sind.
5. Ersetzen  *\<path\>*  Sie die Datei durch den Dateinamen und lokalen Pfad der MasterSkypeSettings.xml konfigurationsdatei (oder designbild).
    
So erhalten Sie angefügte Geräte
  
```PowerShell
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

Abrufen des App-Status
  
```PowerShell
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

Abrufen von Systeminformationen
  
```PowerShell
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

Neustart des Systems
  
```PowerShell
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

Abrufen von Protokollen
  
```PowerShell
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

Push an XML-Konfigurationsdatei (oder Designgrafik)
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Softwareupdates
<a name="SWupdate"> </a>

Standardmäßig versucht Microsoft Teams-Räume, eine Verbindung mit der Windows Store herzustellen, um die neueste Version von Microsoft Teams-Räume-Software zu erhalten, sodass für das Gerät ein regulärer Internetzugang erforderlich ist. Stellen Sie vor dem Kontaktieren von Microsoft-Supportproblemen sicher, dass das Microsoft Teams-Räume-Gerät mit der neuesten Version der App geladen ist.
  
Standardmäßig stellt Microsoft Teams-Räume eine Verbindung mit Windows Update auf, um Firmwareupdates für Betriebssysteme und USB-Peripheriegeräte abzurufen, und installiert diese außerhalb der konfigurierten Geschäftszeiten. Sie können Geschäftszeiten konfigurieren, indem Sie sich beim Administratorkonto anmelden und die Einstellungen-App ausführen.
  
Wenn Sie Updates manuell verwalten möchten und nicht das normale Verfahren für [Microsoft Store für Unternehmen](https://businessstore.microsoft.com/store) zum Verteilen von [Offline-Apps](/microsoft-store/distribute-offline-apps)ausführen können, können Sie die entsprechende APPX-Datei und -Abhängigkeiten aus dem Bereitstellungskit [(aus](https://go.microsoft.com/fwlink/?linkid=851168) den Anweisungen unter Konfigurieren einer [Microsoft Teams-Räume-Konsole)](console.md)erwerben, die mit Configuration Manager verwendet werden kann. Da die Veröffentlichung des Bereitstellungskits hinter der Store-Version zurück liegt, passt es möglicherweise nicht immer zum neuesten verfügbaren Build.
  
### <a name="to-update-using-powershell"></a>So aktualisieren Sie ein Update mit Powershell

1. Extrahieren Sie das Paket aus der [MSI-Installations-MSI,](https://go.microsoft.com/fwlink/?linkid=851168) um eine Freigabe zu erhalten, auf die das Gerät zugreifen kann.
2. Führen Sie das folgende Skript für die Microsoft Teams-Räume aus, und ändern Sie die \<share\> Gerätefreigabe entsprechend:
    
    ```PowerShell
    Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
    ```

## <a name="admin-mode-and-device-management"></a>Administratormodus und Geräteverwaltung
<a name="AdminMode"> </a>

Einige Verwaltungsfunktionen, z. B. die manuelle Installation eines Zertifikats einer privaten Zertifizierungsstelle, erfordern das Platzieren Surface Pro Geräts im Administratormodus. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Wechseln in den Administratormodus und zurück, wenn die Microsoft Teams-Räume ausgeführt wird

1. Bleiben Sie bei laufenden Anrufen auf, und kehren Sie zum Startbildschirm zurück.
2. Wählen Sie das Zahnradsymbol aus, und öffnen Sie das Menü (Optionen **sind Einstellungen** **,** Bedienungshilfen und Gerät **neu starten** ).
3. Wählen Sie **Einstellungen** aus.
4. Geben Sie das Administratorkennwort ein. Der Setupbildschirm wird angezeigt.  Wenn das Gerät nicht der Domäne beigetreten ist, wird standardmäßig das lokale Administratorkonto (Benutzername "Administrator") verwendet. Das Standardkennwort für dieses Konto ist 'sfb'. Ändern Sie das Kennwort so bald wie möglich. Wenn der Computer einer Domäne beigetreten ist, können Sie sich mit einem entsprechend privilegierten Domänenkonto anmelden. 
5. Wählen **Windows Einstellungen** in der linken Spalte aus.
6. Wählen Sie **Zu Administratoranmeldung wechseln** aus.
7. Geben Sie das Administratorkennwort ein. Daraufhin wird die App ordnungsgemäß abgemeldet, und Sie gelangen zum Windows-Anmeldebildschirm. 
8. Melden Sie sich mit Ihren Administratoranmeldeinformationen beim Desktop an. Sie verfügen über die erforderlichen Berechtigungen zum Verwalten des Geräts.
9. Führen Sie die notwendigen Administratoraufgaben aus.
10. Melden Sie sich bei Ihrem Administratorkonto ab.
11. Kehren Sie Microsoft Teams-Räume zurück, indem Sie das Benutzerkontosymbol ganz links auf dem Bildschirm und dann auf **Skype.**
    
    Wenn der **Skype** nicht aufgeführt ist, müssen Sie  möglicherweise einen anderen Benutzer auswählen und **".\skype"** als Benutzernamen eingeben und sich anmelden.
    
Die Konsole befindet sich nun wieder in ihrem normalen Betriebsmodus. Das folgende Verfahren erfordert, dass Sie eine Tastatur an das Gerät anfügen, sofern noch keine Tastatur angeschlossen ist. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Wechseln in den Administratormodus und zurück, wenn die Microsoft Teams-Räume abstürzt

1. Drücken Sie fünf Mal schnell hintereinander die WINDOWS-TASTE. Daraufhin gelangen Sie zum Windows-Anmeldebildschirm.  
2. Melden Sie sich mit Ihren Administratoranmeldeinformationen beim Desktop an.
3. Führen Sie die notwendigen Administratoraufgaben aus.
4. Starten Sie den Computer neu, wenn Sie fertig sind.

    > [!NOTE]
    > Mit dieser Methode wird der Skype-Benutzer nicht abgemeldet oder die App anmutig beendet. Sie verwenden sie jedoch, wenn die App nicht reagiert hat und die andere Methode nicht verfügbar war. 

   Die Konsole wird in ihrem normalen Betriebsmodus neu gestartet, und die app Microsoft Teams-Räume ausgeführt. Sie können die Tastatur entfernen, wenn sie angeschlossen wurde, damit Sie dieses Verfahren ausführen können.
   ## <a name="troubleshooting-tips"></a>Tipps zur Problembehandlung
   <a name="TS"> </a>

- Besprechungseinladungen werden möglicherweise nicht angezeigt, wenn sie über Domänengrenzen hinweg gesendet werden (z. B. zwischen zwei Unternehmen). In solchen Fällen sollten IT-Administratoren entscheiden, ob sie externen Benutzern das Planen einer Besprechung gestatten.
- Microsoft Teams-Räume unterstützt keine AutoDiscover Exchange Umleitungen über Exchange 2010.
- Im Allgemeinen sollten IT-Administratoren alle Audioendpunkte deaktivieren, die sie nicht verwenden möchten.
- Falls ein Spiegelbild in der Raumvorschau angezeigt wird, kann der IT-Administrator dies korrigieren, indem die Stromversorgung der Kamera angestellt wird oder die Bildausrichtung mit der Fernsteuerung der Kamera gekippt wird.
- Es ist bekannt, dass der Zugang zum Konsolentouchscreen verloren gehen kann. In diesen Fällen wird das Problem manchmal durch einen Neustart des Microsoft Teams-Räume behoben.
- Beim Verbinden eines PCs mit der Konsole über verkabelte Erfassung kann ein Verlust der lokalen Audiodaten auftreten. Das Problem mit der Wiedergabe der lokalen Audiodaten kann in diesem Fall durch einen Neustart des PCs gelöst werden.
