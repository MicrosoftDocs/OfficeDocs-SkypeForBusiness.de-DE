---
title: "Aktivieren und verwenden Qualität Dashboards aufrufen"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: ms.lync.lac.ToolsCallQualityDashboard
ms.custom: Setup
description: 'See how to turn on and use the Skype for Business Online Call Quality Dashboard and get summary reports of quality of calls. '
ms.openlocfilehash: a3838906532aad5d583ddc786e85516c7b78cf01
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Einschalten und Aufrufen Qualitätsdashboard für Microsoft-Teams und Skype für Business Online

Hier erfahren Sie, wie Sie Ihre Office 365-Organisation konfigurieren können, um das Anrufqualitäts-Dashboard zur Überwachung der Anrufqualität zu verwenden.
  
Mit dem Anrufqualitäts-Dashboard (AQD) für Microsoft Teams und Skype for Business Online erhalten Sie einen Einblick in die Qualität von Anrufen, die mit Microsoft Teams- und Skype for Business-Diensten getätigt wurden. In diesem Thema werden die Schritte beschrieben, die Sie ausführen müssen, um die Datenerfassung zu starten.
  
> [!NOTE]
> Die detaillierten CQD-Berichte sind derzeit als technische Vorschau für alle Kunden verfügbar. 
  
## <a name="latest-changes-and-updates"></a>Aktuelle Änderungen und Updates

Dies sind die neuesten Änderungen am AQD:
  
- Microsoft Teams-Daten sind zusätzlich zu Skype for Business Online-Daten enthalten.
    
- Zusammenfassungsberichte enthalten einen Produktfilter, mit dem Sie alle Daten, Microsoft Teams-Daten oder Skype for Business Online-Daten auswählen können.
    
Finden Sie in diesem Artikel finden Sie eine Liste von [Dimensionen und Measures in Aufrufen Qualitätsdashboard für Microsoft-Teams und Skype für Business Online verfügbar](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
> [!NOTE]
> Informationen zu Updates und Änderungen an das Dashboard kann gefunden werden, indem Sie auf **daran!** im Dashboard. Navigieren Sie zu [Anrufqualität Dashboard](https://aka.ms/CQDOnline). 
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a>Aktivieren von Zusammenfassungsberichten des Microsoft-Anrufqualitäts-Dashboards (AQD)

Bevor Sie mit der Verwendung des AQD beginnen können, müssen Sie es für Ihre Office 365-Organisation aktivieren.
  
1. Melden Sie sich mit einem Administratorkonto bei Ihrer Office 365-Organisation an, und wählen Sie dann die Kachel **Admin** aus, um das Admin Center zu öffnen.
    
2. Wählen Sie im linken Bereich unter **Admin Center** die Option **Skype for Business** aus, um das Skype for Business Admin Center zu öffnen.
    
3. Wählen Sie im linken Bereich des Skype for Business Admin Center die Option **Tools** aus, und wählen Sie dann **Qualitätsdashboard für Anrufe mit Skype for Business Online** aus.
    
     ![Skype for Business tools](../images/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. Melden Sie sich auf der daraufhin geöffneten Seite mit Ihrem globalen Administratorkonto an, und geben Sie dann auf die entsprechende Aufforderung hin die Anmeldeinformationen für das Konto ein.
    
     ![CQD Login](../images/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
Sobald Sie sich angemeldet und die Aktivierung vorgenommen haben, beginnt das AQD, Daten zu erfassen und zu verarbeiten.
  
> [!NOTE]
> Es kann einige Stunden dauern, bis genügend Daten verarbeitet worden sind, um in den Berichten aussagekräftige Ergebnisse anzuzeigen. 
  
## <a name="features-of-the-call-quality-dashboard-for-skype-for-business-online"></a>Funktionen des Anrufqualitäts-Dashboards für Skype for Business Online
<a name="BKMKFeaturesOfTheCQD"> </a>

CQD-Zusammenfassungsberichte bieten eine Reihe von Funktionen, die für detaillierte Berichte geplant sind. Die Unterschiede zwischen den zwei Versionen werden hier zusammengefasst:
  
|**Funktion**|**Zusammenfassungsberichte**|**Detaillierte Berichte**|
|:-----|:-----|:-----|
|Anwendungsfreigabemetrik  <br/> |Nein  <br/> |Ja  <br/> |
|Unterstützung von Kunden-Gebäudeinformationen  <br/> |Ja  <br/> |Ja  <br/> |
|Drilldown-Analyse-Support  <br/> |Nein  <br/> |Ja  <br/> |
|Medienzuverlässigkeitsmetriken  <br/> |Nein  <br/> |Ja  <br/> |
|Sofort einsatzbereite Berichte  <br/> |Ja  <br/> |Ja  <br/> |
|Übersichtsberichte  <br/> |Ja  <br/> |Ja  <br/> |
|Berichtssatz pro Nutzer  <br/> |Nein  <br/> |Ja  <br/> |
|Anpassung des Berichtssatzes (Hinzufügen, Löschen, Ändern von Berichten)  <br/> |Nein  <br/> |Ja  <br/> |
|Videobasierte Bildschirmfreigabe-Metriken  <br/> |Nein  <br/> |Ja  <br/> |
|Videometriken  <br/> |Nein  <br/> |Ja  <br/> |
|Verfügbare Datenmenge  <br/> |Letzte 6 Monate  <br/> |Letzte 6 Monate  <br/> |
|Microsoft Teams-Daten  <br/> |Ja  <br/> |Ja  <br/> |
   
### <a name="out-of-the-box-reports"></a>Sofort einsatzbereite Berichte

Beide Versionen des AQD sind sofort einsatzbereit. So erhalten Sie Kennzahlen zur Anrufqualität, ohne neue Berichte erstellen zu müssen. Sobald Daten im Back-End verarbeitet wurden, können Sie die Daten zur Anrufqualität in den Berichten einsehen.
  
### <a name="overview-reports"></a>Übersichtsberichte

Beide Versionen von CQD bieten einen hervorragenden Einstiegspunkt in Bezug auf die Informationen zur allgemeinen Anrufqualität. Jedoch unterscheidet sich die Art der Darstellung der Informationen in den Zusammenfassungsberichten und den detaillierten Berichten.
  
Die Zusammenfassungsberichte bieten eine einfache Berichtsansicht mit Seiten im Registerformat, damit Benutzer den Bericht schneller durchsuchen und den Status sowie Trends bezüglich der allgemeinen Anrufqualität schneller nachvollziehen können.
  
Die vier Registerkarten umfassen:
  
- **Gesamtanrufqualität** - Bietet Informationen zu allen Datenströmen. Hierbei handelt es sich um eine Aggregation der Server-Client-Datenströme und der Client-Client-Datenströme sowie um separate Server-Client- und Client-Client-Datenströme in Form monatlicher und täglicher Trends.
    
- **Server - Client** - Bietet zusätzliche Details für die Datenströme zwischen Server- und Clientendpunkten.
    
- **Client - Client** - Bietet zusätzliche Details für die Datenströme zwischen zwei Clientendpunkten.
    
- **SLA zur Sprachqualität** - Bietet Informationen zu den Anrufen, die im SLA zur Sprachqualität für Skype for Business Online enthalten sind.
    
### <a name="overall-call-quality-tab"></a>Registerkarte „Gesamtanrufqualität"

Verwenden Sie die Daten auf dieser Registerkarte, um den Status und die Trends der Anrufqualität auszuwerten, indem Sie sich die Anzahl der Datenströme und die Prozentzahlen zu Anrufen mit schlechter Qualität ansehen. Die Legende oben rechts zeigt an, welche Farbe und welche visuellen Elemente diese Kennzahlen darstellen.
  
![CQD Data key](../images/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
Datenströme werden in drei Gruppen unterteilt: gut, schlecht und nicht klassifizierte. Es werden auch berechnet, geben Sie das Verhältnis von Datenströmen als klassifiziert Werte für *unzureichende %* * schlecht *, um die Anzahl der insgesamt geschützte Stream. Da *schlechter % = schlecht Datenströme / (schlechter Datenströme + gute Streams) * 100* , auf diese Weise werden die *schlechter %* durch die Anwesenheit mit mehreren *Unclassified* Strömen nicht betroffen. Was für die Klassifizierung eines Stream-Objekts als schlecht oder eine gute verwendet wird finden Sie unter [Qualität Schwellenwerte aufrufen](https://aka.ms/cqd_quality_thresholds).
  
Verwenden Sie die Skala links, um die Werte für die Anrufanzahl zu ermitteln.
  
![CQD data count](../images/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Verwenden Sie die Skala rechts, um die Werte für „% Schlecht" zu ermitteln.
  
![CQD data per cent](../images/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
Sie erhalten auch die tatsächlichen numerischen Werte, indem Sie mit der Maus über eine Leiste fahren.
  
> [!NOTE]
> Das folgende Beispiel stammt aus einem kleinen Beispiel-Dataset, und die Werte sind für eine tatsächliche Bereitstellung nicht realistisch. 
  
![CQD Data numeric](../images/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
Das gesamte Datenstromvolumen ist ein wichtiger Faktor bei der Bestimmung der Relevanz der berechneten Prozentsätze für die Klassifizierung „Schlecht". Je kleiner das Volumen des gesamten Datenstroms ist, desto unzuverlässiger sind die im Bericht enthaltenen Werte für die Klassifizierung „Schlecht".
  
### <a name="server-client-tab-and-client-client-tabs"></a>Registerkarten „Server-Client" und „Client-Client"

Diese zwei Registerkarten bieten zusätzliche Details für die Datenströme, die in ihren entsprechenden Endpunkt-zu-Endpunkt-Szenarien aufgetreten sind. Beide Registerkarten haben vier reduzierbare Bereiche, die vier Szenarien darstellen, in denen die Medienströme sich bewegen würden.
  
- Innen verkabelt
    
- Außen verkabelt
    
- Innen WLAN
    
- Außen WLAN
    
#### <a name="inside-test"></a>Innentest

Bei der Verarbeitung klassifiziert das AQD-Back-End einen Datenstrom als  *Innen*  oder *Außen*  anhand von Gebäudeinformationen, falls diese vorhanden sind. Die Endpunkte jedes Datenstroms sind einer Subnetzadresse zugeordnet. Falls das Subnetz in der Liste der Subnetze in den hochgeladenen Gebäudeinformationen enthalten ist, gilt dieses als „Innen". Falls die Gebäudeinformationen noch nicht hochgeladen wurden, wird der Innentest die Datenströme stets als *Außen*  klassifizieren. Beachten Sie, dass beim Innentest für das Server-Client-Szenario nur der Clientendpunkt berücksichtigt wird. Da sich Server aus der Perspektive des Benutzers stets außerhalb befinden, werden sie beim Test nicht berücksichtigt.
  
#### <a name="wired-vs-wifi"></a>Verkabelt oder WLAN

Wie es der Name bereits besagt, handelt es sich hier um das Klassifizierungskriterium basierend auf der Art der Clientverbindungen. Um es noch einmal zu verdeutlichen: Ein Server ist immer verkabelt und wird nicht in die Berechnung einbezogen.
  
> [!NOTE]
> Wenn wir von einem Datenstrom ausgehen und einer der beiden Endpunkte mit einem WLAN verbunden ist, wird er im AQD als WLAN klassifiziert. 
  
## <a name="selecting-product-data-to-see-in-reports"></a>Auswählen der Produktdaten, die in Berichten angezeigt werden sollen
<a name="BKMKFeaturesOfTheCQD"> </a>

In den Zusammenfassungsberichten und erweiterten Standortberichten können Sie mithilfe der Dropdownliste **Produktfilter** alle Produktdaten, nur Microsoft Teams-Daten oder nur Skype for Business Online-Daten anzeigen.
  
![Screenshot shows the Product Filter control with options for All, Microsoft Teams, and Skype for Business.](../images/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
In detaillierten Berichten können Sie beim Definieren des Berichts die Daten mithilfe der Microsoft Teams-Dimension nach Microsoft Teams- oder Skype for Business Online-Daten filtern.
  
## <a name="upload-building-information"></a>Hochladen von Gebäudeinformationen
<a name="BKMKFeaturesOfTheCQD"> </a>

Das Dashboard für AQD-Zusammenfassungsberichte enthält die Seite **Upload von Mandantendaten**, auf die Sie zugreifen können, indem Sie rechts oben im Einstellungsmenü die Option **Upload von Mandantendaten** auswählen. Diese Seite wird von Administratoren zum Hochladen ihrer eigenen Informationen verwendet, wie z. B. Zuordnung von IP-Adressen und geografischen Informationen, Zuordnung der einzelnen Funkzugriffspunkte und ihrer MAC-Adressen usw.
  
![CQD Dashboard](../images/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. Verwenden Sie das Dropdownmenü auf der Seite **Upload von Mandantendaten**, um einen Datendateityp für den Upload auszuwählen. Der Dateidatentyp bezeichnet den Inhalt der Datei (z. B. bezieht sich „Gebäude" auf die Zuordnung von IP-Adressen und Gebäuden sowie auf andere geografische Informationen). Derzeit unterstützen wir nur den Datentyp „Gebäude". Weitere Datentypen werden in den nächsten Versionen hinzugefügt.
    
2. Klicken Sie nach Auswahl des Dateidatentyps auf **Durchsuchen**, um eine Datendatei auszuwählen.
    
  - Bei der Datendatei muss es sich um eine TSV-Datei (Datei mit tabulatorgetrennten Werten) oder eine CSV-Datei (Datei mit durch Trennzeichen getrennten Werten) handeln. Bei Verwendung einer CSV-Datei müssen alle Felder, die ein Komma enthalten, Anführungszeichen enthalten, oder das Komma muss entfernt werden. Beispiel: Wenn Ihr Gebäudename NY,NY lautet, muss er in der CSV-Datei als „NY,NY" eingegeben werden.
    
  - Die Datendatei darf maximal 50 MB groß sein.
    
  - Bei jeder Datendatei muss jede Spalte in der Datei einem vordefinierten Datentyp entsprechen, der später in diesem Thema besprochen wird.
    
3. Geben Sie nach Auswahl einer Datendatei das **Startdatum** und optional ein **Enddatum** ein.
    
4. Wählen Sie nach der Auswahl von **Startdatum** die Option **Hochladen** aus, um die Datei auf den AQD-Server hochzuladen.
    
    Bevor die Datei hochgeladen wird, wird sie zunächst validiert. Sobald sie validiert ist, wird sie in einem Azure-BLOB gespeichert. Falls die Validierung fehlschlägt oder die Datei nicht in einem Azure-BLOB gespeichert werden kann, wird eine Fehlermeldung angezeigt, in der die Korrektur der Datei angefordert wird. Die folgende Abbildung zeigt einen Fehler, der auftritt, wenn die Anzahl der Spalten in der Datendatei falsch ist.
    
     ![CQD Example upload validation error](../images/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. Falls während der Validierung keine Fehler auftreten, war der Dateiupload erfolgreich. Sie können die hochgeladene Datendatei in der Tabelle **Meine Uploads** anzeigen. Dort wird eine vollständige Liste aller hochgeladenen Dateien für den aktuellen Mandanten unten auf der Seite angezeigt.
    
    Jeder Eintrag zeigt eine hochgeladene Mandantendatendatei an, einschließlich Dateityp, letzter Aktualisierungszeit, Zeitraum, Beschreibung sowie Symbolen zum Entfernen und Herunterladen. Um eine Datei zu entfernen, wählen Sie das Papierkorbsymbol in der Tabelle aus. Um eine Datei herunterzuladen, wählen Sie das Downloadsymbol in der Spalte **Download** der Tabelle aus.
    
     ![CQD My Uploads table](../images/4168a883-bbea-461a-80b1-42eedf2e7732.png)
  
### <a name="tenant-data-file-format-and-building-data-file-structure"></a>Dateiformat der Mandantendaten und Dateistruktur der Gebäudedaten
<a name="BKMKTenantDataFile"> </a>

Das Format der Datei, die Sie hochladen, muss folgende Bedingungen erfüllen, um die Validierungsprüfung vor dem Hochladen zu bestehen.
  
- Bei der Datei muss es sich um eine TSV-Datei (die Spalten in den einzelnen Zeilen werden durch Tabstopps getrennt) oder um eine CSV-Datei (alle Spalten werden durch Trennzeichen getrennt) handeln.
    
- Der Inhalt der Datendatei umfasst keine Tabellenüberschriften. Das bedeutet, dass die erste Zeile der Datendatei echte Daten enthalten muss, keine Überschriften wie „Netzwerk" usw.
    
- In jeder Spalte kann der Datentyp nur eine Zeichenfolge, eine Zahl oder der boolesche Datentyp sein. Falls es eine Zahl ist, muss es sich um einen numerischen Wert handeln; falls es der boolesche Datentyp ist, muss der Wert entweder 0 oder 1 betragen.
    
- In jeder Spalte können die Daten leer sein, falls der Datentyp „Zeichenfolge" verwendet wird (jedoch müssen sie durch ein passendes Trennzeichen wie zum Beispiel einen Tabstopp oder ein Komma getrennt werden). Dadurch wird dem Feld eine leere Zeichenfolge zugewiesen.
    
- Es müssen 14 Spalten für jede Zeile vorhanden sein. Jede Spalte muss den folgenden Datentyp enthalten, und die Spalten müssen in der Reihenfolge angeordnet sein, die in der folgenden Tabelle angegeben ist:
    
|**Spaltenname**|**Datentyp**|**Beispiel**|
|:-----|:-----|:-----|
|Netzwerk  <br/> |Zeichenfolge  <br/> |192.168.1.0  <br/> |
|Netzwerkname  <br/> |Zeichenfolge  <br/> |USA/Seattle/SEATTLE-SEA-1  <br/> |
|NetworkRange  <br/> |Zahl  <br/> |26  <br/> |
|BuildingName  <br/> |Zeichenfolge  <br/> |SEATTLE-SEA-1  <br/> |
|OwnershipType  <br/> |Zeichenfolge  <br/> |Contoso  <br/> |
|BuildingType  <br/> |Zeichenfolge  <br/> |IT Termination  <br/> |
|BuildingOfficeType  <br/> |Zeichenfolge  <br/> |Engineering  <br/> |
|Ort  <br/> |Zeichenfolge  <br/> |Seattle  <br/> |
|Postleitzahl  <br/> |Zeichenfolge  <br/> |98001  <br/> |
|Land  <br/> |Zeichenfolge  <br/> |USA  <br/> |
|Bundesland  <br/> |Zeichenfolge  <br/> |WA  <br/> |
|Region  <br/> |Zeichenfolge  <br/> |MSUS  <br/> |
|InsideCorp  <br/> |Bool  <br/> |1  <br/> |
|ExpressRoute  <br/> |Bool  <br/> |0  <br/> |
   
> [!IMPORTANT]
> Der Netzwerkbereich kann zur Darstellung einer Supernetting (Kombination aus mehreren Subnetzen mit einem einzelnen routing Präfix) verwendet werden. Grenzen Sie überlappende Bereiche werden alle neuen Erstellen von Uploads überprüft werden soll. Wenn Sie eine Datei zum Erstellen von zuvor hochgeladen haben, sollten Sie die aktuelle Datei herunterladen und erneut hochladen, um eine beliebige überlappt identifizieren und beheben Sie das Problem, bevor Sie erneut hochladen. Alle Überlappung in zuvor hochgeladenen Dateien möglicherweise falschen Zuordnungen von Subnetzen zu Gebäude in den Berichten. Bestimmte VPN-Implementierungen meldet nicht genau die Subnetzinformationen. Empfiehlt es sich, die beim Hinzufügen einer VPN-Subnetz in der Datei zum Erstellen von anstelle eines Eintrags für das Subnetz werden separate Einträge für jede Adresse in das VPN-Subnetz als ein separates 32-Bit-Netzwerk hinzugefügt. Jede Zeile kann die gleiche Erstellen von Metadaten haben. Statt eine Zeile für 172.16.18.0/24, sollten Sie beispielsweise 256 Zeilen, mit einer Zeile für jeden Adresse zwischen 172.16.18.0/32 und 172.16.18.255/32, inklusive verfügen. 
  
## <a name="selecting-media-type-in-detailed-reports"></a>Auswählen eines Medientyps in detaillierten Berichten
<a name="BKMKFeaturesOfTheCQD"> </a>

Mit detaillierten Berichten können die Qualität und die Medienzuverlässigkeit von Medientypen für Audio, Video, Anwendungsfreigabe und videobasierte Bildschirmübertragung ermittelt werden. Die für einen Medientyp spezifischen Dimensionen, Kennzahlen und Filter weisen das Präfix „Audio", „Video", „AppSharing" oder „VBSS" auf.
  
![Call Quality Dashboard Dimensions.](../images/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
Wenn Sie die Dimensionen und Kennzahlen für einen einzelnen Medientyp anzeigen möchten, müssen Sie möglicherweise die neue MediaType-Dimension sowie den neuen MediaType-Filter verwenden. Beispiel: Wenn ein Bericht die Gesamtzahl aller Sitzungen für verschiedene Medientypen enthalten soll, müssen Sie die MediaType-Dimension einbeziehen.
  
![Call Quality Dashboard Total Stream Count.](../images/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a>Verwandte Themen
[Einrichten von Skype für BA aufrufen](set-up-call-analytics.md)

[Verwenden Sie Analytics rufen Sie für die Problembehandlung bei schlechter Anrufqualität](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Unterschied zwischen Anruf Analytics und Anrufqualität Dashboard?](difference-between-call-analytics-and-call-quality-dashboard.md)
