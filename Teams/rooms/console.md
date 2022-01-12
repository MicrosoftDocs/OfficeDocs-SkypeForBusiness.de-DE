---
title: Konfigurieren einer Konsole für Microsoft Teams-Räume
ms.author: dstrome
author: dstrome
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: In diesem Artikel wird beschrieben, wie Sie die Microsoft Teams-Räume und peripheriegeräte einrichten und konfigurieren.
ms.openlocfilehash: 2df40f136308bb7855d911667bc871e5750f06cd
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767278"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>Konfigurieren einer Konsole für Microsoft Teams-Räume

In diesem Artikel wird beschrieben, wie Sie die Microsoft Teams-Räume und ihre Peripheriegeräte einrichten.

Sie sollten diese Schritte nur ausführen, wenn die erforderlichen Microsoft Teams- oder Skype for Business- und Exchange-Konten bereits erstellt und getestet wurden, wie unter Bereitstellen von Microsoft Teams-Räume [beschrieben.](rooms-deploy.md) Sie benötigen die in den Microsoft Teams-Räume [beschriebene Hardware und Software.](requirements.md) Dieses Thema enthält die folgenden Abschnitte:
  
- [Vorbereiten der Installationsmedien](console.md#Prep_Media)
- [Installieren eines Zertifikats einer privaten Zertifizierungsstelle auf der Konsole](console.md#Certs)
- [Installieren Windows 10 und der Microsoft Teams-Räume-Konsolen-App](console.md#Reimage)
- [Erste Einrichtung der Konsole](console.md#Initial)
- [Microsoft Teams-Räume prüfliste für die Bereitstellung](console.md#Checklist)

## <a name="prepare-the-installation-media"></a>Vorbereiten der Installationsmedien
<a name="Prep_Media"> </a>

Zum Installieren Microsoft Teams-Räume Konsolen-App ist ein USB-Speichergerät mit mindestens 32 GB Kapazität erforderlich. Auf dem Gerät sollten keine weiteren Dateien installiert sein. alle vorhandenen Dateien im USB-Speicher verloren gehen.
  
> [!NOTE]
> Wenn die Installationsmedien Microsoft Teams-Räume Anweisungen nicht erstellt wurden, führt dies wahrscheinlich zu unerwartetem Verhalten.

> [!NOTE]
> Im folgenden Prozess wird das Erstellen von Installationsmedien zum Abbilden neuer Microsoft Teams-Räume erstellt. Vorhandene Geräte werden standardmäßig automatisch über Windows Update und die Windows Store.

> [!IMPORTANT]
> Der Windows 10, der zum Erstellen der Microsoft Teams-Räume-Installationsmedien verwendet wird, muss sich in derselben oder einer höher Windows wie das Zielinstallationsmedium.
  
1. Laden Sie das [CreateSrsMedia.ps1 herunter.](https://go.microsoft.com/fwlink/?linkid=867842)
2. Führen Sie das Skript „CreateSrsMedia.ps1“ an einer Eingabeaufforderung mit erhöhten Rechten auf einem Windows 10-Computer aus.
3. Folgen Sie den Anweisungen des Skripts, um einen USB Microsoft Teams-Räume Zu erstellen.


> [!TIP]
> Jedes Mal, CreateSrsMedia.ps1 das Skript gestartet wird, enthält die Bildschirmausgabe den Namen einer Protokolldatei oder eines Transkripts für die Sitzung. Wenn beim Ausführen des Skripts Probleme auftreten, stellen Sie sicher, dass eine Kopie dieses Transkripts verfügbar ist, wenn Sie den Support anfordern. 

Das CreateSrsMedia.ps1 Skript automatisiert die folgenden Aufgaben:

1. Laden Sie das neueste MSI-Installationsprogramm für Microsoft Teams-Räume.
2. Ermitteln Sie den Build Windows, den der Benutzer liefern muss. Die neuesten Versionen werden möglicherweise getestet und für die Verwendung mit anderen Microsoft Teams-Räume unterstützt.
3. Laden Sie erforderliche unterstützende Komponenten herunter.
4. Stellen Sie die erforderlichen Komponenten auf den Installationsmedien zusammen.

Eine bestimmte Version des Windows 10 ist erforderlich, und diese Version ist nur für Volumenlizenzkunden verfügbar.  Eine Kopie erhalten Sie im [Volume Licensing Service Center.](https://www.microsoft.com/Licensing/servicecenter/)

Wenn Sie fertig sind, entfernen Sie den USB-Datenträger von Ihrem Computer, und fahren Sie mit installieren Windows 10 und der [Microsoft Teams-Räume-App fort.](console.md#Reimage)

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Installieren Windows 10 und der Microsoft Teams-Räume-Konsolen-App
<a name="Reimage"> </a>

Jetzt müssen Sie die von Ihnen erstellten Setupmedien anwenden. Das Zielgerät wird als Gerät ausgeführt, und der Standardbenutzer wird so eingestellt, dass nur die App Microsoft Teams-Räume ausgeführt wird.

1. Wenn das Zielgerät in einem Dock installiert wird (z. B. eine Surface Pro), trennen Sie es von der Docking-Station.

2. Stellen Sie sicher, dass das Zielgerät nicht mit dem Netzwerk verbunden ist.

3. Stellen Sie sicher, dass das Zielgerät mit dem Netzstrom verbunden ist.

4. Schließen Sie den USB-Setup-Datenträger an das Zielgerät an.

5. Starten Sie auf dem USB-Setup-Datenträger. Weitere Informationen finden Sie in den Anweisungen des Herstellers. Wenn es sich bei Ihrem Zielgerät Surface Pro, starten Sie mit den folgenden Schritten auf dem USB-Setup-Datenträger:

    a. Halten Sie die Lautstärketaste gedrückt (-).

    b. Drücken Sie die Ein/Aus-Taste, und lassen Sie sie los.

    c. Wenn Windows Setup gestartet wurde, lassen Sie die Leiser-Taste (-) los.

8. Das System wird nach Abschluss der Installation heruntergefahren.
    
Nach dem Herunterfahren des Systems ist es sicher, den USB-Setupdatenträger zu entfernen. An diesem Punkt können Sie das Zielgerät in seine Docking-Station setzen (wenn Sie ein dockbasiertes Produkt verwenden), die für Ihren Besprechungsraum benötigten Peripheriegeräte anschließen und eine Verbindung mit dem Netzwerk herstellen. Weitere Informationen finden Sie in den Anweisungen des Herstellers.

> [!NOTE]
> Softwareupdates für Microsoft Teams-Räume werden automatisch von der App Microsoft Store für Unternehmen. Unter [Voraussetzungen für Microsoft Store für Unternehmen und Education](/microsoft-store/prerequisites-microsoft-store-for-business) können Sie überprüfen, ob die Raumkonsole auf den Store zugreifen und die App selbst aktualisieren kann.  

### <a name="selecting-a-language"></a>Auswählen einer Sprache 

In Creators Update müssen Sie das ApplyCurrentRegionAndLanguage.ps1-Skript in Szenarien verwenden, in denen die implizite Sprachauswahl dem Benutzer nicht die tatsächliche Anwendungssprache bietet, die er verwenden möchte (z. B. wenn die Konsolen-App in Französisch, aber in Englisch angezeigt wird).
  
> [!NOTE]
> Die folgenden Anweisungen funktionieren nur für Konsolen, die mit Windows Creator's Update erstellt wurden. Ältere/in-Market-Systeme, die mit dem neuen Bereitstellungssystem keine Medien verwendet haben, können diese Anweisungen nicht verwenden, sollten aber auch nicht von dem anfänglichen Problem, das diesen manuellen Eingriff erfordert, leiden (Anniversary Edition ermöglicht es Ihnen, Ihre App-Sprache explizit im Rahmen der Einrichtung zu wählen).
  
### <a name="to-apply-your-desired-language"></a>So wenden Sie die gewünschte Sprache an

1. Wechseln Sie in den Administratormodus.
    
2. Wählen Sie das Startmenü aus.
    
3. Wählen Sie das Zahnradsymbol aus, um die App **Einstellungen** zu starten.
    
4. Wählen Sie **&amp; Zeitsprache aus.**
    
5. Wählen Sie **Region &amp; Sprache aus.**
    
6. Wählen Sie **Sprache hinzufügen** aus.
    
7. Wählen Sie die Sprache aus, die Sie hinzufügen möchten.
    
8. Wählen Sie die Sprache aus, die Sie gerade zur Liste "Sprachen" hinzugefügt haben.
    
9. Wählen Sie **Als Standard** aus.
    
10. Wenn Sie Sprachen entfernen möchten, gehen Sie so vor:
    
    a. Wählen Sie die Sprache aus, die Sie entfernen möchten.
    
    b. Wählen Sie **Entfernen** aus.
    
11. Starten Sie eine Eingabeaufforderung mit erhöhten Rechten.
    
12. Führen Sie den folgenden Befehl aus: 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. Starten Sie das System neu.
    
Die gewünschte Sprache wird nun auf die Microsoft Teams-Räume angewendet.
## <a name="initial-set-up-of-the-console"></a>Erste Einrichtung der Konsole
<a name="Initial"> </a>

Nachdem Windows installiert wurde, geht die Microsoft Teams-Räume-Konsolen-App in den anfänglichen Setupprozess, wenn sie als Nächstes gestartet wird oder die Option /reboot ausgewählt wurde.
  
1. Der Bildschirm Benutzerkonto wird angezeigt. Geben Sie Skype Anmeldeadresse (im user@domain Format) des mit der Konsole zu verwendenden Raumkontos ein.
    
2. Geben Sie das Kennwort für das Raumkonto ein, und geben Sie es zur Bestätigung nochmals ein.
    
3. Legen Sie unter "Domäne konfigurieren" den FQDN für die Skype for Business Server. Wenn sich Skype for Business SIP-Domäne von der Domäne Exchange des Benutzers Exchange, geben Sie die Domäne "Exchange" in dieses Feld ein.
    
4. Klicken Sie auf **Weiter**.
    
5. Wählen Sie die angegebenen Geräte auf dem Bildschirm Features aus, und klicken Sie auf **Weiter.** Standardmäßig ist „Automatische Bildschirmfreigabe“ auf „Ein“ und „Besprechungsnamen ausblenden“ auf „Aus“ festgelegt. Die folgenden Geräte können ausgewählt werden:
    
   - Mikrofon für Konferenzen: Das Standardmikrofon für diesen Konferenzraum
    
   - Lautsprecher für Konferenzen: Der Standardlautspreche für Konferenzen  
    
   - Standardlautsprecher: Der Lautsprecher, der für Audio von der HDMI-Erfassung verwendet wird
    
     Jedes Element verfügt über ein Dropdownmenü mit Optionen, die Sie auswählen können. Sie müssen für jedes Gerät eine Auswahl treffen.
    
6. Klicken Sie auf **Fertig stellen**.
    
Die Microsoft Teams-Räume-Konsolen-App sollte sofort mit der Anmeldung bei Skype for Business Server mit den oben eingegebenen Anmeldeinformationen beginnen und auch damit beginnen, ihren Kalender mit Exchange mit denselben Anmeldeinformationen zu synchronisieren. Details zur Verwendung der Konsolen-App finden Sie in der Microsoft Teams-Räume [.](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)
  
> [!IMPORTANT]
> Microsoft Teams-Räume basiert auf dem Vorhandensein zertifizierter Konsolenhardware. Auch ein ordnungsgemäß erstelltes Bild, das die Microsoft Teams-Räume-Konsolen-App enthält, wird erst gestartet, wenn die Konsolenhardware erkannt wird. Für Surface Pro-basierte Lösungen muss die Surface Pro mit der zugehörigen Dockhardware verbunden sein, um diese Prüfung bestehen zu können.
  
> [!NOTE]
> Einige Benutzer in nicht englischer Sprache benötigen möglicherweise eine physische Tastatur, die während der Ersteinrichtung an die Konsole angeschlossen ist, wenn Symbole auf der Bildschirmtastatur nicht unterstützt werden.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Installieren eines Zertifikats einer privaten Zertifizierungsstelle auf der Konsole
<a name="Certs"> </a>

Die Microsoft Teams-Räume muss den Zertifikaten vertrauen, die von den Servern verwendet werden, mit denen sie eine Verbindung herstellt. Für Office 365 geschieht dies automatisch, da diese Server öffentliche Zertifizierungsstellen verwenden, denen Windows 10 automatisch vertraut. In einem Fall, in dem die Zertifizierungsstelle privat ist, z. B. eine lokale Bereitstellung mit Active Directory und der Windows-Zertifizierungsstelle, können Sie das Zertifikat auf verschiedene Weise zur Microsoft Teams-Räume-Konsole hinzufügen:
  
- Sie können die Konsole zu Active Directory hinzufügen, und die erforderlichen Zertifikate werden automatisch hinzugefügt, wenn die Zertifizierungsstelle in Active Directory veröffentlicht wurde (normale Bereitstellungsoption).
    
- Sie können das Zertifikat nach der Imageerstellung manuell installieren. Bevor Sie dies tun, müssen Sie die [erste Einrichtung der Konsole abschließen.](console.md#Initial)
    
### <a name="to-manually-install-the-certificate"></a>So installieren Sie das Zertifikat manuell 

1. Laden Sie das Zertifizierungsstellenzertifikat auf Ihren Computer herunter, und speichern Sie es unter „C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer“.
    
2. Platzieren Sie die Konsole im Administratormodus (siehe [Administratormodus und Geräteverwaltung).](rooms-operations.md#AdminMode)
    
3. Führen Sie den folgenden Befehl aus:
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Beitreten zu einer Active Directory-Domäne (optional)
<a name="Certs"> </a>

Sie können Ihrer Microsoft Teams-Räume Konsolen beitreten. Microsoft Teams-Räume-Konsolen sollten in einer separaten Organisationseinheit von Ihren PC-Arbeitsstationen platziert werden, da viele Arbeitsstationsrichtlinien nicht mit den Arbeitsstationen kompatibel Microsoft Teams-Räume. Ein häufiges Beispiel sind Richtlinien zur Kennworterwingung, die verhindern, dass Microsoft Teams-Räume automatisch gestartet wird. Informationen zur Verwaltung von Gruppenrichtlinienobjekteinstellungen finden Sie unter [Verwalten Microsoft Teams-Räume.](rooms-operations.md)
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>So treten Sie einer Microsoft Teams-Räume bei

1. Melden Sie sich über das Administratorkonto bei der Konsole an (siehe [Administratormodus und Geräteverwaltung).](rooms-operations.md#AdminMode)
    
2. Starten Sie eine PowerShell-Eingabeaufforderung mit erhöhten Rechten.
    
3. Geben Sie in PowerShell den folgenden Befehl ein:
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

Wenn Ihre vollqualifizierte Domäne z. B. redmond.corp.microsoft.com ist und Sie Ihre Microsoft Teams-Räume-Konsolen in einer "Microsoft Teams-Räume"-Organisationseinheit verwenden möchten, die ein untergeordnetes Kind einer Organisationseinheit "Resources" ist, ist der Befehl wie hier zu sehen:
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Wenn Sie den Computer beim Beitritt zu einer Domäne umbenennen möchten, verwenden Sie das -NewName-Kennzeichen gefolgt vom neuen Namen des Computers.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Microsoft Teams-Räume prüfliste für die Bereitstellung
<a name="Checklist"> </a>

Verwenden Sie die folgende Prüfliste bei der abschließenden Überprüfung, ob die Konsole und alle Peripheriegeräte vollständig konfiguriert sind:
  
**Anwendungseinstellungen**

|Abgeschlossen |Überprüfen |
|:-----:|:-----|
|☐   |Der Name des Raumkontos und die Telefonnummer (wenn PSTN unterstützt wird) werden rechts oben auf dem Konsolenbildschirm richtig angezeigt.   |
|☐   |Der Windows-Computername ist richtig festgelegt (hilfreich für die Remoteverwaltung).   |
|☐   |Das Kennwort für das Administratorkonto wurde festgelegt und bestätigt.   |
|☐   |Alle Firmwareupdates wurden angewendet   |
   
**Audio-/Videoperipheriegeräte**

|Abgeschlossen |Überprüfen |
|:-----:|:-----|
|☐   |Die Firmwareversion des Kameraperipheriegeräts ist richtig (wenn zutreffend).   |
|☐   |Funktion der Kamera und optimale Positionierung   |
|☐   |Die Einstellungen für das Standardwiedergabegerät und das Standardkommunikationsgerät für die Wiedergabe sind auf das gewünschte Audioperipheriegerät festgelegt.   |
|☐   |Die Einstellungen für das Standardkommunikationsgerät für Aufnahmen sind auf das gewünschte Audioperipheriegerät festgelegt.   |
|☐   |Die Firmwareversion des Audioperipheriegeräts ist richtig (wenn zutreffend).   |
|☐   |Das Audioeingabegerät ist funktionsfähig und optimal positioniert.   |
|☐   |Das Audioausgabegerät ist funktionsfähig und optimal positioniert.   |

**Dock**

|Abgeschlossen |Überprüfen |
|:-----:|:-----|
|☐   |Die Kabel sind sicher angeschlossen und nicht eingeklemmt.   |
|☐   |Die Audioerfassung über HDMI ist funktionsfähig.   |
|☐   |Die Videoerfassung über HDMI ist funktionsfähig.   |
|☐   |Das Dock lässt sich frei drehen.   |
|☐   |Die Helligkeit des Bildschirms ist für die Umgebung geeignet.   |


   
## <a name="see-also"></a>Mehr dazu
<a name="Checklist"> </a>

[Plan für Microsoft Teams-Räume](rooms-plan.md)
  
[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)
  
[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)
  
[Microsoft Teams-Räume verwalten](rooms-manage.md)
