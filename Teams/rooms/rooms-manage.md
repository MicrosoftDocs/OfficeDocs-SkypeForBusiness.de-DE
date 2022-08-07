---
title: Microsoft Teams-Räume verwalten
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Erfahren Sie, wie Sie fortlaufende Wartungen und Vorgänge entwickeln und ausführen, um sicherzustellen, dass Ihre Microsoft Teams-Räume Systeme für Ihre Benutzer verfügbar sind.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 85bb58005159b18a426aed0851ac7a80b11183eb
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271092"
---
# <a name="manage-microsoft-teams-rooms"></a>Microsoft Teams-Räume verwalten

Wenn Sie Microsoft Teams-Räume in Ihrer Organisation haben, haben Sie flexible Verwaltungsoptionen.  Sie können die Geräte selbst an demselben zentralen Ort verwalten, an dem Sie alle Ihre Teams-Lösungen verwalten, das Microsoft Teams Admin Center. Alternativ können Sie die Verwaltungsverantwortung über [Microsoft Teams-Räume Managed Services](https://portal.rooms.microsoft.com) an dedizierte Experten übertragen.  Sie können den Verwaltungszugriff für eine der Optionen auch an einen Partner Ihrer Wahl delegieren.

Mit dem Microsoft Teams Admin Center haben Sie folgende Möglichkeiten:

- Durchführen der Geräteverwaltung, z. B. Neustarten von Geräten und Herunterladen von Geräteprotokollen
- Anwenden von Teams-spezifischen Einstellungen
- Überprüfen des Integritätsstatus von Microsoft Teams-Räume und deren Peripheriegeräten, einschließlich Kameras, Displays, Mikrofonen usw.
- Überprüfen der aktuellen und letzten Besprechungsaktivitäten (z. B. Details zur Anrufqualität, Netzwerkintegrität und -konnektivität und Anzahl der Teilnehmer)
- Anzeigen von Peripheriegeräten (z. B. Kameras und Projektoren), die mit Microsoft Teams-Räume verbunden sind

Um Teams-Räume Geräten zu verwalten, öffnen Sie das [Microsoft Teams Admin Center](https://admin.teams.microsoft.com), und wechseln Sie zu **Teams-Geräten** >  **Teams-Räume unter Windows**.

:::image type="content" source="../media/teams-rooms-summary2.png" alt-text="Teams-Räume Zusammenfassungsseite im Teams Admin Center.":::


> [!IMPORTANT]
> Zum Verwalten von Geräten mithilfe des Teams Admin Centers müssen Ihnen die Rollen "Globaler Administrator", "Teams-Administrator" oder "Teams-Geräteadministrator" zugewiesen sein.

## <a name="make-changes-to-teams-rooms-devices"></a>Vornehmen von Änderungen an Teams-Räume Geräten

Wenn Sie über mehrere Teams-Räume verfügen, können Sie die meisten Aktionen auf mehreren Geräten gleichzeitig ausführen. Sie können z. B. Teams-App-Einstellungen für alle Ihre Teams-Räume gleichzeitig festlegen.

### <a name="device-settings"></a>Geräteeinstellungen

Sie können Einstellungen für eine oder mehrere Teams-Räume in Ihrer Organisation ändern. Um Einstellungen zu ändern, wählen Sie das Oder die Geräte aus, die Sie verwalten möchten, und wählen Sie dann " **Einstellungen bearbeiten"** aus. Ein neuer Bereich wird mit allen Einstellungen geöffnet, die Sie ändern können. In der folgenden Tabelle sind die Einstellungen aufgeführt, die Sie mithilfe des Teams Admin Centers ändern können. Einige Einstellungen sind nur verfügbar, wenn Sie eine einzelne Teams-Räume auswählen.

Wenn Sie mehrere Optionen auswählen, werden in den Einstellungen, die die Massenbearbeitung unterstützen, die beiden folgenden Optionen angezeigt.

- **Vorhandenen Wert beibehalten** Wenn Sie diese Option auswählen, werden keine Änderungen an der Einstellung auf dem ausgewählten Teams-Räume vorgenommen.
- **Vorhandenen Wert ersetzen durch** Wenn Sie diese Option auswählen, können Sie die Einstellung auf dem Teams-Räume aktualisieren, den Sie mit dem von Ihnen bereitgestellten Wert ausgewählt haben.
    > [!CAUTION]
    > Vorhandene Werte für die Einstellungen, die Sie aktualisieren möchten, werden durch den von Ihnen angegebenen Wert ersetzt. Wenn Sie einer Liste vorhandener Werte hinzufügen möchten, müssen Sie die vorhandenen Werte mit dem Wert einschließen, den Sie hinzufügen möchten. Wenn z. B. eine Einstellung eine vorhandene Domänenliste von `contoso.com, fabrikam.com`, und Sie hinzufügen `northwindtraders.com`möchten, ist der Wert, den Sie bereitstellen `contoso.com, fabrikam.com, northwindtraders.com`müssen.
    >
    > Wenn Sie mehrere Teams-Räume auswählen, wird die Einstellung auf allen ausgewählten Geräten in den von Ihnen bereitgestellten Wert geändert. Wenn Teams-Räume unterschiedliche Werte für eine Einstellung haben, werden alle auf denselben Wert aktualisiert.

| Einstellung                                                      | Akzeptierte Werte                                        | Unterstützt massenbearbeitung |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *Konto*                                                    |                                                        |                    |
| **E-Mail**                                                    | Email Adresse                                          | Nein                 |
| **Unterstützter Besprechungsmodus**                                   | Nur Microsoft Teams<br>Skype for Business (Standard) und Microsoft Teams<br>Skype for Business und Microsoft Teams (Standard)<br>Nur Skype for Business|Ja|
| **Moderne Authentifizierung**                                    | Ein<br>Aus                                              | Ja                |
| **Exchange-Adresse**                                         | Email Adresse                                          | Nein                 |
| **Domäne\Benutzername (optional)**                               | Kontodomäne und Benutzername                           | Nein                 |
| **Domäne konfigurieren**                                         | Durch Trennzeichen getrennte Liste                                   | Ja                |
| *Besprechungen*                                                   |                                                        |                    |
| **Automatische Bildschirmfreigabe**                                 | Ein<br>Aus                                              | Ja                |
| **HDMI-Aufnahme der Audiofreigabe**                                 | Ein<br>Aus                                              | Ja                |
| **Anzeigen von Besprechungsnamen**                                       | Ein<br>Aus                                              | Ja                |
| **Automatisches Verlassen, wenn alle anderen Personen die Besprechung verlassen haben**                 | Ein<br>Aus                                              | Ja                |
| **Teilnehmen an Besprechungen von Drittanbietern**                 | Cisco Webex<br>Zoom                                              | Ja                |
| **Teilnehmen mit Rauminformationen**                 | Ausgewählt<br>Deaktiviert                                              | Ja                |
| **Teilnehmen mit benutzerdefinierten Informationen**                 | Ausgewählt<br>Deaktiviert                                              | Ja                |
| **Name (erforderlich)**                 | Name des Raums oder Leerzeichens                                              | Ja                |
| **Email (erforderlich)**                 | Email Adresse                                              | Ja                |
| *Gerät*                                                     |                                                        |                    |
| **Dual monitor mode**                                        | Ein<br>Aus                                              | Ja                |
| **Duplizierung von Inhalten zulassen** | Ausgewählt<br>Deaktiviert                                 | Ja                |
| **Bluetooth Beaconing**                                      | Ein<br>Aus                                              | Ja                |
| **Automatisches Annehmen von näherungsbasierten Besprechungseinladungen** | Ausgewählt<br>Deaktiviert                                 | Ja                |
| **Senden von Protokollen mit Feedback**                                  | Ein<br>Aus                                              | Ja                |
| **Email Adresse für Protokolle und Feedback**                      | Email Adresse                                          | Ja                |
| *Koordinieren von Besprechungen*                                                     |                                                        |                    |
| **Koordinierte Besprechungen** | Ein<br>Aus                                 | Nein                |
| **Mikrofon dieses Geräts aktivieren** | Ein<br>Aus                                 | Nein                |
| **Zulassen, dass Personen an einer Besprechung teilnehmen** | Ausgewählt<br>Deaktiviert                                 | Nein                |
| **Aktivieren der Kamera dieses Geräts** | Ein<br>Aus                                 | Nein                |
| **Zulassen, dass Personen an einer Besprechung teilnehmen** | Ausgewählt<br>Deaktiviert                                 | Nein                |
| **Whiteboarding für dieses Gerät aktivieren** | Ein<br>Aus                                 | Nein                |
| **Vertrauenswürdige Gerätekonten (getrennt durch Kommas)** | Liste der Geräte                              | Nein                |
| *Peripherals*                                                |                                                        |                    |
| **Konferenzmikrofon**                                  | Liste der verfügbaren Mikrofone                          | Nein                 |
| **Konferenzlautsprecher**                                     | Liste der verfügbaren Lautsprecher                             | Nein                 |
| **Standardvolume**                                           | 0-100                                                  | Nein                 |
| **Standardlautsprecher**                                          | Liste der verfügbaren Lautsprecher                             | Nein                 |
| **Standardvolume**                                           | 0-100                                                  | Nein                 |
| **Inhaltskamera**                                           | Liste der verfügbaren Kameras                              | Nein                 |
| **Verbesserungen an Inhaltskameras**                              | Ein<br>Aus                                              | Nein                 |
| **Inhaltskamera um 180 Grad drehen**                        | Ein<br>Aus                                              | Nein                 |
| *Theming*                                                    |                                                        |                    |
|                                                              | Standard<br>Kein Design<br>Benutzerdefinierte<br>Liste der integrierten Designs   | Ja                |

### <a name="cortana-settings"></a>Cortana-Einstellungen

Sie können Cortana für _die Sprachaktivierung_ oder _Push-Kommunikation_ mithilfe von PowerShell für alle Geräte in Ihrer Organisation oder für jedes Gerät separat aktivieren.

Weitere Informationen [finden Sie unter Microsoft Teams-Räume unter Windows](../cortana-in-teams.md) im Artikel "Cortana-Sprachunterstützung in Teams".

### <a name="front-row-layout-settings"></a>Layouteinstellungen für die erste Zeile

Die erste Zeile ist die Layoutoption für die Besprechungsansicht für Teams-Räume unter Windows.

| Teams-Gerät | App-Version | Anzeige vorn im Raum |
|--------------|-------------|-----------------------|
|Microsoft Teams-Räume unter Windows | 4.11.12.0 oder höher (die neueste Version wird empfohlen) | Unterstützt einzelne und duale Displays; Mindestgröße: 46 Zoll; Seitenverhältnis 16:9 mit einer Auflösung von 1920 x 1080 oder 21:9 mit einer Auflösung von 2560 x 1080; Alle Anzeigen sollten in den Windows-Einstellungen auf eine Skalierung von 100 % festgelegt werden. |

Sehen Sie [sich Microsoft Teams-Räume Wartung und Betrieb](rooms-operations.md#scale-and-resolution) an, um Ihre Anzeigeeinstellungen an die Anforderungen der ersten Zeile anzupassen.

Informationen zum Festlegen der Ersten Zeile als Standardlayout für einen Raum oder zum Deaktivieren finden [Sie unter Remoteverwaltung einer Microsoft Teams-Räume Konsoleneinstellungen mit einer XML-Konfigurationsdatei](xml-config-file.md#set-front-row-as-the-default-layout).

Weitere Informationen zum Verwalten der ersten Zeile finden Sie unter ["Bekannte Probleme](known-issues.md#Limits) ".

## <a name="device-restart-options"></a>Geräteneustartoptionen

Änderungen an den Geräteeinstellungen werden erst wirksam, nachdem Teams-Räume neu gestartet wurde. Wenn Sie Änderungen vornehmen, die einen Neustart erfordern, können Sie auswählen, ob sie sofort neu gestartet werden oder einen Neustart planen möchten. Hier sind die verfügbaren Neustartoptionen:

- **Sofortiger Neustart** Wenn Sie diese Option auswählen, werden alle Geräte, an der Sie Änderungen vornehmen, neu gestartet, sobald Sie diese Option auswählen.
- **Geplanter Neustart** Wenn Sie diese Option auswählen, können Sie die Geräte, an denen Sie Änderungen vornehmen, zu einem Zeitpunkt neu starten, der für Ihre Organisation weniger störend ist.
  - **Wählen Sie Datum und Uhrzeit** aus – Wählen Sie das bestimmte Datum und die Uhrzeit aus, um das Gerät neu zu starten. Datum und Uhrzeit, die Sie auswählen, sind lokal für das Gerät, das neu gestartet wird. 
  - **Update für den nächtlichen Neustart verlassen** Geräte werden nachts neu gestartet, um Wartungsarbeiten auszuführen. Änderungen, die Sie an Geräten vornehmen, werden während dieses Neustarts angewendet.

> [!CAUTION]
> Teams-Räume, die zum Zeitpunkt eines Neustarts verwendet werden, sind für die Dauer des Neustartvorgangs nicht mehr verfügbar. Sie werden von laufenden Besprechungen getrennt und stehen nicht zur Teilnahme an neuen Besprechungen zur Verfügung.

## <a name="remove-device"></a>Gerät entfernen

Wenn Sie ein Gerät entfernen, wird das Gerät aus Ihrer Organisation entfernt und nicht mehr in Ihrer Liste der Teams-Räume unter Windows im Teams Admin Center angezeigt.

Wenn Sie ein Gerät entfernen und es weiterhin mit einem gültigen Benutzernamen und Kennwort konfiguriert ist, wird es automatisch zu Ihrer Teams-Räume Liste hinzugefügt, wenn es erneut eine Verbindung mit Microsoft 365 herstellt.

Gehen Sie wie folgt vor, um ein oder mehrere Geräte zu entfernen:

1. Wechseln Sie zu **Teams-Geräten** >  **Teams-Räume unter Windows**, und wählen Sie die Geräte aus, die Sie entfernen möchten.
2. Wählen Sie **Entfernen** aus.

## <a name="download-device-logs"></a>Herunterladen von Geräteprotokollen

Sie können eine Kopie der Diagnoseprotokolldateien eines Geräts herunterladen, wenn Sie dazu vom Microsoft-Support angefordert werden. Protokolldateien werden in eine ZIP-Datei komprimiert, die aus dem Teams Admin Center heruntergeladen werden kann.

Gehen Sie wie folgt vor, um Protokolle von einem Teams-Räume Gerät auf Ihren Computer herunterzuladen:

1. Wechseln Sie zu **Teams-Geräten** >  **Teams-Räume unter Windows**, und wählen Sie den Namen des Geräts aus, von dem Sie Protokolle herunterladen möchten.
1. Wählen Sie **"Geräteprotokolle herunterladen" aus**. Es kann mehrere Minuten dauern, bis Geräteprotokolle verfügbar sind.
1. Wählen Sie die Registerkarte " **Verlauf** " und dann unter " **Diagnosedatei**" den Link "Protokolldatei" aus. Eine ZIP-Datei mit den Diagnoseprotokolldateien Ihres Geräts wird in den Standardordner "Downloads" Ihres Browsers heruntergeladen.

## <a name="view-device-information"></a>Anzeigen von Geräteinformationen

Im Teams Admin Center können Sie den Gesamtstatus aller Geräte in Ihrer Organisation anzeigen und Details zu jedem Gerät einzeln anzeigen.

### <a name="teams-rooms-system-dashboard"></a>Teams-Räume Systemdashboard

Das Teams-Räume-Systemdashboard zeigt Ihnen den Status und Die Integrität aller Ihrer Geräte auf einen Blick.

### <a name="device-details-view"></a>Ansicht "Gerätedetails"

Um detaillierte Informationen zu einem Gerät anzuzeigen, wählen Sie seinen Namen in der Geräteliste aus. In der Detailansicht werden die folgenden Informationen zu Ihrem Gerät angezeigt:

- **Integritätsstatus** Zeigt den Gesamtzustand des Teams-Raumgeräts an. Der Integritätsstatus kann entweder **"Fehlerfrei** " oder **"Fehlerhaft**" sein.
- **Offline seit** Zeigt das letzte Mal an, als Microsoft 365 mit dem Gerät kommunizieren konnte.
- **Gerätestatus** Zeigt den aktuellen Status des Geräts an: **Leerlauf**, **Teams-Besprechung**, **Skype-Besprechung** oder **Erfassung**.
- **Peripherals** Zeigt die Peripheriegeräte an, die mit Ihrem Teams Room-Gerät verbunden sind, und deren Integritätsstatus. Der Integritätsstatus kann entweder **"Verbunden** " oder **"Getrennt**" sein.
- **Gesundheit** Zeigt detaillierte Informationen zu den Peripheriegeräten, die mit Ihrem Teams Room-Gerät verbunden sind, Netzwerkkonnektivität, Anmeldestatus bei erforderlichen Diensten und Softwareversionsinformationen.
- **Details** Zeigt Herstellerinformationen, Netzwerk-IP-Adresse und serielle/MAC-Adresse des Teams-Raumgeräts an.
- **Aktivität** Zeigt frühere Besprechungsdetails an, einschließlich Datum und Uhrzeit der Besprechung, Anzahl der Teilnehmer, Dauer und Audioqualität. Weitere Informationen zu Besprechungsdetails finden Sie im Abschnitt " [Besprechungsaktivitätsdetails](#meeting-activity-details) " weiter unten in diesem Artikel.
- **Geschichte** Zeigt einen Verlauf der Verwaltungsaktivitäten auf dem Microsoft Teams-Raumgerät an, einschließlich Konfigurationsupdates, Geräteneustarts und Downloadlinks für Geräteprotokolle.

#### <a name="meeting-activity-details"></a>Details zu Besprechungsaktivitäten

Auf der Registerkarte " **Aktivität** " in den Gerätedetails des Teams-Raums werden allgemeine und detaillierte Informationen zu allen Besprechungen angezeigt, an der das Gerät im Laufe der Zeit teilgenommen hat. Auf der Registerkarte " **Aktivität** " können Sie sehen, wann eine Besprechung abgehalten wurde, wie viele Teilnehmer an der Besprechung teilgenommen haben, und die Audioqualität während der Besprechung.

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Teams Room-Geräteaktivitätszusammenfassungsliste.":::

Um die Detailinformationen zu einer bestimmten Besprechung anzuzeigen, wählen Sie das Datum und die Uhrzeit der Besprechung aus, zu der Sie weitere Informationen benötigen. Wenn eine Besprechung nur zwei Teilnehmer enthält, wird die Seite mit den Teilnehmerdetails angezeigt, andernfalls wird eine Teilnehmerzusammenfassungsseite angezeigt.

##### <a name="participant-summary"></a>Teilnehmerzusammenfassung

Auf der Teilnehmerzusammenfassungsseite werden alle Teilnehmer angezeigt, die an der Besprechung teilgenommen haben. Sie können sehen, wann jeder Teilnehmer der Besprechung beigetreten ist, dessen Name, Die Audioqualität und welche Features während der Sitzung verwendet wurden. Um die Details der Sitzung eines Teilnehmers anzuzeigen, wählen Sie die Startzeit der Sitzung für diesen Teilnehmer aus.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Konferenzdetails für Teams Room-Geräte.":::

##### <a name="participant-details"></a>Teilnehmerdetails

Auf der Seite mit den Teilnehmerdetails werden End-to-End-Diagnoseinformationen für die Sitzung dieses Teilnehmers angezeigt. Wie in der folgenden Grafik dargestellt, werden **Geräte**-, **System****- und Konnektivitätsinformationen** für den Teilnehmer und das Teams-Räume Gerät bereitgestellt. **Netzwerkdiagnoseinformationen** zwischen dem Teilnehmer und dem Teams-Räume Gerät werden ebenfalls bereitgestellt. Wählen Sie das Symbol für den Kontext aus, zu dem Sie weitere Informationen benötigen. Wenn Sie weitere Diagnoseinformationen benötigen, wählen Sie die Registerkarte " **Erweitert** " aus.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Anrufdetails für Teams Room-Geräte.":::
