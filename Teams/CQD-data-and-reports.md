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
description: Erfahren Sie mehr über die Daten und Berichte, die im Microsoft-Anrufqualitätsdashboard (CQD) verfügbar sind.
ms.openlocfilehash: 0f54b6c3c69d65b12aa248f7180dec3617273857
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014619"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a>Daten und Berichte im Anrufqualitätsdashboard (CQD)

Das Microsoft-Anrufqualitätsdashboard (CQD) verwendet einen NrT-Datenfeed (Near-Real-Time). Anrufdatensätze sind innerhalb von 30 Minuten nach Ende eines Anrufs im Anruf-AQD verfügbar. Anrufdatensätze aus der NRT-Pipeline sind nur einige Monate lang verfügbar, bevor sie aus dem Datensatz entfernt werden. 


## <a name="many-ways-to-access-cqd-data"></a>Viele Möglichkeiten für den Zugriff auf AQD-Daten

Sie können auf CQD-Daten über verschiedene Möglichkeiten zugreifen. Wählen Sie die Lösung aus, die Ihren Anforderungen am besten entspricht:

|&nbsp;|&nbsp;|
|---------|---------|
|Teams Admin Center [( https://admin.teams.microsoft.com) ](https://admin.teams.microsoft.com)    | CQD-Daten sind  auf der Seite Benutzer im Teams Admin Center enthalten, auf der die am häufigsten benötigten Daten in einem einfach zu lesenen Format angezeigt werden. Sie können keine AQD-Daten anpassen, die Sie unter Benutzer **finden.**  |
|CQD-Portal [( https://cqd.teams.microsoft.com) ](https://cqd.teams.microsoft.com)     | Stabile Zusammenfassung und detaillierte Berichte, die die meisten Anforderungen erfüllen, mit Drillthroughfiltern. Sie können Berichte auch im CQD-Portal anpassen. <br><br>Holen Sie sich [zwei Vorlagen für CQD-Berichte,](#import-the-cqd-report-templates) die Ihnen beim Analysieren von Daten im CQD-Portal helfen sollen.       |
|Power BI     | Verwenden Sie direkte Abfragen zum Anzeigen Ihrer AQD-Daten in Power BI mithilfe [anpassbarer Power BI-Vorlagen.](CQD-Power-BI-query-templates.md) [Laden Sie Power BI-Abfragevorlagen für das AQD herunter.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)<br><br>Sie können auch die REST-API verwenden, um über Power BI [auf AQD-Daten](/skypeforbusiness/management-tools/call-quality-dashboard/data-api) zu zugreifen. Verwenden Sie diese Methode, wenn Sie Ihre AQD-Daten herunterladen möchten, damit Sie offline damit arbeiten können. Der Vorteil dieser Methode ist eine bessere Leistung. Dies gilt besonders für große Datenmengen, die sich in Power BI abschneiden, wenn Sie online sind.       |
|Graph-API     | Greifen Sie mit der Graph-API selbst auf Daten zur [Anrufqualität zu.](/graph/api/resources/callrecords-api-overview?view=graph-rest-beta) Dies ist die komplexeste Methode, bietet Ihnen aber die größte Kontrolle und Flexibilität bei der Analyse der Daten zur Anrufqualität. Wenn Sie sie beispielsweise mit anderen Daten für Ihre Organisation verbinden müssen, können Sie die Graph-API verwenden, um ein Datenmodell zu erstellen und Daten zur Anrufqualität zu integrieren.        |

## <a name="import-the-cqd-report-templates"></a>Importieren der Vorlagen für CQD-Berichte

Laden [Sie zwei kuratierte Vorlagen für CQD-Berichte](https://aka.ms/qertemplates) (Alle Netzwerke und Verwaltete Netzwerke) herunter, damit Sie sich schnell mit dem AQD schnell auf den Weg machen können. Die Vorlage "Alle Netzwerke", die für die Arbeit mit einer Gebäudedatendatei optimiert ist, kann verwendet werden, während Sie auf die Erfassung und das Hochladen von Gebäudeinformationen in CQD hinarbeiten, wie im nächsten Abschnitt beschrieben.

**So importieren Sie die Vorlagen (. CQDX) in CQD**

1. Wählen Sie im AQD **im** Menü oben auf der Seite Detaillierte Berichte aus.

2. Wählen Sie im linken Bereich Importieren **aus.** Navigieren Sie zur ersten CQDX-Vorlage, und wählen Sie **Öffnen aus.**

3. Nachdem die Vorlage hochgeladen wurde, wird in einem Popupfenster die Meldung "Berichtsimport war erfolgreich" angezeigt. 

4. Wiederholen Sie die Schritte 2 und 3 für die zweite CQD-Vorlage.

   > [!NOTE]
   > Jeder Benutzer muss die CQD-Vorlagen in seine AQD-Instanz importieren. 



## <a name="euii-data"></a>EUII-Daten

Aus Konformitätsgründen werden Endbenutzerdaten (EUII) (auch als personenbezogene Informationen oder PII bezeichnet) nur 28 Tage lang aufbewahrt. Wenn NRT-Daten die 28-Tage-Marke überschritten haben, werden Felder, die EUII enthalten, entfernt, was zu NRT-Daten ohne EUII führt. Felder, die EUII-Daten enthalten, sind:

- Vollständige IP-Adresse
- Adresse der Medienzugriffssteuerung (MAC)
- Basic Service Set Identifier (BSSID)
- SIP-URI (Session Initiation Protocol) (nur Skype for Business)
- Benutzerprinzipalname (User Principal Name, UPN)
- Name des Computerendpunkts
- Feedback zur Ausführlichkeit der Benutzer
- Objekt-ID (die Active Directory-Objekt-ID des Benutzers des Endpunkts)

### <a name="admin-roles-with-and-without-euii-access"></a>Administratorrollen mit und ohne EUII-Zugriff

Diese [RBAC-Rollen](/azure/role-based-access-control/overview) **haben** EUII-Zugriff:
- Globaler Administrator
- Teams-Dienstadministrator
- Teams Communications Admin
- Teams-Kommunikationssupporttechniker
- Global Reader
- Skype for Business-Administrator

Diese RBAC-Rollen **haben keinen** EUII-Zugriff:
- Leser für Berichte
- Supportfachmann für die Teams-Kommunikation


## <a name="date-controls"></a>Datumssteuerelemente

Das CQD unterstützt die folgenden Rolltrendtypen:

- 5 Tage
- 7 Tage
- 30 Tage
- 60 Tage
- 90 Tage

Der PARAMETER URL Date akzeptiert ein Feld "Day". In Berichten im Fortlaufenden Tag werden Datumsangaben verwendet, die im Format JJJJ-MM-TT als letzter Tag des Trends angegeben wurden. Der URL Date-Parameter "00" gibt "heute" an.

|URL| Enddatum des Rolltage-Trends|
|:---|:---|
|<span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /2019-02/</span>   |Aktueller Tag im Februar 2019|
|<span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /2019-02-15/</span>|15. Februar 2019|
|<span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /00/</span>        |Aktueller Tag|
|||

Standardmäßig wird der aktuelle Tag des Monats als letzter Tag des Rolltage-Trends verwendet.


## <a name="data-available-in-cqd-reports"></a>In AQD-Berichten verfügbare Daten

Die standardmäßigen Zusammenfassungs- und detaillierten CQD-Berichte sind möglicherweise alles, was Sie zum Verwalten der Anrufqualität für Ihre Organisation benötigen. Bei Bedarf können Sie benutzerdefinierte [Berichte erstellen.](#create-custom-detailed-reports) 

Wenn Sie Power BI zum Analysieren Ihrer AQD-Daten verwenden möchten, lesen Sie Verwenden von Power BI zum Analysieren von [CQD-Daten für Teams.](CQD-Power-BI-query-templates.md)

|Feature|Zusammenfassungsberichte|Detaillierte Berichte|
|:--- |:--- |:--- |
|Anwendungsfreigabemetrik | Nein | Ja |
|Unterstützung von Kunden-Gebäudeinformationen | Ja | Ja |
|Unterstützung von Kundenendpunktinformationen | Nur in <span> cqd.teams.microsoft.com<span/> | Nur in <span> cqd.teams.microsoft.com<span/> |
|Drilldown-Analyseunterstützung   | Nein   | Ja   |
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


 
### <a name="select-product-data-to-see-in-reports"></a>Produktdaten auswählen, die in Berichten zu sehen sind

In den Zusammenfassungs- und Location-Enhanced-Berichten  können Sie die Dropdownliste Produktfilter verwenden, um alle Produktdaten, nur Microsoft Teams-Daten oder nur Skype for Business Online-Daten anzeigen.

> [!div class="mx-imgBorder"]
> ![Screenshot: Zeigt die Optionen des Produktfilter-Steuerelements.](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
In detaillierten Berichten können Sie die Daten mithilfe der Dimension Ist **Teams** nach Microsoft Teams- oder Skype for Business Online-Daten filtern.

## <a name="summary-reports"></a>Zusammenfassungsberichte

Dies sind die Berichte, die im CQD-Dashboard angezeigt werden, wenn Sie sich zum ersten Mal beim CQD anmelden. Sie bieten Ihnen mit täglichen, monatlichen und Tabellenberichten einen Blick auf die Qualitätstrends, um die Identifizierung von Subnetzen zu unterstützen, die eine schlechte Qualität haben. 

| TAB | Beschreibung |
|---------|---------|
|Allgemeine Anrufqualität     | Aggregat der anderen drei Registerkarten.       |
|Server – Client     |Details der Datenströme zwischen Server- und Clientendpunkten.        |
|Client – Client     |Details der Datenströme zwischen zwei Clientendpunkten.        |
|SLA zur Sprachqualität     |Informationen zu Anrufen, die in der SLA zur Sprachqualität in Skype for Business [enthalten sind.](https://go.microsoft.com/fwlink/p/?linkid=846252)        |

### <a name="overall-call-quality-tab"></a>Registerkarte „Gesamtanrufqualität"

Verwenden Sie die Daten auf dieser Registerkarte, um den Status und die Trends der Anrufqualität basierend auf der Datenstromanzahl und schlechte Prozentzahlen auszuwerten. Die Legende oben rechts zeigt an, welche Farbe und welche visuellen Elemente diese Kennzahlen darstellen.

> [!div class="mx-imgBorder"]
> ![Screenshot: Anzeigen der Registerkarte "Anrufqualität".](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
Datenströme werden in drei Gruppen klassifiziert: "Gut", "Schlecht" und "Nicht klassifiziert". Es gibt auch berechnete  *Werte des Werts "Poor %",*  die Ihnen das Verhältnis von Datenströmen, die als *"Schlecht"*  klassifiziert wurden, zur gesamtzahl klassifizierten Datenstromanzahl geben. Da *Poor % = Poor streams/ (Poor streams+ Good streams) * 100*, ist die Poor *%*  nicht vom Vorhandensein mehrerer *Nicht klassifizierter*  Datenströme betroffen. Informationen zur Klassifizierung eines Datenstroms als "schlecht" oder "gut" finden Sie unter Streamklassifizierung [im Anrufqualitätsdashboard.](stream-classification-in-call-quality-dashboard.md)
  
Verwenden Sie die Skala links, um die Datenstromanzahlswerte zu messen.

> [!div class="mx-imgBorder"]
> ![Screenshot: Zeigt Werte für die Datenstromanzahl.](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Verwenden Sie die Skala rechts, um die Werte für „% Schlecht" zu ermitteln.

> [!div class="mx-imgBorder"]
> ![Screenshot: Zeigt schlechte %-Werte.](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
Sie erhalten auch die tatsächlichen numerischen Werte, indem Sie mit der Maus über eine Leiste fahren.
  
> [!NOTE]
> Das folgende Beispiel stammt aus einem kleinen Beispiel-Dataset, und die Werte sind für eine tatsächliche Bereitstellung nicht realistisch.

> [!div class="mx-imgBorder"]
> ![Screenshot: Zeigt die Maus, die für den Zugriff auf Daten verwendet wird.](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
Anhand des gesamten Datenstromvolumens kann ermittelt werden, wie relevant die berechneten Prozentsätze für "Schlecht" sind. Je kleiner das Volumen der gesamten Datenströme ist, desto unvertrauenswürdiger sind die im Bericht angegebenen Werte für die Prozentsätze für "Schlecht".
  
### <a name="server-client-tab-and-client-client-tabs"></a>Registerkarten „Server-Client" und „Client-Client"

Diese beiden Registerkarten enthalten Details zu den Datenströmen, die in ihren jeweiligen Endpunkt-zu-Endpunkt-Szenarien stattgefunden haben. Die registerkarte Server-Client verfügt über vier reduzierbare Abschnitte, die vier Szenarien darstellen, in denen Mediendatenströme fließen würden.
  
- Innen verkabelt
- Außen verkabelt
- WLAN Innen
- WLAN außen

Ebenso enthält die Registerkarte Client-Client fünf reduzierbare Abschnitte:

- Innen verkabelt – Innen verkabelt
- Innen verkabelt – Außen verkabelt
- Außen verkabelt – Außen verkabelt
- Innen verkabelt – WLAN innen
- Innen verkabelt – WLAN außen

#### <a name="inside-versus-outside"></a>Innen im Vergleich zu Außen

Das CQD bezeichnet einen  Datenstrom mithilfe von Gebäudeinformationen als "Innen" oder "Außen", falls er vorhanden ist.  Die Endpunkte jedes Datenstroms sind einer Subnetzadresse zugeordnet. Wenn sich das Subnetz in der Liste der Subnetze befindet, die in den hochgeladenen Gebäudeinformationen mit InsideCorp gekennzeichnet sind, wird es als *Inside betrachtet.* Wenn die Gebäudeinformationen noch nicht hochgeladen wurden, werden die Datenströme beim Innentest immer als *Außen einklassig.* 

Beim Innentest für ein Server-Client wird nur der Clientendpunkt berücksichtigt. Da sich Server aus der Perspektive des Benutzers stets außerhalb befinden, werden sie beim Test nicht berücksichtigt.
  
#### <a name="wired-versus-wifi"></a>Verkabelt im Vergleich zu WLAN

Wie die Namen bereits angeben, basieren die Klassifizierungskriterien auf dem Typ der Clientverbindungen. Der Server ist immer verkabelt und wird nicht in die Berechnung einbezogen. Wenn in einem bestimmten Datenstrom einer der beiden Endpunkte mit einem WLAN-Netzwerk verbunden ist, wird er vom CQD als WLAN klassifizierung.

> [!NOTE]
> Wenn bei einem Datenstrom einer der beiden Endpunkte mit einem WLAN-Netzwerk verbunden ist, wird er im CQD als WLAN klassifiziert.
  
  
## <a name="tenant-data-information"></a>Informationen zu Mandantendaten

Das Dashboard für AQD-Zusammenfassungsberichte enthält eine  Seite Upload von Mandantendaten, auf die Sie zugreifen können, indem Sie in der oberen rechten Ecke im Einstellungsmenü die Option Upload von Mandantendaten auswählen.  Diese Seite wird für Administratoren verwendet, um ihre eigenen Informationen hochzuladen, z. B.:

- Eine Karte mit IP-Adressen und geografischen Informationen.
- Eine Karte der einzelnen Drahtlos-AP und ihrer MAC-Adresse.
- Eine Karte des Endpunkts zum Endpunkt Erstellen/Modell/Typ usw.
  
Es wird empfohlen, die Mandanten-, Gebäude- und Standortdaten hochzuladen, damit das AQD diese Informationen in Ihre Berichte einmingen kann. Wenn Sie diese Daten noch nicht hochgeladen haben, lesen Sie Hochladen von [Mandanten- und Gebäudedaten.](CQD-upload-tenant-building-data.md) 


## <a name="detailed-reports"></a>Detaillierte Berichte

| Name | Beschreibung |
|---------|---------|
|Location-Enhanced berichte     |Zeigt Qualitätstrends auf der Grundlage von Standortinformationen an. Dieser Bericht wird nur angezeigt, wenn Sie [Ihre Mandantendaten hochgeladen haben.](CQD-upload-tenant-building-data.md)        |
|Zuverlässigkeitsberichte     |Umfasst Audio, Video, videobasierte Bildschirmfreigabe (VBSS) und Berichte zur App-Freigabe.        |
|Berichte zur Qualität der Benutzererfahrung     |Audioqualität und Zuverlässigkeit für alle Clients und Geräte, einschließlich Besprechungsräume. Bei diesen Berichten handelt es sich um eine "schlankere" Version der herunterladbaren [CQD-Vorlagen,](https://aka.ms/QERtemplates)wobei der Schwerpunkt auf den Schlüsselbereichen für die Analyse der Audioqualität und Zuverlässigkeit liegen soll.         |
|Qualitätsdrilldownberichte     | Drilldowns: Datum nach Region, Standorten, Subnetzen, Stunden und Benutzern.        |
|Fehlerdrilldownberichte     | Drilldowns: Datum nach Region, Standorten, Subnetzen, Stunden und Benutzern.        |
|Bewerten von Meinen Anrufberichten     |Analysieren Sie die Benutzeranrufbewertungen nach Region, Standort oder Benutzer. Enthält ausführliches Feedback.         |
|Helpdeskberichte     |Helpdeskberichte sehen Anruf- und Besprechungsdaten für einzelne Benutzer, Benutzergruppen oder alle Benutzer. Durch das Einbinden von Gebäude- und EUII-Daten helfen diese Berichte dabei, mögliche Systemprobleme basierend auf dem Netzwerkstandort, Konferenzdetails, Geräten oder Firmware zu identifizieren.         |
|Clientversionsberichte     |Clientversionszusammenfassung: Anzeigen der Anzahl der Sitzungen und Benutzer für jede Client-App-Version<br><br>Clientversion nach Benutzer: Anzeigen der Benutzernamen für jede Client-App-Version <br><br>Vordefinierte Filter für "Produkt- und Clienttyp" helfen dabei, die Versionen auf bestimmte Clients zu konzentrieren.         |
|Endpunktberichte     |Zeigt die Anrufqualität nach Endpunkten des Computers an (Computer erstellen und Modell). Diese Berichte enthalten Gebäudedaten, wenn Sie sie hochgeladen haben.         |


## <a name="create-custom-detailed-reports"></a>Erstellen von benutzerdefinierten detaillierten Berichten

Wenn die standardmäßigen AQD-Berichte nicht Ihren Anforderungen entsprechen, erstellen Sie mithilfe dieser Anweisungen einen benutzerdefinierten Bericht. Oder verwenden Sie (ab Januar 2020) Power BI [für AQD-Berichte. ](cqd-power-bi-query-templates.md)

Wählen Sie in der pull-down-Liste der Berichte am oberen Rand des Bildschirms, die bei der Anmeldung angezeigt wird, Bildschirm Zusammenfassungsberichte die Option Detaillierte Berichte und \( dann Neu  \) **aus.**  Klicken **Sie auf** In einem Bericht bearbeiten, um den Abfrage-Editor zu sehen. Jeder Bericht basiert auf einer Abfrage im Cube. Ein Bericht ist die visuelle Darstellung der Daten, die von der jeweiligen Abfrage zurückgegeben werden. Der Abfrage-Editor hilft Ihnen beim Bearbeiten dieser Abfragen und der Anzeigeoptionen des Berichts.

> [!IMPORTANT]
> Der Netzwerkbereich kann zur Darstellung eines Supernetzes (einer Kombination aus mehreren Subnetzen mit einem einzelnen Routing-Präfix) verwendet werden. Alle neuen Gebäude-Uploads werden auf sich überlappende Bereiche hin untersucht. Wenn Sie zuvor eine Gebäudedatei hochgeladen haben, sollten Sie die aktuelle Datei herunterladen und erneut hochladen, um mögliche Überlappungen zu identifizieren und das Problem vor dem erneuten Hochladen zu beheben. Alle Überlappungen in zuvor hochgeladenen Dateien können zu falschen Zuordnungen von Subnetzen zu Gebäuden in den Berichten führen. Bestimmte VPN-Implementierungen melden die Subnetzinformationen nicht genau. Es wird empfohlen, beim Hinzufügen eines VPN-Subnetzes zur Gebäudedatei anstelle eines Eintrags für das Subnetz separate Einträge für jede Adresse im VPN-Subnetz als separates 32 Bit-Netzwerk hinzuzufügen. Jede Zeile kann die gleichen Gebäudemetadaten enthalten. Ein Beispiel: Anstelle einer Zeile für 172.16.18.0/24 sollten Sie 256 Zeilen verwenden - eine Zeile für jede Adresse zwischen 172.16.18.0/32 und 172.16.18.255/32 (einschließlich).
>
> Die VPN-Spalte ist optional und standardmäßig auf 0 festgelegt.  Wenn der Wert der VPN-Spalte auf 1 festgelegt ist, wird das Subnetz, das durch diese Zeile dargestellt wird, vollständig erweitert, um allen IP-Adressen innerhalb des Subnetzes zu entsprechen.  Verwenden Sie diese Angaben sparsam und nur für VPN-Subnetze, da sich eine vollständige Erweiterung dieser Subnetze negativ auf die Abfragezeiten für Abfragen mit Gebäudedaten auswirken wird.

Zeigen Sie auf Balkendiagramme und Trendlinien im Bericht, um detaillierte Werte anzuzeigen. Der Bericht, der einen Fokus besitzt, zeigt das Aktionsmenü an: **Bearbeitung**, **Klonen**, **Löschen**, **Herunterladen** und **Exportieren**.



## <a name="query-filters"></a>Abfragefilter

Abfragefilter werden mithilfe des Abfrage-Editors in CQD implementiert. Diese Filter werden verwendet, um die Anzahl der von CQD zurückgegebenen Datensätze zu verringern, wodurch die Gesamtgröße und die Abfragezeiten des Berichts minimiert werden. Dies ist besonders hilfreich, wenn nicht verwaltete Netzwerke ausgefiltert werden sollen. Die in der folgenden Tabelle aufgelisteten Filter verwenden reguläre Ausdrücke (RegEx).


| Filter         | Beschreibung          | Beispiel für CQD-Abfragefilter      |
|----------------|----------------------|-------------------------------|
| Keine leeren Werte   | Einige Filter verfügen nicht über die Option zum Filtern nach leeren Werten. Wenn Sie leere Werte manuell filtern möchten, verwenden Sie den leeren Ausdruck, und legen Sie den Filter abhängig von Ihren Anforderungen auf "Equals" oder "Not Equals" fest.      | Second Building Name \<\> \^ \\ s\*\$                       |
| Häufig verwendete Subnetze ausschließen | Ohne eine gültige Gebäudedatei, um verwaltete von nicht verwalteten Netzwerken zu trennen, werden Heimnetzwerke in die Berichte aufgenommen. Diese Heimsubnetze sind außerhalb des Umfangs der Steuerung und können schnell aus einem Bericht ausgeschlossen werden. Häufig verwendete Subnetze laut der Definition in diesem Leitfaden sind 10.0.0.0, 192.168.1.0 und 192.168.0.0. | Zweites Subnetz \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Nur innere anzeigen  | Wird verwendet, um einen Bericht für verwaltete (interne) oder nicht verwaltete (externe) zu filtern. Die Vorlage für verwaltete CQD ist bereits mit diesen Filtern vorkonfiguriert.       | Zweiter innerhalb des Unternehmens = Intern        |

## <a name="report-filters"></a>Berichtsfilter

Verwenden Sie Filter für den CQD-Bericht, um den Schwerpunkt Ihrer Untersuchungen zu konzentrieren. Verwenden Sie Berichtsfilter, indem Sie dem gerenderten Bericht entweder im Abfrage-Editor oder direkt im Bericht einen Filter hinzufügen. Die folgenden Berichtsfilter werden in allen [CQD-Vorlagen verwendet.](https://aka.ms/QERtemplates)


| Filter     | Beschreibung                            | Beispiel für CQD-Berichtsfilter         |
|------------|----------------------------------------|-----------------------------------|
| Monat      | Beginnen Sie zuerst mit dem Jahr und dann mit dem Monat. | 2017-10                           |
| Alphabetisch | Filtert nach alphabetischen Zeichen. | [a-z]                             |
| Numerisch    | Filtert nach allen numerischen Zeichen.    | [0-9]                             |
| Prozent | Filtert nach einem Prozentsatz.              | ([3-9]\\.)\|([3-9])\|([1-9][0-9]) |


### <a name="drill-down-filters"></a>Drilldownfilter

CQD reports feature several drill-down filters, which are powerful tools for narrowing the focus of your call-quality investigations. Wenn Sie ein Drilldownfeld auswählen, öffnet der Bericht automatisch die entsprechende Registerkarte und filtert nach dem ausgewählten Wert. Wenn diese Registerkarte eigene Drilldownfelder enthält und eins ausgewählt ist, werden beide Filtersätze angewendet, wodurch das resultierende Datenset zunehmend einfgt wird.

![Diagramm zur Veranschaulichung des Drilldownberichtsflusses](media/qerguide-image-drillthrureportflow.png)


#### <a name="adding-and-editing-drill-down-fields"></a>Hinzufügen und Bearbeiten von Drilldownfeldern

Beim Bearbeiten eines Berichts haben Sie die Möglichkeit, eigene Drilldownfelder mithilfe des Abfrage-Editors anzugeben.

Klicken Sie zunächst auf **...** für den Bericht, den Sie bearbeiten möchten, und wählen Sie dann **Bearbeiten aus.**

![Screenshot der Bearbeitung eines Drilldownfelds](media/qerguide-image-addeditdrilldownfields.png)

Wählen Sie in der Liste auf der linken Seite des Abfrage-Editors eine Dimension aus. Klicken Sie dann auf das Dropdown unter der Beschriftung Navigieren **nach,** und wählen Sie die Registerkarte und die Erweiterungsgruppe aus, zu der die Dimension einen Drilldown anzeigen soll. Hinweis: Zurzeit können Drilldownfunktionen nur durch Navigieren zu verschiedenen Registerkarten verwendet werden. Unterstützung für das Drill through to a specific expander wird später hinzugefügt. Klicken Sie abschließend **auf Schließen,** um Ihre  Änderungen an der Dimension zu speichern, und klicken Sie dann auf Speichern, um den Abfrage-Editor zu speichern und zu schließen.

![Screenshot der Auswahl einer Dimension im Abfrage-Editor](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a>Mehrfachauswahlfilter

Zusätzlich zur Drilldownfunktion unterstützt das AQD auch das Angeben von Filtern mit mehreren Werten (ODER-Filtern).

Um mehrere Filterwerte auszuwählen, beginnen Sie, indem Sie dem Bericht einen neuen Filter hinzufügen. Klicken **+** Sie neben der Filterbeschriftung, geben Sie den Namen der zu verwendende Dimension ein, und klicken Sie auf **Hinzufügen.** 

![Screenshot: Hinzufügen eines Mehrfachauswahlfilters](media/qerguide-image-addmultiselectfilter.png)

Klicken Sie dann **auf Suchen** (ein Lupensymbol neben dem neuen Filter). Es werden ein Textfeld und eine Reihe von Optionen angezeigt, einschließlich Alles auswählen **und** **Umkehren.** Geben Sie einen Wert ein, und klicken **Sie neben diesem** Feld auf Suchen, um zu suchen. Alternativ können Sie das Textfeld leer lassen und auf **Suchen klicken,** um bis zu den ersten 100 Optionen anzuzeigen.

```powershell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Beispiel:  

![Screenshot zum Hinzufügen eines Abfragefilters](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a>Filter auf Dashboardebene
Bestimmte AQD-Berichte enthalten Filter auf Dashboardebene, die das Filtern nach allgemeinen Parametern einfacher machen. Diese Filter werden außerhalb der normalen Berichtsregisterkarten und direkt unter dem Filter Produkt angezeigt und gelten für alle Filter im Dashboard.

![Screenshot eines Dashboardfilters](media/qerguide-image-dashboardfilters.png)
```powershell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a>URL-Filter

Das CQD unterstützt das Hinzufügen von Filtern zur URL. Dies erleichtert die Freigabe oder Textmarke für eine AQD-Abfrage. Sie können Parameter in der URL definieren, z. B. Trendmonat, Mandanten-ID oder Sprache. Sie können der URL auch Filter auf Produkt- oder Dashboardebene hinzufügen.
Das Ausschließen von Verbunddaten aus AQD-Berichten ist nützlich, wenn Sie verwaltete Gebäude oder Netzwerke sanieren, in denen Verbundendpunkte sich auf Ihre Berichte möglicherweise beeinflussen können.

Um einen Filter hinzuzufügen, fügen Sie Folgendes an das Ende der URL an:

```console
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Beispiel:  

`https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]`

Wenn Sie einer URL einen Filter auf Dashboardebene hinzufügen möchten, muss dieser Filter im AQD als Filter auf Produkt- oder Dashboardebene vorhanden sein. Fügen Sie der URL nach dem Trendmonat und vor den URL-Parametern die folgenden Filter hinzu:

`filter/DATA_MODEL_NAME|VALUE`

Wenn Sie z. B. einen Produktfilterwert von Microsoft Teams anwenden möchten, fügen Sie Folgendes hinzu:

`filter/[AllStreams].[Is%20Teams]|[True]`

Ihre gesamte URL würde etwa so aussehen:

`https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]`

Zum Anwenden von URL-Filtern mit Mehrfachauswahlwerten trennen Sie jeden Wert durch ein Pipe (|) Zeichen. Zum Beispiel: 

`filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]`

Wenn Sie einen ungültigen Namen oder Wert angeben, wird der URL-Filter nicht angewendet.


Sie können einen URL-Filter verwenden, um jeden Bericht für eine bestimmte Dimension zu filtern. Die am häufigsten verwendeten URL-Filter werden zum Filtern von Berichten verwendet, um Telemetriedaten von Partnerteilnehmern auszuschließen oder sich nur auf Teams oder Skype for Business Online zu konzentrieren. Das Ausschließen von Verbunddaten aus AQD-Berichten ist nützlich, wenn Sie verwaltete Gebäude oder Netzwerke sanieren, in denen Verbundendpunkte sich auf Ihre Berichte möglicherweise beeinflussen können.

| Filter         | Beschreibung          | Beispiel für CQD-Abfragefilter      |
|----------------|----------------------|-------------------------------|
| Keine leeren Werte   | Einige Filter haben nicht die Möglichkeit, nach leeren Werten zu filtern. Wenn Sie leere Werte manuell filtern möchten, verwenden Sie den leeren Ausdruck, und legen Sie den Filter abhängig von Ihren Anforderungen auf "Equals" oder "Not Equals" fest.      | Second Building Name \<\> \^ \\ s\*\$                       |
| Häufig verwendete Subnetze ausschließen | Ohne eine gültige Gebäudedatei, um verwaltete von nicht verwalteten Netzwerken zu trennen, werden Heimnetzwerke in die Berichte aufgenommen. Diese Heimnetz-Subnetze liegen außerhalb des Kontrollbereichs der IT und können schnell aus einem Bericht ausgeschlossen werden. Gemeinsame Subnetze, wie in diesem Artikel definiert, sind 10.0.0.0, 192.168.1.0 und 192.168.0.0. | Zweites Subnetz \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Nur innere anzeigen  | Wird verwendet, um einen Bericht für verwaltete (interne) oder nicht verwaltete (externe) zu filtern. Die Vorlage für verwaltete CQD ist bereits mit diesen Filtern vorkonfiguriert.       | Zweiter innerhalb des Unternehmens = Intern        |


#### <a name="how-to-find-your-tenant-id"></a>So suchen Sie Ihre Mandanten-ID

Die Mandanten-ID im AQD entspricht der Verzeichnis-ID in Azure. Wenn Sie Ihre Verzeichnis-ID nicht kennen, können Sie sie im Azure-Portal finden:

1.  Melden Sie sich im Microsoft Azure-Portal an: <https://portal.azure.com>

2.  Wählen Sie **Azure Active Directory** aus.

3.  Wählen Sie unter **Verwalten** **Eigenschaften** aus. Ihre Mandanten-ID befindet sich im **Feld Verzeichnis-ID.**

Sie können Ihre Mandanten-ID auch mithilfe von PowerShell finden: 

```powershell
Login-AzureRmAccount
```

## <a name="comparing-teams-and-skype-for-business-cqd-data"></a>Vergleich von Teams- und Skype for Business-AQD-Daten

Bei der Überprüfung Ihrer Daten können Unterschiede bei den Daten zwischen Teams und Skype for Business bestehen. Dafür gibt es einige Gründe:
- Unterschiede bei den Mechanismen zur Sicherstellung von Leistung und Zuverlässigkeit:
  - Teams verfügt über automatische erneute Verbindungen und schnelles Roaming. Skype for Business funktioniert nicht.
  - Teams verfügt über dynamische Bandbreitenverwaltung. Skype for Business funktioniert nicht.
- Unterschiede bei [den IP-Adressbereichen](Office-365-URLs-IP-address-ranges.md) zwischen Teams und Skype for Business. Die IP-Bereiche von Teams sind neuer, wodurch Verbindungsprobleme bei der Firewall auftreten können.



## <a name="related-topics"></a>Verwandte Themen

[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

[Was ist CQD?](CQD-what-is-call-quality-dashboard.md)

[Einrichten des Anrufqualitätsdashboards (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Hochladen von Mandanten- und Gebäudedaten](CQD-upload-tenant-building-data.md)

[Verwalten der Anruf- und Besprechungsqualität mithilfe des Anrufqualitäts-AQD](quality-of-experience-review-guide.md)

[Im AQD verfügbare Dimensionen und Measures](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Stream Classification in CQD](stream-classification-in-call-quality-dashboard.md)

[Verwenden von Power BI zum Analysieren von AQD-Daten](CQD-Power-BI-query-templates.md)
