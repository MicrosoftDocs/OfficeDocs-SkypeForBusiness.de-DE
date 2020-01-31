---
title: Aktivieren und Verwenden des Dashboards für die Anrufqualität
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
ms.custom:
- Reporting
description: 'Hier erfahren Sie, wie Sie das Dashboard für die Anrufqualität aktivieren und verwenden und zusammenfassende Berichte über die Qualität von Anrufen erhalten. '
ms.openlocfilehash: e29bced13fd4bad900c349efc07219e4edebc9d3
ms.sourcegitcommit: 013190ad10cdc02ce02e583961f433d024d5d370
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/31/2020
ms.locfileid: "41636842"
---
# <a name="turn-on-and-use-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Aktivieren und Verwenden des Dashboards für die Anrufqualität für Microsoft Teams und Skype for Business Online

Hier erfahren Sie, wie Sie Ihre Office 365-Organisation konfigurieren können, um das Anrufqualitäts-Dashboard zur Überwachung der Anrufqualität zu verwenden.
  
Das Anruf Qualitäts Dashboard (CQD) bietet Einblicke in die Qualität von anrufen, die mit Microsoft Teams und Skype for Business Online-Diensten getätigt wurden. In diesem Thema werden die Schritte beschrieben, mit denen Sie Daten sammeln können, um Probleme mit der Anrufqualität zu beheben.

Derzeit stehen erweiterte CQD und CQD zur Verfügung. Advanced CQD ist verfügbar unter <span>https://cqd.teams.microsoft.com</span>. Neue URL, aber dieselbe Anmeldung mit Ihren Administratoranmeldeinformationen.

## <a name="latest-changes-and-updates"></a>Aktuelle Änderungen und Updates


Das aktualisierte CQD (ab Anfang November 2019) bietet ein nahezu Echt Zeit CQD-Dashboard. CQD-Daten sind jetzt im Durchschnitt in 30 Minuten verfügbar (im Vergleich zum vorherigen CQD, der durchschnittlich 24 Stunden beträgt).  Der aktualisierte CQD verwendet Endbenutzer identifizierbare Informationen (EUII), sodass Administratoren die Möglichkeit haben, einen Drilldown durchführen und die Benutzerebene zu vergrößern. Darüber hinaus gibt es Berichts Interaktivität zur Unterstützung neuer Szenarien wie:


- Anrufqualität nach Regionen:
  - Datum-für-Region
  - aggregiert nach Stunden pro Region
  - bestimmte Speicherorte
  - bestimmtes Subnetz
  - betroffene Benutzer oder Benutzer

- Anruf Zuverlässigkeit/-Fehler nach Region:
  - Datum-für-Region
  - aggregiert nach Stunden pro Region
  - bestimmte Speicherorte
  - bestimmtes Subnetz
  - betroffene Benutzer oder Benutzer

- Meinen Anruf (RMA) nach Regionen bewerten: von Monat zu Region, aufgeschlüsselt nach Regionen, bis zu bestimmten Orten für Benutzer, die eine geringe Anzahl von Bewertungen anbieten. CQD V3 enthält auch Verbatim-Feedback.
- Helpdesk: steht für einen bestimmten Benutzer für P2P-Anrufe oder Besprechungen oder für alle Teilnehmer und Anrufdetails zur Verfügung. Hilft bei der Ermittlung möglicher System Probleme basierend auf Netzwerkstandort, Geräten oder Firmware.  
- Clientversionen: zeigen Sie die Sitzungs-und Benutzeranzahl für jede Client Version an, oder führen Sie einen Drilldown zu Benutzernamen für jede Client Version durch. Vordefinierte Filter für Produkt-und Client Typen helfen bei der Fokussierung der Versionen auf bestimmte Clients.
- Endpunkte: zeigt Computer Endpunkte an, die dem Hersteller/Modell des PC/Mac zugeordnet sind. Zeigt die aggregierte Qualität nach Marke/Modell. Zuordnungsdaten werden ähnlich wie Gebäudedaten hochgeladen.

Advanced CQD (v3) bietet auch RBAC-Unterstützung, falls der EUII-Zugriff nicht verfügbar ist.  

Ein Administrator kann Skype for Business Server 2019 (nicht nur Skype for Business Online und Microsoft Teams) über CQD Version 3 verwalten. Dies erfordert eine Hybrid Implementierung und die Verwendung des Anrufdaten-Konnektors. Weitere Informationen finden Sie unter [Planen von Anrufdaten-Konnektoren](/SkypeForBusiness/hybrid/plan-call-data-connector) .

CQD Version 2 hinzugefügt:

- Daten für Microsoft Teams und Skype for Business Online
- Zusammenfassungsberichte enthalten einen Produktfilter, um alle Daten, Microsoft Teams-Daten oder Skype for Business Online-Daten auszuwählen.
- Aktualisierte Video-und schlechte VBSS-Datenstrom Qualitäts Klassifikations Logik. Informationen zu klassifizierungsdefinitionen finden Sie unter [Stream-Klassifikation im Anruf Qualitäts Dashboard](stream-classification-in-call-quality-dashboard.md) .

In diesem Artikel finden Sie eine Liste der [Dimensionen und Measures, die im Dashboard für die Anrufqualität zur Verfügung stehen](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
> [!NOTE]
> Wenn Sie Informationen zu Updates und Änderungen am Dashboard anzeigen möchten, klicken Sie auf den Link in den **guten Nachrichten!** Banner, wenn es im Dashboard angezeigt wird.

CQD Version 1 hat den Skype for Business Server 2015-Administratoren die folgenden Features bereitgestellt:

- Zugriff auf zwischengespeicherte Berichtsdaten für den schnellen Zugriff
- Tiefe Links zu Berichtsseiten für Freigabe-und Veröffentlichungsinformationen
- Optimierte Berichts Bearbeitung und-Erstellung sowie bearbeitbare Metadaten für Bericht Beschreibungen
- Web-APIs, die programmgesteuerten Zugriff auf die Cubedaten zur Verwendung in benutzerdefinierten Dashboards gewähren

## <a name="cqd-near-real-time-nrt-data"></a>CQD (NRT)-Daten (Near-Real-Time)

Advanced CQD (v3, veröffentlicht am 2019) verwendet einen Near-Real-Time-Datenfeed. Anrufdatensätze sind im CQD-Portal innerhalb von 30 Minuten nach dem Ende des Anrufs verfügbar. Anrufdatensätze aus der NRT-Pipeline stehen nur einige Monate zur Verfügung, bevor Sie aus dem Datensatz entfernt werden. CQD V3 führt Daten aus der aktuellen v2-Pipeline mit NRT-Daten aus der V3-Pipeline zusammen. Abfragen auf den V2-und V3-Portalen für die Daten aus dem Archivierungszeitraum liefern dieselben Ergebnisse. V2-und V3-Daten Abfragen für die NRT-Daten und NRT-Daten + PII-Perioden unterscheiden sich.

### <a name="piieuii-data"></a>PII/EUII-Daten

PII-oder EUII-Daten stammen nur aus der V3-Pipeline. Aus Kompatibilitätsgründen werden PII/EUII-Daten nur 30 Tage lang aufbewahrt. Wenn NRT-Daten die 30-Tage-Marke überschreiten, werden die Felder für PII/EUII deaktiviert, was zu PII-freien NRT-Daten führt. Die Felder PII/EUII sind:

- Vollständige IP-Adresse
- Mac-Adresse (Media Access Control)
- Grundlegende Dienst Satz-ID (BSSID)
- SIP-URI (Session Initiation Protocol) (nur Skype for Business)
- Benutzerprinzipalname (User Principal Name, UPN)
- Name des Computer Endpunkts
- Benutzer-Verbatim-Feedback
- Objekt-ID (die Active Directory-Objekt-ID des Benutzers des Endpunkts)

### <a name="date-controls"></a>Datumssteuerelemente

CQD V3 fügt die folgenden neuen Rolling Trend-Typen hinzu:

- 5 Tage
- 7 Tage
- 30 Tage
- 60-Tag
- 90-Tag

Der URL-Datumsparameter kann nun ein Tages Feld akzeptieren. Rolling-Day-Berichte verwenden Datumsangaben, die im Format yyyy-mm-tt als letzten Tag des Trends angegeben wurden.  Der URL-Datumsparameter "00" gibt "heute" an.

|URL| Enddatum des Wälz enden Tagestrends|
|:---|:---|
|<span>https://<cqdv3>/SPD/#/Dashboard/<reportid>/2019-02/</span>   |Aktueller Tag von Feb 2019|
|<span>https://<cqdv3>/SPD/#/Dashboard/<reportid>/2019-02-15/</span>|15 Feb 2019|
|<span>https://<cqdv3>/SPD/#/Dashboard/<reportid>/00/</span>        |Aktueller Tag|
|||

Standardmäßig wird der aktuelle Tag des Monats als letzter Tag des Rolling Day-Trends verwendet.

### <a name="drill-thru-functionality"></a>Drill-Through-Funktionalität

CQD v3 unterstützt die Verwendung von Drill-Through-oder Drilldown-Feldern in SPD-Berichten. Wenn diese Dimensionsfelder markiert sind, wird im Bericht automatisch eine andere Registerkarte "Bericht" geöffnet und der ausgewählte Wert gefiltert. Felder mit einem zugewiesenen Drill-Through-Filter werden durch ein anderes Cursor Symbol (den Mauszeiger) unterschieden, wenn Sie darauf zeigen.

Wenn ein Drillthrough-Feld ausgewählt ist, navigiert das Dashboard automatisch zur neuen, angegebenen Registerkarte und wendet einen Filter mit dem ausgewählten Wert an. Wenn die Registerkarte über eigene Drill-Through-Felder verfügt und eine markiert ist, werden die vorherigen Drillthrough-Filter und die neue durchlaufen alle weitergeleitet. So können Sie einen Bericht erstellen, der die resultierende Datenmenge schrittweise verengt.

In einem Drill-Through-Bericht zur Anrufqualität kann ein Benutzer beispielsweise auf das Datum klicken, an dem er "durchbohren" möchte, was zur Registerkarte "Standort" führt.

![Screenshot: zeigt den Drill-Thru-Bericht](media/CQD-drill-thru-report.png)

Sie können mehrere Datumsangaben auf der Registerkarte Standort hinzufügen, beispielsweise das Hinzufügen von 2019-09-22 zu Datum: 2019-09-24: 

![Screenshot: Hinzufügen eines Datums zum Drill-Thru-Bericht](media/CQD-add-date.png)

> [!NOTE]
> Springen Sie nicht direkt zur letzten Registerkarte. Ohne Filter, die aus einem vorherigen Drilldown ausgewählt wurden, sind die Ergebnisse zu groß, um Sie in einer Tabelle anzuzeigen.

## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a>Aktivieren von Zusammenfassungsberichten des Microsoft-Anrufqualitäts-Dashboards (AQD)

Bevor Sie mit der Verwendung von CQD beginnen können, aktivieren Sie es für Ihre Office 365-Organisation wie folgt:

![Ein Symbol, das das Microsoft Teams-](media/teams-logo-30x30.png) Logo **mit dem Microsoft Teams Admin Center** zeigt

1. Registrieren Sie sich bei Ihrer Office 365-Organisation mit dem Microsoft Teams-Dienstadministratorkonto, und wählen Sie dann die Kachel **Administrator** aus, um das Admin Center zu öffnen.
2. Wählen Sie im linken Bereich unter **Admin Center**die Option **Microsoft Teams** aus, um das Microsoft Teams Admin Center zu öffnen.
3. Wählen Sie im Microsoft Teams Admin Center im linken Bereich **Anruf qualitätsdashboard** aus.
4. Klicken Sie auf der Seite \(,<span>auf<span/>\)der https://CQD.Teams.Microsoft.com geöffnet wird, auf **Anmelden** , und geben Sie Ihr globales Administrator Konto oder Microsoft Teams-Dienstadministratorkonto Informationen ein.

    ![Screenshot: zeigt die Eingabeaufforderung für Anmeldeinformationen an.](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
Nachdem Sie sich angemeldet haben, wird die CQD nach der Aktivierung mit dem sammeln und Verarbeiten von Daten beginnen.  
> [!NOTE]
> Es kann eine oder mehrere Stunden dauern, bis genügend Daten verarbeitet werden, um aussagekräftige Ergebnisse in den Berichten anzuzeigen.

![Symbol des Skype for Business-Logos](media/sfb-logo-30x30.png) **unter Verwendung des Legacy-Portals von Skype for Business**

1. Melden Sie sich mit einem Administratorkonto bei Ihrer Office 365-Organisation an, und wählen Sie dann die Kachel **Admin** aus, um das Admin Center zu öffnen.
2. Wählen Sie im linken Bereich unter **Admin Center**die Option **Microsoft Teams** aus, um das Microsoft Teams Admin Center zu öffnen.
3. Wählen Sie im Microsoft Teams Admin Center im linken Bereich **Legacy Portal** aus, wählen Sie **Tools**aus, und wählen Sie dann **Skype for Business Online-Anruf Qualitäts Dashboard**aus.

     ![Screenshot: Auswählen des Dashboards für die Anrufqualität](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. Melden Sie sich auf der daraufhin geöffneten Seite mit ihrem globalen Administrator Konto an, und geben Sie die Anmeldeinformationen für das Konto ein, wenn Sie dazu aufgefordert werden.

Nachdem Sie sich angemeldet haben, wird das Dashboard für die Anrufqualität nach der Aktivierung mit dem sammeln und Verarbeiten von Daten beginnen.

## <a name="features-of-the-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Features des Anruf Qualitäts Dashboards für Microsoft Teams und Skype for Business Online

<a name="BKMKFeaturesOfTheCQD"> </a>


CQD-Zusammenfassungsberichte bieten eine Reihe von Funktionen, die für detaillierte Berichte geplant sind. Die Unterschiede zwischen den Editionen sind hier zusammengefasst:
  
|Feature|Zusammenfassungsberichte|Detaillierte Berichte|
|:--- |:--- |:--- |
|Anwendungsfreigabemetrik | Nein | Ja |
|Unterstützung von Kunden-Gebäudeinformationen | Ja | Ja  |
|Support für Kunden Endpunktinformationen | Nur in <span>CQD.Teams.Microsoft.com<span/> | Nur in <span>CQD.Teams.Microsoft.com<span/> |
|Unterstützung für Drilldown-Analyse   | Nein   | Ja   |
|Medienzuverlässigkeitsmetriken   | Nein   | Ja   |
|Sofort einsatzbereite Berichte   | Ja   | Ja    |
|Übersichtsberichte   | Ja   | Ja    |
|Berichtssatz pro Nutzer   | Nein   | Ja   |
|Anpassung des Berichtssatzes (Hinzufügen, Löschen, Ändern von Berichten)   | Nein   | Ja   |
|Videobasierte Bildschirmfreigabe-Metriken   | Nein   | Ja   |
|Videometriken   | Nein   | Ja   |
|Verfügbare Datenmenge   | Letzte 12 Monate   | Letzte 12 Monate   |
|Microsoft Teams-Daten   | Ja   | Ja    |
| | | |

### <a name="out-of-the-box-reports"></a>Sofort einsatzbereite Berichte

Alle Editionen von CQD bieten eine Erfahrung, die Ihnen bei der Anruf Qualitätsmetrik hilft, ohne neue Berichte erstellen zu müssen. Nachdem die Daten im Back-End verarbeitet wurden, sehen Sie in den Berichten die Daten zur Anrufqualität.

Neu im Januar 2020: [Herunterladen von Power BI-Abfragevorlagen für CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Anpassbare Power BI-Vorlagen, die Sie verwenden können, um Ihre CQD-Daten zu analysieren und zu melden.
  
### <a name="overview-reports"></a>Übersichtsberichte

Alle Editionen des CQD bieten einen Einstiegspunkt für allgemeine Informationen zur Anrufqualität, aber die Art und Weise, wie Informationen in Zusammenfassungsberichten angezeigt werden, unterscheidet sich von detaillierten Berichten.  
  
Zusammenfassungsberichte bieten eine vereinfachte Ansicht im Registerkartenformat, sodass Sie den allgemeinen Status und die Trends für die Anrufqualität schnell durchsuchen und verstehen können.

Die vier Registerkarten umfassen:
  
- **Allgemeine Anrufqualität** – stellt Informationen zu allen Streams bereit, bei denen es sich um eine Aggregation handelt, in der die monatlichen und täglichen Trends für Folgendes angezeigt werden:
  - Server-Client-Streams
  - Client-Client-Streams
  - Getrennte Server-Client-und Client-Client-Streams
- **Server – Client** – enthält Details zu den Datenströmen zwischen Server-und Client Endpunkten.
- **Client – Client** – enthält Details zu den Streams zwischen zwei Client Endpunkten.
- **SLA zur Sprachqualität** – bietet Informationen zu anrufen, die in der Skype for Business Online-SLA für Sprachqualität enthalten sind.

> [!NOTE]
> CQD Version 3 arbeitet mit Microsoft Teams, Skype for Business Online und Skype for Business Server zusammen. Wenn Sie CQD mit Skype for Business Server 2019 verwenden möchten, müssen Sie den [Anrufdaten-Konnektor konfigurieren](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector). Weitere Informationen finden Sie unter [Planen von Anrufdaten-Konnektoren](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) vor dem Start.

- Anrufqualität nach Regionen:

  - Datum-für-Region
  - aggregiert nach Stunden pro Region
  - bestimmte Speicherorte
  - bestimmtes Subnetz
  - betroffene Benutzer oder Benutzer

- Anruf Zuverlässigkeit/-Fehler nach Region:
  - Datum-für-Region
  - aggregiert nach Stunden pro Region
  - bestimmte Speicherorte
  - bestimmtes Subnetz
  - betroffene Benutzer oder Benutzer

- Meinen Anruf (RMA) nach Regionen bewerten: von Monat zu Region, aufgeschlüsselt nach Regionen, bis zu bestimmten Orten für Benutzer, die eine geringe Anzahl von Bewertungen anbieten. CQD V3 enthält auch Verbatim-Feedback.
- Helpdesk: steht für einen bestimmten Benutzer für P2P-Anrufe oder Besprechungen oder für alle Teilnehmer und Anrufdetails zur Verfügung. Hilft bei der Ermittlung möglicher System Probleme basierend auf Netzwerkstandort, Geräten oder Firmware.  
- Clientversionen: zeigen Sie die Sitzungs-und Benutzeranzahl für jede Client Version an, oder führen Sie einen Drilldown zu Benutzernamen für jede Client Version durch. Vordefinierte Filter für Produkt-und Client Typen helfen bei der Fokussierung der Versionen auf bestimmte Clients.
- Endpunkte: zeigt Computer Endpunkte an, die dem Hersteller/Modell des PC/Mac zugeordnet sind. Zeigt die aggregierte Qualität nach Marke/Modell. Zuordnungsdaten werden ähnlich wie Gebäudedaten hochgeladen.

### <a name="overall-call-quality-tab"></a>Registerkarte „Gesamtanrufqualität"

Verwenden Sie die Daten auf dieser Registerkarte, um den Status und die Trends für die Anrufqualität basierend auf Datenstrom Zählern und schlechten Prozentsätzen zu bewerten. Die Legende oben rechts zeigt an, welche Farbe und welche visuellen Elemente diese Kennzahlen darstellen.
  
![Screenshot: Anzeigen der Registerkarte "Anrufqualität"](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
Streams werden in drei Gruppen klassifiziert: gut, schlecht und nicht klassifiziert. Es gibt auch berechnete *schlechte%* -Werte, die Ihnen das Verhältnis der als *schlecht* klassifizierten Streams zur Gesamtanzahl der klassifizierten Datenströme geben. Da *schlechte% = schlechte Streams/(schlechte Streams + gute Streams) * 100*, ist der *schlechte%* durch das vorhanden sein mehrerer nicht *klassifizierter* Streams nicht betroffen. Wenn Sie sehen möchten, was einen Datenstrom als "schlecht" oder "gut" klassifiziert, lesen Sie die [Datenstrom Klassifizierung im Dashboard für die Anrufqualität](stream-classification-in-call-quality-dashboard.md).
  
Verwenden Sie die Skalierung auf der linken Seite, um die Werte für die Datenstromanzahl zu messen.
  
![Screenshot: zeigt Werte für die Datenstromanzahl an](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Verwenden Sie die Skala rechts, um die Werte für „% Schlecht" zu ermitteln.
  
![Screenshot: zeigt schlechte%-Werte an](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
Sie erhalten auch die tatsächlichen numerischen Werte, indem Sie mit der Maus über eine Leiste fahren.
  
> [!NOTE]
> Das folgende Beispiel stammt aus einem kleinen Beispiel-Dataset, und die Werte sind für eine tatsächliche Bereitstellung nicht realistisch.
  
![Screenshot: zeigt die Maus, die für den Zugriff auf Daten verwendet wird](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
Das Gesamtvolumen des Datenstroms hilft festzustellen, wie relevant die berechneten schlechten Prozentsätze sind. Je kleiner die Gesamtmenge der Datenströme ist, desto weniger zuverlässig sind die gemeldeten schlechten Prozentwerte.
  
### <a name="server-client-tab-and-client-client-tabs"></a>Registerkarten „Server-Client" und „Client-Client"

Diese beiden Registerkarten enthalten Details zu den Datenströmen, die in ihren Endpunkt-zu-Endpunkt-Szenarien stattfanden. Die Registerkarte Server-Client verfügt über vier reduzierbare Abschnitte, die vier Szenarien darstellen, unter denen Mediendatenströme fließen.
  
- Innen verkabelt
- Außen verkabelt
- Innen WLAN
- Außen WLAN

Auf ähnliche Weise verfügt die Registerkarte Client-Client über fünf reduzierbare Abschnitte:

- Intern verdrahtet – innen verkabelt
- Intern verdrahtet – außerhalb verdrahtet
- Außen verdrahtet – außerhalb verdrahtet
- Intern verdrahtet – WLAN-Anschluss
- Intern verdrahtet – WiFi außerhalb

#### <a name="inside-test"></a>Innentest

Bei der Verarbeitung klassifiziert das AQD-Back-End einen Datenstrom als  *Innen*  oder *Außen*  anhand von Gebäudeinformationen, falls diese vorhanden sind. Die Endpunkte jedes Datenstroms sind einer Subnetzadresse zugeordnet. Wenn sich das Subnetz in der Liste der Subnetze befindet, die in den hochgeladenen Gebäudeinformationen als InsideCorp markiert sind, wird es im *Innern*berücksichtigt. Wenn noch keine Gebäudeinformationen hochgeladen wurden, werden die Datenströme von Inside Test immer als *außerhalb*klassifiziert.  

> [!NOTE]
> Der interne Test für ein Server-Client-Szenario berücksichtigt nur den Client Endpunkt. Da sich Server aus der Perspektive des Benutzers stets außerhalb befinden, werden sie beim Test nicht berücksichtigt.
  
#### <a name="wired-vs-wifi"></a>Verkabelt oder WLAN

Wie die Namen angeben, basieren die Klassifizierungskriterien auf dem Typ der Clientverbindungen. Um es noch einmal zu verdeutlichen: Ein Server ist immer verkabelt und wird nicht in die Berechnung einbezogen.
  
> [!NOTE]
> Wenn wir von einem Datenstrom ausgehen und einer der beiden Endpunkte mit einem WLAN verbunden ist, wird er im AQD als WLAN klassifiziert.
  
## <a name="selecting-product-data-to-see-in-reports"></a>Auswählen der Produktdaten, die in Berichten angezeigt werden sollen

<a name="BKMKProductFilter"></a>

In den Zusammenfassungsberichten und erweiterten Standortberichten können Sie mithilfe der Dropdownliste **Produktfilter** alle Produktdaten, nur Microsoft Teams-Daten oder nur Skype for Business Online-Daten anzeigen.
  
![Screenshot: zeigt die Optionen des Produkt Filter-Steuerelements an.](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
In detaillierten Berichten können Sie die **is Teams** -Dimension verwenden, um die Daten nach Microsoft Teams oder Skype for Business Online-Daten zu filtern.
  
## <a name="upload-tenant-data-information"></a>Hochladen von Mandantendaten Informationen

<a name="BKMKTenantDataInformationUpload"></a>

Das Dashboard für CQD-Zusammenfassungsberichte enthält eine Seite für **Mandantendaten Upload** , auf die durch Auswählen von **Mandantendaten Upload** im Menü Einstellungen in der oberen rechten Ecke zugegriffen wird. Diese Seite wird für Administratoren verwendet, um Ihre eigenen Informationen hochzuladen, beispielsweise:

- Eine Karte mit IP-Adressen und geografischen Informationen
- Eine Karte der einzelnen WLAN-AP und deren Mac-Adresse
- Eine Karte des Endpunkt-zu-Endpunkt-Marke/-Modells/-Typs usw.
  
> [!NOTE]
> Berichts Etiketten, die Sie auf CQD hochladen, werden unter ihrer Vereinbarung für Office 365 als *Support Daten* behandelt, einschließlich aller Informationen, die andernfalls als *Kundendaten* oder *persönliche Daten*gelten. Bitte geben Sie keine Daten an, die Sie Microsoft nicht als Support- *Daten*zur Verfügung stellen möchten, diese Informationen sind für Microsoft-Ingenieure zu Supportzwecken sichtbar.

![Screenshot: zeigt die Mandantendaten des Anruf Qualitäts Dashboards](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. Verwenden Sie auf der Seite **Mandantendaten Upload** das Dropdownmenü, um einen Datendateityp auszuwählen, der hochgeladen werden soll. Der Datentyp "Datei" gibt den Inhalt der Datei an (beispielsweise "Gebäude" bezieht sich auf die Zuordnung von IP-Adresse und Gebäude und anderen geografischen Informationen; "Endpunkt" bezieht sich auf die Zuordnung von Endpunkt Name zu Endpunkt-Marke/Modell/Typ-Informationen). CQD unterstützt derzeit "Gebäude"-und "Endpunkt"-Datentypen für CQD.Teams.Microsoft.com (in der Preview-Phase und noch nicht offiziell verfügbar), CQD.lync.com unterstützt nur den "Building"-Datentyp.



2. Nachdem Sie den Datentyp "Datei" ausgewählt haben, klicken Sie auf **Durchsuchen** , um eine Datendatei auszuwählen.

   - Bei einer Datendatei muss es sich um eine TSV-Datei (durch tabstoppgetrennte Werte) oder um eine CSV-Datei (durch Kommas getrennte Werte) handeln. Bei einer CSV-Datei müssen alle Felder, die ein Komma enthalten, in Anführungszeichen gesetzt oder das Komma entfernt werden. Wenn Ihr Gebäudename beispielsweise NY, NY lautet, geben Sie "NY, NY" in die CSV-Datei ein.
   - Die Datendatei darf nicht größer als 50 MB sein.
   - Dateien, die in CQD.Teams.Microsoft.com hochgeladen wurden, verfügen über eine erweiterte Zeilenbeschränkung von 1 Million, um die Abfrageleistung schnell zu halten. Dieser Grenzwert gilt auch für CQD v2 auf CQD<span></span>. lync<span></span>. com.
   - Bei jeder Datendatei muss jede Spalte in der Datei einem vordefinierten Datentyp entsprechen, der später in diesem Thema besprochen wird.
3. Geben Sie als nächstes ein **Start Datum** an, und **Geben Sie optional ein Enddatum**an.
4. Wählen Sie schließlich **Upload** aus, um die Datei auf den CQD-Server hochzuladen.
    Bevor die Datei hochgeladen wird, wird sie zunächst validiert. Sobald sie validiert ist, wird sie in einem Azure-BLOB gespeichert. Wenn die Überprüfung fehlschlägt oder die Datei nicht in einem Azure-BLOB gespeichert werden kann, fordert eine Fehlermeldung eine Korrektur der Datei an. Die folgende Abbildung zeigt einen Beispiel Fehler mit einer falschen Anzahl von Spalten in der Datendatei.

     ![Screenshot: zeigt einen Fehler beim Hochladen der Überprüfung](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. Wenn während der Überprüfung keine Fehler auftreten, wird der Dateiupload erfolgreich ausgeführt. Anschließend können Sie die hochgeladene Datendatei in der Tabelle **meine Uploads** anzeigen. Unten auf dieser Seite wird auch eine vollständige Liste aller Dateien angezeigt, die für den aktuellen Mandanten hochgeladen wurden.
    Jeder Datensatz zeigt eine geuploadete Mandanten Datendatei mit dem Dateityp, dem letzten Aktualisierungszeitpunkt, dem Zeitraum, der Beschreibung, dem Symbol "entfernen" und einem Download Symbol. Um eine Datei zu entfernen, wählen Sie das Papierkorbsymbol in der Tabelle aus. Um eine Datei herunterzuladen, wählen Sie das Downloadsymbol in der Spalte **Download** der Tabelle aus.

     ![Screenshot: zeigt die Tabelle "meine Uploads"](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)

6. Wenn Sie sich für die Verwendung mehrerer Gebäudedaten Dateien oder mehrerer Endpunkt Datendateien entscheiden, werden einige Berichte langsamer generiert.

### <a name="tenant-data-file-format-and-structure"></a>Mandantendaten Dateiformat und-Struktur

<a name="BKMKTenantDataFile"> </a>

### <a name="building-data-file"></a>Erstellen einer Datendatei

CQD verwendet eine Gebäude Datendatei, die hilfreiche Anrufdetails bereitstellt. Die Spalte Subnet wird durch Erweitern der Spalte Netzwerk + NetworkRange abgeleitet, und anschließend wird die Spalte Subnetz mit der Spalte erstes Subnetz oder Zweites Subnetz des Anrufdaten Satzes verknüpft, um die Informationen für Gebäude, Stadt, Land oder Region anzuzeigen. Das Format der Datendatei, die Sie hochladen, muss die folgenden Kriterien erfüllen, um die Gültigkeitsprüfung vor dem Upload durchführen zu können:

Sie können [hier](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true) eine Beispielvorlage herunterladen.
  
- Bei der Datei muss es sich um eine TSV-Datei (Spalten werden durch eine Registerkarte getrennt) oder um eine CSV-Datei (Spalten werden durch ein Komma getrennt) handeln.
- Die Datendatei enthält keine Tabellenkopfzeile. Die erste Zeile der Datendatei wird als reelle Daten erwartet, nicht für Kopfzeilen Beschriftungen wie "Netzwerk".
- Datentypen in der Datei können nur String, Integer oder Boolean sein. Für den Datentyp "Integer" muss der Wert ein numerischer Wert sein. Boolesche Werte müssen entweder 0 oder 1 sein.
- Wenn in einer Spalte der Datentyp "Zeichenfolge" verwendet wird, kann ein Datenfeld leer sein, muss aber durch Tabstopps oder Komma getrennt werden. Ein leeres Datenfeld weist nur einen leeren Zeichenfolgenwert zu.
- Es müssen 14 Spalten für jede Zeile vorhanden sein, jede Spalte muss den entsprechenden Datentyp aufweisen, und die Spalten müssen in der in der folgenden Tabelle aufgelisteten Reihenfolge liegen:

||||||||||||||||
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:---  |:--- |:---|
|**Name des Spaltenfelds**|NetworkIP  |NetworkName              |NetworkRange|BuildingName  |Ownershiptype| Buildingtype  |BuildingOfficeType|Ort   |ZipCode|Land|Bundesland |Region|InsideCorp&dagger;|Express Route&Dagger;|VPN (optional)|
|**Datentyp**        | Zeichenfolge    | Zeichenfolge                  |Nummer      | Zeichenfolge       | Zeichenfolge      | Zeichenfolge        |Zeichenfolge            |Zeichenfolge |Zeichenfolge |Zeichenfolge |Zeichenfolge|Zeichenfolge|Boolean   |Boolean     |Boolean|
|**Beispielwert**    |192.168.1.0|USA/Seattle/SEATTLE-SEA-1| 26         | SEATTLE-SEA-1| Contoso     | IT Termination|Engineering       |Seattle|98001  |USA     |WA    |MSUS  | 1        |0           | 0|
|||||||||||||||||

&dagger;Diese Einstellung kann verwendet werden, um zu reflektieren, ob sich das Subnetz innerhalb des Unternehmensnetzwerks befindet. Sie können die Verwendung für andere Zwecke anpassen, wenn Sie sich dafür entscheiden.

&Dagger;Diese Einstellung kann verwendet werden, um anzugeben, ob das Netzwerk Azure Express Route verwendet. Sie können die Verwendung für andere Zwecke anpassen, wenn Sie sich dafür entscheiden.  

**Beispiel Zeile:**

`192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> Der Netzwerkbereich kann zur Darstellung eines Supernetzes (einer Kombination aus mehreren Subnetzen mit einem einzelnen Routing-Präfix) verwendet werden. Alle neuen Gebäude-Uploads werden auf sich überlappende Bereiche hin untersucht. Wenn Sie zuvor eine Gebäudedatei hochgeladen haben, sollten Sie die aktuelle Datei herunterladen und erneut hochladen, um mögliche Überlappungen zu identifizieren und das Problem vor dem erneuten Hochladen zu beheben. Alle Überlappungen in zuvor hochgeladenen Dateien können zu falschen Zuordnungen von Subnetzen zu Gebäuden in den Berichten führen. Bei bestimmten VPN-Implementierungen werden die Subnetinformationen nicht genau gemeldet. Es wird empfohlen, beim Hinzufügen eines VPN-Subnetzes zur Gebäudedatei anstelle eines Eintrags für das Subnetz separate Einträge für jede Adresse im VPN-Subnetz als separates 32 Bit-Netzwerk hinzuzufügen. Jede Zeile kann die gleichen Gebäudemetadaten enthalten. Ein Beispiel: Anstelle einer Zeile für 172.16.18.0/24 sollten Sie 256 Zeilen verwenden - eine Zeile für jede Adresse zwischen 172.16.18.0/32 und 172.16.18.255/32 (einschließlich).
>
> Die VPN-Spalte ist optional und wird standardmäßig auf 0 gesetzt.  Wenn der Wert der VPN-Spalte auf 1 festgesetzt ist, wird das durch diese Zeile dargestellte Subnetz vollständig erweitert, damit es allen IP-Adressen im Subnetz entspricht.  Verwenden Sie diese sparsam und nur für VPN-Subnetze, da sich diese Subnetze durch eine vollständige Erweiterung negativ auf die Abfragezeiten für Abfragen mit Gebäudedaten auswirken.

### <a name="endpoint-data-file"></a>Endpunkt Datendatei

CQD verwendet eine Endpunkt Datendatei. Die Spaltenwerte werden in der ersten Clientendpunkt Name des Anrufdaten Satzes oder in der Spalte des zweiten Clientendpunkts verwendet, um die Informationen für die Endpunkt Marke, das Modell oder den Typ anzuzeigen. Das Format der Datendatei, die Sie hochladen, muss die folgenden Kriterien erfüllen, um die Gültigkeitsprüfung vor dem Upload durchführen zu können:

- Bei der Datei muss es sich um eine TSV-Datei (Spalten werden durch eine Registerkarte getrennt) oder um eine CSV-Datei (Spalten werden durch ein Komma getrennt) handeln.
- Der Inhalt der Datendatei umfasst keine Tabellenüberschriften. In der ersten Zeile der Datendatei wird erwartet, dass es sich um reelle Daten handelt, nicht um eine Headerbezeichnung wie "Endpunktname".
- In allen sieben Spalten wird nur der Datentyp "Zeichenfolge" verwendet. Die maximal zulässige Länge beträgt 64 Zeichen.
- Ein Datenfeld kann leer sein, muss aber durch Tabstopps oder Kommas getrennt werden. Ein leeres Datenfeld weist nur einen leeren Zeichenfolgenwert zu.
- Endpunktname muss eindeutig sein, da andernfalls der Upload fehlschlägt. Wenn eine Zeile oder zwei Zeilen vorhanden sind, die denselben Endpunktname verwenden, führt der Konflikt zu einer fehlerhaften Verknüpfung.
- EndpointLabel1, EndpointLabel2 und EndpointLabel3 sind anpassbare Beschriftungen. Sie können leere Zeichenfolgen oder Werte sein, beispielsweise "IT-Abteilung, die als 2018-Laptop bezeichnet wird" oder "Asset Tag 5678".
- Für jede Zeile müssen sieben Spalten vorhanden sein, und die Spalten müssen in der folgenden Reihenfolge vorliegen:

  **Feld Reihenfolge:**

EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2, EndpointLabel3

  **Beispiel Zeile:**

"1409W3534, 123-Hersteller, Fabrikam-Modell 123, Laptop, IT-Designated 2018-Laptop, Inventar-Tag 5678, Kauf 2018

## <a name="migrate-reports-from-previous-version-of-cqd"></a>Migrieren von Berichten aus einer früheren Version von CQD

Wenn Sie Berichte oder hochgeladene Mandantendaten (Mapping)-Dateien in CQD fürhttps://cqd.lync.com) Skype for Business erstellt haben (und diese in CQDhttps://cqd.teams.microsoft.com)for Teams migrieren möchten, gehen Sie wie folgt vor:

1.  Wechseln Sie [https://cqd.lync.com/cqd/](https://cqd.lync.com/cqd/) zu dem Berichtssatz, den Sie exportieren möchten, und navigieren Sie zu diesem. 
2.  Zeigen Sie mit der Maus auf den Bericht, und klicken Sie auf "...". Wählen Sie **Berichtstruktur exportieren**aus. Speichern Sie die Exportdatei.
3.  Wechseln Sie [https://cqd.teams.microsoft.com/cqd/](https://cqd.teams.microsoft.com/cqd/) zu dem Speicherort, an dem Sie die Berichte importieren möchten, und navigieren Sie zu ihm.
4.  Klicken Sie in den Links auf der linken Seite auf **importieren** , und wählen Sie die exportierte Datei aus. 
5.  Nachdem die Berichte importiert wurden, wird die folgende Meldung angezeigt: "der berichtsimport war erfolgreich. Der neue Bericht wurde am Ende des Berichtssatzes hinzugefügt. " 


## <a name="create-custom-detailed-reports"></a>Erstellen benutzerdefinierter detaillierter Berichte

Wenn Sie feststellen, dass Sie einen bestimmten Bericht erstellen möchten, der sich auf eine Dimension der Daten in einer Weise konzentriert, in der die bereitgestellten detaillierten Berichte dies nicht tun, erstellen Sie einen benutzerdefinierten Bericht.

Klicken Sie in der Pulldown-Liste der oben auf dem Bildschirm angezeigten Berichte auf \(dem Bildschirm\) " **Zusammenfassungsberichte** " auf " **detaillierte Berichte** " und dann auf " **neu** " und dann im Aktionsmenü eines Berichts auf "Bearbeiten", um den Abfrage-Editor anzuzeigen. Jeder Bericht basiert auf einer Abfrage im Cube. Ein Bericht ist die visuelle Darstellung der Daten, die von der jeweiligen Abfrage zurückgegeben werden. Der Abfrage-Editor hilft Ihnen, diese Abfragen und die Anzeigeoptionen des Berichts zu bearbeiten. Wenn Sie den Abfrage-Editor für einen neuen Bericht öffnen, sehen Sie etwas ähnliches wie diesen Screenshot:

![Bearbeiten neuer Berichte](media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. Dimensionen, Kennzahlen und Filter werden im linken Bereich ausgewählt. Klicken Sie auf die Schaltfläche "Plus" neben einer Überschrift, um das Dialogfeld zu öffnen, in dem Sie eine Bemaßung, ein Measure oder einen Filter hinzufügen und das entsprechende Kontrollkästchen aktivieren können. Wenn Sie einen vorhandenen Bericht bearbeiten, können Sie vorhandene Werte deaktivieren, um Sie zu entfernen. Ausführliche Informationen finden Sie unter [Dimensionen und Measures, die im Dashboard für die Anrufqualität verfügbar sind](dimensions-and-measures-available-in-call-quality-dashboard.md).
2. Optionen für die Diagrammanpassung werden oben angezeigt.
3. Eine Vorschau des Berichts steht im Abfrage-Editor zur Verfügung.
4. Ein detaillierter Berichtname und eine Beschreibung können mit dem Bearbeitungsfeld am unteren Rand erstellt werden.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data"></a>Warum sehen meine CQD v2-Berichtsdaten anders aus als die CQD V3-Berichtsdaten? 

Wenn Daten Unterschiede zwischen CQD v2 und V3 angezeigt werden, stellen Sie sicher, dass der Datenabgleich oder die Validierung auf einer "Äpfel-zu-Apfel"-und einer schmalen Ebene erfolgt, nicht auf einer aggregierten Ebene. Wenn Sie beispielsweise beide Berichte für MSIT ' Building 30 ' WiFi Teams-Desktop Client Daten filtern, sollte der Prozentsatz der schlechten Qualität zwischen V2 und V3 identisch sein.

CQD v2 und CQD V3 haben unterschiedliche Gesamtanzahlen, da in CQD v2 keine neuen Szenarien für CQD V3 vorhanden sind. Es wird davon ausgegangen, dass Zusammenfassungs-oder aggregierte Gesamtzahlen ohne Filter unterschiedlich sind.  

Wenn das Nutzungsszenario Skype for Business Server 2019-Anrufe umfasst, beinhaltet CQD V3-Daten Skype-bot-Anrufe (automatische Telefonzentrale, CVI, Virtual Desktop Interface), Live-Events und PSTN-Anrufe. CQD v2 verwendet diese Daten nicht. (Für CQD v3 ist Skype for Business Server 2019 mit Cloud Data Connector konfiguriert.)

Wenn Sie beispielsweise 200.000-Audiostreams mit 5000-Fehlern in einem CQD v2-Zusammenfassungsbericht sehen, wäre es nicht ungewöhnlich, 300.000 Audiostreams mit 5500-Fehlern zu sehen (der Unterschied kann auf Skype for Business Server 2019-Anrufe, CVI-Anrufe und PSTN-Anrufe zurückzuführen sein. usw.) in einem CQD V3-Zusammenfassungsbericht.

Um unerwartete Unterschiede zu unterscheiden, sehen Sie sich mehr als eine Aufschlüsselung der Gesamtdaten an. Filtern Sie die Daten nach einem oder mehreren der folgenden Parameter:

- User Agent Category Pair
- Erstes Produkt
- Zweites Produkt

### <a name="other-expected-differences-between-cqd-v2-and-cqd-v3"></a>Andere erwartete Unterschiede zwischen CQD v2 und CQD v3

Es gibt mehrere Verbesserungen bei der Qualität und Zuverlässigkeit in Teams, aber nicht in Skype for Business Online:

- Automatisches Wiederherstellen der Verbindung
- Schnelles Roaming
- Verbesserte BW-Verwaltung

Wenn Sie Daten für diese beiden Dienste vergleichen:

- Entscheiden Sie sich für ein Szenario mit engem Fokus, beispielsweise für Unternehmens-Wired-Verbindungen, Windows-Desktops oder eine einzelne Region oder ein einzelnes Gebäude.
- Überprüfen Sie die IP-Bereiche von Teams Mr, TR oder MP. Die Teams-Bereiche sind neuer als Skype for Business Online und können Verbindungsprobleme mit Firewalls verursachen.
- Vergleichen Sie keine Zusammenfassungs-oder Spitzen Zahlen. Diese Vergleiche führen dazu, dass Sie einen umfangreichen Anruf Umfang von Skype for Business Online-anrufen auf einer drahtgebundenen Unternehmensverbindung mit einer kleinen Anzahl von Teams-anrufen in einem LTE-oder privaten Netzwerk vergleichen.
- Achten Sie auf Standort Verzerrungen und Bevölkerungs Unterschiede: Es gibt viele Vergleiche, die zu unähnlich sind, um nützlich zu sein:
  - Noam: APAC
  - NY: Goa
  - Verkabelt:WiFi
  - Unternehmensnetzwerk: Heimnetzwerk
  
### <a name="why-cant-i-see-euii-in-cqd"></a>Warum kann ich EUII in CQD nicht sehen?

Diese Administratorrollen können auf CQD zugreifen, aber Sie können EUII (Endbenutzer identifizierbare Informationen) nicht anzeigen:
- Office 365-berichtsleser
- Supportfachmann für die Teams-Kommunikation

Weitere Informationen zu Rollen, die auf CQD zugreifen können – einschließlich EUII-Read [Zuweisen von Rollen für den Zugriff auf CQD](quality-of-experience-review-guide.md#assign-roles-for-accessing-cqd).

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Warum werden in CQD Skype for Business-Informationen angezeigt, wenn ich nur für Teams gefiltert habe?

Wenn Sie nur in CQD-Berichten (isteams = 1) nach Teams filtern, Filtern Sie nach allen anrufen, wobei der *erste Endpunkt* Teams ist. Wenn es sich bei dem *zweiten Endpunkt* um Skype for Business handelt, werden diese Informationen in Ihrem CQD-Bericht angezeigt.

## <a name="related-topics"></a>Verwandte Themen

[Im Anrufqualitäts-Dashboard verfügbare Dimensionen und Kennzahlen](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Datenstromklassifizierung im Dashboard für Anrufqualität](stream-classification-in-call-quality-dashboard.md)

[Einrichten der Anrufanalyse von Skype for Business](set-up-call-analytics.md)

[Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Anrufanalyse- und Anrufqualitäts-Dashboard](difference-between-call-analytics-and-call-quality-dashboard.md)
