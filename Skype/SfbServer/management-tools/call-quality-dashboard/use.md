---
title: Verwenden des Anruf Qualitäts Dashboards für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec62b70f-885e-4272-b9d2-a574ea434b64
description: 'Zusammenfassung: Informationen zur Verwendung des Dashboards für die Anrufqualität. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: b89f766cfcbfbc9fe2c700162f3c0b4e69a7e6bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274555"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a>Verwenden des Anruf Qualitäts Dashboards für Skype for Business Server
 
**Zusammenfassung:** Informationen zur Verwendung des Dashboards für die Anrufqualität. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.
  
Mit CQD können IT-Profis Daten aggregieren, um die Bereiche in ihrer Umgebung zu ermitteln, in denen die Medienqualität beeinträchtigt ist. CQD ermöglicht den Vergleich von Statistiken für verschiedene Benutzergruppen und die Ermittlung von Trends und Mustern. Dabei liegt der Schwerpunkt nicht auf der Lösung individueller Probleme mit Anrufen, sondern auf der Erkennung von Problemen und Lösungen, die auf viele Benutzer in einer bestimmten Umgebung anwendbar sind.
  
## <a name="call-quality-dashboard-user-guide"></a>Benutzerhandbuch für das Anrufqualitäts-Dashboard

Das Anrufqualitäts-Dashboard (Call Quality Dashboard, CQD) ist ein Webportal zum schnellen Erstellen und Organisieren von Berichten auf Grundlage von QoE-Daten (Quality of Experience). Das CQD stellt einen SSAS-Cube bereit, um die Daten in der Datenbank für QoE-Metriken zusammenzufassen. Dadurch erhalten Benutzer die Möglichkeit, Berichte zu erstellen und zu ändern und die Aktualisierungen der Berichte in Echtzeit anzuzeigen. Obwohl es möglich ist, über Excel direkt mit dem Cube zu verbinden, ist das Portal für verschiedene Workflows in Verbindung mit QoE-Daten optimiert. Dazu gehören die Zwischenspeicherung von Berichtsdaten für schnelles Zugreifen, Deep-Links zu Berichtsseiten zum Teilen und Veröffentlichen von Informationen, verbesserte Funktionen zum Bearbeiten und Erstellen von Berichten und bearbeitbare Metadaten für Berichtsbeschreibungen. Außerdem stellt CQD Web-APIs zur Verfügung, die Benutzern programmgesteuerten Zugriff auf die Cubedaten bieten, um diese in benutzerdefinierten Dashboards zu verwenden.  
  
### <a name="feature-overview"></a>Funktionsübersicht

Im Anrufqualitäts-Dashboard erwartet den Benutzer Folgendes:
  
![Verwenden von CQD](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)
  
1. Im Bereich "Zusammenfassung" finden Sie den Kontext für den "Bericht Satz" (rechts). 
    
2. Eigenschaften der Berichtssatz Ebene (einschließlich Höhe der Y-Achse) können durch Klicken auf "Bearbeiten" im Zusammenfassungsbereich eingestellt werden.
    
3. Die Breadcrumb-Navigation hilft Benutzern, ihren aktuellen Standort innerhalb der Berichtssatzhierarchie zu identifizieren.  
    
4. Berichte mit Unterberichten werden in blau angezeigt. Wenn Sie auf den Link klicken, können Sie Detailinformationen zu den untergeordneten Berichten anzeigen.  
    
Wenn Sie die Maus über die Balkendiagramme und Trendlinien bewegen, werden detaillierte Werte angezeigt. In dem Bericht, der den Fokus hat, wird das Aktionsmenü angezeigt: "Bearbeiten", "Klonen", "Löschen" und "herunterladen". 
  
### <a name="default-reports"></a>Standardberichte

Wenn ein Benutzer zum ersten Mal auf das Portal des Anrufqualitäts-Dashboards zugreift, werden automatisch einige Standardberichte erstellt. Diese Berichte werden manchmal als Systemberichte bezeichnet. Der Benutzer kann diese Berichte wahlweise ändern oder löschen. Im Allgemeinen erweitern Benutzer die Standardberichte, indem sie neben- und untergeordnete Berichte erstellen.  
  
Auf der obersten Ebene zeigt der Bericht "Audio-Streams monatlich Trend" den monatlichen Trend für alle Audiostreams. Wenn Sie den Mauszeiger über die Balken in einem Balkendiagramm bewegen, wird eine detailliertere Ansicht der durch das Balkendiagramm dargestellten Daten angezeigt. Durch Klicken auf den Titel des monatlichen Trend Berichts für Audiostreams wird zum Bericht "verwalteter vs-nicht verwalteter Audiostreams" gewechselt, in dem die Berichte zwischen verwalteten und nicht verwalteten anrufen aufgeteilt werden. Verwaltete Anrufe sind Anrufe, die innerhalb der Unternehmensfirewall über kabelgebundene Verbindungen getätigt werden. Zu den nicht verwalteten anrufen gehören Anrufe, die von außerhalb der Unternehmensfirewall getätigt werden, sowie alle Anrufe, die über WLAN erfolgen.
  
Der andere Bericht auf oberster Ebene wird als "vom Benutzer gemeldete Anruf Qualitätsbewertung-Histogramm" bezeichnet. Die Anrufqualitätsbewertungen sind die Zahlen, die Skype for Business-Benutzer am Ende eines Anrufes zur Qualitätsbewertung angeben. Das Bewertungsspektrum reicht von 1 bis 5, wobei 1 die schlechteste und 5 die beste Bewertung ist. Im Histogramm wird angezeigt, wie viele Audioanrufe innerhalb eines Monats mit welcher Zahl bewertet wurden. 
  
In der Regel werden die Berichte mit zusätzlichen Datenfiltern angezeigt, wenn Sie auf den Titel eines Berichts klicken. Bei den Systemberichten zeigt jeder Unterbericht eine Teilmenge der Daten an, die im übergeordneten Bericht verfügbar sind. So entsteht ein einfach aufgebautes Modell für die Problemlösung: Der Problembereich kann eingekreist werden, indem überprüft wird, zu welchem Unterbericht die problematischen Daten oder der problematische Trend gehört. Durch die Möglichkeit, neue Unterberichte zu erstellen, können Benutzer ihre eigenen Hypothesen bezüglich des Ursprungs bestimmter Datentrends überprüfen.
  
### <a name="creating-and-editing-reports"></a>Erstellen und Bearbeiten von Berichten

Wenn Sie im Aktionsmenü eines Berichts auf "Bearbeiten" klicken, wird der Bericht-Editor angezeigt. Jeder Bericht basiert auf einer Abfrage im Cube. Ein Bericht ist die visuelle Darstellung der Daten, die von der jeweiligen Abfrage zurückgegeben werden. Der Bericht-Editor ist eine Benutzerschnittstelle zum Bearbeiten dieser Abfragen sowie der Anzeigeoptionen des Berichts. Wenn ein Benutzer den Bericht-Editor öffnet, wird Folgendes angezeigt:
  
![Verwenden von CQD](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)
  
1. Dimensionen, Kennzahlen und Filter werden im linken Bereich ausgewählt. Wenn Sie auf einen der vorhandenen Werte zeigen, wird die Schaltfläche "x" angezeigt, mit der der Wert entfernt werden kann. Wenn Sie auf die Schaltfläche "Plus" neben einer Überschrift klicken, wird das Dialogfeld zum Hinzufügen einer neuen Bemaßung, eines Measures oder eines Filters geöffnet. 
    
2. Optionen für die Diagrammanpassung werden oben angezeigt.
    
3. Im Bericht-Editor ist eine Vorschau des Berichts verfügbar.  
    
4. Mithilfe des Eingabefelds unten kann eine ausführliche Berichtbeschreibung erstellt werden.  
    
### <a name="sparklines-in-tables"></a>Sparklines in Tabellen

Wenn StartDate.Month als Dimension hinzugefügt wird und die Daten als Trend in Tabellenform gerendert werden, können Balkendiagramme und Sparklines innerhalb der Tabellenzellen angezeigt werden. Wenn Sie den Mauszeiger über das Balkendiagramm und die Sparklines bewegen, werden Werte für die einzelnen Monate angezeigt.  
  
![Verwenden von CQD](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)
  
Damit die Balkendiagramme und Sparklines angezeigt werden, muss das Kontrollkästchen "Sparklines anzeigen" oben im Berichts-Editor aktiviert sein. Damit wählen Sie die Option Trend aus, und verschieben Sie Monat nach unten, um die letzte Dimension zu sein, die Sie auch erreichen können, indem Sie auf Monat klicken und die aufwärts-und Abwärtspfeile verwenden, um das Startdatum zu verschieben. Monat nach oben oder unten. 
  
### <a name="settings"></a>Einstellungen

Das Menü „Einstellungen“ in der oberen rechten Ecke des Dashboards enthält Links zu hilfreichen Seiten wie Seiten zur Systemintegrität und Info-Seiten.
  
![Verwenden von CQD](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)
  
Ob Beschreibungen und Zeitstempel angezeigt werden sollen, ist den einzelnen Benutzern überlassen, und diese Einstellungen wirken sich nur auf die Version des Dashboards des jeweiligen Benutzers aus, nicht auf den Bericht Satz oder auf die Anzeige anderer Benutzer. Durch das Löschen des Caches werden alle Abfragen dazu veranlasst, die Daten aus dem Cube erneut zu laden, während beim Wiederherstellen der Standardwerte alle vom Benutzer erstellten oder geänderten Berichte gelöscht und der Systemberichts Satz neu erstellt wird – was ein Benutzer beim erstmaligen Anmelden sehen würde.
  
Der Benutzer-Dashboard-Link führt zu einer Seite, auf der Benutzer andere CQD-Benutzer sehen und ihre Berichte durchsuchen können. Wenn Sie einen Berichtsatz teilen möchten, kopieren Sie einfach den Link in der URL-Leiste und geben Sie ihn an einen anderen CQD-Benutzer frei. Dieser Link wird mit dem identisch sein, den andere Benutzer auf der Seite "Benutzer Dashboard-Link" unter dem Nutzernamen sehen würden.
  
### <a name="supplying-subnet-information"></a>Bereitstellen von Informationen zu Subnetzen

Es können zusätzliche Einblicke gewährt werden, wenn Standort-spezifische Informationen in die Archivdatenbank eingegeben werden, um Subnetz-Gebäude-Zuordnungsinformationen (z. B. Anrufqualität nach Gebäude mit Kabel-/Funkverbindung) bereitzustellen.  
  
Es müssen mindestens die folgenden Tabellen ausgefüllt werden, um diese Berichte zu erstellen:
  
- CqdBuilding
    
- CqdNetwork
    
In den Tabellen CqdBuildingType und CqdBuildingOwnershipType können zusätzliche Informationen zur Verfügung gestellt werden, sodass weitergehend gefiltert werden kann und Detailinformationen angezeigt werden können.  
  
Das Schema für diese Tabellen sieht aus wie folgt:
  
**CqdBuilding**

|**Spalte**|**Datentyp**|**Nullen zulassen?**|**Details**|
|:-----|:-----|:-----|:-----|
|BuildingKey  <br/> |int  <br/> |Nein  <br/> |Primärschlüssel für die Tabelle CqdBuilding.  <br/> |
|BuildingName  <br/> |varchar(80)  <br/> |Nein  <br/> |Gebäudename.  <br/> |
|BuildingShortName  <br/> |varchar(10)  <br/> |Nein  <br/> |Kürzere Version des Gebäudenamens.  <br/> |
|OwnershipTypeId  <br/> |int  <br/> |Nein  <br/> |Fremdschlüssel, sollte mit einem der Einträge in der Tabelle CqdBuildingOwners übereinstimmen.  <br/> |
|BuildingTypeId  <br/> |int  <br/> |Nein  <br/> |Fremdschlüssel, sollte mit einem der Einträge in der Tabelle CqdBuildingType übereinstimmen.  <br/> |
|Geografische Breite  <br/> |float  <br/> |Ja  <br/> |Geografische Breite des Gebäudes.  <br/> |
|Geografische Länge  <br/> |float  <br/> |Ja  <br/> |Geografische Länge des Gebäudes.  <br/> |
|CityName  <br/> |varchar(30)  <br/> |Ja  <br/> |Name der Stadt, in dem sich das Gebäude befindet.  <br/> |
|ZipCode  <br/> |varchar(25)  <br/> |Ja  <br/> |Postleitzahl des Gebäudestandortes.  <br/> |
|CountryShortCode  <br/> |varchar(2)  <br/> |Ja  <br/> |Kodes gemäß ISO 3166-1 Alpha-2 für das Land, in dem sich das Gebäude befindet.  <br/> |
|StateProvinceCode  <br/> |varchar(3)  <br/> |Ja  <br/> |Abkürzung (3 Buchstaben) für das Land/die Region, in dem/der sich das Gebäude befindet.  <br/> |
|InsideCorp  <br/> |bit  <br/> |Ja  <br/> |Bit, das angibt, ob das Gebäude Teil des Unternehmensnetzwerks ist.  <br/> |
|BuildingOfficeType  <br/> |nvarchar(150)  <br/> |Ja  <br/> |Beschreibung des Bürogebäudetyps.  <br/> |
|Region  <br/> |varchar(25)  <br/> |Ja  <br/> |Region, in der sich das Gebäude befindet.  <br/> |
   
**CqdNetwork**

|**Spalte**|**Datentyp**|**Nullen zulassen?**|**Details**|
|:-----|:-----|:-----|:-----|
|Netzwerk  <br/> |varchar(25)  <br/> |Nein  <br/> |Subnetzadresse.  <br/> |
|NetworkRange  <br/> |tinyint  <br/> |Ja  <br/> |Subnetzmaske  <br/> |
|NetworkNameID  <br/> |int  <br/> |Ja  <br/> |Wird optional einer Reihe in der Tabelle CqdNetworkName zugeordnet.  <br/> |
|BuildingKey  <br/> |int  <br/> |Ja  <br/> |Fremdschlüssel, sollte mit einem der Einträge in der Tabelle CqdBuilding übereinstimmen.  <br/> |
|UpdatedDate  <br/> |datetime  <br/> |Nein  <br/> |Datum, an dem der Eintrag zuletzt aktualisiert wurde.  <br/> |
   
Standardmäßig enthält die nächste Tabelle einen Eintrag (0; "unbekannt").
  
**CqdBuildingType**

|**Spalte**|**Datentyp**|**Nullen zulassen?**|**Details**|
|:-----|:-----|:-----|:-----|
|BuildingTypeId  <br/> |int  <br/> |Nein  <br/> |Primärschlüssel für die Tabelle CqdBuildingType.  <br/> |
|BuildingTypeDesc  <br/> |char(18)  <br/> |Nein  <br/> |Beschreibung des Gebäudetyps.  <br/> |
   
Standardmäßig enthält die nächste Tabelle einen Eintrag (0; "unbekannt"; 0; null).
  
**CqdBuildingOwnershipType**

|**Spalte**|**Datentyp**|**Nullen zulassen?**|**Details**|
|:-----|:-----|:-----|:-----|
|OwnershipTypeId  <br/> |int  <br/> |Nein  <br/> |Primärschlüssel für die Tabelle CqdBuildingOwnershipType.  <br/> |
|OwnershipTypeDesc  <br/> |varchar(25)  <br/> |Nein  <br/> |Beschreibung des Besitztyps.  <br/> |
|LeaseInd  <br/> |tinyint  <br/> |Ja  <br/> |Index, der sich auf eine andere Reihe in der Tabelle CqdBuildingOwnershipType bezieht und zum Identifizieren geleaster Gebäude dient.  <br/> |
|Besitzer  <br/> |varchar(50)  <br/> |Ja  <br/> |Besitzer des Gebäudes.  <br/> |
   
Standardmäßig enthält die nächste Tabelle einen Eintrag (0; "unbekannt"; 0; null).
  
**CqdBssid**

|**Spalte**|**Datentyp**|**Nullen zulassen?**|**Details**|
|:-----|:-----|:-----|:-----|
|bss  <br/> |nvarchar(50)  <br/> |Nein  <br/> |Primärschlüssel für die Tabelle CqdBssid. Ist die BSSID der WLAN-Zugriffspunkts.  <br/> |
|ess  <br/> |nvarchar(50)  <br/> |Ja  <br/> |Controllerinformation zum WLAN-Zugriffspunkt.  <br/> |
|phy  <br/> |nvarchar(50)  <br/> |Ja  <br/> |Phy-Information.  <br/> |
|ap  <br/> |nvarchar(50)  <br/> |Ja  <br/> |Name des WLAN-Zugriffspunkts.  <br/> |
|Gebäude  <br/> |nvarchar(500)  <br/> |Ja  <br/> |Der Name des Gebäudes, in dem sich der WLAN-Zugriffspunkt befindet.  <br/> |
   
## <a name="cqd-streams"></a>CQD-Streams

Ein CQD-Stream kann von guter oder schlechter Qualität oder unqualifiziert sein. CQM 1.5 verwendet jetzt die folgende CQD-Definition:  
  
- Ein Stream von schlechter Qualität ist jede Kombination der schlechten Anrufmetriken, die den Grenzwert überschreiten.
    
- Wenn ein Datenstrom in einem Anruf schlecht ist, werden beide Streams des Anrufs als "schlecht" gekennzeichnet. In Konferenzen wird jeder Teilnehmer als einmaliger Anruf gewertet und unabhängig von allen anderen gemeldet.
    
- Nicht klassifizierte Streams sind Streams ohne Qualitätsmetriken (d. h. synthetische Transaktionen, kurze Anrufe).
    
- Gültige Streams = Nicht-Mobile-Clients
    
- Klassifizierung kann nicht geändert werden
    
**Definition/Klassifizierung für Anrufe schlechter Qualität**

|**Metrik**|**Grenzwert**|
|:-----|:-----|
|DDegradationAvg  <br/> |Größer als 1.0 (-1 Netzwerk-MOS)  <br/> |
|RoundTrip  <br/> |Größer als 500   <br/> |
|PacketLossRate  <br/> |Größer als 0,1 (10 %)   <br/> |
|JitterInterArrival  <br/> |Größer als 30   <br/> |
|RRatioConcealedSamplesAvg  <br/> |Größer als 0,07   <br/> |
   
JPDR-Definition = Definition für Anrufe schlechter Qualität minus RatioConcealedSamplesAvg  
  
## <a name="where-is-callercallee"></a>Wo befindet sich der Anrufer/Angerufene?

CQD verwendet keine Anrufer/anrufenden-Felder. Diese wurden in "First" und "Second" umbenannt, da zwischen dem Anrufer und dem angerufenen dazwischenliegende Schritte vorhanden sind.
  
 **Erster** Ist immer der Server-Endpunkt (z. B. AV-MCU; Vermittlungsserver) wenn ein Server am Stream beteiligt ist.
  
 **Zweiter** Ist immer der Client-Endpunkt, falls es sich nicht um einen Server-Server-Stream handelt. 
  
**Beispiel für eine Erst- und Zweitklassifizierung**

|**Endpunkt 1 UAType **|**Endpunkt 2 UUAType **|**Erster**|**Zweiter**|
|:-----|:-----|:-----|:-----|
|2 (AVMCU)   <br/> |4 (Skype for Business)   <br/> |Endpunkt 1  <br/> |Endpunkt 2  <br/> |
|2 (AVMCU)   <br/> |1 (mMediationServer)   <br/> |Endpunkt 2  <br/> |Endpunkt 1  <br/> |
|4 (Skype for Business)  <br/> |4 (Skype for Business)   <br/> |Der Anrufer in MediaLine   <br/> |Der Angerufene in MMediaLine  <br/> |
   
Falls beide Endpunkte denselben Typ aufweisen, legt CQD den Anrufer als Ersten fest, sodass der Angerufene zum Zweiten wird. Weitere Informationen finden Sie in [diesem Blog](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx) .
  
## <a name="accounting-for-vpn"></a>VPN-Kontoerstellung

Wenn VPN-Lösung bekannt ist, dass die VPN-Kennzeichnung genau eingestellt ist, sind Sie ganz eingestellt. Andernfalls können Sie eine der folgenden Methoden verwenden:
  
- Erstellen Sie einen Netzwerktyp mit dem Namen VPN (empfehlenswert) und weisen Sie anschließend VPN-Subnetze mit diesem neuen VPN-Netzwerktyp zu.
    
- Erstellen Sie ein Gebäude mit dem Namen VPN und weisen Sie anschließend VPN-Subnetze mit diesem Gebäude zu.  
    
## <a name="query-fundamentals"></a>Abfragegrundsätze

Eine gut formulierte Abfrage enthält die folgenden drei Parameter:  
  
- Kennzahl
    
- Dimension
    
- Filter
    
Hier ist ein Beispiel für eine gut formulierte Abfrage: "Show me Poor Streams [Measurement] by Subnet [Dimension] for Building 6 [Filter].“
  
## <a name="what-does-union-do"></a>Welche Funktion hat UNION?

Union ermöglicht das Filtern von Bedingungen mithilfe des Operators AND. Es gibt Szenarien, bei denen Sie mehrere Filterbedingungen kombinieren müssen, um ein OR-ähnliches Ergebnis zu erhalten
  
Beispiel: Wenn Sie alle Streams eines Gebäudes ermitteln möchten, stellt UNION eine eigene Ansicht des zusammengeführten Datasets bereit. Fügen Sie zur Verwendung von UNION einen allgemeinen Text in das UNION-Feld für die beiden Filterbedingungen, die Sie zusammenführen möchten.  
  
## <a name="default-report-breakdown"></a>Standard-Berichtsübersicht

Falls Wireless intern verwaltet wird, können Sie die Wireless-Berichte im Bucket „Verwaltet“ erneut erstellen.  
  
![CQD-Berichtsübersicht](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)
  
## <a name="operational-processes"></a>Operative Prozesse

Beginnen Sie mit der Überprüfung und Wartung der verwalteten Streams. Die Qualität sollte in diesem Bereich zu 100 % unter Ihrer Kontrolle und daher am leichtesten zu warten sein.  
  
### <a name="managed-streams"></a>Verwaltete Systeme 

Überprüfen und warten Sie verwaltete Streams in der folgenden Reihenfolge:  
  
1. Server-Server  
    
2.   Server-Wired-Inside
    
3. Wired-Wired-Inside  
    
### <a name="unmanaged-streams"></a>Nicht verwaltete Streams

Überprüfen und warten Sie nicht verwaltete Streams in der folgenden Reihenfolge:  
  
1. Server-Wifi-Inside
    
2. Server-Wired-Outside
    
3. Server-Wifi-Outside
    
4. Wired-Outside-Direct
    
5. Wired-Outside-Relay
    
6. Andere nicht verwaltete Streams
    

