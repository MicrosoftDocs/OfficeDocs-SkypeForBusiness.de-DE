---
title: Wartung und Betrieb von Microsoft Teams Rooms
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
description: Lesen Sie dieses Thema, um mehr über die Verwaltung von Microsoft Teams Rooms zu erfahren, der nächsten Generation von Skype Room Systems.
ms.openlocfilehash: 56468ad85b20b25d6e9310a20638ae35e941db73
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875145"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Wartung und Betrieb von Microsoft Teams Rooms 
 
Lesen Sie dieses Thema, um mehr über die Verwaltung von Microsoft Teams Rooms zu erfahren, der nächsten Generation von Skype Room Systems.
  
Microsoft Teams Rooms ist die neueste Konferenzlösung von Microsoft, mit der Sie Ihren Besprechungsraum in eine reichhaltige, kollaborative Umgebung verwandeln können. Die Benutzer profitieren von der vertrauten Benutzeroberfläche von Microsoft Teams oder Skype for Business, und IT-Administratoren schätzen eine einfach bereitgestellte und verwaltete Windows 10 Skype-Besprechungs-App. Microsoft Teams Rooms ist so konzipiert, dass vorhandene Geräte wie ETWA -LC-Panels für eine einfache Installation verwendet werden, um Microsoft Teams oder Skype for Business in Ihren Besprechungsraum zu bringen.
  
Bei zusätzlicher Konfiguration ist die Remoteverwaltung mithilfe von Microsoft Azure Monitor möglich, wie unter Planen der Verwaltung von [Microsoft Teams-Räumen](azure-monitor-plan.md)mit Azure Monitor , Bereitstellen der Verwaltung von Microsoft [Teams-Räumen](azure-monitor-deploy.md)mit Azure Monitor , Verwalten von Microsoft Teams Rooms-Geräten mit [Azure Monitor beschrieben.](azure-monitor-deploy.md) Sie können microsoft [Teams Rooms-Konsoleneinstellungen](xml-config-file.md)auch remote mit einer XML-Konfigurationsdatei verwalten, die das Anwenden eines benutzerdefinierten Anzeigedesigns umfasst. 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Sammeln von Protokollen in Microsoft Teams Rooms
<a name="Logs"> </a>

Zum Sammeln von Protokollen müssen Sie das Protokollsammlungsskript aufrufen, das in der Microsoft Teams Rooms-App enthalten ist. Starten Sie im Administratormodus eine Eingabeaufforderung mit erhöhter Eingabeaufforderung, und lösen Sie den folgenden Befehl aus:
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Die Protokolle werden als #A0 in c:\rigel ausgegeben.
  
## <a name="front-of-room-display-settings"></a>Anzeigeeinstellungen vorne im Raum
<a name="Display"> </a>

Konfigurieren Sie den Bildschirm vorne im Raum für den Modus „Erweitert“. Dadurch wird sichergestellt, dass die Konsolen-UI auf dieser Anzeige nicht dupliziert wird, wenn Sie den Strom auf der Anzeige schalten.
  
> [!NOTE]
> Wenn Sie möchten, dass eine Anzeige vor dem Raum automatisch zu einer aktiven Videoquelle (z. B. einer MTR-Konsole) wechselt, wenn die Quelle aus dem Standbymodus aktiviert wird, müssen bestimmte Bedingungen erfüllt sein. Dieses Feature ist optional, wird aber von der Microsoft Teams Rooms-Software unterstützt, vorausgesetzt, die zugrunde liegende Hardware unterstützt das Feature. Ein Verbraucher-TV, das als Bildschirm vor dem Raum verwendet wird, muss das Feature Consumer Electronics Control (CEC) von HDMI unterstützen.  Je nach ausgewähltem Dock oder der ausgewählten Konsole (die CEC möglicherweise nicht unterstützt, lesen Sie die Dokumentation zum Herstellersupport), ist möglicherweise ein Controller wie [ein HD-TX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) von Crestron oder [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) von Extron erforderlich, um das gewünschte Verhalten zu ermöglichen. 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Zurücksetzen von Microsoft Teams-Räumen (Factory Restore)
<a name="Reset"> </a>

Wenn Microsoft Teams Rooms nicht gut ausgeführt wird, kann das Durchführen einer Werkszurücksetzung hilfreich sein. Verwenden Sie dazu das [Microsoft Teams Room-Wiederherstellungstool,](recovery-tool.md) und folgen Sie den Anweisungen zur Werkswiederherstellung.

> [!NOTE]
> Es gibt ein bekanntes Problem, bei dem microsoft Teams Rooms unbrauchbar werden können, wenn die Option Meine Dateien behalten – Entfernt Apps und **Einstellungen,** aber ihre persönlichen Dateien während des Windows-Reset-Vorgangs aktiviert bleibt. Verwenden *Sie* diese Option nicht.
  
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
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Konfigurieren von Gruppenrichtlinien für Microsoft Teams Rooms
<a name="GroupPolicy"> </a>

In diesem Abschnitt werden Systemeinstellungen behandelt, von deren ordnungsgemäßer Funktion Microsoft Teams Rooms abhängt. Stellen Sie beim Beitritt zu Microsoft Teams Rooms zu einer Domäne sicher, dass ihre Gruppenrichtlinie die Einstellungen in der folgenden Tabelle nicht außer Kraft setzt.
  

|Einstellung|Ermöglicht|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Ermöglicht das Starten von Microsoft Teams Rooms  <br/> |
|Power Management – \> Schalten Sie den Bildschirm bei Wechselstrom nach 10 Minuten aus.  <br/> Power Management – \> Schalten Sie das System niemals in den Ruhezustand ein.  <br/> |Ermöglicht es Microsoft Teams Rooms, angefügte Displays zu deaktivieren und automatisch zu aktivieren.  <br/> |
|net accounts /maxpwage:unlimited  <br/> Oder entsprechende Möglichkeit zum Deaktivieren des Kennwortablaufs für das lokale Konto. Wird dies nicht ausgeführt, kann bei der Anmeldung des Skype-Kontos aufgrund eines abgelaufenen Kennworts ein Fehler auftreten. Beachten Sie, dass sich dies auf alle lokalen Konten auf dem Computer auswirkt, sodass bei Nichtfestlegung dieser Einstellung auch das Administratorkonto ablaufen kann.  <br/> |Ermöglicht die ständige Anmeldung des Skype-Kontos  <br/> |
   
Das Übertragen von Dateien mithilfe von Gruppenrichtlinien wird unter [Konfigurieren eines Dateielements erläutert.](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)

> [!NOTE]
> Wenn Das Microsoft Teams Rooms-Gerät mit der nächsten Version von Windows 10 OS kompatibel ist, wird das Gerät über Windows Update automatisch auf die nächste Version aktualisiert. Microsoft Teams Rooms-Geräte sollten nicht manuell auf die nächste Version von Windows 10 oder über die Aktivierung von Windows Update for Business (WUFB)-Gruppenrichtlinien "Wählen Sie die Windows-Bereitschaftsstufe für die Updates, die Sie erhalten möchten" und "Auswählen, wann Vorschaubuilds und Featureupdates empfangen werden" über GPO aktualisiert werden. Bei einem Gerät, auf dem diese Gruppenrichtlinien aktiviert sind, gibt es bekannte Informationen zu Problemen mit dem Windows 10 -Betriebssystemupdate der Microsoft Teams Rooms-App.

## <a name="remote-management-using-powershell"></a>Remoteverwaltung mit PowerShell
<a name="RemotePS"> </a>

Sie können die folgenden Verwaltungsvorgänge remote mithilfe von PowerShell ausführen (skriptbeispiele finden Sie in der nachstehenden Tabelle):
  
- Abrufen von angeschlossenen Geräten
- Abrufen des App-Status
- Abrufen von Systeminformationen
- Neustart des Systems
- Abrufen von Protokollen
- Übertragen von Dateien (erfordert ein Microsoft Teams Rooms, dem eine Domäne beigetreten ist)
    
> [!NOTE]
> Diese Funktion ist standardmäßig deaktiviert. Sie müssen Remote-PowerShell für Ihre Umgebung auf dem Microsoft Teams Rooms-System aktivieren, um die folgenden Vorgänge ausführen zu können. Informationen zum Aktivieren von Remote-PowerShell finden Sie in der Dokumentation zu **[Aktivieren-PSRemoting.](https://technet.microsoft.com/library/hh849694.aspx)**
  
Sie können Remote-PowerShell beispielsweise wie folgt aktivieren:
  
1. Melden Sie sich als Administrator auf einem Microsoft Teams Rooms-Gerät an.
2. Öffnen Sie eine Eingabeaufforderung mit erhöhter PowerShell.
3. Geben Sie den folgenden Befehl ein: `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. Öffnen Sie die lokale  Sicherheitsrichtlinie, und fügen Sie die Sicherheitsgruppe Administratoren zu **Lokalen** Sicherheitseinstellungen Benutzerrechtezuweisung auf diesen Computer über  >    >    >  **das Netzwerk zu.**

So führen Sie einen Verwaltungsvorgang durch:
  
1. Melden Sie sich bei einem PC mit Kontoanmeldeinformationen an, die über die Berechtigung zum Ausführen von PowerShell-Befehlen auf einem Microsoft Teams Rooms-Gerät verfügen.
2. Öffnen Sie eine normale PowerShell-Eingabeaufforderung auf dem PC.
3. Kopieren Sie den Befehlstext aus der nachstehenden Tabelle, und fügen Sie ihn an der Eingabeaufforderung ein.
4. Ersetzen  `<Device fqdn>` Sie Felder durch FQDN-Werte, die ihrer Umgebung entsprechend sind.
5. Ersetzen Sie dies durch den Dateinamen und den lokalen Pfad der SkypeSettings.xml  *\<path\>*  -Konfigurationsdatei (oder Designbild).
    
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

Pushen einer XML-Konfigurationsdatei (oder Designgrafik)
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Softwareupdates
<a name="SWupdate"> </a>

Standardmäßig versucht Microsoft Teams Rooms, eine Verbindung mit dem Windows Store herzustellen, um die neueste Version der Microsoft Teams Rooms-Software zu erhalten, sodass für das Gerät ein regelmäßiger Internetzugang erforderlich ist. Stellen Sie vor dem Kontaktieren von Microsoft mit Supportproblemen sicher, dass das Microsoft Teams Rooms-Gerät mit der neuesten Version der App geladen ist.
  
Standardmäßig stellt Microsoft Teams Rooms eine Verbindung mit Windows Update ein, um Firmwareupdates für Betriebssysteme und USB-Peripheriegeräte abzurufen und außerhalb der konfigurierten Geschäftszeiten zu installieren. Sie können Geschäftszeiten konfigurieren, indem Sie sich beim Administratorkonto anmelden und die Einstellungen-App ausführen.
  
Wenn Sie Updates manuell verwalten möchten und das normale Verfahren für [Microsoft Store for Business](https://businessstore.microsoft.com/store) zum Verteilen von Offline-Apps nicht ausführen können, können Sie die entsprechende APPX-Datei und Abhängigkeiten aus dem Bereitstellungskit (aus den Anweisungen zum Konfigurieren einer Microsoft Teams [Rooms-Konsole)](console.md)erwerben, die mit Configuration Manager verwendet werden können. [](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) [](https://go.microsoft.com/fwlink/?linkid=851168) Die Version des Bereitstellungskits liegt hinter der Store-Version zurück, sodass sie möglicherweise nicht immer mit dem neuesten verfügbaren Build übereinstimmen kann.
  
### <a name="to-update-using-powershell"></a>So aktualisieren Sie die Aktualisierung mithilfe von Powershell

1. Extrahieren Sie das Paket aus der [MSI-Installation](https://go.microsoft.com/fwlink/?linkid=851168) auf eine Freigabe, auf die das Gerät zugreifen kann.
2. Führen Sie das folgende Skript für die Microsoft Teams Rooms-Geräte aus, und ändern Sie die \<share\> Gerätefreigabe entsprechend:
    
    ```PowerShell
    Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
    ```

## <a name="admin-mode-and-device-management"></a>Administratormodus und Geräteverwaltung
<a name="AdminMode"> </a>

Bei einigen Verwaltungsfunktionen, z. B. der manuellen Installation eines zertifikats für private Zertifizierungsstellen, muss das Surface Pro im Administratormodus platziert werden. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Wechseln in den Administratormodus und zurück, wenn die Microsoft Teams Rooms-App ausgeführt wird

1. Hängen Sie alle laufenden Anrufe auf, und kehren Sie zum Startbildschirm zurück.
2. Wählen Sie das Zahnradsymbol aus, und öffnen Sie das Menü (Optionen sind **Einstellungen,** **Barrierefreiheit** und **Gerät neu starten).**
3. Wählen Sie **Einstellungen** aus.
4. Geben Sie das Administratorkennwort ein. Der Setupbildschirm wird angezeigt.  Wenn das Gerät nicht mit der Domäne verbunden ist, wird standardmäßig das lokale Administratorkonto (Benutzername "Administrator") verwendet. Das Standardkennwort für dieses Konto ist "sfb", und ändern Sie das Kennwort so schnell wie möglich. Wenn der Computer mit der Domäne verbunden ist, können Sie sich mit einem entsprechend privilegierten Domänenkonto anmelden. 
5. Wählen **Sie in der** linken Spalte Windows-Einstellungen aus.
6. Wählen Sie **Zu Administratoranmeldung wechseln** aus.
7. Geben Sie das Administratorkennwort ein. Daraufhin wird die App ordnungsgemäß abgemeldet, und Sie gelangen zum Windows-Anmeldebildschirm. 
8. Melden Sie sich mit Ihren Administratoranmeldeinformationen beim Desktop an. Sie verfügen über die erforderlichen Berechtigungen zum Verwalten des Geräts.
9. Führen Sie die notwendigen Administratoraufgaben aus.
10. Melden Sie sich bei Ihrem Administratorkonto ab.
11. Kehren Sie zu Microsoft Teams Rooms zurück, indem Sie das Benutzerkontosymbol ganz links auf dem Bildschirm und dann **Skype auswählen.**
    
    Wenn der **Skype-Benutzer** nicht aufgeführt ist, müssen Sie möglicherweise einen anderen Benutzer auswählen und  **.\skype** als Benutzernamen eingeben und sich anmelden.
    
Die Konsole befindet sich nun wieder im normalen Betriebsmodus. Das folgende Verfahren setzt voraus, dass Sie eine Tastatur an das Gerät anfügen, wenn noch keine Tastatur angeschlossen ist. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Wechseln in den Administratormodus und zurück, wenn die Microsoft Teams Rooms-App abstürzt

1. Drücken Sie fünf Mal schnell hintereinander die WINDOWS-TASTE. Daraufhin gelangen Sie zum Windows-Anmeldebildschirm. 
2. Melden Sie sich mit Ihren Administratoranmeldeinformationen beim Desktop an.
3. Führen Sie die notwendigen Administratoraufgaben aus.
4. Starten Sie den Computer neu, wenn Sie fertig sind.

    > [!NOTE]
    > Mit dieser Methode wird der Skype-Benutzer nicht abgemeldet oder die App anmutig beendet, aber Sie würden sie verwenden, wenn die App nicht reagierte und die andere Methode nicht verfügbar war. 

   Die Konsole wird in den normalen Betriebsmodus neu gestartet, und die Microsoft Teams Rooms-App wird ausgeführt. Sie können die Tastatur entfernen, wenn sie angefügt wurde, damit Sie dieses Verfahren ausführen können.
   ## <a name="troubleshooting-tips"></a>Tipps zur Problembehandlung
   <a name="TS"> </a>

- Besprechungseinladungen werden möglicherweise nicht angezeigt, wenn sie über Domänengrenzen hinweg gesendet werden (z. B. zwischen zwei Unternehmen). In solchen Fällen sollten IT-Administratoren entscheiden, ob externe Benutzer eine Besprechung planen dürfen.
- Microsoft Teams Rooms unterstützt keine Exchange-AutoErmittlung-Umleitungen über Exchange 2010.
- Im Allgemeinen sollten IT-Administratoren alle Audioendpunkte deaktivieren, die sie nicht verwenden möchten.
- Falls ein Spiegelbild in der Raumvorschau angezeigt wird, kann der IT-Administrator dies korrigieren, indem die Stromversorgung der Kamera angestellt wird oder die Bildausrichtung mit der Fernsteuerung der Kamera gekippt wird.
- Es ist bekannt, dass der Zugang zum Konsolentouchscreen verloren gehen kann. In solchen Fällen wird das Problem manchmal durch einen Neustart des Microsoft Teams Rooms-Systems behoben.
- Beim Verbinden eines PCs mit der Konsole über verkabelte Erfassung kann ein Verlust der lokalen Audiodaten auftreten. Das Problem mit der Wiedergabe der lokalen Audiodaten kann in diesem Fall durch einen Neustart des PCs gelöst werden.
    
