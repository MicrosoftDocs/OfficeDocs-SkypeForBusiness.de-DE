---
title: Hochladen von Mandanten- und Gebäudedaten im Anrufqualitätsdashboard (CQD)
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
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie Mandanten- und Gebäudedaten im Anrufqualitätsdashboard (CQD) hochladen.
ms.openlocfilehash: a7f8b4a8d84429b752692cf05013dfba7321fd5e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909349"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a>Hochladen von Mandanten- und Gebäudedaten im Anrufqualitätsdashboard (CQD)


Um das Anrufqualitätsdashboard (CQD) in den besten 90 Jahren zu verwenden, empfiehlt es sich, den Mandanten hochzuladen und Daten zu erstellen. Es gibt zwei Typen von Mandantendatendateien: [Gebäude](#upload-building-data-file) und [Endpunkt.](#endpoint-data-file)

Hier können Sie eine Beispielvorlage für Mandantendaten [herunterladen.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true) Hilfe zum Erstellen der Zuordnung finden Sie unter ["Erstellen einer Gebäudezuordnung für das CQD".](CQD-building-mapping.md)

Wählen Sie im Dashboard "CQD-Zusammenfassungsberichte" im Menü "CQD-Einstellungen" (ein Zahnradsymbol am oberen Rand des AQD) die Option "Upload von Mandantendaten" aus.   Von hier aus können Administratoren die Gebäude- und Endpunktinformationen ihrer Organisation hochladen, z. B. die Zuordnung von IP-Adressen und geografischen Informationen, die Zuordnung der einzelnen Funkzugriffspunkt und deren MAC-Adresse usw.

1. Öffnen Sie das CQD (im Teams Admin Center oder unter), wählen Sie dann das Zahnradsymbol in der oberen rechten Ecke und dann auf der Seite "Zusammenfassungsberichte" die Option "Upload von Mandantendaten" [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) aus.  

   ![Screenshot des Dialogfelds, das angezeigt wird, während Daten hochgeladen werden](media/qerguide-image-tenantdataupload.png)
    
2. Wenn Sie das AQD zum ersten Mal besuchen, werden Sie alternativ aufgefordert, Gebäudedaten hochzuladen. Sie können **Jetzt Hochladen** auswählen, um schnell zur Seite **Mandantendaten hochladen** zu navigieren.

   ![Screenshot eines Banners, das einen Benutzer zum Hochladen von Gebäudedaten auffordert](media/qerguide-image-buildingdatauploadbanner.png)

3. Wählen Sie auf der Seite **Mandantendaten hochladen** **Durchsuchen** aus, um eine Datendatei auszuwählen.

4. Geben Sie nach Auswahl einer Datendatei das **Startdatum** und optional ein Enddatum ein.

5. Wählen Sie nach der Auswahl von **Startdatum** die Option **Hochladen** aus, um die Datei in CQD hochzuladen. <br><br>Bevor die Datei hochgeladen wird, wird sie überprüft. Wenn die Validierung fehlschlägt, wird eine Fehlermeldung angezeigt, in der Sie aufgefordert werden, die Datei zu korrigieren. Die folgende Abbildung zeigt einen Fehler, der auftritt, wenn die Anzahl der Spalten in der Datendatei falsch ist.

   ![Beispiel für ein Dialogfeld mit einem Fehler beim Hochladen der Gebäudedaten](media/qerguide-image-buildingdatauploaderror.png)
 
6. Falls während der Validierung keine Fehler auftreten, war der Dateiupload erfolgreich. Sie können die hochgeladene Datendatei in der Tabelle **Meine Uploads** anzeigen. Dort wird eine vollständige Liste aller hochgeladenen Dateien für den aktuellen Mandanten unten auf der Seite angezeigt.

> [!NOTE]
> Es kann bis zu vier Stunden dauern, bis die Bearbeitung der Datei abgeschlossen ist.<br><br> Wenn Sie bereits eine Gebäudedatei hochgeladen haben und Subnetze hinzufügen müssen, die möglicherweise verpasst oder ausgeschlossen wurden, ändern Sie die ursprüngliche Datei, indem Sie die neuen Subnetze hinzufügen, entfernen Sie die aktuelle Datei, und laden Sie die neu bearbeitete Datei erneut hoch. In CQD kann nur eine einzige aktive Gebäudedatendatei vorhanden sein. 


## <a name="upload-building-data-file"></a>Hochladen einer Gebäudedatendatei

Der erste Typ der Mandantendatendatei im  AQD ist die Gebäudedatendatei. Die Spalte "Subnetz" wird abgeleitet, indem die Spalte "Network+NetworkRange" erweitert und dann die Spalte "Subnetz" mit der ersten Subnetz- oder zweiten Subnetzspalte des Anrufdatensatz verbunden wird, um Informationen zu Gebäude, Ort, Land oder Region zu erhalten. Das Format der Datendatei, die Sie hochladen, muss die folgenden Kriterien erfüllen, um die Überprüfung vor dem Hochladen zu bestehen:
  
- Bei der Datei muss es sich entweder um eine TSV-Datei (Spalten sind durch TAB voneinander getrennt) oder um eine CSV-Datei (Spalten werden durch ein Komma getrennt) geben.

- Die Datendatei enthält keine Tabellenkopfzeile. Die erste Zeile der Datendatei wird als echte Daten und nicht als Überschriftenbeschriftungen wie "Netzwerk" erwartet.

- Die Datentypen in der Datei können nur "String", "Integer" oder "Boolean" sein. Für den Datentyp "Integer" muss der Wert ein numerischer Wert sein. Boolesche Werte müssen entweder 0 oder 1 sein.

- Wenn in einer Spalte der Datentyp "Zeichenfolge" verwendet wird, kann ein Datenfeld leer sein, muss aber trotzdem durch eine Registerkarte oder ein Komma getrennt sein. Ein leeres Datenfeld weist lediglich einen leeren Zeichenfolgenwert zu.

- Jede Zeile muss 15 Spalten enthalten, jede Spalte muss den entsprechenden Datentyp haben, und die Spalten müssen in der Reihenfolge liegen, die in der folgenden Tabelle (durch Kommas oder Tabstopps getrennt) aufgeführt ist:

  **Dateiformat für Gebäudedaten**
  
  | Spaltenname        | Datentyp | Beispiel                   | Anleitung              |
  |--------------------|-----------|---------------------------|-----------------------|
  | NetworkIP          | Zeichenfolge    | 192.168.1.0               | Erforderlich              |
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

  <sup>1</sup> Zwar ist das AQD nicht erforderlich, aber die Vorlagen sind für die Anzeige des Gebäude- und Netzwerknamens konfiguriert.

  <sup>2</sup> Diese Einstellung kann verwendet werden, um zu überprüfen, ob sich das Subnetz innerhalb des Unternehmensnetzwerks befindet. Sie können die Verwendung für andere Zwecke anpassen.

  <sup>3</sup> Mit dieser Einstellung kann angezeigt werden, ob das Netzwerk Azure ExpressRoute verwendet oder nicht. Sie können die Verwendung für andere Zwecke anpassen.  

  **Beispielzeile:**

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> Der Netzwerkbereich kann zur Darstellung eines Supernetzes (einer Kombination aus mehreren Subnetzen mit einem einzelnen Routing-Präfix) verwendet werden. Alle neuen Gebäude-Uploads werden auf sich überlappende Bereiche hin untersucht. Wenn Sie zuvor eine Gebäudedatei hochgeladen haben, sollten Sie die aktuelle Datei herunterladen und erneut hochladen, um mögliche Überlappungen zu identifizieren und das Problem vor dem erneuten Hochladen zu beheben. Alle Überlappungen in zuvor hochgeladenen Dateien können zu falschen Zuordnungen von Subnetzen zu Gebäuden in den Berichten führen. Bestimmte VPN-Implementierungen melden die Subnetzinformationen nicht genau. 
>
> Die Spalte "VPN" ist optional und standardmäßig auf 0 festgelegt. Wenn der Wert der Spalte VPN auf 1 festgelegt ist, wird das subnetz, das durch diese Zeile dargestellt wird, vollständig erweitert, um allen IP-Adressen im Subnetz zu entsprechen.  Verwenden Sie dies sparsam und nur für VPN-Subnetze, da sich eine vollständige Erweiterung dieser Subnetze negativ auf die Abfragezeiten für Abfragen mit Gebäudedaten auswirken kann.


### <a name="supernetting"></a>Supernetting

Sie können Supernetting verwenden, das gewöhnlich als "Klassenloses domänenübergreifendes Routing (Classless Inter-Domain Routing, CIDR)" bezeichnet wird, anstatt jedes Subnetz zu definieren. Bei einem *Supernet* handelt es sich um eine Kombination aus mehreren Subnetzen, die ein einzelnes Routingpräfix aufweisen. Statt für jedes Subnetz einen Eintrag hinzuzufügen, können Sie die Supernetting-Adresse verwenden. Supernetting wird unterstützt, wir raten jedoch von der Verwendung ab.

Beispielsweise besteht das Marketinggebäude von Contoso aus den folgenden Subnetzen:

-   10.1.0.0/24—1. OG
-   10.1.1.0/24—2. OG
-   10.1.2.0/24—3. OG
-   10.1.3.0/24—4. OG

Statt für jedes Subnetz einen Eintrag hinzuzufügen, können Sie die Supernetting-Adresse verwenden. In diesem Beispiel 10.1.0.0/22.

-   Netzwerk = 10.1.0.0
-   Netzwerkbereich = 22

Hier einige Punkte, die Sie berücksichtigen sollten, bevor Sie Supernetting implementieren:

-   Supernetting kann nur in einer Subnetz-Zuordnung mit einer 8-Bit-zu-28-Bit-Maske verwendet werden.

-   Supernetting nimmt im Vorfeld weniger Zeit in Anspruch, aber es geht darum, die Reichhaltigkeit ihrer Daten zu verringern. Angenommen, es gibt ein Qualitätsproblem mit Subnetz 10.1.2.0. Wenn Sie Supernetting implementiert haben, wissen Sie nicht, wo sich das Subnetz im Gebäude befindet oder um welchen Netzwerktyp es sich handelt (z. B. ein Labor). Wenn Sie alle Subnetze für ein Gebäude definiert und Standortinformationen hochgeladen haben, können Sie diese Unterscheidung sehen.

-   Es ist wichtig sicherzustellen, dass die übertenete Adresse korrekt ist und keine unerwünschten Subnetze abfangen.

-   Es ist üblich, 192.168.0.0 in Daten zu finden. Für viele Organisationen gibt dies an, dass der Benutzer zu Hause ist. Bei anderen handelt es sich um das IP-Adressschema für ein Satellitenbüro. Wenn Ihre Organisation über Niederlassungen verfügt, die diese Konfiguration verwenden, schließen Sie sie nicht in die Gebäudedatei ein, da es schwierig ist, mithilfe gemeinsamer Subnetze zwischen Heim- und internen Netzwerken [zu unterscheiden.](quality-of-experience-review-guide.md#common-subnets) 

> [!IMPORTANT]
> Der Netzwerkbereich kann verwendet werden, um ein Supernet darzustellen. Alle neuen Uploads von Gebäudedatendateien werden auf sich überlappende Bereiche hin untersucht. Wenn Sie zuvor eine Gebäudedatei hochgeladen haben, sollten Sie die aktuelle Datei herunterladen und erneut hochladen, um mögliche Überlappungen zu identifizieren und das Problem zu beheben. Alle Überlappungen in zuvor hochgeladenen Dateien könnten zu falschen Zuordnungen von Subnetzen zu Gebäuden in den Berichten führen.

### <a name="vpn"></a>VPN

Die Quality of Experience (QoE)-Daten, die Clients an Microsoft 365 oder Office 365 senden , aus denen CQD-Daten stammen, umfassen ein VPN-Flag. CQD sieht dies als die erste und die zweite VPN-Dimension. Diese Kennzeichnung basiert jedoch auf der Meldung von VPN-Anbietern an Windows, dass es sich bei dem registrierten VPN-Netzwerkadapter um einen Remotezugriffsadapter handelt. Nicht alle VPN-Anbieter registrieren die Fernzugriffsadapter ordnungsgemäß. Aus diesem Grund sind Sie möglicherweise nicht in der Lage, die integrierten VPN-Abfragefilter zu verwenden. Verwenden Sie die oben beschriebene VPN-Spalte, um VPN-Subnetze präzise zu markieren und zu identifizieren. Es ist auch eine bewährte Methode, Ihre -VPN-Netzwerke zur einfachen Identifikation in Ihren Berichten zu beschriften. Im Folgenden finden Sie zwei Beispiele für die Bezeichnung Ihrer VPN-Subnetze:

- Definieren Sie **einen Netzwerknamen,** indem Sie "VPN" in dieses Feld für VPN-Subnetze eingeben.

  ![Screenshot des QCD-Berichts mit VPN-Netzwerknamen](media/qerguide-image-vpnnetworkname.png)

- Definieren Sie einen **Gebäudenamen,** indem Sie "VPN" in dieses Feld für VPN-Subnetze eingeben.

  ![Screenshot des QCD-Berichts mit VPN-Gebäudenamen](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> Es ist bekannt, dass sich der Netzwerkverbindungstyp als verkabelt identifiziert, wenn die zugrunde liegende Verbindung drahtlos ist. Bei der Qualität von VPN-Verbindungen können Sie nicht davon ausgehen, dass der Verbindungstyp exakt identifiziert wurde.

## <a name="endpoint-data-file"></a>Endpunktdatendatei

Der andere Typ der AQD-Mandantendatendatei ist die **Endpunktdatendatei.** Die Spaltenwerte werden in der Spalte "Erster Clientendpunktname" oder "Name des zweiten Clientendpunkts" des Anrufdatensatz verwendet, um Endpunkt-Make-, Model- oder Type-Informationen zu zeigen. Das Format der Datendatei, die Sie hochladen, muss die folgenden Kriterien erfüllen, um die Überprüfung vor dem Hochladen zu bestehen:

- Bei der Datei muss es sich entweder um eine TSV-Datei (Spalten sind durch TAB voneinander getrennt) oder um eine CSV-Datei (Spalten werden durch ein Komma getrennt) geben.

- Der Inhalt der Datendatei umfasst keine Tabellenüberschriften. Die erste Zeile der Datendatei wird als echte Daten erwartet, keine Überschriftenbeschriftung wie "EndpointName".

- Alle sieben Spalten verwenden nur den Datentyp "Zeichenfolge". Die maximal zulässige Länge beträgt 64 Zeichen.

- Ein Datenfeld kann leer sein, muss aber trotzdem durch ein Tabstopp- oder Komma getrennt sein. Ein leeres Datenfeld weist lediglich einen leeren Zeichenfolgenwert zu.

- EndpointName muss eindeutig sein, andernfalls schlägt der Upload fehl. Wenn es eine doppelte Zeile oder zwei Zeilen gibt, die denselben Endpunktnamen verwenden, verursacht der Konflikt eine falsche Verbindung.

- EndpointLabel1, EndpointLabel2 und EndpointLabel3 sind anpassbare Beschriftungen. Sie können leere Zeichenfolgen oder Werte wie "IT Department designated 2018 Laptop" oder "Asset Tag 5678" sein.

- Jede Zeile muss sieben Spalten enthalten, und die Spalten müssen in der folgenden Reihenfolge angeordnet sein:

  **Feldreihenfolge:**

  EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2, EndpointLabel3

  **Beispielzeile:**

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`

## <a name="update-a-building-file"></a>Aktualisieren einer Gebäudedatei

Beim Sammeln von Gebäude- und Subnetzinformationen laden Administratoren die Gebäudedatei oft in mehreren Versionen im Laufe der Zeit hoch und fügen neue Subnetze und ihre Gebäudeinformationen hinzu, sobald diese verfügbar sind. In diesem Fall müssen Sie Ihre Gebäudedatei erneut hochladen. Dieser Vorgang ähnelt dem anfänglichen Upload gemäß der Beschreibung im vorherigen Abschnitt, mit ein paar Ausnahmen, wie im folgenden Abschnitt beschrieben.

> [!Important]
> Es kann jeweils nur eine Gebäudedatei aktiv sein. Mehrere Gebäudedateien sind nicht kumulativ.

## <a name="add-net-new-subnets"></a>Hinzufügen neuer Subnetze

Es gibt Zeiten, in denen Sie net neue Subnetze zum AQD hinzufügen müssen, die ursprünglich nicht Teil Ihrer Netzwerktopologie waren. Gehen Sie auf der Seite "Upload von Mandantendaten" im AQD wie folgt vor, um net neue **Subnetze** hinzuzufügen:

1.  Laden Sie die Ursprüngliche Datei herunter, wenn Sie noch nicht über eine aktuelle Kopie verfügen.

1.  Entfernen Sie die aktuelle Datei in CQD.

1.  Bearbeiten Sie die ursprüngliche Erstellungsdatei, und geben Sie ein Enddatum ein, das mindestens einen Tag vor dem Erwerb der neuen Nettosubnetze stattfindet.

1.  Fügen Sie die neuen Nettosubnetze der ursprünglichen Gebäudedatei hinzu.

1.  Laden Sie die neu geänderte Gebäudedatei hoch, und legen Sie das Startdatum für einen Tag nach Dem Ende der vorherigen Gebäudedatei festgelegt.

## <a name="add-missing-subnets"></a>Hinzufügen fehlender Subnetze

Nachdem Sie die Gebäudeinformationen für verwaltete Netzwerke hochgeladen haben, sollte jedes verwaltete Netzwerk über eine Gebäudezuordnung verfügen. Dies ist jedoch nicht immer der Fall. in der Regel fehlen einige Subnetze. Um diese fehlenden Netzwerke zu finden,  überprüfen Sie den **Bericht "Fehlendes Subnetz"** auf der Seite "Berichte zur Qualität der Benutzererfahrung" im AQD. Dadurch werden alle Subnetze mit 10 oder mehr Audiodatenströmen angezeigt, die nicht in der Gebäudedatendatei definiert sind und als außerhalb gekennzeichnet sind. Stellen Sie sicher, dass in dieser Liste keine verwalteten Netzwerke vorhanden sind. Wenn Subnetze fehlen, aktualisieren Sie die ursprüngliche Gebäudedatendatei mit dem folgenden Verfahren, und laden Sie sie erneut in das AQD hoch.

1. Wechseln Sie im **AQD zur** Seite "Upload von Mandantendaten".

1. Laden Sie die Ursprüngliche Datei herunter, wenn Sie noch nicht über eine aktuelle Kopie verfügen.

1. Entfernen Sie die aktuelle Datei in CQD.

1. Fügen Sie die neuen Subnetze der ursprünglichen Datei hinzu.

1. Laden Sie die Gebäudedatei hoch. Stellen Sie sicher, dass das Startdatum mindestens acht Monate zurückliegt, damit das CQD historische Daten verarbeiten kann.


> [!IMPORTANT]
> Sie müssen Ihre Mandanten-ID als Abfragefilter für die Second **Tenant-ID** zu diesem Bericht hinzufügen, um den Bericht so zu filtern, dass nur die Mandantendaten Ihrer Organisation angezeigt werden. Andernfalls zeigt der Bericht Partnersubnetze an.

> [!NOTE] 
> Stellen Sie sicher, dass Sie den Berichtsfilter "Monat Jahr" auf den aktuellen Monat anpassen. Wählen Sie **Bearbeiten** aus und passen Sie den Berichtsfilter **Monat Jahr** so an, dass der neue Standardmonat gespeichert wird.


## <a name="related-topics"></a>Verwandte Themen

[Erstellen einer Gebäudezuordnung für das AQD](CQD-building-mapping.md)

[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

[Was ist CQD?](CQD-what-is-call-quality-dashboard.md)

[Einrichten des Anrufqualitätsdashboards (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Daten und Berichte zum AQD](CQD-data-and-reports.md)

[Verwenden des AQD zum Verwalten der Anruf- und Besprechungsqualität](quality-of-experience-review-guide.md)

[Im AQD verfügbare Dimensionen und Measures](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Stream Classification in CQD](stream-classification-in-call-quality-dashboard.md)

[Verwenden von Power BI zum Analysieren von AQD-Daten](CQD-Power-BI-query-templates.md)
