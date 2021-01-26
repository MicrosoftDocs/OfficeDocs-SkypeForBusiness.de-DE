---
title: CQD-Entwicklungsbeispiele
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
ms.assetid: 8ca9bf7a-2d6f-48d5-a821-531009726525
description: 'Zusammenfassung: Sehen Sie sich ein Lernprogramm und Entwicklungsbeispiele für das Anrufqualitätsdashboard an. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 193a03662d6f771b19c57017d909cc6574a755ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832725"
---
# <a name="cqd-development-samples"></a>CQD-Entwicklungsbeispiele

**Zusammenfassung:** Sehen Sie sich ein Lernprogramm und Entwicklungsbeispiele für das Anrufqualitätsdashboard an. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.

Dieser Artikel enthält ein Lernprogramm und Beispiele zur Entwicklung des Anrufqualitätsdashboards (Call Quality Dashboard, CQD).

## <a name="call-quality-dashboard-cqd-development-samples"></a>Beispiele für die Entwicklung des Anrufqualitätsdashboards (CQD)

Lernprogramm: Erstellen einer angepassten Berichtspräsentation mithilfe der CQD-Datendienst- und Repositorydienst-API.

### <a name="introduction-to-cqd"></a>Einführung in CQD

CQD bietet schnellen und einfachen Zugriff auf aggregierte Informationen zur Anrufqualität für lokale Skype for Business Server-Bereitstellungen. CQD besteht aus drei Komponenten: der QoE-Archivdatenbank, dem Cube und dem Portal. Das Portal ist die Hauptpräsentationsschicht und kann weiter in die folgenden drei Komponenten unterteilt werden:

1. Datendienst, auf den authentifizierte Benutzer über die Daten-API für das Anrufqualitätsdashboard [(CQD) in Skype for Business Server zugreifen können.](data-api.md)

2. Repositorydienst, auf den authentifizierte Benutzer über die Repository-API für das Anrufqualitätsdashboard [(CQD) in Skype for Business Server zugreifen können.](repository-api.md)

3. Webportal, die HTML5-basierte Schnittstelle, die CQD-Benutzern angezeigt wird und mit der sie interagieren. Dies ist für authentifizierte Benutzer zugänglich.

Die im Webportal angezeigten Berichte sind in "Berichtssätze" eingeteilt. Die Abbildung zeigt einen Berichtsatz mit zwei Berichten. Jeder Bericht in diesem Dashboard unten zeigt Abfrageergebnisse zur Anzahl der anrufe, Anrufe schlechter Qualität und Prozentsatz schlechter Anrufe für mehrere Monate, mit verschiedenen Filtern angewendet. 

![CQD-Beispielbericht](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

CQD wird nach der Call Quality Methodology (CQM) erstellt, sodass der Standardsatz von Berichten auf den von CQM eingeführten Untersuchungsfluss ausgerichtet ist. Benutzer haben auch die Flexibilität, benutzerdefinierte Berichte zu bearbeiten oder zu erstellen, um ihre Anforderungen zu erfüllen. Da es jedoch mehrere Möglichkeiten gibt, die Daten zu visualisieren, kann die vom CQD bereitgestellte Visualisierung möglicherweise nicht die Anforderungen jedes Benutzers vollständig erfüllen. In solchen Situationen kann ein Benutzer die Daten-APIs und Repository-APIs verwenden, um benutzerdefinierte Berichtsseiten zu erstellen. Wir werden in diesem Lernprogramm eine Reihe von Beispielen durchgehen.

### <a name="how-the-dashboard-consumes-the-data-service"></a>Verwendung des Datendiensts durch das Dashboard

Beim Navigieren zur CQD-Homepage (z. B. werden der Berichtssatz und die entsprechenden Berichte für einen authentifizierten und autorisierten Benutzer aus dem http://localhost/cqd) Repositorydienst abgerufen. Eine vollständige URL wird aus der Berichtssatz-ID und dem Jahr-Monat erstellt (berichtssatz-ID ist die ganzzahlige Zahl nach dem Abschnitt "/#/" in der URL, und standardmäßig wird der aktuelle Jahrmonat am Ende der Berichtssatz-ID nach dem Schrägstrich angefügt). Die Berichtsdefinitionen werden im JSON-Format gespeichert und beim Abrufen aus dem Repositorydienst als Eingabe für den Datendienst verwendet. Der Datendienst generiert mdX(Multi-Dimension-Ausdrücke)-Abfragen basierend auf der Eingabe und führt dann diese -MDX-Abfragen für den Cube aus, um Daten für jeden Bericht abzurufen. 

### <a name="building-customized-reports"></a>Erstellen angepasster Berichte

CQD verfügt bereits über eine große Flexibilität beim Anpassen von Berichten, aber es kann Situationen geben, in denen Benutzer Daten über mehrere in CQD erstellte Berichte hinweg aggregieren möchten. Beispielsweise kann es nötig sein, einen Bericht zu erstellen, in dem die Prozentsatze schlechter Anrufe aller möglichen Kombinationen von kabelgebundenen Anrufen in einer Tabelle angezeigt werden (ein Ergebnis wie in der Abbildung):

![CQD Table](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

Mithilfe des vom CQD bereitgestellten Portals müsste ein Benutzer zu mehreren Berichten navigieren, um den %-Anteil der Anrufe schlechter Qualität für jeden Bericht zu extrahieren und zu aufzeichnen. Dies kann mühsam sein, wenn es viele Datenpunkte gibt, die gesammelt werden müssen. Die Daten-APIs bieten Benutzern eine programmgesteuerte Möglichkeit, dies durch Abrufen von Daten aus dem Datendienst (z. B. über AJAX-Aufrufe) zu erreichen. 

 **Beispiel 1: Beispiel für einen einfachen Bericht**

Nehmen wir zunächst ein einfaches Beispiel. Wenn wir den Audio Good Stream und den Audio Bad Stream vom Februar 2015 auf einer HTML-Seite wie der Abbildung anzeigen möchten:

![CQD-Beispielbericht](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

Was wir benötigen, ist das Senden eines Aufrufs an den Datendienst mit den richtigen Parametern und das Anzeigen der Abfrageergebnisse in einer HTML-Tabelle. Es folgt ein Beispiel für den JavaScript-Code:

```javascript        
$($.fn.freeFormReport = function (queries, urlApi, presentation) {
            var query = {
                Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                Filters: [{
                    DataModelName: '[StartDate].[Month]',
                    Value: '[2015-02-01T00:00:00]',
                    Operand: 0
                }],
                Measurements:
                    [{ DataModelName: '[Measures].[Audio Good Streams JPDR Count]' },
                     { DataModelName: '[Measures].[Audio Poor Streams JPDR Count]' },]
            };            

            $.ajax({
                url: 'http://localhost/QoEDataService/RunQuery',
                data: JSON.stringify(query),
                type: 'POST',
                async: true,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    //This is the jQuery syntax for document.GetElementById()
                    $('#AudioGoodStreamsJPDRCount').html(data.DataResult[0][1]);
                    $('#AudioPoorStreamsJPDRCount').html(data.DataResult[0][2]);
                }
                error: function (error) {
                    alert('Error getting data, check that the data service is running and that the URL is correct.');
           }
            });
        });
```

Dieses Beispiel kann in drei Schritte weiter destrukturiert werden:

1. Erstellen Sie die Abfrage (im Beispiel ist dies in der Variablen "query" definiert). Die Abfrage ist als ein JSON-Objekt definiert, das die folgenden Daten enthält:

   a. Null oder mehr Dimensionen. Jede Dimension wird durch einen DataModelName angegeben.

   b. Null oder mehr Filter. Jeder Filter verfügt über:

   - DataModelName (die Dimension, für die der Filter festgelegt wird).

   - Wert (der Wert, der vom Operanden verglichen wird).

   - Operand (Vergleichstyp, 0 bedeutet "Gleich").

     c. Mindestens ein Maß.

2. Senden Sie die Abfrage über einen AJAX-Aufruf an Den Datendienst. Die folgenden Anforderungsparameter müssen angegeben werden:

   a. url (die http://[ServerName]/QoEDataService/RunQuery sein sollte).

   b. (dies ist die Zeichenfolgendarstellung des JSON-Objekts, das in der Variablen "Query" definiert ist). Data Service gibt die Abfrageergebnisse als Parameter der Rückruffunktion zurück, um erfolglos zu sein.

   c. type (for QoEDataService, RunQuery only accepts 'POST' requests).

   d. async (ein Flag, das angibt, ob der AUFRUF VON AJAX synchron oder asynchron sein soll).

   e. contentType (sollte "application/json" sein).

   f. erfolg (Rückruffunktion für den Erfolgreichen Abschluss des AJAX-Aufrufs).

   g. fehler (Fehlerbehandlungsfunktion für fehler beim AJAX-Aufruf).

3. Legen Sie Daten in div-Elemente im HTML-Code ab (im Beispiel im Code erfolgt dies über den anonymen Funktionsaufruf, nachdem die ANFORDERUNG AJAX erfolgreich abgeschlossen wurde).

Umschließen des JavaScript-Codes in eine HTML-Seite, und die Seite zeigt einen Bericht wie den in der Abbildung gezeigt. Der vollständige HTML-Code lautet wie folgt:

```javascript
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
</head>
<body>
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <script>
        $($.fn.freeFormReport = function (queries, urlApi, presentation) {

            var query = {
                Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                Filters: [{
                    DataModelName: '[StartDate].[Month]',
                    Value: '[2015-02-01T00:00:00]',
                    Operand: 0
                }],
                Measurements:
                    [{ DataModelName: '[Measures].[Audio Good Streams JPDR Count]' },
                     { DataModelName: '[Measures].[Audio Poor Streams JPDR Count]' },]
            };            

            $.ajax({
                url: 'http://localhost/QoEDataService/RunQuery',
                data: JSON.stringify(query),
                type: 'POST',
                async: true,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    //This is the jQuery syntax for document.GetElementById()
                    $('#AudioGoodStreamsJPDRCount').html(data.DataResult[0][1]);
                    $('#AudioPoorStreamsJPDRCount').html(data.DataResult[0][2]);
                }
                error: function (error) {
                    alert('Error getting data, check that the data service is running and that the URL is correct.');
           }

            });
        });
    </script>
    <table border="1">
        <tr>
            <td></td>
            <td><div>Audio Good Streams JPDR Count</div></td>
            <td><div>Audio Poor Streams JPDR Count</div></td>
        </tr>
        <tr>
            <td>February</td>
            <td><div id="AudioGoodStreamsJPDRCount"></div></td>
            <td><div id="AudioPoorStreamsJPDRCount"></div></td>
        </tr>
    </table>
</body>
</html>
```

Bisher ist der Bericht noch sehr einfach. Der Benutzer kann weitere Messungen, Dimensionen oder Filter hinzufügen, um den Bericht anzupassen. Wenn Sie z. B. den Prozentsatz der Anrufe schlechter Qualität in AppSharing anzeigen möchten, muss eine neue Maßeinheit für AppSharing hinzugefügt werden. Wenn Sie alle TCP-Aufrufe v.s anzeigen möchten UDP-Aufrufe, eine neue Dimension für den Transporttyp sollte hinzugefügt werden. Wenn Sie die Anzahl der Anrufe schlechter Qualität in einem bestimmten Gebäude anzeigen möchten, sollte ein neuer Filter hinzugefügt werden, um die Anrufe an und aus diesem Gebäude auszuwählen.

 **Beispiel 2: Berichtsdefinitionsbeispiel**

Es kann schwierig für jemanden sein, herauszufinden, wie die vollständige Liste der Messungen/Dimensionen/Filter und die entsprechenden Werte beim Erstellen einer Abfrage geschrieben wird. In diesem Fall können Sie zum Portal wechseln, einen Bericht mithilfe des Berichtseditors erstellen und die JSON-Zeichenfolge der Berichtsdefinition anzeigen und dann die Definition in einen benutzerdefinierten Bericht kopieren. 

In diesem Beispiel erstellen wir eine Webseite wie die in der Abbildung gezeigte, auf der ein Benutzer die ID eines vorhandenen Berichtssatzes (oder Berichts) eingeben und die Definition des Berichtssatzes oder Berichts auf der Webseite anzeigen kann. Der Benutzer kann dann die JSON-Zeichenfolge jedes Berichts in Code ähnlich dem in Beispiel 1 einpassen und jeden benutzerdefinierten Bericht erstellen, den der Benutzer wünscht. 

![Beispiel für CQD](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

Um das Tool für die Berichtdefinitionsanzeige zu erstellen, müssen wir Aufrufe an den Repositorydienst senden, um die JSON-Zeichenfolgendarstellungen der Definitionen jedes berichtssatz abzurufen, den wir benötigen. Die Repository-API gibt eine Berichtssatzdefinition basierend auf einer bestimmten Berichtssatz-ID zurück. 

Ein schnelles Beispiel: Der Code enthält einen Block, der ein einfaches Beispiel zum Senden einer Abfrage an den Repositorydienst ist, um den Inhalt eines Repositoryelements basierend auf seinem Bezeichner zu erhalten. Und der nächste Codeabschnitt (processReportSetData-Methode) sendet AJAX-Aufrufe, um die Definition der einzelnen Berichte in diesem Berichtssatz zu erhalten. Da die ID im CQD-Webportal die ID eines Berichtssatz ist, gibt der AUFRUF VON AJAX ein Berichtssatzelement zurück. Weitere Details zur Repository-API und insbesondere zu GetItems finden Sie unter ["Elemente abrufen".](get-items.md) 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta http-equiv='cache-control' content='no-cache'>
    <meta http-equiv='expires' content='0'>
    <meta http-equiv='pragma' content='no-cache'>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta http-equiv="x-content-type-options" content="nosniff">
    <title>CQD Report definition viewer</title>
</head>
<body>    
    <div style="font-size:32pt">CQD Report definition viewer</div>
        <p>ReportSet Id: <input id="reportSetId" /></p>
        <button onclick='loadReportSet()'>Load</button>
        <div id="Report"></div>
    <!-- Third party Libraries -->
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <script>
        var urlRepositoryApi = 'http://localhost/QoERepositoryService/repository/item/';

        var loadReportSet = function ()
        {
            var reportSetId = document.getElementById('reportSetId').value;

            $.ajax({
                url: urlRepositoryApi + reportSetId,
                data: '',
                type: 'GET',
                async: false,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    var reportSetDiv = document.getElementById('Report');
                    reportSetDiv.innerHTML = '';
                    processReportSetData(reportSetDiv, data);
                },
                error: function (error) {
                    alert('Error getting Report, check that the qoe data service is running and url is correct.');
                }
            });
        };

        var processReportSetData = function (divReportSet, reportSetDef) {
             //show the report set definition like Title, Description, etc
            showReportSetDefinition(divReportSet, reportSetDef);

            //for each Report in the Reportset, get the Report definition from the Repository Service
            for (var i = 0; i < reportSetDef.subItemIds.length; i++)
            {
                //the reportId is in the subItemIds array.  This is not shown in the CQD UI at all
                var reportId = reportSetDef.subItemIds[i];

                var divReport = document.createElement('div');
                divReport.style.margin = '12px';                
                divReportSet.appendChild(divReport);

                //retrieve the report definition with the reportId
                $.ajax({
                    url: urlRepositoryApi + reportId,
                    data: '',
                    type: 'GET',
                    async: false,
                    contentType: 'application/json;charset=utf-8',
                    success: function (reportData) {
                        processReportData(divReport, reportData, reportId);
                    },
                    error: function (error) {
                        alert('Error getting Report ' + reportId.toString() + ', check that the qoe data service is running and url is correct.');
                    }
                });
            }
        };

        //helper function to render the ReportSet definition
        var showReportSetDefinition = function (divReportSet, reportSetDef) {
            var div = document.createElement('div');
            ReportSetDefinition = reportSetDef.content;
            txt = document.createTextNode(ReportSetDefinition);
            div.style.margin = '12px';
            div.appendChild(txt);
            divReportSet.appendChild(div);
        };

        //show the report definition
        var processReportData = function (divReport, reportData, itemId) {
            if (divReport != undefined &amp;&amp; reportData.content != undefined) {
                var Report = JSON.parse(reportData.content);

                var divReportId = document.createElement('div');
                var subItemId = reportData.subItemIds.length > 0 ? reportData.subItemIds[0].toString() : 'none';
                divReportId.innerHTML = 'ItemId: ' + itemId.toString() + ' (' + Report.Title + ') [subItemId:' + subItemId + ']';
                divReport.appendChild(divReportId);

                var divReportDef = document.createElement('div');
                txt = document.createTextNode(JSON.stringify(Report));
                divReportDef.style.margin = '12px';
                divReportDef.appendChild(txt);                            
                divReport.appendChild(divReportDef);
            }
        };
    </script>
</body>
</html>
```

Das obige Ergebnis ist eine Webseite wie die in der Abbildung (ohne berichtsdefinition beim ersten Besuch). Erhalten Sie die Berichtssatz-ID aus dem CQD-Portal (nach '/#/'-Anmeldung bei der CQD-Portal-URL (z. B. in der ersten Abbildung ist die Berichtssatz-ID 3024), und legen Sie diese Berichtssatz-ID in den Eingabeabschnitt dieser Webseite. Klicken Sie auf die Schaltfläche "Laden", und sehen Sie sich die vollständige Definition (Messungen, Dimensionen, Filterlisten) des Berichtssatz an.

Zusammenfassung: Um schnell die vollständige Definition eines Berichts-/Berichtssatzes zu erhalten. Das sind die Schritte:

1. Wechseln Sie zum Portal, und verwenden Sie den Abfrage-Editor, um einen Bericht anzupassen (klicken Sie über einem Bericht auf die Schaltfläche "Bearbeiten", um Messungen/Dimensionen/Filter zu bearbeiten, hinzuzufügen, zu entfernen und dann den Bericht zu speichern).

2. Get the report set ID from URL (the integer after '/#/' sign in URL).

3. Starten Sie diese in Beispiel 2 erstellte Berichtsdefinitionswebseite, geben Sie die Berichtssatz-ID ein, und rufen Sie die vollständige Definition eines Berichtssatz ab (zur Verwendung in Daten-API-Aufrufen).

   **Beispiel 3: Scorecardbeispiel**

Zeit für eine kompliziertere Aufgabe. Was passiert, wenn wir eine Webseite wie die Abbildung erstellen möchten? Wir müssen Beispiel 1 aktualisieren (mithilfe der in Beispiel 2 generierten Webseite, um die vollständige Definition eines Berichts abzurufen), damit wir größere Datenmenge verarbeiten können.

In diesem Fall müssen wir die Maß- und Dimensionsliste aktualisieren. Die Möglichkeit, herauszufinden, wie Eine Maßeinheit und/oder Dimension hinzugefügt/bearbeitet wird, besteht in der Befolgen der Anweisungen in Beispiel 2 und dem Abrufen der vollständigen Berichtsdefinition, einschließlich der vollständigen Maß- und Dimensionslisten. Schließen Sie die vollständige Berichtsdefinition in den Beispielcode ein. 

Im Folgenden finden Sie die detaillierten Schritte zum Öffnen der Scorecardseite in der Abbildung aus dem Beispiel in Beispiel 1:

1. Aktualisieren Sie Die Messungen in der Variablen "Abfrage" von  `[Measures].[Audio Good Streams JPDR Count]` und `[Measures].[Audio Poor Streams JPDR Count]` zu `[Measures].[AudioPoorJPDRPercentage]` . 

2. Aktualisieren Sie die Filter. Die JSON-Daten für Filter in Beispiel 1 haben einen Filter, der für die Dimension festgelegt  `[StartDate].[Month]` ist. Da Filters ein JSON-Array ist, können der Liste der Filter zusätzliche Dimensionen hinzugefügt werden. Um z. B. den Serverclient innerhalb von kabelgebundenen Anrufen für "currentMonth" zu erhalten, sollten die folgenden Filter vorhanden sein:

   ```javascript
   Filters: [
     { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
    {
        "DataModelName": "[Scenarios].[ScenarioPair]",
         "Caption": " Server-Inside-wired,Client-Inside-wired",
         "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
         "Operand": 0,
         "UnionGroup": ""
     },

     { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
   ],
   ```

   Hier ist die  `[Scenarios].[ScenarioPair]` Dimension auf "equal" `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` festgelegt. Dies  `[Scenario.][ScenarioPair]` ist eine spezielle Dimension, die zur Vereinfachung der Berichtserstellung erstellt wurde. Es verfügt über sechs Werte, die `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]` . Anstatt also eine Kombination von sechs Filtern zum Definieren eines Szenarios zu verwenden, müssen wir nur 1 Filter verwenden. In unserem Beispiel wird der Wert in das Szenario übersetzt, in dem: der erste ist Server, der zweite ist kein Server, der zweite ist innen, der zweite ist innen, der erste Verbindungstyp ist verkabelt, und der zweite Verbindungstyp ist verkabelt, was der genauen Definition von  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` "Server-Client-Inside Wired" entspricht.

3. Erstellen Sie einen Filtersatz pro Szenario. Jede Zeile in der Scorecard in der Abbildung stellt ein anderes Szenario dar, bei dem es sich um einen anderen Filter handelt (während die Dimensionen und Maßangaben gleich bleiben). 

4. Analysieren Sie die Ergebnisse der AJAX-Aufrufe, und platzieren Sie sie an der richtigen Position der Tabelle. Da es sich hierbei hauptsächlich um HTML- und JavaScript-Manipulation handelt, gehen wir hier nicht auf die Details ein. Stattdessen wird der Code in Anhang A bereitgestellt.

    > [!NOTE]
    >  Wenn CROSS-Origin Resource Sharing (CORS) aktiviert ist, können Fehler wie "Kein "Access-Control-Allow-Origin"-Header für die angeforderte Ressource vorhanden sein. Origin 'null' is therefore not allowed access". Um das Problem zu beheben, platzieren Sie die HTML-Datei unter dem Ordner, in dem das Portal installiert ist (standardmäßig sollte es `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)` sein. Greifen Sie dann über einen beliebigen Browser mit der URL auf den HTML-Code  `http://<servername>/cqd/<html_file_name>` zu. (Die Standard-URL für das lokale CQD-Dashboard ist  `http://<servername>/cqd.` ) 

### <a name="appendix-a"></a>Anhang A

HTML-Code für Beispiel 3 (Scorecardbeispiel):

```html
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <meta charset="utf-8" />
    <meta http-equiv='cache-control' content='no-cache'>
    <meta http-equiv='expires' content='0'>
    <meta http-equiv='pragma' content='no-cache'>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>Scoreboard Sample</title>

    <style>
        .row {
            margin-right: -15px;
            margin-left: -15px;
            display: table-row;
        }
        .col-md-3 {
            width: 25%;
            display: table-cell;
        }
        .col-md-2 {
            width: 16.66666667%;
            display: table-cell;
        }
        .col-md-1 {
            width: 8.33333333%;
            display: table-cell;
        }

    </style>
</head>
<body>    

    <!-- Third party Libraries -->
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <table id="ScoreCardTable" style="margin:100px">
        <tr>
            <td width="250px" style="text-align: center; font-size: 24px; font-family: 'Segoe UI'; font-weight: lighter; color: white; background-color: #505050">
                <div style="margin:10px">Scoreboard Sample</div>
            </td>
            <td width="1200px">
                <div style="margin:10px;background-color:#D9D9D9" >
                    <div class="row" id="Header" style="font-size:24px;font-family:'Segoe UI';font-weight:lighter;color:white;background-color:#505050">
                        <div class="col-md-3">Poor Call %</div>
                        <div class="col-md-1">Month1</div>
                        <div class="col-md-1">Month2</div>
                        <div class="col-md-1">Month3</div>
                        <div class="col-md-1">Month4</div>
                        <div class="col-md-1">Month5</div>
                        <div class="col-md-1">Month6</div>
                    </div>                    
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Wired</div></div>
                    <div class="row" id="SS"><div class="col-md-3">Server-Server</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWI"><div class="col-md-3">Server-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWO"><div class="col-md-3">Server-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WWI"><div class="col-md-3">Client-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WIWO"><div class="col-md-3">Client-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Wireless</div></div>
                    <div class="row" id="SWFI"><div class="col-md-3">Server-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWFO"><div class="col-md-3">Server-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WFIWFI"><div class="col-md-3">Client-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WFOWFO"><div class="col-md-3">Client-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Mobile/Broadband</div></div>
                    <div class="row" id="SMP"><div class="col-md-3">Server-MobilePhone</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SMBB"><div class="col-md-3">Server-MobileBroadBand</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Lync Web App</div></div>
                    <div class="row" id="SLWA"><div class="col-md-3">Server-Client (inside &amp; outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                </div>
            </td>
        </tr>
        <tr>
            <td><br /></td>
        </tr>
    </table>

    <script>

        $(function () {
            var month_names_short = ['NAM', 'Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'];
            var currentMonth = '2015-3';

            //update the header with the month names
            var row = document.getElementById('Header');
            var numMonthsToShow = 6;
            for (var m = numMonthsToShow-1; m >= 0; m--) {
                var dateSplit = currentMonth.split('-');
                var monthInt = parseInt(dateSplit[1]);
                var yearInt = parseInt(dateSplit[0]);
                monthInt = monthInt - m;
                if (monthInt < 1)
                {
                    monthInt += 12;
                    yearInt--;
                }
                row.children[numMonthsToShow-m].innerHTML = month_names_short[monthInt];
            }

            var queries = [
            {
                Label: "Server-Server",
                ID: "SS",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]'}],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Server-Inside-wired",
                          "Value": "[1]&amp;[1]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: ""}
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]'}],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                 }
            },
            {
                Label: "Server-Client (inside)",
                ID: "SWI",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Client-Inside-wired",
                          "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (outside)",
                ID: "SWO",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Client-Outside-wired",
                          "Value": "[1]&amp;[0]&amp;[1]&amp;[0]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                 }
            },
            {
                Label: "Client-Client (inside)",
                ID: "WWI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Client-Inside-wired,Client-Inside-wired",
                            "Value": "[0]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            }
            ,
            {
                Label: "Client-Client (outside)",
                ID: "WIWO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": "Client-Outside-Wired,Client-Outside-Wired",
                          "Value": "[0]&amp;[0]&amp;[0]&amp;[0]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (inside)",
                ID: "SWFI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Server-Inside-wired,Client-Inside-wifi",
                            "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wifi]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (outside)",
                ID: "SWFO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                         {
                             "DataModelName": "[Scenarios].[ScenarioPair]",
                             "Caption": " Server-Inside-wired,Client-Outside-wifi",
                             "Value": "[1]&amp;[0]&amp;[1]&amp;[0]&amp;[Wired]&amp;[Wifi]",
                             "Operand": 0,
                             "UnionGroup": ""
                         },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Client-Client (inside)",
                ID: "WFIWFI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Client-Inside-Wifi,Client-Inside-Wifi",
                            "Value": "[0]&amp;[0]&amp;[1]&amp;[1]&amp;[Wifi]&amp;[Wifi]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Client-Client (outside)",
                ID: "WFOWFO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": "Client-Outside-Wifi,Client-Outside-Wifi",
                          "Value": "[0]&amp;[0]&amp;[0]&amp;[0]&amp;[Wifi]&amp;[Wifi]",
                          "Operand": 0,
                          "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-MobilePhone",
                ID: "SMP",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second User Agent].[User Agent Type]","Caption": "AndroidLync | iPhoneLync | WPLync","Value": "[AndroidLync],[iPhoneLync],[WPLync]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-MobileBroadBand",
                ID: "SMBB",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[Second Network Connection Type].[Network Connection Detail]","Caption": "MobileBB","Value": "[MobileBB]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second Is Server].[Agent]","Caption": "Client ","Value": "[0]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 }                       
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-LWA",
                ID: "SLWA",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second User Agent].[User Agent Type]","Caption": "LWA","Value": "[LWA]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 }                       
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            }

            ];

            //get the overall corpnet data
            for (var i = 0; i < queries.length; i++) {
                $.ajax({

                    url: 'http://localhost/QoEDataService/RunQuery',
                    data: JSON.stringify(queries[i].Query),
                    type: 'POST',
                    async: false,
                    withCredentials: true,
                    contentType: 'application/json;charset=utf-8',
                    success: function (data) {

                        //find the table row corresponding to the name of this query
                        var row = document.getElementById(queries[i].ID);

                        //update the values for each month
                        for (var m = 0; m < data.DataResult.length; m++)
                        {
                            row.children[m + 1].innerHTML = data.DataResult[m][1].toFixed(2).toString();
                        }

                    },
                    error: function (error) {
                        var row = document.getElementById(queries[i].ID);
                        row.children[1].innerHTML = 'error';
                    }
                });
            }
        });
    </script>
</body>
</html>
```
