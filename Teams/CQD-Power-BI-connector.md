---
title: Installieren von Power BI Connector zur Verwendung von CQD-Abfragevorlagen
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
description: Installieren von Power BI Connector zur Verwendung von CQD-Abfragevorlagen (Call Quality Dashboard)
ms.openlocfilehash: 3ca8a4c70b23923dcf49906b85529c7b7e369008
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675257"
---
# <a name="install-microsoft-call-quality-connector-for-power-bi-to-use-call-quality-dashboard-query-templates"></a>Installieren des Microsoft-Anrufqualitätsconnectors für Power BI zur Verwendung von Abfragevorlagen für das Anrufqualitätsdashboard

Bevor Sie die Power BI-Abfragevorlagen (PBIX-Dateien) für Microsoft Teams Anrufqualitätsdashboard (Call Quality Dashboard, CQD) verwenden können, müssen Sie den Microsoft Call Quality Connector für Power BI mithilfe der im [Download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) enthaltenen Datei *"MicrosoftCallQuality.pqx*" installieren.

Lesen [Sie "Verwenden Power BI" zum Analysieren von CQD-Daten für Teams](CQD-Power-BI-query-templates.md), um mehr über diese Vorlagen zu erfahren.

Stellen Sie sicher, dass Sie über die richtige [CQD-Zugriffsrolle](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) für den Zugriff auf die Power BI Berichte verfügen.

> [!NOTE]
> Der Microsoft-Anrufqualitätsconnector unterstützt DirectQuery nur in Power BI; Der Importmodus wird nicht unterstützt. 

## <a name="installation"></a>Installation

Der Prozess für die Installation eines benutzerdefinierten Connectors und das Anpassen der Sicherheit, um die Verwendung des Connectors zu ermöglichen, wird in der [Power BI Dokumentation](/power-bi/desktop-connector-extensibility) ausführlich beschrieben. Der Einfachheit halber finden Sie hier eine kurze Erklärung:

1. Überprüfen Sie, ob Ihr Computer bereits über den *\[Ordner "Dokumente\]\\ Power BI Desktop\\ Custom Connectors" verfügt*. Wenn nicht, erstellen Sie diesen Ordner. <sup>1</sup>

2. Laden Sie die Connectordatei (entweder eine *\*MEZ* - oder *\*PQX-Datei* ) herunter, und platzieren Sie sie im Verzeichnis " *Benutzerdefinierte Connectors* ".

3. **Wenn es sich bei der Connectordatei um eine *\*MEZ-Datei* handelt,** müssen Sie auch Ihre Sicherheitseinstellungen anpassen, wie in der [Benutzerdefinierten Connector-Setupdokumentation](/power-bi/desktop-connector-extensibility#data-extension-security) beschrieben.

Wenn eine neue Version des Microsoft-Anrufqualitätsconnectors veröffentlicht wird, ersetzen Sie die alte Connectordatei im Verzeichnis " *Benutzerdefinierte Connectors* " durch die neue Datei.

## <a name="setup"></a>Installationsanforderungen

Um einen Bericht zu erstellen und Abfragen auszuführen, müssen Sie zuerst eine Verbindung mit der CQD-Datenquelle herstellen. Führen Sie die folgenden Schritte aus, um eine Verbindung herzustellen:

1. Klicken Sie auf der Registerkarte "Start" von Power BI Desktop auf *"Daten abrufen"*.

    ![Abrufen von Daten im Power BI Connector.](media/CQD-power-bi-connector1-resize.png)

2. Das Fenster " *Daten abrufen* " sollte an diesem Punkt angezeigt werden. Navigieren Sie zu *Onlinediensten*, wählen Sie dann *Microsoft-Anrufqualität (Beta)* aus, und drücken Sie *Verbinden*.

    ![Microsoft-Anrufqualität im Power BI Connector.](media/CQD-power-bi-connector2-resize.png)

3. Sie werden aufgefordert, sich als Nächstes anzumelden. Verwenden Sie die gleichen Anmeldeinformationen, die Sie für das Anrufqualitätsdashboard verwenden. <sup>2</sup>

4. Bei der nächsten Eingabeaufforderung erhalten Sie die Option zwischen zwei *Data Connectivity-Modi*. Wählen Sie *"DirectQuery"* aus, und klicken Sie auf *"OK"*.

5. Schließlich erhalten Sie eine letzte Eingabeaufforderung, in der das gesamte Datenmodell für das Anrufqualitätsdashboard angezeigt wird. An diesem Punkt sind keine Daten sichtbar, nur das Datenmodell für CQD. Wählen Sie *"Laden"* aus, um den Setupvorgang abzuschließen.

6. An diesem Punkt lädt Power BI das Datenmodell auf der rechten Seite des Fensters. Die Seite bleibt andernfalls leer, und standardmäßig werden keine Abfragen geladen. Fahren Sie unten mit **dem Erstellen von Abfragen** fort, um eine Abfrage zu erstellen und Daten zurückzugeben.

Wenn einer der Schritte während dieses Setupvorgangs nicht klar war, finden Sie eine ausführlichere Erläuterung des Vorgangs in der [Schnellstartanleitung: Verbinden zu Daten in Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data).

## <a name="building-queries"></a>Erstellen von Abfragen

Sobald die Einrichtung abgeschlossen ist, sollten die Namen mehrerer hundert Dimensionen und Measures im *Bereich "Felder* " angezeigt werden. Das Erstellen tatsächlicher Abfragen von hier aus ist einfach. Wählen Sie einfach die Dimensionen und Measures aus, die Sie für Ihre Abfrage benötigen, und ziehen Sie sie dann auf die Seite. Hier ist eine ausführlichere Erläuterung mit einem einfachen Beispiel:

1. Wählen Sie im Bereich *"Visualisierungen* " die Visualisierung aus, die Sie verwenden möchten. Eine leere Version dieser Visualisierung sollte auf der Seite angezeigt werden. Für die Zwecke dieses Beispiels verwenden wir die Tabellenvisualisierung.

    ![Bereich "Visualisierungen" im Power BI Connector.](media/CQD-power-bi-connector3-resize.png)

2. Bestimmen Sie, welche Dimensionen und Measures (gekennzeichnet durch ein Aggregationssymbol anhand ihres Namens) Sie für Ihre Abfrage verwenden möchten, wählen Sie sie dann manuell aus, und ziehen Sie sie auf die schwarze Visualisierung. Ziehen Sie sie alternativ auf das Feld *"Werte"* unter den Visualisierungsoptionen.

    ! Visualisierungsabfrage im Power BI Connector.] (Medien/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > Das Anrufqualitätsdashboard erfordert ein Measure, damit eine Abfrage ausgeführt werden kann. Fehler beim Hinzufügen eines Measures zu einer Abfrage führen dazu, dass diese Abfrage fehlschlägt.

3. Wählen Sie als Nächstes alle Dimensionen aus, nach der Sie filtern möchten, und ziehen Sie sie auf die *Filter in diesem visuellen* Feld im *Bereich "Filter"* . Der Microsoft-Anrufqualitätsconnector unterstützt derzeit *die Standardfilterung* (Auswahlwerte aus einer Liste möglicher Dimensionswerte), *erweiterte Filterung* (manuelle Angabe von Werten und Operanden, nach der gefiltert werden soll, ähnlich wie beim Anrufqualitätsdashboard) und *relative Datumsfilterung* (nur für *endzeit* - und *Startzeitdimensionen* verfügbar). Das Filtern nach *top N* wird vom Anrufqualitätsdashboard nicht unterstützt.

    ![Visualisierungsfilter im Power BI Connector.](media/CQD-power-bi-connector5-resize.png)

    > [!IMPORTANT]
    > Filter werden nur unterstützt, wenn sie auf Dimensionen angewendet werden. Das Filtern nach den Werten von Messungen wird im Anrufqualitätsdashboard nicht unterstützt.

4. Wählen Sie schließlich die Registerkarte " *Format* " im Bereich *"Visualisierungen* " aus, um Ihre Abfrage zu formatieren und zu formatieren.

    > [!NOTE]
    > Abfragen des Anrufqualitätsdashboards erfordern mindestens ein Measure, um ausgeführt werden zu können. Wenn die Abfrage nicht geladen wird, überprüfen Sie doppelt, ob Sie ein Measure in die Abfrage eingeschlossen haben.

## <a name="creating-a-drillthrough-report"></a>Erstellen eines Drillthrough-Berichts

[Drillthrough in Power BI](/power-bi/desktop-drillthrough) allows you to create focused reports that you can quickly filter using the values of other reports as context. Sobald Sie wissen, wie Sie Ihre erste Abfrage mit dem Microsoft Call Quality Connector erstellen, ist das Erstellen einer Drillthrough noch einfacher.

1. Erstellen Sie eine weitere Seite für den bericht mit Relevanz, und fügen Sie dann Ihre Abfragen zu dieser Seite hinzu.

2. Wählen Sie die Dimension aus, die Sie als Drillthrough-Filter verwenden möchten, und ziehen Sie sie auf das Feld " *Drillthrough* " im Bereich *"Visualisierungen* ".

    ![Drillthrough in the Power BI Connector.](media/CQD-power-bi-connector6-resize.png)

3. **Das wars\!** Jede andere Abfrage auf einer anderen Seite, die diese Dimension verwendet, kann nun einen Drilldown auf diese Seite ausführen und den Wert der Drillthrough-Dimension automatisch als Filter anwenden.

    ![Drillthrough-Filter im Power BI Connector.](media/CQD-power-bi-connector7-resize.png)

Im Gegensatz zum Anrufqualitätsdashboard unterstützt Power BI nicht sequenzielle Drillthrough-Methoden. Wenn eine Abfrage die erforderliche Dimension enthält, kann sie einen Drilldown zu einer beliebigen anderen Seite ausführen.

### <a name="best-practice"></a>Bewährte Methode

Microsoft Call Quality Connector-Abfragen sollten unter Berücksichtigung der Drillthrough-Funktionalität konzipiert werden. Anstatt zu versuchen, alle Daten gleichzeitig zu laden und dann mit Filtern nach unten zu zersplizieren, beginnen Sie mit umfangreicheren Abfragen mit niedriger Kardinalität, und führen Sie einen Drilldown zu Abfragen mit hoher Kardinalität durch. Wenn Sie beispielsweise versuchen zu diagnostizieren, welche Subnetze am meisten zu Qualitätsproblemen beitragen, ist es hilfreich, zuerst die Regionen und Länder zu identifizieren, die zu dem Problem beitragen, und dann einen Drilldown zu den Subnetzen in dieser Region oder diesem Land durchzuführen. Die Connectorvorlagen für die Anrufqualität wurden auf diese Weise entwickelt, um als Beispiel zu dienen.

## <a name="limitations"></a>Einschränkungen

Obwohl Power BI verwendet wird, werden nicht alle Power BI Funktionen vom Microsoft-Anrufqualitätsconnector unterstützt, entweder aufgrund von Einschränkungen beim Datenmodell des Anrufqualitätsdashboards oder bei DirectQuery-Connectors im Allgemeinen. In der nachstehenden Liste sind einige der bemerkenswerteren Einschränkungen des Connectors aufgeführt, diese Liste sollte jedoch nicht als erschöpfend betrachtet werden:

1. **Berechnete Spalten –** DirectQuery-Connectors haben im Allgemeinen eingeschränkte Unterstützung für berechnete Spalten in Power BI. Einige berechnete Spalten funktionieren möglicherweise mit dem Connector, da diese Spalten Ausnahmen sind. In der Regel funktionieren berechnete Spalten nicht.

2. **Aggregationen –** Das Datenmodell des Anrufqualitätsdashboards basiert auf einem Cubemodell, was bedeutet, dass Aggregationen bereits in Form von Measures unterstützt werden. Der Versuch, Aggregationen manuell zu verschiedenen Dimensionen hinzuzufügen oder den Aggregationstyp eines Measures zu ändern, funktioniert nicht mit dem Connector und führt im Allgemeinen zu einem Fehler.

3. **Benutzerdefinierte visuelle Elemente –** Während der Microsoft Call Quality Connector mit einer Reihe von benutzerdefinierten visuellen Elementen funktioniert, können wir keine Kompatibilität mit allen benutzerdefinierten visuellen Elementen garantieren. Viele benutzerdefinierte visuelle Elemente basieren auf der Verwendung berechneter Spalten oder importierter Daten, die von DirectQuery-Connectors nicht unterstützt werden.

4. **Verweisen auf zwischengespeicherte Daten –** Power BI unterstützt derzeit in keiner Weise das Verweisen auf zwischengespeicherte Daten aus einem DirectQuery-Connector. Jeder Versuch, auf die Ergebnisse einer Abfrage zu verweisen, führt zu einer neuen Abfrage.

5. **Relative Datenfilterung –** Wird im Microsoft-Anrufqualitätsconnector unterstützt, jedoch nur mit den Dimensionen *"Startzeit* " und " *Endzeit* ". Obwohl die *Datumsdimension* die offensichtliche Wahl für die relative Datumsfilterung ist, wird *Date* nicht als Datums-Uhrzeit-Objekt gespeichert und unterstützt daher keine relative Datumsfilterung in Power BI.

6. **Nur Messabfragen -** Werden derzeit im Microsoft-Anrufqualitätsconnector nicht unterstützt. Beim Erstellen einer Visualisierung mit drei oder mehr Maßen und ohne Dimensionen werden die Spaltendaten transponiert. Um dies zu vermeiden, schließen Sie immer mindestens eine Dimension (z. B. Monat Jahr) in Ihre Visualisierungen ein. Dies soll in einer bevorstehenden Version des Microsoft-Anrufqualitätsconnectors für Power BI behoben werden.

7. **Government Community Cloud (GCC) Support –** Für Kunden in der GCC-Umgebung funktioniert der Microsoft-Anrufqualitätsconnector nur bei Verwendung Power BI Desktop. Der Microsoft-Anrufqualitätsconnector ist derzeit nicht mit dem Power BI-Dienst für GCC Kunden kompatibel.

Die meisten dieser Probleme sind entweder Einschränkungen für den DirectQuery-Konnektorentwurf in Power BI oder grundlegend für den Entwurf des CQD-Datenmodells.

## <a name="troubleshooting"></a>Problembehandlung

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>Ich versuche, die Spalte "Datum" als Datenschnitt zu verwenden. Sobald ich den Datentyp dieser Spalte in "Datum" konvertiert habe, wird dieser Fehler angezeigt.

> **Die Daten für dieses visuelle Element konnten nicht geladen** werden: OLE DB- oder ODBC-Fehler: [Expression.Error] Der Ausdruck konnte nicht in die Datenquelle gefaltet werden. Versuchen Sie es mit einem einfacheren Ausdruck.

Datumsschnitte werden mit dem Microsoft-Anrufqualitätsconnector nicht unterstützt. Um einen Datumsbereich anzugeben, wenden Sie zwei Filter auf den Bericht an, indem Sie ein Datum kleiner und größer angeben.

Wenn die anzuzeigenden Datumsangaben neu sind, wenden Sie alternativ einen relativen Datumsfilter an, um nur Daten für die letzten N Tage/Wochen/Monate anzuzeigen.


### <a name="when-i-add-certain-dimensions-to-my-reports-the-visual-immediately-returns-couldnt-load-the-data-for-this-visual-removing-the-dimension-fixes-the-visual----what-is-happening"></a>Wenn ich meinen Berichten bestimmte Dimensionen hinzufüge, gibt das Visuelle sofort **"Die Daten für dieses visuelle Element konnten nicht geladen werden"** zurück. Das Entfernen der Dimension behebt das visuelle Element – was geschieht?

Dies ist ein bekanntes Problem im Microsoft-Anrufqualitätsconnector. Alle Dimensionen, die als ganze Zahl verfügbar gemacht werden, werden in Power BI als "Aggregatspalte" angezeigt, wobei Power BI eine standardmäßige Zusammenfassungsaktion (in der Regel "Summe") versucht. In einigen Fällen gelingt es diesem Verhalten, die Werte zu addieren, obwohl das Ergebnis nicht nützlich ist, da die "Summe" einer Dimension wie dem zweiten WLAN-Kanal bedeutungslos ist. In anderen Fällen schlägt diese Zusammenfassungsaktion fehl und verursacht Fehler im visuellen Bereich.

Um dieses Problem zu umgehen, entfernen Sie zunächst die Dimension aus dem visuellen Element. Wählen Sie die Dimension aus der Liste "Felder" aus, navigieren Sie im Menüband zur Registerkarte "Spaltentools", klicken Sie auf das Dropdownmenü "Zusammenfassung", und wählen Sie **"Nicht zusammenfassen**" aus. Die Dimension kann nun dem visuellen Element erneut hinzugefügt werden.


## <a name="error-codes"></a>Fehlercodes

Da der Microsoft-Anrufqualitätsconnector für Power BI hinsichtlich der Arten von Abfragen, die Sie erstellen können, weniger eingeschränkt ist als die Browser-App, können beim Erstellen Ihrer Abfragen gelegentlich eine Reihe von Fehlern auftreten. Für den Fall, dass Sie eine Fehlermeldung vom Typ "CQDError. RunQuery – Query Execution Error", verweisen Sie auf die nachstehende Liste mit der angegebenen ErrorType-Nummer, um das mögliche Problem mit der Abfrage zu beheben. Im Folgenden sind die häufigsten Fehlertypcodes aufgeführt, die beim CQD-Power BI Connector auftreten können:

- **ErrorType 1 – Abfragestrukturfehler:** Ein Abfragestrukturfehler wird in der Regel dadurch verursacht, dass der Connector keine ordnungsgemäß formatierte Abfrage erstellt. Dies geschieht am häufigsten, wenn nicht unterstützte Funktionen verwendet werden, wie in den obigen Einschränkungen angegeben. Überprüfen Sie, ob Sie keine berechneten Spalten oder benutzerdefinierten visuellen Elemente für diese Abfrage verwenden.

  - **ErrorType 2 – Abfrageerstellungsfehler:** Ein Abfrageerstellungsfehler wird verursacht, wenn der Microsoft-Anrufqualitätsconnector die Abfrage, die Sie erstellen möchten, nicht ordnungsgemäß analysieren kann. Dies geschieht am häufigsten, wenn nicht unterstützte Funktionen verwendet werden, wie in den obigen Einschränkungen angegeben. Überprüfen Sie, ob Sie keine berechneten Spalten oder benutzerdefinierten visuellen Elemente für diese Abfrage verwenden.

  - **ErrorType 5 – Ausführungstimeout:** Die Abfrage hat die maximal mögliche Laufzeit vor dem Timing erreicht. Versuchen Sie, der Abfrage weitere Filter hinzuzufügen, um den Bereich einzuschränken. Das Einschränken des Datenbereichs ist häufig die effektivste Methode, um dies zu erreichen.

  - **ErrorType 7 - No Measurements Error:** Abfragen des Anrufqualitätsdashboards erfordern ein Measure, um funktionieren zu können. Überprüfen Sie doppelt, ob ihre Abfrage Measure enthält. Measures im Microsoft-Anrufqualitätsconnector werden durch das Aggregationssymbol (Summe) vor ihrem Namen gekennzeichnet.

Wenn zusätzliche Fehler außerhalb dieses Bereichs auftreten, benachrichtigen Sie das Team des Anrufqualitäts-Dashboards, damit wir bei der Problembehandlung helfen und die Dokumentation entsprechend aktualisieren können.

## <a name="footnotes"></a>Fußnoten

**<sup>1</sup>** Bestimmte Prozesse und Apps (z. B. OneDrive) können dazu führen, dass sich der Stammordner "Dokumente" ändert. Stellen Sie sicher, dass sich das Verzeichnis *Power BI Desktop\\ Custom Connectors* innerhalb des aktuellen Stammordners "Dokumente" befindet.

**<sup>2</sup>** Die Anmeldeinformationen, die Sie für das Anrufqualitäts-Dashboard verwenden, müssen *nicht* mit den Anmeldeinformationen übereinstimmen, die Sie für die Anmeldung bei der Power BI Desktop-App selbst verwenden.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>Wann wird der Power BI Connector vom Status "Beta" aktualisiert?

Trotz des Beta-Tags ist der Microsoft Call Quality (Beta)-Connector für Power BI die erste "Release"-Version des Connectors und wurde offiziell vom Power BI-Team unterzeichnet, um dies widerzuspiegeln. Zum Zeitpunkt der ersten Version des Connectors konnte das Power BI-Team keinen Support und eine umfassendere Zertifizierung bereitstellen, war aber dennoch bereit, die Sicherheit, Authentizität und allgemeine Funktionalität des Microsoft-Anrufqualitätsconnectors zu bestätigen. Mit Blick auf die Zukunft planen wir, in naher Zukunft in den Microsoft-Anrufqualitätsconnector für Power BI zu investieren.

### <a name="why-does-the-connector-seem-slower-compared-to-call-quality-dashboard-in-the-browser-what-can-i-do-to-improve-performance"></a>Warum wirkt der Connector im Vergleich zum Anrufqualitätsdashboard im Browser langsamer? Was kann ich tun, um die Leistung zu verbessern?

Die Abfrageleistung für die verschiedenen Vorlagen ist im Browser und im Connector tatsächlich identisch.  Wie jede andere eigenständige App fügt Power BI die Authentifizierungs- und Renderingzeit unserer Leistung hinzu. Darüber hinaus besteht der Unterschied in der Anzahl der gleichzeitig ausgeführten Abfragen. Da die In-Browser-Version des Anrufqualitäts-Dashboards weniger gut entwickelte und informationsdichte Visualisierungsoptionen hatte, waren die meisten unserer Berichte auf das Gleichzeitige Laden von 2-3 Abfragen beschränkt. Andererseits werden in den Connectorvorlagen häufig mehr als 20 gleichzeitige Abfragen angezeigt. Wenn Sie Berichte erstellen möchten, die genauso reaktionsfähig sind wie die älteren, die Sie gewohnt waren, versuchen Sie, Berichte mit nicht mehr als 2-3 Abfragen pro Registerkarte zu erstellen.

Weitere Informationen finden Sie in den folgenden Artikeln:

- [Optimierungsleitfaden für Power BI](/power-bi/guidance/power-bi-optimization)
- [DirectQuery-Modellanleitung](/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>Ich finde, dass ich beim Ausführen von Abfragen routinemäßig auf das Limit von 10.000 Zeilen läuft. Wie kann ich erreichen, dass der Verbinder mehr als 10.000 Zeilen zurückgibt?

Der Grenzwert von 10.000 Zeilen wird tatsächlich am API-Ende angegeben und soll dazu beitragen, die Leistung erheblich zu verbessern und das Risiko von Abfrageausführungsfehlern zu verringern, die sich aus geringen Speicherbedingungen ergeben.

Anstatt zu versuchen, die Anzahl der Ergebniszeilen zu erhöhen, empfiehlt es sich, Ihre Berichte entsprechend den bewährten Methoden des Connectors neu zu strukturieren. Die von uns enthaltenen Vorlagen sollen diese bewährten Methoden veranschaulichen. Sehen Sie sich nach Möglichkeit Ihre KPIs mit breiteren, niedrigeren Kardinalitätsdimensionen an, z. B. "Monat", "Jahr", "Datum", "Region", "Land" usw. Von dort aus können Sie einen Drilldown in immer höhere Kardinalitätsdimensionen ausführen. Helpdesk- und Location-Enhanced-Berichte bieten beide gute Beispiele für diesen Drilldownworkflow.



## <a name="related-topics"></a>Verwandte Themen

[Verwenden von Power BI zum Analysieren von CQD-Daten für Teams](CQD-Power-BI-query-templates.md)
