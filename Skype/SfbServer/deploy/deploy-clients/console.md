---
title: Konfigurieren einer Microsoft-Teams Räume-Konsole
ms.author: jambirk
author: jambirk
ms.reviewer: Travis-Snoozy
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: In diesem Artikel wird beschrieben, wie die Microsoft-Teams Räume-Konsole und zugehörigen Peripheriegeräte einrichten.
ms.openlocfilehash: fc1d50ffe6dd7415848e02571eab1484bd3dfe22
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012613"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>Konfigurieren einer Microsoft-Teams Räume-Konsole

In diesem Artikel wird beschrieben, wie die Microsoft-Teams Räume-Konsole und zugehörigen Peripheriegeräte einrichten.
  
Sie sollten nur diese Schritte ausführen, wenn die erforderlichen Skype für Geschäfts- und Exchange-Konten bereits erstellt und getestet werden, wie unter [Bereitstellen von Microsoft Teams Chatrooms](room-systems-v2.md)beschrieben. Sie benötigen die Hardware und Software, die in [Microsoft Teams Chatrooms Anforderungen](../../plan-your-deployment/clients-and-devices/requirements.md)beschrieben. Dieses Thema enthält die folgenden Abschnitte:
  
- [Vorbereiten der Installationsmedien](console.md#Prep_Media)
- [Installieren Sie das Zertifikat einen privates in der Konsole](console.md#Certs)
- [Installieren Sie Windows 10 und die Microsoft-Teams Chatrooms Konsole-app](console.md#Reimage)
- [Anfängliche Einrichten der Konsole](console.md#Initial)
- [Prüfliste für die Bereitstellung von Microsoft-Teams Räume](console.md#Checklist)

> [!NOTE]
> Microsoft-Teams Chatrooms funktioniert nur in einer ordnungsgemäß konfigurierten Skype für Business-Umgebung, in dem die Gerät Konten wie unter [Bereitstellen von Microsoft Teams Chatrooms](room-systems-v2.md)ordnungsgemäß eingerichtet wurden.
  
## <a name="prepare-the-installation-media"></a>Vorbereiten der Installationsmedien
<a name="Prep_Media"> </a>

Installieren der Microsoft-Teams Chatrooms Konsole-app erfordert ein USB-Speichergerät mit mindestens 32GB Kapazität. Es sollte keine anderen Dateien auf dem Gerät vorhanden sein. alle vorhandenen Dateien auf den USB-Speicher geht verloren.
  
> [!NOTE]
> Fehler bei die Microsoft-Teams Chatrooms Installationsmedien entsprechend diese Anweisungen wahrscheinlich in unerwartetes Verhalten zu erstellen.

> [!NOTE]
> Der nachfolgend beschriebenen Vorgang ist für das Erstellen Installationsmedium Bild neue Microsoft-Teams Chatrooms Geräte. Vorhandene Geräte aktualisieren standardmäßig automatisch aus Windows Update und den Windows Store.
  
1. Laden Sie das [Skript CreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842).
2. Führen Sie das Skript „CreateSrsMedia.ps1“ an einer Eingabeaufforderung mit erhöhten Rechten auf einem Windows 10-Computer aus.
3. Führen Sie das Skript-Anweisungen, um eine Microsoft-Teams Chatrooms USB-Installationsdiskette erstellen.

> [!CAUTION]
> Der Name des Ordners, den Sie das Medium Erstellungsskript aus ausführen kann keine Leerzeichen enthalten. Das Skript schlägt fehl, wenn ein Leerzeichen in Ordnernamen vorhanden ist.

Das Skript CreateSrsMedia.ps1 automatisiert die folgenden Aufgaben:

1. Laden Sie den neueste Version MSI-Installer für Microsoft-Teams Chatrooms.
2. Bestimmen des Builds von Windows, die der Benutzer eingeben muss. Die am häufigsten kürzlich veröffentlichten Versionen möglicherweise oder möglicherweise nicht getestet und für die Verwendung mit Microsoft-Teams Chatrooms Geräte unterstützt werden.
3. Laden Sie die erforderliche unterstützende Komponenten.
4. Die erforderlichen Komponenten auf dem Installationsmedium zusammenstellen.

Eine bestimmte Version von Windows 10 ist erforderlich, und dieser Version ist nur verfügbar für Volume licensing-Kunden.  Sie können eine Kopie aus dem [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/)abrufen.

Nach Abschluss den USB-Datenträger auf Ihrem Computer zu entfernen, und fahren Sie [Windows 10 installieren und die Microsoft-Teams Räume console app](console.md#Reimage)fort.

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Installieren Sie Windows 10 und die Microsoft-Teams Chatrooms Konsole-app
<a name="Reimage"> </a>

Nun müssen Sie die Setup-Medien anwenden, die Sie erstellt haben. Das Zielgerät wird als Appliance ausgeführt, und der Standard-Benutzer werden nur die Microsoft-Teams Chatrooms Konsole app ausgeführt festgelegt werden.

1. Wenn das Zielgerät in ein (z. B. eine Surface Pro) Andocken installiert wird, trennen sie die Dockingstation.

2. Stellen Sie sicher, dass das Gerät nicht mit dem Netzwerk verbunden ist.

3. Stellen Sie sicher, dass das Gerät mit Strom verbunden ist.

4. Schließen Sie den USB-Setup-Speicher an das Zielgerät.

5. Starten Sie die Installationsdiskette USB. Weitere Informationen finden Sie in den Anweisungen des Herstellers. Wenn Ihr Zielgerät Surface Pro ist, gehen Sie folgendermaßen vor, der USB-Installationsdatenträger zu starten:

    a. Halten Sie weiterhin die Lautstärke (-) gedrückt halten.

    b. Drücken und halten.

    c. Wenn Windows Setup gestartet wurde, lassen Sie die Leiser-Taste (-) los.

8. Das System wird heruntergefahren, sobald die Installation abgeschlossen ist.
    
Nachdem das System heruntergefahren hat, ist es sicher, entfernen Sie die Installationsdiskette USB. Zu diesem Zeitpunkt können Sie seine andocken (bei Verwendung von einem Produkt Andocken-basierte) das Zielgerät versehen, fügen Sie die Peripheriegeräte für Ihre Besprechungsraum erforderlich ist und mit dem Netzwerk verbunden. Weitere Informationen finden Sie in den Anweisungen des Herstellers.
  
### <a name="selecting-a-language"></a>Auswählen einer Sprache 

In Erstellers aktualisieren müssen, verwenden Sie das Skript ApplyCurrentRegionAndLanguage.ps1 in Szenarien, in dem impliziten Sprachauswahl den Benutzer mit dem tatsächlichen Anwendungssprache bietet keine werden sollen (z. B. möchten sie die Konsole-app in Französisch, angezeigt, aber Es ist in Englisch stattfindende).
  
> [!NOTE]
> Die folgenden Anweisungen funktionieren nur für Konsolen mithilfe des Erstellers Windows Update erstellt. Legacy-Market/Systeme, die nicht eingerichtet wurde, die neue Bereitstellungssystem Medien mit werden nicht verwenden Sie diese Anweisungen, jedoch sollten auch nicht leiden unter das anfängliche Problem, das diese manuelle Eingriffe erfordert (Jahrestag Edition können Sie auswählen, Ihre App Sprache explizit als Teil des Setups).
  
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
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. Starten Sie das System neu.
    
Die gewünschte Sprache ist jetzt auf der Microsoft-Teams Chatrooms Konsole angewendet.
## <a name="initial-set-up-of-the-console"></a>Anfängliche Einrichten der Konsole
<a name="Initial"> </a>

Nach der Installation von Windows gehen die Microsoft-Teams Chatrooms Konsole app in seiner ursprünglichen Setup-Prozess beim nächsten Starten, oder wenn die Option/Reboot ausgewählt wurde.
  
1. Der Benutzerkonto Bildschirm wird angezeigt. Geben Sie die Skype-Anmeldeadresse ein (im Format user@domain) des Raums Kontos, das mit der Konsole verwendet werden.
    
2. Geben Sie das Kennwort für das Raumkonto ein, und geben Sie es zur Bestätigung nochmals ein.
    
3. Legen Sie unter "Konfigurieren der Domäne" den FQDN für die Skype für Business Server fest. Wenn die Skype für Business-SIP-Domäne aus der Exchange-Domäne des Benutzers ist, geben Sie die Exchange-Domäne in dieses Feld ein.
    
4. Klicken Sie auf **Weiter**.
    
5. Wählen Sie die angegebenen Geräte auf dem Bildschirm Features, und klicken Sie auf **Weiter**. Standardmäßig ist „Automatische Bildschirmfreigabe“ auf „Ein“ und „Besprechungsnamen ausblenden“ auf „Aus“ festgelegt. Die folgenden Geräte können ausgewählt werden:
    
   - Mikrofon für Konferenzen: Das Standardmikrofon für diesen Konferenzraum
    
   - Lautsprecher für Konferenzen: Der Standardlautspreche für Konferenzen  
    
   - Standardlautsprecher: Der Lautsprecher, der für Audio von der HDMI-Erfassung verwendet wird
    
     Jedes Element verfügt über ein Dropdownmenü mit Optionen, die Sie auswählen können. Sie müssen für jedes Gerät eine Auswahl treffen.
    
6. Klicken Sie auf **Fertig stellen**.
    
Die Microsoft-Teams Chatrooms Konsole app Anmelden bei Skype für Business Server mit den oben eingegebenen Anmeldeinformationen sollten sofort gestartet werden soll, und beginnen soll auch den Kalender mit Exchange diese dieselben Anmeldeinformationen verwenden wird synchronisiert. Ausführliche Informationen zum Verwenden der Verwaltungskonsole app finden Sie in der [Hilfe von Microsoft Teams Chatrooms](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).
  
> [!IMPORTANT]
> Microsoft-Teams Chatrooms erfordert das Vorhandensein von zertifizierten Konsole Hardware. Selbst ein Bild ordnungsgemäß erstellte, enthält die Microsoft-Teams Chatrooms Konsole app startet nicht nach der Erstinstallation Verfahren, wenn die Konsole Hardware erkannt wird. Für Surface Pro-basierte Lösungen muss die Surface Pro für die zugehörige Andocken Hardware, übergeben dieses Kontrollkästchen verbunden sein.
  
> [!NOTE]
> Möglicherweise benötigen einige Benutzer nicht-englischen eine physische Tastatur während des Setups mit der Konsole verbunden, Symbole auf der Bildschirmtastatur nicht unterstützt werden.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Installieren Sie das Zertifikat einen privates in der Konsole
<a name="Certs"> </a>

Zertifikate wird von der Skype für Geschäfts- und Exchange-Servern, die Verbindung mit muss die Microsoft-Teams Chatrooms Konsole. Für Office 365 geschieht dies automatisch, da diese Server öffentliche Zertifizierungsstellen verwenden, denen Windows 10 automatisch vertraut. In dem Fall, in dem die Zertifizierungsstelle privat, ist, für die Instanz einer lokalen Bereitstellung mit Active Directory und die Windows-Zertifizierungsstelle können Sie das Zertifikat auf der Microsoft-Teams Räume-Konsole in eine Reihe von Methoden hinzufügen:
  
- Sie können die Konsole Active Directory teilnehmen und, die werden automatisch hinzugefügt, die erforderlichen Zertifikate erhält der Zertifizierungsstelle auf Active Directory (normale Bereitstellungsoption) veröffentlicht wird.
    
- Sie können das Zertifikat nach der Imageerstellung manuell installieren. Bevor Sie dies tun, müssen Sie die [Initial Einrichten der Konsole](console.md#Initial)durchführen.
    
### <a name="to-manually-install-the-certificate"></a>So installieren Sie das Zertifikat manuell 

1. Laden Sie das Zertifizierungsstellenzertifikat auf Ihren Computer herunter, und speichern Sie es unter „C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer“.
    
2. Platzieren Sie die Konsole im Admin-Modus (siehe [Admin-Modus und Gerät Management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).
    
3. Führen Sie den folgenden Befehl aus:  
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Teilnehmen an einer Active Directory-Domäne (Optional)
<a name="Certs"> </a>

Sie können Microsoft Teams Chatrooms Konsolen an Ihre Domäne beitreten. Microsoft-Teams Chatrooms Konsolen sollte in einer separaten Organisationseinheit aus Ihrem PC Arbeitsstationen platziert werden, da viele Arbeitsstation Richtlinien nicht kompatibel mit Microsoft-Teams Räumen sind. Ein allgemeines Beispiel sind Erzwingung Kennwortrichtlinien, die Microsoft-Teams Chatrooms verhindern automatisch gestartet. Informationen über die Verwaltung der Gruppenrichtlinienergebnisse finden Sie unter [Verwalten von Microsoft Teams Räumen](../../manage/skype-room-systems-v2/room-systems-v2-operations.md).
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>Microsoft-Teams Chatrooms einer Domäne beitreten

1. Melden Sie sich bei der Konsole aus der Administrator beifügen (siehe [Admin-Modus und Gerät Management](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).
    
2. Starten Sie eine PowerShell-Eingabeaufforderung mit erhöhten Rechten.
    
3. Geben Sie in PowerShell den folgenden Befehl ein:
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

Wenn Ihre vollqualifizierten Domänennamen redmond.corp.microsoft.com und Sie möchten die Microsoft-Teams Chatrooms Konsolen in einer Organisationseinheit "Microsoft-Teams Rooms" sein, die ein untergeordnetes Element des einer OU "Ressourcen" ist, kann beispielsweise der Befehl werden:
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Wenn Sie den Computer umbenennen, wenn sie einer Domäne beitreten möchten, verwenden Sie das NewName - Flag gefolgt von der neue Name des Computers.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Prüfliste für die Bereitstellung von Microsoft-Teams Räume
<a name="Checklist"> </a>

Verwenden Sie die folgende Checkliste, während eine endgültige Überprüfung, dass die Konsole und alle zugehörigen Peripheriegeräte konfiguriert sind:
  
**Anwendungseinstellungen**

|||
|:-----|:-----|
|☐  <br/> |Der Name des Raumkontos und die Telefonnummer (wenn PSTN unterstützt wird) werden rechts oben auf dem Konsolenbildschirm richtig angezeigt.  <br/> |
|☐  <br/> |Der Windows-Computername ist richtig festgelegt (hilfreich für die Remoteverwaltung).  <br/> |
|☐  <br/> |Das Kennwort für das Administratorkonto wurde festgelegt und bestätigt.  <br/> |
|☐  <br/> |Alle Firmwareupdates wurden angewendet  <br/> |
   
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
   
**Dock**

|||
|:-----|:-----|
|☐  <br/> |Die Kabel sind sicher angeschlossen und nicht eingeklemmt.  <br/> |
|☐  <br/> |Die Audioerfassung über HDMI ist funktionsfähig.  <br/> |
|☐  <br/> |Die Videoerfassung über HDMI ist funktionsfähig.  <br/> |
|☐  <br/> |Das Dock lässt sich frei drehen.  <br/> |
|☐  <br/> |Die Helligkeit des Bildschirms ist für die Umgebung geeignet.  <br/> |
   
## <a name="see-also"></a>Siehe auch
<a name="Checklist"> </a>

[Planen der Microsoft-Teams, Räume](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Bereitstellen von Microsoft-Teams, Räume](room-systems-v2.md)
  
[Konfigurieren einer Microsoft-Teams Räume-Konsole](console.md)
  
[Verwalten von Microsoft-Teams, Räume](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)