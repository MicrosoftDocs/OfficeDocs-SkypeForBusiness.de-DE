---
title: Wartung und Betrieb von Microsoft Teams-Räumen
ms.author: v-lanac
author: lanachin
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
description: Lesen Sie dieses Thema, um mehr über die Verwaltung von Microsoft Teams rooms, der nächsten Generation von Skype Room-Systemen, zu erfahren.
ms.openlocfilehash: 109d07bdf7b4925f7c3d0481e1ff7facef3de8f8
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "43580703"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Wartung und Betrieb von Microsoft Teams-Räumen 
 
Lesen Sie dieses Thema, um mehr über die Verwaltung von Microsoft Teams rooms, der nächsten Generation von Skype Room-Systemen, zu erfahren.
  
Microsoft Teams Rooms ist die neueste Konferenzlösung von Microsoft, die ihren Besprechungsraum in eine umfassende, kollaborative Umgebung verwandeln soll. Die Benutzer können Ihre vertrauten Microsoft Teams oder Skype for Business-Benutzeroberfläche nutzen, und IT-Administratoren schätzen eine einfach bereitgestellte und verwaltete Windows 10 Skype-Besprechungs-app. Microsoft Teams rooms wurde entwickelt, um vorhandene Geräte wie LCD-Panels zur Vereinfachung der Installation zu nutzen, um Microsoft Teams oder Skype for Business in ihren Besprechungsraum zu bringen.
  
Mit zusätzlicher Konfiguration ist die Remoteverwaltung mithilfe von Microsoft Azure Monitor möglich, wie in [Plan Microsoft Teams rooms Management with Azure Monitor](azure-monitor-plan.md)beschrieben, [Bereitstellen von Microsoft Teams rooms Management mit Azure Monitor](azure-monitor-deploy.md), [Verwalten von Microsoft Teams rooms-Geräten mit Azure Monitor](azure-monitor-deploy.md). Sie können die [Konsoleneinstellungen für Microsoft Teams rooms auch Remote mit einer XML-Konfigurationsdatei verwalten](xml-config-file.md), die das Anwenden eines benutzerdefinierten Anzeige Designs umfasst. 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Sammeln von Protokollen in Microsoft Teams-Räumen
<a name="Logs"> </a>

Zum Sammeln von Protokollen müssen Sie das Protokoll Sammlungs Skript aufrufen, das mit der Microsoft Teams rooms-App ausgeliefert wird. Starten Sie im Administratormodus eine Eingabeaufforderung mit erhöhten Rechten, und geben Sie den folgenden Befehl ein:
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Die Protokolle werden in c:\rigel. als ZIP-Datei ausgegeben
  
## <a name="front-of-room-display-settings"></a>Anzeigeeinstellungen vorne im Raum
<a name="Display"> </a>

Konfigurieren Sie den Bildschirm vorne im Raum für den Modus „Erweitert“. Auf diese Weise wird sichergestellt, dass die Konsolen-Benutzeroberfläche nicht auf dieser Anzeige dupliziert wird, wenn Sie die Anzeige auf dem Bildschirm ausschalten.
  
> [!NOTE]
> Wenn Sie möchten, dass ein Front-Room-Display automatisch zu einer aktiven Videoquelle (wie einer MTR-Konsole) wechselt, wenn die Quelle aus dem Standbymodus aktiviert wird, müssen bestimmte Bedingungen erfüllt sein. Dieses Feature ist optional, wird aber von der Microsoft Teams Rooms-Software unterstützt, sofern die zugrunde liegende Hardware das Feature unterstützt. Ein Consumer-Fernsehgerät, das als Front-of-room-Display verwendet wird, muss die Funktion Consumer Electronics Control (CEC) von HDMI unterstützen.  Je nach ausgewähltem Dock oder der ausgewählten Konsole (die CEC möglicherweise nicht unterstützt, beziehen Sie sich auf die Dokumentation des Hersteller Supports), kann ein Controller wie ein [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) von Crestron oder die [newtron HD CTL 100](https://www.extron.com/article/hdctl100ad) von der newtron benötigt werden, um das gewünschte Verhalten zu ermöglichen. 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Microsoft Teams rooms Reset (Factory Restore)
<a name="Reset"> </a>

Wenn die Microsoft Teams-Räume nicht gut ausgeführt werden, kann es hilfreich sein, einen Factory-Reset durchzuführen. Verwenden Sie dazu das [Microsoft Teams Room Recovery Tool](recovery-tool.md) , und folgen Sie den Anweisungen für die Werks Wiederherstellung.

> [!NOTE]
> Es gibt ein bekanntes Problem, bei dem die Microsoft Teams-Räume unbrauchbar werden können, wenn die Option **meine Dateien beibehalten-apps und Einstellungen entfernt, aber Ihre persönlichen Dateien beibehalten** aktiviert ist, während des Windows-Reset-Vorgangs. Verwenden Sie diese Option *nicht* .
  
## <a name="supported-remote-options"></a>Unterstützte Remoteoptionen
<a name="RemoteOptions"> </a>

In der folgenden Tabelle sind die möglichen Remotevorgänge und die Methoden zusammengefasst, die Sie für diese Vorgänge verwenden können.
  

|Arbeitsgruppe |Nicht Mitglied einer Domäne|Mitglied einer Domäne|
|:-----|:-----|:-----|
|Neustart  <br/> |Remotedesktop  <br/> Remote-Powershell  <br/> |Remote Desktop (erfordert weitere Konfiguration)  <br/> Remote-PowerShell (weitere Konfiguration erforderlich)  <br/> Configuration Manager  <br/> |
|Betriebssystemupdate  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|App-Update  <br/> |Windows Store  <br/> |Windows Store  <br/> Configuration Manager  <br/> |
|Skype-Kontokonfiguration  <br/> |Zurzeit nicht unterstützt  <br/> |Zurzeit nicht unterstützt  <br/> |
|Zugriff auf Protokolle  <br/> |Zurzeit nicht unterstützt  <br/> |Zurzeit nicht unterstützt  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Konfigurieren von Gruppenrichtlinien für Microsoft Teams-Chatrooms
<a name="GroupPolicy"> </a>

Dieser Abschnitt behandelt die Systemeinstellungen, von denen Microsoft Teams-Räume abhängig sind, um ordnungsgemäß zu funktionieren. Wenn Sie Microsoft Teams-Räumen eine Domäne hinzugefügt haben, stellen Sie sicher, dass Ihre Gruppenrichtlinie die Einstellungen in der folgenden Tabelle nicht außer Kraft setzt.
  

|Einstellung|Ermöglicht|
|:-----|:-----|
|HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Ermöglicht das Starten von Microsoft Teams-Räumen  <br/> |
|Power Management- \> auf AC, schalten Sie den Bildschirm nach 10 Minuten aus.  <br/> Power Management- \> auf AC, niemals System in den Standbymodus versetzen  <br/> |Ermöglicht Microsoft Teams-Räumen, die angefügten anzeigen zu deaktivieren und automatisch zu aktivieren  <br/> |
|net accounts /maxpwage:unlimited  <br/> Oder entsprechende Möglichkeit zum Deaktivieren des Kennwortablaufs für das lokale Konto. Wird dies nicht ausgeführt, kann bei der Anmeldung des Skype-Kontos aufgrund eines abgelaufenen Kennworts ein Fehler auftreten. Beachten Sie, dass sich dies auf alle lokalen Konten auf dem Computer auswirkt, sodass bei Nichtfestlegung dieser Einstellung auch das Administratorkonto ablaufen kann.  <br/> |Ermöglicht die ständige Anmeldung des Skype-Kontos  <br/> |
   
Das Übertragen von Dateien mithilfe von Gruppenrichtlinien wird unter [Konfigurieren eines Dateielements](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)erläutert.

> [!NOTE]
> Wenn das Gerät von Microsoft Teams Rooms mit der nächsten Version von Windows 10 kompatibel ist, wird das Gerät automatisch auf die nächste Version über Windows Update aktualisiert. Microsoft Teams rooms-Gerät sollte nicht manuell auf die nächste Version von Windows 10 aktualisiert werden oder über die Aktivierung von Windows Update for Business (WUFB)-Gruppenrichtlinien "wählen Sie die Windows-Bereitschaftsstufe für die Updates aus, die Sie empfangen möchten" und "wählen Sie aus, wann Vorschau-Builds und Funktionsupdates empfangen werden" über das Gruppenrichtlinienobjekt. Auf einem Gerät mit aktivierten Gruppenrichtlinien ist bekannt, dass es Probleme mit dem Windows 10-Betriebssystemupdate durch die Microsoft Teams rooms-App gibt.

## <a name="remote-management-using-powershell"></a>Remoteverwaltung mit PowerShell
<a name="RemotePS"> </a>

Sie können die folgenden Verwaltungsvorgänge Remote mithilfe von PowerShell ausführen (in der folgenden Tabelle finden Sie Skriptbeispiele):
  
- Abrufen von angeschlossenen Geräten
- Abrufen des App-Status
- Abrufen von Systeminformationen
- Neustart des Systems
- Abrufen von Protokollen
- Übertragen von Dateien (erfordert einen Domänenbeitritt zu Microsoft Teams-Räumen)
    
> [!NOTE]
> Diese Funktion ist standardmäßig deaktiviert. Sie müssen die Remote-PowerShell für Ihre Umgebung im Microsoft Teams rooms-System aktivieren, um die folgenden Vorgänge auszuführen. Informationen zum Aktivieren von Remote-PowerShell finden Sie in der Dokumentation zu **[enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** .
  
Sie können Remote-PowerShell beispielsweise wie folgt aktivieren:
  
1. Anmelden als Administrator auf einem Microsoft Teams rooms-Gerät.
2. Öffnen Sie eine erweiterte PowerShell-Eingabeaufforderung.
3. Geben Sie den folgenden Befehl ein: Enable-PSRemoting -force

So führen Sie einen Verwaltungsvorgang durch:
  
1. Melden Sie sich bei einem PC mit Kontoanmeldeinformationen an, die über die Berechtigung zum Ausführen von PowerShell-Befehlen auf einem Microsoft Teams rooms-Gerät verfügen.
2. Öffnen Sie eine reguläre PowerShell-Eingabeaufforderung auf dem PC.
3. Kopieren Sie den Befehlstext aus der folgenden Tabelle, und fügen Sie ihn an der Eingabeaufforderung ein.
4. Ersetzen `<Device fqdn>` Sie Felder durch FQDN-Werte, die für Ihre Umgebung geeignet sind.
5. Ersetzen Sie * \< path \> * durch den Dateinamen und den lokalen Pfad der Master-SkypeSettings. XML-Konfigurationsdatei (oder des Design Bilds).
    
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

Pushen einer XML-Konfigurationsdatei (oder Design Grafik)
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Softwareupdates
<a name="SWupdate"> </a>

Standardmäßig versucht Microsoft Teams rooms, eine Verbindung mit dem Windows Store herzustellen, um die neueste Version der Microsoft Teams Rooms-Software abzurufen, damit das Gerät normalen Internetzugriff benötigt. Bevor Sie sich mit Microsoft mit Supportproblemen in Verbindung setzen, stellen Sie sicher, dass das Gerät Microsoft Teams Rooms mit der neuesten Version der App geladen wurde.
  
Standardmäßig stellt Microsoft Teams rooms eine Verbindung mit Windows Update her, um Betriebssystem-und USB-Peripheriegeräte-Firmware-Aktualisierungen abzurufen und außerhalb der konfigurierten Geschäftszeiten zu installieren. Sie können Geschäftszeiten konfigurieren, indem Sie sich beim Administratorkonto anmelden und die Einstellungen-App ausführen.
  
Wenn Sie Updates manuell verwalten möchten und dem normalen Verfahren für [Microsoft Store for Business](https://businessstore.microsoft.com/store) zum [Verteilen von Offline-Apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)nicht folgen können, können Sie die entsprechenden APPX-Dateien und-Abhängigkeiten aus dem [Deployment Kit](https://go.microsoft.com/fwlink/?linkid=851168) (in den Anweisungen zum [Konfigurieren einer Microsoft Teams rooms-Konsole](console.md)) abrufen, die mit Configuration Manager verwendet werden können. Das Deployment Kit-Release hinkt hinter der Store-Version zurück, daher ist es möglicherweise nicht immer mit dem neuesten verfügbaren Build identisch.
  
### <a name="to-update-using-powershell"></a>So aktualisieren Sie die Verwendung von PowerShell

1. Extrahieren Sie das Paket aus der [MSI](https://go.microsoft.com/fwlink/?linkid=851168) -Installationsdatei auf eine Freigabe, auf die das Gerät zugreifen kann.
2. Führen Sie das folgende Skript aus, das auf die Microsoft Teams rooms-Geräte ausgerichtet ist, und ändern \< Sie die Freigabe \> auf die Gerätefreigabe nach Bedarf:
    
    ```PowerShell
    Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
    ```

## <a name="admin-mode-and-device-management"></a>Administratormodus und Geräteverwaltung
<a name="AdminMode"> </a>

Einige Verwaltungsfunktionen, wie das manuelle Installieren eines privaten Zertifizierungsstellenzertifikats, erfordern das Platzieren des Surface pro-Geräts im Administratormodus. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Wechseln zum Administratormodus und zurück, wenn die Microsoft Teams rooms-app ausgeführt wird

1. Beenden Sie alle laufenden Anrufe, und kehren Sie zum Startbildschirm zurück.
2. Wählen Sie das Zahnradsymbol aus, und öffnen Sie das Menü (Optionen sind **Einstellungen**, **Barrierefreiheit**und **Gerät neu starten** ).
3. Wählen Sie **Einstellungen** aus.
4. Geben Sie das Administratorkennwort ein. Der Setupbildschirm wird angezeigt.  Wenn das Gerät nicht mit der Domäne verbunden ist, wird standardmäßig das lokale Administratorkonto (Benutzername "Administrator") verwendet. Das Standardkennwort für dieses Konto ist "SFB", so dass das Kennwort so schnell wie möglich geändert werden kann. Wenn der Computer mit einer Domäne verbunden ist, können Sie sich mit einem entsprechend privilegierten Domänenkonto anmelden. 
5. Wählen Sie in der linken Spalte **Windows-Einstellungen** aus.
6. Wählen Sie **Zu Administratoranmeldung wechseln** aus.
7. Geben Sie das Administratorkennwort ein. Daraufhin wird die App ordnungsgemäß abgemeldet, und Sie gelangen zum Windows-Anmeldebildschirm. 
8. Melden Sie sich mit Ihren Administratoranmeldeinformationen beim Desktop an. Sie verfügen über die erforderlichen Berechtigungen zum Verwalten des Geräts.
9. Führen Sie die notwendigen Administratoraufgaben aus.
10. Melden Sie sich bei Ihrem Administratorkonto ab.
11. Kehren Sie zu Microsoft Teams rooms zurück, indem Sie auf der linken Seite des Bildschirms das Symbol für das Benutzerkonto auswählen und dann **Skype**auswählen.
    
    Wenn der **Skype** -Nutzer nicht aufgeführt ist, müssen Sie möglicherweise einen **anderen Benutzer** auswählen und **.\skype** als Benutzernamen eingeben und sich anmelden.
    
Die Konsole befindet sich nun wieder im normalen Betriebsmodus. Das folgende Verfahren setzt voraus, dass Sie eine Tastatur an das Gerät anfügen, wenn noch keines angefügt ist. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Wechseln zum Administratormodus und zurück, wenn die Microsoft Teams rooms-App abstürzt

1. Drücken Sie fünf Mal schnell hintereinander die WINDOWS-TASTE. Daraufhin gelangen Sie zum Windows-Anmeldebildschirm. 
2. Melden Sie sich mit Ihren Administratoranmeldeinformationen beim Desktop an.
3. Führen Sie die notwendigen Administratoraufgaben aus.
4. Starten Sie den Computer neu, wenn Sie fertig sind.

    > [!NOTE]
    > Bei dieser Methode wird der Skype-Benutzer nicht abgemeldet oder die APP nicht ordnungsgemäß beendet, aber Sie würden ihn verwenden, wenn die APP nicht antwortete und die andere Methode nicht verfügbar war. 

   Die Konsole wird im normalen Betriebsmodus neu gestartet, wobei die Microsoft Teams rooms-app ausgeführt wird. Sie können die Tastatur entfernen, wenn Sie angefügt wurde, um dieses Verfahren ausführen zu können.
   ## <a name="troubleshooting-tips"></a>Tipps zur Problembehandlung
   <a name="TS"> </a>

- Besprechungseinladungen werden möglicherweise nicht angezeigt, wenn Sie über Domänengrenzen hinweg gesendet werden (beispielsweise zwischen zwei Unternehmen). In solchen Fällen sollten IT-Administratoren entscheiden, ob Sie externen Benutzern das Planen einer Besprechung gestatten möchten.
- Microsoft Teams rooms unterstützt keine Exchange-Auto Ermittlungs Umleitungen über Exchange 2010.
- Im Allgemeinen empfiehlt es sich, dass IT-Administratoren alle audiopunkte deaktivieren, die Sie nicht verwenden möchten.
- Falls ein Spiegelbild in der Raumvorschau angezeigt wird, kann der IT-Administrator dies korrigieren, indem die Stromversorgung der Kamera angestellt wird oder die Bildausrichtung mit der Fernsteuerung der Kamera gekippt wird.
- Es ist bekannt, dass der Zugang zum Konsolentouchscreen verloren gehen kann. In diesem Fall wird das Problem manchmal durch einen Neustart des Microsoft Teams rooms-Systems behoben.
- Beim Verbinden eines PCs mit der Konsole über verkabelte Erfassung kann ein Verlust der lokalen Audiodaten auftreten. Das Problem mit der Wiedergabe der lokalen Audiodaten kann in diesem Fall durch einen Neustart des PCs gelöst werden.
    
