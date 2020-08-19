---
title: Einrichten von koordinierten Besprechungen mit Microsoft Teams-Räumen und Surface Hub
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
description: Konfigurieren von Teams Room-Geräten und Surface Hub für die Teilnahme an Besprechungen, wenn ein Gerät oder der andere Teilnehmer an einer Besprechung teilnimmt.
ms.openlocfilehash: cfd8bd423d8f7765a973d55e42d64773a06bba32
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2020
ms.locfileid: "46803937"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Einrichten von koordinierten Besprechungen mit Microsoft Teams-Räumen und Surface Hub

Wenn Sie über ein oder mehrere Microsoft Teams rooms-Geräte oder Surface Hubs in einem Besprechungsraum verfügen, können Sie koordinierte Besprechungen einrichten. Durch koordinierte Besprechungen können Sie Ihre Teams rooms-Geräte und Surface-Hubs so einrichten, dass, wenn Sie an einer Besprechung auf einem Gerät teilnehmen, die anderen Geräte im Chatroom ebenfalls der gleichen Besprechung beigetreten sind. Sie können Ihre Kameras, Lautsprecher und Mikrofone so konfigurieren, dass diejenigen, die den Teilnehmern die optimale Benutzererfahrung bieten, aktiviert sind, während andere deaktiviert sind. Dies vermeidet die gefürchteten Echo-und Feedback Geräusche, die Teilnehmer beim Hinzufügen mehrerer Geräte zu einer Besprechung erleben können.

Um koordinierte Besprechungen einzurichten, müssen Sie sicherstellen, dass Ihre Teams rooms Devices und Surface Hubs bereits ordnungsgemäß für die Teilnahme an Besprechungen konfiguriert sind. Am wichtigsten ist, dass für jedes Gerät ein eigenes Exchange Room-Postfach vorhanden sein muss. Informationen zum Einrichten finden Sie in den folgenden Artikeln:

- [Bereitstellen von Microsoft Teams-Räume](../rooms/rooms-deploy.md)
- [Erstellen eines Surface Hub 2S-Geräte Kontos](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)

Nachdem Sie bestätigt haben, dass Ihre Teams rooms-Geräte und Surface Hubs automatisch Besprechungen annehmen und erfolgreich daran teilnehmen können, können Sie koordinierte Besprechungen einrichten.

Die folgenden Schritte sollten für jeden Besprechungsraum separat durchgeführt werden. Geräte in einem Besprechungsraum sollten nicht für koordinierte Besprechungen mit Geräten in anderen Besprechungsräumen eingerichtet werden.

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>Schritt 1: Planen einer koordinierten Besprechungs Erfahrung

Bevor Sie Konfigurationsänderungen vornehmen, müssen Sie entscheiden, welche Geräte was in jedem Besprechungsraum tun sollen. Das heißt, Sie müssen für einen bestimmten Besprechungsraum entscheiden, welches Gerät über das aktive Mikrofon, die Kamera und das Whiteboard verfügen soll. Wie Sie Ihre Geräte konfigurieren, hängt von der jeweiligen Umgebung ab, aber hier sind einige allgemeine Empfehlungen für den Einstieg:

- **Mikrofon** Geräte für Teams-Räume
- **Kamera** Teams Room-Gerät (standardmäßig aktiviert) und Surface Hub (standardmäßig deaktiviert, aber zulässig, von Teilnehmern aktiviert zu werden)
- **Whiteboard** Surface Hub

> [!IMPORTANT]
> Stellen Sie sicher, dass das Mikrofon nur auf einem Gerät aktiviert ist. Wenn Sie es auf mehr als einem Gerät aktivieren, erleben Sie Audio-Echo und Feedback.

## <a name="step-2-get-your-devices-upns"></a>Schritt 2: Abrufen der UPNs Ihrer Geräte

Wenn Sie in einem Besprechungsraum eine koordinierte Besprechungs Erfahrung einrichten, müssen Sie den Teams rooms Devices und Surface Hubs in diesem Raum mitteilen, mit welchen Geräten Sie koordinieren möchten. Dazu fügen Sie den Benutzerprinzipalnamen (User Principal Name, UPN) der Geräte hinzu, die mit seiner Konfiguration koordiniert werden sollen. Wenn Sie die UPNs für jedes Gerät, das Sie für koordinierte Besprechungen einrichten möchten, nicht kennen, können Sie diese über das Microsoft 365 Admin Center finden. 

Sie müssen einer Administratorrolle zugewiesen sein, um auf das Microsoft 365 Admin Center zugreifen zu können. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

Gehen Sie wie folgt vor, um die UPNs ihrer Teams rooms-Geräte und Surface-Hubs zu erhalten:

1. Wenn Sie sich beim Microsoft 365 Admin Center anmelden, besuchen Sie https://admin.microsoft.com .
2. Wechseln Sie zu **Benutzer**  >  **aktive Benutzer**.
3. Suchen Sie in der Spalte **Anzeigename** den Namen Ihres Teams rooms Device oder Surface Hub (Sie können das **Suchfeld** verwenden, wenn viele Benutzer vorhanden sind).
4. Suchen Sie den UPN in der Spalte **username** (er sieht so etwas wie Alias@contoso.com oder Alias@contoso.onmicrosoft.com) aus.
5. Wiederholen Sie diesen Vorgang für jedes Gerät, das an koordinierten Besprechungen teilnehmen soll.

## <a name="step-3-create-a-deployment-worksheet"></a>Schritt 3: Erstellen eines Bereitstellungs Arbeitsblatts

Nachdem Sie Ihre koordinierte Besprechungs Erfahrung geplant und eine Liste der UPNs Ihrer Geräte gesammelt haben, empfiehlt es sich, ein Bereitstellungs Arbeitsblatt zu erstellen. Ein Bereitstellungs Arbeitsblatt hilft Ihnen, die Konfiguration zu visualisieren, die Sie für alle Ihre Geräte festlegen möchten, sodass Sie Ihre Auswahl überprüfen und auf Fehler überprüfen können.

Fügen Sie in einer Tabellen Kalkulations-App Zeilen für Folgendes in der ersten Spalte hinzu:

| Einstellung                | Beschreibung      |
|------------------------|-----------------|
| **Audiostandard**      | Bestimmt, auf welchem Gerät das Mikrofon aktiv sein soll, wenn eine Besprechung gestartet wird. Dieses Feld kann nur auf einem Gerät (in der Regel in einem Team Room-Gerät) eingestellt werden, `true` während auf den restlichen Geräten dieses Feld auf " `false` Audio-Echo und-Feedback verhindern" gesetzt sein muss.          |
| **Audio aktiviert**      | Bestimmt, ob Teilnehmer an einer Besprechung das Mikrofon ein-oder ausschalten können. Bei Geräten, auf denen die Standardeinstellung für **Audio** festgelegt ist, `false` sollte diese Einstellung so festgelegt sein `false` , dass die Teilnehmer nicht versehentlich ein Mikrofon einschalten und audioechos oder Feedback verursachen können.<p>Wenn **Audiostandard** auf festgelegt ist `true` , wird diese Einstellung ignoriert, und die Teilnehmer können das Mikrofon stumm schalten oder die Stummschaltung aufheben.          |
| **Video Standard**      | Bestimmt, auf welchem Gerät die Kamera aktiv ist, wenn eine Besprechung gestartet wird. Für eine optimale Benutzerfreundlichkeit empfehlen wir, dass nur das Gerät "Teams Rooms" auf eingestellt ist, `true` während alle anderen Geräte auf fest eingestellt sind `false` .          |
| **Video aktiviert**      | Bestimmt, ob Teilnehmer an einer Besprechung die Kamera ein-oder ausschalten können. Sie können diese Einstellung `true` auf allen anderen Geräten in dem Ereignis festzulegen, in dem die Teilnehmer verschiedene Video Perspektiven freigeben möchten (beispielsweise, wenn ein Teilnehmer das Surface-Hub-Whiteboard verwendet). Wenn Sie nicht möchten, dass Teilnehmer eine Kamera auf einem Gerät ein-oder ausschalten, wählen Sie diese Option aus `false` .<p> Wenn **Video Standard** auf festgelegt ist `true` , wird diese Einstellung ignoriert, und die Teilnehmer können die Kamera ein-oder ausschalten.         |
| **Whiteboard-Standard** | Bestimmt, ob auf dem Gerät "Teams Rooms" ein Whiteboard angezeigt wird, das von einem der Besprechungsteilnehmer freigegeben wurde. Wir empfehlen, dass Sie diese Einstellung auf, `false` Wenn Sie über einen Surface-Hub verfügen und `true` Wenn Sie nicht über eine verfügen. Diese Einstellung hat keine Auswirkungen auf Surface Hubs. Surface Hubs zeigt immer ein Whiteboard an, das von Besprechungsteilnehmern freigegeben wird.         |
| **Whiteboard aktiviert** | Bestimmt, ob Teilnehmer an einer Besprechung das Whiteboard aktivieren oder deaktivieren können. Wenn Sie nicht möchten, dass Teilnehmer das Whiteboard auf einem Gerät ein-oder ausschalten, setzen Sie diese Einstellung auf `false` . <p>Wenn **Whiteboard Standard** auf festgelegt ist `true` , wird diese Einstellung ignoriert, und die Teilnehmer können das Whiteboard aktivieren oder deaktivieren.
| **Vertrauenswürdige Konten**   | Hierbei handelt es sich um eine durch trennzeichengetrennte Liste von UPNs für jedes TeamRoom-Gerät oder einen Surface-Hub, von dem das Gerät Besprechungsteilnahme Anforderungen annehmen soll oder an die Besprechungsteilnahme Anforderungen gesendet werden sollen. |

Fügen Sie in den nachfolgenden Spalten jedes Ihrer Teams rooms-Geräte und Surface-Hubs hinzu. Füllen Sie in jeder Spalte die Werte aus, die der für den Besprechungsraum gewünschten Erfahrung entsprechen. Im folgenden finden Sie ein Beispiel für ein Gerät mit einem Teams und einen Surface-Hub:

- Teams-Gerät
  - Audio und Video **werden beim Start einer Besprechung aktiviert.** Die Teilnehmer **können** Audio und Video ein-oder ausschalten.
  - Die Anzeige eines freigegebenen Whiteboards ist deaktiviert.
- Surface Hub
  - Audio **ist deaktiviert, wenn eine** Besprechung gestartet wird. Die Teilnehmer können die Audiofunktionen **nicht** aktivieren oder deaktivieren.
  - Video **ist deaktiviert, wenn eine** Besprechung gestartet wird. Teilnehmer **können** Video ein-oder ausschalten.

| Einstellung                | TeamRoom      | Surface Hub      |
|------------------------|-----------------|------------------|
| **Audiostandard**      | `true`          | `false`          |
| **Audio aktiviert**      | `true`          | `false`          |
| **Video Standard**      | `true`          | `false`          |
| **Video aktiviert**      | `true`          | `true`           |
| **Whiteboard-Standard** | `false`         | `false`          |
| **Vertrauenswürdige Konten**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>Schritt 4: Konfigurieren des Geräts "Teams Rooms"

Sie können entweder über den Touchscreen des Geräts koordinierte Besprechungen auf einem Teams Room-Gerät einrichten oder, wenn Sie viele Geräte einrichten müssen und dies von einem zentralen Ort aus tun möchten, eine XML-Konfigurationsdatei verwenden.

Verwenden Sie das Arbeitsblatt, das Sie im vorherigen Schritt erstellt haben, um Ihnen bei der Einrichtung Ihrer Geräte zu helfen.

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Verwenden des Touchscreen des Geräts "Teams Rooms"

Gehen Sie wie folgt vor, um koordinierte Besprechungen auf einem Gerät einzurichten:

1. Wählen Sie **... Weitere**  >  **Einstellungen**.
2. Geben Sie das Administrator Kennwort ein, und wählen Sie **Ja**aus.
3. Wählen Sie **koordinierte Besprechungen**aus.
4. Wählen Sie unter **Optionen die Option** **koordinierte Besprechung** auf _ein aus_.
5. Wenn **Audiostandard** in Ihrem Arbeitsblatt ist `true` , setzen Sie **das Mikrofon des Geräts** auf ein, andernfalls lassen Sie es _aus_.
6. Wenn **Audio** in Ihrem Arbeitsblatt aktiviert ist `true` , aktivieren Sie unter Aktivieren **des Mikrofons dieses Geräts die**Option **Personen ermöglichen, wenn Sie an einer Besprechung teilnehmen** . Diese Option kann nicht deaktiviert werden, wenn **das Mikrofon des Geräts** aktiviert ist.
7. Wenn Video in Ihrem Arbeitsblatt **standardmäßig** aktiviert ist `true` , aktivieren Sie die **Kamera dieses Geräts** auf ein, andernfalls lassen Sie es _aus_.
8. Wenn **Video** in Ihrem Arbeitsblatt aktiviert ist `true` , aktivieren Sie unter Aktivieren der **Kamera dieses Geräts die**Option **Personen aktivieren, wenn Sie an einer Besprechung teilnehmen** . Diese Option kann nicht deaktiviert _werden, wenn die_ **Kamera dieses Geräts** aktiviert ist.
9. Wenn das Whiteboard in Ihrem Arbeitsblatt **standardmäßig** aktiviert ist `true` , setzen Sie das **Whiteboarding auf diesem Gerät** auf _ein_, andernfalls lassen Sie es _aus_.
10. Geben Sie unter **Konten für vertrauenswürdige Geräte**jeden UPN ein, der in **vertrauenswürdigen Konten** auf dem Arbeitsblatt aufgeführt ist. Trennen Sie mehrere UPNs durch Kommas.
11. Wählen Sie **Speichern und beenden**aus.

Nachdem Sie **Speichern und beenden**ausgewählt haben, wird das Gerät neu gestartet und kann an koordinierten Besprechungen teilnehmen.

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Verwenden der XML-Konfigurationsdatei "Teams Rooms"

Koordinierte Besprechungen können mithilfe der `SkypeSettings.xml` XML-Konfigurationsdatei des Geräts "Teams Rooms" eingerichtet werden. Die `SkypeSettings.xml` Datei ist keine statische Datei. Wenn das Gerät "Teams Rooms" gestartet wird, checkt es `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` eine Datei mit dem Namen ein `SkypeSettings.xml` . Wenn die Datei vorhanden ist, liest und wendet das Gerät die in der Datei angegebene Konfiguration an. Nachdem Sie die Konfiguration angewendet haben, wird die Datei gelöscht. Weitere Informationen zur `SkypeSettings.xml` Datei finden Sie unter [Verwalten von Konsoleneinstellungen mit einer XML-Konfigurationsdatei](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file).

Die folgende Syntax enthält die Einstellungen für koordinierte Besprechungen in der Konfigurationsdatei:

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

1. Fügen Sie in einem Text Datei-Editor wie Visual Studio-Code oder Notepad das obige XML in eine neue Datei ein.

2. Setzen Sie die einzelnen XML-Elemente auf den `true` entsprechenden `false` Wert in Ihrer Kalkulationstabelle. Wenn beispielsweise " **Audio Standard** " lautet, ist " `true` festlegen" `<Audio default="true">` .

3. Stellen Sie sicher, dass Sie `TrustedAccounts` zu ihrer UPNs-Liste wechseln.

4. Speichern Sie die Datei unter dem Namen `SkypeSettings.xml` .

5. Speichern Sie die Datei im Ordner "Teams rooms Device `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` ". Sie können dies auf verschiedene Weise tun:

    - **Kopieren der Datei auf das Gerät Ihres Teams rooms** Sie müssen die Dateifreigabe aktivieren und eine Netzwerkfreigabe erstellen, bevor Sie Dateien auf Ihr Gerät kopieren können. Anschließend können Sie eine Verbindung mit der Netzwerkfreigabe herstellen und die Datei auf das Gerät kopieren. Weitere Informationen finden Sie unter [Wartung und Vorgänge in Microsoft Teams-Räumen](../rooms/rooms-operations.md).
    - **Verwenden einer Gruppenrichtlinie** Erstellen Sie eine Gruppenrichtlinie, um die Datei auf das Gerät zu kopieren. Weitere Informationen finden Sie unter [Übersicht über Gruppenrichtlinien](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11)).
    - **Herunterladen der Datei auf dem Gerät "Teams rooms** " Sie können sich mit dem Administratormodus beim Gerät anmelden und die Datei dann von einer Netzwerkfreigabe oder einem USB-Laufwerk auf das Gerät kopieren. Weitere Informationen finden Sie unter [Wechseln zum Administratormodus](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).
    
6. Starten Sie das Gerät neu. Sie haben mehrere Möglichkeiten:

    - **Remote-PowerShell** Sie können den Befehl shutdown auf dem Gerät mithilfe der Remote-PowerShell ausführen. Weitere Informationen finden Sie unter [Remote Verwaltung mithilfe von PowerShell](../rooms/rooms-operations.md).
    - **Neustart starten – Computer** Sie können das `Restart-Computer` Cmdlet auf dem lokalen Computer ausführen und den Computernamen des Geräts angeben, das Sie neu starten möchten. Weitere Informationen finden Sie unter [Restart-Computer](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7).

## <a name="step-5-configure-surface-hub"></a>Schritt 5: Konfigurieren des Surface Hub

Sie können den Windows-Konfigurations-Designer verwenden, um ein Bereitstellungspaket zu erstellen, das Sie verwenden können, um koordinierte Besprechungseinstellungen auf Ihre Surface Hubs anzuwenden. Sie fügen die oben erstellte XML-Datei in den Windows-Konfigurations-Designer ein, um das Bereitstellungspaket zu erstellen.

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Erstellen einer koordinierten XML-Konfigurationsdatei für Besprechungen für Surface Hub

Sowohl der Windows-Konfigurations-Designer als auch Microsoft InTune werden verwendet, um die koordinierte besprechungskonfiguration auf Ihre Surface Hubs anzuwenden. Die Konfiguration wird mithilfe von XML definiert. Bevor Sie fortfahren, müssen Sie die XML-Datei erstellen, die angewendet werden soll.

Im folgenden wird die Syntax der XML-Konfigurationsdatei für koordinierte Besprechungen aufgezählt.

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

Gehen Sie wie folgt vor, um den XML für Windows-Konfigurations-Designer oder Microsoft InTune vorzubereiten:

1. Fügen Sie in einem Text Datei-Editor wie Visual Studio-Code oder Notepad das obige XML in eine neue Datei ein.

2. Setzen Sie die einzelnen XML-Elemente auf den `true` entsprechenden `false` Wert in Ihrer Kalkulationstabelle. Wenn beispielsweise " **Audio Standard** " lautet, ist " `true` festlegen" `<Audio default="true">` .

3. Stellen Sie sicher, dass Sie `TrustedAccounts` zu ihrer UPNs-Liste wechseln.

4. Der Windows-Konfigurations-Designer setzt voraus, dass sich die XML-Datei in einer einzigen Zeile befindet. Entfernen Sie alle Zeilenumbrüche zwischen den Zeilen, damit der XML-Code wie folgt aussieht:

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. Speichern Sie die Datei auf Ihrem Computer.

Nachdem Sie Ihre XML-Konfigurationsdatei erstellt haben, führen Sie die Schritte unter [Verwalten von Microsoft Teams-Einstellungen auf Surface Hub](surface-hub-manage-config.md) aus, um Sie auf Ihre Surface Hubs anzuwenden.
