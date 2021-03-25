---
title: Einrichten koordinierter Besprechungen mit Microsoft Teams Rooms und Surface Hub
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
description: Konfigurieren Sie Teams Rooms-Geräte und Surface Hub so, dass sie an Besprechungen teilnehmen, wenn das eine oder andere Gerät einer Besprechung beitritt.
ms.openlocfilehash: 57dc91e4a7d923e218cd1f8f6f0ce22679d550e3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117563"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Einrichten koordinierter Besprechungen mit Microsoft Teams-Räumen und Surface Hub

Wenn Sie über mindestens ein Microsoft Teams Room-Gerät oder Surface Hubs in einem Besprechungsraum verfügen, können Sie koordinierte Besprechungen einrichten. Bei koordinierten Besprechungen können Sie Ihre Teams Rooms-Geräte und Surface Hubs so einrichten, dass die anderen Geräte im Raum auch an derselben Besprechung teilnehmen, wenn Sie auf einem Gerät an einer Besprechung teilnehmen. Sie können Ihre Kameras, Lautsprecher und Mikrofone so konfigurieren, dass die Kameras, die den Teilnehmern die beste Erfahrung bieten, aktiviert werden, während andere deaktiviert sind. Dadurch wird das gefürchtete Echo und feedbackrauschende Geräusch vermieden, das Teilnehmer beim Hinzufügen mehrerer Geräte zu einer Besprechung erleben können.

Um koordinierte Besprechungen einrichten zu können, müssen Sie sicherstellen, dass Ihre Teams Rooms-Geräte und Surface Hubs bereits ordnungsgemäß für die Teilnahme an Besprechungen konfiguriert sind. Am wichtigsten ist, dass jedes Gerät über ein eigenes Exchange-Raumpostfach verfügen muss. Informationen dazu, wie sie eingerichtet werden, finden Sie in den folgenden Artikeln:

- [Bereitstellen von Microsoft Teams-Räume](../rooms/rooms-deploy.md)
- [Erstellen eines Surface Hub 2S-Gerätekontos](/surface-hub/surface-hub-2s-account)

Nachdem Sie bestätigt haben, dass Ihre Teams Rooms-Geräte und Surface Hubs Besprechungen automatisch annehmen und erfolgreich daran teilnehmen können, können Sie koordinierte Besprechungen einrichten.

Die folgenden Schritte sollten für jeden Besprechungsraum separat abgeschlossen werden. Geräte in einem Besprechungsraum sollten nicht für koordinierte Besprechungen mit Geräten in anderen Besprechungsräumen eingerichtet werden.

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>Schritt 1: Planen Ihrer koordinierten Besprechungserfahrung

Bevor Sie Konfigurationsänderungen vornehmen, müssen Sie entscheiden, auf welchen Geräten in den einzelnen Besprechungsraumn was passiert. Das bedeutet, dass Sie für einen bestimmten Besprechungsraum entscheiden müssen, welches Gerät über das aktive Mikrofon, die Kamera und das Whiteboard verfügt. Wie Sie Ihre Geräte konfigurieren, hängt von Ihrer jeweiligen Umgebung ab, doch hier sind einige allgemeine Empfehlungen für den Anfang:

- **Mikrofon** Gerät "Teams Rooms"
- **Kamera** Teams Rooms-Gerät (standardmäßig aktiviert) und Surface Hub (standardmäßig deaktiviert, aber von Teilnehmern aktiviert)
- **Whiteboard** Surface Hub

> [!IMPORTANT]
> Stellen Sie sicher, dass Sie das Mikrofon nur auf einem Gerät aktivieren. Wenn Sie es auf mehreren Geräten aktivieren, werden Echo und Feedback für Audio angezeigt.

## <a name="step-2-get-your-devices-upns"></a>Schritt 2: Holen Sie sich die UPNs Ihrer Geräte.

Wenn Sie eine koordinierte Besprechungserfahrung in einem Besprechungsraum einrichten, müssen Sie die Teams Rooms-Geräte und Surface Hubs in diesem Raum darüber informieren, mit welchen Geräten Sie sich koordinieren möchten. Dazu fügen Sie den Benutzerprinzipalnamen (USER Principal Name, UPN) der Geräte hinzu, mit deren Konfiguration sie sich koordinieren soll. Wenn Sie die UPNs für jedes der Geräte, die Sie für koordinierte Besprechungen einrichten möchten, nicht kennen, können Sie sie über das Microsoft 365 Admin Center finden. 

Ihnen muss eine Administratorrolle zugewiesen werden, um auf das Microsoft 365 Admin Center zugreifen zu können. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen.](/microsoft-365/admin/add-users/about-admin-roles)

Gehen Sie wie folgt vor, um die UPNs Ihrer Teams Rooms-Geräte und Surface Hubs zu erhalten:

1. Melden Sie sich beim Microsoft 365 Admin Center an, indem Sie https://admin.microsoft.com besuchen.
2. Wechseln Sie zu **Aktive**  >  **Benutzer**.
3. Suchen Sie den Namen Ihres Teams Rooms-Geräts oder Surface Hubs in der Spalte Anzeigename (Sie können das Suchfeld verwenden, wenn Sie viele Benutzer haben).  
4. Suchen Sie den  UPN in der Spalte Benutzername (er sieht so aus, als ob alias@contoso.com oder alias@contoso.onmicrosoft.com).
5. Wiederholen Sie diesen Vorgang für jedes Gerät, das an koordinierten Besprechungen teil nimmt.

## <a name="step-3-create-a-deployment-worksheet"></a>Schritt 3: Erstellen eines Bereitstellungsarbeitsblatts

Nachdem Sie Ihre Koordinierte Besprechung geplant und eine Liste der UPNs Ihrer Geräte gesammelt haben, ist es eine gute Idee, ein Bereitstellungsarbeitsblatt zu erstellen. Ein Bereitstellungsarbeitsblatt hilft Ihnen, die Konfiguration, die Sie auf allen Ihren Geräten festlegen möchten, zu visualisieren, sodass Sie Ihre Auswahl überprüfen und auf Fehler überprüfen können.

Fügen Sie in einer Tabellenkalkulations-App Zeilen für folgendes in der ersten Spalte hinzu:

| Einstellung                | Beschreibung      |
|------------------------|-----------------|
| **Audio-Standard**      | Bestimmt, auf welchem Gerät das Mikrofon aktiv ist, wenn eine Besprechung beginnt. Nur auf einem Gerät (in der Regel ein Team Rooms-Gerät) kann dieses Feld auf festgelegt sein, während für die restlichen Geräte dieses Feld auf festgelegt sein muss, um Audio echo und Feedback `true` `false` zu vermeiden.          |
| **Audio aktiviert**      | Bestimmt, ob Teilnehmer an einer Besprechung das Mikrofon ein- oder ausschalten können. Auf Geräten, auf denen **audio default** festgelegt ist, sollte diese Einstellung auf festgelegt sein, damit die Teilnehmer nicht versehentlich ein Mikrofon aktivieren und audio echo oder Feedback `false` verursachen `false` können.<p>Wenn **audio default** auf festgelegt ist, wird diese Einstellung ignoriert, und die Teilnehmer können das Mikrofon stummschalten oder die `true` Stummschaltung aufhören.          |
| **Video-Standard**      | Bestimmt, auf welchem Gerät die Kamera aktiv ist, wenn eine Besprechung beginnt. Zur bestmöglichen Benutzererfahrung empfiehlt es sich, nur auf das Gerät Teams Rooms zu setzen, während `true` alle anderen Geräte auf festgelegt `false` sind.          |
| **Video aktiviert**      | Bestimmt, ob Teilnehmer an einer Besprechung die Kamera ein- oder ausschalten können. Sie können dies auf allen anderen Geräten der Ereignisteilnehmer festlegen, die unterschiedliche Videoperspektiven teilen möchten (z. B. wenn ein Teilnehmer das `true` Surface Hub-Whiteboard verwendet). Wenn Sie nicht möchten, dass Teilnehmer eine Kamera auf einem Gerät ein- oder ausschalten, legen Sie dies auf `false` fest.<p> Wenn **video default** auf festgelegt ist, wird diese Einstellung ignoriert, und die Teilnehmer können die Kamera `true` ein- oder ausschalten.         |
| **Whiteboard Standard** | Bestimmt, ob auf dem Gerät "Teams Rooms" ein Whiteboard angezeigt wird, das von einem der Besprechungsteilnehmer freigegeben wurde. Wir empfehlen, dies auf zu setzen, wenn Sie über einen Surface Hub verfügen und nicht `false` `true` über einen verfügen. Diese Einstellung hat keine Auswirkung auf Surface Hubs. Surface Hubs zeigt immer ein Whiteboard an, das von Besprechungsteilnehmern geteilt wird.         |
| **Whiteboard aktiviert** | Bestimmt, ob Teilnehmer an einer Besprechung das Whiteboard ein- oder ausschalten können. Wenn Teilnehmer das Whiteboard auf einem Gerät nicht aktivieren oder deaktivieren möchten, legen Sie dies auf `false` . <p>Wenn **Whiteboard standardmäßig** auf festgelegt ist, wird diese Einstellung ignoriert, und Die Teilnehmer können das `true` Whiteboard aktivieren oder deaktivieren.
| **Vertrauenswürdige Konten**   | Dies ist eine durch Kommas getrennte Liste von UPNs für jedes Teams Room-Gerät oder Surface Hub, von dem das Gerät Besprechungsbesprechungsanfragen annehmen oder an die Besprechungsbesprechungsanfragen gesendet werden sollen. |

Fügen Sie in nachfolgenden Spalten jedes Ihrer Teams Rooms-Geräte und Surface Hubs hinzu. Füllen Sie in jeder Spalte die Werte aus, die der für den Besprechungsraum bestimmten Benutzererfahrung entsprechen. Hier sehen Sie ein Beispiel mit einem Team Rooms-Gerät und einem Surface Hub:

- Teams-Gerät
  - Audio und Video werden **aktiviert,** wenn eine Besprechung beginnt. Teilnehmer **können** Audio und Video ein- oder ausschalten.
  - Das Anzeigen eines freigegebenen Whiteboards ist deaktiviert.
- Surface Hub
  - Audio wird **deaktiviert,** wenn eine Besprechung beginnt. Teilnehmer **können Audio nicht** ein- oder ausschalten.
  - Video wird **deaktiviert,** wenn eine Besprechung beginnt. Teilnehmer **können** Video ein- oder ausschalten.

| Einstellung                | Teams Room      | Surface Hub      |
|------------------------|-----------------|------------------|
| **Audio-Standard**      | `true`          | `false`          |
| **Audio aktiviert**      | `true`          | `false`          |
| **Video-Standard**      | `true`          | `false`          |
| **Video aktiviert**      | `true`          | `true`           |
| **Whiteboard Standard** | `false`         | `false`          |
| **Vertrauenswürdige Konten**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>Schritt 4: Konfigurieren des Geräts "Teams Rooms"

Sie können koordinierte Besprechungen entweder über den Touchscreen des Geräts auf einem Team Rooms-Gerät einrichten, oder Sie können eine XML-Konfigurationsdatei verwenden, wenn Sie viele Geräte einrichten müssen und dies von einem zentralen Ort aus tun möchten.

Verwenden Sie das Arbeitsblatt, das Sie im vorherigen Schritt erstellt haben, um Ihnen beim Einrichten Ihrer Geräte zu helfen.

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Verwenden des Touchscreens des Teams Rooms-Geräts

Gehen Sie wie folgt vor, um koordinierte Besprechungen auf einem Gerät zu einrichten:

1. Wählen Sie **... aus. Weitere**  >  **Einstellungen**.
2. Geben Sie das Administratorkennwort ein, und wählen Sie **Ja aus.**
3. Wählen Sie **Koordinierte Besprechungen aus.**
4. Legen **Sie unter Optionen** die Option **Koordinierte Besprechung auf** auf _vor._
5. Wenn **audio standard** in Ihrem Arbeitsblatt ist, legen Sie Aktivieren des Mikrofons dieses Geräts auf ein, andernfalls lassen Sie es `true` _deaktiviert._ 
6. Wenn **Audio in Ihrem** Arbeitsblatt aktiviert ist, wählen Sie Unter Mikrofon dieses Geräts aktivieren die Option Personen aktivieren aus, wenn Sie an einer Besprechung teil `true` **nehmen.**  Diese Option kann nicht deaktiviert werden, wenn **Das** Mikrofon dieses Geräts aktivieren aktiviert ist.
7. Wenn **die Standardeinstellung** Video in Ihrem Arbeitsblatt ist, aktivieren Sie die Kamera dieses Geräts, andernfalls `true` lassen Sie sie  _deaktiviert._
8. Wenn **Video auf Ihrem** Arbeitsblatt aktiviert ist, wählen Sie Personen aktivieren aus, wenn Sie an einer Besprechung teil nehmen, unter Kamera dieses `true` Geräts aktivieren **aus.**  Diese Option kann nicht deaktiviert werden, **wenn** die Kamera dieses Geräts auf _aktiviert ist._
9. Wenn **whiteboard standard** in Ihrem Arbeitsblatt ist, legen Sie Aktivieren von Whiteboarding auf diesem Gerät auf ein , `true` andernfalls lassen Sie es _deaktiviert._  
10. Geben **Sie unter Konten vertrauenswürdiger** Geräte jeden UPN ein, der in **Vertrauenswürdige Konten** auf Ihrem Arbeitsblatt aufgeführt ist. Trennen Sie mehrere UPNs durch Kommas.
11. Wählen **Sie Speichern und Beenden aus.**

Nachdem Sie Speichern **und Beenden ausgewählt haben,** wird das Gerät neu gestartet, und es kann an koordinierten Besprechungen teilnehmen.

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Verwenden der XML-Konfigurationsdatei "Teams Rooms"

Koordinierte Besprechungen können mithilfe der XML-Konfigurationsdatei des Teams `SkypeSettings.xml` Rooms-Geräts eingerichtet werden. Die `SkypeSettings.xml` Datei ist keine statische Datei. Wenn das Gerät "Teams Rooms" gestartet wird, wird auf `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` eine Datei namens `SkypeSettings.xml` überprüft. Wenn die Datei vorhanden ist, liest und wendet das Gerät die in der Datei angegebene Konfiguration an. Nachdem die Anwendung der Konfiguration erfolgt ist, wird die Datei gelöscht. Weitere Informationen zur Datei `SkypeSettings.xml` finden Sie unter Verwalten von [Konsoleneinstellungen mit einer XML-Konfigurationsdatei.](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)

Die folgende Syntax ist die Syntax der Einstellungen für koordinierte Besprechungen in der Konfigurationsdatei:

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

1. Fügen Sie in einem Textdatei-Editor, z. B. Visual Studio Code oder Editor, den oben genannten XML-Code in eine neue Datei ein.

2. Legen Sie jedes der XML-Elemente auf den entsprechenden Wert oder `true` den Wert in Ihrer `false` Kalkulationstabelle an. Wenn Audio **standardmäßig** ist, legen Sie `true` z. `<Audio default="true">` B. .

3. Stellen Sie sicher, dass `TrustedAccounts` Sie zu Ihrer Liste der UPNs wechseln.

4. Speichern Sie die Datei mit dem Namen `SkypeSettings.xml` .

5. Platzieren Sie die Datei im Ordner des Teams `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` Rooms-Geräts. Dazu gibt es ein paar Möglichkeiten:

    - **Kopieren der Datei auf Ihr Teams Rooms-Gerät** Sie müssen die Dateifreigabe aktivieren und eine Netzwerkfreigabe erstellen, bevor Sie Dateien auf Ihr Gerät kopieren können. Anschließend können Sie eine Verbindung mit der Netzwerkfreigabe herstellen und die Datei auf das Gerät kopieren. Weitere Informationen finden Sie unter Wartung und Betrieb [von Microsoft Teams-Räumen.](../rooms/rooms-operations.md)
    - **Verwenden einer Gruppenrichtlinie** Erstellen Sie eine Gruppenrichtlinie, um die Datei auf das Gerät zu kopieren. Weitere Informationen finden Sie unter [Übersicht über Gruppenrichtlinien.](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))
    - **Herunterladen der Datei auf das Gerät "Teams Rooms"** Sie können sich im Administratormodus beim Gerät anmelden und dann die Datei von einer Netzwerkfreigabe oder einem USB-Laufwerk auf das Gerät kopieren. Weitere Informationen finden Sie unter [Wechseln in den Administratormodus.](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)
    
6. Starten Sie das Gerät neu. Dazu gibt es mehrere Möglichkeiten:

    - **Remote PowerShell** Sie können den Befehl Herunterfahren auf dem Gerät mithilfe von Remote PowerShell ausführen. Weitere Informationen finden Sie unter [Remoteverwaltung mit PowerShell](../rooms/rooms-operations.md).
    - **Ausführen von Restart-Computer** Sie können das Cmdlet auf Ihrem lokalen Computer ausführen und den Computernamen des Geräts angeben, `Restart-Computer` das Sie neu starten möchten. Weitere Informationen finden Sie unter [Neustart-Computer](/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7).

## <a name="step-5-configure-surface-hub"></a>Schritt 5: Konfigurieren von Surface Hub

Sie können windows configuration designer verwenden, um ein Bereitstellungspaket zu erstellen, mit dem Sie Einstellungen für koordinierende Besprechungen auf Ihre Surface Hubs anwenden können. Sie fügen die oben erstellte XML-Datei in den Windows-Konfigurations-Designer ein, um das Bereitstellungspaket zu erstellen.

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Erstellen einer XML-Konfigurationsdatei für koordinierte Besprechungen für Surface Hub

Sowohl Windows Configuration Designer als auch Microsoft Intune werden verwendet, um die Konfiguration für koordinierte Besprechungen auf Ihre Surface Hubs anzuwenden. Die Konfiguration wird mithilfe von XML definiert. Bevor Sie weiter gehen, müssen Sie die XML erstellen, die angewendet wird.

Im Folgenden wird die Syntax der #A0 "Koordinierte Besprechungen" beschrieben.

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

Gehen Sie wie folgt vor, um die XML für Windows Configuration Designer oder Microsoft Intune vorzubereiten:

1. Fügen Sie in einem Textdatei-Editor, z. B. Visual Studio Code oder Editor, den oben genannten XML-Code in eine neue Datei ein.

2. Legen Sie jedes der XML-Elemente auf den entsprechenden Wert oder `true` den Wert in Ihrer `false` Kalkulationstabelle an. Wenn Audio **standardmäßig** ist, legen Sie `true` z. `<Audio default="true">` B. .

3. Stellen Sie sicher, dass `TrustedAccounts` Sie zu Ihrer Liste der UPNs wechseln.

4. Der Windows-Konfigurations-Designer setzt voraus, dass sich der XML-Code in einer einzigen Zeile enthält. Entfernen Sie alle Zeilenumbrüche zwischen den einzelnen Zeilen, sodass die XML wie folgt aussieht:

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. Speichern Sie die Datei auf Ihrem Computer.

Nachdem Sie Ihre XML-Konfigurationsdatei erstellt haben, führen Sie die Schritte unter Verwalten von [Microsoft Teams-Einstellungen](surface-hub-manage-config.md) auf Surface Hub aus, um sie auf Ihre Surface Hubs anzuwenden.