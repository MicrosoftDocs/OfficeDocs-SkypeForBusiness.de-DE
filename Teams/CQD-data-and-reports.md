---
title: Daten und Berichte im Anrufqualitätsdashboard (CQD)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
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
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Erfahren Sie mehr über die Daten und Berichte, die im Microsoft Call Quality Dashboard (CQD) verfügbar sind.
ms.openlocfilehash: 2d36787a5341db016c18a30977cb086b0b6d7afc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111541"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a>Daten und Berichte im Anrufqualitätsdashboard (CQD)

Das Microsoft Call Quality Dashboard (CQD) verwendet einen Nah-Echtzeit-Datenfeed (NRT). Anrufeinträge sind in CQD innerhalb von 30 Minuten nach dem Ende eines Anrufs verfügbar. Anrufdatensätze aus der NRT-Pipeline sind nur einige Monate verfügbar, bevor sie aus dem Datensatz entfernt werden. 


## <a name="many-ways-to-access-cqd-data"></a>Viele Möglichkeiten für den Zugriff auf CQD-Daten

Sie können über verschiedene Möglichkeiten auf CQD-Daten zugreifen. Wählen Sie den aus, der Ihren Anforderungen am besten entspricht:

|  |  |
|---------|---------|
|Teams Admin Center [( https://admin.teams.microsoft.com) ](https://admin.teams.microsoft.com)    | CQD-Daten werden  auf der Seite Benutzer im Teams Admin Center mit den am häufigsten benötigten Daten in einem leicht lesbaren Format angezeigt. Sie können keine CQD-Daten anpassen, die Sie unter Benutzer **finden.**  |
|CQD-Portal [( https://cqd.teams.microsoft.com) ](https://cqd.teams.microsoft.com)     | Robuste Zusammenfassung und detaillierte Berichte, die die meisten Anforderungen erfüllen, mit Drill-Through-Filterung. Sie können Berichte auch im CQD-Portal anpassen. <br><br>Holen Sie [sich zwei CQD-Berichtsvorlagen,](#import-the-cqd-report-templates) mit deren Hilfe Sie Daten im CQD-Portal analysieren können.       |
|Power BI     | Verwenden Sie direkte Abfragen zum Anzeigen Ihrer CQD-Daten in Power BI mithilfe [anpassbarer Power BI-Vorlagen.](CQD-Power-BI-query-templates.md) [Laden Sie Power BI-Abfragevorlagen für CQD herunter.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)<br><br>Sie können auch die REST-API verwenden, um über Power BI auf [CQD-Daten](/skypeforbusiness/management-tools/call-quality-dashboard/data-api) zu zugreifen. Verwenden Sie diese Methode, wenn Sie Ihre CQD-Daten herunterladen möchten, damit Sie offline darauf arbeiten können. Der Vorteil der Verwendung dieser Methode ist eine bessere Leistung, insbesondere bei großen Datensätzen, die in Power BI beim Onlinespeichern nicht verfügbar sind.       |
|Graph-API     | Greifen Sie mithilfe der Graph-API selbst auf [Anrufqualitätsdaten zu.](/graph/api/resources/callrecords-api-overview?view=graph-rest-beta) Dies ist die komplexeste Methode, bietet Ihnen jedoch die größte Kontrolle und Flexibilität bei der Analyse Ihrer Daten zur Anrufqualität. Wenn Sie es beispielsweise mit anderen Daten für Ihre Organisation verbinden müssen, können Sie die Graph-API verwenden, um ein Datenmodell zu erstellen und Daten zur Anrufqualität zu integrieren.        |

## <a name="import-the-cqd-report-templates"></a>Importieren der CQD-Berichtsvorlagen

Laden [Sie zwei kuratierte CQD-Berichtsvorlagen](https://aka.ms/qertemplates) (Alle Netzwerke und verwaltete Netzwerke) herunter, um CQD schnell zu nutzen. Die Vorlage "Alle Netzwerke", die für die Arbeit mit einer Gebäudedatendatei optimiert ist, kann verwendet werden, während Sie auf die Erfassung und das Hochladen von Gebäudeinformationen in CQD hinarbeiten, wie im nächsten Abschnitt beschrieben.

**So importieren Sie die Vorlagen (. CQDX) in CQD**

1. Wählen Sie in CQD **im** Menü oben auf der Seite detaillierte Berichte aus.

2. Wählen Sie im linken Bereich Importieren **aus.** Navigieren Sie zur ersten CQDX-Vorlage, und wählen Sie **Öffnen aus.**

3. Nachdem die Vorlage hochgeladen wurde, wird in einem Popupfenster die Meldung "Berichtsimport war erfolgreich" angezeigt. 

4. Wiederholen Sie die Schritte 2 und 3 für die zweite CQD-Vorlage.

   > [!NOTE]
   > Jeder Benutzer muss die CQD-Vorlagen in seine CQD-Instanz importieren. 



## <a name="euii-data"></a>EUII-Daten

Aus Compliancegründen werden DIE DATEN (EUII) (auch als personenbezogene Informationen oder PII bezeichnet) nur 28 Tage lang aufbewahrt. Wenn NRT-Daten die 28-Tage-Marke überschritten, werden Felder, die EUII enthalten, entfernt, was zu EUII-freien NRT-Daten führt. Felder, die EUII-Daten enthalten, sind:

- Vollständige IP-Adresse
- Media Access Control (MAC) Adresse
- Basic Service Set Identifier (BSSID)
- SIP-URI (Session Initiation Protocol) (nur Skype for Business)
- Benutzerprinzipalname (User Principal Name, UPN)
- Name des Endpunkts des Computers
- User Verbatim Feedback
- Objekt-ID (die Active Directory-Objekt-ID des Endpunktbenutzers)

### <a name="admin-roles-with-and-without-euii-access"></a>Administratorrollen mit und ohne EUII-Zugriff

Diese [RBAC-Rollen](/azure/role-based-access-control/overview) **verfügen ÜBER** EUII-Zugriff:
- Globaler Administrator
- Teams Service Admin
- Teams Communications Admin
- Teams-Kommunikationssupporttechniker
- Globaler Reader
- Skype for Business Admin

Diese RBAC-Rollen **haben keinen** EUII-Zugriff:
- Reports Reader
- Supportfachmann für die Teams-Kommunikation


## <a name="date-controls"></a>Datumssteuerelemente

CQD unterstützt die folgenden Rolling Trend-Typen:

- 5 Tage
- 7 Tage
- 30 Tage
- 60 Tage
- 90 Tage

Der Parameter URL Date akzeptiert ein Feld "Tag". In Berichten für fortlaufende Tage werden Datumsangaben verwendet, die im Format JJJJ-MM-TT als letzter Tag des Trends angegeben wurden. Der Parameter URL Date "00" gibt "heute" an.

|URL| Enddatum des Rolling Day Trend|
|:---|:---|
|<span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /2019-02/</span>   |Aktueller Tag im Februar 2019|
|<span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /2019-02-15/</span>|15. Februar 2019|
|<span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /00/</span>        |Aktueller Tag|
|||

Standardmäßig wird der aktuelle Tag des Monats als letzter Tag des Rolling Day Trends verwendet.


## <a name="data-available-in-cqd-reports"></a>In CQD-Berichten verfügbare Daten

Die Standardzusammenfassung und detaillierte CQD-Berichte sind möglicherweise alles, was Sie zum Verwalten der Anrufqualität für Ihre Organisation benötigen. Bei Bedarf können Sie [benutzerdefinierte Berichte erstellen.](#create-custom-detailed-reports) 

Wenn Sie Power BI zum Analysieren Ihrer CQD-Daten verwenden möchten, lesen Sie Verwenden von Power BI zum Analysieren von [CQD-Daten für Teams.](CQD-Power-BI-query-templates.md)

|Feature|Zusammenfassungsberichte|Detaillierte Berichte|
|:--- |:--- |:--- |
|Anwendungsfreigabemetrik | Nein | Ja |
|Unterstützung von Kunden-Gebäudeinformationen | Ja | Ja |
|Support für Kundenendpunktinformationen | Nur in <span> cqd.teams.microsoft.com<span/> | Nur in <span> cqd.teams.microsoft.com<span/> |
|Drilldownanalyseunterstützung   | Nein   | Ja   |
|Medienzuverlässigkeitsmetriken   | Nein   | Ja   |
|Sofort einsatzbereite Berichte   | Ja   | Ja   |
|Übersichtsberichte   | Ja   | Ja   |
|Berichtssatz pro Nutzer   | Nein   | Ja   |
|Anpassung des Berichtssatzes (Hinzufügen, Löschen, Ändern von Berichten)   | Nein   | Ja   |
|Videobasierte Bildschirmfreigabe-Metriken   | Nein   | Ja   |
|Videometriken   | Nein   | Ja   |
|Verfügbare Datenmenge   | Letzte 12 Monate   | Letzte 12 Monate   |
|Microsoft Teams-Daten   | Ja   | Ja   |
| | | |


 
### <a name="select-product-data-to-see-in-reports"></a>Auswählen von Produktdaten, die in Berichten zu sehen sind

In der Zusammenfassung und Location-Enhanced können Sie  die Dropdownliste Produktfilter verwenden, um alle Produktdaten, nur Microsoft Teams-Daten oder nur Skype for Business Online-Daten anzeigen.
  
![Screenshot: Zeigt die Steuerelementoptionen für den Produktfilter](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
In detaillierten Berichten können Sie die Dimension **Ist Teams** verwenden, um die Daten in Microsoft Teams- oder Skype for Business Online-Daten zu filtern.

## <a name="summary-reports"></a>Zusammenfassungsberichte

Dies sind die Berichte, die auf dem CQD-Dashboard angezeigt werden, wenn Sie sich zum ersten Mal bei CQD anmelden. Sie bieten Ihnen einen Überblick über Qualitätstrends mit täglichen, monatlichen und Tabellenberichten, um Subnetze mit schlechter Qualität zu identifizieren. 

| Tabstopp | Beschreibung |
|---------|---------|
|Allgemeine Anrufqualität     | Aggregat der anderen 3 Registerkarten.       |
|Server – Client     |Details der Datenströme zwischen Server- und Clientendpunkten.        |
|Client – Client     |Details der Datenströme zwischen zwei Clientendpunkten.        |
|SLA für Sprachqualität     |Informationen zu Anrufen, die in der Skype for Business-Sprachqualitäts-SLA [enthalten sind.](https://go.microsoft.com/fwlink/p/?linkid=846252)        |

### <a name="overall-call-quality-tab"></a>Registerkarte „Gesamtanrufqualität"

Verwenden Sie die Daten auf dieser Registerkarte, um den Anrufqualitätsstatus und Trends basierend auf Datenstromanzahl und schlechten Prozentwerten auszuwerten. Die Legende oben rechts zeigt an, welche Farbe und welche visuellen Elemente diese Kennzahlen darstellen.
  
![Screenshot: Anzeigen der Registerkarte Anrufqualität](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
Datenströme werden in drei Gruppen klassifiziert: "Gut", "Schlecht" und "Nicht klassifiziert". Es gibt auch *berechnete Schlechte %-Werte,*  die Ihnen das Verhältnis von Datenströmen, die als "Schlecht" klassifiziert wurden, zur Gesamtanzahl der klassifizierten Datenströme geben. Da *Poor % = Poor streams/ (Poor streams+ Good streams) * 100* ist das Poor *%*  von der Anwesenheit mehrerer nicht klassifizierter *Datenströme nicht*  betroffen. Informationen dazu, was einen Datenstrom als "schlecht" oder "gut" einreiht, finden Sie unter [Streamklassifizierung im Anrufqualitätsdashboard](stream-classification-in-call-quality-dashboard.md).
  
Verwenden Sie den Maßstab auf der linken Seite, um die Werte für die Datenstromanzahl zu messen.
  
![Screenshot: Zeigt Werte für die Datenstromanzahl](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Verwenden Sie die Skala rechts, um die Werte für „% Schlecht" zu ermitteln.
  
![Screenshot: Zeigt schlechte %-Werte](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
Sie erhalten auch die tatsächlichen numerischen Werte, indem Sie mit der Maus über eine Leiste fahren.
  
> [!NOTE]
> Das folgende Beispiel stammt aus einem kleinen Beispiel-Dataset, und die Werte sind für eine tatsächliche Bereitstellung nicht realistisch.
  
![Screenshot: Zeigt die Maus, mit der auf Daten zugegriffen wird](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
Das gesamte Datenstromvolumen hilft zu bestimmen, wie relevant die berechneten Prozentsätze "Schlecht" sind. Je kleiner das Gesamtvolumen der Datenströme ist, desto weniger zuverlässig sind die gemeldeten Prozentwerte schlecht.
  
### <a name="server-client-tab-and-client-client-tabs"></a>Registerkarten „Server-Client" und „Client-Client"

Diese beiden Registerkarten enthalten Details zu den Datenströmen, die in ihren Endpunkt-zu-Endpunkt-Szenarien stattgefunden haben. Die registerkarte Server-Client enthält vier reduzierbare Abschnitte, die vier Szenarien darstellen, unter denen Medienströme fließen würden.
  
- Innen verkabelt
- Außen verkabelt
- WiFi Inside
- WLAN außerhalb

Ebenso verfügt die Registerkarte Client-Client über fünf reduzierbare Abschnitte:

- Verkabelt – Verkabelt innen
- Verkabelt – Außen verkabelt
- Außen verkabelt – Außen verkabelt
- Verkabelt – WIFi Inside
- Verkabelt – WLAN außen

#### <a name="inside-versus-outside"></a>Innen und Außen

CQD klassifizierung einen Datenstrom  mithilfe von Gebäudeinformationen als *"Innen"* oder "Außen", sofern vorhanden. Die Endpunkte jedes Datenstroms sind einer Subnetzadresse zugeordnet. Wenn sich das Subnetz in der Liste der Subnetze befindet, die in den hochgeladenen Gebäudeinformationen als InsideCorp gekennzeichnet sind, wird es als *Inside betrachtet.* Wenn Die Gebäudeinformationen noch nicht hochgeladen wurden, werden die Datenströme von Inside Test immer als *Außerhalb klassifikisiert.* 

Der Innere Test für ein Server-Client berücksichtigt nur den Clientendpunkt. Da sich Server aus der Perspektive des Benutzers stets außerhalb befinden, werden sie beim Test nicht berücksichtigt.
  
#### <a name="wired-versus-wifi"></a>Verkabelt im Vergleich zu WLAN

Wie die Namen angeben, basieren die Klassifizierungskriterien auf dem Typ der Clientverbindungen. Server ist immer verkabelt und nicht in die Berechnung einbezogen. Wenn in einem bestimmten Datenstrom einer der beiden Endpunkte mit einem WLAN verbunden ist, wird er von CQD als WLAN klassifiisiert.

> [!NOTE]
> Wenn bei einem Datenstrom einer der beiden Endpunkte mit einem WLAN verbunden ist, wird er in CQD als WLAN klassifiziert.
  
  
## <a name="tenant-data-information"></a>Mandantendateninformationen

Das Dashboard CQD-Zusammenfassungsberichte enthält eine Seite  zum Hochladen von Mandantendaten, auf die zugegriffen wird, indem Sie im Menü Einstellungen in der oberen rechten Ecke die Option Mandantendatenupload auswählen.  Diese Seite wird für Administratoren verwendet, um eigene Informationen hochzuladen, z. B.:

- Eine Karte der IP-Adresse und geografischen Informationen.
- Eine Karte der einzelnen drahtlosen Aps und ihrer MAC-Adresse.
- Eine Karte von Endpoint to Endpoint Make/Model/Type usw.
  
Es wird empfohlen, Ihre Mandanten-, Gebäude- und Standortdaten hochzuladen, damit CQD diese Informationen in Ihre Berichte einmächst. Wenn Sie diese Daten noch nicht hochgeladen haben, lesen Sie [Hochladen von Mandanten- und Gebäudedaten.](CQD-upload-tenant-building-data.md) 


## <a name="detailed-reports"></a>Detaillierte Berichte

| Name | Beschreibung |
|---------|---------|
|Location-Enhanced Berichte     |Zeigt Qualitätstrends basierend auf Standortinformationen an. Dieser Bericht wird nur angezeigt, wenn Sie [Ihre Mandantendaten hochgeladen haben.](CQD-upload-tenant-building-data.md)        |
|Zuverlässigkeitsberichte     |Umfasst Audio-, Video-, Video-basierte Bildschirmfreigabe (VBSS) und Berichte zur App-Freigabe.        |
|Berichte zur Qualität der Benutzererfahrung     |Audioqualität und Zuverlässigkeit für alle Clients und Geräte, einschließlich Besprechungsräume. Diese Berichte sind eine "abgespeckte" Version der herunterladbaren [CQD-Vorlagen,](https://aka.ms/QERtemplates)die sich auf wichtige Bereiche für die Analyse der Audioqualität und Zuverlässigkeit konzentrieren.         |
|Drilldownberichte für Qualität     | Drilldowns: Datum nach Region, Speicherorten, Subnetzen, Stunde und Benutzern.        |
|Fehlerdrilldownberichte     | Drilldowns: Datum nach Region, Speicherorten, Subnetzen, Stunde und Benutzern.        |
|Bewerten von Anrufberichten     |Analysieren Sie die Bewertungen von Benutzeranrufen nach Region, Ort oder Benutzer. Enthält ausführliches Feedback.         |
|HelpDeskberichte     |HelpDeskberichte betrachten Anruf- und Besprechungsdaten für einzelne Benutzer, Benutzergruppen oder alle Benutzer. Durch die Einbeziehung von Gebäude- und EUII-Daten helfen diese Berichte, mögliche Systemprobleme basierend auf dem Netzwerkstandort, Konferenzdetails, Geräten oder Firmware zu identifizieren.         |
|Clientversionsberichte     |Clientversionszusammenfassung: Anzeigen der Anzahl der Sitzungen und Benutzer für jede Client-App-Version<br><br>Clientversion nach Benutzer: Anzeigen von Benutzernamen für jede Client-App-Version <br><br>Vordefinierte Filter für Produkt- und Clienttyp helfen, die Versionen auf bestimmte Clients zu konzentrieren.         |
|Endpunktberichte     |Zeigt die Anrufqualität nach Endpunkten des Computers (Computermodell und -modell) an. Diese Berichte enthalten Gebäudedaten, wenn Sie sie hochgeladen haben.         |


## <a name="create-custom-detailed-reports"></a>Erstellen benutzerdefinierter detaillierter Berichte

Wenn die standardmäßigen CQD-Berichte Ihren Anforderungen nicht entsprechen, verwenden Sie diese Anweisungen, um einen benutzerdefinierten Bericht zu erstellen. Oder (ab Januar 2020) Verwenden Sie [Stattdessen Power BI für CQD-Berichte. ](cqd-power-bi-query-templates.md)

Wählen Sie in der Pull-down-Liste der Berichte am oberen Rand des Bildschirms, die bei der Anmeldung angezeigt wird, auf dem Bildschirm Zusammenfassungsberichte die Option Detaillierte Berichte und \( dann Neu  \) **aus.**  Klicken **Sie auf** In einem Bericht bearbeiten, um den Abfrage-Editor zu sehen. Jeder Bericht basiert auf einer Abfrage im Cube. Ein Bericht ist die visuelle Darstellung der Daten, die von der jeweiligen Abfrage zurückgegeben werden. Der Abfrage-Editor hilft Ihnen beim Bearbeiten dieser Abfragen und der Anzeigeoptionen des Berichts.

> [!IMPORTANT]
> Der Netzwerkbereich kann zur Darstellung eines Supernetzes (einer Kombination aus mehreren Subnetzen mit einem einzelnen Routing-Präfix) verwendet werden. Alle neuen Gebäude-Uploads werden auf sich überlappende Bereiche hin untersucht. Wenn Sie zuvor eine Gebäudedatei hochgeladen haben, sollten Sie die aktuelle Datei herunterladen und erneut hochladen, um mögliche Überlappungen zu identifizieren und das Problem vor dem erneuten Hochladen zu beheben. Alle Überlappungen in zuvor hochgeladenen Dateien können zu falschen Zuordnungen von Subnetzen zu Gebäuden in den Berichten führen. Bestimmte VPN-Implementierungen geben die Subnetzinformationen nicht genau an. Es wird empfohlen, beim Hinzufügen eines VPN-Subnetzes zur Gebäudedatei anstelle eines Eintrags für das Subnetz separate Einträge für jede Adresse im VPN-Subnetz als separates 32 Bit-Netzwerk hinzuzufügen. Jede Zeile kann die gleichen Gebäudemetadaten enthalten. Ein Beispiel: Anstelle einer Zeile für 172.16.18.0/24 sollten Sie 256 Zeilen verwenden - eine Zeile für jede Adresse zwischen 172.16.18.0/32 und 172.16.18.255/32 (einschließlich).
>
> Die Spalte VPN ist optional und standardmäßig auf 0 festgelegt.  Wenn der Wert der VPN-Spalte auf 1 festgelegt ist, wird das durch diese Zeile dargestellte Subnetz vollständig erweitert, um allen IP-Adressen im Subnetz zu entsprechen.  Verwenden Sie dies sparsam und nur für VPN-Subnetze, da sich eine vollständige Erweiterung dieser Subnetze negativ auf die Abfragezeiten für Abfragen mit Gebäudedaten auswirken wird.

Zeigen Sie auf Balkendiagramme und Trendlinien im Bericht, um detaillierte Werte anzuzeigen. Der Bericht, der einen Fokus besitzt, zeigt das Aktionsmenü an: **Bearbeitung**, **Klonen**, **Löschen**, **Herunterladen** und **Exportieren**.



## <a name="query-filters"></a>Abfragefilter

Abfragefilter werden mithilfe des Abfrage-Editors in CQD implementiert. Diese Filter werden verwendet, um die Anzahl der von CQD zurückgegebenen Datensätze zu verringern, wodurch die Gesamtgröße und die Abfragezeiten des Berichts minimiert werden. Dies ist besonders hilfreich, wenn nicht verwaltete Netzwerke ausgefiltert werden sollen. Die in der folgenden Tabelle aufgelisteten Filter verwenden reguläre Ausdrücke (RegEx).


| Filter         | Beschreibung          | Beispiel für CQD-Abfragefilter      |
|----------------|----------------------|-------------------------------|
| Keine leeren Werte   | Einige Filter verfügen nicht über die Option zum Filtern nach leeren Werten. Wenn Sie leere Werte manuell filtern möchten, verwenden Sie den leeren Ausdruck, und legen Sie den Filter abhängig von Ihren Anforderungen auf "Equals" oder "Not Equals" fest.      | Second Building Name \<\> \^ \\ s\*\$                       |
| Häufig verwendete Subnetze ausschließen | Ohne eine gültige Gebäudedatei, um verwaltete von nicht verwalteten Netzwerken zu trennen, werden Heimnetzwerke in die Berichte aufgenommen. Diese Heimsubnetze sind außerhalb des Umfangs der Steuerung und können schnell aus einem Bericht ausgeschlossen werden. Häufig verwendete Subnetze laut der Definition in diesem Leitfaden sind 10.0.0.0, 192.168.1.0 und 192.168.0.0. | Zweites Subnetz \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Nur innere anzeigen  | Wird verwendet, um einen Bericht für verwaltete (interne) oder nicht verwaltete (externe) zu filtern. Die Vorlage für verwaltete CQD ist bereits mit diesen Filtern vorkonfiguriert.       | Zweiter innerhalb des Unternehmens = Intern        |

## <a name="report-filters"></a>Berichtsfilter

Verwenden Sie CQD-Berichtsfilter, um den Fokus Ihrer Untersuchungen zu verenten. Verwenden Sie Berichtsfilter, indem Sie dem gerenderten Bericht entweder im Abfrage-Editor oder direkt im Bericht einen Filter hinzufügen. Die folgenden Berichtsfilter werden in den [CQD-Vorlagen verwendet.](https://aka.ms/QERtemplates)


| Filter     | Beschreibung                            | Beispiel für CQD-Berichtsfilter         |
|------------|----------------------------------------|-----------------------------------|
| Monat      | Beginnen Sie zuerst mit dem Jahr und dann mit dem Monat. | 2017-10                           |
| Alphabetisch | Filtert nach alphabetischen Zeichen. | [a-z]                             |
| Numerisch    | Filtert nach allen numerischen Zeichen.    | [0-9]                             |
| Prozent | Filtert nach einem Prozentsatz.              | ([3-9]\\.)\|([3-9])\|([1-9][0-9]) |


### <a name="drill-down-filters"></a>Drilldownfilter

CQD-Berichte verfügen über mehrere Drilldownfilter, die leistungsfähige Tools sind, um den Fokus Ihrer Untersuchungen zur Anrufqualität zu verengungen. Wenn Sie ein Drilldownfeld auswählen, öffnet der Bericht automatisch die entsprechende Registerkarte und filtert den ausgewählten Wert. Wenn diese Registerkarte eigene Drilldownfelder enthält und eines ausgewählt ist, werden beide Filtersätze angewendet, wodurch sich der resultierende Datensatz schrittweise eindrilliert.

![Diagramm zur Veranschaulichung des Drilldownberichtsflusses](media/qerguide-image-drillthrureportflow.png)


#### <a name="adding-and-editing-drill-down-fields"></a>Hinzufügen und Bearbeiten von Drilldownfeldern

Beim Bearbeiten eines Berichts haben Sie die Möglichkeit, eigene Drilldownfelder mit dem Abfrage-Editor anzugeben.

Klicken Sie zunächst auf **...** für den Bericht, den Sie bearbeiten möchten, und wählen Sie dann **Bearbeiten aus.**

![Screenshot des Bearbeitens eines Drilldownfelds](media/qerguide-image-addeditdrilldownfields.png)

Wählen Sie in der Liste auf der linken Seite des Abfrage-Editors eine Dimension aus. Klicken Sie dann auf die Dropdownliste unter der Bezeichnung **Navigieren** nach, und wählen Sie die Registerkarte und die Erweiterungsgruppe aus, zu der diese Dimension einen Drilldown erstellen soll. Hinweis: Derzeit funktionieren Drilldownfunktionen nur, indem sie zu verschiedenen Registerkarten navigieren. Unterstützung für das Durcharbeiten zu einem bestimmten Expander wird später hinzugefügt. Klicken Sie schließlich auf **Schließen,** um Ihre Änderungen an der Dimension zu speichern, und klicken Sie dann auf **Speichern,** um den Abfrage-Editor zu speichern und zu schließen.

![Screenshot der Auswahl einer Dimension im Abfrage-Editor](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a>Filter mit mehrfacher Auswahl

Zusätzlich zu den Drilldownfunktionen unterstützt CQD auch das Angeben von Filtern mit mehreren Werten (ODER-Filter).

Um mehrere Filterwerte auszuwählen, fügen Sie dem Bericht zunächst einen neuen Filter hinzu. Klicken Sie neben der Bezeichnung Filter, geben Sie den Namen der zu **+** verwendende Dimension ein, und klicken Sie auf **Hinzufügen.** 

![Screenshot des Hinzufügens eines Mehrfachauswahlfilters](media/qerguide-image-addmultiselectfilter.png)

Klicken Sie dann auf **Suchen** (ein Lupensymbol neben dem neuen Filter). Es werden ein Textfeld und eine Reihe von Optionen angezeigt, einschließlich **"Alle** auswählen" und **"Umkehren".** Geben Sie einen Wert ein, und klicken Sie **neben** diesem Feld auf Suchen, um zu suchen. Alternativ lassen Sie das Textfeld leer, und klicken Sie auf **Suchen,** um die ersten 100 Optionen anzuzeigen.

```powershell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Beispiel:  

![Screenshot des Hinzufügens eines Abfragefilters](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a>Filter auf Dashboardebene
Bestimmte CQD-Berichte verfügen über Filter auf Dashboardebene, die das Filtern nach allgemeinen Parametern einfach machen. Diese Filter werden außerhalb der normalen Berichtsregisterkarten und direkt unter dem Produktfilter angezeigt, und sie gelten für alle Filter im Dashboard.

![Screenshot eines Dashboardfilters](media/qerguide-image-dashboardfilters.png)
```powershell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a>URL-Filter

CQD unterstützt das Hinzufügen von Filtern zur URL. Dadurch können Sie eine CQD-Abfrage ganz einfach freigeben oder mit einem Lesezeichen versehen. Sie können Parameter in der URL definieren, z. B. Trendmonat, Mandanten-ID oder Sprache. Sie können der URL auch Filter auf Produkt- oder Dashboardebene hinzufügen.
Das Ausschließen von Verbunddaten aus CQD-Berichten ist nützlich, wenn Sie verwaltete Gebäude oder Netzwerke sanieren, in denen Verbundendpunkte Ihre Berichte beeinflussen können.

Wenn Sie einen Filter hinzufügen möchten, fügen Sie folgendes an das Ende der URL an:

```console
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Beispiel:  

`https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]`

Um einer URL einen Filter auf Dashboardebene hinzuzufügen, muss dieser Filter in CQD entweder als Filter auf Produkt- oder Dashboardebene vorhanden sein. Fügen Sie der URL nach dem Trending Month und vor den URL-Parametern diese Filter hinzu:

`filter/DATA_MODEL_NAME|VALUE`

Wenn Sie z. B. einen Produktfilterwert von Microsoft Teams anwenden möchten, fügen Sie Folgendes hinzu:

`filter/[AllStreams].[Is%20Teams]|[True]`

Ihre gesamte URL sieht etwa so aus:

`https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]`

Um URL-Filter mit Mehrfachauswahlwerten anzuwenden, trennen Sie jeden Wert durch ein Pipezeichen (| ). Beispiel:

`filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]`

Wenn Sie einen ungültigen Namen oder Wert angeben, wird der URL-Filter nicht angewendet.


Sie können einen URL-Filter verwenden, um jeden Bericht für eine bestimmte Dimension zu filtern. Die am häufigsten verwendeten URL-Filter werden verwendet, um Berichte zu filtern, um die Telemetrie von Verbundteilnehmern auszuschließen oder sich nur auf Teams oder Skype for Business Online zu konzentrieren. Das Ausschließen von Verbunddaten aus CQD-Berichten ist nützlich, wenn Sie verwaltete Gebäude oder Netzwerke sanieren, in denen Verbundendpunkte Ihre Berichte beeinflussen können.

| Filter         | Beschreibung          | Beispiel für CQD-Abfragefilter      |
|----------------|----------------------|-------------------------------|
| Keine leeren Werte   | Einige Filter haben nicht die Möglichkeit, nach leeren Werten zu filtern. Wenn Sie leere Werte manuell filtern möchten, verwenden Sie den leeren Ausdruck, und legen Sie den Filter abhängig von Ihren Anforderungen auf "Equals" oder "Not Equals" fest.      | Second Building Name \<\> \^ \\ s\*\$                       |
| Häufig verwendete Subnetze ausschließen | Ohne eine gültige Gebäudedatei, um verwaltete von nicht verwalteten Netzwerken zu trennen, werden Heimnetzwerke in die Berichte aufgenommen. Diese Heimsubnetze liegen außerhalb des Bereichs des STEUERELEMENTs der IT und können schnell aus einem Bericht ausgeschlossen werden. Allgemeine Subnetze, wie in diesem Artikel definiert, sind 10.0.0.0, 192.168.1.0 und 192.168.0.0. | Zweites Subnetz \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Nur innere anzeigen  | Wird verwendet, um einen Bericht für verwaltete (interne) oder nicht verwaltete (externe) zu filtern. Die Vorlage für verwaltete CQD ist bereits mit diesen Filtern vorkonfiguriert.       | Zweiter innerhalb des Unternehmens = Intern        |


#### <a name="how-to-find-your-tenant-id"></a>So finden Sie Ihre Mandanten-ID

Die Mandanten-ID in CQD entspricht der Verzeichnis-ID in Azure. Wenn Sie Ihre Verzeichnis-ID nicht kennen, finden Sie sie im Azure-Portal:

1.  Melden Sie sich im Microsoft Azure-Portal an: <https://portal.azure.com>

2.  Wählen Sie **Azure Active Directory** aus.

3.  Wählen Sie unter **Verwalten** **Eigenschaften** aus. Ihre Mandanten-ID befindet sich im **Feld Verzeichnis-ID.**

Sie können Ihre Mandanten-ID auch mithilfe von PowerShell finden: 

```powershell
Login-AzureRmAccount
```

## <a name="comparing-teams-and-skype-for-business-cqd-data"></a>Vergleich von Teams und Skype for Business CQD-Daten

Selbst innerhalb der neuesten CQD (cqd.teams.microsoft.com) werden Unterschiede bei den Daten zwischen Teams und Skype for Business zu sehen sein. Einige Gründe:
- Unterschiede bei den Mechanismen zur Sicherstellung von Leistung und Zuverlässigkeit:
  - Teams verfügt über automatisches Erneutes Verbinden und schnelles Roaming. Skype for Business nicht.
  - Teams verfügt über eine dynamische Bandbreitenverwaltung. Skype for Business nicht.
- Unterschiede in [den IP-Adressbereichen](Office-365-URLs-IP-address-ranges.md) zwischen Teams und Skype for Business. Die Teams-IP-Bereiche sind neuer, was Konnektivitätsprobleme bei der Firewall verursachen könnte.

## <a name="open-cqd-from-the-skype-for-business-legacy-portal"></a>Öffnen von CQD über das Skype for Business-Legacyportal

![Symbol des Skype for Business-Logos ](media/sfb-logo-30x30.png) **Verwenden des Skype for Business-Legacyportals**

1. Melden Sie sich mit einem Administratorkonto bei Ihrer Office 365-Organisation an, und wählen Sie dann die Kachel **Admin** aus, um das Admin Center zu öffnen.

2. Wählen Sie im linken Bereich unter **Admin Center** die Option Microsoft **Teams aus,** um das Teams Admin Center zu öffnen.

3. Wählen Sie im Teams Admin Center im linken Bereich **Legacyportal** aus, wählen Sie **Extras** aus, und wählen Sie dann **Skype for Business Online Anrufqualitätsdashboard aus.**

   ![Screenshot: Auswählen des Anrufqualitätsdashboards](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. Melden Sie sich auf der nun geöffneten Seite mit Ihrem globalen Administratorkonto an, und geben Sie dann die Anmeldeinformationen für das Konto an, wenn Sie dazu aufgefordert werden.

Nach der ersten Anmeldung beginnt CQD mit dem Sammeln und Verarbeiten von Daten. 

> [!IMPORTANT]
> Ab Dezember 2019 können Sie weiterhin auf die ältere Version von CQD (cqd.lync.com) zugreifen, obwohl ihnen das Ältere Portal einen Link zum neuesten CQD (cqd.teams.microsoft.com) bietet. Schließlich wird die ältere Version von CQD außer Betrieb gesetzt. Ab dem 1. Juli 2020 zugegriffen die ältere Version von CQD auf Daten aus dem neuen CQD ( , und Sie können keine Gebäude- und Berichtsdaten mehr https://CQD.teams.microsoft.com) exportieren. Irgendwann Ende 2020 deaktivieren wir das alte CQD, und Sie können nicht mehr darauf zugreifen.


## <a name="related-topics"></a>Verwandte Themen

[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

[Was ist CQD?](CQD-what-is-call-quality-dashboard.md)

[Einrichten des Anrufqualitätsdashboards (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Hochladen von Mandanten- und Gebäudedaten](CQD-upload-tenant-building-data.md)

[Verwenden von CQD zum Verwalten der Anruf- und Besprechungsqualität](quality-of-experience-review-guide.md)

[In CQD verfügbare Dimensionen und Measures](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Streamklassifizierung in CQD](stream-classification-in-call-quality-dashboard.md)

[Verwenden von Power BI zum Analysieren von CQD-Daten](CQD-Power-BI-query-templates.md)