---
title: Verwenden des Anrufqualitätsdashboards für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec62b70f-885e-4272-b9d2-a574ea434b64
description: 'Zusammenfassung: Erfahren Sie mehr über die Verwendung des Anrufqualitätsdashboards. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: d4787671955159d2bef0144872c50caccbbbb8eb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098961"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a>Verwenden des Anrufqualitätsdashboards für Skype for Business Server

**Zusammenfassung:** Erfahren Sie mehr über die Verwendung des Anrufqualitätsdashboards. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.

Mit dem Call Quality Dashboard (CQD) können IT-Profis aggregierte Daten verwenden, um Probleme bei der Medienqualität zu identifizieren, indem sie Statistiken für Benutzergruppen vergleichen, um Trends und Muster zu identifizieren. CQD konzentriert sich nicht auf die Lösung einzelner Anrufprobleme, sondern auf die Identifizierung von Problemen und Lösungen, die für viele Benutzer gelten.

## <a name="call-quality-dashboard-user-guide"></a>Benutzerhandbuch für das Anrufqualitätsdashboard

CQD ist ein Webportal zum schnellen Erstellen und Organisieren von Berichten basierend auf QoE-Daten (Quality of Experience). CQD stellt einen SSAS-Cube bereit, um die Daten in der QoE-Metrikdatenbank zu aggregieren, und ermöglicht Es Administratoren, Berichte zu erstellen und zu ändern oder Untersuchungen in Echtzeit durchzuführen. Es ist zwar möglich, mit Excel eine direkte Verbindung mit dem Cube herzustellen, das Portal ist jedoch für mehrere Workflows mit QoE-Daten optimiert. Die Daten umfassen:

- Zwischengespeicherte Berichtsdaten für schnellen Zugriff
- Tiefe Links zu Berichtsseiten für die Freigabe und Veröffentlichung von Informationen
- Optimierte Berichtsbearbeitung und -erstellung sowie bearbeitbare Metadaten für Berichtsbeschreibungen.

Darüber hinaus macht CQD Web-APIs verfügbar, die Benutzern programmgesteuerten Zugriff auf die Cubedaten für die Verwendung in benutzerdefinierten Dashboards ermöglichen.

### <a name="feature-overview"></a>Featureübersicht

Wenn Sie das Anrufqualitätsdashboard besuchen, wird der folgende Bildschirm angezeigt:

![Verwenden von CQD](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)

1. Im "Zusammenfassungsbereich" befindet sich der Kontext für den "Berichtssatz" (rechts).
2. Klicken Sie im Zusammenfassenden PaneReport auf "Bearbeiten", um Ebeneneigenschaften (einschließlich höhe der Y-Achse) festlegen zu können.
3. Das Breadcrumb hilft Ihnen, Ihren aktuellen Speicherort innerhalb der Berichtssatzhierarchie zu identifizieren.
4. Berichte mit Unterberichten werden mit einem blauen Link angezeigt. Klicken Sie auf den Link, um einen Drilldown zu den untergeordneten Berichten zu erstellen.

Bewegen Sie die Maus über die Balkendiagramme und Trendlinien, um detaillierte Werte anzuzeigen. Der Bericht mit dem Fokus zeigt das Aktionsmenü an: "Bearbeiten", "Klonen", "Löschen" und "Herunterladen".

### <a name="default-reports"></a>Standardberichte

Wenn Sie zum ersten Mal auf das Anrufqualitätsdashboard-Portal zugreifen, wird automatisch ein Standardsatz von Berichten erstellt. Diese Berichte werden manchmal als Systemberichte bezeichnet. Sie können diese Berichte frei ändern oder löschen oder erweitern, indem Sie neue gleichgeordnete und untergeordnete Berichte erstellen.

Auf der obersten Ebene zeigt der Bericht "Monatlicher Trend für Audiostreams" den monatlichen Trend für alle Audiostreams. Bewegen Sie die Maus über die Balken in einem Balkendiagramm, um eine detailliertere Ansicht der durch das Balkendiagramm dargestellten Daten zu erhalten. Klicken Sie auf den Titel des Monatlichen Trendberichts "Audiostreams", um zum Bericht "Verwaltete und nicht verwaltete Audiodatenströme" zu navigieren, in dem die Berichte zwischen verwalteten und nicht verwalteten Anrufen aufgeteilt werden. Bei verwalteten Anrufen handelt es sich um Anrufe innerhalb der Unternehmensfirewall über kabelgebundene Verbindungen. Nicht verwaltete Anrufe umfassen Anrufe von außerhalb der Unternehmensfirewall und alle Anrufe, die über WLAN vorgenommen werden.

Der andere Bericht auf oberster Ebene wird als "Vom Benutzer gemeldetes Histogramm für die Anrufqualitätsbewertung" bezeichnet. Anrufqualitätsbewertungen sind die Nummern, die von Skype for Business-Benutzern am Ende eines Anrufs angegeben werden, um die Qualität des Anrufs anzugeben. Die Bewertungsnummern liegen zwischen 1 und 5, 1 ist die schlechteste und 5 die beste. Das Histogramm zeigt die Anzahl der Audioanrufe an, die die angegebene Bewertung in einem Monat hatten.

Klicken Sie auf den Titel eines der Berichte, um in Berichte mit weiteren Filtern für die Daten zu navigieren. In den Systemberichten zeigt jeder untergeordnete Bericht eine Teilmenge der im übergeordneten Bericht verfügbaren Daten an. Das Problemlösungsmodell ist einfach: Untersuchen Sie, auf welchen Unterbericht die Daten oder Der Trend, auf den ein Problem hindeggeriert wird, beschränkt sind, und beschränken Sie den Problemraum schrittweise. Die Möglichkeit zum Erstellen von Unterberichten ermöglicht es Ihnen, Ihre eigenen Vermutungen zur Ursache bestimmter Datentrends zu untersuchen.

### <a name="create-and-edit-reports"></a>Erstellen und Bearbeiten von Berichten

Klicken Sie im Aktionsmenü eines Berichts auf "Bearbeiten", um den Berichts-Editor anzuzeigen. Jeder Bericht wird durch eine Abfrage in den Cube gesichert. Ein Bericht ist eine Visualisierung der von der Abfrage zurückgegebenen Daten. Der Berichts-Editor hilft Ihnen beim Bearbeiten dieser Abfragen und der Anzeigeoptionen des Berichts. Wenn Sie den Berichts-Editor öffnen, sehen Sie:

![Verwenden von CQD](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. Dimensionen, Measures und Filter werden im linken Bereich ausgewählt. Zeigen Sie auf einen der vorhandenen Werte, um eine Schaltfläche "x" zu zeigen, mit der der Wert entfernt werden kann. Klicken Sie auf die Schaltfläche "Plus" neben einer Überschrift, um das Dialogfeld zu öffnen, in dem Sie eine neue Dimension, ein neues Maß oder eine neue Filterung hinzufügen können.
2. Optionen für die Diagrammanpassung werden oben angezeigt.
3. Eine Vorschau des Berichts ist im Berichts-Editor verfügbar.
4. Eine detaillierte Berichtsbeschreibung kann mit dem Bearbeitungsfeld am unteren Rand erstellt werden.

### <a name="sparklines-in-tables"></a>Sparklines in Tables

Wenn StartDate.Month als Dimension hinzugefügt wird und die Daten als Trend in Tabellenform gerendert werden, können Balkendiagramme und Sparklines innerhalb der Tabellenzellen angezeigt werden. Bewegen Sie den Mauszeiger über das Balkendiagramm und die Sparklines, um die Werte für einzelne Monate zu zeigen.

![Verwenden von CQD](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)

Damit die Balkendiagramme und Sparklines angezeigt werden, muss das Kontrollkästchen Sparklines anzeigen oben im Berichts-Editor aktiviert sein. Dadurch wird die Option Trend ausgewählt und Month nach unten verschoben, um die letzte Dimension zu sein. Dies kann auch erreicht werden, indem Sie auf Monat klicken und die Pfeile nach oben und unten verwenden, um StartDate.Month nach oben oder unten zu verschieben.

### <a name="settings"></a>Einstellungen

Das Menü Einstellungen enthält Links zu nützlichen Seiten wie den Seiten Systemintegologie und Informationen und befindet sich in der oberen rechten Ecke des Dashboards.

![Verwenden von CQD](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)

Ob Beschreibungen und Zeitstempel angezeigt werden sollen, liegt bei einzelnen Benutzern, und diese Einstellungen wirken sich nur auf die Version des Dashboards aus und ändern nicht den Berichtssatz oder das, was andere Benutzer sehen. Wenn Sie den Cache löschen, laden alle Abfragen ihre Daten aus dem Cube neu, während beim Wiederherstellen von Standardeinstellungen alle vom Benutzer erstellten oder geänderten Berichte gelöscht und der Systemberichtssatz neu erstellt wird – was einem Benutzer bei der ersten Anmeldung angezeigt wird.

Der Link Benutzerdashboard zeigt eine Seite, auf der Benutzer andere Benutzer von CQD anzeigen und ihre Berichte durchsuchen können. Wenn Sie einen Berichtssatz freigeben möchten, kopieren Sie den Link in der URL-Leiste, und geben Sie ihn für einen anderen CQD-Benutzer weiter. Dieser Link ist der gleiche Link, den andere Benutzer auf der Seite Benutzerdashboardlink unter dem Benutzernamen des Benutzers sehen würden.

### <a name="supplying-subnet-information"></a>Bereitstellen von Subnetzinformationen

Zusätzliche Informationen können angezeigt werden, wenn standortspezifische Informationen in die Archivdatenbank eingegeben werden, um Subnetz-zu-Gebäude-Zuordnungsinformationen (z. B. kabelgebundene/drahtlose Anrufqualität durch Gebäude) zur Verfügung zu stellen.

Füllen Sie mindestens die folgenden Tabellen aus, um diese Berichte zu erstellen:

- CqdBuilding
- CqdNetwork

Zusätzliche Informationen können in den Tabellen CqdBuildingType und CqdBuildingOwnershipType bereitgestellt werden, um weitere Filterungen und Drilldowns zu ermöglichen.

Die für diese Tabellen verwendeten Daten sind wie folgt definiert:

**CqdBuilding**

|Spalte|Datentyp|Nullen zulassen?|Details|
|:-----|:-----|:-----|:-----|
|BuildingKey |int |Nein |Primärschlüssel für die CqdBuilding-Tabelle. |
|BuildingName |varchar(80) |Nein |Gebäudename. |
|BuildingShortName |varchar(10) |Nein |Kürzere Version des Gebäudenamens. |
|OwnershipTypeId |int |Nein |Fremdschlüssel, entspricht einem der Einträge in der Tabelle CqdBuildingOwners. |
|BuildingTypeId |int |Nein |Fremdschlüssel, entspricht einem der Einträge in der Tabelle CqdBuildingType. |
|Breitengrad |Gleitkommazahl |Ja |Breite des Gebäudes. |
|Längengrad |Gleitkommazahl |Ja |Längengrad des Gebäudes. |
|CityName |varchar(30) |Ja |Ortsname, in dem sich das Gebäude befindet. |
|ZipCode |varchar(25) |Ja |Postleitzahl, in der sich das Gebäude befindet. |
|CountryShortCode |varchar(2) |Ja |ISO 3166-1 alpha-2-Codes für das Land, in dem sich das Gebäude befindet. |
|StateProvinceCode |varchar(3) |Ja |Abkürzung mit drei Buchstaben für das Bundesland/die Provinz, in dem sich das Gebäude befindet. |
|InsideCorp |bit |Ja |Bit gibt an, ob das Gebäude Teil des Unternehmensnetzwerks ist. |
|BuildingOfficeType |nvarchar(150) |Ja |Beschreibung des Gebäudebürotyps. |
|Region |varchar(25) |Ja |Region, in der sich das Gebäude befindet. |
|||||

**CqdNetwork**

|Spalte|Datentyp|Nullen zulassen?|Details|
|:-----|:-----|:-----|:-----|
|Netzwerk |varchar(25) |Nein |Subnetzadresse. |
|NetworkRange |tinyint |Ja |Subnetzmaske |
|NetworkNameID |int |Ja |Ordnet optional eine Zeile in der CqdNetworkName-Tabelle zu. |
|BuildingKey |int |Ja |Fremdschlüssel, entspricht einem der Einträge in der CqdBuilding-Tabelle. |
|UpdatedDate |Datum/Uhrzeit |Nein |Datetime für den Zeitpunkt, zu dem der Eintrag zuletzt aktualisiert wurde. |
||||||

Standardmäßig verfügt diese nächste Tabelle über einen Eintrag (0, "Unbekannt").

**CqdBuildingType**

|Spalte|Datentyp|Nullen zulassen?|Details|
|:-----|:-----|:-----|:-----|
|BuildingTypeId |int |Nein |Primärschlüssel für die CqdBuildingType-Tabelle. |
|BuildingTypeDesc |char(18) |Nein |Beschreibung des Gebäudetyps. |
|||||

Standardmäßig verfügt diese nächste Tabelle über einen Eintrag (0, "Unbekannt", 0, Null).

**CqdBuildingOwnershipType**

|Spalte|Datentyp|Nullen zulassen?|Details|
|:-----|:-----|:-----|:-----|
|OwnershipTypeId |int |Nein |Primärschlüssel für die Tabelle CqdBuildingOwnershipType. |
|OwnershipTypeDesc |varchar(25) |Nein |Beschreibung des Besitztyps. |
|LeaseInd |tinyint |Ja |Index, der auf eine andere Zeile in der Tabelle CqdBuildingOwnershipType bezugt, die zum Identifizieren von geleachten Gebäuden verwendet wird. |
|Besitzer |varchar(50) |Ja |Gebäudebesitzer. |
|||||

Standardmäßig verfügt diese nächste Tabelle über einen Eintrag (0, "Unbekannt", 0, Null).

**CqdBssid**

|Spalte|Datentyp|Nullen zulassen?|Details|
|:-----|:-----|:-----|:-----|
|bss |nvarchar(50) |Nein |Primärschlüssel für die CqdBssid-Tabelle. Ist die BSSID des WLAN-Zugriffspunkts. |
|ess |nvarchar(50) |Ja |Wifi Access Point Controller-Informationen. |
|phy |nvarchar(50) |Ja |Phy-Informationen. |
|ap |nvarchar(50) |Ja |Name des Wlan-Zugriffspunkts. |
|Erstellen |nvarchar(500) |Ja |Der Gebäudename, in dem sich der WLAN-Zugriffspunkt befindet. |
||||

## <a name="cqd-streams"></a>CQD-Datenströme

Ein CQD-Stream wird als gut, schlecht oder nicht klassifiziert betrachtet. CQM 1.5 verwendet nun die folgende CQD-Definition:

- Ein schlechter Datenstrom ist eine beliebige Kombination der Metriken schlechter Anrufe über den Schwellenwert hinaus.
- Wenn ein Datenstrom in einem Anruf schlecht ist, sind beide Datenströme des Anrufs als schlecht gekennzeichnet. In Konferenzen wird jeder Teilnehmer als eindeutiger Anruf gezählt und unabhängig von allen anderen gemeldet.
- Nicht klassifizierte Datenströme sind Datenströme ohne Qualitätsmetriken (d. h. synthetische Transaktionen oder kurze Anrufe).
- Gültige Datenströme = nicht mobile Clients
- Klassifizierung kann nicht geändert werden

**Definition/Klassifizierung schlechter Anrufe**

|Metrik|Schwellenwert|
|:-----|:-----|
|DegradationAvg |Größer als 1,0 (-1 Netzwerk-MOS) |
|RoundTrip |Größer als 500 |
|PacketLossRate |Größer als 0,1 (10 %) |
|JitterInterArrival |Größer als 30 |
|RatioConcealedSamplesAvg |Größer als 0,07 |
|||

JPDR-Definition = Schlechte Anrufdefinition minus RatioConcealedSamplesAvg

## <a name="where-is-callercallee"></a>Wo befindet sich Caller/Callee?

CQD verwendet keine Caller/Callee-Felder, sondern "First" und "Second", da zwischen dem Anrufer und dem Anrufer Dazwischenschritte unternommen werden.

 **First** Ist immer der Serverendpunkt (z. B. AV MCU oder Vermittlungsserver), wenn ein Server am Datenstrom beteiligt ist.

 **Second** Wird immer der Clientendpunkt sein, es sei denn, es handelt sich um Server-Server Datenstrom.

**Beispiel für erste und zweite Klassifizierung**

|Endpunkt 1 UAType|Endpunkt 2 UUAType|Erster|Zweiter|
|:-----|:-----|:-----|:-----|
|2 (AVMCU) |4 (Skype for Business) |Endpunkt 1 |Endpunkt 2 |
|2 (AVMCU) |1 (mMediationServer) |Endpunkt 2 |Endpunkt 1 |
|4 (Skype for Business) |4 (Skype for Business) |Der Anrufer in MediaLine |Der Anrufer in MMediaLine |
|||||

Wenn beide Endpunkte denselben Typ haben, macht CQD den Anrufereintrag First und den Callee Second. Weitere Informationen zu Endpunktnamen finden Sie in [diesem Blog](/archive/blogs/jenstr/call-quality-dashboard-tips-and-tricks).

## <a name="accounting-for-vpn"></a>Accounting for VPN

Wenn bekannt ist, dass die VPN-Lösung das VPN-Flag genau festgelegt hat, sind Sie alle festgelegt. Verwenden Sie andernfalls eine der folgenden Methoden:

- Erstellen Sie einen Netzwerktyp namens VPN (bevorzugt), und ordnen Sie diesem neuen VPN NetworkType VPN-Subnetze zu.
- Erstellen Sie ein Gebäude mit dem Namen VPN, und ordnen Sie diesem Gebäude dann VPN-Subnetze zu.

## <a name="query-fundamentals"></a>Grundlagen der Abfrage

Eine wohlgeformte Abfrage enthält alle drei folgenden Parameter:

- Maß
- Dimension
- Filter

Ein Beispiel für eine wohlgeformte Abfrage wäre "Show me Poor Streams [Measurement] by Subnet [Dimension] for Building 6 [Filter]."

## <a name="what-does-union-do"></a>Was macht UNION?

Union ermöglicht ihnen das Filtern von Bedingungen mit dem AND-Operator. Es gibt Szenarien, in denen Sie mehrere Filterbedingungen kombinieren können, um ein Ergebnis zu erzielen, das einem OR-Vorgang ähnelt.

Beispiel: Union bietet eine unterschiedliche Ansicht des zusammengeführten Datasets, um alle Datenströme aus einem Gebäude zu erhalten. Um die UNION zu verwenden, fügen Sie allgemeinen Text in das Feld UNION für die beiden Filterbedingungen ein, die Sie UNION verwenden möchten.

## <a name="default-report-breakdown"></a>Standardberichtsaufschlüsselung

Wenn Wireless intern verwaltet wird, können Sie die Drahtlosberichte im Verwalteten Bucket neu erstellen.

![Aufschlüsselung des CQD-Berichts](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)

## <a name="operational-processes"></a>Operative Prozesse

Überprüfen und besen sie zuerst verwaltete Datenströme. Die Qualität in diesem Bereich sollte zu 100 % innerhalb Ihres Steuerelements liegen und daher am einfachsten behoben werden.

### <a name="managed-streams"></a>Verwaltete Datenströme

Überprüfen und Behebung verwalteter Datenströme in der folgenden Reihenfolge:

1. Server-Server
2. Server-Wired-Inside
3. Wired-Wired-Inside

### <a name="unmanaged-streams"></a>Nicht verwaltete Datenströme

Überprüfen und Behebung nicht verwalteter Datenströme in der folgenden Reihenfolge:

1. Server-Wifi-Inside
2. Server-Wired-Outside
3. Server-Wifi-Outside
4. Wired-Outside-Direct
5. Wired-Outside-Relay
6. Andere nicht verwaltete