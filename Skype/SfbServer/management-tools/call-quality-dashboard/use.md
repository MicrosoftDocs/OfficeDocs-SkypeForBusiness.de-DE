---
title: Verwenden des Anruf Qualitäts Dashboards für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec62b70f-885e-4272-b9d2-a574ea434b64
description: 'Zusammenfassung: Informationen zur Verwendung des Dashboards für die Anrufqualität. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 61b20062925f59474d387a022a92663e0ffcd6ba
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816664"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a>Verwenden des Anruf Qualitäts Dashboards für Skype for Business Server

**Zusammenfassung:** Informationen zur Verwendung des Dashboards für die Anrufqualität. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.

Mit der Funktion "Anrufqualität" (CQD) können IT-Experten aggregierte Daten verwenden, um Probleme beim Erstellen von Problemen mit der Medienqualität zu erkennen, indem Statistiken für Benutzergruppen verglichen werden, um Trends und Muster zu erkennen. CQD ist nicht auf die Lösung einzelner Anruf Probleme ausgerichtet, sondern auf das Identifizieren von Problemen und Lösungen, die für viele Benutzer gelten.

## <a name="call-quality-dashboard-user-guide"></a>Benutzerhandbuch für das Anrufqualitäts-Dashboard

CQD ist ein Webportal zum schnellen Erstellen und organisieren von Berichten auf der Grundlage von QoE-Daten (Quality of Experience). CQD stellt einen SSAS-Cube bereit, um die Daten in der QoE Metrics-Datenbank zu aggregieren, und ermöglicht es Administratoren, Berichte zu erstellen und zu ändern oder Untersuchungen in Echtzeit durchzuführen. Obwohl es möglich ist, über Excel direkt mit dem Cube zu verbinden, ist das Portal für verschiedene Workflows in Verbindung mit QoE-Daten optimiert. Zu den Daten gehören:

- Zwischengespeicherte Berichtsdaten für den schnellen Zugriff
- Tiefe Links zu Berichtsseiten für die Freigabe und Veröffentlichung von Informationen
- Optimierte Berichts Bearbeitung und-Erstellung sowie bearbeitbare Metadaten für Bericht Beschreibungen.

Darüber hinaus macht CQD Web-APIs verfügbar, mit denen Benutzerprogramm gesteuerten Zugriff auf die Cubedaten für die Verwendung in benutzerdefinierten Dashboards erhalten.

### <a name="feature-overview"></a>Funktionsübersicht

Wenn Sie das Dashboard für die Anrufqualität besuchen, sehen Sie den folgenden Bildschirm:

![Verwenden von CQD](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)

1. Im Bereich "Zusammenfassung" finden Sie den Kontext für den "Bericht Satz" (rechts).
2. Klicken Sie im Zusammenfassungs PaneReport auf "Bearbeiten", um die Eigenschaften der Ebene (einschließlich der Höhe der Y-Achse) einzustellen.
3. Mithilfe der Breadcrumb-Struktur können Sie die aktuelle Position in der Berichtssatz Hierarchie ermitteln.
4. Berichte mit Unterberichten werden mit einem blauen Link angezeigt. Klicken Sie auf den Link, um einen Drilldown zu den untergeordneten Berichten auszuführen.

Bewegen Sie den Mauszeiger über die Balkendiagramme und Trendlinien, um detaillierte Werte anzuzeigen. Der Bericht mit dem Fokus zeigt das Aktionsmenü: "Bearbeiten", "Klonen", "Löschen" und "herunterladen".

### <a name="default-reports"></a>Standardberichte

Wenn Sie zum ersten Mal auf das Dashboard-Portal für die Anrufqualität zugreifen, wird automatisch ein Standardsatz von Berichten erstellt. Diese Berichte werden manchmal als Systemberichte bezeichnet. Sie können diese Berichte frei ändern oder löschen oder erweitern, indem Sie neue Geschwister-und untergeordnete Berichte erstellen.

Auf der obersten Ebene zeigt der Bericht "Audio-Streams monatlich Trend" den monatlichen Trend für alle Audiostreams. Bewegen Sie den Mauszeiger über die Balken in einem Balkendiagramm, um eine detailliertere Ansicht der durch das Balkendiagramm dargestellten Daten anzuzeigen. Klicken Sie auf den Titel des monatlichen Trend Berichts für Audiostreams, um zum Bericht "verwalteter vs-nicht verwalteter Audiostreams" zu navigieren, in dem die Berichte zwischen verwalteten und nicht verwalteten anrufen aufgeteilt werden. Verwaltete Anrufe sind Anrufe, die innerhalb der Unternehmensfirewall über kabelgebundene Verbindungen getätigt werden. Zu den nicht verwalteten anrufen gehören Anrufe, die von außerhalb der Unternehmensfirewall getätigt werden, sowie alle Anrufe, die über WLAN erfolgen.

Der andere Bericht auf oberster Ebene wird als "vom Benutzer gemeldete Anruf Qualitätsbewertung-Histogramm" bezeichnet. Anruf Qualitätsbewertungen sind die Nummern, die Skype for Business-Benutzern am Ende eines Anrufs gegeben hat, um die Qualität des Anrufs anzugeben. Die Bewertungszahlen liegen zwischen 1 und 5, 1 ist die schlechteste und 5 ist die beste. Im Histogramm wird angezeigt, wie viele Audioanrufe innerhalb eines Monats mit welcher Zahl bewertet wurden.

Klicken Sie auf den Titel eines beliebigen Berichts, um in Berichte mit weiteren Filtern für die Daten zu navigieren. Bei den Systemberichten zeigt jeder Unterbericht eine Teilmenge der Daten an, die im übergeordneten Bericht verfügbar sind. Das Problemlösungsmodell ist einfach: untersuchen Sie, in welchem Unterbericht die Daten oder der Trend, der auf ein Problem hindeutet, auf und nach und nach den Problembereich einschränken. Durch die Möglichkeit, Unterberichte zu erstellen, können Sie eigene Vermutungen zur Ursache spezifischer Datentrends untersuchen.

### <a name="create-and-edit-reports"></a>Erstellen und Bearbeiten von Berichten

Klicken Sie im Aktionsmenü eines Berichts auf "Bearbeiten", um den Berichts-Editor anzuzeigen. Jeder Bericht basiert auf einer Abfrage im Cube. Ein Bericht ist die visuelle Darstellung der Daten, die von der jeweiligen Abfrage zurückgegeben werden. Der Berichts-Editor hilft Ihnen, diese Abfragen und die Anzeigeoptionen des Berichts zu bearbeiten. Wenn Sie den Berichts-Editor öffnen, sehen Sie Folgendes:

![Verwenden von CQD](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. Dimensionen, Kennzahlen und Filter werden im linken Bereich ausgewählt. Zeigen Sie mit der Maus auf einen der vorhandenen Werte, um eine Schaltfläche "x" anzuzeigen, mit der der Wert entfernt werden kann. Klicken Sie auf die Schaltfläche "Plus" neben einer Überschrift, um das Dialogfeld zu öffnen, in dem Sie eine neue Dimension, ein Measure oder einen Filter hinzufügen können.
2. Optionen für die Diagrammanpassung werden oben angezeigt.
3. Im Bericht-Editor ist eine Vorschau des Berichts verfügbar. 
4. Eine detaillierte Berichtbeschreibung kann mit dem Bearbeitungsfeld am unteren Rand erstellt werden.

### <a name="sparklines-in-tables"></a>Sparklines in Tabellen

Wenn StartDate.Month als Dimension hinzugefügt wird und die Daten als Trend in Tabellenform gerendert werden, können Balkendiagramme und Sparklines innerhalb der Tabellenzellen angezeigt werden. Bewegen Sie den Mauszeiger über das Balkendiagramm und die Sparklines, um die Werte für einzelne Monate anzuzeigen.

![Verwenden von CQD](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)

Damit die Balkendiagramme und Sparklines angezeigt werden, muss das Kontrollkästchen "Sparklines anzeigen" oben im Berichts-Editor aktiviert sein. Dadurch wird die Option Trend ausgewählt und der Monat nach unten verschoben, um die letzte Dimension zu sein, die auch durch Klicken auf month und mithilfe der nach-oben-und nach-unten-Taste erfolgen kann, um das Startdatum zu verschieben. Monat nach oben oder unten.

### <a name="settings"></a>Einstellungen

Das Menü "Einstellungen" enthält Links zu nützlichen Seiten wie dem System Status und zu den Seiten und befindet sich in der oberen rechten Ecke des Dashboards.

![Verwenden von CQD](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)

Ob Beschreibungen und Zeitstempel angezeigt werden, richtet sich nach den einzelnen Benutzern, und diese Einstellungen wirken sich nur auf die Version des Dashboards der einzelnen Benutzer aus, und Sie können den Berichtssatz nicht ändern, oder was andere Benutzer sehen. Durch das Löschen des Caches werden alle Abfragen veranlasst, die Daten aus dem Cube erneut zu laden, während beim Wiederherstellen der Standardwerte alle vom Benutzer erstellten oder geänderten Berichte gelöscht und der Systemberichts Satz neu erstellt wird – was ein Benutzer sehen würde, wenn er sich zum ersten Mal anmeldet.

Der Benutzer-Dashboard-Link führt zu einer Seite, auf der Benutzer andere CQD-Benutzer sehen und ihre Berichte durchsuchen können. Wenn Sie einen Berichtssatz freigeben möchten, kopieren Sie den Link in der URL-Leiste, und geben Sie ihn für einen anderen CQD-Benutzer frei. Dieser Link ist derselbe Link, den andere Benutzer auf der Seite "Benutzer Dashboard-Link" unter dem Nutzernamen sehen würden.

### <a name="supplying-subnet-information"></a>Bereitstellen von Informationen zu Subnetzen

Zusätzliche Informationen können angezeigt werden, wenn Website spezifische Informationen in die Archivdatenbank eingegeben werden, um Zuordnungsinformationen für Subnet-to-Building bereitzustellen (beispielsweise die Qualität von Kabel-oder drahtlos anrufen durch Gebäude).

Führen Sie mindestens die folgenden Tabellen aus, um diese Berichte zu erstellen:

- CqdBuilding
- CqdNetwork

In den Tabellen CqdBuildingType und CqdBuildingOwnershipType können zusätzliche Informationen zur Verfügung gestellt werden, sodass weitergehend gefiltert werden kann und Detailinformationen angezeigt werden können. 

Die für diese Tabellen verwendeten Daten sind wie folgt definiert:

**CqdBuilding**

|Spalte|Datentyp|Nullen zulassen?|Beschreibung|
|:-----|:-----|:-----|:-----|
|BuildingKey |int |Nein |Primärschlüssel für die Tabelle CqdBuilding. |
|BuildingName |varchar(80) |Nein |Gebäudename. |
|BuildingShortName |varchar(10) |Nein |Kürzere Version des Gebäudenamens. |
|OwnershipTypeId |int |Nein |Fremdschlüssel, entspricht einem der Einträge in der CqdBuildingOwners-Tabelle. |
|BuildingTypeId |int |Nein |Fremdschlüssel, entspricht einem der Einträge in der CqdBuildingType-Tabelle. |
|Breiten |float |Ja |Geografische Breite des Gebäudes. |
|Geografische Länge |float |Ja |Geografische Länge des Gebäudes. |
|CityName |varchar(30) |Ja |Name der Stadt, in dem sich das Gebäude befindet. |
|ZipCode |varchar(25) |Ja |Postleitzahl des Gebäudestandortes. |
|CountryShortCode |varchar(2) |Ja |Kodes gemäß ISO 3166-1 Alpha-2 für das Land, in dem sich das Gebäude befindet. |
|StateProvinceCode |varchar(3) |Ja |Abkürzung für Bundesland/Kanton, in dem sich das Gebäude befindet. |
|InsideCorp |bit |Ja |Bit gibt an, ob das Gebäudeteil des Unternehmensnetzwerks ist. |
|BuildingOfficeType |nvarchar(150) |Ja |Beschreibung des Bürogebäudetyps. |
|Region |varchar(25) |Ja |Region, in der sich das Gebäude befindet. |
|||||

**CqdNetwork**

|Spalte|Datentyp|Nullen zulassen?|Beschreibung|
|:-----|:-----|:-----|:-----|
|Netzwerk |varchar(25) |Nein |Subnetzadresse. |
|NetworkRange |tinyint |Ja |Subnetzmaske |
|NetworkNameID |int |Ja |Wird optional einer Reihe in der Tabelle CqdNetworkName zugeordnet. |
|BuildingKey |int |Ja |Fremdschlüssel, entspricht einem der Einträge in der CqdBuilding-Tabelle. |
|UpdatedDate |datetime |Nein |Datum, an dem der Eintrag zuletzt aktualisiert wurde. |
||||||

Standardmäßig enthält die nächste Tabelle einen Eintrag (0; "unbekannt").

**CqdBuildingType**

|Spalte|Datentyp|Nullen zulassen?|Beschreibung|
|:-----|:-----|:-----|:-----|
|BuildingTypeId |int |Nein |Primärschlüssel für die Tabelle CqdBuildingType. |
|BuildingTypeDesc |char(18) |Nein |Beschreibung des Gebäudetyps. |
|||||

Standardmäßig enthält die nächste Tabelle einen Eintrag (0; "unbekannt"; 0; null).

**CqdBuildingOwnershipType**

|Spalte|Datentyp|Nullen zulassen?|Beschreibung|
|:-----|:-----|:-----|:-----|
|OwnershipTypeId |int |Nein |Primärschlüssel für die Tabelle CqdBuildingOwnershipType. |
|OwnershipTypeDesc |varchar(25) |Nein |Beschreibung des Besitztyps. |
|LeaseInd |tinyint |Ja |Index, der sich auf eine andere Reihe in der Tabelle CqdBuildingOwnershipType bezieht und zum Identifizieren geleaster Gebäude dient. |
|Besitzer |varchar(50) |Ja |Besitzer des Gebäudes. |
|||||

Standardmäßig enthält die nächste Tabelle einen Eintrag (0; "unbekannt"; 0; null).

**CqdBssid**

|Spalte|Datentyp|Nullen zulassen?|Beschreibung|
|:-----|:-----|:-----|:-----|
|bss |nvarchar(50) |Nein |Primärschlüssel für die Tabelle CqdBssid. Ist die BSSID des WLAN-Zugriffspunkts. |
|ess |nvarchar(50) |Ja |Controllerinformation zum WLAN-Zugriffspunkt. |
|phy |nvarchar(50) |Ja |Phy-Information. |
|ap |nvarchar(50) |Ja |Name des WLAN-Zugriffspunkts. |
|Gebäude |nvarchar(500) |Ja |Der Name des Gebäudes, in dem sich der WLAN-Zugriffspunkt befindet. |
||||

## <a name="cqd-streams"></a>CQD-Streams

Ein CQD-Datenstrom wird als "gut", "schlecht" oder "nicht klassifiziert" angesehen. CQM 1.5 verwendet jetzt die folgende CQD-Definition:

- Ein schlechter Datenstrom ist eine beliebige Kombination der schlechten Anruf Metriken jenseits der Schwelle.
- Wenn ein Datenstrom in einem Anruf schlecht ist, werden beide Streams des Anrufs als "schlecht" gekennzeichnet. In Konferenzen wird jeder Teilnehmer als einmaliger Anruf gewertet und unabhängig von allen anderen gemeldet.
- Nicht klassifizierte Datenströme sind Datenströme ohne Qualitätsmetrik (also synthetische Transaktionen oder kurze Anrufe).
- Gültige Streams = Nicht-Mobile-Clients
- Klassifizierung kann nicht geändert werden

**Definition/Klassifizierung für Anrufe schlechter Qualität**

|Metrik|Grenzwert|
|:-----|:-----|
|DegradationAvg |Größer als 1.0 (-1 Netzwerk-MOS) |
|RoundTrip |Größer als 500  |
|PacketLossRate |Größer als 0,1 (10%) |
|JitterInterArrival |Größer als 30  |
|RatioConcealedSamplesAvg |Größer als 0,07 |
|||

JPDR-Definition = Definition für Anrufe schlechter Qualität minus RatioConcealedSamplesAvg 

## <a name="where-is-callercallee"></a>Wo befindet sich der Anrufer/Angerufene?

CQD verwendet nicht die Felder "Anrufer/aufgerufener", sondern "First" und "Second", da zwischen dem Anrufer und dem angerufenen dazwischenliegende Schritte vorhanden sind.

 **Zuerst** Ist immer der Serverendpunkt (beispielsweise AV MCU oder Vermittlungsserver), wenn ein Server am Datenstrom beteiligt ist.

 **Zweiter** Ist immer der Client-Endpunkt, falls es sich nicht um einen Server-Server-Stream handelt. 

**Beispiel für eine Erst- und Zweitklassifizierung**

|Endpunkt 1 UAType |Endpunkt 2 UUAType |Erster|Zweiter|
|:-----|:-----|:-----|:-----|
|2 (AVMCU)  |4 (Skype for Business)  |Endpunkt 1 |Endpunkt 2 |
|2 (AVMCU)  |1 (mMediationServer)  |Endpunkt 2 |Endpunkt 1 |
|4 (Skype for Business) |4 (Skype for Business)  |Der Anrufer in MediaLine  |Der Angerufene in MMediaLine  |
|||||

Wenn beide Endpunkte vom gleichen Typ sind, wird von CQD zuerst der Anrufer-Eintrag und dann der zweite aufgerufen. Weitere Informationen zu Endpunktnamen finden Sie in [diesem Blog](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx).

## <a name="accounting-for-vpn"></a>VPN-Kontoerstellung

Wenn VPN-Lösung bekannt ist, dass die VPN-Kennzeichnung genau eingestellt ist, sind Sie ganz eingestellt. Verwenden Sie andernfalls eine der folgenden Methoden:

- Erstellen Sie einen Netzwerktyp mit dem Namen VPN (empfehlenswert) und weisen Sie anschließend VPN-Subnetze mit diesem neuen VPN-Netzwerktyp zu.
- Erstellen Sie ein Gebäude mit dem Namen VPN und weisen Sie anschließend VPN-Subnetze mit diesem Gebäude zu. 

## <a name="query-fundamentals"></a>Abfragegrundsätze

Eine gut formulierte Abfrage enthält die folgenden drei Parameter: 

- Kennzahl
- Dimension
- Filter

Hier ist ein Beispiel für eine gut formulierte Abfrage: "Show me Poor Streams [Measurement] by Subnet [Dimension] for Building 6 [Filter].“

## <a name="what-does-union-do"></a>Welche Funktion hat UNION?

Union ermöglicht das Filtern von Bedingungen mit dem und-Operator. Es gibt Szenarien, in denen Sie mehrere Filter Bedingungen zusammen kombinieren können, um ein Ergebnis zu erzielen, das einem oder-Vorgang ähnelt.

Beispiel: um alle Datenströme aus einem Gebäude abzurufen, bietet Union eine unterschiedliche Ansicht des zusammengeführten Datasets. Fügen Sie zur Verwendung von UNION einen allgemeinen Text in das UNION-Feld für die beiden Filterbedingungen, die Sie zusammenführen möchten.

## <a name="default-report-breakdown"></a>Standard-Berichtsübersicht

Falls Wireless intern verwaltet wird, können Sie die Wireless-Berichte im Bucket „Verwaltet“ erneut erstellen. 

![CQD-Berichtsübersicht](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)

## <a name="operational-processes"></a>Operative Prozesse

Überprüfen und beheben Sie zuerst verwaltete Datenströme. Die Qualität sollte in diesem Bereich zu 100 % unter Ihrer Kontrolle und daher am leichtesten zu warten sein.

### <a name="managed-streams"></a>Verwaltete Systeme 

Überprüfen und warten Sie verwaltete Streams in der folgenden Reihenfolge: 

1. Server-Server 
2.  Server-Wired-Inside
3. Wired-Wired-Inside 

### <a name="unmanaged-streams"></a>Nicht verwaltete Streams

Überprüfen und warten Sie nicht verwaltete Streams in der folgenden Reihenfolge: 

1. Server-Wifi-Inside
2. Server-Wired-Outside
3. Server-Wifi-Outside
4. Wired-Outside-Direct
5. Wired-Outside-Relay
6. Andere nicht verwaltete Streams
