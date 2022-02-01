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
description: Hier erfahren Sie, wie Sie fortlaufende Wartungs- und Betriebsvorgänge entwickeln und ausführen, um sicherzustellen, dass Microsoft Teams-Räume-System für Ihre Benutzer verfügbar sind.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 02faaec97837f61befaa5320f7d73b84e33d25c2
ms.sourcegitcommit: d3c48f0c147cf0c47d5eb4ea1128b5bca13be718
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2022
ms.locfileid: "62299000"
---
# <a name="manage-microsoft-teams-rooms"></a>Microsoft Teams-Räume verwalten

Wenn Sie über Microsoft Teams-Räume in Ihrer Organisation verfügen, haben Sie flexible Verwaltungsoptionen.  Sie können die Geräte selbst an demselben zentralen Ort verwalten, an dem Sie alle ihre Teams, Microsoft Teams Admin Center verwalten. Alternativ können Sie Verwaltungsverantwortliche an dedizierte Experten übertragen, die [Microsoft Teams-Räume Dienste verwenden](https://portal.rooms.microsoft.com).  Sie können für eine der Optionen auch den Verwaltungszugriff an einen Partner Ihrer Wahl delegieren.

Mit Microsoft Teams Admin Center können Sie:

- Ausführen der Geräteverwaltung wie Neustarten von Geräten und Herunterladen von Geräteprotokollen
- Anwenden Teams spezifischen Einstellungen
- Überprüfen sie den Integritätsstatus Microsoft Teams-Räume Und ihre Peripheriegeräte, einschließlich Kameras, Anzeigen, Mikrofone und so weiter.
- Überprüfen der aktuellen und vergangenen Besprechungsaktivität (z. B. Details zur Anrufqualität, Netzwerkinte health und Konnektivität und Anzahl der Teilnehmer)
- Peripheriegeräte (z. B. Kameras und Projektoren) sehen, die an Microsoft Teams-Räume

Um Ihre Teams-Räume zu verwalten, öffnen Sie [das Microsoft Teams Admin Center](https://admin.teams.microsoft.com), und wechseln Sie zu Teams **Geräte** >  **Teams-Räume auf Windows**.

:::image type="content" source="../media/teams-rooms-summary2.png" alt-text="Teams-Räume Zusammenfassungsseite im Teams Admin Center anzeigen.":::


> [!IMPORTANT]
> Zum Verwalten von Geräten über Teams Admin Center müssen Ihnen die Rollen "Globaler Administrator", "Teams-Administrator" oder "Teams Geräteadministrator" zugewiesen sein.

## <a name="make-changes-to-teams-rooms-devices"></a>Vornehmen von Änderungen an Teams-Räume-Geräten

Wenn Sie über mehrere Teams-Räume verfügen, können Sie die meisten Aktionen auf mehreren Geräten gleichzeitig ausführen. So können Sie beispielsweise Teams-App-Einstellungen für alle Ihre Teams-Räume gleichzeitig festlegen.

### <a name="device-settings"></a>Geräteeinstellungen

Sie können Einstellungen für einen oder mehrere Teams-Räume in Ihrer Organisation ändern. Um Einstellungen zu ändern, wählen Sie das gerät oder geräte aus, das Sie verwalten möchten, und wählen Sie dann Bearbeiten **Einstellungen**. Ein neuer Bereich mit allen Einstellungen, die Sie ändern können, wird geöffnet. In der folgenden Tabelle sind die Einstellungen aufgeführt, die Sie mithilfe des Teams Admin Centers ändern können. Einige Einstellungen sind nur verfügbar, wenn Sie ein einzelnes Teams-Räume.

Wenn Sie mehrere Optionen auswählen, werden für Einstellungen, die die Massenbearbeitung unterstützen, die beiden folgenden Optionen angezeigt:

- **Vorhandenen Wert behalten** Wenn Sie diese Option auswählen, werden keine Änderungen an der Einstellung auf dem ausgewählten Teams-Räume vorgenommen.
- **Ersetzen eines vorhandenen Werts durch** Wenn Sie diese Option auswählen, können Sie die Einstellung auf dem ausgewählten Teams-Räume mit dem von Ihnen ausgewählten Wert aktualisieren.
    > [!CAUTION]
    > Vorhandene Werte in den Einstellungen, die Sie aktualisieren möchten, werden durch den von Ihnen angegebenen Wert ersetzt. Wenn Sie eine Liste mit vorhandenen Werten hinzufügen möchten, müssen Sie die vorhandenen Werte mit dem Wert, den Sie addieren möchten, hinzufügen. Wenn eine Einstellung beispielsweise `contoso.com, fabrikam.com``northwindtraders.com`über eine vorhandene Domänenliste mit verfügt und Sie hinzufügen möchten, müssten Sie den Wert von bereitstellen`contoso.com, fabrikam.com, northwindtraders.com`.
    >
    > Wenn Sie mehrere Teams-Räume, wird die Einstellung auf allen von Ihnen ausgewählten Geräten in den von Ihnen angezeigten Wert geändert. Wenn Teams-Räume für eine Einstellung unterschiedliche Werte haben, werden diese alle auf denselben Wert aktualisiert.

| Einstellung                                                      | Akzeptierte Werte                                        | Unterstützt die Massenbearbeitung |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *Konto*                                                    |                                                        |                    |
| **E-Mail**                                                    | E-Mail-Adresse                                          | Nein                 |
| **Unterstützter Besprechungsmodus**                                   | nur Microsoft Teams<br>Skype for Business (Standard) und Microsoft Teams<br>Skype for Business und Microsoft Teams (Standard)<br>Nur Skype for Business|Ja|
| **Moderne Authentifizierung**                                    | Ein<br>Aus                                              | Ja                |
| **Exchange adresse**                                         | E-Mail-Adresse                                          | Nein                 |
| **Domäne\Benutzername (optional)**                               | Kontodomäne und Benutzername                           | Nein                 |
| **Domäne konfigurieren**                                         | Durch Kommas getrennte Liste                                   | Ja                |
| *Besprechungen*                                                   |                                                        |                    |
| **Automatische Bildschirmfreigabe**                                 | Ein<br>Aus                                              | Ja                |
| **HDMI-Aufnahmeaudiofreigabe**                                 | Ein<br>Aus                                              | Ja                |
| **Anzeigen von Besprechungsnamen**                                       | Ein<br>Aus                                              | Ja                |
| **Automatisches Verlassen, wenn alle anderen die Besprechung verlassen haben**                 | Ein<br>Aus                                              | Ja                |
| **Teilnehmen an Besprechungen von Drittanbietern**                 | Cisco Webex<br>Zoomen                                              | Ja                |
| **Teilnehmen mit Rauminformationen**                 | Ausgewählt<br>Nicht ausgewählt                                              | Ja                |
| **Teilnehmen mit benutzerdefinierten Informationen**                 | Ausgewählt<br>Nicht ausgewählt                                              | Ja                |
| **Name (erforderlich)**                 | Name des Raums oder Leerzeichens                                              | Ja                |
| **E-Mail (erforderlich)**                 | E-Mail-Adresse                                              | Ja                |
| *Gerät*                                                     |                                                        |                    |
| **Modus mit zwei Monitoren**                                        | Ein<br>Aus                                              | Ja                |
| **Inhaltsduplizierung zulassen** | Ausgewählt<br>Nicht ausgewählt                                 | Ja                |
| **Bluetooth beacing**                                      | Ein<br>Aus                                              | Ja                |
| **Automatisches Annehmen von näherungsbasierten Besprechungseinladungen** | Ausgewählt<br>Nicht ausgewählt                                 | Ja                |
| **Senden von Protokollen mit Feedback**                                  | Ein<br>Aus                                              | Ja                |
| **E-Mail-Adresse für Protokolle und Feedback**                      | E-Mail-Adresse                                          | Ja                |
| *Koordinieren von Besprechungen*                                                     |                                                        |                    |
| **Koordinierte Besprechungen** | Ein<br>Aus                                 | Nein                |
| **Mikrofon dieses Geräts aktivieren** | Ein<br>Aus                                 | Nein                |
| **Personen beim Beitreten zu einer Besprechung aktivieren lassen** | Ausgewählt<br>Nicht ausgewählt                                 | Nein                |
| **Kamera dieses Geräts aktivieren** | Ein<br>Aus                                 | Nein                |
| **Personen beim Beitreten zu einer Besprechung aktivieren lassen** | Ausgewählt<br>Nicht ausgewählt                                 | Nein                |
| **Aktivieren von Whiteboards für dieses Gerät** | Ein<br>Aus                                 | Nein                |
| **Vertrauenswürdige Gerätekonten (durch Kommas getrennt)** | Liste der Geräte                              | Nein                |
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

### <a name="cortana-settings"></a>Cortana-Einstellungen

Sie können die Cortana für die _Sprachaktivierung_ _oder Push aktivieren_, um mithilfe von PowerShell für alle Geräte in Ihrer Organisation oder für jedes Gerät separat zu sprechen.

Weitere [Microsoft Teams-Räume der Windows](../cortana-in-teams.md) im Artikel "Cortana Sprachunterstützung in Teams".

### <a name="front-row-layout-settings"></a>Layouteinstellungen für die Erste Zeile

Die erste Zeile ist die Layoutoption für Besprechungsansichten Teams-Räume Besprechungen Windows.

| Teams Gerät | App-Version | Vor dem Raumanzeige |
|--------------|-------------|-----------------------|
|Microsoft Teams-Räume auf Windows | 4.11.14.0 bis 4.11.12.0 | Unterstützt single- und duale Anzeigen. Mindestgröße: 46 Zoll; Seitenverhältnis 16:9 mit Einer Auflösung von 1920*1080 oder 21:9 mit einer Auflösung von 2560 x 1080; Alle Anzeigen sollten in den Einstellungen Windows 100 % Windows werden |

Weitere [Microsoft Teams-Räume finden](rooms-operations.md#change-scale-and-resolution) Sie unter Wartung und Vorgänge, um die Anzeigeeinstellungen an die Anforderungen der Zeile "Front" anzupassen.

Informationen zum Festlegen der Zeile "Vor" als Standardlayout für einen Raum oder zum Deaktivieren finden Sie unter Remoteverwaltung einer Microsoft Teams-Räume-Konsoleneinstellungen mit einer [XML-Konfigurationsdatei](xml-config-file.md#set-front-row-as-the-default-layout).

Weitere [Informationen zum Verwalten von](known-issues.md#Limits) Front-Row finden Sie unter Bekannte Probleme.

## <a name="device-restart-options"></a>Optionen für den Geräteneustart

Änderungen an den Geräteeinstellungen werden erst wirksam, Teams-Räume neu gestartet wurde. Wenn Sie Änderungen vornehmen, die einen Neustart erforderlich machen, können Sie auswählen, ob Sie sofort neu starten oder einen Neustart planen möchten. Hier sind die verfügbaren Neustartoptionen:

- **Sofortiger Neustart** Wenn Sie diese Option auswählen, werden alle Geräte, an der Sie Änderungen vornehmen, neu gestartet, sobald Sie diese Option auswählen.
- **Geplanter Neustart** Wenn Sie diese Option auswählen, können Sie die Geräte neu starten, an der Sie Änderungen vornehmen, zu einer Zeit, die für Ihre Organisation weniger störend ist.
  - **Datum und Uhrzeit auswählen** : Wählen Sie das Datum und die Uhrzeit für den Neustart des Geräts aus. Datum und Uhrzeit des neu gestarteten Geräts sind lokal. 
  - **Update für nächtlichen Neustart verlassen** Geräte werden für Wartungen nachts neu gestartet. Änderungen, die Sie an Geräten vornehmen, werden während dieses Neustarts angewendet.

> [!CAUTION]
> Teams-Räume, die zum Zeitpunkt eines Neustarts verwendet werden, sind für die Dauer des Neustartvorgangs nicht mehr verfügbar. Sie werden von ihren in Bearbeitungen ausgeführten Besprechungen getrennt und stehen nicht zur Verfügung, um an neuen Besprechungen teilzunehmen.

## <a name="remove-device"></a>Gerät entfernen

Wenn Sie ein Gerät entfernen, wird das Gerät aus Ihrer Organisation entfernt und nicht mehr in Ihrer Liste der Teams-Räume auf Windows im Teams Admin Center angezeigt.

Wenn Sie ein Gerät entfernen und es weiterhin mit einem gültigen Benutzernamen und Kennwort konfiguriert ist, wird es automatisch erneut zu Ihrer Teams-Räume-Liste hinzugefügt, wenn es erneut eine Verbindung mit Microsoft 365 herstellt.

Gehen Sie wie folgt vor, um ein oder mehrere Geräte zu entfernen:

1. Wechseln Sie **Teams Geräte** >  **Teams-Räume auf Windows**, und wählen Sie die Geräte aus, die Sie entfernen möchten.
2. Wählen Sie **Entfernen** aus.

## <a name="download-device-logs"></a>Herunterladen von Geräteprotokollen

Sie können eine Kopie der Diagnoseprotokolldateien eines Geräts herunterladen, wenn Sie vom Microsoft-Support dazu aufgefordert werden. Protokolldateien werden in eine ZIP-Datei komprimiert, die aus dem Teams Admin Center heruntergeladen werden kann.

Gehen Sie wie folgt vor, Teams-Räume Protokolle von einem anderen Gerät auf Ihren Computer herunterzuladen:

1. Wechseln Sie **Teams auf Teams-Räume** >  Gerät **zu** Windows und wählen Sie den Namen des Geräts aus, von dem Sie Protokolle herunterladen möchten.
1. Wählen Sie **Geräteprotokolle herunterladen aus**. Es kann einige Minuten dauern, bis Geräteprotokolle verfügbar sind.
1. Wählen Sie die **Registerkarte** Verlauf und dann unter Diagnosedatei den Link **Protokolldatei aus**. Eine ZIP-Datei, die die Diagnoseprotokolldateien Ihres Geräts enthält, wird in den Standardordner "Downloads" Ihres Browsers heruntergeladen.

## <a name="view-device-information"></a>Anzeigen von Geräteinformationen

Im Teams Admin Center können Sie den Gesamtstatus aller Geräte in Ihrer Organisation und Details zu jedem Gerät einzeln anzeigen.

### <a name="teams-rooms-system-dashboard"></a>Teams-Räume Systemdashboard

Im Teams-Räume Systemdashboard können Sie den Status und Status aller Ihrer Geräte auf einen Blick sehen.

### <a name="device-details-view"></a>Ansicht "Gerätedetails"

Wenn Sie detaillierte Informationen zu einem Gerät anzeigen möchten, wählen Sie dessen Namen aus der Geräteliste aus. In der Detailansicht werden die folgenden Informationen zu Ihrem Gerät angezeigt:

- **Integritätsstatus** Zeigt den Gesamtzustand des Teams Raumgeräts an. Der Status kann entweder fehlerfrei **oder** **fehlerhaft sein**.
- **Offline seit** Zeigt an, wie Microsoft 365 zuletzt mit dem Gerät kommunizieren konnte.
- **Gerätestatus** Zeigt den aktuellen Status des Geräts an: **Idle** (Leerlauf), **Teams Besprechung**, **Skype Besprechung oder** **Ingest (Ingest**).
- **Peripheriegeräte** Zeigt die an Ihr Gerät Teams angeschlossenen Peripheriegeräte und deren Integritätsstatus an. Statusstatus kann entweder Verbunden **oder** Getrennt **sein**.
- **Integrität** Zeigt detaillierte Informationen zu Den Peripheriegeräten, die an Ihr Teams-Raumgerät angeschlossen sind, Netzwerkverbindung, Anmeldestatus bei erforderlichen Diensten und Informationen zur Softwareversion.
- **Details** Zeigt Herstellerinformationen, Netzwerk-IP-Adresse und Teams Seriennummer/MAC-Adresse des Raumgeräts an.
- **Aktivität** Zeigt vergangene Besprechungsdetails an, einschließlich Datum und Uhrzeit der Besprechung, Anzahl der Teilnehmer, Dauer und Audioqualität. Weitere Informationen zu Besprechungsdetails finden Sie im Abschnitt [Details](#meeting-activity-details) zur Besprechungsaktivität weiter unten in diesem Artikel.
- **Verlauf** Zeigt einen Verlauf der Verwaltungsaktivität auf dem Teams Raumgerät an, einschließlich Konfigurationsupdates, Geräteneustarts und Links zum Herunterladen von Geräteprotokollen.

#### <a name="meeting-activity-details"></a>Details zur Besprechungsaktivität

Auf **der** Registerkarte Aktivität in Teams Des Raumgeräts werden auf hoher Ebene detaillierte Informationen zu allen Besprechungen angezeigt, an der das Gerät im Laufe der Zeit teilgenommen hat. Auf der **Registerkarte Aktivität** können Sie sehen, wann eine Besprechung abgehalten wurde, wie viele Teilnehmer an der Besprechung teilgenommen haben und wie gut die Audioqualität während der Besprechung war.

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Teams Zusammenfassung der Aktivitäten des Raumgeräts.":::

Wenn Sie die Detailinformationen zu einer bestimmten Besprechung sehen möchten, wählen Sie Datum und Uhrzeit der Besprechung aus, zu der Sie weitere Informationen wünschen. Wenn eine Besprechung nur zwei Teilnehmer enthält, wird die Seite mit den Teilnehmerdetails angezeigt, andernfalls wird eine Zusammenfassungsseite für Teilnehmer angezeigt.

##### <a name="participant-summary"></a>Teilnehmerzusammenfassung

Auf der Teilnehmerzusammenfassungsseite werden alle Teilnehmer angezeigt, die an der Besprechung teilgenommen haben. Sie können sehen, wann jeder Teilnehmer der Besprechung beigetreten ist, seinen Namen, die Audioqualität und die Funktionen sehen, die während der Sitzung verwendet wurden. Um die Details der Sitzung eines Teilnehmers anzuzeigen, wählen Sie die Startzeit der Sitzung für den Teilnehmer aus.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Teams Konferenzdetails für Raumgeräte an.":::

##### <a name="participant-details"></a>Teilnehmerdetails

Auf der Seite "Teilnehmerdetails" werden End-to-End-Diagnoseinformationen für die Sitzung dieses Teilnehmers angezeigt. Wie in der folgenden Abbildung gezeigt, werden **Geräte**-, **System**- und **Verbindungsinformationen** für den Teilnehmer und das Teams-Räume bereitgestellt. **Darüber** hinaus werden Netzwerkdiagnoseinformationen zwischen dem Teilnehmer und Teams-Räume Gerät bereitgestellt. Wählen Sie das Symbol für den Kontext aus, zu dem Sie weitere Informationen wünschen. Um weitere Diagnoseinformationen zu erhalten, wählen Sie die **Registerkarte Erweitert** aus.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Teams Sie Anrufdetails für Raumgeräte.":::
