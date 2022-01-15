---
title: Erstellen eines Microsoft Teams-Räume Bilds
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
description: In diesem Artikel wird beschrieben, wie Sie die Microsoft Teams-Räume und ihre Peripheriegeräte einrichten und konfigurieren.
ms.openlocfilehash: d6c675ed6eb6f50cf41b817770caf723f75f556b
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055645"
---
# <a name="build-a-microsoft-teams-rooms-image"></a>Erstellen eines Microsoft Teams-Räume Bilds

In diesem Artikel wird beschrieben, wie Sie Microsoft Teams-Räume Bild für die Massenbereitstellung von Teams-Räume.

> [!NOTE]
> Die folgenden Schritte sollten nur beim Erstellen eines [WIM-basierten Bilds](/windows-hardware/manufacture/desktop/capture-and-apply-an-image) für die Massenbereitstellung verwendet werden. Wenn Sie einzelne Geräte wiederherstellen, wenden Sie sich an den Oem, um Unterstützung zu erhalten.

Sie sollten diese Schritte nur ausführen, wenn die erforderlichen Microsoft Teams- oder Skype for Business- und Exchange-Konten bereits erstellt und getestet wurden, wie unter Bereitstellen von Microsoft Teams-Räume [beschrieben.](rooms-deploy.md) Sie benötigen die Hardware und Software, die in den Microsoft Teams-Räume [ist.](requirements.md) Dieses Thema enthält die folgenden Abschnitte:
  
- [Vorbereiten der Installationsmedien](console.md#Prep_Media)
- [Installieren eines Zertifikats einer privaten Zertifizierungsstelle auf der Konsole](console.md#Certs)
- [Installieren Windows 10 und der Microsoft Teams-Räume-Konsolen-App](console.md#Reimage)
- [Erste Einrichtung der Konsole](console.md#Initial)
- [Microsoft Teams-Räume prüfliste für die Bereitstellung](console.md#Checklist)

## <a name="prepare-the-installation-media"></a>Vorbereiten der Installationsmedien
<a name="Prep_Media"> </a>

Zum Installieren Microsoft Teams-Räume-Konsolen-App ist ein USB-Speichergerät mit mindestens 32 GB Kapazität erforderlich. Auf dem Gerät sollten keine weiteren Dateien installiert sein. alle vorhandenen Dateien im USB-Speicher verloren gehen.
  
> [!NOTE]
> Wenn die Installationsmedien Microsoft Teams-Räume Anweisungen nicht erstellt wurden, führt dies wahrscheinlich zu unerwartetem Verhalten.

> [!NOTE]
> Im folgenden Prozess wird das Erstellen von Installationsmedien zum Abbilden neuer Microsoft Teams-Räume-Geräten erläutert. Vorhandene Geräte werden standardmäßig automatisch über Windows Update und die Windows Store.

> [!IMPORTANT]
> Der Windows 10, der zum Erstellen der Microsoft Teams-Räume-Installationsmedien verwendet wird, muss sich mit derselben oder einer späteren Version von Windows wie das Zielinstallationsmedium haben.
  
1. Laden Sie das [CreateSrsMedia.ps1 herunter.](https://go.microsoft.com/fwlink/?linkid=867842)
2. Führen Sie das Skript „CreateSrsMedia.ps1“ an einer Eingabeaufforderung mit erhöhten Rechten auf einem Windows 10-Computer aus.
3. Folgen Sie den Anweisungen des Skripts, um einen USB Microsoft Teams-Räume-Setup-Datenträger zu erstellen.


> [!TIP]
> Jedes Mal, CreateSrsMedia.ps1 das Skript gestartet wird, enthält die Bildschirmausgabe den Namen einer Protokolldatei oder eines Transkripts für die Sitzung. Wenn beim Ausführen des Skripts Probleme auftreten, stellen Sie sicher, dass eine Kopie dieses Transkripts verfügbar ist, wenn Sie den Support anfordern. 

Das CreateSrsMedia.ps1 Skript automatisiert die folgenden Aufgaben:

1. Laden Sie das neueste MSI-Installationsprogramm für Microsoft Teams-Räume.
2. Ermitteln Sie den Build Windows, den der Benutzer liefern muss. Die neuesten Versionen werden möglicherweise getestet und für die Verwendung mit anderen Microsoft Teams-Räume unterstützt.
3. Laden Sie erforderliche unterstützende Komponenten herunter.
4. Stellen Sie die erforderlichen Komponenten auf den Installationsmedien zusammen.

> [!NOTE]
Eine bestimmte Version des Windows 10 ist erforderlich, und diese Version ist nur für Volumenlizenzkunden verfügbar.  Eine Kopie erhalten Sie im [Volume Licensing Service Center.](https://www.microsoft.com/Licensing/servicecenter/)

Wenn Sie fertig sind, entfernen Sie den USB-Datenträger von Ihrem Computer, und fahren Sie mit installieren Windows 10 und der [Microsoft Teams-Räume-App fort.](console.md#Reimage)

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Installieren Windows 10 und der Microsoft Teams-Räume-Konsolen-App
<a name="Reimage"> </a>

Jetzt müssen Sie die von Ihnen erstellten Setupmedien anwenden. Das Zielgerät wird als Gerät ausgeführt, und der Standardbenutzer wird so eingestellt, dass nur die App Microsoft Teams-Räume wird.

1. Wenn das Zielgerät in einem Dock installiert wird (z. B. eine Surface Pro), trennen Sie es von der Docking-Station.

2. Stellen Sie sicher, dass das Zielgerät nicht mit dem Netzwerk verbunden ist.

3. Stellen Sie sicher, dass das Zielgerät mit dem Netzstrom verbunden ist.

4. Schließen Sie den USB-Setup-Datenträger an das Zielgerät an.

5. Starten Sie auf dem USB-Setup-Datenträger. Weitere Informationen finden Sie in den Anweisungen des Herstellers. Wenn es sich bei Ihrem Zielgerät um Surface Pro, starten Sie mit den folgenden Schritten auf dem USB-Setup-Datenträger:

    a. Halten Sie die Lautstärketaste gedrückt (-).

    b. Drücken Sie die Ein/Aus-Taste, und lassen Sie sie los.

    c. Wenn Windows Setup gestartet wurde, lassen Sie die Leiser-Taste (-) los.

8. Das System wird nach Abschluss der Installation heruntergefahren.
    
Nach dem Herunterfahren des Systems ist es sicher, den USB-Setupdatenträger zu entfernen. An diesem Punkt können Sie das Zielgerät in seine Docking-Station setzen (wenn Sie ein dockbasiertes Produkt verwenden), die für Ihren Besprechungsraum benötigten Peripheriegeräte anschließen und eine Verbindung mit dem Netzwerk herstellen. Weitere Informationen finden Sie in den Anweisungen des Herstellers.

> [!NOTE]
> Softwareupdates für Microsoft Teams-Räume werden automatisch von der App Microsoft Store für Unternehmen. Unter [Voraussetzungen für Microsoft Store für Unternehmen und Education](/microsoft-store/prerequisites-microsoft-store-for-business) können Sie überprüfen, ob die Raumkonsole auf den Store zugreifen und die App selbst aktualisieren kann.  

### <a name="selecting-a-language"></a>Auswählen einer Sprache 

In Creators Update müssen Sie das ApplyCurrentRegionAndLanguage.ps1-Skript in Szenarien verwenden, in denen die implizite Sprachauswahl dem Benutzer nicht die tatsächliche Anwendungssprache bietet, die er möchte (z. B. wenn die Konsolen-App in Französisch, aber in Englisch angezeigt wird).
  
> [!NOTE]
> Die folgenden Anweisungen funktionieren nur für Konsolen, die mit Windows Creator's Update (Windows 10 20H1) oder höher erstellt wurden.
  
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

Nachdem Windows installiert wurde, Microsoft Teams-Räume die App in den anfänglichen Setupprozess.
  
1. Der Bildschirm Benutzerkonto wird angezeigt. Geben Sie die Anmeldeadresse Exchange Microsoft Exchange-Ressourcenkontos (im user@domain-Format) des Raumkontos ein, das mit der Konsole verwendet werden soll.
    
2. Geben Sie das Kennwort für das Raumkonto ein, und geben Sie es zur Bestätigung nochmals ein.
   
3. Wählen Sie den unterstützten Besprechungsmodus Microsoft Teams, Skype for Business Oder eine der beiden Optionen für gemischten Modus aus. Aktivieren Sie bei Bedarf die moderne Authentifizierung.

4. Klicken Sie auf **Weiter**.
    
5. Wenn Sie Skype for Business verwenden und sich die SIP-Domäne Skype for Business von der Exchange-Domäne des Benutzers unterscheiden, legen Sie im Abschnitt Erweitert den FQDN für die Skype for Business Server-Domäne ein. Wenn Sie eine Domäne nicht Skype for Business oder die SIP-Domäne der Domäne Exchange, lassen Sie diesen Abschnitt leer.
6. Klicken Sie auf **Weiter**.
    
7. Klicken Sie auf **Fertig stellen**.
    
Die Microsoft Teams-Räume-App sollte sich mit den oben eingegebenen Anmeldeinformationen bei Microsoft Teams oder Skype for Business Server anmelden und außerdem mit der Synchronisierung ihres Kalenders mit Exchange mit denselben Anmeldeinformationen beginnen. Details zur Verwendung von Teams-Räume finden Sie in der Microsoft Teams-Räume [Hilfe.](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)
  
> [!IMPORTANT]
> Microsoft Teams-Räume basiert auf dem Vorhandensein zertifizierter Konsolenhardware. Selbst ein ordnungsgemäß erstelltes Bild, das die Microsoft Teams-Räume-Konsolen-App enthält, wird erst gestartet, wenn die Konsolenhardware erkannt wird. Für Surface Pro-basierte Lösungen muss die Surface Pro mit der zugehörigen Dockhardware verbunden sein, um diese Prüfung bestehen zu können.
  
> [!NOTE]
> Einige Benutzer in nicht englischer Sprache benötigen möglicherweise eine physische Tastatur, die während der Ersteinrichtung an die Konsole angeschlossen ist, wenn Symbole auf der Bildschirmtastatur nicht unterstützt werden.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Installieren eines Zertifikats einer privaten Zertifizierungsstelle auf der Konsole
<a name="Certs"> </a>
> [!NOTE]
> Folgendes gilt nur, wenn Sie Teams-Räume mit Skype for Business.

Microsoft Teams-Räume muss den Zertifikaten vertrauen, die von den Servern verwendet werden, mit denen die Verbindung hergestellt wird. In einem Fall, in dem die Zertifizierungsstelle privat ist, z. B. eine lokale Bereitstellung mit Active Directory und der Windows-Zertifizierungsstelle, können Sie das Zertifikat auf verschiedene Arten zu Microsoft Teams-Räume hinzufügen:
  
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

Sie können ihrer Microsoft Teams-Räume beitreten. Microsoft Teams-Räume sollten in einer separaten Organisationseinheit von den Arbeitsstationen Ihres PCs platziert werden, da viele Arbeitsstationsrichtlinien nicht mit den Arbeitsstationen kompatibel Microsoft Teams-Räume. Ein häufiges Beispiel sind Richtlinien zur Kennworterwingung, die verhindern, dass Microsoft Teams-Räume automatisch gestartet wird. Informationen zur Verwaltung von Gruppenrichtlinienobjekteinstellungen finden Sie unter Verwalten [Microsoft Teams-Räume.](rooms-operations.md)
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>So treten Sie Microsoft Teams-Räume Domäne bei

1. Melden Sie sich über das Administratorkonto bei der Konsole an (siehe [Administratormodus und Geräteverwaltung).](rooms-operations.md#AdminMode)
    
2. Starten Sie eine PowerShell-Eingabeaufforderung mit erhöhten Rechten.
    
3. Geben Sie in PowerShell den folgenden Befehl ein:
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

Wenn Ihre vollqualifizierte Domäne z. B. redmond.corp.microsoft.com ist und Sie Ihre Microsoft Teams-Räume-Konsolen in einer "Microsoft Teams-Räume"-Organisationseinheit verwenden möchten, die ein untergeordnetes Kind einer "Resources"-OU ist, ist der Befehl wie hier zu sehen:
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Wenn Sie den Computer beim Beitritt zu einer Domäne umbenennen möchten, verwenden Sie das -NewName-Kennzeichen gefolgt vom neuen Namen des Computers.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Microsoft Teams-Räume der Bereitstellung
<a name="Checklist"> </a>

Verwenden Sie die folgende Prüfliste bei der abschließenden Überprüfung, ob die Konsole und alle Peripheriegeräte vollständig konfiguriert sind:
  
**Anwendungseinstellungen**

|Abgeschlossen |Überprüfen |
|:-----:|:-----|
|☐   |Name des Raumkontos und Telefonnummer # (wenn PSTN aktiviert ist) werden richtig angezeigt   |
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

**Konsole**

|Abgeschlossen |Überprüfen |
|:-----:|:-----|
|☐   |Die Kabel sind sicher angeschlossen und nicht eingeklemmt.   |
|☐   |Die Audioerfassung über HDMI ist funktionsfähig.   |
|☐   |Die Videoerfassung über HDMI ist funktionsfähig.   |
|☐   |Konsole kann frei gedreht werden   |



   
## <a name="see-also"></a>Mehr dazu
<a name="Checklist"> </a>

[Plan für Microsoft Teams-Räume](rooms-plan.md)
  
[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)
  
[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)
  
[Microsoft Teams-Räume verwalten](rooms-manage.md)
