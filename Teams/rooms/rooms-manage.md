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
description: Hier erfahren Sie, wie Sie laufende Wartungen und Vorgänge entwickeln und ausführen, um sicherzustellen, dass Ihre Microsoft Teams rooms-Systeme für Ihre Benutzer verfügbar sind.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2339967d6d7705266c13dbc65fb689c49c8e8279
ms.sourcegitcommit: a5276a713697e089d0eb0d80bba83a7af8d48251
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "45202921"
---
# <a name="manage-microsoft-teams-rooms"></a>Microsoft Teams-Räume verwalten

Wenn Sie über Microsoft Teams rooms zertifizierte Geräte in Ihrer Organisation verfügen, können Sie diese über das Microsoft Teams Admin Center von einem zentralen Ort aus verwalten. Sie haben folgende Möglichkeiten:

- Durchführen der Geräteverwaltung wie dem Neustart oder Blockieren von Geräten und dem Herunterladen von Geräte Protokollen
- Anwenden von Teams-spezifischen Einstellungen
- Überprüfen Sie den Integritätsstatus von Microsoft Teams Room-Geräten und deren Peripheriegeräten, einschließlich Kameras, Displays, Mikrofone usw.
- Überprüfen der aktuellen und vergangenen Besprechungs Aktivitäten (beispielsweise Details zur Anrufqualität, Netzwerkintegrität und-Konnektivität sowie die Anzahl der Teilnehmer)
- Anzeigen von Peripheriegeräten (wie Kameras und Projektoren), die mit einem Microsoft Teams Room-Gerät verbunden sind

Zum Verwalten von Teams rooms-Geräten öffnen Sie das [Microsoft Teams Admin Center](https://admin.teams.microsoft.com) , und wechseln Sie zu **Devices**  >  **Teams rooms**.

:::image type="content" source="../media/teams-rooms-summary.png" alt-text="TeamRoom-Zusammenfassungsseiten im Team Admin Center":::

> [!IMPORTANT]
> Zum Verwalten von Geräten mit dem Team Admin Center müssen Sie die rollenteam Dienst Administrator oder globaler Administrator zugewiesen haben.

## <a name="make-changes-to-teams-rooms-devices"></a>Vornehmen von Änderungen an Teams rooms-Geräten

Wenn Sie über mehr als ein Team Room-Gerät verfügen, können Sie die meisten Aktionen auf mehreren Geräten gleichzeitig ausführen. So können Sie beispielsweise die Einstellungen für die Team-App auf allen Geräten gleichzeitig festlegen.

### <a name="device-settings"></a>Geräteeinstellungen

Sie können die Einstellungen auf einem oder mehreren Geräten in Ihrer Organisation ändern. Um die Einstellungen zu ändern, wählen Sie das Gerät oder die Geräte aus, das Sie verwalten möchten, und wählen Sie dann **Einstellungen bearbeiten**aus. Ein neuer Bereich mit allen Einstellungen, die Sie auf Ihren Geräten ändern können, wird geöffnet. In der folgenden Tabelle sind die Einstellungen aufgeführt, die Sie mit dem Team Admin Center ändern können. Einige Einstellungen stehen nur zur Verfügung, wenn Sie ein einzelnes Gerät auswählen.

Wenn Sie mehr als ein Gerät auswählen, werden in den Einstellungen, die die Massenbearbeitung unterstützen, die beiden folgenden Optionen angezeigt.

- **Vorhandenen Wert beibehalten** Wenn Sie diese Option auswählen, werden keine Änderungen an der Einstellung auf den ausgewählten Geräten vorgenommen.
- **Vorhandenen Wert ersetzen durch** Wenn Sie diese Option auswählen, können Sie die Einstellung auf den ausgewählten Geräten mit dem von Ihnen angegebenen Wert aktualisieren.
    > [!CAUTION]
    > Vorhandene Werte für die Einstellungen, die Sie aktualisieren möchten, werden durch den von Ihnen bereitgestellten Wert ersetzt. Wenn Sie eine Liste vorhandener Werte hinzufügen möchten, müssen Sie die vorhandenen Werte mit dem Wert einbeziehen, den Sie hinzufügen möchten. Wenn beispielsweise eine Einstellung eine Domänenliste von enthält `contoso.com, fabrikam.com` , die Sie hinzufügen möchten, lautet `northwindtraders.com` der Wert, den Sie angeben müssen `contoso.com, fabrikam.com, northwindtraders.com` .
    >
    > Wenn Sie mehrere Geräte auswählen, wird die Einstellung auf allen ausgewählten Geräten in den von Ihnen bereitgestellten Wert geändert. Wenn Geräte unterschiedliche Werte für eine Einstellung aufweisen, werden Sie alle auf denselben Wert aktualisiert.

| Einstellung                                                      | Akzeptierte Werte                                        | Unterstützt die Massenbearbeitung |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *Konto*                                                    |                                                        |                    |
| **E-Mail**                                                    | E-Mail-Adresse                                          | Nein                 |
| **Unterstützter Besprechungs Modus**                                   | Skype for Business (Standard) und Microsoft Teams<br>Skype for Business und Microsoft Teams (Standard)<br>Nur Skype for Business|Ja|
| **Moderne Authentifizierung**                                    | Ein<br>Aus                                              | Ja                |
| **Exchange-Adresse**                                         | E-Mail-Adresse                                          | Nein                 |
| **Domäne \ Benutzername (optional)**                               | Kontodomäne und Benutzername                           | Nein                 |
| **Domäne konfigurieren**                                         | Durch trennzeichengetrennte Liste                                   | Ja                |
| *Besprechungen*                                                   |                                                        |                    |
| **Automatische Bildschirmfreigabe**                                 | Ein<br>Aus                                              | Ja                |
| **Anzeigen von Besprechungs Namen**                                       | Ein<br>Aus                                              | Ja                |
| **Automatisches verlassen, wenn alle anderen Personen die Besprechung verlassen haben**                 | Ein<br>Aus                                              | Ja                |
| *Gerät*                                                     |                                                        |                    |
| **Dual-Monitor-Modus**                                        | Ein<br>Aus                                              | Ja                |
| **Bluetooth-Beaconing**                                      | Ein<br>Aus                                              | Ja                |
| **Automatisches Annehmen von Proximity-basierten Besprechungseinladungen** | Ausgewählt<br>Deaktiviert                                 | Ja                |
| **Senden von Protokollen mit Feedback**                                  | Ein<br>Aus                                              | Ja                |
| **E-Mail-Adresse für Protokolle und Feedback**                      | E-Mail-Adresse                                          | Ja                |
| *Peripherie*                                                |                                                        |                    |
| **Konferenz Mikrofon**                                  | Liste der verfügbaren Mikrofone                          | Nein                 |
| **Konferenz Lautsprecher**                                     | Liste der verfügbaren Lautsprecher                             | Nein                 |
| **Standardlautstärke**                                           | 0-100                                                  | Nein                 |
| **Standardlautsprecher**                                          | Liste der verfügbaren Lautsprecher                             | Nein                 |
| **Standardlautstärke**                                           | 0-100                                                  | Nein                 |
| **Inhalts Kamera**                                           | Liste der verfügbaren Kameras                              | Nein                 |
| **Verbesserungen der Inhalts Kamera**                              | Ein<br>Aus                                              | Nein                 |
| **Drehen der Inhalts Kamera 180 Grad**                        | Ein<br>Aus                                              | Nein                 |
| *Design*                                                    |                                                        |                    |
|                                                              | Standard<br>Kein Design<br>Benutzerdefinierten<br>Liste der integrierten Designs   | Ja                |

### <a name="device-restart-options"></a>Optionen für den Geräteneustart

Änderungen an den Geräteeinstellungen werden erst wirksam, nachdem die Geräte neu gestartet wurden. Wenn Sie Änderungen vornehmen, für die ein Neustart erforderlich ist, können Sie auswählen, ob Sie die Geräte sofort neu starten oder einen Neustart planen möchten. Hier sind die verfügbaren Neustartoptionen:

- **Sofortiger Neustart** Wenn Sie diese Option auswählen, werden alle Geräte, an denen Sie Änderungen vornehmen, neu gestartet, sobald Sie diese Option ausgewählt haben.
- **Geplanter Neustart** Wenn Sie diese Option auswählen, können Sie die Geräte, an denen Sie Änderungen vornehmen, zu einem Zeitpunkt neu starten, der für Ihre Organisation nicht mehr störend ist.
  - **Wählen Sie Datum und Uhrzeit aus** , und wählen Sie das Datum und die Uhrzeit für den Neustart des Geräts aus. Das Datum und die Uhrzeit, die Sie auswählen, sind lokal für das Gerät, das neu gestartet wird. 
  - **Update für nächtlichen Neustart beenden** Geräte werden nächtlich neu gestartet, um Wartungsarbeiten durchzuführen. Änderungen, die Sie an Geräten vornehmen, werden während des Neustarts übernommen.

> [!CAUTION]
> Geräte, die zum Zeitpunkt des Neustarts verwendet werden, werden für die Dauer des Neustartvorgangs nicht mehr zur Verfügung stehen. Sie werden von in-Progress-Besprechungen getrennt und stehen nicht für die Teilnahme an neuen Besprechungen zur Verfügung.

### <a name="remove-or-block-a-device"></a>Entfernen oder Blockieren eines Geräts

Wenn Sie ein Gerät **Entfernen** , wird das Gerät aus Ihrer Organisation entfernt, und es wird nicht mehr in der Liste der Teams rooms-Geräte im Team Admin Center angezeigt. 

Wenn Sie ein Gerät **blockieren** , kommuniziert Teams nicht mehr mit dem Gerät. Blockierten Geräten werden keine Befehle gesendet, auch wenn Sie in einer Gruppe von Geräten enthalten sind, die Massen bearbeitet werden. Sie ist immer noch in der Liste der Teams für Teams mit dem Status " **blockiert**" aufgeführt.

Unabhängig davon, ob ein Gerät blockiert oder entfernt wird, wenn es immer noch mit einem gültigen Benutzernamen und Kennwort konfiguriert ist, wird es automatisch wieder in die Liste Ihrer Teams rooms-Geräte aufgenommen, wenn es eine Verbindung mit Microsoft 365 herstellt.

Gehen Sie wie folgt vor, um ein oder mehrere Geräte zu entfernen:

1. Wechseln Sie zu **Devices**  >  **Teams rooms** , und wählen Sie die Geräte aus, die Sie entfernen möchten.
1. Wählen Sie **Entfernen** aus.

Gehen Sie wie folgt vor, um ein Gerät zu blockieren:

1. Wechseln Sie zu **Devices**  >  **Teams rooms** , und wählen Sie den Namen des Geräts aus, das Sie blockieren möchten.
1. Wählen Sie auf der Seite Gerätedetails in der oberen rechten Ecke der Seite **Aktionen** aus.
1. Wählen Sie **blockieren**aus.

Gehen Sie wie folgt vor, um die Blockierung eines Geräts aufzuheben:

1. Wechseln Sie zu **Devices**  >  **Teams rooms** , und wählen Sie den Namen des Geräts aus, das Sie blockieren möchten.
1. Wählen Sie auf der Seite Gerätedetails in der oberen rechten Ecke der Seite **Aktionen** aus.
1. Wählen Sie **Freigeben**aus.

## <a name="download-device-logs"></a>Herunterladen von Geräte Protokollen

Wenn Sie vom Microsoft-Support dazu aufgefordert werden, können Sie eine Kopie der Diagnoseprotokolldateien eines Geräts herunterladen. Protokolldateien werden in eine ZIP-Datei komprimiert, die aus dem Team Admin Center heruntergeladen werden kann.

Gehen Sie wie folgt vor, um Protokolle von einem Team Room-Gerät auf Ihren Computer herunterzuladen:

1. Wechseln Sie zu **Devices**  >  **Teams rooms** , und wählen Sie den Namen des Geräts aus, von dem Sie die Protokolle herunterladen möchten.
1. Wählen Sie **Geräteprotokolle herunterladen**aus. Es kann mehrere Minuten dauern, bis Geräteprotokolle verfügbar werden.
1. Wählen Sie die Registerkarte **Verlauf** aus, und wählen Sie dann unter **Diagnosedatei**den Link Protokolldatei aus. Eine ZIP-Datei mit den Diagnoseprotokolldateien Ihres Geräts wird in den standardmäßigen Downloadordner Ihres Browsers heruntergeladen.

## <a name="view-device-information"></a>Anzeigen von Geräteinformationen

Im Team Admin Center können Sie den Gesamtstatus aller Geräte in Ihrer Organisation anzeigen und die Details der einzelnen Geräte einzeln anzeigen.

### <a name="teams-rooms-system-dashboard"></a>Teams rooms-systemdashboard

Das systemdashboard "Teams Rooms" zeigt Ihnen den Status und die Integrität aller Ihrer Geräte auf einen Blick.

### <a name="device-details-view"></a>Geräte Detailansicht

Wenn Sie detaillierte Informationen zu einem Gerät anzeigen möchten, wählen Sie seinen Namen in der Geräteliste aus. In der Detailansicht werden die folgenden Informationen zu Ihrem Gerät angezeigt:

- **Integritätsstatus** Zeigt den Gesamtzustand des Geräts "Teams Room" an. Der Integritätsstatus kann entweder **gesund** oder **unschädlich**sein.
- **Offline seit** Zeigt das letzte Mal an, dass Microsoft 365 mit dem Gerät kommunizieren konnte.
- **Gerätestatus** Zeigt den aktuellen Zustand des Geräts an: **Idle**, **Teams-Besprechung**, **Skype-Besprechung**oder **Ingest**.
- **Peripheriegeräte** Zeigt die Peripheriegeräte an, die mit Ihrem TeamRoom-Gerät verbunden sind, und deren Zustand. Der Integritätsstatus kann entweder **verbunden** oder **getrennt**werden.
- **Gesundheit** Zeigt detaillierte Informationen zu den Peripheriegeräten, die mit Ihrem TeamRoom-Gerät, der Netzwerkkonnektivität, dem Anmeldestatus für erforderliche Dienste und Softwareversionsinformationen verbunden sind.
- **Weitere Informationen** Zeigt die Herstellerinformationen, die Netzwerk-IP-Adresse und die serielle/Mac-Adresse des Teams Room Device an.
- **Aktivitäten** Zeigt vergangene Besprechungsdetails an, einschließlich Datum und Uhrzeit der Besprechung, Anzahl der Teilnehmer, Dauer und Audioqualität. Weitere Informationen zu Besprechungsdetails finden Sie weiter unten in diesem Artikel im Abschnitt [Besprechungs Aktivitätsdetails](#meeting-activity-details) .
- **Verlauf** Zeigt einen Verlauf der Verwaltungsaktivitäten auf dem TeamRoom-Gerät an, einschließlich Konfigurationsupdates, Geräteneustarts und Download Links für Geräteprotokolle.

#### <a name="meeting-activity-details"></a>Details zu Besprechungs Aktivitäten

Auf der Registerkarte " **Aktivität** " in "Teams Room Device Details" werden allgemeine und detaillierte Informationen zu allen Besprechungen angezeigt, an denen das Gerät im Laufe der Zeit teilgenommen hat. Auf der Registerkarte **Aktivität** können Sie sehen, wann eine Besprechung abgehalten wurde, wie viele Teilnehmer an der Besprechung teilgenommen haben, und die Audioqualität während der Besprechung.

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Übersicht über die Liste der Teamarbeits Raum Geräte Aktivitäten":::

Wenn Sie die Detailinformationen zu einer bestimmten Besprechung anzeigen möchten, wählen Sie das Datum und die Uhrzeit der Besprechung aus, über die Sie weitere Informationen wünschen. Wenn eine Besprechung nur zwei Teilnehmer enthält, wird die Seite Teilnehmerdetails angezeigt, andernfalls wird eine Seite mit den Teilnehmern angezeigt.

##### <a name="participant-summary"></a>Teilnehmer Zusammenfassung

Auf der Seite "Teilnehmer Zusammenfassung" werden alle Teilnehmer angezeigt, die an der Besprechung teilgenommen haben. Sie können sehen, wann jeder Teilnehmer der Besprechung beigetreten ist, den Namen, die Audioqualität und die Features, die während der Sitzung verwendet wurden. Wenn Sie die Details der Sitzung eines Teilnehmers anzeigen möchten, wählen Sie die Startzeit der Sitzung für diesen Teilnehmer aus.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Konferenzdetails für Teams für raumgeräte":::

##### <a name="participant-details"></a>Teilnehmerdetails

Auf der Seite Teilnehmer-Details werden die End-to-End-Diagnoseinformationen für die Sitzung des Teilnehmers angezeigt. Wie in der folgenden Abbildung dargestellt, werden **Geräte**-, **System**-und **Verbindungs** Informationen für den Teilnehmer und für das Gerät "Teams Rooms" bereitgestellt. Außerdem werden **Netzwerk** Diagnoseinformationen zwischen dem Teilnehmer und dem Team Room-Gerät bereitgestellt. Wählen Sie das Symbol für den Kontext aus, zu dem Sie weitere Informationen wünschen. Wenn Sie weitere Diagnoseinformationen erhalten möchten, wählen Sie die Registerkarte **erweitert** aus.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Geräte Anrufdetails für Teams":::
