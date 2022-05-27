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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Erfahren Sie mehr über die Daten und Berichte, die im Microsoft Call Quality Dashboard (CQD) verfügbar sind.
ms.openlocfilehash: c30840ea4bf1de02572300044964211c5668056f
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675007"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a>Daten und Berichte im Anrufqualitätsdashboard (CQD)

Das Microsoft Call Quality Dashboard (CQD) verwendet einen Nahezu-Echtzeit-Datenfeed (NRT). Anrufdatensätze sind innerhalb von 30 Minuten nach Dem Ende eines Anrufs in CQD verfügbar. Anrufdatensätze aus der NRT-Pipeline sind nur einige Monate verfügbar, bevor sie aus dem Dataset entfernt werden.

## <a name="many-ways-to-access-cqd-data"></a>Viele Möglichkeiten für den Zugriff auf CQD-Daten

Sie können über verschiedene Möglichkeiten auf CQD-Daten zugreifen. Wählen Sie dasjenige aus, das Ihren Anforderungen am besten entspricht:

|&nbsp;|&nbsp;|
|---|---|
|Teams Admin Center [(https://admin.teams.microsoft.com)](https://admin.teams.microsoft.com)|CQD-Daten sind auf der Seite **"Benutzer**" im Teams Admin Center enthalten und zeigen die am häufigsten benötigten Daten in einem leicht lesbaren Format an. Sie können keine CQD-Daten anpassen, die Sie unter **"Benutzer**" finden.|
|CQD-Portal [(https://cqd.teams.microsoft.com)](https://cqd.teams.microsoft.com)|Robuste Zusammenfassung und detaillierte Berichte, die die meisten Anforderungen erfüllen, mit Drill-Through-Filterung. Sie können Berichte auch im CQD-Portal anpassen. <br><br>Rufen Sie zwei [CQD-Berichtsvorlagen](#import-the-cqd-report-templates) ab, mit denen Sie Daten im CQD-Portal analysieren können.|
|Power BI|Verwenden Sie direkte Abfragen, um Ihre CQD-Daten in Power BI mit [anpassbaren Power BI Vorlagen](CQD-Power-BI-query-templates.md) anzuzeigen. [Laden Sie Power BI Abfragevorlagen für CQD herunter](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).<br><br>Sie können [auch die REST-API verwenden, um über Power BI auf CQD-Daten zuzugreifen](/skypeforbusiness/management-tools/call-quality-dashboard/data-api). Verwenden Sie diese Methode, wenn Sie Ihre CQD-Daten herunterladen möchten, damit Sie offline daran arbeiten können. Der Vorteil dieser Methode ist eine bessere Leistung, insbesondere nützlich für große Datasets, die sich in Power BI befinden, wenn Sie online sind.|
|Graph-API|Greifen Sie selbst mithilfe der [Graph-API](/graph/api/resources/callrecords-api-overview) auf Anrufqualitätsdaten zu. Dies ist die komplexeste Methode, bietet Ihnen aber die meiste Kontrolle und Flexibilität bei der Analyse Ihrer Anrufqualitätsdaten. Wenn Sie es beispielsweise mit anderen Daten für Ihre Organisation verknüpfen müssen, können Sie die Graph-API verwenden, um ein Datenmodell zu erstellen und Anrufqualitätsdaten zu integrieren.|

## <a name="import-the-cqd-report-templates"></a>Importieren der CQD-Berichtsvorlagen

Laden Sie [zwei kuratierte CQD-Berichtsvorlagen](https://aka.ms/qertemplates) (Alle Netzwerke und verwaltete Netzwerke) herunter, um schnell mit CQD auf dem laufenden zu sein. Die Vorlage "Alle Netzwerke", die für die Arbeit mit einer Gebäudedatendatei optimiert ist, kann verwendet werden, während Sie auf die Erfassung und das Hochladen von Gebäudeinformationen in CQD hinarbeiten, wie im nächsten Abschnitt beschrieben.

**So importieren Sie die Vorlagen (. CQDX) in CQD**:

1. Wählen Sie im CQD im Menü oben auf der Seite die Option **"Detaillierte Berichte** " aus.

2. Wählen Sie im linken Bereich " **Importieren**" aus. Navigieren Sie zur ersten CQDX-Vorlage, und wählen Sie **"Öffnen**" aus.

3. Nachdem die Vorlage hochgeladen wurde, wird in einem Popupfenster die Meldung "Der Berichtimport war erfolgreich" angezeigt.

4. Wiederholen Sie die Schritte 2 und 3 für die zweite CQD-Vorlage.

   > [!NOTE]
   > Jeder Benutzer muss die CQD-Vorlagen in seine CQD-Instanz importieren.

## <a name="euii-data"></a>EUII-Daten

Aus Compliancegründen werden Endbenutzerdaten (EUII) (auch als personenbezogene Informationen oder PII bezeichnet) nur 28 Tage lang aufbewahrt. Da NRT-Daten die 28-Tage-Marke überschreiten, werden Felder, die EUII enthalten, gelöscht, was zu EUII-freien NRT-Daten führt. Felder, die EUII-Daten enthalten, sind:

- Vollständige IP-Adresse
- Mac-Adresse (Media Access Control)
- Standarddienstsatz-ID (BSSID)
- Session Initiation Protocol (SIP)-URI (nur Skype for Business)
- Benutzerprinzipalname (User Principal Name, UPN)
- Computerendpunktname
- Ausführliches Feedback des Benutzers
- Objekt-ID (die Active Directory-Objekt-ID des Benutzers des Endpunkts)
- Telefon Nummer

### <a name="admin-roles-with-and-without-euii-access"></a>Admin Rollen mit und ohne EUII-Zugriff

Diese [RBAC-Rollen](/azure/role-based-access-control/overview) haben **EUII-Zugriff** :

- Globale Admin
- Teams Service Admin
- Teams Communications Admin
- Teams-Kommunikationssupporttechniker
- Globaler Reader
- Skype for Business Admin

Diese RBAC-Rollen haben **keinen** EUII-Zugriff:

- Berichtsleser
- Supportfachmann für die Teams-Kommunikation

## <a name="date-controls"></a>Datumssteuerelemente

CQD unterstützt die folgenden Rolling Trend-Typen:

- 5 Tage
- 7 Tage
- 30 Tage
- 60 Tage
- 90 Tage

Der Parameter "URL Date" akzeptiert ein Feld "Day". Rolling-Day-Berichte verwenden Datumsangaben, die im YYYY-MM-DD-Format als letzten Tag des Trends angegeben sind. Der URL-Datumsparameter "00" gibt "heute" an.

|URL|Enddatum des Rolling Day Trend|
|:---|:---|
|<span>\<cqdv3>https:///spd/#/Dashboard/\<reportid>2019-02/</span>|Aktueller Tag vom Februar 2019|
|<span>\<cqdv3>https:///spd/#/Dashboard/\<reportid>2019-02-15/</span>|15. Februar 2019|
|<span>\<cqdv3>https:///spd/#/Dashboard/\<reportid>/00/</span>|Aktueller Tag|

Standardmäßig wird der aktuelle Tag des Monats als letzter Tag des Rolling Day Trend verwendet.

## <a name="data-available-in-cqd-reports"></a>In CQD-Berichten verfügbare Daten

Die Standardzusammenfassung und detaillierteN CQD-Berichte sind möglicherweise alles, was Sie zum Verwalten der Anrufqualität für Ihre Organisation benötigen. Bei Bedarf können Sie [benutzerdefinierte Berichte erstellen](#create-custom-detailed-reports).

Wenn Sie ihre CQD-Daten mithilfe von Power BI analysieren möchten, lesen [Sie "Verwenden Power BI zum Analysieren von CQD-Daten für Teams](CQD-Power-BI-query-templates.md)".

|Feature|Zusammenfassungsberichte|Detaillierte Berichte|
|:---|:---|:---|
|Anwendungsfreigabemetrik|Nein|Ja|
|Unterstützung von Kunden-Gebäudeinformationen|Ja|Ja|
|Support für Kundenendpunktinformationen|Nur in <span>cqd.teams.microsoft.com<span/>|Nur in <span>cqd.teams.microsoft.com<span/>|
|Drilldownanalyseunterstützung|Nein|Ja|
|Medienzuverlässigkeitsmetriken|Nein|Ja|
|Sofort einsatzbereite Berichte|Ja|Ja|
|Übersichtsberichte|Ja|Ja|
|Berichtssatz pro Nutzer|Nein|Ja|
|Anpassung des Berichtssatzes (Hinzufügen, Löschen, Ändern von Berichten)|Nein|Ja|
|Videobasierte Bildschirmfreigabe-Metriken|Nein|Ja|
|Videometriken|Nein|Ja|
|Verfügbare Datenmenge|Letzte 12 Monate|Letzte 12 Monate|
|Microsoft Teams-Daten|Ja|Ja|

### <a name="select-product-data-to-see-in-reports"></a>Produktdaten auswählen, die in Berichten angezeigt werden sollen

In der Zusammenfassung und Location-Enhanced Berichten können Sie die Dropdownliste "**Produktfilter**" verwenden, um alle Produktdaten, nur Microsoft Teams Daten oder nur Skype for Business Onlinedaten anzuzeigen.

> [!div class="mx-imgBorder"]
> ![Screenshot: Zeigt die Produktfilter-Steuerelementoptionen.](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)

In detaillierten Berichten können Sie die Dimension **"Ist Teams**" verwenden, um die Daten nach Microsoft Teams oder Skype for Business Onlinedaten zu filtern.

## <a name="summary-reports"></a>Zusammenfassungsberichte

Dies sind die Berichte, die beim ersten Anmelden bei CQD im CQD-Dashboard angezeigt werden. Sie bieten Ihnen einen Überblick über Qualitätstrends mit täglichen, monatlichen und Tabellenberichten, um Subnetze mit schlechter Qualität zu identifizieren.

|Registerkarte|Beschreibung|
|---|---|
|Anrufqualität insgesamt|Aggregat der anderen 3 Registerkarten.|
|Server – Client|Details der Datenströme zwischen Server- und Clientendpunkten.|
|Client – Client|Details der Datenströme zwischen zwei Clientendpunkten.|
|Sprachqualitäts-SLA|Informationen zu Anrufen, die im [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252) für Skype for Business Sprachqualität enthalten sind.|

### <a name="overall-call-quality-tab"></a>Registerkarte „Gesamtanrufqualität"

Verwenden Sie die Daten auf dieser Registerkarte, um den Status und die Trends der Anrufqualität basierend auf der Datenstromanzahl und den Prozentsätzen schlechter Qualität auszuwerten. Die Legende oben rechts zeigt an, welche Farbe und welche visuellen Elemente diese Kennzahlen darstellen.

> [!div class="mx-imgBorder"]
> ![Screenshot: Anzeigen der Registerkarte "Anrufqualität".](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)

Streams werden in drei Gruppen klassifiziert: "Gut", "Schlecht" und "Nicht klassifiziert". Es gibt auch  *berechnete Poor %*  -Werte, mit denen Sie das Verhältnis der als *"Schlecht"*  klassifizierten Datenströme zur Gesamtzahl der klassifizierten Datenströme erhalten. Da *Poor % = Poor streams/(Poor streams+ Good streams) \* 100*, the *Poor %* is unaffected by the presence of multiple *Unclassified*  streams. Informationen dazu, was einen Datenstrom als "schlecht" oder "gut" klassifiziert, finden Sie [unter "Datenstromklassifizierung" im Anrufqualitätsdashboard](stream-classification-in-call-quality-dashboard.md).

Verwenden Sie die Skala auf der linken Seite, um die Datenstromanzahlwerte zu messen.

> [!div class="mx-imgBorder"]
> ![Screenshot: Zeigt Datenstromanzahlwerte.](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)

Verwenden Sie die Skala rechts, um die Werte für „% Schlecht" zu ermitteln.

> [!div class="mx-imgBorder"]
> ![Screenshot: Zeigt schlechte % Werte.](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)

Sie erhalten auch die tatsächlichen numerischen Werte, indem Sie mit der Maus über eine Leiste fahren.

> [!NOTE]
> Das folgende Beispiel stammt aus einem kleinen Beispiel-Dataset, und die Werte sind für eine tatsächliche Bereitstellung nicht realistisch.

> [!div class="mx-imgBorder"]
> ![Screenshot: Zeigt die Maus, die für den Zugriff auf Daten verwendet wird.](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)

Das gesamte Datenstromvolume hilft zu bestimmen, wie relevant die berechneten Prozentsätze für "Schlecht" sind. Je kleiner das Volumen der Gesamtdatenströme ist, desto weniger zuverlässig sind die gemeldeten Poor-Prozentwerte.

### <a name="server-client-tab-and-client-client-tabs"></a>Registerkarten „Server-Client" und „Client-Client"

Diese beiden Registerkarten enthalten Details zu den Datenströmen, die in ihren Endpunkt-zu-Endpunkt-Szenarien stattfanden. Die Registerkarte Server-Client enthält vier reduzierbare Abschnitte, die vier Szenarien darstellen, unter denen Mediendatenströme fließen würden.

- Innen verkabelt
- Außen verkabelt
- WLAN innen
- WLAN außerhalb

Ebenso verfügt die Registerkarte Client-Client über fünf reduzierbare Abschnitte:

- Verkabelt innen – Verkabelt innen
- Verkabelt innen – Außen verkabelt
- Verkabelt außen – Verkabelt außen
- Verkabelt innen – WLAN innen
- Verkabelt innen – WLAN außen

#### <a name="inside-versus-outside"></a>Innen und Außen

CQD klassifiziert einen Datenstrom mithilfe von Gebäudeinformationen als  *"Innen*  " oder " *Außen*  ", sofern vorhanden. Die Endpunkte jedes Datenstroms sind einer Subnetzadresse zugeordnet. Wenn sich das Subnetz in der Liste der Subnetze befindet, die in den hochgeladenen Gebäudeinformationen als InsideCorp gekennzeichnet sind, wird es als *"Innen"* betrachtet. Wenn Gebäudeinformationen noch nicht hochgeladen wurden, klassifiziert Inside Test die Datenströme immer als *"Außen"*.

Der Inside Test für ein Server-Client-Szenario berücksichtigt nur den Clientendpunkt. Da sich Server aus der Perspektive des Benutzers stets außerhalb befinden, werden sie beim Test nicht berücksichtigt.

#### <a name="wired-versus-wifi"></a>Verkabelt im Vergleich zu WLAN

Wie die Namen angeben, basieren die Klassifizierungskriterien auf dem Typ der Clientverbindungen. Der Server ist immer verkabelt und wird nicht in die Berechnung einbezogen. Wenn in einem bestimmten Datenstrom einer der beiden Endpunkte mit einem WLAN-Netzwerk verbunden ist, klassifiziert CQD ihn als WLAN.

> [!NOTE]
> Wenn bei einem Datenstrom einer der beiden Endpunkte mit einem WLAN-Netzwerk verbunden ist, wird er im CQD als WLAN klassifiziert.

## <a name="tenant-data-information"></a>Mandantendateninformationen

Das Dashboard für CQD-Zusammenfassungsberichte enthält eine Seite **mit Mandantendaten Hochladen**, auf die sie zugreifen können, indem Sie im Menü "Einstellungen" in der oberen rechten Ecke Hochladen "**Mandantendaten**" auswählen. Diese Seite wird für Administratoren verwendet, um ihre eigenen Informationen hochzuladen, z. B.:

- Eine Karte mit IP-Adresse und geografischen Informationen.
- Eine Karte der einzelnen drahtlosen AP und ihrer MAC-Adresse.
- Eine Zuordnung von Endpunkt zu Endpunkt make/Model/Type usw.

Es wird empfohlen, Mandanten-, Gebäude- und Standortdaten hochzuladen, damit CQD diese Informationen in Ihre Berichte aufnehmen kann. Wenn Sie diese Daten noch nicht hochgeladen haben, lesen Sie [Hochladen Mandanten- und Gebäudedaten](CQD-upload-tenant-building-data.md).

## <a name="detailed-reports"></a>Detaillierte Berichte

|Name|Beschreibung|
|---|---|
|Location-Enhanced Berichte|Zeigt Qualitätstrends basierend auf Standortinformationen an. Dieser Bericht wird nur angezeigt, wenn Sie [Ihre Mandantendaten hochgeladen](CQD-upload-tenant-building-data.md) haben.|
|Zuverlässigkeitsberichte|Umfasst Audio-, Video-, Video-basierte Bildschirmfreigabe (VBSS) und App-Freigabeberichte.|
|Erfahrungsqualitätsberichte|Audioqualität und Zuverlässigkeit für alle Clients und Geräte, einschließlich Besprechungsräume. Diese Berichte sind eine "abgespeckte" Version der herunterladbaren [CQD-Vorlagen](https://aka.ms/QERtemplates), die sich auf Schlüsselbereiche für die Analyse der Audioqualität und -zuverlässigkeit konzentriert.|
|Qualitäts-Drilldownberichte|Drilldowns: Datum nach Region, Standorten, Subnetzen, Stunde und Benutzern.|
|Fehler-Drilldownberichte|Drilldowns: Datum nach Region, Standorten, Subnetzen, Stunde und Benutzern.|
|Meine Anrufberichte bewerten|Analysieren Sie Die Bewertungen von Benutzeranrufen nach Region, Standort oder Benutzer. Enthält ausführliches Feedback.|
|Helpdeskberichte|Helpdeskberichte betrachten Anruf- und Besprechungsdaten für einzelne Benutzer, Benutzergruppen oder alle Benutzer. Diese Berichte enthalten Gebäude- und EUII-Daten und helfen dabei, mögliche Systemprobleme basierend auf Netzwerkstandort, Konferenzdetails, Geräten oder Firmware zu identifizieren.|
|Clientversionsberichte|Zusammenfassung der Clientversion: Anzeigen der Anzahl der Sitzungen und Benutzer für jede Client-App-Version<br><br>Clientversion nach Benutzer: Anzeigen von Benutzernamen für jede Client-App-Version <br><br>Vordefinierte Filter für Produkt und Clienttyp helfen dabei, die Versionen auf bestimmte Clients zu konzentrieren.|
|Endpunktberichte|Zeigt die Anrufqualität nach Computerendpunkten (Computermodell und -modell) an. Diese Berichte enthalten Gebäudedaten, wenn Sie sie hochgeladen haben.|

## <a name="create-custom-detailed-reports"></a>Erstellen von benutzerdefinierten detaillierten Berichten

Wenn die Standard-CQD-Berichte Ihren Anforderungen nicht entsprechen, verwenden Sie diese Anweisungen, um einen benutzerdefinierten Bericht zu erstellen. Oder verwenden Sie (stand Januar 2020) [stattdessen Power BI für CQD-Berichte](cqd-power-bi-query-templates.md).

Wählen Sie in der Dropdownliste der Berichte am oberen Rand des Bildschirms, der bei der Anmeldung \(angezeigt wird, den Bildschirm "**Zusammenfassungsberichte**\)" aus, wählen Sie **"Detaillierte Berichte**" und dann "**Neu**" aus. Klicken Sie in einem Bericht auf **"Bearbeiten**", um die Abfrage-Editor anzuzeigen. Jeder Bericht basiert auf einer Abfrage im Cube. Ein Bericht ist die visuelle Darstellung der Daten, die von der jeweiligen Abfrage zurückgegeben werden. Die Abfrage-Editor hilft Ihnen beim Bearbeiten dieser Abfragen und der Anzeigeoptionen des Berichts.

> [!IMPORTANT]
> Der Netzwerkbereich kann zur Darstellung eines Supernetzes (einer Kombination aus mehreren Subnetzen mit einem einzelnen Routing-Präfix) verwendet werden. Alle neuen Gebäude-Uploads werden auf sich überlappende Bereiche hin untersucht. Wenn Sie zuvor eine Gebäudedatei hochgeladen haben, sollten Sie die aktuelle Datei herunterladen und erneut hochladen, um mögliche Überlappungen zu identifizieren und das Problem vor dem erneuten Hochladen zu beheben. Alle Überlappungen in zuvor hochgeladenen Dateien können zu falschen Zuordnungen von Subnetzen zu Gebäuden in den Berichten führen. Bestimmte VPN-Implementierungen melden die Subnetzinformationen nicht genau. Es wird empfohlen, beim Hinzufügen eines VPN-Subnetzes zur Gebäudedatei anstelle eines Eintrags für das Subnetz separate Einträge für jede Adresse im VPN-Subnetz als separates 32 Bit-Netzwerk hinzuzufügen. Jede Zeile kann die gleichen Gebäudemetadaten enthalten. Ein Beispiel: Anstelle einer Zeile für 172.16.18.0/24 sollten Sie 256 Zeilen verwenden - eine Zeile für jede Adresse zwischen 172.16.18.0/32 und 172.16.18.255/32 (einschließlich).
>
> Die VPN-Spalte ist optional und wird standardmäßig auf 0 festgelegt.  Wenn der Wert der VPN-Spalte auf 1 festgelegt ist, wird das durch diese Zeile dargestellte Subnetz vollständig erweitert, sodass es allen IP-Adressen innerhalb des Subnetzes entspricht.  Verwenden Sie dies nur sparsam und nur für VPN-Subnetze, da eine vollständige Erweiterung dieser Subnetze negative Auswirkungen auf die Abfragezeiten für Abfragen mit Gebäudedaten hat.

Zeigen Sie auf Balkendiagramme und Trendlinien im Bericht, um detaillierte Werte anzuzeigen. Der Bericht, der einen Fokus besitzt, zeigt das Aktionsmenü an: **Bearbeitung**, **Klonen**, **Löschen**, **Herunterladen** und **Exportieren**.

## <a name="query-filters"></a>Abfragefilter

Abfragefilter werden mithilfe des Abfrage-Editors in CQD implementiert. Diese Filter werden verwendet, um die Anzahl der vom CQD zurückgegebenen Datensätze zu verringern und so die Gesamtgröße und Abfragezeiten des Berichts zu minimieren. Dies ist besonders hilfreich, wenn nicht verwaltete Netzwerke ausgefiltert werden sollen. Die in der folgenden Tabelle aufgelisteten Filter verwenden reguläre Ausdrücke (RegEx).

|Filter|Beschreibung|Beispiel für CQD-Abfragefilter|
|---|---|---|
|Keine leeren Werte|Einige Filter haben nicht die Möglichkeit, nach leeren Werten zu filtern. Wenn Sie leere Werte manuell filtern möchten, verwenden Sie den leeren Ausdruck, und legen Sie den Filter abhängig von Ihren Anforderungen auf "Equals" oder "Not Equals" fest.|Second Building Name \<\> \^\\s\*\$|
|Häufig verwendete Subnetze ausschließen|Ohne eine gültige Gebäudedatei, um verwaltete von nicht verwalteten Netzwerken zu trennen, werden Heimnetzwerke in die Berichte aufgenommen. Diese Heimsubnetze liegen außerhalb des Bereichs der IT-Kontrolle und können schnell aus einem Bericht ausgeschlossen werden. Häufig verwendete Subnetze laut der Definition in diesem Leitfaden sind 10.0.0.0, 192.168.1.0 und 192.168.0.0.|Second Subnet \<\> 10.0.0.0 \|192.168.0.0 \|192.168.1.0|
|Nur innere anzeigen|Wird verwendet, um einen Bericht für verwaltete (interne) oder nicht verwaltete (externe) zu filtern. Die Vorlage für verwaltete CQD ist bereits mit diesen Filtern vorkonfiguriert.|Zweiter innerhalb des Unternehmens = Intern|

## <a name="report-filters"></a>Berichtsfilter

Verwenden Sie CQD-Berichtsfilter, um den Fokus Ihrer Untersuchungen einzuschränken. Verwenden Sie Berichtsfilter, indem Sie dem gerenderten Bericht entweder im Abfrage-Editor oder direkt im Bericht einen Filter hinzufügen. Die folgenden Berichtsfilter werden in allen [CQD-Vorlagen](https://aka.ms/QERtemplates) verwendet.

|Filter|Beschreibung|Beispiel für CQD-Berichtsfilter|
|---|---|---|
|Monat|Beginnen Sie zuerst mit dem Jahr und dann mit dem Monat.|2017-10|
|Alphabetisch|Filtert nach alphabetischen Zeichen.|[a-z]|
|Numerisch|Filtert nach allen numerischen Zeichen.|[0-9]|
|Prozent|Filtert nach einem Prozentsatz.|([3-9]\\.)\|([3-9])\|([1-9][0-9])|

### <a name="drill-down-filters"></a>Drilldownfilter

CQD-Berichte verfügen über mehrere Drilldownfilter, die leistungsstarke Tools sind, um den Fokus Ihrer Untersuchungen zur Anrufqualität einzuschränken. Wenn Sie ein Drilldownfeld auswählen, öffnet der Bericht automatisch die entsprechende Registerkarte und filtert nach dem ausgewählten Wert. Wenn diese Registerkarte über eigene Drilldownfelder verfügt und eines ausgewählt ist, werden beide Filtergruppen angewendet, wodurch das resultierende Dataset schrittweise eingegrenzt wird.

![Diagramm, das den Drilldownberichtsfluss veranschaulicht.](media/qerguide-image-drillthrureportflow.png)

#### <a name="adding-and-editing-drill-down-fields"></a>Hinzufügen und Bearbeiten von Drilldownfeldern

Beim Bearbeiten eines Berichts haben Sie die Möglichkeit, eigene Drilldownfelder mithilfe der Abfrage-Editor anzugeben.

Klicken Sie zunächst auf **...** für den Bericht, den Sie bearbeiten möchten, und wählen Sie dann **"Bearbeiten"** aus.

![Screenshot der Bearbeitung eines Drilldownfelds.](media/qerguide-image-addeditdrilldownfields.png)

Wählen Sie in der Liste auf der linken Seite des Abfrage-Editor eine Dimension aus. Klicken Sie dann auf die Dropdownliste unter der Beschriftung **"Navigieren zu"** , und wählen Sie die Registerkarte und die Erweiterungsgruppe aus, zu der diese Dimension führen soll. Hinweis: Drilldownfunktionen funktionieren derzeit nur, wenn Sie zu verschiedenen Registerkarten navigieren. Unterstützung für das Bohren bis zu einem bestimmten Expander wird später hinzugefügt. Klicken Sie abschließend auf **"Schließen**", um die Änderungen an der Dimension zu speichern, und klicken Sie dann auf **"Speichern**", um die Abfrage-Editor zu speichern und zu schließen.

![Screenshot der Auswahl einer Dimension im Abfrage-Editor.](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a>Mehrfachauswahlfilter

Zusätzlich zur Drilldownfunktion unterstützt CQD auch die Angabe von Filtern mit mehreren Werten (OR-Filter).

Um mehrere Filterwerte auszuwählen, fügen Sie zunächst einen neuen Filter zum Bericht hinzu. Klicken Sie **+** neben der **Beschriftung "Filter** ", geben Sie den Namen der zu verwendenden Dimension ein, und klicken Sie auf **"Hinzufügen"**.

![Screenshot des Hinzufügens eines Mehrfachauswahlfilters.](media/qerguide-image-addmultiselectfilter.png)

Klicken Sie dann auf **"Suchen** " (ein Lupensymbol neben dem neuen Filter). Es werden ein Textfeld und eine Reihe von Optionen angezeigt, einschließlich **"Alles auswählen"** und **"Umkehren"**. Geben Sie einen Wert ein, und klicken Sie auf **"Suchen** " neben diesem Feld, um zu suchen. Alternativ können Sie das Textfeld leer lassen und auf **"Suchen** " klicken, um bis zu den ersten 100 Optionen anzuzeigen.

```powershell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Beispiel:

![Screenshot des Hinzufügens eines Abfragefilters.](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a>Filter auf Dashboardebene

Bestimmte CQD-Berichte verfügen über Filter auf Dashboardebene, die das Filtern nach allgemeinen Parametern erleichtern. Diese Filter werden außerhalb der regulären Berichtsregisterkarten und direkt unter dem Produktfilter angezeigt und gelten für alle Filter im Dashboard.

![Screenshot eines Dashboardfilters.](media/qerguide-image-dashboardfilters.png)

```powershell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a>URL-Filter

CQD unterstützt das Hinzufügen von Filtern zur URL. Auf diese Weise können Sie eine CQD-Abfrage ganz einfach freigeben oder mit einem Lesezeichen versehen. Sie können Parameter in der URL definieren, z. B. Trendmonat, Mandanten-ID oder Sprache. Sie können der URL auch Filter auf Produkt- oder Dashboardebene hinzufügen.
Das Ausschließen von Verbunddaten aus CQD-Berichten ist nützlich, wenn Sie verwaltete Gebäude oder Netzwerke korrigieren, in denen Verbundendpunkte Ihre Berichte beeinflussen können.

Fügen Sie zum Hinzufügen eines Filters Folgendes an das Ende der URL an:

```console
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Beispiel:

`https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]`

Um einen Filter auf Dashboardebene zu einer URL hinzuzufügen, muss dieser Filter in CQD entweder als Filter auf Produkt- oder Dashboardebene vorhanden sein. Fügen Sie der URL nach dem Trendmonat und vor den URL-Parametern diese Filter hinzu:

`filter/DATA_MODEL_NAME|VALUE`

Um beispielsweise einen Produktfilterwert von Microsoft Teams anzuwenden, fügen Sie Folgendes hinzu:

`filter/[AllStreams].[Is%20Teams]|[True]`

Ihre gesamte URL würde ungefähr wie folgt aussehen:

`https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]`

Um URL-Filter mit Mehrfachauswahlwerten anzuwenden, trennen Sie jeden Wert durch ein Pipezeichen (|). Zum Beispiel: 

`filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]`

Wenn Sie einen ungültigen Namen oder Wert angeben, wird der URL-Filter nicht angewendet.

Sie können einen URL-Filter verwenden, um jeden Bericht für eine bestimmte Dimension zu filtern. Die am häufigsten verwendeten URL-Filter werden verwendet, um Berichte zu filtern, um telemetrische Partnerteilnehmer auszuschließen oder sich nur auf Teams oder Skype for Business Online zu konzentrieren. Das Ausschließen von Verbunddaten aus CQD-Berichten ist nützlich, wenn Sie verwaltete Gebäude oder Netzwerke korrigieren, in denen Verbundendpunkte Ihre Berichte beeinflussen können.

|Filter|Beschreibung|Beispiel für CQD-Abfragefilter|
|---|---|---|
|Keine leeren Werte|Einige Filter haben nicht die Möglichkeit, nach leeren Werten zu filtern. Wenn Sie leere Werte manuell filtern möchten, verwenden Sie den leeren Ausdruck, und legen Sie den Filter abhängig von Ihren Anforderungen auf "Equals" oder "Not Equals" fest.|Second Building Name \<\> \^\\s\*\$|
|Häufig verwendete Subnetze ausschließen|Ohne eine gültige Gebäudedatei, um verwaltete von nicht verwalteten Netzwerken zu trennen, werden Heimnetzwerke in die Berichte aufgenommen. Diese Heimsubnetze liegen außerhalb des Bereichs der IT-Kontrolle und können schnell aus einem Bericht ausgeschlossen werden. Allgemeine Subnetze, wie in diesem Artikel definiert, sind 10.0.0.0, 192.168.1.0 und 192.168.0.0.|Second Subnet \<\> 10.0.0.0 \|192.168.0.0 \|192.168.1.0|
|Nur innere anzeigen|Wird verwendet, um einen Bericht für verwaltete (interne) oder nicht verwaltete (externe) zu filtern. Die Vorlage für verwaltete CQD ist bereits mit diesen Filtern vorkonfiguriert.|Zweiter innerhalb des Unternehmens = Intern|

#### <a name="how-to-find-your-tenant-id"></a>So finden Sie Ihre Mandanten-ID

Die Mandanten-ID im CQD entspricht der Verzeichnis-ID in Azure. Wenn Sie Ihre Verzeichnis-ID nicht kennen, finden Sie sie im Azure-Portal:

1. Melden Sie sich im Microsoft Azure-Portal an: <https://portal.azure.com>

2. Wählen Sie **Azure Active Directory** aus.

3. Wählen Sie unter **Verwalten** **Eigenschaften** aus. Ihre Mandanten-ID befindet sich im **Feld "Verzeichnis-ID** ".

Sie können Ihre Mandanten-ID auch mithilfe von PowerShell finden:

```powershell
Login-AzureRmAccount
```

## <a name="comparing-teams-and-skype-for-business-cqd-data"></a>Vergleich von Teams- und Skype for Business CQD-Daten

Beim Überprüfen Ihrer Daten werden möglicherweise Unterschiede in den Daten zwischen Teams und Skype for Business angezeigt. Einige Gründe:

- Unterschiede bei den Mechanismen zur Gewährleistung von Leistung und Zuverlässigkeit:
  - Teams verfügt über eine automatische Wiederherstellung und schnelles Roaming. Skype for Business nicht.
  - Teams verfügt über eine dynamische Bandbreitenverwaltung. Skype for Business nicht.
- Unterschiede in [IP-Adressbereichen](Office-365-URLs-IP-address-ranges.md) zwischen Teams und Skype for Business. Die Teams IP-Bereiche sind neuer, was zu Verbindungsproblemen in der Firewall führen kann.

## <a name="related-topics"></a>Verwandte Themen

[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

[Was ist CQD?](CQD-what-is-call-quality-dashboard.md)

[Einrichten des Anrufqualitäts-Dashboards (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Hochladen von Mandanten- und Gebäudedaten](CQD-upload-tenant-building-data.md)

[Verwenden von CQD zum Verwalten der Anruf- und Besprechungsqualität](quality-of-experience-review-guide.md)

[In CQD verfügbare Dimensionen und Kennzahlen](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Streamklassifizierung in CQD](stream-classification-in-call-quality-dashboard.md)

[Verwenden von Power BI zum Analysieren von CQD-Daten](CQD-Power-BI-query-templates.md)
