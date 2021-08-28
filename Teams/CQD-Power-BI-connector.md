---
title: Installieren Power BI Connector zur Verwendung von CQD-Abfragevorlagen
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
description: Installieren Power BI Connector für die Verwendung von Anrufqualitätsdashboard-Abfragevorlagen (CQD)
ms.openlocfilehash: 258d3be034bd956c518f1ed7a67273f064b383b6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593319"
---
# <a name="install-microsoft-call-quality-connector-for-power-bi-to-use-call-quality-dashboard-query-templates"></a>Installieren des Microsoft Call Quality Connectors für Power BI zur Verwendung von Abfragevorlagen für das Anrufqualitätsdashboard

Bevor Sie die Power BI-Abfragevorlagen (PBIX-Dateien) für das Microsoft Teams-Anrufqualitätsdashboard (CQD) verwenden können, müssen Sie den Microsoft Call Quality Connector für Power BI mithilfe der im Download enthaltenen *Datei "MicrosoftCallQuality.pqx"* [installieren.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)

Lesen [Sie Power BI zum Analysieren von AQD-Daten für Teams](CQD-Power-BI-query-templates.md) Informationen zu diesen Vorlagen.

Stellen Sie sicher, dass Sie über die richtige Zugriffsrolle für [AQD verfügen,](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) um auf die Power BI zugreifen zu können.

> [!NOTE]
> Der Connector für die Microsoft-Anrufqualität unterstützt DirectQuery nur in Power BI; Der Importmodus wird nicht unterstützt. 

## <a name="installation"></a>Installation

Der Vorgang zum Installieren eines benutzerdefinierten Verbinders und zum Anpassen der Sicherheit zur Aktivierung der Verwendung des Verbinders wird in der Power BI [ausführlich beschrieben.](/power-bi/desktop-connector-extensibility) Der Einfachheit halber finden Sie hier eine kurze Erklärung:

1. Überprüfen Sie, ob Ihr Computer bereits über einen Ordner Dokumente Power BI Desktop *\[ \] \\ \\ Connectors* verfügt. Andern falls nicht, erstellen Sie diesen Ordner. <sup>1</sup>

2. Laden Sie die Connectordatei (entweder eine *\* MEZ-* oder *\* PQX-Datei)* herunter, und legen Sie sie im Verzeichnis für benutzerdefinierte *Connectors* ab.

3. **Wenn es sich bei der Connectordatei um eine *\* MEZ-Datei* handelt,** müssen Sie auch Ihre Sicherheitseinstellungen anpassen, wie in der Dokumentation zum Einrichten benutzerdefinierter [Connectors beschrieben.](/power-bi/desktop-connector-extensibility#data-extension-security)

Wenn eine neue Version des Microsoft-Connectors für die Anrufqualität  veröffentlicht wird, ersetzen Sie die alte Connectordatei im Verzeichnis benutzerdefinierte Connectors durch die neue Datei.

## <a name="setup"></a>Installationsanforderungen

Um einen Bericht zu erstellen und Abfragen ausführen zu können, müssen Sie zuerst eine Verbindung mit der AQD-Datenquelle herstellen. Führen Sie die folgenden Schritte aus, um eine Verbindung herzustellen:

1. Klicken Sie auf der Registerkarte start Power BI Desktop auf *Daten erhalten*.

    ![Screenshot: Power BI Connector](media/CQD-power-bi-connector1-resize.png)

2. Das *Fenster Daten* erhalten sollte an diesem Punkt angezeigt werden. Navigieren Sie *zu Online Services*, wählen Sie dann Microsoft *Anrufqualität (Beta) aus,* und klicken Sie *Verbinden*.

    ![Screenshot: Power BI Connector](media/CQD-power-bi-connector2-resize.png)

3. Sie werden aufgefordert, sich als Nächstes anmelden. Verwenden Sie die gleichen Anmeldeinformationen, die Sie für das Anrufqualitätsdashboard verwenden. <sup>2</sup>

4. Die nächste Eingabeaufforderung bietet Ihnen die Option zwischen zwei *Datenverbindungsmodi*. Wählen Sie *DirectQuery aus,* und klicken Sie *auf OK.*

5. Schließlich erhalten Sie eine abschließende Eingabeaufforderung, in der das gesamte Datenmodell für das Anrufqualitätsdashboard angezeigt wird. An diesem Punkt sind keine Daten sichtbar, nur das Datenmodell für das AQD. Wählen Sie *Laden aus,* um den Setupvorgang abzuschließen.

6. An diesem Punkt Power BI das Datenmodell auf der rechten Seite des Fensters geladen. Andernfalls bleibt die Seite leer, und es werden standardmäßig keine Abfragen geladen. Fahren Sie unten **mit dem Erstellen von Abfragen** fort, um eine Abfrage zu erstellen und Daten zurückzukehren.

Wenn einer der Schritte während dieses Setupvorgangs nicht eindeutig war, finden Sie eine ausführlichere Erläuterung des Vorgangs in [Schnellstart:](/power-bi/desktop-quickstart-connect-to-data)Verbinden zu Daten in Power BI Desktop.

## <a name="building-queries"></a>Erstellen von Abfragen

Nach Abschluss der Einrichtung sollten die Namen mehrerer hundert Dimensionen und Measures, die geladen wurden, im Bereich *Felder angezeigt* werden. Das Erstellen tatsächlicher Abfragen von hier aus ist einfach. Wählen Sie einfach die Dimensionen und Measures aus, die für Ihre Abfrage verwendet werden sollen, und legen Sie sie dann per Drag & Drop auf der Seite ab. Hier ist eine ausführlichere Erläuterung mit einem einfachen Beispiel:

1. Wählen Sie im Bereich Visualisierungen die *Visualisierung aus, die Sie verwenden* möchten. Auf der Seite sollte eine leere Version dieser Visualisierung angezeigt werden. Für dieses Beispiel verwenden wir die *Tabellenvisualisierung.*

    ![Screenshot: Power BI Connector](media/CQD-power-bi-connector3-resize.png)

2. Legen Sie fest, welche Dimensionen und Measures (durch ein Aggregationssymbol durch ihren Namen gekennzeichnet) Sie für die Abfrage verwenden möchten. Wählen Sie sie dann manuell aus, und ziehen Sie sie auf die schwarze Visualisierung. Ziehen Sie sie alternativ auf das *Feld* Werte unter den Visualisierungsoptionen.

    ![Screenshot: Power BI Connector](media/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > Für das Anrufqualitätsdashboard ist ein Measure erforderlich, damit eine Abfrage ausgeführt werden kann. Wenn Sie einer Abfrage kein Measure hinzufügen, kann diese Abfrage nicht mehr ausgeführt werden.

3. Wählen Sie als Nächstes alle Dimensionen aus,  nach die Sie filtern möchten, und ziehen Sie sie in das Feld Filter für dieses visuelle Feld im *Bereich Filter.* Der Microsoft-Connector für die Anrufqualität unterstützt derzeit Standardfilterung *(Wählen* Sie Werte aus einer Liste möglicher Dimensionswerte *aus),* Erweiterte Filterung (manuelle Angabe  von Werten und Operanden zum Filtern, ähnlich wie anrufqualitätsdashboard) und *Relative* Datumsfilterung (nur für die Dimensionen Endzeit und Startzeit verfügbar).  Das Filtern nach *Top N* wird vom Anrufqualitätsdashboard nicht unterstützt.

    ![Screenshot: Power BI Connector](media/CQD-power-bi-connector5-resize.png)

    > [!IMPORTANT]
    > Filter werden nur unterstützt, wenn sie auf Dimensionen angewendet werden. Das Filtern nach den Werten der Messwerte wird im Anrufqualitätsdashboard nicht unterstützt.

4. Wählen Sie schließlich im  Bereich *Visualisierungen* die Registerkarte Format aus, um Ihre Abfrage zu formatieren und zu formatieren.

    > [!NOTE]
    > Anrufqualitätsdashboardabfragen erfordern mindestens ein Measure, um ausgeführt zu werden. Wenn die Abfrage nicht geladen wird, überprüfen Sie, ob Sie ein Measure in die Abfrage einbezogen haben.

## <a name="creating-a-drillthrough-report"></a>Erstellen eines Drillthroughberichts

[Mithilfe von Drillthrough in Power BI](/power-bi/desktop-drillthrough) können Sie fokussierte Berichte erstellen, die Sie schnell filtern können, indem Sie die Werte anderer Berichte als Kontext verwenden. Sobald Sie wissen, wie Sie Ihre erste Abfrage mit dem Microsoft-Connector für die Anrufqualität erstellen, ist die Erstellung eines Drillthroughs noch einfacher.

1. Erstellen Sie eine weitere Seite für den Bericht mit Fokus, und fügen Sie dann Ihre Abfragen zu dieser Seite hinzu.

2. Wählen Sie die Dimension aus, die Sie als Drillthroughfilter verwenden möchten, und ziehen Sie sie auf das *Drillthroughfeld* unter dem *Bereich Visualisierungen.*

    ![Screenshot: Power BI Connector](media/CQD-power-bi-connector6-resize.png)

3. **Das wars\!** Jede andere Abfrage auf einer anderen Seite, die diese Dimension verwendet, kann nun einen Drillthrough bis zu dieser Seite ausführen und automatisch den Wert der Drillthroughdimension als Filter anwenden.

    ![Screenshot: Power BI Connector](media/CQD-power-bi-connector7-resize.png)

Im Gegensatz zum Anrufqualitätsdashboard Power BI nicht sequenzielles Drillthrough unterstützt. Wenn eine Abfrage die erforderliche Dimension enthält, kann sie einen Drillthrough bis zu einer beliebigen anderen Seite ausführen.

### <a name="best-practice&quot;></a>Bewährte Methode

Microsoft Call Quality Connector queries should be designed with drillthrough functionality. Anstatt zu versuchen, alle Daten auf einmal zu laden und dann mit Filtern nach unten zu slicingen, beginnen Sie mit umfangreicheren Abfragen mit geringer Kardinalität, und führen Sie einen Drilldown zu Abfragen mit hoher Kardinalität durch. Wenn Sie z. B. versuchen, die Subnetze zu diagnostizieren, die zu den Qualitätsproblemen am meisten beitragen, ist es hilfreich, zuerst die Regionen und Länder zu identifizieren, die zu dem Problem beitragen, und dann einen Drilldown zu den Subnetzen in dieser Region oder diesem Land zu erstellen. Die Verbindervorlagen für die Anrufqualität wurden auf diese Weise entworfen, um als Beispiel zu fungieren.

## <a name=&quot;limitations&quot;></a>Einschränkungen

Obwohl Power BI verwendet wird, werden nicht alle Power BI-Funktionen vom Microsoft-Connector für die Anrufqualität unterstützt, entweder durch Einschränkungen beim Datenmodell des Anrufqualitätsdashboards oder bei DirectQuery-Connectors im Allgemeinen. In der nachstehenden Liste werden einige der beachtenswerten Einschränkungen des Connectors aufgeführt, diese Liste sollte jedoch nicht als erschöpfend betrachtet werden:

1. **Berechnete Spalten –** DirectQuery-Connectors bieten im Allgemeinen eingeschränkte Unterstützung für berechnete Spalten in Power BI. Einige berechnete Spalten funktionieren möglicherweise mit dem Connector, da diese Spalten Ausnahmen sind. Im Allgemeinen funktionieren berechnete Spalten nicht.

2. **Aggregationen –** Das Datenmodell des Anrufqualitätsdashboards baut auf einem Cubemodell auf, d. h., Aggregationen werden bereits in Form von Measures unterstützt. Der Versuch, Aggregationen manuell zu verschiedenen Dimensionen hinzuzufügen oder den Aggregationstyp eines Measures zu ändern, funktioniert nicht mit dem Connector und führt im Allgemeinen zu einem Fehler.

3. **Benutzerdefinierte Visualisierungen –** Der Connector für die Microsoft-Anrufqualität funktioniert zwar mit einer Reihe benutzerdefinierter visueller Elemente, aber wir können nicht die Kompatibilität mit allen benutzerdefinierten visualisierungen garantieren. Viele benutzerdefinierte visualisierungen sind von der Verwendung berechneter Spalten oder importierter Daten angewiesen, die von DirectQuery-Connectors nicht unterstützt werden.

4. **Verweisen auf zwischengespeicherte** Daten – Power BI unterstützt derzeit in keinem Fall das Verweisen auf zwischengespeicherte Daten von einem DirectQuery-Connector. Jeder Versuch, auf die Ergebnisse einer Abfrage zu verweisen, führt zu einer neuen Abfrage.

5. **Relative Datenfilterung –** Wird vom Microsoft-Connector für Die Anrufqualität unterstützt, jedoch nur mit den Abmessungen *Startzeit* und *Endzeit.* Obwohl die *Datumsdimension* die offensichtliche Wahl für die relative Datumsfilterung *ist,* wird Datum nicht als Datums-/Uhrzeitobjekt gespeichert und unterstützt daher keine relative Datumsfilterung in Power BI.

6. **Nur Messungsabfragen –** Der Connector für die Microsoft-Anrufqualität wird derzeit nicht unterstützt. Beim Erstellen einer Visualisierung mit drei oder mehr Maßen und ohne Dimensionen werden die Spaltendaten transponiert. Um dies zu vermeiden, schließen Sie immer mindestens eine Dimension (z. B. &quot;Monatsjahr") in Ihre Visualisierungen ein. Dieses Problem wird in einer anstehenden Veröffentlichung des Microsoft Call Quality Connectors für Power BI.

7. **Government Community Cloud (GCC) Support –** Für Kunden in der GCC-Umgebung funktioniert der Microsoft-Connector für die Anrufqualität nur bei Power BI Desktop Verbindungen. Der Connector für die Microsoft-Anrufqualität ist derzeit nicht mit dem Power BI für GCC kompatibel.

Die meisten dieser Probleme sind entweder Einschränkungen für das DirectQuery-Connectordesign in Power BI oder grundlegend für den Entwurf des CQD-Datenmodells.

## <a name="troubleshooting"></a>Problembehandlung

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>Ich versuche, die Spalte Datum als Datenschnitt zu verwenden. Sobald ich den Datentyp dieser Spalte in "Datum" konvertiert habe, wird diese Fehlermeldung angezeigt

> **Die Daten für dieses** visuelle Objekt konnten nicht geladen werden: OLE DB- oder ODBC-Fehler: [Ausdruck.Fehler] Der Ausdruck konnte nicht auf die Datenquelle gefaltet werden. Versuchen Sie es mit einem einfacheren Ausdruck.

Datumsschnitte werden vom Microsoft-Connector für die Anrufqualität nicht unterstützt. Zum Angeben eines Datumsbereichs wenden Sie zwei Filter auf den Bericht an, indem Sie einen kleineren und größeren als den Datumsumfang angeben.

Wenn die Datumsangaben, die Sie anzeigen möchten, zuletzt verwendet wurden, verwenden Sie alternativ einen relativen Datumsfilter, um nur Daten für die letzten N Tage/Wochen/Monate anzeigen zu können.

## <a name="error-codes"></a>Fehlercodes

Da der Microsoft-Connector für die Anrufqualität für Power BI hinsichtlich der Arten von Abfragen, die Sie erstellen können, weniger eingeschränkt ist als die Browser-App, kann es gelegentlich zu Fehlern beim Erstellen von Abfragen kommt. Wenn Sie eine Fehlermeldung vom Typ "CQDError. RunQuery – Abfrageausführungsfehler", verweisen Sie in der nachstehenden Liste auf die Fehlertypnummer, die angegeben ist, um das mögliche Problem mit der Abfrage zu beheben. Im Folgenden werden die am häufigsten verwendeten Fehlertypcodes für den CQD-Power BI Connector angezeigt:

- **Fehlertyp 1 – Abfragestrukturfehler:** Ein Fehler bei der Abfragestruktur wird in der Regel durch den Fehler des Connectors verursacht, dass eine Abfrage mit ordnungsgemäßer Formatierung nicht erstellt wurde. Dies geschieht am häufigsten, wenn nicht unterstützte Funktionen verwendet werden, wie in den vorstehenden Einschränkungen beschrieben. Vergewissern Sie sich, dass Sie keine berechneten Spalten oder benutzerdefinierten Visualisierungen für diese Abfrage verwenden.

  - **Fehlertyp 2 – Fehler beim Erstellen von Abfragen:** Ein Fehler beim Erstellen von Abfragen wird dadurch verursacht, dass der Microsoft-Connector für die Anrufqualität die Abfrage, die Sie erstellen möchten, nicht ordnungsgemäß analysieren kann. Dies geschieht am häufigsten, wenn nicht unterstützte Funktionen verwendet werden, wie in den vorstehenden Einschränkungen beschrieben. Vergewissern Sie sich, dass Sie keine berechneten Spalten oder benutzerdefinierten Visualisierungen für diese Abfrage verwenden.

  - **ErrorType 5 – Ausführungstimeout:** Die Abfrage hat die maximal mögliche Laufzeit vor dem Timeout erreicht. Versuchen Sie, der Abfrage weitere Filter hinzufügen, um ihren Bereich zu beschränken. Die Ein grenzen des Datenbereichs ist häufig die effektivste Möglichkeit, dies zu erreichen.

  - **ErrorType 7: Keine Messfehler:** Für Abfragen des Anrufqualitätsdashboards ist ein Measure erforderlich, damit es funktioniert. Vergewissern Sie sich, dass die Abfrage Kennzahl enthält. Measures im Microsoft Call Quality Connector sind durch das Aggregationssymbol (Summe) vor ihrem Namen gekennzeichnet.

Wenn weitere Fehler außerhalb dieses Bereichs auftreten, benachrichtigen Sie das Anrufqualitäts-Dashboard-Team, damit wir ihnen bei der Problembehandlung helfen und die Dokumentation entsprechend aktualisieren können.

## <a name="footnotes"></a>Fußnoten

**<sup>1</sup>** Bestimmte Prozesse und Apps (z. B. OneDrive) können dazu führen, dass sich der Stammordner "Dokumente" ändert; Stellen Sie sicher, *dass Power BI Desktop \\ Verzeichnis* für benutzerdefinierte Connectors im Ordner Dokumente des aktuellen Stammordners gespeichert ist.

**<sup>2</sup>** Die Anmeldeinformationen, die Sie  für das Anrufqualitätsdashboard verwenden, müssen nicht mit den Anmeldeinformationen identisch sein, die Sie für die Anmeldung bei der Power BI Desktop-App verwenden.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>Wann wird Power BI Connector vom Status "Beta" aktualisiert?

Trotz des Beta-Tags ist der Microsoft Call Quality (Beta)-Connector für Power BI die erste "Release"-Version des Connectors und wurde vom Power BI-Team offiziell mit Sicherheit signiert, um dies zu zeigen. Zum Zeitpunkt der ersten Veröffentlichung des Connectors konnte das Power BI-Team keine Unterstützung und breitere Zertifizierung bereitstellen, war aber dennoch darauf vorbereitet, die Sicherheit, Echtheit und allgemeine Funktionalität des Microsoft Call Quality-Connectors zu belegen. In Zukunft planen wir, in naher Zukunft in den Connector für die Microsoft Power BI Anrufqualität zu investieren.

### <a name="why-does-the-connector-seem-slower-compared-to-call-quality-dashboard-in-the-browser-what-can-i-do-to-improve-performance"></a>Warum scheint der Verbinder im Vergleich zum Anrufqualitätsdashboard im Browser langsamer zu sein? Wie kann ich die Leistung verbessern?

Die Abfrageleistung für die verschiedenen Vorlagen ist im Browser und im Connector tatsächlich identisch.  Wie jede andere eigenständige App fügt Power BI Authentifizierungs- und Renderzeit zu unserer Leistung hinzu. Darüber hinaus ist der Unterschied bei der Anzahl der gleichzeitig ausgeführten Abfragen zu erkennen. Da die Browserversion des Anrufqualitätsdashboards weniger gut entwickelte Visualisierungsoptionen und Visualisierungsoptionen mit informationsdichtem Daten enthält, waren die meisten unserer Berichte auf das Laden von 2-3 Abfragen gleichzeitig beschränkt. Andererseits werden in den Connectorvorlagen häufig mehr als 20 gleichzeitige Abfragen angezeigt. Wenn Sie Berichte erstellen möchten, die genauso gut wie die älteren Berichte, die Sie gewohnt sind, erstellen Sie Berichte mit nicht mehr als 2-3 Abfragen pro Registerkarte.

Weitere Informationen finden Sie in den folgenden Artikeln:

- [Leitfaden zur Optimierung Power BI](/power-bi/guidance/power-bi-optimization)
- [Leitfaden zum DirectQuery-Modell](/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>Ich finde, dass beim Ausführen von Abfragen routinemäßig das Limit von 10.000 Zeilen überschritten wird. Wie kann ich den Verbinder so konfigurieren, dass mehr als 10.000 Zeilen zurückgegeben werden?

Das Limit von 10.000 Zeilen wird tatsächlich am API-Ende angegeben und soll dazu beitragen, die Leistung erheblich zu verbessern und das Risiko von Fehlern bei der Abfrageausführung zu verringern, die sich durch bedingungen mit wenig Arbeitsspeicher ergeben.

Anstatt zu versuchen, die Anzahl der Ergebniszeile zu erhöhen, ist es am besten, Ihre Berichte entsprechend den bewährten Methoden des Connectors neu zu strukturieren. Die enthaltenen Vorlagen sollen diese bewährten Methoden veranschaulichen. Beginnen Sie, wenn möglich, indem Sie Ihre KPIs unter Verwendung breiterer Dimensionen der Unteren Kardinalität, z. B. Monat, Jahr, Datum, Region, Land usw., anzeigen. Von dort aus können Sie drilldowns zu zunehmend höheren Kardinalitätsdimensionen führen. Die Helpdesk- und Location-Enhanced-Berichte bieten gute Beispiele für diesen Drilldownworkflow.



## <a name="related-topics"></a>Verwandte Themen

[Verwenden Power BI Zum Analysieren von AQD-Daten für Teams](CQD-Power-BI-query-templates.md)
