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
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: In diesem Artikel wird beschrieben, wie Sie die Microsoft Teams Rooms-Konsole und deren Peripheriegeräte einrichten und konfigurieren.
ms.openlocfilehash: 4caa2677eea01ecc96e426692b536aec8563c473
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117573"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>Konfigurieren einer Konsole für Microsoft Teams-Räume

In diesem Artikel wird beschrieben, wie Sie die Microsoft Teams Rooms-Konsole und deren Peripheriegeräte einrichten.
  
Sie sollten diese Schritte nur ausführen, wenn die erforderlichen Microsoft Teams- oder Skype for Business- und Exchange-Konten bereits erstellt und getestet wurden, wie unter Bereitstellen [von Microsoft Teams-Räumen beschrieben.](rooms-deploy.md) Sie benötigen die Hardware und Software, die in [den Microsoft Teams Rooms-Anforderungen beschrieben ist.](requirements.md) Dieses Thema enthält die folgenden Abschnitte:
  
- [Vorbereiten der Installationsmedien](console.md#Prep_Media)
- [Installieren eines zertifikats für private Zertifizierungsstellen auf der Konsole](console.md#Certs)
- [Installieren von Windows 10 und der Microsoft Teams Rooms-Konsolen-App](console.md#Reimage)
- [Erste Einrichtung der Konsole](console.md#Initial)
- [Prüfliste für die Bereitstellung von Microsoft Teams Rooms](console.md#Checklist)

> [!NOTE]
> Microsoft Teams Rooms funktioniert nur in einer ordnungsgemäß konfigurierten Microsoft Teams- oder Skype for Business-Umgebung, in der die Gerätekonten ordnungsgemäß eingerichtet sind, wie unter Bereitstellen von [Microsoft Teams-Räumen beschrieben.](rooms-deploy.md)
  
## <a name="prepare-the-installation-media"></a>Vorbereiten der Installationsmedien
<a name="Prep_Media"> </a>

Für die Installation der Microsoft Teams Rooms-Konsolen-App ist ein USB-Speichergerät mit mindestens 32 GB Kapazität erforderlich. Es sollten keine anderen Dateien auf dem Gerät enthalten sein. alle vorhandenen Dateien auf dem USB-Speicher gehen verloren.
  
> [!NOTE]
> Wenn Sie Ihre Microsoft Teams Rooms-Installationsmedien nicht gemäß diesen Anweisungen erstellen, führt dies wahrscheinlich zu unerwartetem Verhalten.

> [!NOTE]
> Im Folgenden wird das Erstellen von Installationsmedien zum Abbilden neuer Microsoft Teams Rooms-Geräte beschrieben. Vorhandene Geräte werden standardmäßig automatisch aus Windows Update und dem Windows Store aktualisiert.

> [!IMPORTANT]
> Der Windows 10-Computer, der zum Erstellen der Microsoft Teams Rooms-Installationsmedien verwendet wird, muss sich auf derselben oder höher wie die Zielinstallationsmedien befinden.
  
1. Laden Sie das [CreateSrsMedia.ps1 herunter.](https://go.microsoft.com/fwlink/?linkid=867842)
2. Führen Sie das Skript „CreateSrsMedia.ps1“ an einer Eingabeaufforderung mit erhöhten Rechten auf einem Windows 10-Computer aus.
3. Befolgen Sie die Anweisungen des Skripts, um einen Microsoft Teams Rooms USB-Setupdatenträger zu erstellen.


> [!TIP]
> Jedes Mal, CreateSrsMedia.ps1 das Skript gestartet wird, enthält die Bildschirmausgabe den Namen einer Protokolldatei oder eines Transkripts für die Sitzung. Wenn Beim Ausführen des Skripts Probleme auftreten, stellen Sie sicher, dass beim Anfordern des Support eine Kopie dieses Transkripts verfügbar ist. 

Das CreateSrsMedia.ps1 skript automatisiert die folgenden Aufgaben:

1. Laden Sie das neueste MSI-Installationsprogramm für Microsoft Teams Rooms herunter.
2. Bestimmen Sie den Build von Windows, den der Benutzer liefern muss. Die zuletzt veröffentlichten Versionen werden möglicherweise getestet und für die Verwendung mit Microsoft Teams Rooms-Geräten unterstützt.
3. Laden Sie die erforderlichen unterstützenden Komponenten herunter.
4. Stellen Sie die erforderlichen Komponenten auf den Installationsmedien zusammen.

Eine bestimmte Version von Windows 10 ist erforderlich, und diese Version ist nur für Volumenlizenzkunden verfügbar.  Sie können eine Kopie aus dem [Volume Licensing Service Center erhalten.](https://www.microsoft.com/Licensing/servicecenter/)

Wenn Sie fertig sind, entfernen Sie den USB-Datenträger von Ihrem Computer, und fahren Sie mit Installieren von [Windows 10 und der Microsoft Teams Rooms-Konsolen-App fort.](console.md#Reimage)

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Installieren von Windows 10 und der Microsoft Teams Rooms-Konsolen-App
<a name="Reimage"> </a>

Sie müssen nun die von Ihnen erstellten Setupmedien anwenden. Das Zielgerät wird als Gerät ausgeführt, und der Standardbenutzer ist so eingestellt, dass nur die Microsoft Teams Rooms-Konsolen-App ausgeführt wird.

1. Wenn das Zielgerät in einem Dock installiert wird (z. B. ein Surface Pro), trennen Sie es vom Dock.

2. Stellen Sie sicher, dass das Zielgerät nicht mit dem Netzwerk verbunden ist.

3. Stellen Sie sicher, dass das Zielgerät an den Netzstrom angeschlossen ist.

4. Schließen Sie den USB-Setupdatenträger an das Zielgerät an.

5. Starten Sie auf den USB-Setupdatenträger. Weitere Informationen finden Sie in den Anweisungen des Herstellers. Wenn Ihr Zielgerät ein Surface Pro, müssen Sie die folgenden Schritte ausführen, um den USB-Setupdatenträger zu starten:

    a. Halten Sie die Schaltfläche "Volume down" (-) gedrückt, und halten Sie sie gedrückt.

    b. Drücken Sie die Ein/Aus-Taste, und lassen Sie sie los.

    c. Wenn Windows Setup gestartet wurde, lassen Sie die Leiser-Taste (-) los.

8. Das System wird nach Abschluss der Installation heruntergefahren.
    
Nachdem das System heruntergefahren wurde, ist es sicher, den USB-Setupdatenträger zu entfernen. An diesem Punkt können Sie das Zielgerät im Dock platzieren (wenn Sie ein dockbasiertes Produkt verwenden), die für Ihren Besprechungsraum erforderlichen Peripheriegeräte anfügen und eine Verbindung mit dem Netzwerk herstellen. Weitere Informationen finden Sie in den Anweisungen des Herstellers.

> [!NOTE]
> Softwareupdates für Microsoft Teams Rooms werden automatisch aus dem Microsoft Store für Unternehmen heruntergeladen. Unter [Voraussetzungen für Microsoft Store for Business und Education](/microsoft-store/prerequisites-microsoft-store-for-business) können Sie überprüfen, ob die Raumkonsole auf den Store zugreifen und sich selbst aktualisieren kann.  

### <a name="selecting-a-language"></a>Auswählen einer Sprache 

In Creator es Update müssen Sie das ApplyCurrentRegionAndLanguage.ps1-Skript in Szenarien verwenden, in denen die implizite Sprachauswahl dem Benutzer nicht die tatsächliche Anwendungssprache bietet, die er verwenden möchte (z. B. soll die Konsolen-App in Französisch, aber in Englisch angezeigt werden).
  
> [!NOTE]
> Die folgenden Anweisungen funktionieren nur für Konsolen, die mit Windows Creator es Update erstellt wurden. Ältere/in-Markt-Systeme, die mit dem neuen Bereitstellungssystem nicht mithilfe von Medien eingerichtet wurden, können diese Anweisungen nicht verwenden, sollten aber auch nicht unter dem anfänglichen Problem leiden, das dieses manuelle Eingreifen erfordert (Anniversary Edition ermöglicht es Ihnen, Ihre App-Sprache explizit im Rahmen der Einrichtung zu wählen).
  
### <a name="to-apply-your-desired-language"></a>So wenden Sie die gewünschte Sprache an

1. Wechseln Sie in den Administratormodus.
    
2. Wählen Sie das Startmenü aus.
    
3. Wählen Sie das Zahnradsymbol aus, um die App **Einstellungen** zu starten.
    
4. Wählen **Sie &amp; Zeitsprache aus.**
    
5. Wählen Sie **Region &amp; language aus.**
    
6. Wählen Sie **Sprache hinzufügen** aus.
    
7. Wählen Sie die Sprache aus, die Sie hinzufügen möchten.
    
8. Wählen Sie die Sprache aus, die Sie der Liste "Sprachen" hinzugefügt haben.
    
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
    
Die gewünschte Sprache wird jetzt auf die Microsoft Teams Rooms-Konsole angewendet.
## <a name="initial-set-up-of-the-console"></a>Erste Einrichtung der Konsole
<a name="Initial"> </a>

Nach der Installation von Windows wird die Microsoft Teams Rooms-Konsolen-App beim nächsten Start oder bei Auswahl der Option /reboot in den ersten Setupprozess übergehen.
  
1. Der Bildschirm Benutzerkonto wird angezeigt. Geben Sie die Skype-Anmeldeadresse (im user@domain) des Chatkontos ein, das mit der Konsole verwendet werden soll.
    
2. Geben Sie das Kennwort für das Raumkonto ein, und geben Sie es zur Bestätigung nochmals ein.
    
3. Legen Sie unter "Domäne konfigurieren" den FQDN für den Skype for Business Server ein. Wenn sich die Skype for Business SIP-Domäne von der Exchange-Domäne des Benutzers unterscheiden soll, geben Sie in diesem Feld die Exchange-Domäne ein.
    
4. Klicken Sie auf **Weiter**.
    
5. Wählen Sie die angegebenen Geräte auf dem Bildschirm Features aus, und klicken Sie auf **Weiter.** Standardmäßig ist „Automatische Bildschirmfreigabe“ auf „Ein“ und „Besprechungsnamen ausblenden“ auf „Aus“ festgelegt. Die folgenden Geräte können ausgewählt werden:
    
   - Mikrofon für Konferenzen: Das Standardmikrofon für diesen Konferenzraum
    
   - Lautsprecher für Konferenzen: Der Standardlautspreche für Konferenzen  
    
   - Standardlautsprecher: Der Lautsprecher, der für Audio von der HDMI-Erfassung verwendet wird
    
     Jedes Element verfügt über ein Dropdownmenü mit Optionen, die Sie auswählen können. Sie müssen für jedes Gerät eine Auswahl treffen.
    
6. Klicken Sie auf **Fertig stellen**.
    
Die Microsoft Teams Rooms-Konsolen-App sollte sofort mit der Anmeldung bei Skype for Business Server mit den oben eingegebenen Anmeldeinformationen beginnen und auch mit der Synchronisierung des Kalenders mit Exchange mit diesen Anmeldeinformationen beginnen. Details zur Verwendung der Konsolen-App finden Sie in der [Hilfe zu Microsoft Teams Rooms.](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)
  
> [!IMPORTANT]
> Microsoft Teams Rooms basiert auf der Anwesenheit zertifizierter Konsolenhardware. Selbst ein ordnungsgemäß erstelltes Bild mit der Microsoft Teams Rooms-Konsolen-App wird erst gestartet, wenn die Konsolenhardware erkannt wird. Für Surface Pro-basierte Lösungen muss Surface Pro mit der zugehörigen Dockhardware verbunden sein, um diese Überprüfung zu bestehen.
  
> [!NOTE]
> Einige Benutzer in nicht englischer Sprache benötigen möglicherweise eine physische Tastatur, die während der Ersteinrichtung an die Konsole angeschlossen ist, wenn Symbole auf der Bildschirmtastatur nicht unterstützt werden.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Installieren eines zertifikats für private Zertifizierungsstellen auf der Konsole
<a name="Certs"> </a>

Die Microsoft Teams Rooms-Konsole muss den Zertifikaten vertrauen, die von den Servern verwendet werden, mit denen sie eine Verbindung herstellt. Für Office 365 geschieht dies automatisch, da diese Server öffentliche Zertifizierungsstellen verwenden, denen Windows 10 automatisch vertraut. In einem Fall, in dem die Zertifizierungsstelle privat ist, z. B. eine lokale Bereitstellung mit Active Directory und der Windows-Zertifizierungsstelle, können Sie das Zertifikat der Microsoft Teams Rooms-Konsole auf verschiedene Arten hinzufügen:
  
- Sie können der Konsole in Active Directory beitreten und automatisch die erforderlichen Zertifikate hinzufügen, wenn die Zertifizierungsstelle in Active Directory veröffentlicht wird (normale Bereitstellungsoption).
    
- Sie können das Zertifikat nach der Imageerstellung manuell installieren. Bevor Sie dies tun, müssen Sie die [Erste Einrichtung der Konsole abschließen.](console.md#Initial)
    
### <a name="to-manually-install-the-certificate"></a>So installieren Sie das Zertifikat manuell 

1. Laden Sie das Zertifizierungsstellenzertifikat auf Ihren Computer herunter, und speichern Sie es unter „C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer“.
    
2. Platzieren Sie die Konsole im Administratormodus [(siehe Administratormodus und Geräteverwaltung](rooms-operations.md#AdminMode)).
    
3. Führen Sie den folgenden Befehl aus:
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Teilnehmen an einer Active Directory-Domäne (optional)
<a name="Certs"> </a>

Sie können Microsoft Teams Rooms-Konsolen ihrer Domäne beitreten. Microsoft Teams Rooms-Konsolen sollten in einer separaten Organisationseinheit von Ihren PC-Arbeitsstationen platziert werden, da viele Arbeitsstationsrichtlinien nicht mit Microsoft Teams Rooms kompatibel sind. Ein gängiges Beispiel sind Richtlinien zur Kennwortersetzung, die verhindern, dass Microsoft Teams Rooms automatisch gestartet wird. Informationen zur Verwaltung von Gruppenrichtlinieneinstellungen finden Sie unter [Verwalten von Microsoft Teams-Räumen.](rooms-operations.md)
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>So treten Sie Microsoft Teams Rooms einer Domäne bei

1. Melden Sie sich über das Administratorkonto bei der Konsole an (siehe [Administratormodus und Geräteverwaltung](rooms-operations.md#AdminMode)).
    
2. Starten Sie eine PowerShell-Eingabeaufforderung mit erhöhten Rechten.
    
3. Geben Sie in PowerShell den folgenden Befehl ein:
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

Wenn Ihre vollqualifizierte Domäne z. B. redmond.corp.microsoft.com ist und Sich Ihre Microsoft Teams Rooms-Konsolen in einer Ou "Microsoft Teams Rooms" befinden sollen, die ein Untergeordnetes einer Organisationseinheit "Ressourcen" ist, wird der Befehl wie hier ausgeführt:
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Wenn Sie den Computer beim Beitritt zu einer Domäne umbenennen möchten, verwenden Sie das -NewName-Flag gefolgt vom neuen Namen des Computers.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Prüfliste für die Bereitstellung von Microsoft Teams Rooms
<a name="Checklist"> </a>

Verwenden Sie die folgende Prüfliste, während Sie abschließend überprüfen, ob die Konsole und alle Peripheriegeräte vollständig konfiguriert sind:
  
**Anwendungseinstellungen**

|||
|:-----|:-----|
|☐  <br/> |Der Name des Raumkontos und die Telefonnummer (wenn PSTN unterstützt wird) werden rechts oben auf dem Konsolenbildschirm richtig angezeigt.  <br/> |
|☐  <br/> |Der Windows-Computername ist richtig festgelegt (hilfreich für die Remoteverwaltung).  <br/> |
|☐  <br/> |Das Kennwort für das Administratorkonto wurde festgelegt und bestätigt.  <br/> |
|☐  <br/> |Alle Firmwareupdates wurden angewendet  <br/> |
   
**Audio-/Videoperipheriegeräte**

|||
|:-----|:-----|
|☐  <br/> |Die Firmwareversion des Kameraperipheriegeräts ist richtig (wenn zutreffend).  <br/> |
|☐  <br/> |Kamera funktional und optimal positioniert  <br/> |
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

[Plan für Microsoft Teams-Räume](rooms-plan.md)
  
[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)
  
[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)
  
[Microsoft Teams-Räume verwalten](rooms-manage.md)