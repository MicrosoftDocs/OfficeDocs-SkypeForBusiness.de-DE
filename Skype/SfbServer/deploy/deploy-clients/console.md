---
title: Konfigurieren einer Konsole für Skype Room Systems v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: In diesem Artikel wird beschrieben, wie Sie das Skype Room Systems v2-Konsolengerät und die entsprechenden Peripheriegeräte einrichten.
ms.openlocfilehash: 6ca029fa7f5560dfdfebd789938d9b53ff2e9abc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-skype-room-systems-v2-console"></a>Konfigurieren einer Konsole für Skype Room Systems v2
 
In diesem Artikel wird beschrieben, wie Sie das Skype Room Systems v2-Konsolengerät und die entsprechenden Peripheriegeräte einrichten.
  
Sie sollten nur diese Schritte ausführen, wenn die erforderlichen Skype für Geschäfts- und Exchange-Konten bereits erstellt und getestet werden, wie unter [Bereitstellen von Skype Raum Systemen v2](room-systems-v2.md)beschrieben. Sie benötigen die Hardware und Software in [Skype Raum Systemen v2 Anforderungen](../../plan-your-deployment/clients-and-devices/requirements.md)beschrieben. Dieses Thema enthält die folgenden Abschnitte:
  
- [Vorbereiten des Installationsimages](console.md#Prep_Image)
    
- [Installieren Sie das Zertifikat einen privates auf dem Tablettgerät](console.md#Certs)
    
- [Installieren Sie Windows 10 und die app Skype Raum Systeme v2-Konsole](console.md#Reimage)
   
- [Anfängliche Einrichten der Konsole](console.md#Initial)
    
- [Prüfliste für die Bereitstellung von Skype Raum Systemen v2](console.md#Checklist)
    
> [!NOTE]
> Skype-Chatroom-Systemen v2 funktioniert nur in einer ordnungsgemäß konfigurierten Skype für Business-Umgebung, in dem die Gerät Konten wie unter [Bereitstellen von Skype Raum Systemen v2](room-systems-v2.md)ordnungsgemäß eingerichtet wurden. 
  
## <a name="prepare-the-installation-image"></a>Vorbereiten des Installationsimages
<a name="Prep_Image"> </a>

Installieren der Skype Raum Systemen v2-app in einem Surface Pro 4 oder Surface Pro erfordert ein USB-Speichergerät mit mindestens 32GB Arbeitsspeicher als FAT32 Datenträger formatiert. Es sollte keine anderen Dateien auf dem Gerät, alle vorhandenen Dateien auf den USB-Speicher gehen verloren. 
  
> [!NOTE]
> Wenn das Konsolenimage nicht gemäß diesen Anweisungen erstellt wurde, kann dies zu unerwünschtem Verhalten führen. Update für Windows 10 Enterprise Jahrestag (Version 1607) ist für die Erstellung von Skype Raum Systemen v2 Bild nicht mehr unterstützt. 
  
> [!NOTE]
> Eine vorhandene v2 Skype Raum Systeme mit Windows 10 Enterprise Jahrestag Update verschieben in Skype Raum Systemen v2 Update 3 über die Windows Store ausgeführt werden, jedoch sollte eine neue Installation durchgeführt werden, wie unten beschrieben. 
  
1. Laden Sie die [MSU für KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu).
2. Laden Sie das [Skript CreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842).
3. Platzieren Sie die MSU für KB4056892 im gleichen Verzeichnis befindet wie das Skript CreateSrsMedia.ps1.
4. Führen Sie das Skript CreateSrsMedia.ps1 aus einer Eingabeaufforderung mit erhöhten Rechten auf einem Windows-10-Computer.


Führen Sie das Skript-Anweisungen, um eine Skype Raum Systemen v2 USB-Installationsdiskette erstellen. Nach Abschluss den USB-Datenträger auf Ihrem Computer zu entfernen, und fahren Sie [Windows 10 installieren und die Skype Raum Systemen v2 Konsole app ](console.md#Reimage)fort.
    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a>Installieren von Windows 10 und der Konsolen-App für Skype Room Systems v2 
<a name="Reimage"> </a>

Jetzt müssen Sie das erstellte Image anwenden. Das Tablet wird als Appliance ausgeführt, und der Standard-Benutzer werden nur die Skype Raum Systemen v2 app ausgeführt festgelegt werden. 
  
1. Das Tablet muss mit einer Stromquelle verbunden sein. Beginnen Sie mit dem Gerät im vollständig ausgeschalteten Zustand. Drücken Sie gegebenenfalls den Netzschalter, und halten Sie ihn gedrückt, bis das Tablet ausgeschaltet wird.
    
2. Schließen Sie den USB-Installationsdatenträger an das Tablet an.
    
3. Drücken Sie die Leiser-Taste (-) am Tablet, und halten Sie sie gedrückt. 
    
4. Drücken Sie den Netzschalter am Tablet, und lassen Sie ihn wieder los.
    
5. Wenn Windows Setup gestartet wurde, lassen Sie die Leiser-Taste (-) los.
    
6. Wenn das Skype Raum Systemen v2 Gerät zum ersten Mal startet, das Verhalten hängt welche Version von Sysprep.exe in der Datei AutoUnattend.xml verwendet wird (siehe Schritt 7 [Prepare Abbild der Installation](console.md#Prep_Image)):
    
   - Wenn die /shutdown-Version des Befehls aktiviert wurde, führt das System die Installation fort und fährt zum Schluss herunter. Sobald es heruntergefahren ist, können Sie über externe Medien starten, die Windows PE enthalten, und DISM zum Installieren von Sprachpaketen, Anwenden von Images, Erfassen des Referenzimage vom Computer oder Durchführen anderer Aktionen verwenden.
    
   - Wenn die /reboot-Version des Befehls aktiviert wurde, führt das System die Installation fort und fordert den Benutzer zum Schluss auf, die Gebietsschemaeinstellungen auszuwählen. Nach Abschluss dieser Auswahl, startet das Skype Raum Systemen v2 Gerät in den ersten Startvorgang. Siehe [Anfangssetup der Konsole](console.md#Initial)
    
Nachdem das System heruntergefahren oder neu gestartet wurde, können Sie den USB-Installationsdatenträger gefahrlos entfernen. Jetzt können Sie das Tablet im Dock platzieren und die für Ihren Besprechungsraum benötigten Peripheriegeräte anschließen. Weitere Informationen finden Sie in den Anweisungen des Herstellers.
  
 
### <a name="selecting-a-language-in-creators-update"></a>Auswählen einer Sprache in Creators Update

In Erstellers aktualisieren müssen, verwenden Sie das Skript ApplyCurrentRegionAndLanguage.ps1 in Szenarien, in dem impliziten Sprachauswahl den Benutzer mit dem tatsächlichen Anwendungssprache bietet keine werden sollen (z. B., sie möchten die app in Französisch angezeigt, aber es ist stattfindende nur auf Englisch verfügbar).
  
> [!NOTE]
> Die folgenden Anweisungen gelten nur für Geräte, die mit Windows Creators Update erstellt werden. Für Legacysysteme bzw. auf dem Markt vorhandene Systeme, für die nicht ordnungsgemäß dem neuen Bereitstellungssystem entsprechende neue Images angewendet wurden, können diese Anweisungen nicht verwendet werden. Diese Systeme sollten aber auch nicht von dem anfänglichen Problem betroffen sein, das diesen manuellen Eingriff erforderlich macht (in Anniversary Edition können Sie die App-Sprache beim Setup explizit auswählen). 
  
### <a name="to-apply-your-desired-language"></a>So wenden Sie die gewünschte Sprache an

1. Wechseln Sie in den Administratormodus.
    
2. Wählen Sie das Startmenü aus.
    
3. Wählen Sie das Zahnradsymbol aus, um die App **Einstellungen** zu starten.
    
4. Wählen Sie **Zeit &amp; Sprache**.
    
5. Wählen Sie **Region &amp; Sprache**.
    
6. Wählen Sie **Sprache hinzufügen** aus.
    
7. Wählen Sie die Sprache aus, die Sie hinzufügen möchten.
    
8. Wählen Sie die Sprache, die Sie soeben hinzugefügt, um der Liste "Sprachen haben".
    
9. Wählen Sie **Als Standard** aus.
    
10. Wenn Sie Sprachen entfernen möchten, gehen Sie so vor:
    
    a. Wählen Sie die Sprache aus, die Sie entfernen möchten.
    
    b. Wählen Sie **Entfernen** aus.
    
11. Starten Sie eine Eingabeaufforderung mit erhöhten Rechten.
    
12. Führen Sie den folgenden Befehl aus:  
    
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    
13. Starten Sie das System neu.
    
Die gewünschte Sprache ist jetzt auf das Skype Raum Systemen v2 Gerät angewendet.
## <a name="initial-set-up-of-the-console"></a>Anfangssetup der Konsole 
<a name="Initial"> </a>

Nach der Installation von Windows gehen die Skype Raum Systemen v2-app in seiner ursprünglichen Setup-Prozess beim nächsten Starten, oder wenn die Option/Reboot ausgewählt wurde.
  
1. Daraufhin wird der Bildschirm „Benutzerkonto“ angezeigt. Geben Sie die Skype-Anmeldeadresse des Raumkontos ein, das für das Gerät verwendet werden soll. Verwenden Sie das Format „benutzer@domäne“.
    
2. Geben Sie das Kennwort für das Raumkonto ein, und geben Sie es zur Bestätigung nochmals ein.
    
3. Legen Sie unter "Konfigurieren der Domäne" den FQDN für die Skype für Business Server fest. Wenn die Skype für Business-SIP-Domäne aus der Exchange-Domäne des Benutzers ist, geben Sie die Exchange-Domäne in dieses Feld ein.
    
4. Klicken Sie auf **Weiter**.
    
5. Wählen Sie die angegebenen Geräte auf dem Bildschirm Features, und klicken Sie auf **Weiter**. Standardmäßig ist „Automatische Bildschirmfreigabe“ auf „Ein“ und „Besprechungsnamen ausblenden“ auf „Aus“ festgelegt. Die folgenden Geräte können ausgewählt werden:
    
   - Mikrofon für Konferenzen: Das Standardmikrofon für diesen Konferenzraum
    
   - Lautsprecher für Konferenzen: Der Standardlautspreche für Konferenzen  
    
   - Standardlautsprecher: Der Lautsprecher, der für Audio von der HDMI-Erfassung verwendet wird
    
    Jedes Element verfügt über ein Dropdownmenü mit Optionen, die Sie auswählen können. Sie müssen für jedes Gerät eine Auswahl treffen.
    
6. Klicken Sie auf **Fertig stellen**.
    
Die app Anmelden bei Skype für Business Server 2015 mit den oben eingegebenen Anmeldeinformationen sollten sofort gestartet werden soll, und beginnen soll auch den Kalender mit Exchange diese dieselben Anmeldeinformationen verwenden wird synchronisiert. Ausführliche Informationen zum Verwenden der app finden Sie in der [Hilfe Skype Raum Systeme, Version 2](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).
  
> [!IMPORTANT]
> Skype Raum Systemen v2 erfordert das Vorhandensein von zertifizierten Konsole Hardware (das Logitech SmartDock). Sogar eine ordnungsgemäß erstellte Image, enthält die Skype Raum Systemen v2 app auf einem Surface Pro 4 oder Surface Pro geladen kann nicht nach der Erstinstallation Verfahren starten, es sei denn, die Konsole Hardware erkannt wird. 
  
> [!NOTE]
> Einige nicht englischsprachige Benutzer müssen beim Anfangssetup eine physische Tastatur an die Konsole anschließen, wenn auf der Bildschirmtastatur keine Symbole unterstützt werden. 
  
### <a name="install-a-private-ca-certificate-on-the-tablet-device"></a>Installieren eines Zertifikats einer privaten Zertifizierungsstelle auf dem Tablet
<a name="Certs"> </a>

Das Skype Raum Systemen v2-Gerät muss Zertifikate von der Skype für Geschäfts- und Exchange-Servern, die Verbindung mit verwendet wird. Für Office 365 geschieht dies automatisch, da diese Server öffentliche Zertifizierungsstellen verwenden, denen Windows 10 automatisch vertraut. In dem Fall, in dem die Zertifizierungsstelle privat, ist, für die Instanz einer lokalen Bereitstellung mit Active Directory und die Windows-Zertifizierungsstelle können Sie das Zertifikat zum Skype Raum Systemen v2 Gerät in eine Reihe von Methoden hinzufügen:
  
- Sie können das Gerät mit Active Directory verbinden. Dadurch werden automatisch die erforderlichen Zertifikate hinzugefügt, wenn die Zertifizierungsstelle in Active Directory veröffentlicht ist (normale Bereitstellungsoption).
    
- Sie können das Zertifikat nach der Imageerstellung manuell installieren. Zuvor müssen Sie das [Anfangssetup der Konsole](console.md#Initial) abschließen.  
    
### <a name="to-manually-install-the-certificate"></a>So installieren Sie das Zertifikat manuell 

1. Laden Sie das Zertifizierungsstellenzertifikat auf Ihren Computer herunter, und speichern Sie es unter „C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer“.
    
2. Platzieren Sie die Fläche 4 im Admin-Modus (siehe [Admin-Modus und Gerät Management](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)).
    
3. Führen Sie den folgenden Befehl aus:
    
  ```
  certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
  ```

### <a name="join-an-active-directory-domain-optional"></a>Beitritt zu einer Active Directory-Domäne (optional)
<a name="Certs"> </a>

Sie können an Ihre Domäne Skype Raum Systemen v2 Geräte teilnehmen. Skype Raum Systemen v2 Geräte sollte in einer separaten Organisationseinheit aus Ihrem PC Arbeitsstationen platziert werden, da viele Arbeitsstation Richtlinien nicht mit Skype Raum Systemen v2 kompatibel sind. Ein allgemeines Beispiel sind Erzwingung Kennwortrichtlinien, die verhindern Skype Raum Systemen v2 automatisch gestartet. Informationen über die Verwaltung der Gruppenrichtlinienergebnisse finden Sie unter [Verwalten von Skype Raum Systemen v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md). 
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a>So verbinden Sie Skype Room Systems v2 durch einen Domänenbeitritt mit einer Domäne

1. Melden Sie sich bei der Konsole aus der Administrator beifügen (siehe [Admin-Modus und Gerät Management](../../manage/skype-room-systems-v2/skype-room-systems-v2.md#AdminMode)).
    
2. Starten Sie eine PowerShell-Eingabeaufforderung mit erhöhten Rechten.
    
3. Geben Sie in PowerShell den folgenden Befehl ein:
    
  ```
  Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
  ```

Wenn Ihre vollqualifizierten Domänennamen redmond.corp.microsoft.com und Sie möchten Ihre Skype Raum Systemen v2-Geräte in "Skype Raum Systemen v2" werden beispielsweise Organisationseinheit, die ein untergeordnetes Element des einer OU "Ressourcen" ist der Befehl werden:
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Wenn Sie den Computer umbenennen, wenn sie einer Domäne beitreten möchten, verwenden Sie das NewName - Flag gefolgt von der neue Name des Computers.
  
## <a name="skype-room-systems-v2-deployment-checklist"></a>Bereitstellungsprüfliste für Skype Room Systems v2
<a name="Checklist"> </a>

Vergewissern Sie sich abschließend anhand der folgenden Prüfliste, dass das Konsolengerät und alle Peripheriegeräte vollständig konfiguriert sind:
  
**Anwendungseinstellungen**

|||
|:-----|:-----|
|☐  <br/> |Der Name des Raumkontos und die Telefonnummer (wenn PSTN unterstützt wird) werden rechts oben auf dem Konsolenbildschirm richtig angezeigt.  <br/> |
|☐  <br/> |Der Windows-Computername ist richtig festgelegt (hilfreich für die Remoteverwaltung).  <br/> |
|☐  <br/> |Das Kennwort für das Administratorkonto wurde festgelegt und bestätigt.  <br/> |
|☐  <br/> |Alle Surface Pro 4- oder Surface Pro-Systemupdates wurden angewendet.  <br/> |
   
**A/v-Peripheriegeräte**

|||
|:-----|:-----|
|☐  <br/> |Die Firmwareversion des Kameraperipheriegeräts ist richtig (wenn zutreffend).  <br/> |
|☐  <br/> |Kamera funktionale und optimal positioniert  <br/> |
|☐  <br/> |Die Einstellungen für das Standardwiedergabegerät und das Standardkommunikationsgerät für die Wiedergabe sind auf das gewünschte Audioperipheriegerät festgelegt.  <br/> |
|☐  <br/> |Die Einstellungen für das Standardkommunikationsgerät für Aufnahmen sind auf das gewünschte Audioperipheriegerät festgelegt.  <br/> |
|☐  <br/> |Die Firmwareversion des Audioperipheriegeräts ist richtig (wenn zutreffend).  <br/> |
|☐  <br/> |Das Audioeingabegerät ist funktionsfähig und optimal positioniert.  <br/> |
|☐  <br/> |Das Audioausgabegerät ist funktionsfähig und optimal positioniert.  <br/> |
   
**Andocken**

|||
|:-----|:-----|
|☐  <br/> |Die Kabel sind sicher angeschlossen und nicht eingeklemmt.  <br/> |
|☐  <br/> |Die Audioerfassung über HDMI ist funktionsfähig.  <br/> |
|☐  <br/> |Die Videoerfassung über HDMI ist funktionsfähig.  <br/> |
|☐  <br/> |Das Dock lässt sich frei drehen.  <br/> |
|☐  <br/> |Die Helligkeit des Bildschirms ist für die Umgebung geeignet.  <br/> |
   
## <a name="see-also"></a>Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.
<a name="Checklist"> </a>

#### 

[Planen von Skype Raum Systemen v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Bereitstellen von Skype Raum Systemen v2](room-systems-v2.md)
  
[Konfigurieren einer Skype Raum Systemen v2-Konsole](console.md)
  
[Verwalten von Skype Raum Systemen v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

