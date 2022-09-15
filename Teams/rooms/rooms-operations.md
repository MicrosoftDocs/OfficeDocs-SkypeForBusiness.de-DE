---
title: Microsoft Teams-Räume Wartung und Betrieb
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Erfahren Sie mehr über das Verwalten von Microsoft Teams-Räume.
ms.openlocfilehash: 85979448c425f2ab0de9a5956ba4e74b2a5697cc
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706662"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Microsoft Teams-Räume Wartung und Betrieb
 
 
Microsoft Teams-Räume ist die Konferenzlösung von Microsoft, die entwickelt wurde, um Ihren Besprechungsraum in eine umfassende, kollaborative Erfahrung zu verwandeln. Benutzer profitieren von der vertrauten Microsoft Teams- oder Skype for Business-Benutzeroberfläche, und IT-Administratoren schätzen eine einfach bereitgestellte und verwaltete Windows 10 Teams-Räume-App. Microsoft Teams-Räume wurde entwickelt, um vorhandene Geräte für eine einfache Installation zu nutzen, um Microsoft Teams oder Skype for Business in Ihren Besprechungsraum zu bringen.
    
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Sammeln von Protokollen bei Microsoft Teams-Räume
<a name="Logs"> </a>

Um Protokolle im Teams Admin Center zu sammeln, wechseln Sie zu **Teams-Geräten > Teams-Räume unter Windows**. Wählen Sie den Anzeigenamen des Geräts aus, für das Sie Protokolle verwenden möchten. Wählen Sie im oberen Bereich "Geräteprotokolle herunterladen" aus. Nachdem Sie dies bestätigt haben, können die Protokolle nach einigen Minuten auf der Registerkarte "Verlauf" heruntergeladen werden.

Sie können PowerShell auch zum Sammeln von Protokollen verwenden. Sie müssen das Protokollsammlungsskript aufrufen, das im Lieferumfang der Microsoft Teams-Räume-App enthalten ist. Starten Sie [im Admin Modus](rooms-operations.md) eine Eingabeaufforderung mit erhöhten Rechten, und geben Sie den folgenden Befehl aus:
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Die Protokolle werden als ZIP-Datei in c:\rigel ausgegeben.

### <a name="managing-disk-space"></a>Verwalten von Speicherplatz
<a name="Space"> </a>

Heruntergeladene Protokolle auf dem Gerät können Speicherplatz belegen. Wenn Protokolle nicht regelmäßig bereinigt werden, können sie die normale Funktionalität des Raums beeinträchtigen. Teams-Räume löscht heruntergeladene Protokolle nach 30 Tagen. IT-Administratoren können die Protokollbereinigung mithilfe der Geräteregistrierungseinstellung außer Kraft setzen.

|Einstellung|Ermöglicht|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\PPI\SkypeSettings\LogCleanupAgeThreshold  <br/> |Bereinigt Protokolle nach 30 Tagen.  <br/> |
  
## <a name="front-of-room-display-settings"></a>Anzeigeeinstellungen für die Vorderseite des Raums
<a name="Display"> </a>

Konfigurieren Sie die Einstellungen der Front-of-Room-Anzeige(en), um die Consumer Electronics Control (CEC) zu unterstützen oder den PC-Modus zu aktivieren.
  
Wenn Sie möchten, dass eine Anzeige vor dem Raum automatisch zu Teams-Räume wechselt, wenn sie aus dem Standbymodus aktiviert wird, müssen bestimmte Bedingungen erfüllt sein. Dieses Feature ist optional, wird jedoch von Microsoft Teams-Räume Software unterstützt, vorausgesetzt, die zugrunde liegende Hardware unterstützt das Feature. Ein Consumer-TV, der als Front-of-Room-Display verwendet wird, muss die Consumer Electronics Control (CEC)-Funktion von HDMI unterstützen.  Je nach ausgewähltem Dock oder der ausgewählten Konsole (die CEC möglicherweise nicht unterstützen, lesen Sie die Supportdokumentation des Herstellers), kann ein Controller wie ein [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) von Crestron oder [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) von Extron erforderlich sein, um das gewünschte Verhalten zu ermöglichen.

### <a name="scale-and-resolution"></a>Skalierung und Auflösung

Um Teams-Räume designte Oberfläche zu erhalten, müssen Ihre Front-of-Room-Displays auflösungs- und skalierungsanforderungen erfüllen.

Informationen zum Remote-Festlegen der Skalierung und Auflösung ihrer Front-of-Rooms-Anzeigen finden [Sie unter Verwalten einer Microsoft Teams-Räume Konsoleneinstellungen remote mit einer XML-Konfigurationsdatei](xml-config-file.md#set-front-of-room-scale-and-resolution).

So legen Sie die Skalierung und Auflösung manuell in den Teams-Räume Administratoreinstellungen fest:

1. Wechseln Sie in Ihrem Teams-Raum zum [Administratormodus](#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)

2. Wählen Sie das Startsymbol aus. Einstellungen **> System > Anzeige**

3. Wechseln Sie zu **"Skalieren" und "Layout**", **ändern Sie dann die Größe von Text, Apps und anderen Elementen**, und legen Sie die Skalierung auf 100 % fest.

4. Legen Sie die Anzeigeauflösung auf 1080p fest. Wenn Sie über duale Monitore verfügen, legen Sie die Skalierung und Auflösung für beide Bildschirme fest.

5. Wählen Sie als Nächstes das Startsymbol aus, und geben Sie **die Eingabeaufforderung** ein. Wählen Sie **"Als Administrator ausführen" aus**.

6. Führen Sie den folgenden Befehl aus:

```cmdlet
 Powershell -ExecutionPolicy Unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentDisplayScaling.ps1 
```

7. Starten Sie das Gerät neu.
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Microsoft Teams-Räume Zurücksetzen (Werkswiederherstellung)
<a name="Reset"> </a>

Wenn Microsoft Teams-Räume nicht gut läuft, kann das Zurücksetzen auf die Werkseinstellungen hilfreich sein. Verwenden Sie dazu das [Microsoft Teams-Räume-Wiederherstellungstool](recovery-tool.md), und folgen Sie den Anweisungen zur Werkswiederherstellung.

> [!NOTE]
> Es gibt ein bekanntes Problem, bei dem die Microsoft Teams-Räume unbrauchbar werden kann, wenn die Option "**Meine Dateien beibehalten – Entfernt Apps und Einstellungen", während** des Windows-Zurücksetzens jedoch die Option "Persönliche Dateien" aktiviert bleibt. Verwenden Sie diese Option *nicht* .
  
## <a name="supported-remote-options"></a>Unterstützte Remoteoptionen
<a name="RemoteOptions"> </a>

In der folgenden Tabelle sind die möglichen Remotevorgänge und die Methoden zusammengefasst, die Sie für diese Vorgänge verwenden können.
  

|Arbeitsgruppe |Nicht Mitglied einer Domäne|Mitglied einer Domäne|
|:-----|:-----|:-----|
|Neustart  <br/> |Teams Admin Center  <br/> Remotedesktop  <br/> Remote-PowerShell  <br/> | <br/>Remotedesktop (erfordert weitere Konfiguration)  <br/> Remote PowerShell (erfordert weitere Konfiguration)  <br/> Configuration Manager  <br/> |
|Betriebssystemupdate  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|App-Update  <br/> |Windows Store  <br/> |Windows Store  <br/> Configuration Manager  <br/> |
|Kontokonfiguration  <br/> |Teams Admin Center  <br/> |Teams Admin Center  <br/> |
|Zugriff auf Protokolle  <br/> |Teams Admin Center  <br/> Powershell  <br/> |Teams Admin Center <br/> Powershell  <br/>  |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Konfigurieren von Gruppenrichtlinie für Microsoft Teams-Räume
<a name="GroupPolicy"> </a>

In diesem Abschnitt werden Die Systemeinstellungen behandelt, von denen Microsoft Teams-Räume abhängig sind, um ordnungsgemäß zu funktionieren. 

Der Beitritt Teams-Räume zu einer Active Directory-Domäne bietet die folgenden Vorteile:

- Mit Teams-Räume können Sie Domänenbenutzern und Gruppen Administratorrechte erteilen. Dadurch müssten Sie sich das Kennwort für das Administratorkonto auf Computerebene nicht merken.

- Sie können die Windows Quality of Service-Konfiguration auf Teams-Räume bereitstellen.

- Wenn Sie Skype for Business verwenden, automatisiert der Domänenbeitritt zum Teams-Räume den Import der privaten Stammzertifikatkette Ihrer Organisation.

Wenn Sie Teams-Räume mit einer Domäne verknüpfen, müssen Sie eine separate Organisationseinheit (Ou) erstellen, damit Sie Gruppenrichtlinie Object (GPO)-Ausschlüsse für die OU bereitstellen können, in der sich alle Teams-Räume Objekte befinden. Deaktivieren Sie die gesamte GPO-Vererbung, damit nicht unterstützte Gruppenrichtlinie-Einstellungen nicht auf Teams-Räume angewendet werden. Erstellen Sie Computerobjekte in der OE, bevor Sie Teams-Räume mit der Domäne verbinden, um sicherzustellen, dass gruppenrichtlinien, die auf die Standardcomputer-OE angewendet werden, nicht angewendet werden.

> [!NOTE]
> Selbst wenn Sie eine separate OE erstellen und die Vererbung blockieren, gibt es einige Gruppenrichtlinien, die Probleme verursachen können, wenn keine Außerkraftsetzung festgelegt ist. Ein Gruppenrichtlinie ohne Außerkraftsetzungssatz schlägt eine OU mit blockrichtlinienvererbungssatz.

Viele Organisationen verfügen über die folgenden GPOs, die sich auf Teams-Räume-Funktionalität auswirken. Stellen Sie sicher, dass Sie die Vererbung dieser Elemente außer Kraft setzen oder blockieren:

  - Timeout von Anmeldesitzungen (automatische Sperre)
  - Richtlinien in Bezug auf die Energieverwaltung
  - Notwendigkeit zusätzlicher Authentifizierungsschritte
  - Verweigern des Zugriffs auf lokale Laufwerke
  - Benutzeraufforderungen bei langsamen Netzwerkverbindungen
  - Starten eines bestimmten Programms bei der Anmeldung
  - Erstellen eines weiteren Domänennutzerkontos auf allen Computern in der Domäne.
  - Push-Windows Update an Teams-Räume

Stellen Sie beim Verknüpfen von Microsoft Teams-Räume zu einer Domäne sicher, dass ihre Gruppenrichtlinien die Einstellungen in der folgenden Tabelle nicht außer Kraft setzen.

|Einstellung|Ermöglicht|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Aktiviert das Starten Microsoft Teams-Räume  <br/> |
|Energieverwaltung –\> Schalten Sie den Bildschirm nach 10 Minuten unter "Netzbetrieb" aus.  <br/> Energieverwaltung –\> Schalten Sie das System niemals in den Ruhezustand  <br/> |Ermöglicht Microsoft Teams-Räume, angefügte Anzeigen zu deaktivieren und automatisch zu reaktivieren.  <br/> |
|net accounts /maxpwage:unlimited  <br/> Oder entsprechende Möglichkeit zum Deaktivieren des Kennwortablaufs für das lokale Konto. Wird dies nicht ausgeführt, kann bei der Anmeldung des Skype-Kontos aufgrund eines abgelaufenen Kennworts ein Fehler auftreten. Beachten Sie, dass sich dies auf alle lokalen Konten auf dem Computer auswirkt, sodass bei Nichtfestlegung dieser Einstellung auch das Administratorkonto ablaufen kann.   <br/> |Ermöglicht die ständige Anmeldung des Skype-Kontos  <br/> |

> [!NOTE]
> Wenn Microsoft Teams-Räume mit der nächsten Version von Windows 10 Betriebssystem kompatibel ist, wird Teams-Räume automatisch über Windows Update auf die nächste Version aktualisiert. Microsoft Teams-Räume sollten nicht manuell oder über die Aktivierung Windows 10 von Windows Update for Business (WUFB)-Gruppenrichtlinien "Wählen Sie die Windows-Bereitschaftsstufe für die Updates aus, die Sie erhalten möchten" und "Auswählen, wann Preview Builds und Feature-Aktualisierungen empfangen werden" über GPO aktualisiert werden. . Teams-Räume diese Gruppenrichtlinien aktiviert sind, treten bekanntermaßen Probleme mit Windows 10 Betriebssystemupdates auf.

## <a name="remote-management-using-powershell"></a>Remoteverwaltung mit PowerShell
<a name="RemotePS"> </a>

Sie können die folgenden Verwaltungsvorgänge remote mithilfe von PowerShell ausführen (Skriptbeispiele finden Sie in der folgenden Tabelle):
  
- Abrufen von angeschlossenen Geräten
- Abrufen des App-Status
- Abrufen von Systeminformationen
- Neustart des Systems
- Abrufen von Protokollen
- Übertragen von Dateien (erfordert eine in die Domäne eingebundene Microsoft Teams-Räume)
    
> [!NOTE]
> Diese Funktion ist standardmäßig deaktiviert. Sie müssen Remote-PowerShell für Ihre Umgebung auf dem Microsoft Teams-Räume System aktivieren, um die folgenden Vorgänge ausführen zu können. Informationen zum Aktivieren von Remote-PowerShell finden Sie in der Dokumentation zu **[Enable-PSRemoting](/powershell/module/microsoft.powershell.core/enable-psremoting)** .
  
Sie können Remote-PowerShell beispielsweise wie folgt aktivieren:
  
1. Melden Sie sich als Admin auf einem Microsoft Teams-Räume Gerät an.
2. Öffnen Sie eine PowerShell-Eingabeaufforderung mit erhöhten Rechten.
3. Geben Sie den folgenden Befehl ein: `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. Öffnen Sie die lokale Sicherheitsrichtlinie, und fügen Sie die Sicherheitsgruppe *"Administratoren* " zu " **Sicherheitseinstellungen** > **" "Lokale Richtlinien** > **" hinzu. Zugriff auf** > **diesen Computer über das Netzwerk**.

So führen Sie einen Verwaltungsvorgang durch:
  
1. Melden Sie sich bei einem PC mit Kontoanmeldeinformationen an, die über die Berechtigung zum Ausführen von PowerShell-Befehlen auf einem Microsoft Teams-Räume Gerät verfügen.
2. Öffnen Sie eine normale PowerShell-Eingabeaufforderung auf dem PC.
3. Kopieren Sie den Befehlstext aus der nachstehenden Tabelle, und fügen Sie ihn an der Eingabeaufforderung ein.
4. Ersetzen Sie  `<Device fqdn>` Felder durch FQDN-Werte, die ihrer Umgebung entsprechen.
5. Ersetzen Sie  *\<path\>*  sie durch den Dateinamen und den lokalen Pfad der Master-SkypeSettings.xml Konfigurationsdatei (oder Designimage).
    
So rufen Sie angefügte Geräte ab
  
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

Standardmäßig stellt Microsoft Teams-Räume eine Verbindung mit Windows Update her, um Firmwareupdates für Betriebssystem- und USB-Peripheriegeräte abzurufen, und installiert diese außerhalb der konfigurierten Geschäftszeiten. Sie können Geschäftszeiten konfigurieren, indem Sie sich beim Administratorkonto anmelden und  die Einstellungs-App ausführen.
  
Wenn Sie Updates manuell verwalten möchten und das normale Verfahren für [Microsoft Store für Unternehmen](https://businessstore.microsoft.com/store) zum [Verteilen von Offline-Apps](/microsoft-store/distribute-offline-apps) nicht einhalten können, können Sie das neueste MTR-Update-Skript abrufen und ausführen, wenn [Sie ein Microsoft Teams-Räume Gerät manuell aktualisieren](/microsoftteams/rooms/manual-update).

Standardmäßig versucht Microsoft Teams-Räume, eine Verbindung mit dem Windows Store herzustellen, um die neueste Version von Microsoft Teams-Räume-Software abzurufen. Daher erfordert Teams-Räume regelmäßigen Internetzugang. Bevor Sie Sich mit Supportproblemen an Microsoft wenden, stellen Sie sicher, dass Microsoft Teams-Räume mit der neuesten Version der App geladen ist.



## <a name="admin-mode-and-device-management"></a>Administratormodus und Geräteverwaltung
<a name="AdminMode"> </a>

Einige Verwaltungsfunktionen, z. B. die manuelle Installation eines privaten Zertifizierungsstellenzertifikats, erfordern das Platzieren Teams-Räume in Admin Modus. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Wechseln zum Admin-Modus und zurück, wenn die Microsoft Teams-Räume-App ausgeführt wird

1. Legen Sie alle laufenden Anrufe auf, und kehren Sie zur Startseite zurück.
2. Wählen Sie das Zahnradsymbol aus, und öffnen Sie das Menü (die Optionen sind **"Einstellungen"**, **"Barrierefreiheit**" und " **Gerät neu starten** ").
3. Wählen Sie **Einstellungen** aus.
4. Geben Sie das Administratorkennwort ein. Der Setupbildschirm wird angezeigt.  Wenn das Gerät nicht in die Domäne eingebunden ist, wird standardmäßig das lokale Administratorkonto (Benutzername "Admin") verwendet. Das Standardkennwort für dieses Konto ist "sfb". Ändern Sie dieses Kennwort so schnell wie möglich. Wenn der Computer einer Domäne beigetreten ist, können Sie sich mit einem entsprechend privilegierten Domänenkonto anmelden.
5. Wählen Sie in der linken Spalte **Windows-Einstellungen** aus.
6. Melden Sie sich mit Ihren Administratoranmeldeinformationen beim Desktop an. Sie verfügen über die erforderlichen Berechtigungen zum Verwalten des Geräts.
7. Führen Sie die notwendigen Administratoraufgaben aus.
8.  Starten Sie den Computer neu, wenn Sie fertig sind.
    
Die Konsole befindet sich nun wieder in ihrem normalen Betriebsmodus. Für das folgende Verfahren müssen Sie eine Tastatur an das Gerät anschließen, falls noch keine angeschlossen ist.  
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Wechseln zum Admin-Modus und zurück, wenn die Microsoft Teams-Räume-App abstürzt

1. Drücken Sie fünf Mal schnell hintereinander die WINDOWS-TASTE. Daraufhin gelangen Sie zum Windows-Anmeldebildschirm. 
2. Melden Sie sich mit Ihren Administratoranmeldeinformationen beim Desktop an.
3. Führen Sie die notwendigen Administratoraufgaben aus.
4. Starten Sie den Computer neu, wenn Sie fertig sind.

    > [!NOTE]
    > Mit dieser Methode wird der Skype-Benutzer nicht abgemeldet oder die App ordnungsgemäß beendet. Sie würden sie jedoch verwenden, wenn die App nicht reagierte und die andere Methode nicht verfügbar war. 

   Die Konsole wird im normalen Betriebsmodus neu gestartet und führt die Microsoft Teams-Räume-App aus. Sie können die Tastatur entfernen, wenn Sie eine angefügt haben, um dieses Verfahren abzuschließen.
   ## <a name="troubleshooting-tips"></a>Tipps zur Problembehandlung
   <a name="TS"> </a>

- Besprechungseinladungen werden möglicherweise nicht angezeigt, wenn sie über Domänengrenzen hinweg gesendet werden (z. B. zwischen zwei Unternehmen). In solchen Fällen sollten IT-Administratoren entscheiden, ob externe Benutzer eine Besprechung planen dürfen. Weitere Informationen finden Sie im Artikel zum Exchange PowerShell-Cmdlet [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing), insbesondere dem Parameter "ProcessExternalMeetingMessages".
- Microsoft Teams-Räume unterstützt keine Exchange-AutoErmittlungsumleitungen über Exchange 2010.
- Im Allgemeinen ist es eine bewährte Methode für IT-Administratoren, audioendpunkte zu deaktivieren, die sie nicht verwenden möchten.
- Für den Fall, dass ein Spiegelbild in der Raumvorschau angezeigt wird, kann der IT-Administrator dies korrigieren, indem er die Kamera einschalten oder die Bildausrichtung mithilfe der Kameraeinstellungen kippt.
- Es ist bekannt, dass der Zugang zum Konsolentouchscreen verloren gehen kann. In solchen Fällen wird das Problem manchmal durch einen Neustart Teams-Räume behoben.
- Beim Verbinden eines PCs mit der Konsole über verkabelte Erfassung kann ein Verlust der lokalen Audiodaten auftreten. Das Problem mit der Wiedergabe der lokalen Audiodaten kann in diesem Fall durch einen Neustart des PCs gelöst werden.
