---
title: Hochladen von Mandanten und Erstellen von Daten im Dashboard für die Anrufqualität (CQD)
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
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Hier erfahren Sie, wie Sie Mandanten und Gebäudedaten im Dashboard für die Anrufqualität (CQD) hochladen.
ms.openlocfilehash: d8a27ab45a01d1b0eccc28716bee9fa838fb8de5
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086084"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a>Hochladen von Mandanten und Erstellen von Daten im Dashboard für die Anrufqualität (CQD)


Damit Sie die Anrufqualität optimal nutzen können (CQD), empfehlen wir, dass Sie Ihre Mandanten und Gebäudedaten hochladen. Es gibt zwei Typen von Mandantendaten Dateien, [Gebäude](#upload-building-data-file) und [Endpunkt](#endpoint-data-file).

[Hier](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)können Sie eine Beispiel-Mandantendaten Vorlage herunterladen. Hilfe zum Erstellen einer Zuordnung finden Sie unter [Erstellen eines Bauplans für CQD](CQD-building-mapping.md).

Wählen Sie im Dashboard für CQD-Zusammenfassungsberichte die Option **Mandantendaten Upload** aus dem CQD-Menü **Einstellungen** aus (ein Zahnradsymbol oben in CQD). Von hier aus können Administratoren die Gebäude-und Endpunktinformationen Ihrer Organisation hochladen, wie etwa die Zuordnung von IP-Adressen und geografischen Informationen, die Zuordnung der einzelnen WLAN-Zugriffspunkte und deren Mac-Adresse usw.

1. Öffnen Sie CQD (im Team Admin Center oder bei [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) ), und wählen Sie dann in der oberen rechten Ecke das Zahnradsymbol aus, und wählen Sie auf der Seite **Zusammenfassungsberichte** den Eintrag **Mandantendaten Upload** aus.

   ![Screenshot des Dialogfelds, das angezeigt wird, während Daten hochgeladen werden](media/qerguide-image-tenantdataupload.png)
    
2. Wenn Sie CQD zum ersten Mal besuchen, werden Sie aufgefordert, Gebäudedaten hochzuladen. Sie können **Jetzt Hochladen** auswählen, um schnell zur Seite **Mandantendaten hochladen** zu navigieren.

   ![Screenshot eines Banners, das einen Benutzer zum Hochladen von Gebäudedaten auffordert](media/qerguide-image-buildingdatauploadbanner.png)

3. Wählen Sie auf der Seite **Mandantendaten hochladen** **Durchsuchen** aus, um eine Datendatei auszuwählen.

4. Geben Sie nach Auswahl einer Datendatei das **Startdatum** und optional ein Enddatum ein.

5. Wählen Sie nach der Auswahl von **Startdatum** die Option **Hochladen** aus, um die Datei in CQD hochzuladen. <br><br>Bevor die Datei hochgeladen wird, wird Sie überprüft. Wenn die Validierung fehlschlägt, wird eine Fehlermeldung angezeigt, in der Sie aufgefordert werden, die Datei zu korrigieren. Die folgende Abbildung zeigt einen Fehler, der auftritt, wenn die Anzahl der Spalten in der Datendatei falsch ist.

   ![Beispiel für ein Dialogfeld mit einem Fehler beim Hochladen der Gebäudedaten](media/qerguide-image-buildingdatauploaderror.png)
 
6. Falls während der Validierung keine Fehler auftreten, war der Dateiupload erfolgreich. Sie können die hochgeladene Datendatei in der Tabelle **Meine Uploads** anzeigen. Dort wird eine vollständige Liste aller hochgeladenen Dateien für den aktuellen Mandanten unten auf der Seite angezeigt.

> [!NOTE]
> Es kann bis zu vier Stunden dauern, bis die Bearbeitung der Datei abgeschlossen ist.<br><br> Wenn Sie bereits eine Gebäude Datei hochgeladen haben und Subnetze hinzufügen müssen, die möglicherweise verpasst oder ausgeschlossen wurden, ändern Sie die ursprüngliche Datei, indem Sie die neuen Subnetze hinzufügen, die aktuelle Datei entfernen und die neu bearbeitete Datei erneut hochladen. In CQD kann nur eine einzige aktive Gebäudedatendatei vorhanden sein. 


## <a name="upload-building-data-file"></a>Hochladen einer Gebäude Datendatei

Der erste Typ der Mandanten Datendatei in CQD ist die **Gebäude** Datendatei. Die Spalte Subnet wird durch Erweitern der Spalte Netzwerk + NetworkRange abgeleitet, und anschließend wird die Spalte Subnetz mit der Spalte erstes Subnetz oder Zweites Subnetz des Anrufdaten Satzes verknüpft, um die Informationen für Gebäude, Stadt, Land oder Region anzuzeigen. Das Format der Datendatei, die Sie hochladen, muss die folgenden Kriterien erfüllen, um die Gültigkeitsprüfung vor dem Upload durchführen zu können:
  
- Bei der Datei muss es sich um eine TSV-Datei (Spalten werden durch eine Registerkarte getrennt) oder um eine CSV-Datei (Spalten werden durch ein Komma getrennt) handeln.
- Die Datendatei enthält keine Tabellenkopfzeile. Die erste Zeile der Datendatei wird als reelle Daten erwartet, nicht für Kopfzeilen Beschriftungen wie "Netzwerk".
- Datentypen in der Datei können nur String, Integer oder Boolean sein. Für den Datentyp "Integer" muss der Wert ein numerischer Wert sein. Boolesche Werte müssen entweder 0 oder 1 sein.
- Wenn in einer Spalte der Datentyp "Zeichenfolge" verwendet wird, kann ein Datenfeld leer sein, muss aber durch Tabstopps oder Komma getrennt werden. Ein leeres Datenfeld weist nur einen leeren Zeichenfolgenwert zu.
- Es müssen 14 Spalten für jede Zeile vorhanden sein, jede Spalte muss den entsprechenden Datentyp aufweisen, und die Spalten müssen in der in der folgenden Tabelle aufgelisteten Reihenfolge liegen (Komma oder Tabstopp getrennt):

**Erstellen eines Datendateiformats**

| Spaltenname        | Datentyp | Beispiel                   | Anleitung              |
|--------------------|-----------|---------------------------|-----------------------|
| NetworkIP          | String    | 192.168.1.0               | Erforderlich              |
| NetworkName        | String    | USA/Seattle/SEATTLE-SEA-1 | Erforderlich<sup>1</sup>  |
| NetworkRange       | Zahl    | 26                        | Erforderlich              |
| BuildingName       | String    | SEATTLE-SEA-1             | Erforderlich<sup>1</sup>  |
| OwnershipType      | String    | Contoso                   | Optional              |
| BuildingType       | String    | IT Termination            | Optional              |
| BuildingOfficeType | String    | Engineering (Technik)               | Optional              |
| Stadt/Ort               | String    | Seattle                   | Empfohlen           |
| ZipCode            | String    | 98001                     | Empfohlen           |
| Land            | String    | US                        | Empfohlen           |
| Status              | Zeichenfolge    | WA                        | Empfohlen           |
| Region             | String    | MSUS                      | Empfohlen           |
| InsideCorp<sup>2</sup>         | Boolescher Wert      | 1             | Erforderlich              |
| Express Route<sup>3</sup>       | Boolescher Wert      | 0             | Erforderlich              |
| VPN                | Boolescher Wert      | 0                         | Optional              |

<sup>1</sup> Obwohl es für CQD nicht erforderlich ist, sind die Vorlagen für die Anzeige von Gebäude-und Netzwerknamen konfiguriert.

<sup>2</sup> Diese Einstellung kann verwendet werden, um zu reflektieren, ob sich das Subnetz innerhalb des Unternehmensnetzwerks befindet. Sie können die Verwendung für andere Zwecke anpassen.

<sup>3</sup> Diese Einstellung kann verwendet werden, um anzugeben, ob das Netzwerk Azure Express Route verwendet. Sie können die Verwendung für andere Zwecke anpassen.  

**Beispiel Zeile:**

`192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> Der Netzwerkbereich kann zur Darstellung eines Supernetzes (einer Kombination aus mehreren Subnetzen mit einem einzelnen Routing-Präfix) verwendet werden. Alle neuen Gebäude-Uploads werden auf sich überlappende Bereiche hin untersucht. Wenn Sie zuvor eine Gebäudedatei hochgeladen haben, sollten Sie die aktuelle Datei herunterladen und erneut hochladen, um mögliche Überlappungen zu identifizieren und das Problem vor dem erneuten Hochladen zu beheben. Alle Überlappungen in zuvor hochgeladenen Dateien können zu falschen Zuordnungen von Subnetzen zu Gebäuden in den Berichten führen. Bei bestimmten VPN-Implementierungen werden die Subnetinformationen nicht genau gemeldet. Es wird empfohlen, beim Hinzufügen eines VPN-Subnetzes zur Gebäudedatei anstelle eines Eintrags für das Subnetz separate Einträge für jede Adresse im VPN-Subnetz als separates 32 Bit-Netzwerk hinzuzufügen. Jede Zeile kann die gleichen Gebäudemetadaten enthalten. Ein Beispiel: Anstelle einer Zeile für 172.16.18.0/24 sollten Sie 256 Zeilen verwenden - eine Zeile für jede Adresse zwischen 172.16.18.0/32 und 172.16.18.255/32 (einschließlich).
>
> Die VPN-Spalte ist optional und wird standardmäßig auf 0 gesetzt. Wenn der Wert der VPN-Spalte auf 1 festgesetzt ist, wird das durch diese Zeile dargestellte Subnetz vollständig erweitert, damit es allen IP-Adressen im Subnetz entspricht.  Verwenden Sie diese sparsam und nur für VPN-Subnetze, da sich diese Subnetze durch eine vollständige Erweiterung negativ auf die Abfragezeiten für Abfragen mit Gebäudedaten auswirken.


### <a name="supernetting"></a>Supernetting

Sie können Supernetting verwenden, das gewöhnlich als "Klassenloses domänenübergreifendes Routing (Classless Inter-Domain Routing, CIDR)" bezeichnet wird, anstatt jedes Subnetz zu definieren. Bei einem *Supernet* handelt es sich um eine Kombination aus mehreren Subnetzen, die ein einzelnes Routingpräfix aufweisen. Statt für jedes Subnetz einen Eintrag hinzuzufügen, können Sie die Supernetting-Adresse verwenden. Supernetting wird unterstützt, aber wir raten davon ab, es zu verwenden.

Das Marketing Gebäude von Contoso besteht beispielsweise aus den folgenden Subnetzen:

-   10.1.0.0/24—1. OG
-   10.1.1.0/24—2. OG
-   10.1.2.0/24—3. OG
-   10.1.3.0/24—4. OG

Statt für jedes Subnetz einen Eintrag hinzuzufügen, können Sie die Supernetting-Adresse verwenden. In diesem Beispiel 10.1.0.0/22.

-   Netzwerk = 10.1.0.0
-   Netzwerkbereich = 22

Hier einige Punkte, die Sie berücksichtigen sollten, bevor Sie Supernetting implementieren:

-   Supernetting kann nur in einer Subnetz-Zuordnung mit einer 8-Bit-zu-28-Bit-Maske verwendet werden.

-   Supernetting nimmt im Vorfeld weniger Zeit in Anspruch, aber es geht darum, die Reichhaltigkeit ihrer Daten zu verringern. Angenommen, es gibt ein Qualitätsproblem mit Subnetz-10.1.2.0. Wenn Sie Supernetting implementiert haben, wissen Sie nicht, an welcher Stelle im Gebäude sich das Subnetz befindet oder welche Art von Netzwerk es ist (beispielsweise eine Übungseinheit). Wenn Sie alle Subnetze für ein Gebäude definiert und Informationen zur bodenposition hochgeladen haben, können Sie diese Unterscheidung sehen.

-   Es ist wichtig, sicherzustellen, dass die überarbeiteten Adressen richtig sind und keine unerwünschten Subnetze fangen.

-   Es ist ziemlich üblich, 192.168.0.0 in Daten zu finden. Für viele Organisationen gibt dies an, dass der Benutzer zu Hause ist. Bei anderen handelt es sich um das IP-Adressschema für ein Satellitenbüro. Wenn Ihre Organisation über Büros verfügt, die diese Konfiguration verwenden, fügen Sie Sie nicht in ihre Gebäude Datei ein, da es schwierig ist, zwischen privaten und internen Netzwerken unterscheiden zu können, indem Sie [Allgemeine Subnetze](quality-of-experience-review-guide.md#common-subnets)verwenden. 

> [!IMPORTANT]
> Der Netzwerkbereich kann verwendet werden, um ein Supernet darzustellen. Alle neuen Uploads von Gebäudedatendateien werden auf sich überlappende Bereiche hin untersucht. Wenn Sie zuvor eine Building-Datei hochgeladen haben, sollten Sie die aktuelle Datei herunterladen und erneut hochladen, um Überlappungen zu identifizieren und das Problem zu beheben. Alle Überlappungen in zuvor hochgeladenen Dateien könnten zu falschen Zuordnungen von Subnetzen zu Gebäuden in den Berichten führen.

### <a name="vpn"></a>VPN

Die QoE-Daten (Quality of Experience), die Clients an Microsoft 365 oder Office 365 senden, an denen CQD-Daten bezogen werden, enthalten ein VPN-Flag. CQD sieht dies als die erste und die zweite VPN-Dimension. Dieses Flag basiert jedoch auf der Berichterstellung des VPN-Anbieters an Windows, dass der registrierte VPN-Netzwerkadapter ein RAS-Adapter ist. Nicht alle VPN-Anbieter registrieren die Fernzugriffsadapter ordnungsgemäß. Aus diesem Grund sind Sie möglicherweise nicht in der Lage, die integrierten VPN-Abfragefilter zu verwenden. Es gibt zwei Vorgehensweisen für die Aufnahme von VPN-Subnetzen in die Gebäudeinformationsdatei:

- Definieren Sie einen **Netzwerknamen** , indem Sie in dieses Feld für VPN-Subnetze "VPN" eingeben.

  ![Screenshot des QCD-Berichts mit VPN-Netzwerknamen](media/qerguide-image-vpnnetworkname.png)

- Definieren Sie einen **Gebäudenamen** , indem Sie in dieses Feld für VPN-Subnetze "VPN" eingeben.

  ![Screenshot des QCD-Berichts mit VPN-Gebäudenamen](media/qerguide-image-vpnbuildingname.png)

> [!IMPORTANT]
> Bei bestimmten VPN-Implementierungen werden die Subnetinformationen nicht genau gemeldet. Falls dies bei Ihrer Berichtserstattung auftritt, empfehlen wir, beim Hinzufügen eines VPN-Subnetzes zur Gebäudedatei anstelle eines Eintrags für das Subnetz separate Einträge für jede Adresse im VPN-Subnetz als separates 32 Bit-Netzwerk hinzuzufügen. Jede Zeile kann die gleichen Gebäudemetadaten aufweisen. So haben Sie beispielsweise anstelle einer Zeile für 172.16.18.0/24 253 Zeilen und eine Zeile für jede Adresse aus 172.16.18.1/32 bis 172.16.18.254/32 einschließlich.


> [!NOTE]
> Bei VPN-Verbindungen ist bekannt, dass die Netzwerkverbindung als verdrahtet gekennzeichnet ist, wenn die zugrundeliegende Internetverbindung drahtlos ist. Wenn Sie die Qualität über VPN-Verbindungen betrachten, können Sie nicht davon ausgehen, dass der Verbindungstyp genau identifiziert wurde.


## <a name="endpoint-data-file"></a>Endpunkt Datendatei

Der andere Typ der CQD-Mandantendaten Datei ist die **Endpunkt** Datendatei. Die Spaltenwerte werden in der ersten Clientendpunkt Name des Anrufdaten Satzes oder in der Spalte des zweiten Clientendpunkts verwendet, um die Informationen für die Endpunkt Marke, das Modell oder den Typ anzuzeigen. Das Format der Datendatei, die Sie hochladen, muss die folgenden Kriterien erfüllen, um die Gültigkeitsprüfung vor dem Upload durchführen zu können:

- Bei der Datei muss es sich um eine TSV-Datei (Spalten werden durch eine Registerkarte getrennt) oder um eine CSV-Datei (Spalten werden durch ein Komma getrennt) handeln.
- Der Inhalt der Datendatei umfasst keine Tabellenüberschriften. In der ersten Zeile der Datendatei wird erwartet, dass es sich um reelle Daten handelt, nicht um eine Headerbezeichnung wie "Endpunktname".
- Alle sechs Spalten verwenden nur den Datentyp "Zeichenfolge". Die maximal zulässige Länge beträgt 64 Zeichen.
- Ein Datenfeld kann leer sein, muss aber durch Tabstopps oder Kommas getrennt werden. Ein leeres Datenfeld weist nur einen leeren Zeichenfolgenwert zu.
- Endpunktname muss eindeutig sein, da andernfalls der Upload fehlschlägt. Wenn eine Zeile oder zwei Zeilen vorhanden sind, die denselben Endpunktname verwenden, führt der Konflikt zu einer fehlerhaften Verknüpfung.
- EndpointLabel1, EndpointLabel2 und EndpointLabel3 sind anpassbare Beschriftungen. Sie können leere Zeichenfolgen oder Werte sein, beispielsweise "IT-Abteilung, die als 2018-Laptop bezeichnet wird" oder "Asset Tag 5678".
- Es müssen sechs Spalten für jede Zeile vorhanden sein, und die Spalten müssen in der folgenden Reihenfolge vorliegen:

  **Feld Reihenfolge:**

EndpointName, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2, EndpointLabel3

  **Beispiel Zeile:**

`1409W3534, Fabrikam Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018,`  



## <a name="update-a-building-file"></a>Aktualisieren einer Gebäude Datei

Beim Sammeln von Gebäude- und Subnetzinformationen laden Administratoren die Gebäudedatei oft in mehreren Versionen im Laufe der Zeit hoch und fügen neue Subnetze und ihre Gebäudeinformationen hinzu, sobald diese verfügbar sind. In diesem Fall müssen Sie Ihre Gebäude Datei erneut hochladen. Dieser Vorgang ähnelt dem anfänglichen Upload gemäß der Beschreibung im vorherigen Abschnitt, mit ein paar Ausnahmen, wie im folgenden Abschnitt beschrieben.

> [!Important]
> Es kann jeweils nur eine Gebäudedatei aktiv sein. Mehrere Gebäude Dateien sind nicht kumulativ.

## <a name="add-net-new-subnets"></a>Hinzufügen von neuen net-Subnetzen

Es gibt Situationen, in denen Sie neue net-Subnetze zu CQD hinzufügen müssen, die ursprünglich nicht Bestandteil Ihrer Netzwerktopologie waren. Gehen Sie zum Hinzufügen von Netto neuen Subnetzen auf der Seite **Mandantendaten Upload** in CQD wie folgt vor:

2.  Laden Sie die ursprüngliche Datei herunter, wenn Sie noch nicht über eine aktuelle Kopie verfügen.
1.  Entfernen Sie die aktuelle Datei in CQD.
1.  Bearbeiten Sie die ursprüngliche Erstellungsdatei, und geben Sie ein Enddatum ein, das mindestens einen Tag vor dem Erwerb der neuen Nettosubnetze stattfindet.
1.  Fügen Sie die neuen Nettosubnetze der ursprünglichen Gebäudedatei hinzu.
1.  Laden Sie die neu geänderte Gebäude Datei hoch, und legen Sie den Anfangstermin für einen Tag nach dem Ende der vorherigen Gebäude Datei ein.

## <a name="add-missing-subnets"></a>Hinzufügen fehlender Subnetze

Nachdem Sie die Gebäudeinformationen für verwaltete Netzwerke hochgeladen haben, sollte jedes verwaltete Netzwerk über eine Gebäudezuordnung verfügen. Dies ist allerdings nicht immer der Fall; in der Regel werden einige Subnetze übersehen. Wenn Sie nach diesen fehlenden Netzwerken suchen möchten, lesen Sie den **Bericht fehlendes Subnetz** auf der Seite **Quality of Experience Reports** in CQD. Dadurch werden alle Subnetze mit 10 oder mehr Audiostreams dargestellt, die nicht in der Gebäudedaten Datei definiert sind und als "extern" gekennzeichnet sind. Stellen Sie sicher, dass in dieser Liste keine verwalteten Netzwerke vorhanden sind. Wenn Subnetze fehlen, führen Sie die folgenden Schritte aus, um die ursprüngliche Gebäude Datendatei zu aktualisieren und Sie erneut in CQD hochzuladen.

1. Wechseln Sie in CQD zur Seite **Mandantendaten Upload** .
1. Laden Sie die ursprüngliche Datei herunter, wenn Sie noch nicht über eine aktuelle Kopie verfügen.
1. Entfernen Sie die aktuelle Datei in CQD.
1. Fügen Sie die neuen Subnetze der ursprünglichen Datei hinzu.
1. Laden Sie die Gebäudedatei hoch. Stellen Sie sicher, dass das Startdatum mindestens acht Monate zurückliegt, damit das CQD historische Daten verarbeiten kann.


> [!IMPORTANT]
> Sie müssen Ihre Mandanten-ID als Abfragefilter für die **zweite Mandanten-ID** für diesen Bericht hinzufügen, um den Bericht so zu filtern, dass nur die Mandantendaten Ihrer Organisation angezeigt werden. Andernfalls zeigt der Bericht Partnersubnetze an.

> [!NOTE] 
> Stellen Sie sicher, dass Sie den Berichtsfilter "Monat Jahr" auf den aktuellen Monat anpassen. Wählen Sie **Bearbeiten** aus und passen Sie den Berichtsfilter **Monat Jahr** so an, dass der neue Standardmonat gespeichert wird.


## <a name="related-topics"></a>Verwandte Themen

[Erstellen eines Gebäudeplans für CQD](CQD-building-mapping.md)

[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

[Was ist CQD?](CQD-what-is-call-quality-dashboard.md)

[Einrichten des Dashboards für die Anrufqualität (CQD)](turning-on-and-using-call-quality-dashboard.md)

[CQD-Daten und-Berichte](CQD-data-and-reports.md)

[Verwenden von CQD zum Verwalten von Anruf-und Besprechungs Qualität](quality-of-experience-review-guide.md)

[In CQD verfügbare Dimensionen und Measures](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Datenstrom Klassifizierung in CQD](stream-classification-in-call-quality-dashboard.md)

[Verwenden von Power BI zum Analysieren von CQD-Daten](CQD-Power-BI-query-templates.md)
