---
title: Einrichten koordinierter Besprechungen mit Microsoft Teams-Räume und Surface Hub
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Konfigurieren Sie Teams-Räume Geräte und Surface Hub für die Teilnahme an Besprechungen, wenn ein Gerät oder das andere an einer Besprechung teilnimmt.
ms.openlocfilehash: f34e3637c9c9716c6f8ec87865c3c570820a0357
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270480"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Einrichten koordinierter Besprechungen mit Microsoft Teams-Räume und Surface Hub

Wenn ein oder mehrere Microsoft Teams-Räume-Geräte oder Surface Hubs in einem Besprechungsraum vorhanden sind, können Sie koordinierte Besprechungen einrichten. Mithilfe koordinierter Besprechungen können Sie Ihre Teams-Räume-Geräte und Surface Hubs so einrichten, dass bei der Teilnahme an einer Besprechung auf einem Gerät auch die anderen Geräte im Raum mit derselben Besprechung verbunden sind. Sie können Ihre Kameras, Lautsprecher und Mikrofone so konfigurieren, dass diejenigen, die den Teilnehmern die beste Erfahrung bieten, aktiviert werden, während andere deaktiviert sind. Dies vermeidet das gefürchtete Echo und Feedback-Rauschen, das Teilnehmer beim Hinzufügen mehrerer Geräte zu einer Besprechung erleben können.

Um koordinierte Besprechungen einzurichten, müssen Sie sicherstellen, dass Ihre Teams-Räume Geräte und Surface Hubs bereits ordnungsgemäß für die Teilnahme an Besprechungen konfiguriert sind. Am wichtigsten ist, dass jedes Gerät über ein eigenes Exchange-Raumpostfach verfügen muss. Informationen zum Einrichten finden Sie in den folgenden Artikeln:

- [Bereitstellen von Microsoft Teams-Räume](../rooms/rooms-deploy.md)
- [Erstellen eines Surface Hub 2S-Gerätekontos](/surface-hub/surface-hub-2s-account)

Nachdem Sie bestätigt haben, dass Ihre Teams-Räume-Geräte und Surface Hubs Besprechungen automatisch annehmen und erfolgreich daran teilnehmen können, können Sie koordinierte Besprechungen einrichten.

Die folgenden Schritte sollten für jeden Besprechungsraum separat ausgeführt werden.

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>Schritt 1: Planen der koordinierten Besprechungserfahrung

Bevor Sie Konfigurationsänderungen vornehmen, müssen Sie entscheiden, welche Geräte in jedem Besprechungsraum was tun. Bei einem bestimmten Besprechungsraum müssen Sie also entscheiden, welches Gerät über das aktive Mikrofon, die Kamera und das Whiteboard verfügt. Wie Sie Ihre Geräte konfigurieren, hängt von Ihrer spezifischen Umgebung ab. Hier sind jedoch einige allgemeine Empfehlungen für den Anfang:

- **Mikrofon** Teams-Räume Gerät
- **Kamera** Teams-Räume Gerät (standardmäßig aktiviert) und Surface Hub (standardmäßig deaktiviert, kann aber von Teilnehmern aktiviert werden)
- **Whiteboard** Surface Hub

> [!IMPORTANT]
> Stellen Sie sicher, dass Sie das Mikrofon nur auf einem Gerät aktivieren. Wenn Sie es auf mehreren Geräten aktivieren, werden Audio-Echo und Feedback angezeigt.

## <a name="step-2-get-your-devices-upns"></a>Schritt 2: Abrufen der UPNs Ihrer Geräte

Wenn Sie eine koordinierte Besprechungserfahrung in einem Besprechungsraum einrichten, müssen Sie den Teams-Räume Geräten und Surface Hubs in diesem Raum mitteilen, mit welchen Geräten sie sich abstimmen sollen. Dazu fügen Sie den Benutzerprinzipalnamen (USER Principal Name, UPN) der Geräte hinzu, mit dem er sich in seiner Konfiguration koordinieren soll. Wenn Sie die UPNs für jedes der Geräte, die Sie für koordinierte Besprechungen einrichten möchten, nicht kennen, können Sie diese mithilfe der Microsoft 365 Admin Center finden. 

Ihnen muss eine Administratorrolle zugewiesen werden, um auf die Microsoft 365 Admin Center zugreifen zu können. Weitere Informationen finden Sie unter ["Informationen zu Administratorrollen"](/microsoft-365/admin/add-users/about-admin-roles).

Gehen Sie wie folgt vor, um die UPNs Ihrer Teams-Räume-Geräte und Surface Hubs abzurufen:

1. Melden Sie sich bei der Microsoft 365 Admin Center an, indem Sie besuchenhttps://admin.microsoft.com.
2. Wechseln Sie zu **"Aktive Benutzer"** > .
3. Suchen Sie den Namen Ihres Teams-Räume Geräts oder Surface Hub in der Spalte **"Anzeigename**" (Sie können das **Suchfeld** verwenden, wenn Sie viele Benutzer haben).
4. Suchen Sie den UPN in der Spalte **"Benutzername"** (er sieht ungefähr wie alias@contoso.com oder alias@contoso.onmicrosoft.com aus).
5. Wiederholen Sie diesen Schritt für jedes Gerät, das an koordinierten Besprechungen teilnimmt.

## <a name="step-3-create-a-deployment-worksheet"></a>Schritt 3: Erstellen eines Bereitstellungsarbeitsblatts

Nachdem Sie Ihre koordinierte Besprechungserfahrung geplant und eine Liste der UPNs Ihrer Geräte gesammelt haben, empfiehlt es sich, ein Bereitstellungsarbeitsblatt zu erstellen. Ein Bereitstellungsarbeitsblatt hilft Ihnen, die Konfiguration zu visualisieren, die Sie auf allen Ihren Geräten festlegen möchten, sodass Sie Ihre Auswahl überprüfen und auf Fehler überprüfen können.

Fügen Sie in einer Tabellenkalkulations-App Zeilen für Folgendes in der ersten Spalte hinzu:

| Einstellung                | Beschreibung      |
|------------------------|-----------------|
| **Audiostandard**      | Bestimmt, auf welchem Gerät das Mikrofon aktiv ist, wenn eine Besprechung beginnt. Nur ein Gerät (in der Regel ein Teams-Räume Gerät) kann dieses Feld festlegen`true`, während für die restlichen Geräte dieses Feld festgelegt sein muss, um Audio-Echo und -Feedback zu `false` vermeiden.          |
| **Audio aktiviert**      | Bestimmt, ob teilnehmer an einer Besprechung das Mikrofon ein- oder ausschalten können. Auf Geräten, auf denen der **Audiostandard** festgelegt `false` ist, sollte diese Einstellung so festgelegt `false` sein, dass Teilnehmer nicht versehentlich ein Mikrofon einschalten und Audio-Echo oder Feedback auslösen können.<p>Wenn der **Audiostandard** festgelegt `true`ist, wird diese Einstellung ignoriert, und die Teilnehmer können das Mikrofon stummschalten oder die Stummschaltung aufheben.          |
| **Videostandard**      | Bestimmt, auf welchem Gerät die Kamera aktiv ist, wenn eine Besprechung beginnt. Für eine optimale Benutzererfahrung wird empfohlen, dass nur die Teams-Räume Geräts festgelegt `true` wird, während alle anderen Geräte auf `false`festgelegt sind.          |
| **Video aktiviert**      | Bestimmt, ob Teilnehmer an einer Besprechung die Kamera ein- oder ausschalten können. Sie können dies `true` auf allen anderen Geräten des Ereignisses festlegen, auf dem Teilnehmer unterschiedliche Videoperspektiven teilen möchten (z. B. wenn ein Teilnehmer das Surface Hub-Whiteboard verwendet). Wenn Sie nicht möchten, dass Teilnehmer eine Kamera auf einem Gerät ein- oder ausschalten, legen Sie dies auf `false`" fest.<p> Wenn **der Videostandard** festgelegt `true`ist, wird diese Einstellung ignoriert, und teilnehmer können die Kamera ein- oder ausschalten.         |
| **Whiteboard-Standard** | Bestimmt, ob auf dem Teams-Räume Gerät ein Whiteboard angezeigt wird, das von einem der Besprechungsteilnehmer freigegeben wurde. Es wird empfohlen, dies festzulegen `false` , wenn Sie über einen Surface Hub verfügen und `true` kein Surface Hub besitzen. Diese Einstellung hat keine Auswirkungen auf Surface Hubs. Surface Hubs zeigen immer ein Whiteboard an, das von Besprechungsteilnehmern freigegeben wurde.         |
| **Whiteboard aktiviert** | Bestimmt, ob Teilnehmer an einer Besprechung das Whiteboard ein- oder ausschalten können. Wenn Sie nicht möchten, dass Teilnehmer das Whiteboard auf einem Gerät aktivieren oder deaktivieren, legen Sie dies auf `false`" fest. <p>Wenn **der Whiteboard-Standard** festgelegt `true`ist, wird diese Einstellung ignoriert, und Teilnehmer können das Whiteboard aktivieren oder deaktivieren.
| **Vertrauenswürdige Konten**   | Dies ist eine durch Trennzeichen getrennte Liste von UPNs für jedes Teams Room-Gerät oder Surface Hub, von dem das Gerät Besprechungsteilnahmeanfragen annehmen soll oder an die Besprechungsteilnahmeanfragen gesendet werden sollten. |

Fügen Sie in den nachfolgenden Spalten jedes Ihrer Teams-Räume-Geräte und Surface Hubs hinzu. Füllen Sie in jeder Spalte die Werte aus, die der gewünschten Erfahrung für den Besprechungsraum entsprechen. Hier sehen Sie ein Beispiel mit einem Teams-Räume Gerät und einem Surface Hub:

- Teams-Gerät
  - Audio und Video sind beim Start einer Besprechung **aktiviert** . Teilnehmer **können** Audio und Video ein- oder ausschalten.
  - Das Anzeigen eines freigegebenen Whiteboards ist deaktiviert.
- Surface Hub
  - Audio wird **deaktiviert** , wenn eine Besprechung beginnt. Teilnehmer **können audio nicht** ein- oder ausschalten.
  - Das Video wird **deaktiviert** , wenn eine Besprechung beginnt. Teilnehmer **können** Das Video ein- oder ausschalten.

| Einstellung                | Teams-Raum      | Surface Hub      |
|------------------------|-----------------|------------------|
| **Audiostandard**      | `true`          | `false`          |
| **Audio aktiviert**      | `true`          | `false`          |
| **Videostandard**      | `true`          | `false`          |
| **Video aktiviert**      | `true`          | `true`           |
| **Whiteboard-Standard** | `false`         | `false`          |
| **Vertrauenswürdige Konten**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>Schritt 4: Konfigurieren Teams-Räume Geräts

Sie können entweder koordinierte Besprechungen auf einem Teams-Räume Gerät über den Touchscreen des Geräts einrichten oder, wenn Sie viele Geräte einrichten müssen und dies von einem zentralen Ort aus tun möchten, eine XML-Konfigurationsdatei verwenden.

Verwenden Sie das Arbeitsblatt, das Sie im vorherigen Schritt erstellt haben, um Ihnen beim Einrichten Ihrer Geräte zu helfen.

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Verwenden des Touchscreens des Teams-Räume Geräts

Gehen Sie wie folgt vor, um koordinierte Besprechungen auf einem Gerät einzurichten:

1. Wählen Sie **... Weitere** > **Einstellungen**.
2. Geben Sie das Administratorkennwort ein, und wählen Sie **"Ja**" aus.
3. Wählen Sie **"Koordinierte Besprechungen" aus**.
4. Legen Sie unter **"Optionen**" die **Option "Koordinierte Besprechung** " _auf "Aktiviert_" fest.
5. Wenn der **Audiostandard** in Ihrem Arbeitsblatt lautet `true`, aktivieren **Sie das Mikrofon dieses Geräts, andernfalls** lassen Sie es _deaktiviert_.
6. Wenn " **Audio"** in Ihrem Arbeitsblatt aktiviert ist `true`, wählen Sie " **Zulassen, dass Personen bei der Teilnahme an einer Besprechung aktivieren"** unter **"Mikrofon dieses Geräts aktivieren**" aus. Diese Option kann nicht deaktiviert werden, wenn **das Mikrofon dieses Geräts** aktiviert ist.
7. Wenn **der Videostandard** in Ihrem Arbeitsblatt lautet `true`, legen **Sie "Kamera dieses Geräts** aktivieren" fest, andernfalls lassen Sie es _deaktiviert_.
8. Wenn **"Video"** in Ihrem Arbeitsblatt aktiviert ist `true`, wählen Sie " **Zulassen, dass Personen bei der Teilnahme an einer Besprechung** aktivieren" unter **"Kamera dieses Geräts aktivieren**" aus. Diese Option kann nicht deaktiviert werden, wenn **die Kamera dieses Geräts aktiviert** _ist._
9. Wenn **whiteboard standard** in Ihrem Arbeitsblatt ist `true`, legen **Sie aktivieren Whiteboarding auf diesem Gerät auf** _ein_, andernfalls lassen Sie es _deaktiviert_.
10. Geben Sie unter **"Vertrauenswürdige Gerätekonten**" jeden UPN ein, der in **vertrauenswürdigen Konten** in Ihrem Arbeitsblatt aufgeführt ist. Trennen Sie mehrere UPNs durch Kommas.
11. Deaktivieren Sie auf dem vertrauenswürdigen Gerät die Näherung und raumferne Umgebung. 
12. Wählen Sie **"Speichern" und "Beenden" aus**.

Nachdem Sie **"Speichern" und "Beenden**" ausgewählt haben, wird das Gerät neu gestartet und kann an koordinierten Besprechungen teilnehmen.

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Verwenden der Teams-Räume XML-Konfigurationsdatei

Koordinierte Besprechungen können mithilfe der XML-Konfigurationsdatei des Teams-Räume Geräts `SkypeSettings.xml` eingerichtet werden. Die `SkypeSettings.xml` Datei ist keine statische Datei. Wenn das Teams-Räume Gerät gestartet wird, wird nach einer Datei mit dem Namen `SkypeSettings.xml`eingecheckt`C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`. Wenn die Datei vorhanden ist, liest das Gerät die in der Datei angegebene Konfiguration und wendet sie an. Nachdem die Anwendung der Konfiguration abgeschlossen ist, wird die Datei gelöscht. Weitere Informationen zur Datei finden [Sie unter Verwalten von](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)`SkypeSettings.xml` Konsoleneinstellungen mit einer XML-Konfigurationsdatei.

Es folgt die Syntax der Einstellungen für koordinierte Besprechungen in der Konfigurationsdatei:

```xml
<CoordinatedMeetings enabled="true">
    <Settings>
        <Audio default="true" enabled="true"/>
        <Video default="true" enabled="true"/>
        <Whiteboard default="false" enabled="false"/>
    </Settings>
    <TrustedAccounts>hub@contoso.com</TrustedAccounts>
</CoordinatedMeetings>
```

Gehen Sie wie folgt vor, um koordinierte Besprechungen auf einem Gerät einzurichten:

1. Fügen Sie in einem Textdatei-Editor, z. B. Visual Studio Code oder Editor, den obigen XML-Code in eine neue Datei ein.

2. Legen Sie jedes der XML-Elemente auf den entsprechenden `true` wert in `false` Ihrer Kalkulationstabelle fest. Wenn der **Audiostandard** beispielsweise lautet `true`, legen Sie fest `<Audio default="true">`.

3. Stellen Sie sicher, dass Sie zu Ihrer Liste der UPNs wechseln `TrustedAccounts` .

4. Speichern Sie die Datei unter dem Namen `SkypeSettings.xml`.

5. Platzieren Sie die Datei im Ordner Teams-Räume Geräts`C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`. Sie können dies auf verschiedene Arten tun:

    - **Kopieren Sie die Datei auf Ihr Teams-Räume Gerät**. Sie müssen die Dateifreigabe aktivieren und eine Netzwerkfreigabe erstellen, bevor Sie Dateien auf Ihr Gerät kopieren können. Anschließend können Sie eine Verbindung mit der Netzwerkfreigabe herstellen und die Datei auf das Gerät kopieren. Weitere Informationen finden Sie [unter Microsoft Teams-Räume Wartung und Betrieb](../rooms/rooms-operations.md).
    - **Verwenden Sie eine Gruppenrichtlinie** Erstellen einer Gruppenrichtlinie, um die Datei auf das Gerät zu kopieren. Weitere Informationen finden Sie [unter Gruppenrichtlinie Übersicht](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11)).
    - **Laden Sie die Datei auf das Teams-Räume Gerät herunter**. Sie können sich mit Admin Modus beim Gerät anmelden und die Datei dann von einer Netzwerkfreigabe oder einem USB-Laufwerk auf das Gerät kopieren. Weitere Informationen finden Sie unter [Wechseln zum Admin-Modus](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).
    
6. Starten Sie das Gerät neu. Sie können dies auf verschiedene Arten tun:

    - **Remote-PowerShell** Sie können den Befehl "Herunterfahren" auf dem Gerät mithilfe von Remote PowerShell ausführen. Weitere Informationen finden Sie unter [Remoteverwaltung mitHilfe von PowerShell](../rooms/rooms-operations.md).
    - **Neustart-Computer ausführen** Sie können das `Restart-Computer` Cmdlet auf Ihrem lokalen Computer ausführen und den Computernamen des Geräts angeben, das Sie neu starten möchten. Weitere Informationen finden Sie [unter Restart-Computer](/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7).

## <a name="step-5-configure-surface-hub"></a>Schritt 5: Konfigurieren von Surface Hub

Sie können den Windows-Konfigurations-Designer verwenden, um ein Bereitstellungspaket zu erstellen, mit dem Sie Einstellungen für koordinierte Besprechungen auf Ihre Surface Hubs anwenden können. Sie fügen die oben erstellte XML-Datei in den Windows-Konfigurations-Designer ein, um das Bereitstellungspaket zu erstellen.

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Erstellen einer XML-Konfigurationsdatei für koordinierte Besprechungen für Surface Hub

Sowohl Der Windows-Konfigurations-Designer als auch Microsoft Intune werden verwendet, um die Konfiguration für koordinierte Besprechungen auf Ihre Surface Hubs anzuwenden. Die Konfiguration wird mithilfe von XML definiert. Bevor Sie fortfahren, müssen Sie den XML-Code erstellen, der angewendet wird.

Es folgt die Syntax der XML-Konfigurationsdatei für koordinierte Besprechungen.

```xml
<SurfaceHubSettings>
    <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
    <AutoAcceptProximateMeetingInvitations>true</AutoAcceptProximateMeetingInvitations>
    <CoordinatedMeetings enabled="true"> 
        <TrustedAccounts>room@contoso.com</TrustedAccounts>
        <Settings> 
            <Audio default="false" enabled="false" />
            <Video default="false" enabled="true" /> 
        </Settings> 
    </CoordinatedMeetings>
</SurfaceHubSettings>
```

Führen Sie die folgenden Schritte aus, um den XML-Code für Windows-Konfigurations-Designer oder Microsoft Intune vorzubereiten:

1. Fügen Sie in einem Textdatei-Editor, z. B. Visual Studio Code oder Editor, den obigen XML-Code in eine neue Datei ein.

2. Legen Sie jedes der XML-Elemente auf den entsprechenden `true` wert in `false` Ihrer Kalkulationstabelle fest. Wenn der **Audiostandard** beispielsweise lautet `true`, legen Sie fest `<Audio default="true">`.

3. Stellen Sie sicher, dass Sie zu Ihrer Liste der UPNs wechseln `TrustedAccounts` .

4. Der Windows-Konfigurations-Designer erfordert, dass sich der XML-Code in einer einzigen Zeile befinden muss. Entfernen Sie alle Zeilenumbrüche zwischen den einzelnen Zeilen, damit der XML-Code wie folgt aussieht:

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. Speichern Sie die Datei auf Ihrem Computer.

Nachdem Sie Ihre XML-Konfigurationsdatei erstellt haben, führen Sie die Schritte unter ["Verwalten von Microsoft Teams-Einstellungen auf Surface Hub](surface-hub-manage-config.md) " aus, um sie auf Ihre Surface Hubs anzuwenden.
