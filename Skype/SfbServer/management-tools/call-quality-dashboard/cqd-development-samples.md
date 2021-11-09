---
title: CQD-Entwicklungsbeispiele
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 8ca9bf7a-2d6f-48d5-a821-531009726525
description: 'Zusammenfassung: Sehen Sie sich ein Lernprogramm und Entwicklungsbeispiele für das Anrufqualitäts-Dashboard an. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 91e6f15f167000904626dc5a90d3766283396d7c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837507"
---
# <a name="cqd-development-samples"></a>CQD-Entwicklungsbeispiele

**Zusammenfassung:** Sehen Sie sich ein Lernprogramm und Entwicklungsbeispiele für das Anrufqualitäts-Dashboard an. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.

Dieser Artikel enthält ein Lernprogramm und Beispiele zur Entwicklung für das Anrufqualitäts-Dashboard (Call Quality Dashboard, CQD).

## <a name="call-quality-dashboard-cqd-development-samples"></a>Entwicklungsbeispiele für das Anrufqualitäts-Dashboard (Call Quality Dashboard, CQD)

Tutorial: Building Customized Report Presentation using the CQD Data Service and Repository Service API's.

### <a name="introduction-to-cqd"></a>Einführung in CQD

CQD bietet schnellen und einfachen Zugriff auf aggregierte Anrufqualitätsinformationen für lokale Skype for Business Server Bereitstellungen. CQD besteht aus drei Komponenten: der QoE-Archivdatenbank, dem Cube und dem Portal. Das Portal ist die Hauptpräsentationsschicht und kann weiter in die folgenden drei Komponenten unterteilt werden:

1. Data Service, der für authentifizierte Benutzer über die [Daten-API für das Anrufqualitäts-Dashboard (Call Quality Dashboard, CQD) in Skype for Business Server](data-api.md)zugänglich ist.

2. Repository service, which is accessible for authenticated users through the [Repository API for Call Quality Dashboard (CQD) in Skype for Business Server](repository-api.md).

3. Webportal, die HTML5-basierte Schnittstelle, die CQD-Benutzern angezeigt wird und mit der sie interagieren. Dies ist für authentifizierte Benutzer zugänglich.

Die im Webportal angezeigten Berichte sind in "Berichtssätze" gruppiert. Die Abbildung zeigt einen Bericht mit zwei Berichten. Jeder Bericht in diesem Dashboard unten zeigt Abfrageergebnisse zur Anzahl der guten Anrufe, Anrufe schlechter Qualität und Prozentsatz der Anrufe schlechter Qualität für mehrere Monate an, wobei verschiedene Filter angewendet werden. 

![CQD-Beispielbericht.](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

CQD wird nach der Call Quality Methodology (CQM) erstellt, sodass der Standardsatz von Berichten auf den von CQM eingeführten Untersuchungsfluss abgestimmt ist. Benutzer haben auch die Flexibilität, benutzerdefinierte Berichte entsprechend ihren Anforderungen zu bearbeiten oder zu erstellen. Da es jedoch mehrere Möglichkeiten gibt, die Daten zu visualisieren, erfüllt die vom CQD bereitgestellte Visualisierung möglicherweise nicht vollständig die Anforderungen jedes Benutzers. In solchen Situationen kann ein Benutzer die Daten-APIs und Repository-APIs nutzen, um benutzerdefinierte Berichtsseiten zu erstellen. In diesem Lernprogramm werden wir eine Reihe von Beispielen durchgehen.

### <a name="how-the-dashboard-consumes-the-data-service"></a>Nutzung des Datendiensts durch das Dashboard

Beim Navigieren zur CQD-Homepage (z. B. http://localhost/cqd) werden der Berichtssatz und die entsprechenden Berichte für einen authentifizierten und autorisierten Benutzer aus dem Repositorydienst abgerufen. Eine vollständige URL wird aus der Berichtssatz-ID und dem Jahr-Monat erstellt (Berichtssatz-ID ist die ganzzahlige Zahl nach dem Abschnitt "/#/" in der URL, und standardmäßig wird der aktuelle Jahresmonat am Ende der Berichtssatz-ID nach dem Schrägstrich angefügt). Die Berichtsdefinitionen werden im JSON-Format gespeichert und beim Abrufen aus dem Repositorydienst als Eingabe für den Datendienst verwendet. Der Datendienst generiert MDX-Abfragen (Multi-Dimension Expressions) basierend auf der Eingabe und führt dann diese MDX-Abfragen für den Cube aus, um Daten für jeden Bericht abzurufen. 

### <a name="building-customized-reports"></a>Erstellen benutzerdefinierter Berichte

CQD verfügt bereits über eine große Flexibilität beim Anpassen von Berichten, aber es kann Situationen geben, in denen Benutzer Daten über mehrere Berichte hinweg aggregieren möchten, die in CQD erstellt wurden. Beispielsweise kann es erforderlich sein, einen Bericht zu erstellen, der den Prozentsatz der Anrufe schlechter Qualität aller möglichen Kombinationen von kabelgebundenen Anrufen in einer Tabelle anzeigt (ein Ergebnis wie die Abbildung):

![CQD-Tabelle.](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

Mithilfe des von CQD bereitgestellten Portals müsste ein Benutzer zu mehreren Berichten navigieren, um den Prozentsatz der Anrufe schlechter Qualität für jeden zu extrahieren und zu notieren. Dies kann mühsam sein, wenn viele Datenpunkte gesammelt werden müssen. Die Daten-APIs bieten Benutzern eine programmgesteuerte Möglichkeit, dies durch Abrufen von Daten aus dem Datendienst (z. B. über AJAX-Aufrufe) zu erreichen. 

 **Beispiel 1: Beispiel für einen einfachen Bericht**

Nehmen wir zunächst ein einfaches Beispiel. Wenn wir die Anzahl der Audio Good Stream- und Audio Bad-Streams von Februar 2015 auf einer HTML-Seite wie der Abbildung anzeigen möchten:

![CQD-Beispielbericht.](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

Wir müssen einen Aufruf an den Datendienst mit den richtigen Parametern senden und die Abfrageergebnisse in einer HTML-Tabelle anzeigen. Es folgt ein Beispiel für den JavaScript-Code:

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

Dieses Beispiel kann in drei Schritte unterteilt werden:

1. Erstellen Sie die Abfrage (im Beispiel ist dies in der Variablen "Abfrage" definiert). Die Abfrage ist als JSON-Objekt definiert, das die folgenden Daten enthält:

   a. Null oder mehr Dimensionen. Jede Dimension wird durch einen DataModelName angegeben.

   b. Null oder mehr Filter. Jeder Filter hat Folgendes:

   - DataModelName (die Dimension, für die der Filter festgelegt wird).

   - Wert (der Wert, der vom Operanden verglichen wird).

   - Operand (Vergleichstyp, 0 bedeutet "Gleich").

     c. Mindestens eine Maßeinheit.

2. Senden Sie die Abfrage per AJAX-Aufruf an den Datendienst. Die folgenden Anforderungsparameter müssen bereitgestellt werden:

   a. url (which should be http://[ServerName]/QoEDataService/RunQuery).

   b. Daten (dies ist die Zeichenfolgendarstellung des JSON-Objekts, das in der Variablen "Abfrage" definiert ist). Der Datendienst gibt die Abfrageergebnisse als Parameter der Rückruffunktion für den Erfolg zurück.

   c. typ (für QoEDataService akzeptiert RunQuery nur 'POST'-Anforderungen).

   d. asynchron (ein Flag, das angibt, ob der AJAX-Aufruf synchron oder asynchron sein soll).

   e. contentType (sollte "application/json" sein).

   f. erfolgreich (Rückruffunktion für den Zeitpunkt, an dem der AJAX-Aufruf erfolgreich abgeschlossen wurde).

   g. error (Fehlerbehandlungsfunktion für den Zeitpunkt, an dem der AJAX-Aufruf fehlschlägt).

3. Fügen Sie Daten in div-Elemente in den HTML-Code ein (im Beispiel im Code erfolgt dies über den anonymen Funktionsaufruf, nachdem die AJAX-Anforderung erfolgreich abgeschlossen wurde).

Wenn Sie den JavaScript-Code in eine HTML-Seite einschließen, wird auf der Seite ein Bericht wie in der Abbildung angezeigt. Der vollständige HTML-Code lautet wie folgt:

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

Bisher ist der Bericht noch sehr einfach. Der Benutzer kann weitere Messungen, Dimensionen oder Filter hinzufügen, um den Bericht anzupassen. Wenn Sie beispielsweise den Prozentsatz der AppSharing-Anrufe mit schlechter Qualität anzeigen möchten, muss eine neue Maßeinheit für AppSharing hinzugefügt werden. Wenn Sie alle TCP-Aufrufe v.s anzeigen möchten. UDP-Anrufe, eine neue Dimension hinsichtlich transporttyp hinzugefügt werden sollte. Wenn Sie die Anzahl schlechter Anrufe in einem bestimmten Gebäude anzeigen möchten, sollte ein neuer Filter hinzugefügt werden, um die Anrufe zu und aus diesem Gebäude auszuwählen.

 **Beispiel 2: Beispiel für eine Berichtsdefinition**

Es kann für jemanden schwierig sein, herauszufinden, wie die vollständige Liste von Maßen/Dimensionen/Filtern und deren entsprechenden Werten beim Erstellen einer Abfrage geschrieben wird. In diesem Fall können Sie zum Portal wechseln, einen Bericht mithilfe des Berichts-Editors erstellen, die JSON-Zeichenfolge der Berichtsdefinition anzeigen und dann die Definition in einen benutzerdefinierten Bericht kopieren. 

In diesem Beispiel erstellen wir eine Webseite wie in der Abbildung, auf der ein Benutzer die ID eines vorhandenen Berichtssatzes (oder Berichts) eingeben und die Definition des Berichtssatzes oder Berichts auf der Webseite anzeigen kann. Der Benutzer kann dann die JSON-Zeichenfolge jedes Berichts in Code ähnlich dem in Beispiel 1 gezeigten einfügen und alle vom Benutzer gewünschten benutzerdefinierten Berichte erstellen. 

![CQD-Beispiel.](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

Um das Tool zum Anzeigen der Berichtsdefinition zu erstellen, müssen wir Aufrufe an den Repositorydienst senden, um die JSON-Zeichenfolgendarstellungen der Definitionen jedes gewünschten Berichtssatzes abzurufen. Die Repository-API gibt die Berichtssatzdefinition basierend auf einer bestimmten Berichtssatz-ID zurück. 

Ein kurzes Beispiel ist wie folgt: Der Code enthält einen Block, der ein einfaches Beispiel zum Senden einer Abfrage an den Repository-Dienst ist, um den Inhalt eines Repositoryelements basierend auf seinem Bezeichner abzurufen. Und der nächste Codeteil (processReportSetData-Methode) sendet AJAX-Aufrufe, um die Definition der einzelnen Berichte innerhalb dieses Berichtssatzes abzurufen. Da die ID im CQD-Webportal die ID eines Berichtssatzes ist, gibt der AJAX-Aufruf ein Berichtssatzelement zurück. Weitere Details zur Repository-API und insbesondere zu GetItems finden Sie unter ["Elemente abrufen".](get-items.md) 

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

Das obige Ergebnis führt zu einer Webseite wie der in der Abbildung (ohne die Berichtsdefinition beim ersten Besuch). Abrufen der Berichtssatz-ID aus dem CQD-Portal (nach der "/#/"-Anmeldung in der CQD-Portal-URL (z. B. in der ersten Abbildung lautet die Berichtssatz-ID 3024), und fügen Sie diese Berichtssatz-ID in den Eingabeabschnitt dieser Webseite ein. Drücken Sie die Schaltfläche "Laden", und sehen Sie die vollständige Definition (Maßangaben, Dimensionen, Filterlisten) des Berichtssatzes.

Zusammengefasst, um schnell die vollständige Definition eines Berichts/Berichtssatzes zu erhalten. Das sind die Schritte:

1. Wechseln Sie zum Portal, und verwenden Sie den Abfrage-Editor, um einen Bericht anzupassen (klicken Sie auf die Schaltfläche "Bearbeiten" oberhalb eines Berichts, um Maßangaben/Dimensionen/Filter zu bearbeiten, hinzuzufügen, zu entfernen und dann den Bericht zu speichern).

2. Rufen Sie die Berichtssatz-ID von der URL ab (die ganze Zahl nach der Anmelde-URL von "/#/").

3. Starten Sie diese in Beispiel 2 erstellte Berichtsdefinitionswebseite, und geben Sie die Berichtssatz-ID ein, und rufen Sie die vollständige Definition eines Berichtssatzes ab (zur Verwendung in Daten-API-Aufrufen).

   **Beispiel 3: Scorecardbeispiel**

Zeit für eine kompliziertere Aufgabe. Was geschieht, wenn wir eine Webseite wie die Abbildung erstellen möchten? Wir müssen Beispiel 1 aktualisieren (mithilfe der in Beispiel 2 generierten Webseite, um die vollständige Definition eines beliebigen Berichts abzurufen), damit wir größere Datenmengen verarbeiten können.

In diesem Fall müssen wir die Mess- und Dimensionsliste aktualisieren. Sie können herausfinden, wie Sie eine Maßeinheit und/oder Dimension hinzufügen/bearbeiten, wenn Sie den Anweisungen in Beispiel 2 folgen und die vollständige Berichtsdefinition einschließlich der vollständigen Mess- und Dimensionslisten abrufen. Schließen Sie die vollständige Berichtsdefinition in den Beispielcode an. 

Hier sind die detaillierten Schritte, um zur Scorecardseite in der Abbildung aus dem Beispiel in Beispiel 1 zu gelangen:

1. Aktualisieren Sie Die Messungen in der Variablen "Abfrage" von  `[Measures].[Audio Good Streams JPDR Count]` und `[Measures].[Audio Poor Streams JPDR Count]` nach `[Measures].[AudioPoorJPDRPercentage]` . 

2. Aktualisieren Sie die Filter. Die JSON-Daten für Filter in Beispiel 1 haben einen Filter, der für die Dimension festgelegt  `[StartDate].[Month]` ist. Da Filter ein JSON-Array sind, können der Liste der Filter zusätzliche Dimensionen hinzugefügt werden. Um z. B. den Server-Client innerhalb von kabelgebundenen Aufrufen für "currentMonth" abzurufen, sollten die folgenden Filter vorhanden sein:

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

   Hier wird die Dimension  `[Scenarios].[ScenarioPair]` auf "gleich" `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` festgelegt. Dies  `[Scenario.][ScenarioPair]` ist eine spezielle Dimension, die erstellt wurde, um die Erstellung von Berichten zu vereinfachen. Es hat sechs Werte, die entsprechen `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]` . Anstatt also eine Kombination aus 6 Filtern zum Definieren eines Szenarios zu verwenden, müssen wir nur 1 Filter verwenden. In unserem Beispiel wird der Wert  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` in das Szenario übersetzt, in dem: der erste Server, der zweite nicht der Server, der erste ist innerhalb, der erste Verbindungstyp verkabelt und der zweite Verbindungstyp verkabelt ist, was die genaue Definition von "Server-Client-Inside Wired" ist.

3. Erstellen Sie einen Filtersatz pro Szenario. Jede Zeile in der Scorecard in der Abbildung stellt ein anderes Szenario dar, bei dem es sich um einen anderen Filter handelt (während die Abmessungen und Maßangaben gleich bleiben). 

4. Analysieren Sie die Ergebnisse der AJAX-Aufrufe, und platzieren Sie sie an der richtigen Position der Tabelle. Da dies hauptsächlich HTML- und JavaScript-Manipulation ist, werden wir hier nicht auf details eingehen. Stattdessen wird der Code in Anhang A bereitgestellt.

    > [!NOTE]
    >  Wenn cross-origin Resource Sharing (CORS) aktiviert ist, können Benutzer Fehler wie "Kein "Access-Control-Allow-Origin"-Header ist in der angeforderten Ressource vorhanden sein. Origin 'null' is therefore not allowed access". Um das Problem zu beheben, platzieren Sie die HTML-Datei unter dem Ordner, in dem das Portal installiert ist (standardmäßig sollte sie `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)` . Greifen Sie dann über einen beliebigen Browser mit der URL auf den HTML-Code  `http://<servername>/cqd/<html_file_name>` zu. (Die Standard-URL für das lokale CQD-Dashboard lautet  `http://<servername>/cqd.` ) 

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
