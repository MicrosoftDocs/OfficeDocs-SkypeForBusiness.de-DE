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
description: Hier erfahren Sie, wie Sie fortlaufende Wartungs- und Betriebsvorgänge entwickeln und ausführen, um sicherzustellen, dass Ihre Microsoft Teams-Räume-Systeme für Ihre Benutzer verfügbar sind.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dbe3a22b86fa9f4b0773e1a7397bb206deb093e1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58636639"
---
# <a name="manage-microsoft-teams-rooms"></a>Microsoft Teams-Räume verwalten

Wenn Sie über Microsoft Teams-Räume zertifizierten Geräten in Ihrer Organisation verfügen, haben Sie flexible Verwaltungsoptionen.  Sie können die Geräte selbst an demselben zentralen Ort verwalten, an dem Sie alle Ihre Teams-Lösungen, Microsoft Teams Admin Center verwalten, oder Sie können Verwaltungsverantwortliche an dedizierte Experten mit Microsoft Teams-Räume [Managed Services übertragen.](https://portal.rooms.microsoft.com)  Sie können für eine der Optionen auch den Verwaltungszugriff an einen Partner Ihrer Wahl delegieren.

Mit Microsoft Teams Admin Center können Sie:

- Ausführen der Geräteverwaltung wie Neustarten von Geräten und Herunterladen von Geräteprotokollen
- Anwenden Teams spezifischen Einstellungen
- Überprüfen des Integritätsstatus Microsoft Teams Raumgeräten und ihren Peripheriegeräten, einschließlich Kameras, Anzeigen, Mikrofonen und so weiter
- Überprüfen der aktuellen und vergangenen Besprechungsaktivität (z. B. Details zur Anrufqualität, Netzwerkinte health und Konnektivität und Anzahl der Teilnehmer)
- Peripheriegeräte (z. B. Kameras und Projektoren) sehen, die an ein Microsoft Teams Raumgerät angeschlossen sind

Um Ihre Teams-Räume zu verwalten, öffnen Sie [das Microsoft Teams Admin Center,](https://admin.teams.microsoft.com) und wechseln Sie **zu** Geräte  >  **Teams-Räume.**

:::image type="content" source="../media/teams-rooms-summary.png" alt-text="Teams-Räume von Zusammenfassungsseiten im Teams Admin Center":::

> [!IMPORTANT]
> Zum Verwalten von Geräten über Teams Admin Center müssen Ihnen die Rollen "Globaler Administrator", "Teams-Administrator" oder "Teams"-Administrator zugewiesen sein.

## <a name="make-changes-to-teams-rooms-devices"></a>Vornehmen von Änderungen an Teams-Räume-Geräten

Wenn Sie über mehrere Teams-Räume verfügen, können Sie die meisten Aktionen auf mehreren Geräten gleichzeitig ausführen. So können Sie beispielsweise Teams Auf allen Ihren Geräten gleichzeitig festlegen.

### <a name="device-settings"></a>Geräteeinstellungen

Sie können Einstellungen auf einem oder mehreren Geräten in Ihrer Organisation ändern. Wenn Sie Einstellungen ändern möchten, wählen Sie das zu verwaltende Gerät bzw. die zu verwaltende Geräte und dann Bearbeiten **Einstellungen.** Ein neuer Bereich mit allen Einstellungen, die Sie auf Ihren Geräten ändern können, wird geöffnet. In der folgenden Tabelle sind die Einstellungen aufgeführt, die Sie mithilfe des Teams Admin Center ändern können. Einige Einstellungen sind nur verfügbar, wenn Sie ein einzelnes Gerät auswählen.

Wenn Sie mehrere Geräte auswählen, werden für Einstellungen, die die Massenbearbeitung unterstützen, die beiden folgenden Optionen angezeigt:

- **Vorhandenen Wert behalten** Wenn Sie diese Option auswählen, werden auf den ausgewählten Geräten keine Änderungen an der Einstellung vorgenommen.
- **Ersetzen eines vorhandenen Werts durch** Wenn Sie diese Option auswählen, können Sie die Einstellung auf den ausgewählten Geräten mit dem von Ihnen ausgewählten Wert aktualisieren.
    > [!CAUTION]
    > Vorhandene Werte in den Einstellungen, die Sie aktualisieren möchten, werden durch den von Ihnen angegebenen Wert ersetzt. Wenn Sie eine Liste mit vorhandenen Werten hinzufügen möchten, müssen Sie die vorhandenen Werte in den Wert, den Sie hinzufügen möchten, hinzufügen. Wenn eine Einstellung beispielsweise über eine vorhandene Domänenliste mit verfügt und Sie hinzufügen möchten, müssten Sie den Wert `contoso.com, fabrikam.com` `northwindtraders.com` von `contoso.com, fabrikam.com, northwindtraders.com` bereitstellen.
    >
    > Wenn Sie mehrere Geräte auswählen, wird die Einstellung auf allen von Ihnen ausgewählten Geräten in den von Ihnen verwendeten Wert geändert. Wenn Geräte unterschiedliche Werte für eine Einstellung haben, werden alle auf denselben Wert aktualisiert.

| Einstellung                                                      | Akzeptierte Werte                                        | Unterstützt die Massenbearbeitung |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *Konto*                                                    |                                                        |                    |
| **E-Mail**                                                    | E-Mail-Adresse                                          | Nein                 |
| **Unterstützter Besprechungsmodus**                                   | Skype for Business (Standard) und Microsoft Teams<br>Skype for Business und Microsoft Teams (Standard)<br>Skype for Business Nur|Ja|
| **Moderne Authentifizierung**                                    | Ein<br>Aus                                              | Ja                |
| **Exchange adresse**                                         | E-Mail-Adresse                                          | Nein                 |
| **Domäne\Benutzername (optional)**                               | Kontodomäne und Benutzername                           | Nein                 |
| **Domäne konfigurieren**                                         | Durch Kommas getrennte Liste                                   | Ja                |
| *Besprechungen*                                                   |                                                        |                    |
| **Automatische Bildschirmfreigabe**                                 | Ein<br>Aus                                              | Ja                |
| **Anzeigen von Besprechungsnamen**                                       | Ein<br>Aus                                              | Ja                |
| **Automatisches Verlassen, wenn alle anderen die Besprechung verlassen haben**                 | Ein<br>Aus                                              | Ja                |
| *Gerät*                                                     |                                                        |                    |
| **Modus mit zwei Monitoren**                                        | Ein<br>Aus                                              | Ja                |
| **Bluetooth beacing**                                      | Ein<br>Aus                                              | Ja                |
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
| **Erweiterungen für die Inhaltskamera**                              | Ein<br>Aus                                              | Nein                 |
| **Inhaltskamera um 180 Grad drehen**                        | Ein<br>Aus                                              | Nein                 |
| *Theming*                                                    |                                                        |                    |
|                                                              | Standard<br>Kein Design<br>Benutzerdefiniert<br>Liste der integrierten Designs   | Ja                |

### <a name="device-restart-options"></a>Optionen für den Geräteneustart

Änderungen an den Geräteeinstellungen werden erst wirksam, nachdem die Geräte neu gestartet wurden. Wenn Sie Änderungen vornehmen, die neu gestartet werden müssen, können Sie auswählen, ob die Geräte sofort neu gestartet oder ein Neustart geplant werden soll. Hier sind die verfügbaren Neustartoptionen:

- **Sofortiger Neustart** Wenn Sie diese Option auswählen, werden alle Geräte, an der Sie Änderungen vornehmen, neu gestartet, sobald Sie diese Option auswählen.
- **Geplanter Neustart** Wenn Sie diese Option auswählen, können Sie die Geräte neu starten, an der Sie Änderungen vornehmen, zu einer Zeit, die für Ihre Organisation weniger störend ist.
  - **Datum und Uhrzeit auswählen:** Wählen Sie das Datum und die Uhrzeit für den Neustart des Geräts aus. Datum und Uhrzeit des neu gestarteten Geräts sind lokal. 
  - **Update für nächtlichen Neustart verlassen** Geräte werden für Wartungen nachts neu gestartet. Änderungen, die Sie an Geräten vornehmen, werden während dieses Neustarts angewendet.

> [!CAUTION]
> Geräte, die zum Zeitpunkt eines Neustarts verwendet werden, sind für die Dauer des Neustartvorgangs nicht mehr verfügbar. Sie werden von ihren in Bearbeitungen ausgeführten Besprechungen getrennt und stehen nicht zur Verfügung, um an neuen Besprechungen teilzunehmen.

### <a name="remove-device"></a>Gerät entfernen

Wenn Sie ein Gerät entfernen, wird das Gerät aus Ihrer Organisation entfernt und in Ihrer Liste der Teams-Räume-Geräte im Teams Admin Center nicht mehr angezeigt.

Wenn Sie ein Gerät entfernen und es weiterhin mit einem gültigen Benutzernamen und Kennwort konfiguriert ist, wird es automatisch erneut zu Ihrer Teams-Räume-Geräteliste hinzugefügt, wenn es erneut eine Verbindung mit Microsoft 365 herstellt.

Gehen Sie wie folgt vor, um ein oder mehrere Geräte zu entfernen:

1. Wechseln Sie **zu**  >  **Geräte Teams-Räume** und wählen Sie die Geräte aus, die Sie entfernen möchten.
1. Wählen Sie **Entfernen** aus.

## <a name="download-device-logs"></a>Herunterladen von Geräteprotokollen

Sie können eine Kopie der Diagnoseprotokolldateien eines Geräts herunterladen, wenn Sie vom Microsoft-Support dazu aufgefordert werden. Protokolldateien werden in eine ZIP-Datei komprimiert, die aus dem Admin Center Teams werden kann.

Gehen Sie wie folgt vor, Teams-Räume Protokolle von einem anderen Gerät auf Ihren Computer herunterzuladen:

1. Wechseln Sie **zu Teams-Räume** und wählen Sie den Namen des Geräts aus, von dem Sie Protokolle herunterladen  >   möchten.
1. Wählen Sie **Geräteprotokolle herunterladen aus.** Es kann einige Minuten dauern, bis Geräteprotokolle verfügbar sind.
1. Wählen Sie die **Registerkarte** Verlauf und dann unter Diagnosedatei den Link **Protokolldatei aus.** Eine ZIP-Datei, die die Diagnoseprotokolldateien Ihres Geräts enthält, wird in den Standardordner "Downloads" Ihres Browsers heruntergeladen.

## <a name="view-device-information"></a>Anzeigen von Geräteinformationen

Im Teams Admin Center können Sie den Gesamtstatus aller Geräte in Ihrer Organisation und Details zu den einzelnen Geräten anzeigen.

### <a name="teams-rooms-system-dashboard"></a>Teams-Räume Systemdashboard

Im Teams-Räume Systemdashboard können Sie den Status und Status aller Ihrer Geräte auf einen Blick sehen.

### <a name="device-details-view"></a>Ansicht "Gerätedetails"

Wenn Sie detaillierte Informationen zu einem Gerät anzeigen möchten, wählen Sie dessen Namen aus der Geräteliste aus. In der Detailansicht werden die folgenden Informationen zu Ihrem Gerät angezeigt:

- **Integritätsstatus** Zeigt den Gesamtzustand des Teams Des Raumgeräts an. Der Status kann entweder fehlerfrei **oder** **fehlerhaft sein.**
- **Offline seit** Zeigt an, wie Microsoft 365 zuletzt mit dem Gerät kommunizieren konnte.
- **Gerätestatus** Zeigt den aktuellen Status des Geräts an: **Im** Leerlauf, **Teams Besprechung,** **Skype Besprechung** oder **Ingest.**
- **Peripheriegeräte** Zeigt die an Ihr Gerät angeschlossenen Peripheriegeräte Teams status des Raumgeräts an. Statusstatus kann entweder Verbunden **oder** **Getrennt sein.**
- **Integrität** Zeigt detaillierte Informationen zu Den Peripheriegeräten, die an Ihr Teams-Raumgerät angeschlossen sind, Netzwerkverbindung, Anmeldestatus bei erforderlichen Diensten und Informationen zur Softwareversion.
- **Details** Zeigt Herstellerinformationen, Netzwerk-IP-Adresse und Teams Seriennummer/MAC-Adresse des Raumgeräts an.
- **Aktivität** Zeigt vergangene Besprechungsdetails an, einschließlich Datum und Uhrzeit der Besprechung, Anzahl der Teilnehmer, Dauer und Audioqualität. Weitere Informationen zu Besprechungsdetails finden Sie im Abschnitt [Details](#meeting-activity-details) zur Besprechungsaktivität weiter unten in diesem Artikel.
- **Verlauf** Zeigt einen Verlauf der Verwaltungsaktivität auf dem Teams Raumgerät an, einschließlich Konfigurationsupdates, Geräteneustarts und Links zum Herunterladen von Geräteprotokollen.

#### <a name="meeting-activity-details"></a>Details zur Besprechungsaktivität

Auf **der** Registerkarte "Aktivität" in Teams "Raumgerät" werden auf hoher Ebene detaillierte Informationen zu allen Besprechungen angezeigt, an der das Gerät im Laufe der Zeit teilgenommen hat. Auf der **Registerkarte Aktivität** können Sie sehen, wann eine Besprechung abgehalten wurde, wie viele Teilnehmer an der Besprechung teilgenommen haben und wie gut die Audioqualität während der Besprechung war.

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Teams Zusammenfassungsliste der Raumgeräteaktivität":::

Wenn Sie die Detailinformationen zu einer bestimmten Besprechung sehen möchten, wählen Sie Datum und Uhrzeit der Besprechung aus, zu der Sie weitere Informationen wünschen. Wenn eine Besprechung nur zwei Teilnehmer enthält, wird die Seite mit den Teilnehmerdetails angezeigt, andernfalls wird eine Zusammenfassungsseite für Teilnehmer angezeigt.

##### <a name="participant-summary"></a>Teilnehmerzusammenfassung

Auf der Teilnehmerzusammenfassungsseite werden alle Teilnehmer angezeigt, die an der Besprechung teilgenommen haben. Sie können sehen, wann jeder Teilnehmer der Besprechung beigetreten ist, seinen Namen, die Audioqualität und die Funktionen sehen, die während der Sitzung verwendet wurden. Um die Details der Sitzung eines Teilnehmers anzuzeigen, wählen Sie die Startzeit der Sitzung für den Teilnehmer aus.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Teams Konferenzdetails für Raumgeräte":::

##### <a name="participant-details"></a>Teilnehmerdetails

Auf der Seite "Teilnehmerdetails" werden End-to-End-Diagnoseinformationen für die Sitzung dieses Teilnehmers angezeigt. Wie in der folgenden Abbildung gezeigt, **werden Geräte-,** **System-** und **Verbindungsinformationen** für den Teilnehmer und das Teams-Räume bereitgestellt. **Darüber** hinaus werden Netzwerkdiagnoseinformationen zwischen dem Teilnehmer und Teams-Räume Gerät bereitgestellt. Wählen Sie das Symbol für den Kontext aus, zu dem Sie weitere Informationen wünschen. Um weitere Diagnoseinformationen zu erhalten, wählen Sie die **Registerkarte Erweitert** aus.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Teams Anrufdetails für Raumgeräte":::
