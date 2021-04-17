---
title: Installieren von Power BI Connector für die Verwendung von CQD-Abfragevorlagen
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
localization_priority: Normal
description: Installieren von Power BI Connector für die Verwendung von CQD-Abfragevorlagen (Call Quality Dashboard)
ms.openlocfilehash: 15e02ed85720cf96babc470e021df1a960d4b608
ms.sourcegitcommit: 4e1f5d99c1d0612dc5b50f850280983867ff53d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51874481"
---
# <a name="install-power-bi-connector-to-use-cqd-query-templates"></a>Installieren von Power BI Connector für die Verwendung von CQD-Abfragevorlagen

Bevor Sie die Power BI-Abfragevorlagen (PBIX-Dateien) für das Microsoft Teams Call Quality Dashboard (CQD) verwenden können, müssen Sie den Power BI Connector für Microsoft CQD mithilfe der im Download enthaltenen *MicrosoftCallQuality.pqx-Datei* [installieren.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)

Weitere Informationen zu diesen Vorlagen finden Sie unter Verwenden von Power BI zum Analysieren von [CQD-Daten](CQD-Power-BI-query-templates.md) für Teams.

Stellen Sie sicher, dass Sie über die richtige [CQD-Zugriffsrolle verfügen,](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) um auf die Power BI-Berichte zu zugreifen.

> [!NOTE]
> Der CQD Power BI Connector unterstützt nur DirectQuery in Power BI. Der Importmodus wird nicht unterstützt. 

## <a name="installation"></a>Installation

Der Vorgang zum Installieren eines benutzerdefinierten Verbinders und zum Anpassen der Sicherheit zum Aktivieren der Verwendung des Verbinders wird in der [Power BI-Dokumentation ausführlich beschrieben.](/power-bi/desktop-connector-extensibility) Aus Gründen der Einfachheit finden Sie hier eine kurze Erläuterung:

1. Überprüfen Sie, ob Ihr Computer bereits über einen Ordner "Benutzerdefinierte Connectors für *\[ Power BI \] \\ \\ Desktop"-Dokumente* verfügt. Andern falls nicht, erstellen Sie diesen Ordner. <sup>1</sup>

2. Laden Sie die Connectordatei (entweder eine *\* MEZ-* oder *\* PQX-Datei)* herunter, und platzieren Sie sie im Verzeichnis *Benutzerdefinierte Connectors.*

3. **Wenn es sich bei der Connectordatei um eine *\* MEZ-Datei* handelt,** müssen Sie auch Ihre Sicherheitseinstellungen anpassen, wie in der Dokumentation zum Einrichten von benutzerdefinierten [Connectors beschrieben.](/power-bi/desktop-connector-extensibility#data-extension-security)

Wenn eine neue Version dieses Power BI Connector für Microsoft Teams veröffentlicht  wird, ersetzen Sie einfach die alte Connectordatei im Verzeichnis Benutzerdefinierte Connectors durch die neue Datei.

## <a name="setup"></a>Installationsanforderungen

Um einen Bericht zu erstellen und Abfragen ausführen zu können, müssen Sie zuerst eine Verbindung mit der CQD-Datenquelle herstellen. Führen Sie die folgenden Schritte aus, um eine Verbindung herzustellen:

1. Klicken Sie auf der Registerkarte Start von Power BI Desktop auf *Daten herunterladen.*

    ![Screenshot: Power BI Connector](media/CQD-power-bi-connector1-resize.png)

2. Das *Fenster* Daten erhalten sollte an diesem Punkt angezeigt werden. Navigieren Sie zu *Onlinedienste,* wählen Sie *dann Microsoft Anrufqualität (Beta) aus,* und klicken Sie auf *Verbinden.*

    ![Screenshot: Power BI Connector](media/CQD-power-bi-connector2-resize.png)

3. Als Nächstes werden Sie zur Anmeldung aufgefordert. Verwenden Sie dieselben Anmeldeinformationen, die Sie für CQD verwenden. <sup>2</sup>

4. Mit der nächsten Eingabeaufforderung erhalten Sie die Option zwischen zwei *Datenkonnektivitätsmodi.* Wählen *Sie DirectQuery aus,* und klicken Sie auf *OK.*

5. Schließlich erhalten Sie eine abschließende Eingabeaufforderung, in der das gesamte Datenmodell für CQD angezeigt wird. An diesem Punkt werden keine Daten angezeigt, sondern nur das Datenmodell für CQD. Wählen Sie *Laden aus,* um den Setupvorgang abzuschließen.

6. An diesem Punkt wird das Datenmodell von Power BI auf die rechte Seite des Fensters geladen. Andernfalls bleibt die Seite leer, und es werden standardmäßig keine Abfragen geladen. Fahren Sie mit **Erstellen von Abfragen unten** fort, um eine Abfrage zu erstellen und Daten zurück zu geben.

Wenn einer der Schritte während dieses Setupvorgangs nicht vollständig klar war, finden Sie eine ausführlichere Erläuterung des Vorgangs in [Schnellstart: Herstellen](/power-bi/desktop-quickstart-connect-to-data)einer Verbindung mit Daten in Power BI Desktop.

## <a name="building-queries"></a>Erstellen von Abfragen

Sobald die Einrichtung abgeschlossen ist, sollten die Namen von mehreren hundert Dimensionen und Measures im Bereich Felder *geladen* werden. Das Erstellen von tatsächlichen Abfragen von hier aus ist einfach: Wählen Sie einfach die Dimensionen und Measures aus, die Sie für ihre Abfrage verwenden möchten, und ziehen Sie sie dann, und legen Sie sie auf die Seite ab. Im Folgenden finden Sie eine ausführlichere Erläuterung mit einem einfachen Beispiel:

1. Wählen Sie im Bereich Visualisierungen die Visualisierung *aus,* die Sie verwenden möchten. Eine leere Version dieser Visualisierung sollte auf der Seite angezeigt werden. Für die Zwecke dieses Beispiels verwenden wir die *Tabellenvisualisierung.*

    ![Screenshot: Power BI Connector](media/CQD-power-bi-connector3-resize.png)

2. Bestimmen Sie, welche Dimensionen und Measures (durch ein Aggregationssymbol durch ihren Namen gekennzeichnet) sie für die Abfrage verwenden möchten, wählen Sie sie dann manuell aus, und ziehen Sie sie auf die schwarze Visualisierung. Ziehen Sie sie alternativ auf das *Feld* Werte unter den Visualisierungsoptionen.

    ![Screenshot: Power BI Connector](media/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > Für das Anrufqualitätsdashboard ist ein Measure für die Ausführung einer Abfrage erforderlich. Wenn Sie einer Abfrage kein Measure hinzufügen, kann die Abfrage fehlschlagen.

3. Wählen Sie als Nächstes alle Dimensionen aus, nach die Sie filtern möchten, und ziehen Sie sie in das Feld Filter *in* diesem visuellen Feld im *Bereich Filter.* Der CQD Power BI  Connector unterstützt zurzeit standardfiltern (Auswahlwerte aus einer Liste möglicher Dimensionswerte),  Erweiterte Filterung (manuelles Angeben von Werten und Operanden, nach denen gefiltert werden soll, ähnlich wie Advanced CQD) und *Relative* Datumsfilterung (nur für die Dimensionen *Endzeit* und *Startzeit* verfügbar). Das Filtern nach *Top N* wird von CQD nicht unterstützt.

    ![Screenshot: Power BI Connector](media/CQD-power-bi-connector5-resize.png)

4. Wählen Sie schließlich im  Bereich Visualisierungen die Registerkarte *Format* aus, um die Abfrage zu formatieren und zu formatieren.

    > [!NOTE]
    > Für CQD-Abfragen ist mindestens ein Measure erforderlich, um ausgeführt zu werden. Wenn Ihre Abfrage nicht geladen wird, überprüfen Sie, ob Sie ein Measure in die Abfrage eingeschlossen haben.

## <a name="creating-a-drillthrough-report"></a>Erstellen eines Drillthroughberichts

[Mit drillthrough in Power BI](/power-bi/desktop-drillthrough) können Sie berichte mit Schwerpunkt erstellen, die Sie mithilfe der Werte anderer Berichte als Kontext schnell filtern können. Sobald Sie wissen, wie Sie Ihre erste Abfrage mit dem CQD Connector erstellen, ist das Erstellen eines Drillthroughs noch einfacher.

1. Erstellen Sie eine weitere Seite für den bericht mit Schwerpunkt, und fügen Sie dann Ihre Abfragen zu dieser Seite hinzu.

2. Wählen Sie die Dimension aus, die Sie als Drillthroughfilter verwenden möchten, und ziehen Sie sie unter im Bereich *Visualisierungen* auf das Feld *Drillthrough.*

    ![Screenshot: Power BI Connector](media/CQD-power-bi-connector6-resize.png)

3. **Das wars\!** Jede andere Abfrage auf einer anderen Seite, die diese Dimension verwendet, kann nun drillthrough auf diese Seite ausführen und den Wert der Drillthroughdimension automatisch als Filter anwenden.

    ![Screenshot: Power BI Connector](media/CQD-power-bi-connector7-resize.png)

Im Gegensatz zu Advanced CQD unterstützt Power BI nicht sequenzielle Drillthroughs. Solange eine Abfrage die erforderliche Dimension enthält, kann sie einen Drillthrough zu jeder anderen Seite ausführen.

### <a name="best-practice"></a>Bewährte Methode

Anrufqualitätsconnectorabfragen sollten unter Berücksichtigen der Drillthroughfunktionalität entwickelt werden. Statt zu versuchen, alle Daten gleichzeitig zu laden und dann mit Filtern zu schneiden, beginnen Sie mit breiteren Abfragen mit geringer Kardinalität, und führen Sie einen Drilldown zu Abfragen mit hoher Kardinalität aus. Wenn Sie beispielsweise versuchen zu diagnostizieren, welche Subnetze am meisten zu Qualitätsproblemen beitragen, ist es hilfreich, zuerst die Regionen und Länder zu identifizieren, die zu dem Problem beitragen, und dann einen Drilldown zu den Subnetzen in dieser Region oder diesem Land zu machen. Die Verbindervorlagen für die Anrufqualität wurden auf diese Weise entworfen, um als Beispiel zu fungieren.

## <a name="limitations"></a>Einschränkungen

Obwohl Power BI verwendet wird, werden nicht alle Power BI-Funktionen vom CQD Connector unterstützt, entweder als Folge von Einschränkungen beim CQD-Datenmodell oder auf DirectQuery-Connectors im Allgemeinen. In der nachstehenden Liste sind einige der beachtenswerten Einschränkungen des Connectors aufgeführt, diese Liste sollte jedoch nicht als erschöpfend betrachtet werden:

1. **Berechnete Spalten –** DirectQuery-Connectors bieten im Allgemeinen eingeschränkte Unterstützung für berechnete Spalten in Power BI. Einige berechnete Spalten funktionieren möglicherweise mit dem Connector, diese sollten jedoch als Ausnahmen betrachtet werden. In der Regel funktionieren berechnete Spalten nicht.

2. **Aggregationen –** Das CQD-Datenmodell ist auf einem Cubemodell aufgebaut, was bedeutet, dass Aggregationen bereits in Form von Measures unterstützt werden. Der Versuch, Aggregationen manuell zu verschiedenen Dimensionen hinzuzufügen oder den Aggregationstyp eines Measures zu ändern, funktioniert nicht mit dem Connector, und dies führt im Allgemeinen zu einem Fehler.

3. **Benutzerdefinierte Visuelle Elemente –** Der CQD Connector funktioniert zwar mit einer Reihe von benutzerdefinierten Visuellen, aber wir können nicht die Kompatibilität mit allen benutzerdefinierten Visuellen garantieren. Viele benutzerdefinierte visuelle Elemente sind auf die Verwendung von berechneten Spalten oder importierten Daten angewiesen, weder oder die von DirectQuery-Connectors unterstützt werden.

4. **Verweisen auf zwischengespeicherte Daten –** Power BI unterstützt derzeit in keinem Fall das Verweisen auf zwischengespeicherte Daten von einem DirectQuery-Connector. Jeder Versuch, auf die Ergebnisse einer Abfrage zu verweisen, führt zu einer neuen Abfrage.

5. **Relative Datenfilterung –** Wird im CQD Connector unterstützt, jedoch nur mit den Dimensionen *Startzeit* *und Endzeit.* Obwohl die *Datumsdimension* die offensichtliche Wahl für die relative Datumsfilterung ist, wird *Datum* nicht als Datumszeitobjekt gespeichert und unterstützt daher keine relative Datumsfilterung in Power BI.

6. **Unterstützung für die Government Community Cloud (GCC) –** Für Kunden in der GCC-Umgebung funktioniert der CQD Power BI Connector bei Verwendung von Power BI Desktop. Der CQD Power BI-Connector ist derzeit nicht mit dem Power BI-Dienst für GCC-Kunden kompatibel.

Die meisten dieser Probleme sind entweder Einschränkungen des DirectQuery-Connectordesigns in Power BI oder grundlegende Aspekte des Entwurfs des CQD-Datenmodells.

## <a name="troubleshooting"></a>Problembehandlung

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>Ich versuche, die Spalte Datum als Datenschnitt zu verwenden. Sobald ich den Datentyp dieser Spalte in Datum konvertiert habe, wird dieser Fehler angezeigt.

> **Die Daten für dieses** visuelle Objekt konnten nicht geladen werden: OLE DB- oder ODBC-Fehler: [Ausdruck.Fehler] Der Ausdruck konnte nicht an die Datenquelle gefaltet werden. Versuchen Sie es mit einem einfacheren Ausdruck.

Datumsschnitte werden vom Power BI Connector nicht unterstützt. Um einen Datumsbereich anzugeben, wenden Sie zwei Filter auf den Bericht an, und geben Sie einen kleineren und größeren Als-Datum-Wert an.

Wenn die Datumsangaben, die Sie anzeigen möchten, zuletzt verwendet werden, wenden Sie alternativ einen relativen Datumsfilter an, um nur Daten für die letzten N Tage/Wochen/Monate zu zeigen.

## <a name="error-codes"></a>Fehlercodes

Da der CQD Power BI Connector hinsichtlich der Arten von Abfragen, die Sie erstellen können, weniger eingeschränkt ist als die Browser-App, kann es gelegentlich zu einer Reihe von Fehlern beim Erstellen Ihrer Abfragen führen. Für den Fall, dass Sie eine Fehlermeldung vom Typ "CQDError. RunQuery – Abfrageausführungsfehler", verweisen Sie auf die nachstehende Liste mit der angegebenen Fehlertypnummer, um das mögliche Problem mit der Abfrage zu beheben. Im Folgenden werden die am häufigsten verwendeten Fehlertypcodes für den CQD Power BI Connector angezeigt:

- **ErrorType 1 – Abfragestrukturfehler:** Ein Abfragestrukturfehler wird in der Regel dadurch verursacht, dass der Connector eine ordnungsgemäß formatierte Abfrage nicht erstellt. Dies geschieht am häufigsten, wenn nicht unterstützte Funktionen verwendet werden, wie in den vorstehenden Einschränkungen angegeben. Überprüfen Sie, ob Sie keine berechneten Spalten oder benutzerdefinierten Visuellen für diese Abfrage verwenden.

  - **ErrorType 2 – Fehler beim Erstellen von Abfragen:** Ein Abfrageaufbaufehler wird dadurch verursacht, dass der CQD-Connector die zu erstellende Abfrage nicht ordnungsgemäß analysieren kann. Dies geschieht am häufigsten, wenn nicht unterstützte Funktionen verwendet werden, wie in den vorstehenden Einschränkungen angegeben. Überprüfen Sie, ob Sie keine berechneten Spalten oder benutzerdefinierten Visuellen für diese Abfrage verwenden.

  - **ErrorType 5 – Ausführungstimeout:** Die Abfrage hat die maximal mögliche Laufzeit vor dem Timeout erreicht. Versuchen Sie, der Abfrage weitere Filter zu hinzufügen, um den Umfang zu beschränken. Das Einen des Datenbereichs ist häufig die effektivste Möglichkeit, dies zu erreichen.

  - **ErrorType 7 – Kein Messfehler:** Für CQD-Abfragen ist ein Measure erforderlich, um funktionieren zu können. Überprüfen Sie, ob ihre Abfrage measure enthält. Measures im CQD Connector werden durch das Aggregationssymbol (Summe) vor ihrem Namen gekennzeichnet.

Wenn weitere Fehler außerhalb dieses Bereichs auftreten, benachrichtigen Sie das CQD-Team, damit wir ihnen bei der Problembehandlung helfen und die Dokumentation entsprechend aktualisieren können.

## <a name="footnotes"></a>Fußnoten

**<sup>1</sup>** Bestimmte Prozesse und Apps (z. B. OneDrive) können dazu führen, dass sich ihr Stammordner "Dokumente" ändert. Stellen Sie sicher, *dass das Power BI Desktop Custom \\ Connectors-Verzeichnis* innerhalb des aktuellen Stammordnerordners Dokumente abgelegt ist.

**<sup>2</sup>** Die Anmeldeinformationen, die Sie  für CQD verwenden, müssen nicht die gleichen Anmeldeinformationen sein, die Sie für die Anmeldung bei der Power BI-Desktop-App selbst verwenden.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>Wann wird der Power BI Connector vom Status "Beta" aktualisiert?

Trotz des Betatags ist der Anrufqualitätsconnector für Power BI die Releaseversion des Connectors und wurde vom Power BI-Team offiziell signiert, um dies zu widerspiegeln. Der Zertifizierungsprozess zum Entfernen dieses Betatags ist umfangreich und erfordert eine Verpflichtung des Power BI-Teams, den Connector auch direkt zu unterstützen. Aufgrund von Zeiteinschränkungen kann das Power BI-Team diesen Support und die umfassendere Zertifizierung derzeit nicht bereitstellen, ist aber weiterhin bereit, die Sicherheit, Authentizität und allgemeine Funktionalität des Microsoft Call Quality Connector zu bestätigen.

### <a name="why-does-the-connector-seem-slower-compared-to-advanced-cqd-in-the-browser-what-can-i-do-to-improve-performance"></a>Warum scheint der Verbinder im Vergleich zu Advanced CQD im Browser langsamer zu sein? Was kann ich tun, um die Leistung zu verbessern?

Die Abfrageleistung für die verschiedenen Vorlagen ist sowohl im Browser als auch im Connector identisch.  Wie jede andere eigenständige App fügt Power BI die Authentifizierungs- und Renderzeit zu unserer Leistung hinzu. Darüber hinaus liegt der Unterschied in der Anzahl der gleichzeitig ausgeführten Abfragen. Da die Browserversion von CQD weniger gut entwickelte und informationsdichte Visualisierungsoptionen hatte, waren die meisten unserer Berichte auf das Laden von 2 bis 3 Abfragen gleichzeitig beschränkt. Auf der anderen Seite werden in den Verbindervorlagen häufig mehr als 20 gleichzeitige Abfragen angezeigt. Wenn Sie Berichte erstellen möchten, die genauso reaktionsfähig sind wie die älteren Berichte, die Sie gewohnt sind, versuchen Sie, Berichte mit nicht mehr als 2 bis 3 Abfragen pro Registerkarte zu erstellen.

Weitere Informationen finden Sie in den folgenden Artikeln:

- [Leitfaden zur Optimierung von Power BI](/power-bi/guidance/power-bi-optimization)
- [DirectQuery-Modellleitfäden](/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>Ich finde, dass ich beim Ausführen von Abfragen routinemäßig den Grenzwert von 10.000 Zeilen einlaufe. Wie kann der Verbinder mehr als 10.000 Zeilen zurückgeben?

Der Grenzwert von 10.000 Zeilen wird tatsächlich am API-Ende angegeben, und er soll dazu beitragen, die Leistung erheblich zu verbessern und das Risiko von Abfrageausführungsfehlern aufgrund geringer Speicherbedingungen zu verringern.

Statt zu versuchen, die Anzahl der Ergebniszeile zu erhöhen, sollten Sie Ihre Berichte nach bewährten Methoden des Connectors neu strukturieren. Die enthaltenen Vorlagen sollen diese bewährten Methoden veranschaulichen. Beginnen Sie, wenn möglich, indem Sie Ihre KPIs mit breiteren, niedrigeren Kardinalitätsdimensionen wie Monat, Jahr, Datum, Region, Land usw. anzeigen. Von dort aus können Sie einen Drilldown zu immer höheren Kardinalitätsdimensionen erstellen. Das Helpdesk und Location-Enhanced-Berichte bieten gute Beispiele für diesen Drilldownworkflow.



## <a name="related-topics"></a>Verwandte Themen

[Verwenden von Power BI zum Analysieren von CQD-Daten für Teams](CQD-Power-BI-query-templates.md)
