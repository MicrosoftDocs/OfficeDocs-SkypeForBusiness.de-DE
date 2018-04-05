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
# <a name="manage-skype-room-systems-v2"></a>Verwalten von Skype Room Systems v2
 
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

Konfigurieren Sie den Bildschirm vorne im Raum für den Modus „Erweitert“. Dadurch wird sichergestellt, dass die Konsolen-Benutzeroberfläche auf diesem Bildschirm nicht dupliziert wird, wenn er mit Strom versorgt wird.
  
> [!NOTE]
> Ein Consumer TV als Front Raum Anzeige Anforderungen für den Support/HDMI das Consumer Electronics Steuerelement (CEC)-Feature aktivieren, damit er automatisch an eine aktive Bildquelle aus dem Standbymodus wechseln kann. Dieses Feature wird auf alle TV-Geräte nicht unterstützt. 
  
## <a name="skype-room-systems-v2-reset-factory-restore"></a>Zurücksetzen von Skype Room Systems v2 (Zurücksetzung auf Werkseinstellungen)
<a name="Reset"> </a>

Wenn Skype Raum Systemen v2 ebenfalls nicht ausgeführt wird, kann ein Herstellerstandard ausführen hilfreich sein. Dies kann in der app Einstellungen aus der Registerkarte "Wiederherstellung" unter der Überschrift "Dieser PC zurücksetzen", wählen Sie "Einstieg" gefolgt von "Alles entfernen". Gehen Sie entsprechend den Eingabeaufforderungen vor, um das Gerät zurückzusetzen.
  
> [!NOTE]
> Es ist ein bekanntes Problem, in dem die Skype Raum Systemen v2 verwendet werden kann nicht mehr verwendet werden, wenn die Option "Meine Dateien behalten - Apps und -Einstellungen entfernt, jedoch bleibt Ihre persönlichen Dateien" während des Aktivierungsvorgangs zurücksetzen ausgewählt ist. Verwenden Sie **nicht** diese Option.
  
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

In diesem Abschnitt werden die Systemeinstellungen, von denen Skype Raum Systemen v2 abhängt, ordnungsgemäß behandelt. Wenn v2 Skype Raum Systeme mit einer Domäne verknüpft wird, stellen Sie sicher, dass Ihre Gruppenrichtlinien die folgenden Einstellungen nicht überschrieben wird:
  

|**Einstellung**|**Ermöglicht**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AdminAutoLogon = (dword) 1  <br/> |Ermöglicht das Skype Raum Systemen v2 starten  <br/> |
|Strom-Management -\> AC, deaktivieren Sie auf Bildschirm nach 10 Minuten  <br/> Strom-Management -\> auf AC, setzen Sie nie System in den Energiesparmodus  <br/> |Skype-Chatroom-Systemen v2 angefügte zeigt deaktivieren und Reaktivieren von automatisch aktiviert  <br/> |
|net accounts /maxpwage:unlimited  <br/> Oder entsprechende Möglichkeit zum Deaktivieren des Kennwortablaufs für das lokale Konto. Wird dies nicht ausgeführt, kann bei der Anmeldung des Skype-Kontos aufgrund eines abgelaufenen Kennworts ein Fehler auftreten. Beachten Sie, dass sich dies auf alle lokalen Konten auf dem Computer auswirkt, sodass bei Nichtfestlegung dieser Einstellung auch das Administratorkonto ablaufen kann.  <br/> |Ermöglicht die ständige Anmeldung des Skype-Kontos  <br/> |
   
Übertragen von Dateien mithilfe von Gruppenrichtlinien wird unter [Konfigurieren einer Dateielement](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)erläutert.
  
## <a name="remote-management-using-powershell"></a>Remoteverwaltung mit PowerShell
<a name="RemotePS"> </a>

Die folgenden Verwaltungsvorgänge können remote mit PowerShell ausgeführt werden (Skriptbeispiele finden Sie in der Tabelle unten):
  
- Abrufen von angeschlossenen Geräten
    
- Abrufen des App-Status
    
- Abrufen von Systeminformationen
    
- Neustart des Systems
    
- Abrufen von Protokollen
    
- Übertragen von Dateien (erfordert eine in die Domäne eingebundener Skype Raum Systemen v2)
    
> [!NOTE]
> Diese Funktion ist standardmäßig deaktiviert. Sie müssen zum Ausführen der folgenden Vorgänge remote-PowerShell für Ihre Umgebung für das Skype Raum Systemen v2 System aktivieren. Finden Sie in der Dokumentation auf **[Enable-psremoting sieht](https://technet.microsoft.com/en-us/library/hh849694.aspx)** für Informationen zum remote-PowerShell aktivieren.
  
Sie können Remote-PowerShell beispielsweise wie folgt aktivieren:
  
1. Melden Sie sich als Administrator auf einem Gerät mit Skype Raum Systemen v2.
    
2. Starten Sie eine PowerShell-Eingabeaufforderung mit erhöhten Rechten.
    
3. Geben Sie den folgenden Befehl ein: Enable-psremoting sieht - erzwingen
    
So führen Sie einen Verwaltungsvorgang durch:
  
1. Melden Sie sich bei einem PC mit den Anmeldeinformationen des Kontos, die Berechtigung zum Ausführen von PowerShell-Befehlen auf einem Gerät mit Skype Raum Systemen v2.
    
2. Starten Sie eine reguläre PowerShell-Eingabeaufforderung auf dem PC.
    
3. Kopieren Sie den Befehlstext aus der Tabelle unten, und fügen Sie ihn an der Eingabeaufforderung ein.
    
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

(Klicken Sie auf eine XML-Konfigurationsdatei oder auf eine Designgrafik)
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Softwareupdates
<a name="SWupdate"> </a>

Skype Raum Systemen v2 versucht, eine Verbindung herzustellen, an den Windows Store zum Abrufen der neuesten Version von Skype Raum v2 Systemsoftware, damit das Gerät regulären Internetzugriff erforderlich ist. Stellen Sie sicher, dass das Skype Raum Systemen v2-Gerät mit der neuesten Version der app, geladen wird, bevor Sie sich an Microsoft Support-Probleme.
  
Standardmäßig wird Skype Raum Systemen v2 Herstellen einer Verbindung mit Windows Update abrufen OS als auch für USB-Peripheriegeräte Firmware Updates und außerhalb der Geschäftszeiten konfigurierten installieren. Sie können Geschäftszeiten konfigurieren, indem Sie sich beim Administratorkonto anmelden und die Einstellungen-App ausführen.
  
Wenn Sie Updates manuell verwalten möchten, und nicht im normale Verfahren für eine [Microsoft Store for Business](https://businessstore.microsoft.com/en-us/store) zu [verteilen offline-apps](https://docs.microsoft.com/en-us/microsoft-store/distribute-offline-apps)haben, können Sie die entsprechende APPX Datei und Abhängigkeiten in [Deployment Kit](https://go.microsoft.com/fwlink/?linkid=851168) (aus abrufen. die Anweisungen zum [Konfigurieren einer Skype Raum Systemen v2 Konsole](../../deploy/deploy-clients/console.md)) mit SCCM verwendet werden kann. Die Deployment Kit-Version Positionen davor befindet hinter der Store-Version, damit es nicht immer den neuesten Build überein kann.
  
### <a name="to-update-using-powershell"></a>Aktualisieren von Powershell

1. Extrahieren Sie das Paket aus der [MSI](https://go.microsoft.com/fwlink/?linkid=851168) -Installation in eine Freigabe für zugegriffen werden.
    
2. Führen Sie das folgende Skript für die Skype Raum Systemen v2-Geräte ändern \<freigeben\> freigeben als Antwort auf das Gerät:
    
  ```
  Add-AppxPackage -Update -ForceApplicationShutdown -Path \\<share>\Rigel\x64\Ship\AppPackages\*\*.appx -DependencyPath (Get-ChildItem \\<share>\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx | Foreach-Object {$_.FullName}) 

  ```

## <a name="admin-mode-and-device-management"></a>Administratormodus und Geräteverwaltung
<a name="AdminMode"> </a>

Für einige Verwaltungsfunktionen, zum Beispiel die manuelle Installation eines privaten Zertifizierungsstellenzertifikats, muss das Surface 4-Gerät in den Administratormodus versetzt werden.  
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-is-running"></a>Wechsel in Administratormodus und zurück, wenn die Skype Raum Systemen v2 app ausgeführt wird

1. Beenden Sie die aktuellen Anrufe, und kehren Sie zum Startbildschirm zurück.
    
2. Klicken Sie auf das Zahnradsymbol und rufen Sie das Menü (Optionen sind **Einstellungen**, **Eingabehilfen**und **Gerät neu starten** ).
    
3. Wählen Sie **Einstellungen** aus.
    
4. Geben Sie das Administratorkennwort ein. Der Setupbildschirm wird angezeigt.
    
    > [!NOTE]
    > Wenn das Gerät nicht Mitglied einer Domäne ist, wird standardmäßig das lokale Administratorkonto (Benutzername „Admin“) verwendet. Das Standardkennwort für dieses Konto lautet „sfb“. Aus Sicherheitsgründen wird jedoch empfohlen, dieses Kennwort so bald wie möglich zu ändern.
Wenn der Computer Mitglied einer Domäne ist, können Sie sich mit einem Domänenkonto mit entsprechenden Berechtigungen anmelden. 
  
5. Klicken Sie in der linken Spalte auf **Windows-Einstellungen**.
    
6. Wählen Sie **Zu Administratoranmeldung wechseln** aus.
    
7. Geben Sie das Administratorkennwort ein. Daraufhin wird die App ordnungsgemäß abgemeldet, und Sie gelangen zum Windows-Anmeldebildschirm. 
    
8. Melden Sie sich mit Ihren Administratoranmeldeinformationen beim Desktop an. Sie verfügen dann über die notwendigen Berechtigungen zum Verwalten des Geräts.
    
9. Führen Sie die notwendigen Administratoraufgaben aus.
    
10. Melden Sie sich bei Ihrem Administratorkonto ab.
    
11. Zurück zu Skype Raum Systemen v2, indem Sie das Symbol Benutzer Konto am linken Rand des Bildschirms auswählen, und wählen Sie **Skype**.
    
    Wenn der Benutzer **Skype** nicht aufgeführt ist, müssen Sie möglicherweise wählen Sie **Benutzer** aus, und geben **. \skype** als den Benutzernamen und das anmelden.
    
 Die Konsole ist nun wieder in den normalen Betrieb-Modus. Das folgende Verfahren benötigen Sie eine Tastatur auf das Gerät anfügen, falls noch nicht angefügt wurde. 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-crashes"></a>Wechsel in Administratormodus und zurück, wenn die Skype Raum Systemen v2 app stürzt ab

1. Drücken Sie fünf Mal schnell hintereinander die WINDOWS-TASTE. Daraufhin gelangen Sie zum Windows-Anmeldebildschirm.  
    
2. Melden Sie sich mit Ihren Administratoranmeldeinformationen beim Desktop an.
    
    > [!NOTE]
    > Bei dieser Methode wird der Skype-Benutzer zwar nicht abgemeldet und die App nicht ordnungsgemäß beendet, aber Sie verwenden diese Methode nur, wenn die App nicht reagiert und die andere Methode nicht verfügbar ist. 
  
3. Führen Sie die notwendigen Administratoraufgaben aus.
    
4. Starten Sie den Computer anschließend neu.
    
 Die Konsole wird neu gestartet, in den normalen Betrieb-Modus, die Skype Raum Systemen v2 app ausgeführt. Sie können die Tastatur entfernen, wenn Sie sie angeschlossen hatten, um dieses Verfahren ausführen zu können.
## <a name="troubleshooting-tips"></a>Tipps zur Problembehandlung
<a name="TS"> </a>

- Besprechungseinladungen werden möglicherweise nicht angezeigt, wenn sie über Domänengrenzen hinaus versendet werden (beispielsweise zwischen zwei Unternehmen). In diesen Fällen müssen IT-Administratoren entscheiden, ob externe Benutzer eine Besprechung planen dürfen.
    
- Skype-Chatroom-Systemen v2 unterstützt Exchange AutoDiscover leitet über Exchange 2010 nicht.
    
- Es empfiehlt sich, dass IT-Administratoren nicht verwendete Audioendpunkte deaktivieren.
    
- Falls ein Spiegelbild in der Raumvorschau angezeigt wird, kann der IT-Administrator dies korrigieren, indem die Stromversorgung der Kamera angestellt wird oder die Bildausrichtung mit der Fernsteuerung der Kamera gekippt wird.
    
- Es ist bekannt, dass der Zugang zum Konsolentouchscreen verloren gehen kann. In solchen Fällen wird durch einen Neustart des Systems der Skype Raum Systemen v2 manchmal das Problem behoben.
    
- Beim Verbinden eines PCs mit der Konsole über verkabelte Erfassung kann ein Verlust der lokalen Audiodaten auftreten. Das Problem mit der Wiedergabe der lokalen Audiodaten kann in diesem Fall durch einen Neustart des PCs gelöst werden.
    
## <a name="see-also"></a>Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.
<a name="TS"> </a>

#### 

[Planen von Skype Raum Systemen v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Bereitstellen von Skype Raum Systemen v2](../../deploy/deploy-clients/room-systems-v2.md)
  
[Konfigurieren einer Skype Raum Systemen v2-Konsole](../../deploy/deploy-clients/console.md)
  
[Verwalten einer Skype Raum v2 Konsole Systemeinstellungen Remote mit einer XML-Konfigurationsdatei](xml-config-file.md)

