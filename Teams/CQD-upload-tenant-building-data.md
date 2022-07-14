---
title: Hochladen von Mandanten- und Gebäudedaten im Anrufqualitätsdashboard (CQD)
author: CarolynRowe
ms.author: crowe
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
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie Mandanten- und Gebäudedaten im Anrufqualitäts-Dashboard (Call Quality Dashboard, CQD) hochladen.
ms.openlocfilehash: d9559490aa990f3df800e0e9438810c63d153d3c
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789640"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a>Hochladen von Mandanten- und Gebäudedaten im Anrufqualitätsdashboard (CQD)


Um das Anrufqualitätsdashboard (Call Quality Dashboard, CQD) optimal nutzen zu können, empfehlen wir Ihnen, Ihren Mandanten hochzuladen und Gebäudedaten hochzuladen. Es gibt zwei Arten von Mandantendatendateien, [Gebäude](#upload-building-data-file) und [Endpunkt](#endpoint-data-file).

Hier können Sie eine Beispiel-Mandantendatenvorlage [herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true). Hilfe zur Gebäudezuordnung finden [Sie unter Erstellen einer Gebäudezuordnung für CQD](CQD-building-mapping.md).

Wählen Sie im Dashboard "CQD-Zusammenfassungsberichte" im Menü "CQD-Einstellungen" die Option "**Mandantendatenupload**" aus (ein Zahnradsymbol oben im CQD). Von hier aus können Administratoren die Gebäude- und Endpunktinformationen ihrer Organisation hochladen, z. B. die Zuordnung von IP-Adressen und geografischen Informationen, die Zuordnung jedes drahtlosen Zugriffspunkts und seiner MAC-Adresse usw.

1. Öffnen Sie CQD (im Teams Admin Center oder unter [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)), wählen Sie dann das Zahnradsymbol in der oberen rechten Ecke aus, und wählen Sie auf der Seite "**Zusammenfassungsberichte**" den **Eintrag "Mandantendatenupload**" aus.

   ![Screenshot des Dialogfelds, das angezeigt wird, während Daten hochgeladen werden.](media/qerguide-image-tenantdataupload.png)
    
2. Wenn Sie CQD zum ersten Mal besuchen, werden Sie alternativ aufgefordert, Gebäudedaten hochzuladen. Sie können **Jetzt Hochladen** auswählen, um schnell zur Seite **Mandantendaten hochladen** zu navigieren.

   ![Screenshot eines Banners, das einen Benutzer zum Hochladen von Gebäudedaten benachrichtigt.](media/qerguide-image-buildingdatauploadbanner.png)

3. Wählen Sie auf der Seite **Mandantendaten hochladen** **Durchsuchen** aus, um eine Datendatei auszuwählen.

4. Geben Sie nach Auswahl einer Datendatei das **Startdatum** und optional ein Enddatum ein.

5. Wählen Sie nach der Auswahl von **Startdatum** die Option **Hochladen** aus, um die Datei in CQD hochzuladen. <br><br>Bevor die Datei hochgeladen wird, wird sie überprüft. Wenn die Validierung fehlschlägt, wird eine Fehlermeldung angezeigt, in der Sie aufgefordert werden, die Datei zu korrigieren. Die folgende Abbildung zeigt einen Fehler, der auftritt, wenn die Anzahl der Spalten in der Datendatei falsch ist.

   ![Beispiel für ein Dialogfeld, in dem ein Fehler beim Hochladen von Gebäudedaten angezeigt wird.](media/qerguide-image-buildingdatauploaderror.png)
 
6. Falls während der Validierung keine Fehler auftreten, war der Dateiupload erfolgreich. Sie können die hochgeladene Datendatei in der Tabelle **Meine Uploads** anzeigen. Dort wird eine vollständige Liste aller hochgeladenen Dateien für den aktuellen Mandanten unten auf der Seite angezeigt.

> [!NOTE]
> Es kann bis zu vier Stunden dauern, bis die Bearbeitung der Datei abgeschlossen ist.<br><br> Wenn Sie bereits eine Gebäudedatei hochgeladen haben und Subnetze hinzufügen müssen, die möglicherweise verpasst oder ausgeschlossen wurden, ändern Sie die Ursprüngliche Datei, indem Sie die neuen Subnetze hinzufügen, die aktuelle Datei entfernen und die neu bearbeitete Datei erneut hochladen. In CQD kann nur eine einzige aktive Gebäudedatendatei vorhanden sein. 


## <a name="upload-building-data-file"></a>Hochladen der Gebäudedatendatei

Der erste Typ der Mandantendatendatei in CQD ist die **Gebäudedatendatei** . Die Subnetzspalte wird abgeleitet, indem die Spalte "Netzwerk+NetzwerkRange" erweitert wird und dann die Subnetzspalte mit der Spalte "Erstes Subnetz" oder "Zweites Subnetz" des Anrufdatensatzes verbunden wird, um Gebäude-, Stadt-, Land- oder Regionsinformationen anzuzeigen. Das Format der Datendatei, die Sie hochladen, muss die folgenden Kriterien erfüllen, um die Überprüfung vor dem Hochladen zu bestehen:
  
- Die Datei muss entweder eine TSV-Datei (Spalten sind durch ein TAB getrennt) oder eine .csv Datei (Spalten sind durch ein Komma getrennt) sein.

- Die Datendatei enthält keine Tabellenkopfzeile. Bei der ersten Zeile der Datendatei wird erwartet, dass es sich um echte Daten handelt, nicht um Headerbeschriftungen wie "Netzwerk".

- Datentypen in der Datei können nur "String", "Integer" oder "Boolean" sein. Für den Datentyp Integer muss der Wert ein numerischer Wert sein. Boolesche Werte müssen entweder 0 oder 1 sein.

- Wenn eine Spalte den Datentyp "String" verwendet, kann ein Datenfeld leer sein, muss aber dennoch durch ein Tabstopp oder Komma getrennt werden. Ein leeres Datenfeld weist nur einen leeren String-Wert zu.

- Es gibt einen erweiterten Zeilengrenzwert von 1.000.000 pro Mandantendatendatei.

- Es müssen 15 Spalten für jede Zeile vorhanden sein, jede Spalte muss den entsprechenden Datentyp aufweisen, und die Spalten müssen in der reihenfolge sein, die in der folgenden Tabelle aufgeführt ist (Komma oder Tabstopp getrennt):

  **Erstellen eines Datendateiformats**
  
  | Spaltenname        | Datentyp | Beispiel                   | Anleitung              |
  |--------------------|-----------|---------------------------|-----------------------|
  | NetworkIP          | String    | 192.168.1.0               | Erforderlich              |
  | NetworkName        | Zeichenfolge    | USA/Seattle/SEATTLE-SEA-1 | Erforderlich<sup>1</sup>  |
  | NetworkRange       | Zahl    | 26                        | Erforderlich              |
  | BuildingName       | Zeichenfolge    | SEATTLE-SEA-1             | Erforderlich<sup>1</sup>  |
  | OwnershipType      | String    | Contoso                   | Optional              |
  | BuildingType       | Zeichenfolge    | IT Termination            | Optional              |
  | BuildingOfficeType | Zeichenfolge    | Engineering (Technik)               | Optional              |
  | Stadt/Ort               | Zeichenfolge    | Seattle                   | Empfohlen           |
  | ZipCode            | Zeichenfolge    | 98001                     | Empfohlen           |
  | Land            | Zeichenfolge    | US                        | Empfohlen           |
  | Status              | Zeichenfolge    | WA                        | Empfohlen           |
  | Region             | String    | MSUS                      | Empfohlen           |
  | InsideCorp<sup>2</sup>         | Boolescher Wert      | 1             | Erforderlich              |
  | ExpressRoute<sup>3</sup>       | Boolescher Wert      | 0             | Erforderlich              |
  | VPN                | Boolescher Wert      | 0                         | Optional              |

  <sup>1</sup> Obwohl CQD nicht erforderlich ist, sind die Vorlagen so konfiguriert, dass gebäude- und netzwerkname angezeigt werden.

  <sup>2</sup> Diese Einstellung kann verwendet werden, um anzugeben, ob sich das Subnetz innerhalb des Unternehmensnetzwerks befindet. Sie können die Nutzung für andere Zwecke anpassen.

  <sup>3</sup> Diese Einstellung kann verwendet werden, um anzugeben, ob das Netzwerk Azure ExpressRoute verwendet. Sie können die Nutzung für andere Zwecke anpassen.  

  **Beispielzeile:**

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> Der Netzwerkbereich kann zur Darstellung eines Supernetzes (einer Kombination aus mehreren Subnetzen mit einem einzelnen Routing-Präfix) verwendet werden. Alle neuen Gebäude-Uploads werden auf sich überlappende Bereiche hin untersucht. Wenn Sie zuvor eine Gebäudedatei hochgeladen haben, sollten Sie die aktuelle Datei herunterladen und erneut hochladen, um mögliche Überlappungen zu identifizieren und das Problem vor dem erneuten Hochladen zu beheben. Alle Überlappungen in zuvor hochgeladenen Dateien können zu falschen Zuordnungen von Subnetzen zu Gebäuden in den Berichten führen. Bestimmte VPN-Implementierungen melden die Subnetzinformationen nicht genau. 
>
> Die VPN-Spalte ist optional und wird standardmäßig auf 0 festgelegt. Wenn der Wert der VPN-Spalte auf 1 festgelegt ist, wird das durch diese Zeile dargestellte Subnetz vollständig erweitert, sodass es allen IP-Adressen innerhalb des Subnetzes entspricht. Verwenden Sie dies nur sparsam und nur für VPN-Subnetze, da eine vollständige Erweiterung dieser Subnetze negative Auswirkungen auf die Abfragezeiten für Abfragen mit Gebäudedaten hat. Wenn die Erweiterung des Subnetzes dazu führt, dass die Erweiterungszeilengrenze von 1.000.000 überschritten wird, wird die Gebäudedatei nicht akzeptiert.


### <a name="supernetting"></a>Supernetting

Sie können Supernetting verwenden, das gewöhnlich als "Klassenloses domänenübergreifendes Routing (Classless Inter-Domain Routing, CIDR)" bezeichnet wird, anstatt jedes Subnetz zu definieren. Bei einem *Supernet* handelt es sich um eine Kombination aus mehreren Subnetzen, die ein einzelnes Routingpräfix aufweisen. Statt für jedes Subnetz einen Eintrag hinzuzufügen, können Sie die Supernetting-Adresse verwenden. Supernetting wird unterstützt, es wird jedoch nicht empfohlen, es zu verwenden.

Das Marketinggebäude von Contoso besteht beispielsweise aus den folgenden Subnetzen:

-   10.1.0.0/24—1. OG
-   10.1.1.0/24—2. OG
-   10.1.2.0/24—3. OG
-   10.1.3.0/24—4. OG

Statt für jedes Subnetz einen Eintrag hinzuzufügen, können Sie die Supernetting-Adresse verwenden. In diesem Beispiel 10.1.0.0/22.

-   Netzwerk = 10.1.0.0
-   Netzwerkbereich = 22

Hier einige Punkte, die Sie berücksichtigen sollten, bevor Sie Supernetting implementieren:

-   Supernetting kann nur in einer Subnetz-Zuordnung mit einer 8-Bit-zu-28-Bit-Maske verwendet werden.

-   Supernetting nimmt im Vorfeld weniger Zeit in Anspruch, aber es geht darum, die Reichhaltigkeit ihrer Daten zu verringern. Angenommen, es gibt ein Qualitätsproblem im Subnetz 10.1.2.0. Wenn Sie Supernetting implementiert haben, wissen Sie nicht, wo sich das Subnetz im Gebäude befindet oder um welchen Netzwerktyp es sich handelt (z. B. ein Labor). Wenn Sie alle Subnetze für ein Gebäude definiert und Standortinformationen hochgeladen haben, können Sie diesen Unterschied erkennen.

-   Es ist wichtig sicherzustellen, dass die übernetete Adresse korrekt ist und keine unerwünschten Subnetze abfangen.

-   Es ist üblich, 192.168.0.0 in Daten zu finden. Für viele Organisationen gibt dies an, dass der Benutzer zu Hause ist. Bei anderen handelt es sich um das IP-Adressschema für ein Satellitenbüro. Wenn Ihre Organisation Niederlassungen hat, in denen diese Konfiguration verwendet wird, schließen Sie sie nicht in Ihre Gebäudedatei ein, da es schwierig ist, mithilfe [gängiger Subnetze](quality-of-experience-review-guide.md#common-subnets) zwischen privaten und internen Netzwerken zu unterscheiden. 

> [!IMPORTANT]
> Der Netzwerkbereich kann verwendet werden, um ein Supernet darzustellen. Alle neuen Uploads von Gebäudedatendateien werden auf sich überlappende Bereiche hin untersucht. Wenn Sie zuvor eine Gebäudedatei hochgeladen haben, sollten Sie die aktuelle Datei herunterladen und erneut hochladen, um Überlappungen zu identifizieren und das Problem zu beheben. Alle Überlappungen in zuvor hochgeladenen Dateien könnten zu falschen Zuordnungen von Subnetzen zu Gebäuden in den Berichten führen.

### <a name="vpn"></a>VPN

Die QoE-Daten (Quality of Experience), die Clients an Microsoft 365 oder Office 365 senden , aus denen CQD-Daten stammen, umfassen ein VPN-Flag. CQD sieht dies als die erste und die zweite VPN-Dimension. Dieses Kennzeichen basiert jedoch darauf, dass VPN-Anbieter Windows melden, dass der registrierte VPN-Netzwerkadapter ein Remotezugriffsadapter ist. Nicht alle VPN-Anbieter registrieren die Fernzugriffsadapter ordnungsgemäß. Aus diesem Grund sind Sie möglicherweise nicht in der Lage, die integrierten VPN-Abfragefilter zu verwenden. Verwenden Sie die oben beschriebene VPN-Spalte, um VPN-Subnetze genau zu markieren und zu identifizieren. Es empfiehlt sich auch, Ihre VPN-Netzwerke für eine einfache Identifizierung in Ihren Berichten zu kennzeichnen. Im Folgenden finden Sie zwei Beispiele zum Bezeichnen Ihrer VPN-Subnetze:

- Definieren Sie einen **Netzwerknamen** , indem Sie "VPN" in dieses Feld für VPN-Subnetze eingeben.

  ![Screenshot des QCD-Berichts mit VPN unter Verwendung des Netzwerknamens.](media/qerguide-image-vpnnetworkname.png)

- Definieren Sie einen **Gebäudenamen** , indem Sie "VPN" in dieses Feld für VPN-Subnetze eingeben.

  ![Screenshot des QCD-Berichts mit VPN unter Verwendung des Gebäudenamens.](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> Bei VPN-Verbindungen wurde bekannt, dass der Netzwerkverbindungstyp als verkabelt identifiziert wird, wenn die zugrunde liegende Verbindung drahtlos ist. Wenn Sie sich die Qualität gegenüber VPN-Verbindungen ansehen, können Sie nicht davon ausgehen, dass der Verbindungstyp genau identifiziert wurde.

## <a name="endpoint-data-file"></a>Endpunktdatendatei

Der andere Typ der CQD-Mandantendatendatei ist die **Endpunktdatendatei** . Die Spaltenwerte werden in der Spalte "First Client Endpoint Name" oder "Second Client Endpoint Name" des Anrufdatensatzes verwendet, um Endpunkt-Make-, Model- oder Type-Informationen anzuzeigen. Das Format der Datendatei, die Sie hochladen, muss die folgenden Kriterien erfüllen, um die Überprüfung vor dem Hochladen zu bestehen:

- Die Datei muss entweder eine TSV-Datei (Spalten sind durch ein TAB getrennt) oder eine .csv Datei (Spalten sind durch ein Komma getrennt) sein.

- Der Inhalt der Datendatei umfasst keine Tabellenüberschriften. Bei der ersten Zeile der Datendatei wird erwartet, dass es sich um echte Daten handelt, nicht um eine Kopfzeilenbeschriftung wie "EndpointName".

- Alle sieben Spalten verwenden nur den Datentyp "String". Die maximal zulässige Länge beträgt 64 Zeichen.

- Bei Einträgen wird die Groß-/Kleinschreibung beachtet. EndpointName **ABC123** wird als eindeutig von EndpointName **abc123** behandelt.

- Ein Datenfeld kann leer sein, muss aber trotzdem durch ein Tabstopp- oder Komma getrennt werden. Ein leeres Datenfeld weist nur einen leeren String-Wert zu.

- EndpointName muss eindeutig sein, andernfalls schlägt der Upload fehl. Wenn es eine doppelte Zeile oder zwei Zeilen gibt, die denselben EndpointName verwenden, führt der Konflikt zu einer falschen Verknüpfung.

- EndpointLabel1, EndpointLabel2 und EndpointLabel3 sind anpassbare Bezeichnungen. Dabei kann es sich um leere Zeichenfolgen oder Werte wie "IT-Abteilung 2018 Laptop" oder "Asset Tag 5678" handeln.

- Für jede Zeile müssen sieben Spalten vorhanden sein, und die Spalten müssen in der folgenden Reihenfolge vorliegen:

  **Feldreihenfolge:**

  EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2, EndpointLabel3

  **Beispielzeile:**

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`

## <a name="update-a-building-file"></a>Aktualisieren einer Gebäudedatei

Beim Sammeln von Gebäude- und Subnetzinformationen laden Administratoren die Gebäudedatei oft in mehreren Versionen im Laufe der Zeit hoch und fügen neue Subnetze und ihre Gebäudeinformationen hinzu, sobald diese verfügbar sind. In diesem Fall müssen Sie Ihre Gebäudedatei erneut hochladen. Dieser Vorgang ähnelt dem anfänglichen Upload gemäß der Beschreibung im vorherigen Abschnitt, mit ein paar Ausnahmen, wie im folgenden Abschnitt beschrieben.

> [!Important]
> Es kann jeweils nur eine Gebäudedatei aktiv sein. Mehrere Gebäudedateien sind nicht kumulativ.

## <a name="add-net-new-subnets"></a>Hinzufügen neuer Nettosubnetze

Es gibt Zeiten, in denen Sie neue Nettosubnetze zu CQD hinzufügen müssen, die ursprünglich nicht Teil Ihrer Netzwerktopologie waren. Gehen Sie auf der Seite " **Mandantendatenupload** " im CQD wie folgt vor, um neue Nettosubnetze hinzuzufügen:

1.  Laden Sie die Originaldatei herunter, wenn Sie noch nicht über eine aktuelle Kopie verfügen.

1.  Entfernen Sie die aktuelle Datei in CQD.

1.  Bearbeiten Sie die ursprüngliche Erstellungsdatei, und geben Sie ein Enddatum ein, das mindestens einen Tag vor dem Erwerb der neuen Nettosubnetze stattfindet.

1.  Fügen Sie die neuen Nettosubnetze der ursprünglichen Gebäudedatei hinzu.

1.  Laden Sie die neu geänderte Gebäudedatei hoch, und legen Sie das Startdatum für einen Tag nach Dem Ende der vorherigen Gebäudedatei fest.

## <a name="add-missing-subnets"></a>Hinzufügen fehlender Subnetze

Nachdem Sie die Gebäudeinformationen für verwaltete Netzwerke hochgeladen haben, sollte jedes verwaltete Netzwerk über eine Gebäudezuordnung verfügen. Dies wird jedoch nicht immer der Fall sein; in der Regel werden einige Subnetze verpasst. Um diese fehlenden Netzwerke zu finden, überprüfen Sie den **Bericht "Fehlendes Subnetz"** auf der Seite " **Berichte zur Qualität der Erfahrung"** in CQD. Dadurch werden alle Subnetze mit 10 oder mehr Audiodatenströmen angezeigt, die nicht in der Gebäudedatendatei definiert sind und als außen gekennzeichnet werden. Stellen Sie sicher, dass in dieser Liste keine verwalteten Netzwerke vorhanden sind. Wenn Subnetze fehlen, führen Sie das folgende Verfahren aus, um die ursprüngliche Gebäudedatendatei zu aktualisieren und erneut in den CQD hochzuladen.

1. Wechseln Sie zur Seite " **Mandantendatenupload** " in CQD.

1. Laden Sie die Originaldatei herunter, wenn Sie noch nicht über eine aktuelle Kopie verfügen.

1. Entfernen Sie die aktuelle Datei in CQD.

1. Fügen Sie die neuen Subnetze der ursprünglichen Datei hinzu.

1. Laden Sie die Gebäudedatei hoch. Stellen Sie sicher, dass das Startdatum mindestens acht Monate zurückliegt, damit das CQD historische Daten verarbeiten kann.


> [!IMPORTANT]
> Sie müssen Ihre Mandanten-ID als Abfragefilter für **die zweite Mandanten-ID** zu diesem Bericht hinzufügen, um den Bericht so zu filtern, dass nur die Mandantendaten Ihrer Organisation angezeigt werden. Andernfalls zeigt der Bericht Partnersubnetze an.

> [!NOTE] 
> Stellen Sie sicher, dass Sie den Berichtsfilter "Monat Jahr" auf den aktuellen Monat anpassen. Wählen Sie **Bearbeiten** aus und passen Sie den Berichtsfilter **Monat Jahr** so an, dass der neue Standardmonat gespeichert wird.


## <a name="related-topics"></a>Verwandte Themen

[Erstellen einer Gebäudekarte für CQD](CQD-building-mapping.md)

[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

[Was ist CQD?](CQD-what-is-call-quality-dashboard.md)

[Einrichten des Anrufqualitäts-Dashboards (CQD)](turning-on-and-using-call-quality-dashboard.md)

[CQD-Daten und -Berichte](CQD-data-and-reports.md)

[Verwenden von CQD zum Verwalten der Anruf- und Besprechungsqualität](quality-of-experience-review-guide.md)

[In CQD verfügbare Dimensionen und Kennzahlen](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Streamklassifizierung in CQD](stream-classification-in-call-quality-dashboard.md)

[Verwenden von Power BI zum Analysieren von CQD-Daten](CQD-Power-BI-query-templates.md)
