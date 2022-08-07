---
title: Erstellen eines Microsoft Teams-Räume-Images
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
- Teams_ITAdmin_Rooms
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: In diesem Artikel wird beschrieben, wie Sie die Microsoft Teams-Räume Konsole und ihre Peripheriegeräte einrichten und konfigurieren.
ms.openlocfilehash: 2a38154ebca1dfae282722fdb64e76389627ca15
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270110"
---
# <a name="build-a-microsoft-teams-rooms-image"></a>Erstellen eines Microsoft Teams-Räume-Images

In diesem Artikel wird beschrieben, wie Sie ein Microsoft Teams-Räume Image für die Massenbereitstellung von Teams-Räume erstellen.

> [!NOTE]
> Die folgenden Schritte sollten nur beim Erstellen eines [WIM-basierten Images](/windows-hardware/manufacture/desktop/capture-and-apply-an-image) für die Massenbereitstellung verwendet werden. Wenn Sie einzelne Geräte wiederherstellen, wenden Sie sich an den Oem (Original Equipment Manufacturer), um Support zu erhalten.

Sie sollten diese Schritte nur ausführen, wenn die erforderlichen Microsoft Teams- oder Skype for Business- und Exchange-Konten bereits erstellt und getestet wurden, wie unter [Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md) beschrieben. Sie benötigen die in [Microsoft Teams-Räume Anforderungen](requirements.md) beschriebene Hardware und Software. Dieses Thema enthält die folgenden Abschnitte:
  
- [Vorbereiten des Installationsmediums](console.md#Prep_Media)
- [Installieren eines privaten Zertifizierungsstellenzertifikats auf der Konsole](console.md#Certs)
- [Installieren von Windows 10 und der Microsoft Teams-Räume Konsolen-App](console.md#Reimage)
- [Erstsetup der Konsole](console.md#Initial)
- [Prüfliste für Microsoft Teams-Räume Bereitstellung](console.md#Checklist)

## <a name="prepare-the-installation-media"></a>Vorbereiten des Installationsmediums
<a name="Prep_Media"> </a>

Zum Installieren der Microsoft Teams-Räume Konsolen-App ist ein USB-Speichergerät mit mindestens 32 GB Kapazität erforderlich. Es sollten keine anderen Dateien auf dem Gerät vorhanden sein. alle vorhandenen Dateien auf dem USB-Speicher werden verloren.
  
> [!NOTE]
> Wenn Sie ihre Microsoft Teams-Räume Installationsmedien gemäß diesen Anweisungen nicht erstellen, führt dies wahrscheinlich zu unerwartetem Verhalten.

> [!NOTE]
> Der folgende Prozess dient zum Erstellen von Installationsmedien zum Abbilden neuer Microsoft Teams-Räume Geräten. Vorhandene Geräte werden standardmäßig automatisch aus Windows Update und dem Windows Store aktualisiert.

> [!IMPORTANT]
> Der Windows 10 Computer, der zum Erstellen der Microsoft Teams-Räume Installationsmedien verwendet wird, muss sich auf derselben oder einer höheren Version von Windows wie das Zielinstallationsmedium befinden.
  
1. Laden Sie das [CreateSrsMedia.ps1 Skript](https://go.microsoft.com/fwlink/?linkid=867842) herunter.
2. Führen Sie das Skript „CreateSrsMedia.ps1“ an einer Eingabeaufforderung mit erhöhten Rechten auf einem Windows 10-Computer aus.
3. Befolgen Sie die Anweisungen des Skripts, um einen Microsoft Teams-Räume USB-Setupdatenträger zu erstellen.


> [!TIP]
> Jedes Mal, wenn das CreateSrsMedia.ps1 Skript gestartet wird, enthält die Bildschirmausgabe den Namen einer Protokolldatei oder eines Transkripts für die Sitzung. Wenn Probleme beim Ausführen des Skripts auftreten, stellen Sie sicher, dass eine Kopie dieses Transkripts verfügbar ist, wenn Sie Support anfordern. 

Das CreateSrsMedia.ps1-Skript automatisiert die folgenden Aufgaben:

1. Laden Sie das neueste MSI-Installationsprogramm für Microsoft Teams-Räume herunter.
2. Ermitteln Sie den Build von Windows, den der Benutzer bereitstellen muss. Die zuletzt veröffentlichten Versionen werden möglicherweise getestet und für die Verwendung mit Microsoft Teams-Räume Geräten unterstützt.
3. Laden Sie die erforderlichen unterstützenden Komponenten herunter.
4. Stellen Sie die erforderlichen Komponenten auf dem Installationsmedium zusammen.

> [!NOTE]
Eine bestimmte Version von Windows 10 ist erforderlich, und diese Version ist nur für Volumenlizenzkunden verfügbar.  Sie können eine Kopie aus dem [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/) abrufen.

Wenn Sie fertig sind, entfernen Sie den USB-Datenträger von Ihrem Computer, und fahren [Sie mit der Installation von Windows 10 und der Microsoft Teams-Räume Konsolen-App](console.md#Reimage) fort.

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Installieren von Windows 10 und der Microsoft Teams-Räume Konsolen-App
<a name="Reimage"> </a>

Sie müssen jetzt die von Ihnen erstellten Setupmedien anwenden. Das Zielgerät wird als Appliance ausgeführt, und der Standardbenutzer wird so eingestellt, dass nur die Microsoft Teams-Räume-App ausgeführt wird.

1. Wenn das Zielgerät in einem Dock installiert wird (z. B. ein Surface Pro), trennen Sie es vom Dock.

2. Stellen Sie sicher, dass das Zielgerät nicht mit dem Netzwerk verbunden ist.

3. Stellen Sie sicher, dass das Zielgerät an die Stromversorgung angeschlossen ist.

4. Schließen Sie den USB-Setupdatenträger an das Zielgerät an.

5. Starten Sie den USB-Setupdatenträger. Weitere Informationen finden Sie in den Anweisungen des Herstellers. Wenn Ihr Zielgerät ein Surface Pro ist, führen Sie die folgenden Schritte aus, um den USB-Setupdatenträger zu starten:

    a. Halten Sie die Lautstärke gedrückt (-).

    b. Drücken und lassen Sie den Netzschalter los.

    c. Wenn Windows Setup gestartet wurde, lassen Sie die Leiser-Taste (-) los.

8. Das System wird heruntergefahren, sobald die Installation abgeschlossen ist.
    
Nachdem das System heruntergefahren wurde, ist es sicher, den USB-Setupdatenträger zu entfernen. An diesem Punkt können Sie das Zielgerät im Dock platzieren (wenn Sie ein dockbasiertes Produkt verwenden), die für Ihren Besprechungsraum erforderlichen Peripheriegeräte anfügen und eine Verbindung mit dem Netzwerk herstellen. Weitere Informationen finden Sie in den Anweisungen des Herstellers.

> [!NOTE]
> Softwareupdates für Microsoft Teams-Räume werden automatisch aus dem Microsoft Store für Unternehmen heruntergeladen. Weitere Informationen finden [Sie unter Voraussetzungen für Microsoft Store für Unternehmen und Bildungseinrichtungen](/microsoft-store/prerequisites-microsoft-store-for-business), um zu überprüfen, ob die Raumkonsole auf den Store zugreifen und sich selbst aktualisieren kann.  

### <a name="selecting-a-language"></a>Auswählen einer Sprache 

In Creator's Update müssen Sie das ApplyCurrentRegionAndLanguage.ps1-Skript in Szenarien verwenden, in denen die implizite Sprachauswahl dem Benutzer nicht die gewünschte Anwendungssprache bereitstellt (z. B. soll die Konsolen-App auf Französisch, aber in Englisch verfügbar sein).
  
> [!NOTE]
> Die folgenden Anweisungen funktionieren nur für Konsolen, die mit Windows Creator's Update (Windows 10 20H1) oder höher erstellt wurden.
  
### <a name="to-apply-your-desired-language"></a>So wenden Sie die gewünschte Sprache an

1. Wechseln Sie in den Administratormodus.
    
2. Wählen Sie das Startmenü aus.
    
3. Wählen Sie das Zahnradsymbol aus, um die App **Einstellungen** zu starten.
    
4. Wählen Sie **"Zeitsprache &amp; " aus**.
    
5. **Sprache auswählen**.
    
6. Wählen Sie **Sprache hinzufügen** aus.
    
7. Wählen Sie die Sprache aus, die Sie hinzufügen möchten.
    
8. Installieren Sie Sprachfeatures.
    
9. Aktivieren Sie "Als Windows-Anzeigesprache festlegen" nicht.
    
10. Wählen Sie **"Installieren"** aus.
    
11. Wählen Sie die Sprache aus, die Sie soeben der Liste "Sprachen" hinzugefügt haben.
    
12. Als Standard festlegen- Pfeil nach oben verschieben, um Standard festzulegen

13. Wenn Sie Sprachen entfernen möchten, gehen Sie so vor:
    
    a. Wählen Sie die Sprache aus, die Sie entfernen möchten.
    
    b. Wählen Sie Entfernen aus.

14. Starten Sie eine Eingabeaufforderung mit erhöhten Rechten.

15. Führen Sie den folgenden Befehl aus: 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
16. Starten Sie das System neu.
    
Die gewünschte Sprache wird jetzt auf die Microsoft Teams-Räume Konsole angewendet.
## <a name="initial-set-up-of-the-console"></a>Erstsetup der Konsole
<a name="Initial"> </a>

Nachdem Windows installiert wurde, wechselt die Microsoft Teams-Räume App in den anfänglichen Setupprozess.
  
1. Der Bildschirm "Benutzerkonto" wird angezeigt. Geben Sie die Anmeldeadresse des Microsoft Exchange-Ressourcenkontos (im user@domain Format) des Raumkontos ein, das mit der Konsole verwendet werden soll.
    
2. Geben Sie das Kennwort für das Raumkonto ein, und geben Sie es zur Bestätigung nochmals ein.
   
3. Wählen Sie den unterstützten Besprechungsmodus aus – "Nur Microsoft Teams", "Nur Skype for Business" oder eine der beiden Optionen für den gemischten Modus. Aktivieren Sie bei Bedarf die moderne Authentifizierung.

4. Wählen Sie **"Weiter**" aus.
    
5. Wenn Sie Skype for Business verwenden und wenn sich die Skype for Business SIP-Domäne von der Exchange-Domäne des Benutzers unterscheidet, legen Sie den FQDN für die Skype for Business Server im Abschnitt "Erweitert" fest. Wenn Sie Skype for Business nicht verwenden oder die SIP-Domäne der Exchange-Domäne entspricht, lassen Sie diesen Abschnitt leer.
6. Wählen Sie **"Weiter**" aus.
    
7. Wählen Sie **"Fertig stellen" aus**.
    
Die Microsoft Teams-Räume-App sollte sich bei Microsoft Teams anmelden oder mit den oben eingegebenen Anmeldeinformationen Skype for Business Server und auch mit der Synchronisierung des Kalenders mit Exchange beginnen, indem dieselben Anmeldeinformationen verwendet werden. Ausführliche Informationen zur Verwendung von Teams-Räume finden Sie in der [Microsoft Teams-Räume Hilfe](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).
  
> [!IMPORTANT]
> Microsoft Teams-Räume basiert auf dem Vorhandensein zertifizierter Konsolenhardware. Selbst ein ordnungsgemäß erstelltes Image, das die Microsoft Teams-Räume Konsolen-App enthält, wird erst nach dem anfänglichen Setupvorgang gestartet, wenn die Konsolenhardware erkannt wird. Bei Surface Pro basierten Lösungen muss die Surface Pro mit der zugehörigen Dockhardware verbunden sein, um diese Überprüfung bestehen zu können.
  
> [!NOTE]
> Einige Benutzer in nicht englischer Sprache benötigen möglicherweise während der ersteinrichtung eine physische Tastatur, die mit der Konsole verbunden ist, falls Symbole auf der Bildschirmtastatur nicht unterstützt werden.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Installieren eines privaten Zertifizierungsstellenzertifikats auf der Konsole
<a name="Certs"> </a>
> [!NOTE]
> Folgendes gilt nur, wenn Teams-Räume mit Skype for Business verbunden wird.

Microsoft Teams-Räume muss den Zertifikaten vertrauen, die von den Servern verwendet werden, mit dem die Verbindung hergestellt wird. In einem Fall, in dem die Zertifizierungsstelle privat ist, z. B. eine lokale Bereitstellung mit Active Directory und der Windows-Zertifizierungsstelle, können Sie das Zertifikat auf verschiedene Arten zu Microsoft Teams-Räume hinzufügen:
  
- Sie können die Konsole mit Active Directory verknüpfen, wodurch automatisch die erforderlichen Zertifikate hinzugefügt werden, wenn die Zertifizierungsstelle in Active Directory veröffentlicht wird (normale Bereitstellungsoption).
    
- Sie können das Zertifikat nach der Imageerstellung manuell installieren. Bevor Sie dies tun, müssen Sie [die erst eingerichtete Konsole](console.md#Initial) abschließen.
    
### <a name="to-manually-install-the-certificate"></a>So installieren Sie das Zertifikat manuell 

1. Laden Sie das Zertifizierungsstellenzertifikat auf Ihren Computer herunter, und speichern Sie es unter „C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer“.
    
2. Platzieren Sie die Konsole im Administratormodus (siehe [Admin Modus und Geräteverwaltung](rooms-operations.md#AdminMode)).
    
3. Führen Sie den folgenden Befehl aus:
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Beitreten zu einer Active Directory-Domäne (optional)
<a name="Certs"> </a>

Sie können Microsoft Teams-Räume ihrer Domäne beitreten. Microsoft Teams-Räume sollten in einer separaten Organisationseinheit von Ihren PC-Arbeitsstationen platziert werden, da viele Arbeitsstationsrichtlinien nicht mit Microsoft Teams-Räume kompatibel sind. Ein gängiges Beispiel ist eine Richtlinie zur Kennworterzwingung, die verhindert, dass Microsoft Teams-Räume automatisch gestartet werden. Informationen zur Verwaltung von GPO-Einstellungen finden [Sie unter Verwalten von Microsoft Teams-Räume](rooms-operations.md).
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>So verknüpfen Sie Microsoft Teams-Räume mit einer Domäne

1. Melden Sie sich über das Administratorkonto bei der Konsole an (siehe [Admin Modus und Geräteverwaltung](rooms-operations.md#AdminMode)).
    
2. Starten Sie eine PowerShell-Eingabeaufforderung mit erhöhten Rechten.
    
3. Geben Sie in PowerShell den folgenden Befehl ein:
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, ... ,OU=<Top level OU>,DC=<child domain>,...,DC=<top level domain>"
   ```

Wenn Ihre vollqualifizierte Domäne beispielsweise redmond.corp.microsoft.com ist und Sie möchten, dass sich ihre Microsoft Teams-Räume-Konsolen in einer "Microsoft Teams-Räume"-OU befinden, die ein untergeordnetes Element einer Ou "Resources" ist, lautet der Befehl wie folgt:
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Wenn Sie den Computer umbenennen möchten, wenn Sie ihn einer Domäne hinzufügen, verwenden Sie das Kennzeichen "-NewName" gefolgt vom neuen Namen des Computers.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Prüfliste für Microsoft Teams-Räume Bereitstellung
<a name="Checklist"> </a>

Verwenden Sie die folgende Checkliste, während Sie eine abschließende Überprüfung durchführen, ob die Konsole und alle ihre Peripheriegeräte vollständig konfiguriert sind:
  
**Anwendungseinstellungen**

|Abgeschlossen |Prüfen |
|:-----:|:-----|
|☐   |Raumkontoname und Telefonnummer (wenn PSTN aktiviert) werden ordnungsgemäß angezeigt   |
|☐   |Der Windows-Computername ist richtig festgelegt (hilfreich für die Remoteverwaltung).   |
|☐   |Das Kennwort für das Administratorkonto wurde festgelegt und bestätigt.   |
|☐   |Alle Firmwareupdates wurden angewendet   |
   
**Audio-/Videoperipheriegeräte**

|Abgeschlossen |Prüfen |
|:-----:|:-----|
|☐   |Die Firmwareversion des Kameraperipheriegeräts ist richtig (wenn zutreffend).   |
|☐   |Kamera funktionstüchtig und optimal positioniert   |
|☐   |Die Einstellungen für das Standardwiedergabegerät und das Standardkommunikationsgerät für die Wiedergabe sind auf das gewünschte Audioperipheriegerät festgelegt.   |
|☐   |Die Einstellungen für das Standardkommunikationsgerät für Aufnahmen sind auf das gewünschte Audioperipheriegerät festgelegt.   |
|☐   |Die Firmwareversion des Audioperipheriegeräts ist richtig (wenn zutreffend).   |
|☐   |Das Audioeingabegerät ist funktionsfähig und optimal positioniert.   |
|☐   |Das Audioausgabegerät ist funktionsfähig und optimal positioniert.   |

**Konsole**

|Abgeschlossen |Prüfen |
|:-----:|:-----|
|☐   |Die Kabel sind sicher angeschlossen und nicht eingeklemmt.   |
|☐   |Die Audioerfassung über HDMI ist funktionsfähig.   |
|☐   |Die Videoerfassung über HDMI ist funktionsfähig.   |
|☐   |Konsole kann frei gedreht werden   |



   
## <a name="see-also"></a>Siehe auch
<a name="Checklist"> </a>

[Plan für Microsoft Teams-Räume](rooms-plan.md)
  
[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)
  
[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)
  
[Microsoft Teams-Räume verwalten](rooms-manage.md)
