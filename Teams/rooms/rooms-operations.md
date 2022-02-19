---
title: Microsoft Teams-Räume und Vorgänge
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Weitere Informationen zum Verwalten Microsoft Teams-Räume.
ms.openlocfilehash: 864438890bbaef87842f6cb4b77328906036ea56
ms.sourcegitcommit: 060ba9910b8d74cbf7097cd3b8e2834afdb3db95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2022
ms.locfileid: "62909017"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Microsoft Teams-Räume und Vorgänge
 
 
Microsoft Teams-Räume ist die Microsoft-Konferenzlösung, mit der Sie Ihren Besprechungsraum in eine umfassende, zusammenarbeitsreiche Umgebung verwandeln können. Die Benutzer werden die vertraute Benutzeroberfläche Microsoft Teams-Skype for Business nutzen, und IT-Administratoren werden eine einfach bereitgestellte und verwaltete App Windows 10 Teams-Räume schätzen. Microsoft Teams-Räume -Gerät wurde entwickelt, um vorhandene Geräte zur einfacheren Installation zu nutzen, um Microsoft Teams oder Skype for Business in Ihren Besprechungsraum zu bringen.
    
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Sammeln von Protokollen Microsoft Teams-Räume
<a name="Logs"> </a>

Um Protokolle im admin center Teams zu erfassen, wechseln Sie zu Teams auf **> Teams-Räume auf Windows**. Wählen Sie den Anzeigenamen des Geräts aus, für das Sie Protokolle erstellen möchten. Wählen Sie im oberen Bereich "Geräteprotokolle herunterladen" aus. Nachdem Sie dies bestätigt haben, können die Protokolle nach ein paar Minuten auf der Registerkarte Verlauf heruntergeladen werden.

Sie können auch PowerShell zum Sammeln von Protokollen verwenden. Sie müssen das Protokollsammlungsskript aufrufen, das mit der App Microsoft Teams-Räume wird. Starten [Sie im Administratormodus](rooms-operations.md) eine Eingabeaufforderung mit erhöhten Rechten, und gibt den folgenden Befehl aus:
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Die Protokolle werden als ZIP-Datei in "c:\rigel" ausgegeben.
  
## <a name="front-of-room-display-settings"></a>Anzeigeeinstellungen vorne im Raum
<a name="Display"> </a>

Konfigurieren Sie die Einstellungen der Front of Room-Anzeige(en), um Consumer Electronic Control(CEC) zu unterstützen oder den PC-Modus zu aktivieren.
  
Wenn Sie möchten, dass die Anzeige vor dem Raum automatisch Teams-Räume, wenn sie aus dem Standbymodus aktiviert wird, müssen bestimmte Bedingungen erfüllt sein. Dieses Feature ist optional, wird aber von Microsoft Teams-Räume unterstützt, vorausgesetzt, die zugrunde liegende Hardware unterstützt das Feature. Ein Consumer-TV, das als Front-Of-Room-Anzeige verwendet wird, muss die HDMI-Funktion (Consumer Electronics Control) für Consumer Electronics Control (CEC) unterstützen.  Je nach ausgewählter Docking-Station oder Konsole (die CEC möglicherweise nicht unterstützt, finden Sie in der Dokumentation zum Support des Herstellers) kann ein Controller wie [HD-TX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) von Crestron oder [Exppe HD CTL 100](https://www.extron.com/article/hdctl100ad) von Ex selbst erforderlich sein, um das gewünschte Verhalten zu ermöglichen.

### <a name="change-scale-and-resolution"></a>Ändern der Skalierung und Auflösung

Wenn der Schriftgrad auf der Anzeige "Vor dem Raum" zu groß oder zu klein ist, müssen Sie die Bildschirmauflösung anpassen. 

1. Wechseln in [den Administratormodus](#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)

2. Wählen Sie das Startsymbol aus. Dann Einstellungen > **System > Anzeigen**

3. Wechseln Sie **zu Skalierung und Layout**, ändern Sie dann die Größe von Text **,** Apps und anderen Elementen, und legen Sie die Skalierung auf 100 % festgelegt.

4. Legen Sie die Anzeigeauflösung auf 1080p festgelegt. Wenn Sie über zwei Monitore verfügen, legen Sie die Skalierung und Auflösung für beide Bildschirme an.

5. Wählen Sie als Nächstes das Startsymbol aus, und geben Sie **Eingabeaufforderung ein**. Wählen **Sie Als Administrator ausführen aus**.

6. Führen Sie den folgenden Befehl aus:

```cmdlet
 Powershell -ExecutionPolicy Unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentDisplayScaling.ps1 
```
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Microsoft Teams-Räume Zurücksetzen (Werkswiederherstellung)
<a name="Reset"> </a>

Wenn Microsoft Teams-Räume nicht gut ausgeführt wird, kann ein Zurücksetzen auf die Werkseinstellung hilfreich sein. Verwenden Sie dazu das Wiederherstellungstool Microsoft Teams [Raum](recovery-tool.md)", und folgen Sie den Anweisungen zur Wiederherstellung auf Werkseinstellungen.

> [!NOTE]
> Es gibt ein bekanntes Problem, bei dem das Microsoft Teams-Räume nicht mehr verwendet werden kann, wenn die Option Meine Dateien behalten – Entfernt Apps und Einstellungen, aber ihre persönlichen Dateien beibehalten während des **Vorgangs** zum Zurücksetzen Windows aktiviert ist. Verwenden *Sie* diese Option nicht.
  
## <a name="supported-remote-options"></a>Unterstützte Remoteoptionen
<a name="RemoteOptions"> </a>

In der folgenden Tabelle sind die möglichen Remotevorgänge und die Methoden zusammengefasst, die Sie für diese Vorgänge verwenden können.
  

|Arbeitsgruppe |Nicht Mitglied einer Domäne|Mitglied einer Domäne|
|:-----|:-----|:-----|
|Neustart  <br/> |Teams Admin Center  <br/> Remotedesktop  <br/> Remote-PowerShell  <br/> | <br/>Remotedesktop (erfordert weitere Konfiguration)  <br/> Remote-PowerShell (erfordert weitere Konfiguration)  <br/> Configuration Manager  <br/> |
|Betriebssystemupdate  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|App-Update  <br/> |Windows Store  <br/> |Windows Store  <br/> Configuration Manager  <br/> |
|Kontokonfiguration  <br/> |Teams Admin Center  <br/> |Teams Admin Center  <br/> |
|Zugriff auf Protokolle  <br/> |Teams Admin Center  <br/> PowerShell  <br/> |Teams Admin Center <br/> PowerShell  <br/>  |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Konfigurieren von Gruppenrichtlinien für Microsoft Teams-Räume
<a name="GroupPolicy"> </a>

In diesem Abschnitt werden die Systemeinstellungen Microsoft Teams-Räume, die davon abhängig sind, dass sie ordnungsgemäß funktionieren. 

Das Teams-Räume einer Active Directory-Domäne bietet die folgenden Vorteile:

- Bei einem Domänen-Teams-Räume können Sie Domänenbenutzern und Gruppen Administratorrechte erteilen. Dadurch müssten Sie sich das Kennwort für das Administratorkonto auf Computerebene nicht merken.

- Sie können Windows Quality of Service-Konfiguration für die Teams-Räume.

- Wenn Sie Skype for Business, automatisiert die Domänen-Teams-Räume das Importieren der privaten Stammzertifikatkette Ihrer Organisation.

Wenn Sie Teams-Räume einer Domäne beitreten, müssen Sie eine separate Organisationseinheit erstellen, damit Sie Gruppenrichtlinienobjektausschlüsse für die Organisationseinheit bereitstellen können, in der sich alle Teams-Räume-Objekte befinden. Deaktivieren Sie alle GPO-Vererbung, damit nicht unterstützte Gruppenrichtlinieneinstellungen nicht auf ihre Teams-Räume. Erstellen Sie Computerobjekte in der Organisationseinheit, bevor Sie Teams-Räume Domäne beitreten, um sicherzustellen, dass auf die Standardcomputer-OU angewendete Gruppenrichtlinien nicht angewendet werden.

> [!NOTE]
> Selbst wenn Sie eine separate Organisationseinheit erstellen und die Vererbung blockieren, gibt es einige Gruppenrichtlinien, die zu Problemen führen könnten, wenn sie keine Überschreibung festgelegt haben. Eine Gruppenrichtlinie ohne Überschreibung überschreibt eine Organisationseinheit mit festgelegter Blockrichtlinienvererbung.

Viele Organisationen verfügen über die folgenden Gruppenrichtlinienobjekte, die sich auf die Teams-Räume auswirken. Stellen Sie sicher, dass Sie die Vererbung der folgenden Werte außer Kraft setzen oder blockieren:

  - Timeout von Anmeldesitzungen (automatische Sperre)
  - Richtlinien in Bezug auf die Energieverwaltung
  - Notwendigkeit zusätzlicher Authentifizierungsschritte
  - Verweigern des Zugriffs auf lokale Laufwerke
  - Benutzeraufforderungen bei langsamen Netzwerkverbindungen
  - Starten eines bestimmten Programms bei der Anmeldung
  - Erstellen eines weiteren Domänennutzerkontos auf allen Computern in der Domäne.
  - Push Windows Update to Teams-Räume

Wenn Sie Microsoft Teams-Räume Domäne beitreten, stellen Sie sicher, dass Ihre Gruppenrichtlinien die Einstellungen in der folgenden Tabelle nicht außer Kraft setzen.

|Einstellung|Lässt zu|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Ermöglicht Microsoft Teams-Räume starten  <br/> |
|Power Management –\> Netzstrom, Bildschirm nach 10 Minuten ausschalten  <br/> Power Management – Schalten\> Sie die Stromversorgung ein, und legen Sie das System nie in den Ruhezustand  <br/> |Ermöglicht Microsoft Teams-Räume, angefügte Anzeigen auszuschalten und automatisch zu reaktivierungen.  <br/> |
|net accounts /maxpwage:unlimited  <br/> Oder entsprechende Möglichkeit zum Deaktivieren des Kennwortablaufs für das lokale Konto. Wird dies nicht ausgeführt, kann bei der Anmeldung des Skype-Kontos aufgrund eines abgelaufenen Kennworts ein Fehler auftreten. Beachten Sie, dass sich dies auf alle lokalen Konten auf dem Computer auswirkt, sodass bei Nichtfestlegung dieser Einstellung auch das Administratorkonto ablaufen kann.   <br/> |Ermöglicht die ständige Anmeldung des Skype-Kontos  <br/> |

> [!NOTE]
> Wenn Microsoft Teams-Räume mit der nächsten Version von Windows 10 Betriebssystem kompatibel ist, wird Teams-Räume Über das Update automatisch auf die Windows Version aktualisiert. Microsoft Teams-Räume sollte nicht manuell oder über die Aktivierung der Gruppenrichtlinien von Windows Update for Business (WUFB) "Select the Windows readiness level for the updates you want to the updates you want to receive" oder "Select when Preview Builds and Feature Updates are received" (Auswählen, wann Vorabversions- und Featureupdates empfangen werden) über das Gruppenrichtlinienobjekt auf die nächste Version von Windows 10 aktualisiert werden. Teams-Räume diese Gruppenrichtlinien aktiviert sind, ist bekannt, dass es zu Problemen mit Windows 10 Betriebssystemupdates kommt.

## <a name="remote-management-using-powershell"></a>Remoteverwaltung mit PowerShell
<a name="RemotePS"> </a>

Sie können die folgenden Verwaltungsvorgänge remote mithilfe von PowerShell ausführen (Skriptbeispiele finden Sie in der folgenden Tabelle):
  
- Abrufen von angeschlossenen Geräten
- Abrufen des App-Status
- Abrufen von Systeminformationen
- Neustart des Systems
- Abrufen von Protokollen
- Übertragen von Dateien (erfordert eine In eine Domäne Microsoft Teams-Räume)
    
> [!NOTE]
> Diese Funktion ist standardmäßig deaktiviert. Sie müssen Remote-PowerShell für Ihre Umgebung auf dem Microsoft Teams-Räume aktivieren, um die folgenden Vorgänge ausführen zu können. Informationen zum Aktivieren von Remote-PowerShell finden Sie in der Dokumentation zum Aktivieren von **[PSRemoting](/powershell/module/microsoft.powershell.core/enable-psremoting)** .
  
Sie können Remote-PowerShell beispielsweise wie folgt aktivieren:
  
1. Melden Sie sich auf einem mobilen Microsoft Teams-Räume als Administrator an.
2. Öffnen Sie eine PowerShell-Eingabeaufforderung mit erhöhten Rechten.
3. Geben Sie den folgenden Befehl ein: `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. Öffnen Sie die lokale Sicherheitsrichtlinie, und  fügen Sie die Sicherheitsgruppe "Administratoren" zu "**Sicherheit Einstellungen** >  **Lokale RichtlinienUser** >  **Rights AssignmentAccess** >  für diesen Computer **aus dem Netzwerk" hinzu**.

So führen Sie einen Verwaltungsvorgang durch:
  
1. Melden Sie sich bei einem PC mit Kontoanmeldeinformationen an, die über die Berechtigung zum Ausführen von PowerShell-Befehlen auf einem Microsoft Teams-Räume verfügen.
2. Öffnen Sie eine normale PowerShell-Eingabeaufforderung auf dem PC.
3. Kopieren Sie den Befehlstext aus der nachstehenden Tabelle, und fügen Sie ihn an der Eingabeaufforderung ein.
4. Ersetzen Sie  `<Device fqdn>` Felder durch FQDN-Werte, die Ihrer Umgebung angemessen sind.
5. Ersetzen  *\<path\>*  Sie die Datei durch den Dateinamen und lokalen Pfad der MasterSkypeSettings.xml Konfigurationsdatei (oder designbild).
    
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

Standardmäßig versucht Microsoft Teams-Räume, eine Verbindung mit dem Windows Store herzustellen, um die neueste Version der Microsoft Teams-Räume zu erhalten. Daher ist Teams-Räume regelmäßige Internetverbindung erforderlich. Stellen Sie vor dem Kontaktieren von Microsoft-Supportproblemen sicher, Microsoft Teams-Räume die neueste Version der App geladen wurde.
  
Microsoft Teams-Räume stellt eine Verbindung mit Windows Update auf, um Firmwareupdates für Betriebssysteme und Peripheriegeräte abzurufen. Sie stellt außerdem eine Verbindung mit dem Microsoft Store, um Anwendungsupdates abzurufen.

Wenn Sie Anwendungsupdates manuell verwalten müssen, aber das normale Verfahren für [Microsoft Store für Unternehmen](https://businessstore.microsoft.com/store) zum Verteilen von [Offline-Apps](/microsoft-store/distribute-offline-apps) nicht ausführen können, können Sie Teams-Räume-Updatepakete erwerben, um App-Updates unter unterstützten Betriebssystemen durchzuführen. Die Updateversion kann hinter der Store-Version zurück liegen und nicht immer mit dem neuesten verfügbaren Build übereinstimmen. Weitere [Informationen finden Sie unter Microsoft Teams-Räume Gerät](manual-update.md) manuell aktualisieren.

## <a name="admin-mode-and-device-management"></a>Administratormodus und Geräteverwaltung
<a name="AdminMode"> </a>

Einige Verwaltungsfunktionen, z. B. die manuelle Installation eines Zertifikats einer privaten Zertifizierungsstelle, erfordern das Teams-Räume im Administratormodus. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Wechseln in den Administratormodus und zurück, wenn die Microsoft Teams-Räume ausgeführt wird

1. Bleiben Sie bei laufenden Anrufen auf, und kehren Sie zum Startbildschirm zurück.
2. Wählen Sie das Zahnradsymbol aus, und öffnen Sie das Menü (optionen **sind Einstellungen****,** Bedienungshilfen und **Gerät neu starten**).
3. Wählen Sie **Einstellungen** aus.
4. Geben Sie das Administratorkennwort ein. Der Setupbildschirm wird angezeigt.  Wenn das Gerät nicht der Domäne beigetreten ist, wird standardmäßig das lokale Administratorkonto (Benutzername "Administrator") verwendet. Das Standardkennwort für dieses Konto ist 'sfb'. Ändern Sie dieses Kennwort so schnell wie möglich. Wenn der Computer einer Domäne beigetreten ist, können Sie sich mit einem entsprechend privilegierten Domänenkonto anmelden.
5. Wählen **Windows Einstellungen** in der linken Spalte aus.
6. Melden Sie sich mit Ihren Administratoranmeldeinformationen beim Desktop an. Sie verfügen über die erforderlichen Berechtigungen zum Verwalten des Geräts.
7. Führen Sie die notwendigen Administratoraufgaben aus.
8.  Starten Sie den Computer neu, wenn Sie fertig sind.
    
Die Konsole befindet sich nun wieder in ihrem normalen Betriebsmodus. Für das folgende Verfahren müssen Sie eine Tastatur an das Gerät anschließen, falls noch keine angeschlossen ist.  
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Wechseln in den Administratormodus und zurück, wenn Microsoft Teams-Räume App abstürzt

1. Drücken Sie fünf Mal schnell hintereinander die WINDOWS-TASTE. Daraufhin gelangen Sie zum Windows-Anmeldebildschirm.  
2. Melden Sie sich mit Ihren Administratoranmeldeinformationen beim Desktop an.
3. Führen Sie die notwendigen Administratoraufgaben aus.
4. Starten Sie den Computer neu, wenn Sie fertig sind.

    > [!NOTE]
    > Mit dieser Methode wird der Skype-Benutzer nicht abgemeldet oder die App anmutig beendet. Sie verwenden sie jedoch, wenn die App nicht reagiert hat und die andere Methode nicht verfügbar war. 

   Die Konsole wird in ihrem normalen Betriebsmodus neu gestartet, und die App Microsoft Teams-Räume ausgeführt. Sie können die Tastatur entfernen, wenn Sie eine angefügt haben, um dieses Verfahren zu führen.
   ## <a name="troubleshooting-tips"></a>Tipps zur Problembehandlung
   <a name="TS"> </a>

- Besprechungseinladungen werden möglicherweise nicht angezeigt, wenn sie über Domänengrenzen hinweg gesendet werden (z. B. zwischen zwei Unternehmen). In solchen Fällen sollten IT-Administratoren entscheiden, ob sie externen Benutzern das Planen einer Besprechung gestatten. Lesen Sie den Artikel für Exchange PowerShell-Cmdlet [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing), insbesondere den Parameter "ProcessExternalMeetingMessages".
- Microsoft Teams-Räume unterstützt keine Exchange von AutoErmittlungsumleitungen über Exchange 2010.
- Im Allgemeinen sollten IT-Administratoren alle Audioendpunkte deaktivieren, die sie nicht verwenden möchten.
- Sollte in der Raumvorschau ein Spiegelbild angezeigt werden, kann der IT-Administrator das Problem durch Drehen der Kameraleistung oder Kippen der Bildausrichtung mithilfe der Kameraeinstellungen korrigieren.
- Es ist bekannt, dass der Zugang zum Konsolentouchscreen verloren gehen kann. In diesen Fällen wird das Problem manchmal durch einen Neustart des Teams-Räume.
- Beim Verbinden eines PCs mit der Konsole über verkabelte Erfassung kann ein Verlust der lokalen Audiodaten auftreten. Das Problem mit der Wiedergabe der lokalen Audiodaten kann in diesem Fall durch einen Neustart des PCs gelöst werden.
