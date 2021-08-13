---
title: Verwenden des Anrufqualitäts-Dashboards für Skype for Business Server
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
description: 'Zusammenfassung: Erfahren Sie mehr über die Verwendung des Anrufqualitäts-Dashboards. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: a2f5cbe503f914fe32b42119397be44ab82617cddd9951ab7064a2d08c0289f4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54317580"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a>Verwenden des Anrufqualitäts-Dashboards für Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie das Anrufqualitäts-Dashboard verwenden. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.

Das Anrufqualitätsdashboard (Call Quality Dashboard, CQD) ermöglicht IT-Experten die Verwendung aggregierter Daten, um Probleme bei der Medienqualität zu identifizieren, indem Statistiken für Benutzergruppen verglichen werden, um Trends und Muster zu identifizieren. CQD konzentriert sich nicht auf die Lösung einzelner Anrufprobleme, sondern auf die Identifizierung von Problemen und Lösungen, die für viele Benutzer gelten.

## <a name="call-quality-dashboard-user-guide"></a>Benutzerhandbuch für das Anrufqualitäts-Dashboard

CQD ist ein Webportal zum schnellen Erstellen und Organisieren von Berichten basierend auf QoE-Daten (Quality of Experience). CQD stellt einen SSAS-Cube bereit, um die Daten in der QoE-Metrikdatenbank zu aggregieren, und ermöglicht Administratoren das Erstellen und Ändern von Berichten oder das Durchführen von Untersuchungen in Echtzeit. Obwohl es möglich ist, Excel zu verwenden, um eine direkte Verbindung mit dem Cube herzustellen, ist das Portal für mehrere Workflows optimiert, die QoE-Daten betreffen. Die Daten umfassen:

- Zwischengespeicherte Berichtsdaten für den schnellen Zugriff
- Deep-Links zu Berichtsseiten für die Freigabe und Veröffentlichung von Informationen
- Optimiertes Bearbeiten und Erstellen von Berichten sowie bearbeitbare Metadaten für Berichtsbeschreibungen.

Darüber hinaus macht CQD Web-APIs verfügbar, die Benutzern programmgesteuerten Zugriff auf die Cubedaten zur Verwendung in benutzerdefinierten Dashboards gewähren.

### <a name="feature-overview"></a>Featureübersicht

Wenn Sie das Anrufqualitäts-Dashboard besuchen, wird der folgende Bildschirm angezeigt:

![Verwenden von CQD](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)

1. Im "Zusammenfassungsbereich" wird der Kontext für den "Berichtssatz" (rechts) gefunden.
2. Klicken Sie im Zusammenfassungsbereichsbericht auf "Bearbeiten", um Ebeneneigenschaften (einschließlich der Höhe der Y-Achse) festzulegen.
3. Der Breadcrumb hilft Ihnen bei der Identifizierung Ihrer aktuellen Position innerhalb der Berichtssatzhierarchie.
4. Berichte mit Unterberichten werden mit einem blauen Link angezeigt. Klicken Sie auf den Link, um einen Drilldown zu den untergeordneten Berichten anzuzeigen.

Bewegen Sie den Mauszeiger über die Balkendiagramme und Trendlinien, um detaillierte Werte anzuzeigen. Der Bericht, der den Fokus hat, zeigt das Aktionsmenü an: "Bearbeiten", "Klonen", "Löschen" und "Herunterladen".

### <a name="default-reports"></a>Standardberichte

Wenn Sie zum ersten Mal auf das Anrufqualitäts-Dashboard-Portal zugreifen, wird automatisch eine Standardgruppe von Berichten erstellt. Diese Berichte werden manchmal als Systemberichte bezeichnet. Sie können diese Berichte frei ändern oder löschen oder erweitern, indem Sie neue gleichgeordnete und untergeordnete Berichte erstellen.

Auf oberster Ebene zeigt der Bericht "Audio Streams Monatlicher Trend" den monatlichen Trend für alle Audiostreams an. Bewegen Sie den Mauszeiger über die Balken in einem Balkendiagramm, um eine detailliertere Ansicht der durch das Balkendiagramm dargestellten Daten anzuzeigen. Klicken Sie auf den Titel des Berichts "Audio Streams Monatlicher Trend", um zum Bericht "Verwaltetes und nicht verwaltetes Audio Streams" zu navigieren, in dem die Berichte zwischen verwalteten und nicht verwalteten Anrufen aufgeteilt werden. Verwaltete Anrufe sind Anrufe, die innerhalb der Unternehmensfirewall über kabelgebundene Verbindungen getätigt werden. Nicht verwaltete Anrufe umfassen Anrufe von außerhalb der Unternehmensfirewall und alle Anrufe, die über WLAN getätigt werden.

Der andere Bericht auf oberster Ebene heißt "Vom Benutzer gemeldetes Histogramm zur Anrufqualitätsbewertung". Anrufqualitätsbewertungen sind die Nummern, die von Skype for Business Benutzern am Ende eines Anrufs angegeben werden, um die Qualität des Anrufs anzugeben. Die Bewertungsnummern reichen von 1 bis 5, 1 ist die schlechteste und 5 die beste. Das Histogramm zeigt die Anzahl der Audioanrufe mit der angegebenen Bewertung in einem Monat an.

Klicken Sie auf den Titel eines der Berichte, um zu Berichten mit weiteren Filtern für die Daten zu navigieren. In den Systemberichten zeigt jeder untergeordnete Bericht eine Teilmenge der Daten an, die in seinem übergeordneten Bericht verfügbar sind. Das Problemlösungsmodell ist einfach: Untersuchen Sie, auf welchen Unterbericht die Daten oder den Trend beschränkt sind, auf die ein Problem vorgeschlagen wird, und schränken Sie den Problembereich schrittweise ein. Die Möglichkeit zum Erstellen von Unterberichten ermöglicht es Ihnen, Ihre eigenen Schätzungen zur Ursache bestimmter Datentrends zu untersuchen.

### <a name="create-and-edit-reports"></a>Erstellen und Bearbeiten von Berichten

Klicken Sie im Aktionsmenü eines Berichts auf "Bearbeiten", um den Bericht-Editor anzuzeigen. Jeder Bericht wird durch eine Abfrage im Cube gesichert. Ein Bericht ist eine Visualisierung der Daten, die von seiner Abfrage zurückgegeben werden. Der Bericht-Editor hilft Ihnen beim Bearbeiten dieser Abfragen und der Anzeigeoptionen des Berichts. Wenn Sie den Bericht-Editor öffnen, wird Folgendes angezeigt:

![Verwenden von CQD](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. Dimensionen, Kennzahlen und Filter werden im linken Bereich ausgewählt. Zeigen Sie auf einen der vorhandenen Werte, um eine "x"-Schaltfläche anzuzeigen, mit der der Wert entfernt werden kann. Klicken Sie auf die Schaltfläche "Plus" neben einer Überschrift, um das Dialogfeld zu öffnen, in dem Sie eine neue Dimension, Maßeinheit oder Filterung hinzufügen können.
2. Optionen für die Diagrammanpassung werden oben angezeigt.
3. Eine Vorschau des Berichts ist im Berichts-Editor verfügbar.
4. Eine detaillierte Berichtsbeschreibung kann mit dem Bearbeitungsfeld unten erstellt werden.

### <a name="sparklines-in-tables"></a>Sparklines in Tabellen

Wenn StartDate.Month als Dimension hinzugefügt wird und die Daten als Trend in Tabellenform gerendert werden, können Balkendiagramme und Sparklines innerhalb der Tabellenzellen angezeigt werden. Bewegen Sie den Mauszeiger über das Balkendiagramm und die Sparklines, um die Werte für einzelne Monate anzuzeigen.

![Verwenden von CQD](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)

Damit die Balkendiagramme und sparklines angezeigt werden, muss das Kontrollkästchen "Sparklines anzeigen" oben im Bericht-Editor aktiviert sein. Dadurch wird die Option "Trend" ausgewählt und "Monat nach unten" zur letzten Dimension verschoben. Dies kann auch erreicht werden, indem Sie auf "Monat" klicken und die Pfeile nach oben und unten verwenden, um StartDate.Month nach oben oder unten zu verschieben.

### <a name="settings"></a>Einstellungen

Das Einstellungsmenü enthält Links zu nützlichen Seiten wie den Seiten "Systemintegrität" und "Info" und befindet sich in der oberen rechten Ecke des Dashboards.

![Verwenden von CQD](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)

Ob Beschreibungen und Zeitstempel angezeigt werden sollen, hängt von einzelnen Benutzern ab, und diese Einstellungen wirken sich nur auf die Version des Dashboards der Person aus und ändern nicht den Berichtsatz oder das, was andere Benutzer sehen. Das Löschen des Caches bewirkt, dass alle Abfragen ihre Daten aus dem Cube neu laden, während beim Wiederherstellen der Standardwerte alle vom Benutzer erstellten oder geänderten Berichte gelöscht und der Systemberichtssatz neu erstellt wird – was einem Benutzer angezeigt wird, wenn er sich zum ersten Mal anmeldet.

Der Link "Benutzerdashboard" zeigt eine Seite an, auf der Benutzer andere Benutzer von CQD anzeigen und ihre Berichte durchsuchen können. Um einen Berichtsatz freizugeben, kopieren Sie den Link in der URL-Leiste, und geben Sie ihn für einen anderen CQD-Benutzer frei. Dieser Link ist der gleiche Link, den andere Benutzer auf der Seite "Link zum Benutzerdashboard" unter dem Benutzernamen des Benutzers sehen würden.

### <a name="supplying-subnet-information"></a>Bereitstellen von Subnetzinformationen

Zusätzliche Informationen können eingeblendet werden, wenn standortspezifische Informationen in die Archivdatenbank eingegeben werden, um Subnetz-zu-Gebäude-Zuordnungsinformationen bereitzustellen (z. B. Kabel-/Funkanrufqualität durch Gebäude).

Führen Sie mindestens die folgenden Tabellen aus, um diese Berichte zu erstellen:

- CqdBuilding
- CqdNetwork

Zusätzliche Informationen können in den Tabellen "CqdBuildingType" und "CqdBuildingOwnershipType" bereitgestellt werden, um weitere Filterung und Drilldowns zu ermöglichen.

Die für diese Tabellen verwendeten Daten sind wie folgt definiert:

**CqdBuilding**

|Spalte|Datentyp|Nullen zulassen?|Details|
|:-----|:-----|:-----|:-----|
|BuildingKey |Ganzzahl |Nein |Primärschlüssel für die Tabelle "CqdBuilding". |
|BuildingName |varchar(80) |Nein |Gebäudename. |
|BuildingShortName |varchar(10) |Nein |Kürzere Version des Gebäudenamens. |
|OwnershipTypeId |Ganzzahl |Nein |Fremdschlüssel, entspricht einem der Einträge in der Tabelle "CqdBuildingOwners". |
|BuildingTypeId |Ganzzahl |Nein |Fremdschlüssel, entspricht einem der Einträge in der CqdBuildingType-Tabelle. |
|Breitengrad |Gleitkommazahl |Ja |Breitengrad des Gebäudes. |
|Längengrad |Gleitkommazahl |Ja |Längengrad des Gebäudes. |
|Cityname |varchar(30) |Ja |Name der Stadt, in der sich das Gebäude befindet. |
|Postleitzahl |varchar(25) |Ja |Postleitzahl, in der sich das Gebäude befindet. |
|CountryShortCode |varchar(2) |Ja |ISO 3166-1 Alpha-2-Codes für das Land, in dem sich das Gebäude befindet. |
|StateProvinceCode |varchar(3) |Ja |Abkürzung aus drei Buchstaben für das Bundesland/die Provinz, in dem sich das Gebäude befindet. |
|InsideCorp |Bit |Ja |Bit gibt an, ob das Gebäude Teil des Unternehmensnetzwerks ist. |
|BuildingOfficeType |nvarchar(150) |Ja |Beschreibung des Gebäude-Office-Typs. |
|Region |varchar(25) |Ja |Region, in der sich das Gebäude befindet. |
|||||

**CqdNetwork**

|Spalte|Datentyp|Nullen zulassen?|Details|
|:-----|:-----|:-----|:-----|
|Netzwerk |varchar(25) |Nein |Subnetzadresse. |
|NetworkRange |Tinyint |Ja |Subnetzmaske |
|NetworkNameID |Ganzzahl |Ja |Optional wird eine Zeile in der CqdNetworkName-Tabelle zugeordnet. |
|BuildingKey |Ganzzahl |Ja |Fremdschlüssel, entspricht einem der Einträge in der CqdBuilding-Tabelle. |
|UpdatedDate |Datum/Uhrzeit |Nein |Datum und Uhrzeit der letzten Aktualisierung des Eintrags. |
||||||

Standardmäßig enthält diese nächste Tabelle einen Eintrag (0, 'Unbekannt').

**CqdBuildingType**

|Spalte|Datentyp|Nullen zulassen?|Details|
|:-----|:-----|:-----|:-----|
|BuildingTypeId |Ganzzahl |Nein |Primärschlüssel für die CqdBuildingType-Tabelle. |
|BuildingTypeDesc |char(18) |Nein |Beschreibung des Gebäudetyps. |
|||||

Standardmäßig enthält diese nächste Tabelle einen Eintrag (0, 'Unknown', 0, null).

**CqdBuildingOwnershipType**

|Spalte|Datentyp|Nullen zulassen?|Details|
|:-----|:-----|:-----|:-----|
|OwnershipTypeId |Ganzzahl |Nein |Primärschlüssel für die Tabelle "CqdBuildingOwnershipType". |
|OwnershipTypeDesc |varchar(25) |Nein |Beschreibung des Besitzertyps. |
|LeaseInd |Tinyint |Ja |Index, der auf eine andere Zeile in der Tabelle "CqdBuildingOwnershipType" verweist, die zum Identifizieren von geleasten Gebäuden verwendet wird. |
|Besitzer |varchar(50) |Ja |Gebäudebesitzer. |
|||||

Standardmäßig enthält diese nächste Tabelle einen Eintrag (0, 'Unknown', 0, null).

**CqdBssid**

|Spalte|Datentyp|Nullen zulassen?|Details|
|:-----|:-----|:-----|:-----|
|Bss |nvarchar(50) |Nein |Primärschlüssel für die CqdBssid-Tabelle. Ist die BSSID des WLAN-Zugriffspunkts. |
|Ess |nvarchar(50) |Ja |Informationen zum Wlan-Zugriffspunkt-Controller. |
|Phy |nvarchar(50) |Ja |Phy-Informationen. |
|Ld |nvarchar(50) |Ja |Name des WLAN-Zugriffspunkts. |
|Gebäude |nvarchar(500) |Ja |Der Gebäudename, in dem sich der WLAN-Zugriffspunkt befindet. |
||||

## <a name="cqd-streams"></a>CQD-Streams

Ein CQD-Datenstrom wird als gut, schlecht oder nicht klassifiziert betrachtet. CQM 1.5 verwendet jetzt die folgende CQD-Definition:

- Ein "schlechter Datenstrom" ist eine beliebige Kombination der Metriken für Anrufe schlechter Qualität, die den Schwellenwert überschreiten.
- Wenn ein Datenstrom in einem Anruf "schlecht" ist, werden beide Anrufströme als "schlecht" gekennzeichnet. In Konferenzen wird jeder Teilnehmer als eindeutiger Anruf gezählt und unabhängig von allen anderen teilnehmern gemeldet.
- Nicht klassifizierte Datenströme sind Datenströme ohne Qualitätsmetriken (also synthetische Transaktionen oder kurze Aufrufe).
- Gültige Streams = nicht mobile Clients
- Klassifizierer kann nicht geändert werden

**Schlechte Anrufdefinition/Klassifizierer**

|Metrik|Schwellenwert|
|:-----|:-----|
|DegradationAvg |Größer als 1,0 (-1 Netzwerk-MOS) |
|Roundtrip |Größer als 500 |
|PacketLossRate |Größer als 0,1 (10 %) |
|JitterInterArrival |Größer als 30 |
|RatioConcealedSamplesAvg |Größer als 0,07 |
|||

JPDR-Definition = Definition schlechter Anrufe minus RatioConcealedSamplesAvg

## <a name="where-is-callercallee"></a>Wo befindet sich der Anrufer/Angerufene?

CQD verwendet keine Felder für Anrufer/Angerufene, sondern "First" und "Second", da zwischen dem Aufrufer und dem Angerufenen dazwischen schritte vorhanden sind.

 **Zuerst** Ist immer der Serverendpunkt (z. B. AV MCU oder Vermittlungsserver), wenn ein Server am Datenstrom beteiligt ist.

 **Second** Ist immer der Clientendpunkt, es sei denn, es handelt sich um einen Server-Server-Datenstrom.

**Beispiel für die Klassifizierung "Erster und Zweiter"**

|Endpunkt 1 UAType|Endpunkt 2 UUAType|Erster|Zweiter|
|:-----|:-----|:-----|:-----|
|2 (AVMCU) |4 (Skype for Business) |Endpunkt 1 |Endpunkt 2 |
|2 (AVMCU) |1 (mMediationServer) |Endpunkt 2 |Endpunkt 1 |
|4 (Skype for Business) |4 (Skype for Business) |Der Anrufer in MediaLine |Der Angerufene in MMediaLine |
|||||

Wenn beide Endpunkte den gleichen Typ aufweisen, macht CQD den Anrufereintrag "First" und "Callee Second". Weitere Informationen zu Endpunktnamen finden Sie in [diesem Blog.](/archive/blogs/jenstr/call-quality-dashboard-tips-and-tricks)

## <a name="accounting-for-vpn"></a>Kontoführung für VPN

Wenn bekannt ist, dass die VPN-Lösung das VPN-Flag genau festgelegt hat, sind Sie alle festgelegt. Verwenden Sie andernfalls eine der folgenden Methoden:

- Erstellen Sie einen Netzwerktyp namens VPN (bevorzugt), und ordnen Sie diesem neuen VPN NetworkType VPN-Subnetze zu.
- Erstellen Sie ein Gebäude namens VPN, und ordnen Sie diesem Gebäude VPN-Subnetze zu.

## <a name="query-fundamentals"></a>Grundlegendes zu Abfragen

Eine wohlgeformte Abfrage enthält alle drei folgenden Parameter:

- Messung
- Dimension
- Filter

Ein Beispiel für eine wohlgeformte Abfrage wäre "Show me Poor Streams [Measurement] by Subnet [Dimension] for Building 6 [Filter]."

## <a name="what-does-union-do"></a>Was macht UNION?

Union ermöglicht es Ihnen, Bedingungen mit dem OPERATOR AND zu filtern. Es gibt Szenarien, in denen Sie mehrere Filterbedingungen kombinieren können, um ein Ähnliches wie bei einem OR-Vorgang zu erzielen.

Beispiel: Um alle Datenströme aus einem Gebäude abzurufen, bietet UNION eine unterschiedliche Ansicht des zusammengeführten Datasets. Um die UNION zu verwenden, fügen Sie allgemeinen Text in das UNION-Feld für die beiden Filterbedingungen ein, die Sie UNION verwenden möchten.

## <a name="default-report-breakdown"></a>Aufschlüsselung des Standardberichts

Wenn drahtlos intern verwaltet wird, können Sie die Drahtlosberichte im Bucket "Verwaltet" neu erstellen.

![Aufschlüsselung des CQD-Berichts](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)

## <a name="operational-processes"></a>Betriebliche Prozesse

Überprüfen und korrigieren Sie zuerst verwaltete Streams. Die Qualität in diesem Bereich sollte zu 100 % in Ihrer Kontrolle liegen und daher am einfachsten zu beheben sein.

### <a name="managed-streams"></a>Verwaltete Streams

Überprüfen und korrigieren Sie verwaltete Datenströme in der folgenden Reihenfolge:

1. Server-Server
2. Serververkabeltes Innenleben
3. Verkabelt-verkabelt-innen

### <a name="unmanaged-streams"></a>Nicht verwaltete Streams

Überprüfen und korrigieren Sie nicht verwaltete Datenströme in der folgenden Reihenfolge:

1. Server-Wifi-Inside
2. Serververkabelte Außenseite
3. Server-Wifi-Outside
4. Wired-Outside-Direct
5. Kabelgebundenes Außenrelay
6. Andere nicht verwaltete