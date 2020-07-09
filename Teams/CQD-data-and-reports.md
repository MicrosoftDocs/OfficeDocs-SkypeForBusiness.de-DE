---
title: Daten und Berichte im Dashboard für die Anrufqualität (CQD)
ms.author: lolaj
author: LolaJacobsen
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
description: Informieren Sie sich über die Daten und Berichte, die im Microsoft Call Quality-Dashboard (CQD) zur Verfügung stehen.
ms.openlocfilehash: 02acff8cd423901c8959e94af664ffe4d43c0e51
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086018"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a>Daten und Berichte im Dashboard für die Anrufqualität (CQD)

Das Microsoft Call Quality-Dashboard (CQD) verwendet einen fast-Echtzeit-Daten Feed (NRT). Anrufdatensätze stehen innerhalb von 30 Minuten nach dem Ende eines Anrufs in CQD zur Verfügung. Anrufdatensätze aus der NRT-Pipeline stehen nur einige Monate zur Verfügung, bevor Sie aus dem Datensatz entfernt werden. 


> [!NOTE]
> Advanced CQD (neu im November 2019) führt Daten aus der älteren CQD-Pipeline zusammen, die anrufdatensätze in etwa 24 Stunden zur Verfügung stellt, mit NRT-Daten aus der erweiterten CQD-Pipeline. Abfragen in den älteren und erweiterten Portalen für die Daten aus dem Archivierungszeitraum liefern dieselben Ergebnisse. Abfragen auf einem Portal für die NRT-Daten und NRT-Daten + EUII-Perioden sind unterschiedlich.

## <a name="many-ways-to-access-cqd-data"></a>Viele Möglichkeiten für den Zugriff auf CQD-Daten

Sie können auf CQD-Daten über verschiedene Alleen zugreifen. Entscheiden Sie sich für die Person, die Ihren Anforderungen am besten entspricht:

|  |  |
|---------|---------|
|Teams Admin Center [( https://admin.teams.microsoft.com) ](https://admin.teams.microsoft.com)    | CQD-Daten sind im Team Admin Center auf der Seite " **Benutzer** " enthalten, wobei die am häufigsten benötigten Daten in einem einfach zu lesenden Format angezeigt werden. Sie können CQD-Daten, die Sie unter " **Benutzer**" finden, nicht anpassen.  |
|CQD- [Portal https://cqd.teams.microsoft.com) (](https://cqd.teams.microsoft.com)     | Robuste Zusammenfassungs-und Detailberichte, die die meisten Anforderungen erfüllen, mit Drillthrough-Filterung. Sie können Berichte auch im CQD-Portal anpassen. <br><br>Besorgen Sie sich zwei [CQD-Berichtsvorlagen](#import-the-cqd-report-templates) , die Ihnen bei der Analyse von Daten im CQD-Portal helfen.       |
|Power BI     | Verwenden Sie direkte Abfragen, um Ihre CQD-Daten in Power BI mithilfe von [anpassbaren Power BI-Vorlagen](CQD-Power-BI-query-templates.md)anzuzeigen. [Herunterladen von Power BI-Abfragevorlagen für CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)<br><br>Sie können auch [die restliche API verwenden, um über Power BI auf CQD-Daten zuzugreifen](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/data-api) . Verwenden Sie diese Methode, wenn Sie Ihre CQD-Daten herunterladen möchten, damit Sie offline daran arbeiten können. Der Vorteil der Verwendung dieser Methode ist eine bessere Leistung, insbesondere bei umfangreichen Datensätzen, die sich in Power BI versumpfen, wenn Sie online sind.       |
|Diagramm-API     | Verwenden Sie die [Diagramm-API](https://docs.microsoft.com/graph/api/resources/callrecords-api-overview?view=graph-rest-beta), um selbst auf die Daten der Anrufqualität zuzugreifen. Hierbei handelt es sich um die komplexeste Methode, die Ihnen jedoch die meiste Kontrolle und Flexibilität bei der Analyse Ihrer Anruf Qualitätsdaten bietet. Wenn Sie beispielsweise mit anderen Daten für Ihre Organisation teilnehmen müssen, können Sie die Diagramm-API verwenden, um ein Datenmodell zu erstellen und die Daten zur Anrufqualität zu integrieren.        |

## <a name="import-the-cqd-report-templates"></a>Importieren der CQD-Berichtsvorlagen

Sie können [zwei kuratierte CQD-Berichtsvorlagen](https://aka.ms/qertemplates) (alle Netzwerke und verwaltete Netzwerke) herunterladen, damit Sie mit CQD schnell auf dem Laufenden sind. Die Vorlage "Alle Netzwerke", die für die Arbeit mit einer Gebäudedatendatei optimiert ist, kann verwendet werden, während Sie auf die Erfassung und das Hochladen von Gebäudeinformationen in CQD hinarbeiten, wie im nächsten Abschnitt beschrieben.

**So importieren Sie die Vorlagen (. CQDX) into CQD**

1. Wählen Sie in CQD im Menü oben auf der Seite **detaillierte Berichte** aus.

2. Wählen Sie im linken Panel **importieren**aus. Navigieren Sie zur ersten CQDX-Vorlage, und wählen Sie **Öffnen**aus.

3. Nachdem die Vorlage hochgeladen wurde, wird in einem Popupfenster die Meldung "Bericht Import war erfolgreich" angezeigt. 

4. Wiederholen Sie die Schritte 2 und 3 für die zweite CQD-Vorlage.

> [!NOTE]
> Jeder Benutzer muss die CQD-Vorlagen in die CQD-Instanz importieren. 



## <a name="euii-data"></a>EUII-Daten

Aus Kompatibilitätsgründen werden Endbenutzer-identifizierbare Daten (EUII) (auch bekannt als personenbezogene Informationen oder PII) nur 30 Tage lang aufbewahrt. Wenn NRT-Daten die 30-Tage-Marke überschreiten, werden Felder, die EUII enthalten, gelöscht, was zu EUII-freien NRT-Daten führt. Felder, die EUII-Daten enthalten, sind:

- Vollständige IP-Adresse
- Mac-Adresse (Media Access Control)
- Grundlegende Dienst Satz-ID (BSSID)
- SIP-URI (Session Initiation Protocol) (nur Skype for Business)
- Benutzerprinzipalname (User Principal Name, UPN)
- Name des Computer Endpunkts
- Benutzer-Verbatim-Feedback
- Objekt-ID (die Active Directory-Objekt-ID des Benutzers des Endpunkts)

### <a name="admin-roles-with-and-without-euii-access"></a>Administratorrollen mit und ohne EUII-Zugriff

Diese [RBAC](https://docs.microsoft.com/azure/role-based-access-control/overview) - **Rollen verfügen** über EUII-Zugriff:
- Globaler Administrator
- Team Dienstadministrator
- Teams Communications-Administrator
- Teams-Kommunikationssupporttechniker
- Globaler Leser
- Skype for Business-Administrator

Diese RBAC-Rollen haben **keinen** EUII-Zugriff:
- Berichtsleser
- Supportfachmann für die Teams-Kommunikation


## <a name="date-controls"></a>Datumssteuerelemente

CQD unterstützt die folgenden Rolling Trend-Typen:

- 5 Tage
- 7 Tage
- 30 Tage
- 60-Tag
- 90-Tag

Der URL-Datumsparameter akzeptiert ein Tages Feld. Rolling-Day-Berichte verwenden Datumsangaben, die im Format yyyy-mm-tt als letzten Tag des Trends angegeben wurden. Der URL-Datumsparameter "00" gibt "heute" an.

|URL| Enddatum des Wälz enden Tagestrends|
|:---|:---|
|<span>https:// <cqdv3> /SPD/#/Dashboard/ <reportid> /2019-02/</span>   |Aktueller Tag von Feb 2019|
|<span>https:// <cqdv3> /SPD/#/Dashboard/ <reportid> /2019-02-15/</span>|15 Feb 2019|
|<span>https:// <cqdv3> /SPD/#/Dashboard// <reportid> 00/</span>        |Aktueller Tag|
|||

Standardmäßig wird der aktuelle Tag des Monats als letzter Tag des Rolling Day-Trends verwendet.


## <a name="data-available-in-cqd-reports"></a>In CQD-Berichten verfügbare Daten

Die Standard Zusammenfassung und detaillierte CQD-Berichte sind möglicherweise alles, was Sie benötigen, um die Anrufqualität für Ihre Organisation zu verwalten. Bei Bedarf können Sie [benutzerdefinierte Berichte erstellen](#create-custom-detailed-reports). 

Wenn Sie Power BI zum Analysieren ihrer CQD-Daten verwenden möchten, lesen Sie [Verwenden von Power BI zum Analysieren von CQD-Daten für Teams](CQD-Power-BI-query-templates.md).

|Feature|Zusammenfassungsberichte|Detaillierte Berichte|
|:--- |:--- |:--- |
|Anwendungsfreigabemetrik | Nein | Ja |
|Unterstützung von Kunden-Gebäudeinformationen | Ja | Ja  |
|Support für Kunden Endpunktinformationen | Nur in <span> CQD.Teams.Microsoft.com<span/> | Nur in <span> CQD.Teams.Microsoft.com<span/> |
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


 
### <a name="select-product-data-to-see-in-reports"></a>Auswählen von Produktdaten, die in Berichten angezeigt werden sollen

In den Berichten "Zusammenfassung" und "Standort optimiert" können Sie die Dropdownliste " **Produkt Filter** " verwenden, um alle Produktdaten, nur Microsoft Teams-Daten oder nur Skype for Business Online-Daten anzuzeigen.
  
![Screenshot: zeigt die Optionen des Produkt Filter-Steuerelements an.](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
In detaillierten Berichten können Sie die **is Teams** -Dimension verwenden, um die Daten nach Microsoft Teams oder Skype for Business Online-Daten zu filtern.

## <a name="summary-reports"></a>Zusammenfassungsberichte

Dies sind die Berichte, die Sie auf dem CQD-Dashboard sehen, wenn Sie sich zum ersten Mal bei CQD anmelden. Sie geben Ihnen einen Überblick über die qualitätstrends mit täglichen, monatlichen und Tabellen Berichten, die Ihnen bei der Ermittlung von Subnetzen helfen, die schlechte Qualität aufweisen. 

|Registerkarte  |  |
|---------|---------|
|Allgemeine Anrufqualität     | Aggregat der anderen drei Registerkarten        |
|Server – Client     |Details zu den Datenströmen zwischen Server-und Clientendpunkten         |
|Client – Client     |Details zu den Streams zwischen zwei Clientendpunkten         |
|SLA zur Sprachqualität     |Informationen zu anrufen, die in der Skype for Business-sprach Quality- [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252) enthalten sind         |

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
- WiFi drinnen
- WLAN außerhalb

Auf ähnliche Weise verfügt die Registerkarte Client-Client über fünf reduzierbare Abschnitte:

- Intern verdrahtet – innen verkabelt
- Intern verdrahtet – außerhalb verdrahtet
- Außen verdrahtet – außerhalb verdrahtet
- Intern verdrahtet – WLAN-Anschluss
- Intern verdrahtet – WiFi außerhalb

#### <a name="inside-versus-outside"></a>Drinnen versus außerhalb

CQD stuft einen Datenstrom *in* oder *außerhalb* mithilfe von Gebäudeinformationen ein, sofern vorhanden. Die Endpunkte jedes Datenstroms sind einer Subnetzadresse zugeordnet. Wenn sich das Subnetz in der Liste der Subnetze befindet, die in den hochgeladenen Gebäudeinformationen als InsideCorp markiert sind, wird es im *Innern*berücksichtigt. Wenn noch keine Gebäudeinformationen hochgeladen wurden, werden die Datenströme von Inside Test immer als *außerhalb*klassifiziert. 

Der interne Test für ein Server-Client-Szenario berücksichtigt nur den Client Endpunkt. Da sich Server aus der Perspektive des Benutzers stets außerhalb befinden, werden sie beim Test nicht berücksichtigt.
  
#### <a name="wired-versus-wifi"></a>Wired versus WiFi

Wie die Namen angeben, basieren die Klassifizierungskriterien auf dem Typ der Clientverbindungen. Der Server ist immer verkabelt und nicht in der Berechnung enthalten. Wenn einer der beiden Endpunkte in einem bestimmten Datenstrom mit einem WLAN-Netzwerk verbunden ist, wird er von CQD als WLAN klassifiziert.
> [!NOTE]
> Wenn einer der beiden Endpunkte in einem Stream mit einem WLAN-Netzwerk verbunden ist, wird er in CQD als WLAN klassifiziert.
  
  
## <a name="tenant-data-information"></a>Mandantendaten Informationen

Das Dashboard für CQD-Zusammenfassungsberichte enthält eine Seite für **Mandantendaten Upload** , auf die durch Auswählen von **Mandantendaten Upload** im Menü Einstellungen in der oberen rechten Ecke zugegriffen wird. Diese Seite wird für Administratoren verwendet, um Ihre eigenen Informationen hochzuladen, beispielsweise:

- Eine Karte mit IP-Adressen und geografischen Informationen
- Eine Karte der einzelnen WLAN-AP und deren Mac-Adresse
- Eine Karte des Endpunkt-zu-Endpunkt-Marke/-Modells/-Typs usw.
  
Wir empfehlen, dass Sie Ihre Mandanten-, Gebäude-und Standortdaten hochladen, damit CQD diese Informationen in Ihre Berichte aufnehmen kann. Wenn Sie diese Daten noch nicht hochgeladen haben, lesen Sie [Hochladen von Mandanten und Erstellen von Daten](CQD-upload-tenant-building-data.md). 


## <a name="detailed-reports"></a>Detaillierte Berichte

|Name  |  |
|---------|---------|
|Standort optimierte Berichte     |Zeigt qualitätstrends auf der Grundlage von Standortinformationen. Dieser Bericht wird nur angezeigt, wenn Sie [Ihre Mandantendaten hochgeladen](CQD-upload-tenant-building-data.md)haben.        |
|Zuverlässigkeitsberichte     |Umfasst Audio, Video, videobasierte Bildschirmfreigabe (schlechte VBSS) und App-Freigabe Berichte         |
|Berichte über die Qualität von Erfahrungen     |Audioqualität und-Zuverlässigkeit für alle Clients und Geräte, einschließlich Besprechungsräumen. Bei diesen Berichten handelt es sich um eine abgespeckte Version der herunterladbaren [CQD-Vorlagen](https://aka.ms/QERtemplates), die sich auf wichtige Bereiche für die Analyse von Audioqualität und-Zuverlässigkeit konzentriert.         |
|Qualitäts Drilldown-Berichte     | Drilldowns: Datum nach Region, Orten, Subnetzen, Stunden und Benutzern         |
|Fehler Drilldown-Berichte     | Drilldowns: Datum nach Region, Orten, Subnetzen, Stunden und Benutzern        |
|Meine Anrufberichte abstimmen     |Analysieren der Nutzer Anruf Bewertungen nach Region, Standort oder nach Benutzer. Enthält Verbatim-Feedback.         |
|Helpdesk-Berichte     |In den Helpdesk-Berichten werden Anruf-und Besprechungsdaten für einzelne Benutzer, Gruppen von Benutzern oder alle Personen betrachtet. Mithilfe dieser Berichte können Sie Gebäude-und EUII-Daten integrieren, um mögliche System Probleme zu erkennen, die auf Netzwerkstandort, Konferenzdetails, Geräten oder Firmware basieren.         |
|Client Versions Berichte     |Client-Versions Zusammenfassung: Anzeigen der Sitzungen und Benutzeranzahl für jede Client-App-Version<br><br>Client Version nach Benutzer: Anzeigen von Benutzernamen für jede Client-App-Version <br><br>Vordefinierte Filter für Produkt-und Client Typen helfen bei der Fokussierung der Versionen auf bestimmte Clients.         |
|Endpunkt Berichte     |Zeigt die Anrufqualität nach Computer Endpunkten an (Computerhersteller und-Modell). Diese Berichte beinhalten Gebäudedaten, wenn Sie Sie hochgeladen haben.         |


## <a name="create-custom-detailed-reports"></a>Erstellen benutzerdefinierter detaillierter Berichte

Wenn die standardmäßigen CQD-Berichte Ihren Anforderungen nicht entsprechen, verwenden Sie diese Anweisungen, um einen benutzerdefinierten Bericht zu erstellen. Oder (ab Januar 2020) [verwenden Sie stattdessen Power BI für CQD-Berichte ](cqd-power-bi-query-templates.md).

Wählen Sie in der Pulldown-Liste der oben auf dem Bildschirm angezeigten Berichte auf \( dem Bildschirm " **Zusammenfassungsberichte** " \) **detaillierte Berichte** und dann **neu**aus. Klicken Sie in einem Bericht auf **Bearbeiten** , um den Abfrage-Editor anzuzeigen. Jeder Bericht basiert auf einer Abfrage im Cube. Ein Bericht ist die visuelle Darstellung der Daten, die von der jeweiligen Abfrage zurückgegeben werden. Der Abfrage-Editor hilft Ihnen, diese Abfragen und die Anzeigeoptionen des Berichts zu bearbeiten.
> [!IMPORTANT]
> Der Netzwerkbereich kann zur Darstellung eines Supernetzes (einer Kombination aus mehreren Subnetzen mit einem einzelnen Routing-Präfix) verwendet werden. Alle neuen Gebäude-Uploads werden auf sich überlappende Bereiche hin untersucht. Wenn Sie zuvor eine Gebäudedatei hochgeladen haben, sollten Sie die aktuelle Datei herunterladen und erneut hochladen, um mögliche Überlappungen zu identifizieren und das Problem vor dem erneuten Hochladen zu beheben. Alle Überlappungen in zuvor hochgeladenen Dateien können zu falschen Zuordnungen von Subnetzen zu Gebäuden in den Berichten führen. Bei bestimmten VPN-Implementierungen werden die Subnetinformationen nicht genau gemeldet. Es wird empfohlen, beim Hinzufügen eines VPN-Subnetzes zur Gebäudedatei anstelle eines Eintrags für das Subnetz separate Einträge für jede Adresse im VPN-Subnetz als separates 32 Bit-Netzwerk hinzuzufügen. Jede Zeile kann die gleichen Gebäudemetadaten enthalten. Ein Beispiel: Anstelle einer Zeile für 172.16.18.0/24 sollten Sie 256 Zeilen verwenden - eine Zeile für jede Adresse zwischen 172.16.18.0/32 und 172.16.18.255/32 (einschließlich).
>
> Die VPN-Spalte ist optional und wird standardmäßig auf 0 gesetzt.  Wenn der Wert der VPN-Spalte auf 1 festgesetzt ist, wird das durch diese Zeile dargestellte Subnetz vollständig erweitert, damit es allen IP-Adressen im Subnetz entspricht.  Verwenden Sie diese sparsam und nur für VPN-Subnetze, da sich diese Subnetze durch eine vollständige Erweiterung negativ auf die Abfragezeiten für Abfragen mit Gebäudedaten auswirken.

Zeigen Sie auf Balkendiagramme und Trendlinien im Bericht, um detaillierte Werte anzuzeigen. Der Bericht, der einen Fokus besitzt, zeigt das Aktionsmenü an: **Bearbeitung**, **Klonen**, **Löschen**, **Herunterladen** und **Exportieren**.



## <a name="query-filters"></a>Abfragefilter

Abfragefilter werden mithilfe des Abfrage-Editors in CQD implementiert. Diese Filter werden verwendet, um die Anzahl der von CQD zurückgegebenen Datensätze zu verringern, wodurch die Gesamtgröße und die Abfragezeiten des Berichts minimiert werden. Dies ist besonders hilfreich, wenn nicht verwaltete Netzwerke ausgefiltert werden sollen. Die in der folgenden Tabelle aufgelisteten Filter verwenden reguläre Ausdrücke (RegEx).


| Filter         | Beschreibung          | Beispiel für CQD-Abfragefilter      |
|----------------|----------------------|-------------------------------|
| Keine leeren Werte   | Einige Filter verfügen nicht über die Option zum Filtern nach leeren Werten. Wenn Sie leere Werte manuell filtern möchten, verwenden Sie den leeren Ausdruck, und legen Sie den Filter abhängig von Ihren Anforderungen auf "Equals" oder "Not Equals" fest.      | Zweiter Gebäude Name \<\> \^ \\ s\*\$                       |
| Häufig verwendete Subnetze ausschließen | Ohne eine gültige Gebäudedatei, um verwaltete von nicht verwalteten Netzwerken zu trennen, werden Heimnetzwerke in die Berichte aufgenommen. Diese Heimsubnetze sind außerhalb des Umfangs der Steuerung und können schnell aus einem Bericht ausgeschlossen werden. Häufig verwendete Subnetze laut der Definition in diesem Leitfaden sind 10.0.0.0, 192.168.1.0 und 192.168.0.0. | Zweites Subnetz \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Nur innere anzeigen  | Wird verwendet, um einen Bericht für verwaltete (interne) oder nicht verwaltete (externe) zu filtern. Die Vorlage für verwaltete CQD ist bereits mit diesen Filtern vorkonfiguriert.       | Zweiter innerhalb des Unternehmens = Intern        |

## <a name="report-filters"></a>Berichtsfilter

Verwenden Sie CQD-Berichtsfilter, um den Fokus Ihrer Untersuchungen einzugrenzen. Verwenden Sie Berichtsfilter, indem Sie dem gerenderten Bericht einen Filter hinzufügen, entweder im Abfrage-Editor oder direkt im Bericht. Die folgenden Berichtsfilter werden in den [CQD-Vorlagen](https://aka.ms/QERtemplates)verwendet.


| Filter     | Beschreibung                            | Beispiel für CQD-Berichtsfilter         |
|------------|----------------------------------------|-----------------------------------|
| Monat      | Beginnen Sie zuerst mit dem Jahr und dann mit dem Monat. | 2017-10                           |
| Alphabetisch | Filtert nach alphabetischen Zeichen. | [a-z]                             |
| Numerisch    | Filtert nach allen numerischen Zeichen.    | [0-9]                             |
| Prozent | Filtert nach einem Prozentsatz.              | ([3-9]\\.)\|([3-9])\|([1-9][0-9]) |


### <a name="drill-down-filters"></a>Drilldown-Filter

CQD-Berichte verfügen über mehrere Drilldown-Filter, die leistungsstarke Tools zur Eingrenzung des Schwerpunkts Ihrer Anruf Qualitäts Ermittlungen sind. Wenn Sie ein Drilldown-Feld auswählen, öffnet der Bericht automatisch die entsprechende Registerkarte und filtert den ausgewählten Wert. Wenn die Registerkarte über eigene Drilldown-Felder verfügt und eine markiert ist, werden beide Filtersätze angewendet, wodurch die resultierende Datenmenge schrittweise eingegrenzt wird.

![Diagramm, das einen Drilldown-Berichts Fluss veranschaulicht](media/qerguide-image-drillthrureportflow.png)


#### <a name="adding-and-editing-drill-down-fields"></a>Hinzufügen und Bearbeiten von Drilldown-Feldern

Wenn Sie einen Bericht bearbeiten, haben Sie die Möglichkeit, mithilfe des Abfrage-Editors eigene Drilldown-Felder anzugeben.

Klicken Sie zunächst auf **...** für den Bericht, den Sie bearbeiten möchten, und wählen Sie dann **Bearbeiten**aus.

![Screenshot zum Bearbeiten eines Drilldown-Felds](media/qerguide-image-addeditdrilldownfields.png)

Wählen Sie in der Liste auf der linken Seite des Abfrage-Editors eine Dimension aus. Klicken Sie dann auf die Dropdownliste unter der Registerkarte **Navigieren zur** Beschriftung, und wählen Sie die Registerkarte und die Erweiterungsgruppe aus, in die die Dimension gebohrt werden soll. Hinweis: Derzeit funktioniert die Drilldownfunktion nur durch Navigieren zu verschiedenen Registerkarten. Die Unterstützung für das Drillthrough zu einem bestimmten Erweiterungsmodul wird später hinzugefügt. Klicken Sie abschließend auf **Schließen** , um die Änderungen an der Dimension zu speichern, und klicken Sie dann auf **Speichern** , um den Abfrage-Editor zu speichern und zu schließen.

![Screenshot der Auswahl einer Dimension im Abfrage-Editor](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a>Mehrfachauswahl-Filter

Neben der Drilldownfunktion unterstützt CQD auch das Angeben von Filtern mit mehreren Werten (oder Filtern).

Um mehrere Filterwerte auszuwählen, fügen Sie zunächst einen neuen Filter zum Bericht hinzu. Klicken Sie **+** neben der **Filter** Beschriftung, geben Sie den Namen der zu verwendenden Dimension ein, und klicken Sie auf **Hinzufügen**.

![Screenshot zum Hinzufügen eines Mehrfachauswahl Filters](media/qerguide-image-addmultiselectfilter.png)

Klicken Sie dann auf **Suchen** (ein Vergrößerungsglassymbol neben dem neuen Filter). Sie sehen ein Textfeld und eine Reihe von Optionen, einschließlich **"Alles auswählen"** und " **umkehren**". Geben Sie einen Wert ein, und klicken Sie neben dem zu durchsuchenden Feld auf **Suchen** . Alternativ können Sie das Textfeld leer lassen und auf **Suchen** klicken, um die ersten 100-Optionen anzuzeigen.

```PowerShell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Beispiel:  

![Screenshot zum Hinzufügen eines Abfragefilters](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a>Dashboard-Stufen Filter
Bestimmten CQD-Berichten sind Filter auf dashboardebene hinzugefügt, sodass Sie nach allgemeinen Parametern einfach gefiltert werden können. Diese Filter werden außerhalb der regulären Bericht Registerkarten und direkt unterhalb des Produkt Filters angezeigt, und Sie gelten für alle Filter im Dashboard.

![Screenshot eines Dashboard-Filters](media/qerguide-image-dashboardfilters.png)
```PowerShell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a>URL-Filter

CQD unterstützt das Hinzufügen von Filtern zur URL. Dadurch ist es einfach, eine CQD-Abfrage freizugeben oder mit einer Textmarke zu versehen. Sie können Parameter in der URL definieren, wie etwa Trend Monat, Mandanten-ID oder Sprache. Sie können der URL auch Produkt-oder dashboardebene-Filter hinzufügen.
Das Ausschließen von Verbund Daten aus CQD-Berichten ist hilfreich, wenn Sie verwaltete Gebäude oder Netzwerke remediationen, in denen Verbundendpunkte ihre Berichte beeinflussen könnten.

Um einen Filter hinzuzufügen, fügen Sie am Ende der URL Folgendes an:

```
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Beispiel:  

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]```

Um einen Filter auf dashboardebene zu einer URL hinzuzufügen, muss dieser Filter in CQD entweder als Produkt-oder dashboardebene-Filter vorhanden sein. Fügen Sie diese Filter der URL nach dem Trend Monat und vor den URL-Parametern hinzu:

```filter/DATA_MODEL_NAME|VALUE```

Wenn Sie beispielsweise einen Produktfilter Wert von Microsoft Teams anwenden möchten, fügen Sie Folgendes hinzu:

```filter/[AllStreams].[Is%20Teams]|[True]```

Die gesamte URL sieht ungefähr wie folgt aus:

```https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]```

Wenn Sie URL-Filter mit Mehrfachauswahl Werten anwenden möchten, trennen Sie die einzelnen Werte durch ein Pipe-Zeichen (|). Beispiel:

```filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]```

Wenn Sie einen ungültigen Namen oder einen ungültigen Wert angeben, wird der URL-Filter nicht angewendet.


Sie können einen URL-Filter verwenden, um jeden Bericht für eine bestimmte Dimension zu filtern. Die am häufigsten verwendeten URL-Filter werden verwendet, um Berichte zu filtern, um die Telemetrie von Teilnehmern auszuschließen, oder sich nur auf Teams oder Skype for Business Online zu konzentrieren. Das Ausschließen von Verbund Daten aus CQD-Berichten ist hilfreich, wenn Sie verwaltete Gebäude oder Netzwerke remediationen, in denen Verbundendpunkte ihre Berichte beeinflussen könnten.

| Filter         | Beschreibung          | Beispiel für CQD-Abfragefilter      |
|----------------|----------------------|-------------------------------|
| Keine leeren Werte   | Einige Filter verfügen nicht über die Option, nach leeren Werten zu filtern. Wenn Sie leere Werte manuell filtern möchten, verwenden Sie den leeren Ausdruck, und legen Sie den Filter abhängig von Ihren Anforderungen auf "Equals" oder "Not Equals" fest.      | Zweiter Gebäude Name \<\> \^ \\ s\*\$                       |
| Häufig verwendete Subnetze ausschließen | Ohne eine gültige Gebäudedatei, um verwaltete von nicht verwalteten Netzwerken zu trennen, werden Heimnetzwerke in die Berichte aufgenommen. Diese Home-Subnetze liegen außerhalb des Kontrollbereichs und können schnell von einem Bericht ausgeschlossen werden. Allgemeine Subnets, wie in diesem Artikel definiert, sind 10.0.0.0, 192.168.1.0 und 192.168.0.0. | Zweites Subnetz \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Nur innere anzeigen  | Wird verwendet, um einen Bericht für verwaltete (interne) oder nicht verwaltete (externe) zu filtern. Die Vorlage für verwaltete CQD ist bereits mit diesen Filtern vorkonfiguriert.       | Zweiter innerhalb des Unternehmens = Intern        |


#### <a name="how-to-find-your-tenant-id"></a>So finden Sie Ihre Mandanten-ID

Die Mandanten-ID in CQD entspricht der Verzeichnis-ID in Azure. Wenn Sie Ihre Verzeichnis-ID nicht kennen, können Sie Sie im Azure-Portal finden:

1.  Melden Sie sich im Microsoft Azure-Portal an: <https://portal.azure.com>

2.  Wählen Sie **Azure Active Directory** aus.

3.  Wählen Sie unter **Verwalten** **Eigenschaften** aus. Ihre Mandanten-ID befindet sich im Feld **Verzeichnis-ID** .

Sie können Ihre Mandanten-ID auch mithilfe von PowerShell ermitteln: 
  ```
  Login-AzureRmAccount
  ```



## <a name="comparing-teams-and-skype-for-business-cqd-data"></a>Vergleich von Teams und Skype for Business-CQD-Daten

Selbst innerhalb des aktuellen CQD (CQD.Teams.Microsoft.com) werden Unterschiede zwischen den Daten zwischen Teams und Skype for Business angezeigt. Einige Gründe:
- Unterschiede bei den Mechanismen zur Sicherstellung der Leistung und Zuverlässigkeit
  - Teams hat eine automatische Wiederherstellung und ein schnelles Roaming. Skype for Business nicht.
  - Teams verfügt über dynamische Bandbreitenverwaltung. Skype for Business nicht.
- Unterschiede bei [IP-Adressbereichen](Office-365-URLs-IP-address-ranges.md) zwischen Teams und Skype for Business. Die IP-Bereiche von Teams sind neuer, was zu Verbindungsproblemen bei der Firewall führen kann.

## <a name="open-cqd-from-the-skype-for-business-legacy-portal"></a>Öffnen von CQD aus dem Skype for Business Legacy-Portal

![Symbol des Skype for Business-Logos ](media/sfb-logo-30x30.png) **unter Verwendung des Legacy-Portals von Skype for Business**

1. Melden Sie sich mit einem Administratorkonto bei Ihrer Office 365-Organisation an, und wählen Sie dann die Kachel **Admin** aus, um das Admin Center zu öffnen.
2. Wählen Sie im linken Bereich unter **Admin Center**die Option **Microsoft Teams** aus, um das Team Admin Center zu öffnen.
3. Wählen Sie im Team Admin Center im linken Bereich **Legacy Portal** aus, wählen Sie **Tools**aus, und wählen Sie dann **Skype for Business Online-Anruf Qualitäts Dashboard**aus.

     ![Screenshot: Auswählen des Dashboards für die Anrufqualität](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. Melden Sie sich auf der daraufhin geöffneten Seite mit ihrem globalen Administrator Konto an, und geben Sie die Anmeldeinformationen für das Konto ein, wenn Sie dazu aufgefordert werden.

Nachdem Sie sich das erste Mal angemeldet haben, wird CQD mit dem sammeln und Verarbeiten von Daten beginnen. 

> [!IMPORTANT]
> Ab Dezember 2019 können Sie weiterhin auf die ältere Version von CQD (CQD.lync.com) zugreifen, obwohl das Legacy Portal Ihnen einen Link zu dem neuesten CQD (CQD.Teams.Microsoft.com) bietet. Schließlich wird die ältere Version von CQD außer Betrieb genommen. Ab dem 1. Juli 2020 greift die ältere Version von CQD auf Daten aus dem neuen CQD ( https://CQD.teams.microsoft.com) und Sie können keine Gebäude-und Berichtsdaten mehr exportieren. Irgendwann in späten 2020, werden wir die alte CQD deaktivieren, und Sie können nicht mehr darauf zugreifen.


## <a name="related-topics"></a>Verwandte Themen

[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

[Was ist CQD?](CQD-what-is-call-quality-dashboard.md)

[Einrichten des Dashboards für die Anrufqualität (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Hochladen von Mandanten-und Gebäudedaten](CQD-upload-tenant-building-data.md)

[Verwenden von CQD zum Verwalten von Anruf-und Besprechungs Qualität](quality-of-experience-review-guide.md)

[In CQD verfügbare Dimensionen und Measures](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Datenstrom Klassifizierung in CQD](stream-classification-in-call-quality-dashboard.md)

[Verwenden von Power BI zum Analysieren von CQD-Daten](CQD-Power-BI-query-templates.md)
