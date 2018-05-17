---
title: Skype-Chatroom-Systemen v2 Wartung und Betrieb
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Lesen Sie in diesem Thema, um Informationen zur Verwaltung von Skype Raum Systemen v2, der nächsten Generation Skype Raum Systeme zu erfahren.
ms.openlocfilehash: d8dfb5c04d73717e8f20352c6cb422498f5a9b34
ms.sourcegitcommit: 265fbdc1a8ac566751e707874656bd6b90de980d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2018
---
# <a name="skype-room-systems-v2-maintenance-and-operations"></a>Skype-Chatroom-Systemen v2 Wartung und Betrieb 
 
Lesen Sie in diesem Thema, um Informationen zur Verwaltung von Skype Raum Systemen v2, der nächsten Generation Skype Raum Systeme zu erfahren.
  
Skype-Chatroom-Systemen v2 ist Microsofts neueste konferenzlösung entwickelt, um Ihre Besprechungsraum in einer umfassenden, gemeinsame Skype Business wünschen umgewandelt. Die Benutzer finden sich dank der vertrauten Benutzeroberfläche von Skype for Business schnell zurecht, und IT-Administratoren werden die Skype-Besprechungs-App für Windows 10 aufgrund der einfachen Bereitstellung und Verwaltung zu schätzen wissen. Skype Raum Systemen v2 dient zur Nutzung von vorhandenen Ausrüstung, wie Bereiche der LCD-Anzeige zur Erleichterung der Installation in Ihrem Besprechungsraum Skype für Unternehmen eingefügt werden sollen.
  
Durch zusätzliche Konfiguration kann die Remoteverwaltung Microsoft Operations Management Suite (OMS) verwenden, wie beschrieben in [Planen Skype Raum v2 systemverwaltung mit OMS](../../plan-your-deployment/clients-and-devices/oms-management.md) [Bereitstellen Skype Raum v2 systemverwaltung mit OMS](../../deploy/deploy-clients/with-oms.md)und [Verwalten Skype-Chatroom-Systemen v2 Geräte mit OMS](oms.md). Sie können auch [Verwalten einer Skype Raum Systemen v2 Konsolenstamm Remote mit einer XML-Konfigurationsdatei](xml-config-file.md), einschließlich eines Designs benutzerdefinierte anzeigen. 
  
## <a name="collecting-logs-on-skype-room-systems-v2"></a>Erfassen von Protokollen in Skype Room Systems v2
<a name="Logs"> </a>

Um die Protokolle gespeichert werden, müssen Sie das Protokoll Auflistung Skript aufrufen, das mit der Skype Raum Systemen v2-app verwendet werden soll. Starten Sie im Administratormodus eine Eingabeaufforderung mit erhöhten Rechten, und geben Sie den folgenden Befehl:
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Die Protokolle werden als ZIP-Datei in c:\rigel ausgegeben werden.
  
## <a name="front-of-room-display-settings"></a>Anzeigeeinstellungen vorne im Raum
<a name="Display"> </a>

Konfigurieren Sie den Bildschirm vorne im Raum für den Modus „Erweitert“. Dadurch wird die Konsole sicherstellen, dass, die Benutzeroberfläche auf, die anzeigen nicht dupliziert werden, wenn Sie die Anzeige schalten.
  
> [!NOTE]
> Ein Consumer TV als Front Raum Anzeige Anforderungen für den Support/HDMI das Consumer Electronics Steuerelement (CEC)-Feature aktivieren, damit er automatisch an eine aktive Bildquelle aus dem Standbymodus wechseln kann. Dieses Feature wird auf alle TV-Geräte nicht unterstützt. 
  
## <a name="skype-room-systems-v2-reset-factory-restore"></a>Zurücksetzen von Skype Room Systems v2 (Zurücksetzung auf Werkseinstellungen)
<a name="Reset"> </a>

Wenn Skype Raum Systemen v2 ebenfalls nicht ausgeführt wird, möglicherweise ausführen Herstellerstandard zurücksetzen helfen. Dies ist möglich, in der app Einstellungen auf der Registerkarte **Wiederherstellen** unter **diesem PC zurücksetzen**, wählen Sie **Erste Schritte**, und klicken Sie dann **Alles entfernen**. Führen Sie die verbleibenden aufforderungen, um das Gerät zurückzusetzen.
  
> [!NOTE]
> Es ist ein bekanntes Problem, in dem die Skype Raum Systemen v2 verwendet werden kann nicht mehr verwendet werden, wenn die Option **Meine Dateien - Apps entfernt und Einstellungen, beibehalten werden sollen, jedoch bleibt Ihre persönlichen Dateien** während des Aktivierungsvorgangs zurücksetzen ausgewählt ist. Führen Sie _nicht_ verwenden Sie diese Option.
  
## <a name="supported-remote-options"></a>Unterstützte Remoteoptionen
<a name="RemoteOptions"> </a>

In der folgenden Tabelle sind die möglichen Remotevorgänge und die Methoden zusammengefasst, die Sie für diese Vorgänge verwenden können.
  

|**Arbeitsgruppe**|**Nicht Domäne beitreten**|**Domäne beitreten**|
|:-----|:-----|:-----|
|Neustart  <br/> |Remotedesktop  <br/> Remote-Powershell  <br/> |Remotedesktop (Weitere Konfiguration erforderlich)  <br/> Remote-Powershell (Weitere Konfiguration erforderlich)  <br/> SCCM  <br/> |
|Betriebssystemupdate  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|App-Update  <br/> |Windows Store  <br/> |Windows Store  <br/> SCCM  <br/> |
|Skype-Kontokonfiguration  <br/> |Zurzeit nicht unterstützt  <br/> |Zurzeit nicht unterstützt  <br/> |
|Zugriff auf Protokolle  <br/> |Zurzeit nicht unterstützt  <br/> |Zurzeit nicht unterstützt  <br/> |
   
## <a name="configuring-group-policy-for-skype-room-systems-v2"></a>Konfigurieren von Gruppenrichtlinie für Skype Room Systems v2
<a name="GroupPolicy"> </a>

In diesem Abschnitt werden die Systemeinstellungen, von denen Skype Raum Systemen v2 abhängt, ordnungsgemäß behandelt. Wenn v2 Skype Raum Systeme mit einer Domäne verknüpft wird, stellen Sie sicher, dass Ihre Gruppenrichtlinien die Einstellungen in der folgenden Tabelle außer Kraft setzen nicht.
  

|**Einstellung**|**Ermöglicht**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AdminAutoLogon = (dword) 1  <br/> |Ermöglicht das Skype Raum Systemen v2 starten  <br/> |
|Strom-Management -\> AC, deaktivieren Sie auf Bildschirm nach 10 Minuten  <br/> Strom-Management -\> auf AC, setzen Sie nie System in den Energiesparmodus  <br/> |Skype-Chatroom-Systemen v2 angefügte zeigt deaktivieren und Reaktivieren von automatisch aktiviert  <br/> |
|net accounts /maxpwage:unlimited  <br/> Oder entsprechende Möglichkeit zum Deaktivieren des Kennwortablaufs für das lokale Konto. Wird dies nicht ausgeführt, kann bei der Anmeldung des Skype-Kontos aufgrund eines abgelaufenen Kennworts ein Fehler auftreten. Beachten Sie, dass sich dies auf alle lokalen Konten auf dem Computer auswirkt, sodass bei Nichtfestlegung dieser Einstellung auch das Administratorkonto ablaufen kann.  <br/> |Ermöglicht die ständige Anmeldung des Skype-Kontos  <br/> |
   
Übertragen von Dateien mithilfe von Gruppenrichtlinien wird unter [Konfigurieren einer Dateielement](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)erläutert.
  
## <a name="remote-management-using-powershell"></a>Remoteverwaltung mit PowerShell
<a name="RemotePS"> </a>

Sie können die folgenden Verwaltungsvorgänge Remote mithilfe von PowerShell ausführen (siehe Tabelle unten für Skriptbeispiele):
  
- Abrufen von angeschlossenen Geräten
    
- Abrufen des App-Status
    
- Abrufen von Systeminformationen
    
- Neustart des Systems
    
- Abrufen von Protokollen
    
- Übertragen von Dateien (einer Domäne gehörenden Skype Raum Systemen v2 erforderlich)
    
> [!NOTE]
> Diese Funktion ist standardmäßig deaktiviert. Sie müssen zum Ausführen der folgenden Vorgänge remote-PowerShell für Ihre Umgebung für das Skype Raum Systemen v2 System aktivieren. Finden Sie in der Dokumentation auf **[Enable-psremoting sieht](https://technet.microsoft.com/library/hh849694.aspx)** für Informationen zur Verwendung von remote-PowerShell aktivieren.
  
Sie können Remote-PowerShell beispielsweise wie folgt aktivieren:
  
1. Melden Sie sich als Administrator auf einem Gerät mit Skype Raum Systemen v2.
    
2. Öffnen Sie eine PowerShell-Eingabeaufforderung mit erhöhten Rechten.
    
3. Geben Sie den folgenden Befehl ein: Enable-psremoting sieht - erzwingen
    
So führen Sie einen Verwaltungsvorgang durch:
  
1. Melden Sie sich an einem Computer mit den Anmeldeinformationen des Kontos, die Berechtigung zum Ausführen von PowerShell-Befehlen auf einem Gerät mit Skype Raum Systemen v2.
    
2. Öffnen Sie eine reguläre PowerShell-Eingabeaufforderung auf dem PC.
    
3. Kopieren Sie den Befehlstext aus der folgenden Tabelle, und fügen Sie ihn an der Eingabeaufforderung ein.
    
4. Ersetzen Sie `<Device fqdn>` Felder mit den Werten des FQDN für Ihre Umgebung geeignet.
    
5. Ersetzen Sie * \<Pfad\> * mit den Dateinamen und den lokalen Pfad der master SkypeSettings.xml-Konfigurationsdatei (oder Bild Design).
    
Abzurufenden angeschlossene Geräte
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

Abrufen des App-Status
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

Abrufen von Systeminformationen
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

Neustart des Systems
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

Abrufen von Protokollen
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

Drücken Sie eine XML-Konfigurationsdatei (oder Grafik Design)
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Softwareupdates
<a name="SWupdate"> </a>

Standardmäßig versucht Skype Raum Systemen v2 zum Verbinden mit den Windows Store zum Abrufen der neuesten Version von Skype Raum v2 Systemsoftware, damit das Gerät regulären Internetzugriff erforderlich ist. Kontaktaufnahme mit Microsoft Support-Probleme, werden Sie sicher, dass das Skype Raum Systemen v2-Gerät mit der neuesten Version der app geladen wird.
  
In der Standardeinstellung Skype Raum Systeme v2 stellt eine Verbindung mit Windows Update Betriebssystem abgerufen und USB-Peripheriegeräte Firmwareupdates und installiert diese außerhalb der Geschäftszeiten konfiguriert. Sie können Geschäftszeiten konfigurieren, indem Sie sich beim Administratorkonto anmelden und die Einstellungen-App ausführen.
  
Wenn Sie Updates manuell verwalten möchten, und nicht im normale Verfahren für eine [Microsoft Store for Business](https://businessstore.microsoft.com/store) zu [verteilen offline-apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)haben, können Sie die entsprechende APPX Datei und Abhängigkeiten in [Deployment Kit](https://go.microsoft.com/fwlink/?linkid=851168) (aus abrufen. die Anweisungen zum [Konfigurieren einer Skype Raum Systemen v2 Konsole](../../deploy/deploy-clients/console.md)) mit SCCM verwendet werden kann. Die Deployment Kit-Version Positionen davor befindet hinter der Store-Version, damit es immer den neuesten Build möglicherweise nicht übereinstimmt.
  
### <a name="to-update-using-powershell"></a>Aktualisieren von Powershell

1. Extrahieren Sie das Paket aus der Installation die [MSI-Datei](https://go.microsoft.com/fwlink/?linkid=851168) zu einer Freigabe das Gerät, die zugreifen kann.
    
2. Führen Sie das folgende Skript für die Skype Raum Systemen v2-Geräte ändern \<freigeben\> freigeben als Antwort auf das Gerät:
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a>Administratormodus und Geräteverwaltung
<a name="AdminMode"> </a>

Einige Managementfunktionen, wie die manuelle Installation eines privaten Zertifizierungsstellenzertifikats erfordern das Vorhandensein des Surface Pro Geräts im Admin-Modus. 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-is-running"></a>Wechsel in Administratormodus und zurück, wenn die Skype Raum Systemen v2 app ausgeführt wird

1. Alle laufenden Anrufe Auflegen, und klicken Sie auf der Startseite zurück.
    
2. Wählen Sie das Zahnradsymbol und rufen Sie das Menü (Optionen sind **Einstellungen**, **Eingabehilfen**und **Gerät neu starten** ).
    
3. Wählen Sie **Einstellungen** aus.
    
4. Geben Sie das Administratorkennwort ein. Der Setupbildschirm wird angezeigt.
    
    > [!NOTE]
    > Wenn das Gerät in die Domäne eingebundener nicht ist, wird das lokale Administratorkonto (Benutzername "Admin") in der Standardeinstellung verwendet werden. Das Standard-Kennwort für dieses Konto ist 'Sfb', aber es wird empfohlen, dass Ihre Organisation dies für aus Sicherheitsgründen so bald wie möglich zu ändern. Wenn der Computer Mitglied einer Domäne ist, können Sie sich mit einem Domänenkonto entsprechend berechtigten anmelden. 
  
5. Wählen Sie **Windows-Einstellungen** in der linken Spalte aus.
    
6. Wählen Sie **Zu Administratoranmeldung wechseln** aus.
    
7. Geben Sie das Administratorkennwort ein. Daraufhin wird die App ordnungsgemäß abgemeldet, und Sie gelangen zum Windows-Anmeldebildschirm. 
    
8. Melden Sie sich mit Ihren Administratoranmeldeinformationen beim Desktop an. Sie müssen die erforderlichen Berechtigungen zum Verwalten des Geräts.
    
9. Führen Sie die notwendigen Administratoraufgaben aus.
    
10. Melden Sie sich bei Ihrem Administratorkonto ab.
    
11. Zur Skype Raum Systemen v2 durch Auswählen des Benutzer Konto-Symbols auf der linken Seite des Bildschirms und anschließend **Skype**zurückzukehren.
    
    Wenn der Benutzer **Skype** nicht aufgeführt ist, möglicherweise müssen Sie wählen Sie **Benutzer** aus, und geben **. \skype** als den Benutzernamen und das anmelden.
    
Die Konsole ist nun wieder in den normalen Betrieb-Modus. Das folgende Verfahren benötigen Sie eine Tastatur auf das Gerät anfügen, falls noch nicht angefügt wurde. 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-crashes"></a>Wechsel in Administratormodus und zurück, wenn die Skype Raum Systemen v2 app stürzt ab

1. Drücken Sie fünf Mal schnell hintereinander die WINDOWS-TASTE. Daraufhin gelangen Sie zum Windows-Anmeldebildschirm.  
    
2. Melden Sie sich mit Ihren Administratoranmeldeinformationen beim Desktop an.
    
    > [!NOTE]
    > Diese Methode nicht melden Sie sich den Skype-Benutzer oder die app ordnungsgemäß beendet, aber verwenden Sie es, wenn die app wurde nicht mehr reagiert und die andere Methode war nicht verfügbar. 
  
3. Führen Sie die notwendigen Administratoraufgaben aus.
    
4. Starten Sie den Computer, wenn Sie fertig sind.
    
 Die Konsole wird neu gestartet, in den normalen Betrieb-Modus, die Skype Raum Systemen v2 app ausgeführt. Sie können die Tastatur entfernen, wenn es angefügt wurde, damit Sie dieses Verfahren ausführen können.
## <a name="troubleshooting-tips"></a>Tipps zur Problembehandlung
<a name="TS"> </a>

- Besprechungsanfragen möglicherweise nicht angezeigt, wenn über Domänengrenzen hinweg (beispielsweise zwischen zwei Unternehmen) gesendet. In solchen Fällen sollten die IT-Administratoren, ob externe Benutzer zum Planen einer Besprechung zugelassen entscheiden.
    
- Exchange AutoDiscover leitet über Exchange 2010 unterstützt keine Skype Raum Systemen v2.
    
- Im Allgemeinen ist es ratsam für IT-Administratoren, die alle audioendpunkte deaktivieren, die er nicht verwenden möchten.
    
- Falls ein Spiegelbild in der Raumvorschau angezeigt wird, kann der IT-Administrator dies korrigieren, indem die Stromversorgung der Kamera angestellt wird oder die Bildausrichtung mit der Fernsteuerung der Kamera gekippt wird.
    
- Es ist bekannt, dass der Zugang zum Konsolentouchscreen verloren gehen kann. In solchen Fällen wird durch einen Neustart des Systems der Skype Raum Systemen v2 manchmal das Problem behoben.
    
- Beim Verbinden eines PCs mit der Konsole über verkabelte Erfassung kann ein Verlust der lokalen Audiodaten auftreten. Das Problem mit der Wiedergabe der lokalen Audiodaten kann in diesem Fall durch einen Neustart des PCs gelöst werden.
    
