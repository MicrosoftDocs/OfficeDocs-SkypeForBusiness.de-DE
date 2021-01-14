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
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie fortlaufende Wartungs- und Betriebsvorgänge entwickeln und ausführen, um sicherzustellen, dass Ihre Microsoft Teams Rooms-Systeme für Ihre Benutzer verfügbar sind.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 830caffbbb0256e64198e84876a4067337e90266
ms.sourcegitcommit: c537b1cf03e7ac5d07f2fbf4ba73d73c510f3d96
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49848837"
---
# <a name="manage-microsoft-teams-rooms"></a>Microsoft Teams-Räume verwalten

Wenn Sie über Geräte in Ihrer Organisation verfügen, für die Microsoft Teams Rooms zertifiziert sind, haben Sie flexible Verwaltungsoptionen.  Sie können die Geräte selbst an demselben zentralen Ort verwalten, an dem Sie alle Ihre Teams-Lösungen verwalten, microsoft Teams Admin Center, oder Sie können Verwaltungsverantwortliche mithilfe der verwalteten Dienste von Microsoft Teams Rooms an dedizierte Experten [übertragen.](https://portal.rooms.microsoft.com)  Sie können den Verwaltungszugriff für eine der Optionen auch an einen Partner Ihrer Wahl delegieren.

Mit dem Microsoft Teams Admin Center können Sie:

- Ausführen der Geräteverwaltung wie Neustarten oder Blockieren von Geräten und Herunterladen von Geräteprotokollen
- Anwenden von Teams-spezifischen Einstellungen
- Überprüfen sie den Integritätsstatus von Microsoft Teams Room-Geräten und ihren Peripheriegeräten, einschließlich Kameras, Anzeigen, Mikrofonen und so weiter
- Überprüfen der aktuellen und vergangenen Besprechungsaktivität (z. B. Details zur Anrufqualität, Netzwerkinte health und Konnektivität und Anzahl der Teilnehmer)
- Peripheriegeräte (z. B. Kameras und Projektoren) sehen, die an ein Microsoft Teams -Raumgerät angeschlossen sind

Um Geräte von Teams Rooms zu verwalten, öffnen Sie [das Microsoft Teams Admin Center,](https://admin.teams.microsoft.com) und wechseln Sie zu **"Geräte-Teams-Räume".**  >  

:::image type="content" source="../media/teams-rooms-summary.png" alt-text="Zusammenfassungsseiten von Teams Rooms im Teams Admin Center":::

> [!IMPORTANT]
> Zum Verwalten von Geräten über das Teams Admin Center müssen Ihnen die Rollen "Globaler Administrator", "Teams-Dienstadministrator" oder "Teams-Geräteadministrator" zugewiesen sein.

## <a name="make-changes-to-teams-rooms-devices"></a>Änderungen an Den Geräten in Teams Rooms vornehmen

Wenn Sie über mehrere Teams Rooms verfügen, können Sie die meisten Aktionen auf mehreren Geräten gleichzeitig ausführen. So können Sie beispielsweise Einstellungen für die Teams-App auf allen Ihren Geräten gleichzeitig festlegen.

### <a name="device-settings"></a>Geräteeinstellungen

Sie können Einstellungen auf einem oder mehreren Geräten in Ihrer Organisation ändern. Um Einstellungen zu ändern, wählen Sie das oder die Geräte aus, die Sie verwalten möchten, und wählen Sie dann **"Einstellungen bearbeiten" aus.** Es wird ein neuer Bereich mit allen Einstellungen geöffnet, die Sie auf Ihren Geräten ändern können. In der folgenden Tabelle sind die Einstellungen aufgeführt, die Sie im Teams Admin Center ändern können. Einige Einstellungen sind nur verfügbar, wenn Sie ein einzelnes Gerät auswählen.

Wenn Sie mehrere Geräte auswählen, werden in den Einstellungen, die die Massenbearbeitung unterstützen, die beiden folgenden Optionen angezeigt.

- **Vorhandenen Wert behalten** Wenn Sie diese Option auswählen, werden auf den ausgewählten Geräten keine Änderungen an der Einstellung vorgenommen.
- **Ersetzen eines vorhandenen Werts durch** Wenn Sie diese Option auswählen, können Sie die Einstellung auf den ausgewählten Geräten mit dem von Ihnen ausgewählten Wert aktualisieren.
    > [!CAUTION]
    > Vorhandene Werte in den Einstellungen, die Sie aktualisieren möchten, werden durch den von Ihnen angegebenen Wert ersetzt. Wenn Sie eine Liste vorhandener Werte hinzufügen möchten, müssen Sie die vorhandenen Werte in den Wert, den Sie hinzufügen möchten, hinzufügen. Wenn eine Einstellung z. B. eine vorhandene Domänenliste von enthält und Sie hinzufügen möchten, müssten Sie den Wert `contoso.com, fabrikam.com` `northwindtraders.com` ". `contoso.com, fabrikam.com, northwindtraders.com`
    >
    > Wenn Sie mehrere Geräte auswählen, wird die Einstellung auf allen von Ihnen ausgewählten Geräten in den von Ihnen angezeigten Wert geändert. Wenn Geräte unterschiedliche Werte für eine Einstellung haben, werden sie alle auf denselben Wert aktualisiert.

| Einstellung                                                      | Akzeptierte Werte                                        | Unterstützt massenbearbeitung |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *Konto*                                                    |                                                        |                    |
| **E-Mail**                                                    | E-Mail-Adresse                                          | Nein                 |
| **Unterstützter Besprechungsmodus**                                   | Skype for Business (Standard) und Microsoft Teams<br>Skype for Business und Microsoft Teams (Standard)<br>Nur Skype for Business|Ja|
| **Moderne Authentifizierung**                                    | Ein<br>Aus                                              | Ja                |
| **Exchange-Adresse**                                         | E-Mail-Adresse                                          | Nein                 |
| **Domäne\Benutzername (optional)**                               | Kontodomäne und Benutzername                           | Nein                 |
| **Domäne konfigurieren**                                         | Durch Kommas getrennte Liste                                   | Ja                |
| *Besprechungen*                                                   |                                                        |                    |
| **Automatische Bildschirmfreigabe**                                 | Ein<br>Aus                                              | Ja                |
| **Anzeigen von Besprechungsnamen**                                       | Ein<br>Aus                                              | Ja                |
| **Automatisches Verlassen der Besprechung, wenn alle anderen die Besprechung verlassen haben**                 | Ein<br>Aus                                              | Ja                |
| *Gerät*                                                     |                                                        |                    |
| **Modus mit zwei Monitoren**                                        | Ein<br>Aus                                              | Ja                |
| **Bluetooth beacons**                                      | Ein<br>Aus                                              | Ja                |
| **Automatisches Annehmen von näherungsbasierten Besprechungseinladungen** | Ausgewählt<br>Nicht ausgewählt                                 | Ja                |
| **Senden von Protokollen mit Feedback**                                  | Ein<br>Aus                                              | Ja                |
| **E-Mail-Adresse für Protokolle und Feedback**                      | E-Mail-Adresse                                          | Ja                |
| *Peripheriegeräte*                                                |                                                        |                    |
| **Konferenzmikrofon**                                  | Liste der verfügbaren Mikrofone                          | Nein                 |
| **Konferenzlautsprecher**                                     | Liste der verfügbaren Lautsprecher                             | Nein                 |
| **Standardlautstärke**                                           | 0-100                                                  | Nein                 |
| **Standardlautsprecher**                                          | Liste der verfügbaren Lautsprecher                             | Nein                 |
| **Standardlautstärke**                                           | 0-100                                                  | Nein                 |
| **Inhaltskamera**                                           | Liste der verfügbaren Kameras                              | Nein                 |
| **Inhaltskameraerweiterungen**                              | Ein<br>Aus                                              | Nein                 |
| **Drehen der Inhaltskamera um 180 Grad**                        | Ein<br>Aus                                              | Nein                 |
| *"Theming"*                                                    |                                                        |                    |
|                                                              | Standard<br>Kein Design<br>Benutzerdefiniert<br>Liste der integrierten Designs   | Ja                |

### <a name="device-restart-options"></a>Optionen für den Geräteneustart

Änderungen an den Geräteeinstellungen werden erst wirksam, nachdem die Geräte neu gestartet wurden. Wenn Sie Änderungen vornehmen, die einen Neustart erforderlich machen, können Sie auswählen, ob die Geräte sofort neu gestartet oder ein Neustart geplant werden soll. Hier sind die verfügbaren Neustartoptionen:

- **Sofortiger Neustart** Wenn Sie diese Option auswählen, werden alle Geräte, an deren Änderungen Sie Änderungen vornehmen, neu gestartet, sobald Sie diese Option auswählen.
- **Geplanter Neustart** Wenn Sie diese Option auswählen, können Sie die Geräte neu starten, an derEn Änderungen Sie vornehmen, und dies zu einem Zeitpunkt, der für Ihre Organisation weniger störend ist.
  - **Datum und Uhrzeit auswählen** – Wählen Sie das Datum und die Uhrzeit für den Neustart des Geräts aus. Datum und Uhrzeit des neu gestarteten Geräts sind lokal. 
  - **Update für nächtlichen Neustart verlassen** Geräte werden nachts neu gestartet, um Wartungen durchzuführen. Änderungen, die Sie an Geräten vornehmen, werden während dieses Neustarts angewendet.

> [!CAUTION]
> Geräte, die zum Zeitpunkt eines Neustarts verwendet werden, stehen während des Neustartvorgangs nicht mehr zur Verfügung. Sie werden von besprechungsbesprechungen getrennt und stehen nicht zur Verfügung, um an neuen Besprechungen teilzunehmen.

### <a name="remove-or-block-a-device"></a>Entfernen oder Blockieren eines Geräts

Wenn Sie **ein** Gerät entfernen, wird das Gerät aus Ihrer Organisation entfernt und nicht mehr in Ihrer Liste der Teams -Räume-Geräte im Teams Admin Center angezeigt. 

Wenn Sie **ein Gerät** blockieren, kommuniziert Teams nicht mehr mit dem Gerät. Blockierte Geräte werden auch dann nicht gesendet, wenn sie zu einer Gruppe von Geräten gehören, die in Massen bearbeitet werden. Sie wird weiterhin in Ihrer Liste der Teams -Räume-Geräte mit dem Status **"Blockiert" aufgeführt.**

Unabhängig davon, ob ein Gerät blockiert oder entfernt wurde, wenn es noch mit einem gültigen Benutzernamen und Kennwort konfiguriert ist, wird es automatisch erneut zu Ihrer Liste der Geräte in Teams -Räumen hinzugefügt, wenn es eine Verbindung mit Microsoft 365 herstellt.

Gehen Sie wie folgt vor, um ein oder mehrere Geräte zu entfernen:

1. Wechseln Sie **zu**  >  **Geräte-Teams-Räume,** und wählen Sie die Geräte aus, die Sie entfernen möchten.
1. Wählen Sie **Entfernen** aus.

Gehen Sie wie folgt vor, um ein Gerät zu blockieren:

1. Wechseln Sie **zu**  >  **"Geräte-Teams-Räume",** und wählen Sie den Namen des Geräts aus, das Sie blockieren möchten.
1. Wählen Sie auf der  Seite "Gerätedetails" in der oberen rechten Ecke der Seite "Aktionen" aus.
1. Wählen Sie **"Blockieren" aus.**

Wenn Sie die Blockierung eines Geräts aufheben möchten, gehen Sie wie folgt vor:

1. Wechseln Sie **zu**  >  **"Geräte-Teams-Räume",** und wählen Sie den Namen des Geräts aus, das Sie blockieren möchten.
1. Wählen Sie auf der  Seite "Gerätedetails" in der oberen rechten Ecke der Seite "Aktionen" aus.
1. Wählen Sie **"Blockierung aufheben" aus.**

## <a name="download-device-logs"></a>Herunterladen von Geräteprotokollen

Sie können eine Kopie der Diagnoseprotokolldateien eines Geräts herunterladen, wenn Sie vom Support von Microsoft dazu aufgefordert werden. Protokolldateien werden in eine ZIP-Datei komprimiert, die aus dem Teams Admin Center heruntergeladen werden kann.

Gehen Sie wie folgt vor, um Protokolle von einem Gerät in Teams Rooms auf Ihren Computer herunterzuladen:

1. Wechseln Sie **zu**  >  **"Geräte-Teams-Räume",** und wählen Sie den Namen des Geräts aus, von dem Sie Protokolle herunterladen möchten.
1. Wählen Sie **"Geräteprotokolle herunterladen" aus.** Es kann einige Minuten dauern, bis Geräteprotokolle verfügbar sind.
1. Wählen Sie die **Registerkarte "Verlauf"** und dann unter "Diagnosedatei" den **Link "Protokolldatei" aus.** Eine ZIP-Datei, die die Diagnoseprotokolldateien Ihres Geräts enthält, wird in den Standardordner "Downloads" Ihres Browsers heruntergeladen.

## <a name="view-device-information"></a>Anzeigen von Geräteinformationen

Im Teams Admin Center können Sie den Gesamtstatus aller Geräte in Ihrer Organisation und details zu jedem Gerät einzeln anzeigen.

### <a name="teams-rooms-system-dashboard"></a>Teams Rooms system dashboard

Im Systemdashboard von Teams Rooms können Sie den Status und Status aller Ihrer Geräte auf einen Blick sehen.

### <a name="device-details-view"></a>Ansicht "Gerätedetails"

Wenn Sie detaillierte Informationen zu einem Gerät anzeigen möchten, wählen Sie dessen Namen aus der Geräteliste aus. In der Detailansicht werden die folgenden Informationen zu Ihrem Gerät angezeigt:

- **Integritätsstatus** Zeigt den Gesamtzustand des Teams Room-Geräts an. Der Integritätsstatus kann **"Fehlerfrei"** oder **"fehlerhaft" sein.**
- **Offline seit** Zeigt an, wie lange Microsoft 365 zuletzt mit dem Gerät kommunizieren konnte.
- **Gerätestatus** Zeigt den aktuellen Status des Geräts an: **"Idle",** **"Teams-Besprechung",** **"Skype-Besprechung"** oder **"Erfassung".**
- **Peripheriegeräte** Zeigt die Peripheriegeräte, die mit Ihrem Teams Room-Gerät verbunden sind, und deren Integritätsstatus an. Der Status kann entweder **"Verbunden" oder** **"Getrennt" sein.**
- **Integrität** Zeigt detaillierte Informationen zu den Peripheriegeräten an, die mit Ihrem Teams-Raumgerät verbunden sind, Netzwerkkonnektivität, Anmeldestatus bei erforderlichen Diensten und Softwareversionsinformationen.
- **Details** Zeigt Herstellerinformationen, Netzwerk-IP-Adresse und Seriennummer/MAC-Adresse des Teams Room-Geräts an.
- **Aktivität** Zeigt vergangene Besprechungsdetails an, einschließlich Datum und Uhrzeit der Besprechung, Anzahl der Teilnehmer, Dauer und Audioqualität. Weitere Informationen zu Besprechungsdetails finden Sie im Abschnitt ["Besprechungsdetails"](#meeting-activity-details) weiter unten in diesem Artikel.
- **Verlauf** Zeigt einen Verlauf der Verwaltungsaktivitäten auf dem Teams Room-Gerät, einschließlich Konfigurationsupdates, Geräteneustarts und Downloadlinks für Geräteprotokolle.

#### <a name="meeting-activity-details"></a>Details zur Besprechungsaktivität

Auf **der Registerkarte "Aktivität"** in den Gerätedetails des Teams Room werden qualitativ hochwertige und detaillierte Informationen zu allen Besprechungen angezeigt, an der das Gerät im Laufe der Zeit teilgenommen hat. Auf der **Registerkarte "Aktivität"** können Sie sehen, wann eine Besprechung abgehalten wurde, wie viele Teilnehmer an der Besprechung teilgenommen haben sowie die Audioqualität während der Besprechung.

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Teams Room device activity summary list":::

Wenn Sie die Detailinformationen zu einer bestimmten Besprechung sehen möchten, wählen Sie das Datum und die Uhrzeit der Besprechung aus, zu der Sie weitere Informationen wünschen. Wenn eine Besprechung nur zwei Teilnehmer enthält, wird die Seite mit den Teilnehmerdetails angezeigt, andernfalls wird eine Teilnehmerzusammenfassungsseite angezeigt.

##### <a name="participant-summary"></a>Teilnehmerzusammenfassung

Auf der Teilnehmerzusammenfassungsseite werden alle Teilnehmer angezeigt, die an der Besprechung teilgenommen haben. Sie können sehen, wann jeder Teilnehmer der Besprechung beigetreten ist, seinen Namen, die Audioqualität und welche Features während der Sitzung verwendet wurden. Um die Details der Sitzung eines Teilnehmers anzuzeigen, wählen Sie die Startzeit der Sitzung für den Teilnehmer aus.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Konferenzdetails für Teams Raumgeräte":::

##### <a name="participant-details"></a>Teilnehmerdetails

Auf der Seite mit den Teilnehmerdetails werden End-to-End-Diagnoseinformationen für die Sitzung dieses Teilnehmers angezeigt. Wie in der folgenden Abbildung gezeigt,  werden **Geräte-,** **System-** und Verbindungsinformationen für den Teilnehmer und für das Gerät "Teams Rooms" bereitgestellt. **Es** werden auch Netzwerkdiagnoseinformationen zwischen dem Teilnehmer und dem Gerät "Teams Rooms" bereitgestellt. Wählen Sie das Symbol für den Kontext aus, zu dem Sie weitere Informationen wünschen. Um weitere Diagnoseinformationen zu erhalten, wählen Sie die Registerkarte **"Erweitert"** aus.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Anrufdetails für Teams Room-Geräte":::
