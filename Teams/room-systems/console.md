---
title: Konfigurieren einer Microsoft Teams rooms-Konsole
ms.author: v-lanac
author: lanachin
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: In diesem Artikel wird beschrieben, wie Sie die Microsoft Teams rooms-Konsole und Ihre Peripheriegeräte einrichten.
ms.openlocfilehash: c2513bbd86e2754c2e1008195ca1cc050a118882
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306534"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>Konfigurieren einer Microsoft Teams rooms-Konsole

In diesem Artikel wird beschrieben, wie Sie die Microsoft Teams rooms-Konsole und Ihre Peripheriegeräte einrichten.
  
Führen Sie diese Schritte nur aus, wenn die erforderlichen Microsoft Teams oder Skype for Business-und Exchange-Konten bereits erstellt und getestet wurden, wie unter [Bereitstellen von Microsoft Teams-Räumen](room-systems-v2.md)beschrieben. Sie benötigen die in den [Microsoft Teams](requirements.md)-Chatrooms beschriebene Hardware und Software. Dieses Thema enthält die folgenden Abschnitte:
  
- [Vorbereiten der Installationsmedien](console.md#Prep_Media)
- [Installieren eines privaten Zertifizierungsstellenzertifikats auf der Konsole](console.md#Certs)
- [Installieren von Windows 10 und der Microsoft Teams rooms-Konsolen-App](console.md#Reimage)
- [Anfängliche Einrichtung der Konsole](console.md#Initial)
- [Checkliste für Microsoft Teams rooms-Bereitstellung](console.md#Checklist)

> [!NOTE]
> Microsoft Teams-Räume funktionieren nur in einer ordnungsgemäß konfigurierten Microsoft Teams-oder Skype for Business-Umgebung, in der die Geräte Konten ordnungsgemäß eingerichtet sind, wie unter [Bereitstellen von Microsoft Teams-Räumen](room-systems-v2.md)beschrieben wird.
  
## <a name="prepare-the-installation-media"></a>Vorbereiten der Installationsmedien
<a name="Prep_Media"> </a>

Zum Installieren der Microsoft Teams rooms Console-APP ist ein USB-Speichergerät mit mindestens 32 GB Kapazität erforderlich. Auf dem Gerät sollten keine weiteren Dateien vorhanden sein. alle vorhandenen Dateien auf dem USB-Speicher gehen verloren.
  
> [!NOTE]
> Fehler beim Erstellen von Microsoft Teams rooms-Installationsmedien entsprechend diesen Anweisungen führen wahrscheinlich zu unerwartetem Verhalten.

> [!NOTE]
> Nachfolgend wird beschrieben, wie Sie Installationsmedien für die Erstellung von neuen Microsoft Teams rooms-Geräten erstellen. Vorhandene Geräte werden standardmäßig automatisch von Windows Update und dem Windows Store aktualisiert.
  
1. Laden Sie das [CreateSrsMedia. ps1-Skript](https://go.microsoft.com/fwlink/?linkid=867842)herunter.
2. Führen Sie das Skript „CreateSrsMedia.ps1“ an einer Eingabeaufforderung mit erhöhten Rechten auf einem Windows 10-Computer aus.
3. Befolgen Sie die Anweisungen des Skripts, um eine USB-Setupdiskette für Microsoft Teams Rooms zu erstellen.


> [!TIP]
> Jedes Mal, wenn das CreateSrsMedia. ps1-Skript gestartet wird, enthält die Bildschirmausgabe den Namen einer Protokolldatei oder eines Protokoll Protokolls für die Sitzung. Wenn Probleme beim Ausführen des Skripts auftreten, stellen Sie sicher, dass eine Kopie dieser Aufzeichnung zur Verfügung steht, wenn Sie den Support anfordern. 

Das CreateSrsMedia. ps1-Skript automatisiert die folgenden Aufgaben:

1. Laden Sie das neueste MSI-Installationsprogramm für Microsoft Teams-Räume herunter.
2. Ermitteln des Windows-Builds, den der Benutzer bereitstellen muss Die zuletzt veröffentlichten Versionen können oder werden möglicherweise nicht getestet und für die Verwendung mit Microsoft Teams rooms-Geräten unterstützt.
3. Erforderliche unterstützende Komponenten herunterladen.
4. Montieren Sie die erforderlichen Komponenten auf dem Installationsmedium.

Eine bestimmte Version von Windows 10 ist erforderlich, und diese Version steht nur für Volumenlizenzkunden zur Verfügung.  Sie können eine Kopie vom [Volumen Lizenzierungs-Service Center](https://www.microsoft.com/Licensing/servicecenter/)erhalten.

Wenn Sie den Vorgang beenden, entfernen Sie den USB-Datenträger von Ihrem Computer, und fahren Sie mit [der Installation von Windows 10 und der Konsolen-App Microsoft Teams rooms](console.md#Reimage)fort.

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Installieren von Windows 10 und der Microsoft Teams rooms-Konsolen-App
<a name="Reimage"> </a>

Sie müssen nun das von Ihnen erstellte Setup-Medium übernehmen. Das Zielgerät wird als Appliance ausgeführt, und der Standardbenutzer wird so eingestellt, dass nur die Microsoft Teams rooms Console-app ausgeführt wird.

1. Wenn das Zielgerät in einem Dock (z.b. Surface pro) installiert wird, trennen Sie es vom Dock.

2. Stellen Sie sicher, dass das Zielgerät nicht mit dem Netzwerk verbunden ist.

3. Stellen Sie sicher, dass das Zielgerät mit dem Stromnetz verbunden ist.

4. Schließen Sie die USB-Setupdiskette an das Zielgerät an.

5. Starten Sie die USB-Setupdiskette. Weitere Informationen finden Sie in den Anweisungen des Herstellers. Wenn es sich bei Ihrem Zielgerät um einen Surface pro handelt, führen Sie die folgenden Schritte aus, um die USB-Setupdiskette zu starten:

    a. Drücken Sie die Taste, und fahren Sie fort, um die Lautstärketaste (-) zu halten.

    b. Drücken Sie die Power-Taste, und lassen Sie sie los.

    c. Wenn Windows Setup gestartet wurde, lassen Sie die Leiser-Taste (-) los.

8. Sobald die Installation abgeschlossen ist, wird das System beendet.
    
Nachdem das System heruntergefahren wurde, ist es sicher, die USB-Setupdiskette zu entfernen. An dieser Stelle können Sie das Zielgerät in der Docking-Station platzieren (wenn Sie ein Dock-basiertes Produkt verwenden), die für den Besprechungsraum benötigten Peripheriegeräte anschließen und eine Verbindung mit dem Netzwerk herstellen. Weitere Informationen finden Sie in den Anweisungen des Herstellers.
  
### <a name="selecting-a-language"></a>Auswählen einer Sprache 

Im Update des Erstellers müssen Sie das ApplyCurrentRegionAndLanguage. ps1-Skript in Szenarien verwenden, in denen der Benutzer mit der impliziten Sprachauswahl nicht über die tatsächliche Anwendungssprache verfügt, die er verwenden soll (beispielsweise, dass die Konsolen-App auf Französisch bereitgestellt werden soll, aber Es kommt in Englisch vor.)
  
> [!NOTE]
> Die folgenden Anweisungen funktionieren nur für Konsolen, die mit dem Update von Windows Creator erstellt wurden. Legacy/in-Market-Systeme, die nicht mithilfe von Medien mit dem neuen Bereitstellungssystem eingerichtet wurden, können diese Anweisungen nicht verwenden, sollten aber auch nicht unter dem anfänglichen Problem leiden, das diesen manuellen Eingriff erfordert (Anniversary Edition ermöglicht Ihnen, Ihr App-Sprache explizit als Teil des Setups).
  
### <a name="to-apply-your-desired-language"></a>So wenden Sie die gewünschte Sprache an

1. Wechseln Sie in den Administratormodus.
    
2. Wählen Sie das Startmenü aus.
    
3. Wählen Sie das Zahnradsymbol aus, um die App **Einstellungen** zu starten.
    
4. Wählen **Sie &amp; Uhrzeit Sprache**aus.
    
5. Wählen **Sie &amp; Regions Sprache**aus.
    
6. Wählen Sie **Sprache hinzufügen** aus.
    
7. Wählen Sie die Sprache aus, die Sie hinzufügen möchten.
    
8. Wählen Sie die Sprache aus, die Sie soeben in der Liste "Sprachen" hinzugefügt haben.
    
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
    
Die gewünschte Sprache wird nun auf die Microsoft Teams rooms-Konsole angewendet.
## <a name="initial-set-up-of-the-console"></a>Anfängliche Einrichtung der Konsole
<a name="Initial"> </a>

Nach der Installation von Windows geht die Konsolen-App Microsoft Teams Rooms in den ersten Setup Prozess über, wenn Sie als nächstes gestartet wird oder wenn die/Reboot-Option ausgewählt wurde.
  
1. Der Bildschirm Benutzerkonto wird angezeigt. Geben Sie die Skype-Anmeldeadresse (im Format User @ Domain) des für die Konsole zu verwendenden Raum Kontos ein.
    
2. Geben Sie das Kennwort für das Raumkonto ein, und geben Sie es zur Bestätigung nochmals ein.
    
3. Legen Sie unter "Domäne konfigurieren" den FQDN für den Skype for Business-Server ein. Wenn sich die Skype for Business-SIP-Domäne von der Exchange-Domäne des Benutzers unterscheidet, geben Sie die Exchange-Domäne in dieses Feld ein.
    
4. Klicken Sie auf **Weiter**.
    
5. Wählen Sie auf dem Bildschirm Funktionen die angezeigten Geräte aus, und klicken Sie auf **weiter**. Standardmäßig ist „Automatische Bildschirmfreigabe“ auf „Ein“ und „Besprechungsnamen ausblenden“ auf „Aus“ festgelegt. Die folgenden Geräte können ausgewählt werden:
    
   - Mikrofon für Konferenzen: Das Standardmikrofon für diesen Konferenzraum
    
   - Lautsprecher für Konferenzen: Der Standardlautspreche für Konferenzen  
    
   - Standardlautsprecher: Der Lautsprecher, der für Audio von der HDMI-Erfassung verwendet wird
    
     Jedes Element verfügt über ein Dropdownmenü mit Optionen, die Sie auswählen können. Sie müssen für jedes Gerät eine Auswahl treffen.
    
6. Klicken Sie auf **Fertig stellen**.
    
Die Microsoft Teams rooms Console-app sollte sich sofort mit der Anmeldung bei Skype for Business Server mit den oben eingegebenen Anmeldeinformationen beginnen und auch mit der Synchronisierung Ihres Kalenders mit Exchange mit denselben Anmeldeinformationen beginnen. Einzelheiten zur Verwendung der Konsolen-App finden Sie in der [Hilfe zu Microsoft Teams rooms](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).
  
> [!IMPORTANT]
> Microsoft Teams rooms beruht auf dem vorhanden sein zertifizierter Konsolen Hardware. Selbst ein korrekt erstelltes Bild, das die Microsoft Teams rooms-Konsolen-app enthält, wird nicht über den anfänglichen Setupvorgang gestartet, es sei denn, die Konsolen Hardware wird erkannt. Bei Surface pro-basierten Lösungen muss Surface pro mit der dazugehörigen Dock-Hardware verbunden sein, um diese Prüfung durchführen zu können.
  
> [!NOTE]
> Einige Benutzer, die nicht in der englischen Sprache sind, benötigen möglicherweise während der Ersteinrichtung eine physische Tastatur, die mit der Konsole verbunden ist, falls Symbole auf der Bildschirmtastatur nicht unterstützt werden.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Installieren eines privaten Zertifizierungsstellenzertifikats auf der Konsole
<a name="Certs"> </a>

Die Microsoft Teams rooms-Konsole muss den Zertifikaten vertrauen, die von den Servern verwendet werden, mit denen Sie eine Verbindung herstellt. Für Office 365 geschieht dies automatisch, da diese Server öffentliche Zertifizierungsstellen verwenden, denen Windows 10 automatisch vertraut. In einem Fall, in dem die Zertifizierungsstelle privat ist, beispielsweise eine lokale Bereitstellung mit Active Directory und die Windows-Zertifizierungsstelle, können Sie das Zertifikat auf verschiedene Arten zur Konsole Microsoft Teams rooms hinzufügen:
  
- Sie können die Konsole an Active Directory anschließen und automatisch die erforderlichen Zertifikate hinzufügen, wenn die Zertifizierungsstelle in Active Directory veröffentlicht wird (normale Bereitstellungsoption).
    
- Sie können das Zertifikat nach der Imageerstellung manuell installieren. Bevor Sie dies tun, müssen Sie [die erste Einrichtung der Konsole](console.md#Initial)abschließen.
    
### <a name="to-manually-install-the-certificate"></a>So installieren Sie das Zertifikat manuell 

1. Laden Sie das Zertifizierungsstellenzertifikat auf Ihren Computer herunter, und speichern Sie es unter „C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer“.
    
2. Setzen Sie die Konsole in den Administratormodus (siehe [Administratormodus und Geräteverwaltung](room-systems-v2-operations.md#AdminMode)).
    
3. Führen Sie den folgenden Befehl aus:
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Teilnehmen an einer Active Directory-Domäne (optional)
<a name="Certs"> </a>

Sie können an Microsoft Teams rooms-Konsolen an Ihre Domäne teilnehmen. Microsoft Teams rooms-Konsolen sollten in einer separaten ou von Ihren PC-Workstations installiert werden, da viele Arbeitsstations Richtlinien nicht mit Microsoft Teams-Räumen kompatibel sind. Ein allgemeines Beispiel sind Kenn Wort Erzwingungsrichtlinien, die verhindern, dass Microsoft Teams-Räume automatisch gestartet werden. Informationen zur Verwaltung von GPO-Einstellungen finden Sie unter Verwalten von [Microsoft Teams-Räumen](room-systems-v2-operations.md).
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>So nehmen Sie an einer Domäne an Microsoft Teams-Chatrooms Teil

1. Registrieren Sie sich über das Administratorkonto bei der Konsole (siehe [Administratormodus und Geräteverwaltung](room-systems-v2-operations.md#AdminMode)).
    
2. Starten Sie eine PowerShell-Eingabeaufforderung mit erhöhten Rechten.
    
3. Geben Sie in PowerShell den folgenden Befehl ein:
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

Wenn Ihre vollqualifizierte Domäne beispielsweise Redmond.Corp.Microsoft.com ist und Sie möchten, dass sich Ihre Microsoft Teams rooms-Konsolen in einer OU "Microsoft Teams Rooms" befinden, die ein untergeordnetes Element einer "Resources"-ou ist, lautet der Befehl wie folgt:
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Wenn Sie den Computer umbenennen möchten, wenn Sie ihn einer Domäne hinzugefügt haben, verwenden Sie das-Name-Flag, gefolgt vom neuen Namen des Computers.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Checkliste für Microsoft Teams rooms-Bereitstellung
<a name="Checklist"> </a>

Verwenden Sie die folgende Checkliste, während Sie eine abschließende Überprüfung durchführen, dass die Konsole und alle zugehörigen Peripheriegeräte vollständig konfiguriert sind:
  
**Anwendungseinstellungen**

|||
|:-----|:-----|
|☐  <br/> |Der Name des Raumkontos und die Telefonnummer (wenn PSTN unterstützt wird) werden rechts oben auf dem Konsolenbildschirm richtig angezeigt.  <br/> |
|☐  <br/> |Der Windows-Computername ist richtig festgelegt (hilfreich für die Remoteverwaltung).  <br/> |
|☐  <br/> |Das Kennwort für das Administratorkonto wurde festgelegt und bestätigt.  <br/> |
|☐  <br/> |Alle Firmware-Updates wurden angewendet  <br/> |
   
**Audio/Video-Peripheriegeräte**

|||
|:-----|:-----|
|☐  <br/> |Die Firmwareversion des Kameraperipheriegeräts ist richtig (wenn zutreffend).  <br/> |
|☐  <br/> |Kamera funktionell und optimal positioniert  <br/> |
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

[Planen von Microsoft Teams-Räumen](skype-room-systems-v2-0.md)
  
[Bereitstellen von Microsoft Teams-Räumen](room-systems-v2.md)
  
[Konfigurieren einer Microsoft Teams rooms-Konsole](console.md)
  
[Microsoft Teams Rooms verwalten](skype-room-systems-v2.md)
