---
title: Installieren von Power BI Connector zur Verwendung von CQD-Abfragevorlagen
ms.author: lolaj
author: LolaJacobsen
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
description: Installieren von Power BI Connector zur Verwendung von CQD-Abfragevorlagen (Call Quality Dashboard)
ms.openlocfilehash: 1c315dc0214ee0540ddce25fb8f0a1dc1794048f
ms.sourcegitcommit: ded1e92348b6c18aa31f7f67e68ced3db525977d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "46506168"
---
# <a name="install-power-bi-connector-to-use-cqd-query-templates"></a>Installieren von Power BI Connector zur Verwendung von CQD-Abfragevorlagen

Bevor Sie die Power BI-Abfragevorlagen (PBIX-Dateien) für das Microsoft Teams Call Quality-Dashboard (CQD) verwenden können, müssen Sie den Power BI-Connector für Microsoft CQD mit der im [Download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)enthaltenen Datei *MicrosoftCallQuality. PQx* installieren.

Lesen [verwenden Sie Power BI zum Analysieren von CQD-Daten für Teams](CQD-Power-BI-query-templates.md) , um mehr über diese Vorlagen zu erfahren.

Stellen Sie sicher, dass Sie über die richtige [CQD-Zugriffs Rolle](https://docs.microsoft.com/microsoftteams/turning-on-and-using-call-quality-dashboard#assign-roles-for-accessing-cqd) verfügen, um auf die Power BI-Berichte zuzugreifen.

## <a name="installation"></a>Installation

Der Vorgang zum Installieren eines benutzerdefinierten Connectors und zum Anpassen der Sicherheit, um die Verwendung des Connectors zu ermöglichen, wird in der [Power BI-Dokumentation](https://docs.microsoft.com/power-bi/desktop-connector-extensibility)ausführlich beschrieben. Aus Gründen der Einfachheit ist hier eine kurze Erläuterung zu finden:

1. Überprüfen Sie, ob Ihr Computer bereits über einen Ordner mit * \[ \] \\ Power BI- \\ benutzerdefinierten Dokumenten für Power BI-Desktops*verfügt   . Wenn dies nicht der Fall ist, erstellen Sie diesen Ordner. <sup>1</sup>

2. Laden Sie die connectordatei (eine * \* MEZ* -oder * \* PQx* -Datei) herunter, und legen Sie Sie im Verzeichnis *benutzerdefinierte Connectors* ab.

3. **Wenn es sich bei der connectordatei um eine * \* MEZ* -Datei handelt,** müssen Sie auch Ihre Sicherheitseinstellungen anpassen, wie in der [benutzerdefinierten Connector-Setup-Dokumentation](https://docs.microsoft.com/power-bi/desktop-connector-extensibility#data-extension-security)beschrieben.

Wenn eine neue Version dieses Power BI Connectors für Microsoft Teams veröffentlicht wird, ersetzen Sie einfach die alte connectordatei im Verzeichnis *benutzerdefinierte* Connectors durch die neue Datei.

## <a name="setup"></a>Installationsanforderungen

Um einen Bericht zu erstellen und Abfragen auszuführen, müssen Sie zuerst eine Verbindung mit der CQD-Datenquelle herstellen. Führen Sie die folgenden Schritte aus, um eine Verbindung herzustellen:

1. Klicken Sie auf der Registerkarte Start des Power BI-Desktops auf *Daten abrufen*.

    ![Screenshot: Power BI-Connector](media/CQD-power-bi-connector1-resize.png)

2. Das Fenster " *Daten abrufen* " sollte an dieser Stelle angezeigt werden. Navigieren Sie zu *Online Diensten*, wählen Sie dann *Microsoft-Anrufqualität (Beta)* und klicken Sie auf *verbinden*.

    ![Screenshot: Power BI-Connector](media/CQD-power-bi-connector2-resize.png)

3. Sie werden zur nächsten Anmeldung aufgefordert. Verwenden Sie die gleichen Anmeldeinformationen, die Sie für CQD verwenden. <sup>2</sup>

4. Die nächste Aufforderung gibt Ihnen die Möglichkeit zwischen zwei *Daten Verbindungsmodi*. Wählen Sie *DirectQuery* und klicken Sie auf *OK*.

5. Schließlich erhalten Sie eine abschließende Aufforderung, in der das gesamte Datenmodell für CQD angezeigt wird. An diesem Punkt werden keine Daten angezeigt, nur das Datenmodell für CQD. Wählen Sie *Laden* aus, um den Setupvorgang abzuschließen.

6. An diesem Punkt lädt Power BI das Datenmodell auf die Rechte Seite des Fensters. Die Seite bleibt ansonsten leer, und standardmäßig werden keine Abfragen geladen. Führen Sie die folgenden Schritte zum Erstellen von **Abfragen** aus, um eine Abfrage zu erstellen und Daten zurückzugeben.

Wenn einer der Schritte während des Setupvorgangs nicht ganz klar war, finden Sie [hier](https://docs.microsoft.com/power-bi/desktop-quickstart-connect-to-data)eine detailliertere Erläuterung des Prozesses.

## <a name="building-queries"></a>Erstellen von Abfragen

Nachdem die Einrichtung abgeschlossen ist, sollten Sie die Namen von mehreren hundert Dimensionen sehen und die Last im *Feld* Bereich misst. Das Erstellen von tatsächlichen Abfragen von hier aus ist einfach, wählen Sie einfach die Dimensionen und Measures aus, die Sie für Ihre Abfrage wünschen, und ziehen Sie Sie dann auf die Seite. Nachfolgend finden Sie eine ausführlichere Erläuterung mit einem einfachen Beispiel:

1. Wählen Sie die Visualisierung aus, die Sie verwenden möchten, im Bereich *Visualisierungen* . Auf der Seite sollte eine leere Version dieser Visualisierung angezeigt werden. In diesem Beispiel wird die *Tabellen* Visualisierung verwendet.

    ![Screenshot: Power BI-Connector](media/CQD-power-bi-connector3-resize.png)

2. Ermitteln Sie, welche Dimensionen und Measures (gekennzeichnet durch ein Aggregations Symbol mit dem Namen) Sie für Ihre Abfrage verwenden möchten, wählen Sie Sie manuell aus, und ziehen Sie Sie auf die schwarze Visualisierung. Ziehen Sie Sie alternativ in das Feld *Werte* unterhalb der Visualisierungsoptionen.

    ![Screenshot: Power BI-Connector](media/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > Das Dashboard für die Anrufqualität erfordert ein Maß für die Ausführung einer Abfrage. Fehler beim Hinzufügen eines Measures zu einer Abfrage führen dazu, dass die Abfrage fehlschlägt.

3. Wählen Sie als nächstes alle Dimensionen aus, nach denen Sie filtern möchten, und ziehen Sie Sie in das Feld *Filter für dieses visuelle* Element im Bereich *Filter* . Der CQD Power BI-Connector unterstützt derzeit die *grundlegende Filterung* (Auswählen von Werten aus einer Liste möglicher Dimensionswerte), *Erweiterte Filterung* (Manuelles angeben von Werten und Operanden zum Filtern auf, ähnlich wie bei erweiterten CQD) und *relative Datumsfilterung* (nur verfügbar für die Dimensionen *Endzeit* und *Anfangszeit* ). Das Filtern nach *Top N* wird von CQD nicht unterstützt.

    ![Screenshot: Power BI-Connector](media/CQD-power-bi-connector5-resize.png)

4. Wählen Sie schließlich im Bereich *Visualisierungen* die Registerkarte *Format* aus, um Ihre Abfrage zu formatieren und zu formatieren.

    > [!NOTE]
    > Für CQD-Abfragen ist mindestens ein Measure erforderlich, damit Sie ausgeführt werden können. Wenn Ihre Abfrage nicht geladen wird, überprüfen Sie, ob Sie ein Measure in die Abfrage aufgenommen haben.

## <a name="creating-a-drillthrough-report"></a>Erstellen eines Drillthrough-Berichts

Mit [Drillthrough in Power BI](https://docs.microsoft.com/power-bi/desktop-drillthrough) können Sie fokussierte Berichte erstellen, die Sie mithilfe der Werte anderer Berichte als Kontext schnell filtern können. Wenn Sie wissen, wie Sie Ihre erste Abfrage mit dem CQD-Konnektor erstellen, ist das Erstellen eines Drillthroughs noch einfacher.

1. Erstellen Sie eine weitere Seite für den fokussierten Bericht, und fügen Sie dann Ihre Abfragen zu dieser Seite hinzu.

2. Wählen Sie die Dimension aus, die Sie als Drillthroughfilter verwenden möchten, und ziehen Sie Sie auf das Feld *Drillthrough* unter im Bereich *Visualisierungen* .

    ![Screenshot: Power BI-Connector](media/CQD-power-bi-connector6-resize.png)

3. **Das wars\!** Jede andere Abfrage auf einer anderen Seite, die diese Dimension verwendet, kann nun auf diese Seite einen Drillthrough durchsetzen, wobei der Wert der Drillthrough-Dimension automatisch als Filter angewendet wird.

    ![Screenshot: Power BI-Connector](media/CQD-power-bi-connector7-resize.png)

Im Gegensatz zu erweiterten CQD unterstützt Power BI nicht sequenziellen Drillthrough. Solange eine Abfrage die erforderliche Dimension enthält, kann Sie Drillthrough zu jeder anderen Seite vornehmen.

### <a name="best-practice"></a>Bewährte Methode

Connector-Abfragen für die Anrufqualität sollten im Hinblick auf Drillthroughfunktionen entworfen werden. Anstatt zu versuchen, alle Daten gleichzeitig zu laden und dann mit Filtern zu verkleinern, beginnen Sie mit breiteren Abfragen mit niedriger Kardinalität, und führen Sie einen Drilldown zu Abfragen mit hoher Kardinalität durch. Wenn Sie beispielsweise versuchen zu diagnostizieren, welche Subnetze am meisten zu Qualitätsproblemen beitragen, ist es hilfreich, zunächst die Regionen und Länder zu identifizieren, die zu dem Problem beitragen, und dann einen Drilldown zu den Subnetzen in dieser Region oder in diesem Land durchführen. Die Verbindungs Vorlagen für die Anrufqualität wurden auf diese Weise entworfen, um als Beispiel zu fungieren.

## <a name="limitations"></a>Einschränkungen

Trotz der Nutzung von Power BI wird nicht alle Power BI-Funktionen vom CQD-Connector unterstützt, und zwar aufgrund von Einschränkungen für CQD-Datenmodell oder für DirectQuery-Connectors im Allgemeinen. In der folgenden Liste sind einige der bemerkenswerten Einschränkungen des Verbinders aufgeführt, die jedoch nicht als erschöpfend gelten sollten:

1. **Berechnete Spalten –** DirectQuery-Connectors haben in der Regel nur begrenzte Unterstützung für berechnete Spalten in Power BI. Während einige berechnete Spalten möglicherweise mit dem Verbinder funktionieren, sollten diese Ausnahmen berücksichtigt werden. In der Regel funktionieren berechnete Spalten nicht.

2. **Aggregationen –** Das CQD-Datenmodell basiert auf einem Cube-Modell, was bedeutet, dass Aggregationen bereits in Form von Measures unterstützt werden. Der Versuch, Aggregationen manuell zu verschiedenen Dimensionen hinzuzufügen oder den Aggregations eines Measures zu ändern, funktioniert nicht mit dem Verbinder, und es wird in der Regel zu einem Fehler führen.

3. **Benutzerdefinierte visuelle Elemente –** Obwohl der CQD-Connector mit einer Reihe von benutzerdefinierten visuellen Elementen funktioniert, können wir die Kompatibilität mit allen benutzerdefinierten visuellen Elementen nicht garantieren. Viele benutzerdefinierte visuelle Elemente Vertrauen auf die Verwendung berechneter Spalten oder importierter Daten, die von DirectQuery-Konnektoren nicht unterstützt werden.

4. **Verweisen auf zwischengespeicherte Daten –** Power BI unterstützt derzeit keine Verweise auf zwischengespeicherte Daten von einem DirectQuery-Connector in irgendeiner Weise. Jeder Versuch, auf die Ergebnisse einer Abfrage zu verweisen, führt zu einer neuen Abfrage.

5. **Relative Datenfilterung –** Wird im CQD-Connector unterstützt, jedoch nur mit den Dimensionen *Startzeit* und *Endzeit* . Obwohl die *Date* -Dimension möglicherweise die offensichtliche Wahl für die relative Datumsfilterung ist, wird *Datum* nicht als Datum-Uhrzeit-Objekt gespeichert und unterstützt daher keine relative Datumsfilterung in Power BI.

6. **Support für Government Community Cloud (gcc) –** Für Kunden in der gcc-Umgebung funktioniert der CQD Power BI-Connector bei Verwendung von Power BI Desktop. Der CQD Power BI Connector ist derzeit nicht mit dem Power BI-Dienst für gcc-Kunden kompatibel.

Bei den meisten dieser Probleme handelt es sich entweder um Einschränkungen des DirectQuery-Connector-Designs in Power BI oder um ein grundlegendes Design des CQD-Datenmodells.

## <a name="troubleshooting"></a>Problembehandlung

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>Ich versuche, die Datumsspalte als Datumsdaten Schnitt zu verwenden. Sobald ich den Datentyp dieser Spalte bis heute konvertiere, erhalte ich diesen Fehler

> **Die Daten für dieses Visual konnten nicht geladen**werden: OLE DB-oder ODBC-Fehler: [Ausdruck. Fehler] der Ausdruck konnte nicht in die Datenquelle gefaltet werden. Versuchen Sie es mit einem einfacheren Ausdruck.

Datumsdaten Schnitte werden vom Power BI-Connector nicht unterstützt. Wenn Sie einen Datumsbereich angeben möchten, wenden Sie zwei Filter auf den Bericht an, indem Sie einen Wert kleiner als und größer als Datum angeben.

Wenn die Datumsangaben, die Sie anzeigen möchten, aktuell sind, verwenden Sie alternativ einen relativen Datumsfilter, um nur Daten für die letzten N Tage/Wochen/Monate anzuzeigen.

## <a name="error-codes"></a>Fehler Codes

Da der CQD Power BI-Connector in Bezug auf Arten von Abfragen, die Sie erstellen können, weniger eingeschränkt als die Browser-APP ist, treten möglicherweise beim Erstellen von Abfragen gelegentlich verschiedene Fehler auf. Für den Fall, dass eine Fehlermeldung vom Typ "CQDError" angezeigt wird. RunQuery – Abfrageausführungsfehler ", verweisen Sie auf die nachstehende Liste mit der Fehlertyp-Nummer, die zur Behandlung des möglichen Problems mit der Abfrage bereitgestellt wurde. Im folgenden finden Sie die am häufigsten verwendeten Fehlertypen Codes, die mit dem CQD Power BI-Connector auftreten können:

- **ErrorType 1 – Abfrage Strukturfehler:** Ein Abfrage Strukturfehler wird in der Regel dadurch verursacht, dass der Connector keine ordnungsgemäß formatierte Abfrage erstellt. Dies geschieht am häufigsten bei Verwendung nicht unterstützter Funktionen, wie in den oben genannten Einschränkungen angegeben. Überprüfen Sie, ob Sie keine berechneten Spalten oder benutzerdefinierte visuelle Elemente für diese Abfrage verwenden.

  - **ErrorType 2 – Fehler beim Erstellen einer Abfrage:** Ein Fehler beim Erstellen einer Abfrage wird dadurch verursacht, dass der CQD-Connector die Abfrage, die Sie erstellen möchten, nicht ordnungsgemäß analysieren kann. Dies geschieht am häufigsten bei Verwendung nicht unterstützter Funktionen, wie in den oben genannten Einschränkungen angegeben. Überprüfen Sie, ob Sie keine berechneten Spalten oder benutzerdefinierte visuelle Elemente für diese Abfrage verwenden.

  - **ErrorType 5 – Ausführungs Timeout:** Die Abfrage hat die maximal mögliche Laufzeit erreicht, bevor ein Timeout eintritt. Versuchen Sie, der Abfrage weitere Filter hinzuzufügen, um deren Bereich zu begrenzen. Das Einschränken des Datenbereichs ist oft die effektivste Methode, um dies zu erreichen.

  - **ErrorType 7 – kein Messfehler:** Für CQD-Abfragen ist ein Measure erforderlich, um zu funktionieren. Überprüfen Sie, ob Ihre Abfrage Measure enthält. Measures im CQD-Verbinder werden durch das Aggregations Symbol (Summe) vor dem Namen gekennzeichnet.

Wenn weitere Fehler außerhalb dieses Bereichs auftreten, Benachrichtigen Sie das CQD-Team, damit wir Ihnen bei der Problembehandlung helfen und die Dokumentation gegebenenfalls aktualisieren können.

## <a name="footnotes"></a>Fußnoten

**<sup>1</sup>** bestimmte Prozesse und Apps (z. b. OneDrive) können dazu führen, dass der Stammordner Ihres Dokuments geändert wird. Stellen Sie sicher, dass das *Power BI-Desktop \\ benutzerdefinierte Connectors* -Verzeichnis innerhalb des aktuellen Ordners für Stammordner Dokumente gespeichert ist.

**<sup>2</sup>** die Anmeldeinformationen, die Sie für CQD verwenden, müssen *nicht* dieselben Anmeldeinformationen sein, die Sie für die Anmeldung bei der Power BI-Desktop Anwendung verwenden.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>Wann wird der Power BI-Connector über den Status "Beta" aktualisiert?

Trotz des Beta-Tags ist der Connector für die Anrufqualität für Power BI die Veröffentlichungsversion des Connectors und wurde offiziell vom Power BI-Team signiert, um dies zu widerspiegeln. Das Zertifizierungsverfahren zum Entfernen dieses Beta-Tags ist umfangreich und erfordert eine Verpflichtung des Power BI-Teams, den Connector auch direkt zu unterstützen. Aus Zeitgründen ist das Power BI-Team derzeit nicht in der Lage, diese Unterstützung und umfassendere Zertifizierung bereitzustellen, ist aber weiterhin bereit, die Sicherheit, Authentizität und allgemeine Funktionalität des Microsoft Call Quality Connectors zu bezeugen.

### <a name="why-does-the-connector-seem-slower-compared-to-advanced-cqd-in-the-browser-what-can-i-do-to-improve-performance"></a>Warum scheint der Verbinder im Vergleich zu erweiterten CQD im Browser langsamer zu sein? Was kann ich tun, um die Leistung zu verbessern?

Die Abfrageleistung für die verschiedenen Vorlagen ist sowohl im Browser als auch im Connector identisch.  Wie bei jeder anderen Standalone-app fügt Power BI auch die Authentifizierungs-und Renderingzeiten für unsere Leistung ein. Darüber hinaus besteht der Unterschied darin, wie viele gleichzeitige Abfragen ausgeführt werden. Da die in-Browser-Version von CQD weniger gut entwickelte und Informationsdichte Visualisierungsoptionen aufwies, waren die meisten unserer Berichte auf das Laden von 2-3-Abfragen auf einmal limitiert. Auf der anderen Seite werden in den Connector-Vorlagen häufig 20 + gleichzeitige Abfragen angezeigt. Wenn Sie Berichte erstellen möchten, die genauso reaktionsfähig sind wie die älteren, die Sie verwendet haben, versuchen Sie, Berichte mit nicht mehr als 2-3-Abfragen pro Registerkarte zu erstellen.

Weitere Informationen finden Sie in den folgenden Artikeln:

- [Optimierungs Handbuch für Power BI](https://docs.microsoft.com/power-bi/guidance/power-bi-optimization)
- [DirectQuery-modellanleitung](https://docs.microsoft.com/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>Ich finde, dass ich beim Ausführen von Abfragen regelmäßig in die 10.000-Zeilenbeschränkung verfüge. Wie kann ich den Connector abrufen, um mehr als 10.000 Zeilen zurückzugeben?

Der Grenzwert für die 10.000-Zeile ist tatsächlich auf dem API-Ende angegeben und soll die Leistung erheblich verbessern und das Risiko von Abfrage Ausführungsfehlern verringern, die sich aus unzureichendem Arbeitsspeicher ergeben.

Anstatt zu versuchen, die Anzahl der Ergebniszeilen zu erhöhen, empfiehlt es sich, die Berichte entsprechend den bewährten Methoden des Connectors umzustrukturieren. Die Vorlagen, die wir enthalten, wurden entwickelt, um diese bewährten Methoden zu veranschaulichen. Beginnen Sie, wenn möglich, mit einem Blick auf Ihre KPIs, indem Sie umfassendere, geringere Kardinalitäts Dimensionen verwenden, wie etwa Monat, Jahr, Datum, Region, Land usw. Von dort aus können Sie einen Drilldown in zunehmend höhere Kardinalität-Dimensionen durchführen. Die Berichte Helpdesk und Standort optimiert bieten beide gute Beispiele für diesen Drilldown-Workflow.



## <a name="related-topics"></a>Verwandte Themen

[Verwenden von Power BI zum Analysieren von CQD-Daten für Teams](CQD-Power-BI-query-templates.md)
