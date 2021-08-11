---
title: Einrichten von koordinierten Besprechungen mit Microsoft Teams-Räume und Surface Hub
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Konfigurieren Teams-Räume geräte und Surface Hub, um an Besprechungen teilzunehmen, wenn das eine oder das andere Gerät einer Besprechung beitritt.
ms.openlocfilehash: 5d46e8b43d0a8b31aa06dda78d1d2c0fb7a1ef55abdfffa2c4c6876be3938cb3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54339463"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Einrichten von koordinierten Besprechungen mit Microsoft Teams-Räume und Surface Hub

Wenn Sie über mindestens ein Microsoft Teams-Räume oder Surface Hubs in einem Besprechungsraum verfügen, können Sie koordinierte Besprechungen einrichten. Bei koordinierten Besprechungen können Sie Ihre Teams-Räume-Geräte und Surface Hubs so einrichten, dass die anderen Geräte im Raum an derselben Besprechung teilnehmen, wenn Sie über ein Gerät an einer Besprechung teilnehmen. Sie können Ihre Kameras, Lautsprecher und Mikrofone so konfigurieren, dass diejenigen aktiviert sind, die den Teilnehmern die bestmögliche Benutzererfahrung bieten, während andere deaktiviert sind. Dadurch wird verhindert, dass Teilnehmer mit echo- und feedbackrauschenden Geräuschen mehrere Geräte zu einer Besprechung hinzufügen.

Zum Einrichten von koordinierten Besprechungen müssen Sie sicherstellen, dass Ihre Teams-Räume-Geräte und Surface Hubs bereits ordnungsgemäß für die Teilnahme an Besprechungen konfiguriert sind. Am wichtigsten ist, dass jedes Gerät über ein eigenes Postfach Exchange Raum verfügen muss. Informationen dazu, wie sie eingerichtet werden, finden Sie in den folgenden Artikeln:

- [Bereitstellen von Microsoft Teams-Räume](../rooms/rooms-deploy.md)
- [Erstellen Surface Hub 2S-Gerätekontos](/surface-hub/surface-hub-2s-account)

Nachdem Sie bestätigt haben, dass Ihre Teams-Räume-Geräte und Surface Hubs Besprechungen automatisch annehmen und erfolgreich daran teilnehmen können, können Sie koordinierte Besprechungen einrichten.

Die folgenden Schritte sollten für jeden Besprechungsraum separat durchgeführt werden. Geräte in einem Besprechungsraum sollten nicht für koordinierte Besprechungen mit Geräten in anderen Besprechungsräumen eingerichtet werden.

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>Schritt 1: Planen der Koordinierten Besprechung

Bevor Sie Konfigurationsänderungen vornehmen, müssen Sie entscheiden, welche Geräte welche in den einzelnen Besprechungsraumen verwenden. Das heißt, für einen bestimmten Besprechungsraum müssen Sie entscheiden, welches Gerät das aktive Mikrofon, die Kamera und das Whiteboard haben soll. Wie Sie Ihre Geräte konfigurieren, hängt von Ihrer jeweiligen Umgebung ab. Im Folgenden finden Sie jedoch einige allgemeine Empfehlungen, mit der Sie beginnen sollten:

- **Mikrofon** Teams-Räume Gerät
- **Kamera** Teams-Räume (standardmäßig aktiviert) und Surface Hub (standardmäßig deaktiviert, aber von Teilnehmern aktiviert werden dürfen)
- **Whiteboard-Surface Hub**

> [!IMPORTANT]
> Stellen Sie sicher, dass das Mikrofon nur auf einem Gerät aktiviert ist. Wenn Sie es auf mehr als einem Gerät aktivieren, werden Audio-Echo und Feedback angezeigt.

## <a name="step-2-get-your-devices-upns"></a>Schritt 2: Erhalten der UPNs Ihrer Geräte

Wenn Sie eine koordinierte Besprechungserfahrung in einem Besprechungsraum einrichten, müssen Sie den Teams-Räume-Geräten und Surface Hubs in diesem Raum mitteilen, mit welchen Geräten Sie koordinieren möchten. Dazu fügen Sie den Benutzerprinzipalnamen (User Principal Name, UPN) der Geräte hinzu, mit der er sich bei der Konfiguration koordinieren soll. Wenn Sie die UPNs für jedes der Geräte, die Sie für koordinierte Besprechungen einrichten möchten, nicht kennen, können Sie sie mithilfe der Microsoft 365 Admin Center. 

Ihnen muss eine Administratorrolle zugewiesen sein, um auf die einzelnen Microsoft 365 Admin Center. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen.](/microsoft-365/admin/add-users/about-admin-roles)

Um die UPNs Ihrer Teams-Räume und Surface Hubs zu erhalten, gehen Sie wie folgt vor:

1. Melden Sie sich bei der Microsoft 365 Admin Center, indem Sie https://admin.microsoft.com besuchen.
2. Wechseln Sie **zu**  >  **Aktive Benutzer**.
3. Suchen Sie den Namen Ihres Teams-Räume-Geräts oder  Ihres Surface Hub in der  Spalte Anzeigename (sie können das Suchfeld verwenden, wenn Sie viele Benutzer haben).
4. Suchen Sie den UPN in der Spalte **Benutzername** (er sieht in etwa wie alias@contoso.com oder alias@contoso.onmicrosoft.com).
5. Wiederholen Sie diesen Vorgang für jedes Gerät, das an koordinierten Besprechungen teilnehmen soll.

## <a name="step-3-create-a-deployment-worksheet"></a>Schritt 3: Erstellen eines Arbeitsblatts für die Bereitstellung

Nachdem Sie die Erfahrung einer koordinierten Besprechung geplant und eine Liste der UPNs Ihrer Geräte gesammelt haben, ist es eine gute Idee, ein Arbeitsblatt für die Bereitstellung zu erstellen. Mithilfe eines Bereitstellungsarbeitsblatts können Sie die Konfiguration, die Sie für alle Ihre Geräte festlegen möchten, visualisieren, sodass Sie Ihre Auswahl überprüfen und auf Fehler überprüfen können.

Fügen Sie in einer Tabellenkalkulations-App in der ersten Spalte Zeilen für Folgendes hinzu:

| Einstellung                | Beschreibung      |
|------------------------|-----------------|
| **Standardaudio**      | Bestimmt, auf welchem Gerät das Mikrofon beim Beginn einer Besprechung aktiv ist. Dieses Feld kann nur auf einem Gerät (in der Regel ein Teams-Räume Gerät) festgelegt werden, während dieses Feld auf den restlichen Geräten auf festgelegt sein muss, um Audio-Echo und -Feedback `true` `false` zu vermeiden.          |
| **Audio aktiviert**      | Bestimmt, ob Teilnehmer an einer Besprechung das Mikrofon ein- oder ausschalten können. Auf Geräten, **auf denen der** Standardwert für Audio festgelegt ist, sollte diese Einstellung auf festgelegt sein, damit Teilnehmer nicht versehentlich ein Mikrofon aktivieren und Audio-Echo oder Feedback verursachen `false` `false` können.<p>Wenn **audio default** auf festgelegt ist, wird diese Einstellung ignoriert, und die Teilnehmer können das Mikrofon stummschalten bzw. die `true` Stummschaltung wieder einstellen.          |
| **Video-Standard**      | Bestimmt, auf welchem Gerät die Kamera aktiv ist, wenn eine Besprechung beginnt. Für eine optimale Benutzererfahrung empfehlen wir, dass nur das Teams-Räume auf festgelegt wird, während alle `true` anderen Geräte auf festgelegt `false` sind.          |
| **Video aktiviert**      | Bestimmt, ob Teilnehmer einer Besprechung die Kamera ein- oder ausschalten können. Sie können dies auf allen anderen Geräten der Ereignisteilnehmer festlegen, die andere Videoperspektiven teilen möchten (z. B. wenn ein Teilnehmer das `true` Surface Hub verwendet). Wenn Sie nicht möchten, dass Teilnehmer eine Kamera auf einem Gerät ein- oder ausschalten, legen Sie dies auf `false` fest.<p> Wenn **video default** auf festgelegt ist, wird diese Einstellung ignoriert, und die Teilnehmer können die Kamera `true` ein- oder ausschalten.         |
| **Whiteboard-Standard** | Bestimmt, ob auf Teams-Räume Gerät ein Whiteboard angezeigt wird, das von einem der Besprechungsteilnehmer freigegeben wurde. Wir empfehlen, diese auf zu setzen, wenn Sie über eine Surface Hub verfügen und `false` `true` keines. Diese Einstellung hat keine Auswirkung auf Surface Hubs. Surface Hubs zeigen immer ein Whiteboard an, das von Besprechungsteilnehmern freigegeben wurde.         |
| **Whiteboard aktiviert** | Bestimmt, ob Teilnehmer an einer Besprechung das Whiteboard ein- oder ausschalten können. Wenn Sie nicht möchten, dass Teilnehmer das Whiteboard auf einem Gerät ein- oder ausschalten, legen Sie dies auf `false` . <p>Wenn **Whiteboard standardmäßig** auf festgelegt ist, wird diese Einstellung ignoriert, und die Teilnehmer können das `true` Whiteboard ein- oder ausschalten.
| **Vertrauenswürdige Konten**   | Dies ist eine durch Kommas getrennte Liste von UPNs für jedes Teams Raumgerät oder jedes Surface Hub, von dem das Gerät Besprechungs-Joinanfragen annehmen oder an die Besprechungs-Joinanfragen gesendet werden sollen. |

Fügen Sie in nachfolgenden Spalten jedes Ihrer Teams-Räume und Surface Hubs hinzu. Geben Sie in jeder Spalte die Werte ein, die der für den Besprechungsraum zu verwendende Erfahrung entsprechen. Hier sehen Sie ein Beispiel mit einem Teams-Räume gerät und einem Surface Hub:

- Teams Gerät
  - Audio und Video werden **beim Beginn** einer Besprechung aktiviert. Teilnehmer **können** Audio und Video ein- oder ausschalten.
  - Die Anzeige eines freigegebenen Whiteboards ist deaktiviert.
- Surface Hub
  - Die Audiowiedergabe **wird beim** Beginn einer Besprechung deaktiviert. Teilnehmer **können die Audiowiedergabe** nicht ein- oder ausschalten.
  - Video wird beim **Beginn** einer Besprechung deaktiviert. Teilnehmer **können** Video ein- oder ausschalten.

| Einstellung                | Teams Raum      | Surface Hub      |
|------------------------|-----------------|------------------|
| **Standardaudio**      | `true`          | `false`          |
| **Audio aktiviert**      | `true`          | `false`          |
| **Video-Standard**      | `true`          | `false`          |
| **Video aktiviert**      | `true`          | `true`           |
| **Whiteboard-Standard** | `false`         | `false`          |
| **Vertrauenswürdige Konten**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>Schritt 4: Konfigurieren Teams-Räume Geräts

Sie können entweder koordinierte Besprechungen auf einem Teams-Räume-Gerät über den Touchscreen des Geräts einrichten, oder Sie können eine XML-Konfigurationsdatei verwenden, wenn Sie viele Geräte einrichten müssen und dies von einem zentralen Ort aus tun möchten.

Verwenden Sie das Arbeitsblatt, das Sie im vorherigen Schritt erstellt haben, um die Geräte einrichten zu können.

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Verwenden des Teams-Räume ihres Geräts

Gehen Sie wie folgt vor, um koordinierte Besprechungen auf einem Gerät zu einrichten:

1. Wählen Sie **... aus. Weitere**  >  **Einstellungen**.
2. Geben Sie das Administratorkennwort ein, und wählen Sie **Ja aus.**
3. Wählen Sie **Koordinierte Besprechungen aus.**
4. Legen **Sie unter Optionen** die Option **Koordinierte Besprechung** auf für _festgelegt._
5. Wenn **audio default** in your worksheet `true` ist, set Turn on this **device's microphone** to on, otherwise leave it _off_.
6. Wenn **Audio in Ihrem** Arbeitsblatt aktiviert ist, wählen Sie unter Mikrofon dieses Geräts aktivieren die Option Personen bei der Teilnahme an einer Besprechung aktivieren `true` **aus.**  Diese Option kann nicht deaktiviert werden, wenn **Das** Mikrofon dieses Geräts aktivieren aktiviert ist.
7. Wenn **der Standardwert für Video** auf dem Arbeitsblatt ist, legen Sie Kamera dieses Geräts aktivieren auf ein `true` fest, andernfalls lassen Sie die Kamera _aus._ 
8. Wenn **auf Ihrem Arbeitsblatt Video** aktiviert ist, wählen Sie unter Kamera dieses Geräts aktivieren die Option Personen bei der Teilnahme an einer Besprechung aktivieren `true` **aus.**  Diese Option kann nicht deaktiviert werden, wenn **Kamera** dieses Geräts aktivieren auf ein _festgelegt ist._
9. Wenn **Whiteboard auf Ihrem** Arbeitsblatt standardmäßig ist, legen Sie Whiteboarding auf diesem Gerät aktivieren auf `true` _ein,_ andernfalls lassen Sie es _aus._ 
10. Geben **Sie unter Vertrauenswürdige Gerätekonten** jeden UPN ein, der im Arbeitsblatt unter **Vertrauenswürdige Konten** aufgeführt ist. Trennen Sie mehrere UPNs durch Kommas.
11. Wählen **Sie Speichern und beenden aus.**

Nachdem Sie Speichern **und beenden ausgewählt haben,** wird das Gerät neu gestartet und kann an koordinierten Besprechungen teilnehmen.

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Verwenden der Teams-Räume XML-Konfigurationsdatei

Koordinierte Besprechungen können mithilfe der XML Teams-Räume konfigurationsdatei des Geräts `SkypeSettings.xml` eingerichtet werden. Die `SkypeSettings.xml` Datei ist keine statische Datei. Wenn das Teams-Räume wird, überprüft es auf `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` eine Datei mit dem Namen `SkypeSettings.xml` . Wenn die Datei vorhanden ist, liest das Gerät die in der Datei angegebene Konfiguration und wendet sie an. Nachdem die Anwendung der Konfiguration erfolgt ist, wird die Datei gelöscht. Weitere Informationen zu der Datei finden Sie unter Verwalten von `SkypeSettings.xml` [Konsoleneinstellungen mit einer XML-Konfigurationsdatei.](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)

Die folgende Syntax enthält die Einstellungen für "Koordinierte Besprechungen" in der Konfigurationsdatei:

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

Gehen Sie wie folgt vor, um koordinierte Besprechungen auf einem Gerät zu einrichten:

1. Fügen Sie in einem Textdatei-Editor, z. B. Visual Studio Code Oder Editor, den obigen XML-Code in eine neue Datei ein.

2. Legen Sie jedes der XML-Elemente auf den entsprechenden - `true` oder `false` -Wert in Ihrer Kalkulationstabelle festgelegt. Wenn audio standardmäßig ist, **legen** Sie `true` z. `<Audio default="true">` B. .

3. Stellen Sie sicher, `TrustedAccounts` dass Sie zu Ihrer Liste der UPNs wechseln.

4. Speichern Sie die Datei unter dem Namen `SkypeSettings.xml` .

5. Speichern Sie die Datei im Teams-Räume des `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` Geräts. Hier einige Möglichkeiten:

    - **Kopieren Der Datei auf Ihr Teams-Räume Gerät** Sie müssen die Dateifreigabe aktivieren und eine Netzwerkfreigabe erstellen, bevor Sie Dateien auf Ihr Gerät kopieren können. Anschließend können Sie eine Verbindung mit der Netzwerkfreigabe herstellen und die Datei auf das Gerät kopieren. Weitere Informationen finden Sie unter [Microsoft Teams-Räume und Vorgängen.](../rooms/rooms-operations.md)
    - **Verwenden einer Gruppenrichtlinie** Erstellen Sie eine Gruppenrichtlinie, um die Datei auf das Gerät zu kopieren. Weitere Informationen finden Sie unter [Übersicht über Gruppenrichtlinien.](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))
    - **Herunterladen der Datei auf das Teams-Räume Gerät** Sie können sich im Administratormodus beim Gerät anmelden und dann die Datei von einer Netzwerkfreigabe oder einem USB-Laufwerk auf das Gerät kopieren. Weitere Informationen finden Sie unter [Wechseln in den Administratormodus.](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)
    
6. Starten Sie das Gerät neu. Hier haben Sie verschiedene Möglichkeiten:

    - **Remote-PowerShell** Sie können den Befehl Herunterfahren auf dem Gerät mithilfe der Remote-PowerShell ausführen. Weitere Informationen finden Sie unter [Remoteverwaltung mit PowerShell.](../rooms/rooms-operations.md)
    - **Restart-Computer ausführen** Sie können das Cmdlet auf dem lokalen Computer ausführen und den Computernamen des Geräts angeben, `Restart-Computer` das Sie neu starten möchten. Weitere Informationen finden Sie unter [Restart-Computer.](/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7)

## <a name="step-5-configure-surface-hub"></a>Schritt 5: Konfigurieren Surface Hub

Sie können mit Windows Configuration Designer ein Bereitstellungspaket erstellen, mit dem Sie Einstellungen für koordinierende Besprechungen auf Ihre Surface Hubs anwenden können. Sie fügen die oben erstellte XML-Datei in den Konfigurations-Designer ein, Windows Bereitstellungspaket zu erstellen.

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>ERSTELLEN einer XML-Konfigurationsdatei für koordinierte Besprechungen für Surface Hub

Sowohl Windows als auch die Microsoft Intune werden verwendet, um die Konfiguration für koordinierte Besprechungen auf Ihre Surface Hubs anzuwenden. Die Konfiguration wird mithilfe von XML definiert. Bevor Sie weiter gehen, müssen Sie den XML-Code erstellen, der angewendet wird.

Die folgende Syntax ist die Syntax der XML-Konfigurationsdatei für koordinierte Besprechungen.

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

Gehen Sie wie folgt vor, um den XML-Code für Windows Konfigurations-Designer oder Microsoft Intune:

1. Fügen Sie in einem Textdatei-Editor, z. B. Visual Studio Code Oder Editor, den obigen XML-Code in eine neue Datei ein.

2. Legen Sie jedes der XML-Elemente auf den entsprechenden - `true` oder `false` -Wert in Ihrer Kalkulationstabelle festgelegt. Wenn audio standardmäßig ist, **legen** Sie `true` z. `<Audio default="true">` B. .

3. Stellen Sie sicher, `TrustedAccounts` dass Sie zu Ihrer Liste der UPNs wechseln.

4. Windows Für den Konfigurations-Designer muss sich der XML-Code in einer einzelnen Zeile enthalten. Entfernen Sie alle Zeilenumbrüche zwischen den einzelnen Zeilen, damit der XML-Code wie folgt aussieht:

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. Speichern Sie die Datei auf Ihrem Computer.

Nachdem Sie die XML-Konfigurationsdatei erstellt haben, führen Sie die Schritte [unter](surface-hub-manage-config.md) Verwalten von Microsoft Teams Einstellungen für Surface Hub aus, um sie auf Ihre Surface Hubs anzuwenden.