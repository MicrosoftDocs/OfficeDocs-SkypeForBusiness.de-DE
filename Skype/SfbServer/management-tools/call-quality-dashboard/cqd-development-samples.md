---
title: CQD-Entwicklungsbeispiele
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8ca9bf7a-2d6f-48d5-a821-531009726525
description: 'Zusammenfassung: Überprüfen Sie ein Lernprogramm und Entwicklungsbeispiele für das Anrufqualitäts-Dashboard. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.'
ms.openlocfilehash: 6bd6031e1d7fc94ed463c53efb068fd1e2e51378
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375323"
---
# <a name="cqd-development-samples"></a><span data-ttu-id="25c0c-104">CQD-Entwicklungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="25c0c-104">CQD Development Samples</span></span>

<span data-ttu-id="25c0c-p102">**Zusammenfassung:** Überprüfen Sie ein Lernprogramm und Entwicklungsbeispiele für das Anrufqualitäts-Dashboard. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="25c0c-p102">**Summary:** Review a tutorial and development samples for Call Quality Dashboard. Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>

<span data-ttu-id="25c0c-107">Dieser Artikel enthält ein Lernprogramm und Beispiele für die Entwicklung des Anrufqualitäts-Dashboards (Call Quality Dashboard, CQD).</span><span class="sxs-lookup"><span data-stu-id="25c0c-107">This article provides a tutorial and samples on development for Call Quality Dashboard (CQD).</span></span>

## <a name="call-quality-dashboard-cqd-development-samples"></a><span data-ttu-id="25c0c-108">Beispiele für die Entwicklung des Anrufqualitäts-Dashboards (CQD)</span><span class="sxs-lookup"><span data-stu-id="25c0c-108">Call Quality Dashboard (CQD) Development Samples</span></span>

<span data-ttu-id="25c0c-109">Lernprogramm: Erstellen benutzerdefinierter Berichte mit dem CQD-Datendienst und Repository Service-APIs.</span><span class="sxs-lookup"><span data-stu-id="25c0c-109">Tutorial: Building Customized Report Presentation using the CQD Data Service and Repository Service API's.</span></span>

### <a name="introduction-to-cqd"></a><span data-ttu-id="25c0c-110">Einführung in CQD</span><span class="sxs-lookup"><span data-stu-id="25c0c-110">Introduction to CQD</span></span>

<span data-ttu-id="25c0c-p103">Das Anrufqualitäts-Dashboard (Call Quality Dashboard, CQD) bietet schnellen und einfachen Zugriff auf die zusammengefassten Daten zur Anrufqualität für lokale Skype for Business Server-Bereitstellungen. Das CQD besteht aus drei Komponenten: der QoE-Archivdatenbank, dem Cube und dem Portal. Das Portal ist die Hauptpräsentationsebene und ist ebenfalls in drei Komponenten unterteilt:</span><span class="sxs-lookup"><span data-stu-id="25c0c-p103">CQD offers quick and easy access to aggregated call quality information for on-premise Skype for Business Server deployments. CQD consists of three components: the QoE Archive database, the Cube, and the Portal. The Portal is the main presentation layer and can be further divided into the following three components:</span></span>

1. <span data-ttu-id="25c0c-114">Data-Dienst, die für authentifizierte Benutzer über [Daten-API für aufrufen Quality Dashboard (CQD) in Skype für Business Server 2015](data-api.md)zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="25c0c-114">Data Service, which is accessible for authenticated users through the [Data API for Call Quality Dashboard (CQD) in Skype for Business Server 2015](data-api.md).</span></span>

2. <span data-ttu-id="25c0c-115">Repository-Dienst, der für authentifizierte Benutzer über die [Repository-API für aufrufen Quality Dashboard (CQD) in Skype für Business Server 2015](repository-api.md)zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="25c0c-115">Repository Service, which is accessible for authenticated users through the [Repository API for Call Quality Dashboard (CQD) in Skype for Business Server 2015](repository-api.md).</span></span>

3. <span data-ttu-id="25c0c-p104">das Webportal der HTML5-basierte Schnittstelle, die CQD-Benutzer sehen und mit der sie interagieren können. Auch sie ist für authentifizierte Benutzer zugänglich.</span><span class="sxs-lookup"><span data-stu-id="25c0c-p104">Web portal, which is the HTML5 based interface that CQD users see and interact with. This is accessible for authenticated users.</span></span>

<span data-ttu-id="25c0c-118">Die Berichte auf dem Webportal angezeigt werden in "Bericht Sätze" gruppiert.</span><span class="sxs-lookup"><span data-stu-id="25c0c-118">The reports shown on the web portal are grouped into "report sets".</span></span> <span data-ttu-id="25c0c-119">Die Abbildung zeigt einen Bericht mit zwei Berichten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="25c0c-119">The figure shows a report set with two reports.</span></span> <span data-ttu-id="25c0c-120">Jeden Bericht im Dashboard unten zeigt Abfrageergebnisse Anzahl gute Anrufe, schlechter Anrufe und Prozentsatz der Anrufe schlechter Qualität für mehrere Monate bei verschiedenen Filter angewendet.</span><span class="sxs-lookup"><span data-stu-id="25c0c-120">Each report in this dashboard below shows query results on number of good calls, poor calls and poor call percentage for several months, with various filters applied.</span></span> 

![CQD-Beispielbericht](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

<span data-ttu-id="25c0c-p106">Das Anrufqualitäts-Dashboard wird entsprechend der Call Quality Methodology (CQM) erstellt, sodass der standardmäßige Berichtesatz auf den Recherche-Workflow ausgelegt ist, der in CQM festgelegt wurde. Benutzer können aber die Berichte nach ihren eigenen Vorstellungen flexibel bearbeiten oder neu erstellen. Aufgrund der Vielzahl der Darstellungsmöglichkeiten erfüllen die im Dashboard bereitgestellten Visualisierungsvorgaben eventuell nicht die Bedürfnisse jedes Benutzers. In diesem Fall kann ein Benutzer die Daten- und Repository-APIs nutzen, um eigene Berichtseiten zu definieren. In diesem Lernprogramm stellen wir einige Beispiele dafür vor.</span><span class="sxs-lookup"><span data-stu-id="25c0c-p106">CQD is created following the Call Quality Methodology (CQM), so the default set of reports is designed to align with the investigation flow introduced by CQM. Users also have the flexibility to edit or create custom reports to meet their needs. However, since there are multiple ways to visualize the data, the visualization provided by CQD may not fully address the needs of every user. In such situations, a user can leverage the Data APIs and Repository APIs to create custom report pages. We will go through a series of examples in this tutorial.</span></span>

### <a name="how-the-dashboard-consumes-the-data-service"></a><span data-ttu-id="25c0c-127">Wie das Dashboard den Datendienst nutzt</span><span class="sxs-lookup"><span data-stu-id="25c0c-127">How the dashboard consumes the data service</span></span>

<span data-ttu-id="25c0c-128">Beim Navigieren zur Homepage CQD (z. B. http://localhost/cqd), legen Sie der Bericht und entsprechende Berichte für einen authentifizierten und autorisierten Benutzer aus dem Repository-Dienst abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="25c0c-128">When navigating to the CQD homepage (e.g. http://localhost/cqd), the report set and corresponding reports for an authenticated and authorized user will be retrieved from the Repository Service.</span></span> <span data-ttu-id="25c0c-129">Eine vollständige URL wird aus dem Bericht-Satz-ID und das Jahr-Monat konstruiert (Bericht Satz-ID ist die ganzzahlige Anzahl nach Abschnitt / #/ in URL und standardmäßig der aktuelle Jahr-Monat am Ende der Bericht Satz-ID nach dem Schrägstrich angefügt ist).</span><span class="sxs-lookup"><span data-stu-id="25c0c-129">A full URL will be constructed from the report-set ID and the year-month (report-set ID is the integer number after '/#/' section in URL, and by default the current year-month is appended at the end of the report-set ID after the slash).</span></span> <span data-ttu-id="25c0c-130">Die Berichtsdefinitionen werden im JSON-Format gespeichert und beim Abrufen aus dem Repository-Dienst werden anschließend als Eingabe für den Datendienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="25c0c-130">The report definitions are stored in JSON format and when retrieved from the Repository Service, will then be used as input to the Data Service.</span></span> <span data-ttu-id="25c0c-131">Der Dienst Daten generiert mehrdimensionale Ausdrücken (MDX)-Abfragen auf der Grundlage der Eingabe und führen Sie diese MDX-Abfragen für den Cube zum Abrufen von Daten für jeden Bericht.</span><span class="sxs-lookup"><span data-stu-id="25c0c-131">The Data Service generates Multi-Dimension expressions (MDX) queries based on the input and then run these MDX queries against the Cube to retrieve data for each report.</span></span> 

### <a name="building-customized-reports"></a><span data-ttu-id="25c0c-132">Erstellen benutzerdefinierter Berichte</span><span class="sxs-lookup"><span data-stu-id="25c0c-132">Building customized reports</span></span>

<span data-ttu-id="25c0c-p108">Das Anrufqualitäts-Dashboard bietet bereits ein hohes Maß an Flexibilität zum Anpassen von Berichten, aber es kann Situationen geben, in denen Benutzer Daten aus mehreren in CQD erstellten Berichten zusammenführen möchten. So könnte beispielsweise die Notwendigkeit bestehen, einen Bericht zu erstellen, in dem aus allen möglichen Kombinationen von kabelgebundenen Anrufen der Prozentsatz der Anrufe schlechter Qualität in einer Tabelle dargestellt werden (mit einem Ergebnis ähnlich wie in der Abbildung):</span><span class="sxs-lookup"><span data-stu-id="25c0c-p108">CQD already has a lot of flexibility in customizing reports, but there could be situations where users may want to aggregate data across multiple reports created in CQD. For example, there could be a need to create a report that shows the poor call percentages of all possible combinations of wired calls in a table (a result like the figure):</span></span>

![CQD-Tabelle](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

<span data-ttu-id="25c0c-p109">Über das vom Anrufqualitäts-Dashboard bereitgestellte Portal müsste der Benutzer durch mehrere Berichte navigieren, um für jeden einzelnen den Prozentsatz von Anrufen schlechter Qualität zu ermitteln, was sehr umständlich sein kann, wenn man zahlreiche Datenpunkte sammeln möchte. Durch den Abruf der Daten mittels eines Datendiensts (z. B. per AJAX-Abruf) bieten die Daten-APIs dem Benutzer eine automatisierte Form der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="25c0c-p109">Using the Portal provided by CQD, a user would have to navigate to multiple reports to extract and record the poor call % for each one, which can be laborious if there are many data points that need to be collected. The Data APIs provide users with a programmatic way to accomplish this, by retrieving data from the Data Service (e.g. via AJAX calls).</span></span> 

 <span data-ttu-id="25c0c-138">**Beispiel 1: Beispiel für einen einfachen Bericht**</span><span class="sxs-lookup"><span data-stu-id="25c0c-138">**Example 1: Simple report sample**</span></span>

<span data-ttu-id="25c0c-p110">Lassen Sie uns zuerst ein einfaches Beispiel anschauen. Angenommen, wir möchten die Zahl an gut gestreamten und schlecht gestreamten Audio-Inhalten im Februar 2015 auf einer HTML-Seite ähnlich der folgenden anzeigen:</span><span class="sxs-lookup"><span data-stu-id="25c0c-p110">Let us take a simple example first. If we want to show the Audio Good Stream and the Audio Bad stream count of February 2015 on an HTML page like the figure:</span></span>

![CQD-Beispielbericht](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

<span data-ttu-id="25c0c-p111">Dazu müssen wir eine Abfrage mit den entsprechenden Parametern an den Datendienst senden und die Ergebnisse in einer HTML-Tabelle darstellen. Im Folgenden sehen Sie ein Beispiel für den JavaScript-Code:</span><span class="sxs-lookup"><span data-stu-id="25c0c-p111">What we need is to send a call to the Data Service with the proper parameters, and show the query results in an HTML table. The following is a sample of the JavaScript code:</span></span>

```        
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

<span data-ttu-id="25c0c-144">Dieses Beispiel lässt sich weiter in drei Schritte unterteilen:</span><span class="sxs-lookup"><span data-stu-id="25c0c-144">This example can be further deconstructed into three steps:</span></span>

1. <span data-ttu-id="25c0c-145">Erstellen Sie die Abfrage (in dem Beispiel, das dies in der Variablen "Abfrage" definiert ist).</span><span class="sxs-lookup"><span data-stu-id="25c0c-145">Construct the query (in the example this is defined in the variable 'query').</span></span> <span data-ttu-id="25c0c-146">Die Abfrage ist als JSON-Objekt definiert, das die folgenden Daten enthält:</span><span class="sxs-lookup"><span data-stu-id="25c0c-146">The query is defined as a JSON object, which includes the following data:</span></span>

   <span data-ttu-id="25c0c-147">a.</span><span class="sxs-lookup"><span data-stu-id="25c0c-147">a.</span></span> <span data-ttu-id="25c0c-148">Null oder mehr Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="25c0c-148">Zero or more dimensions.</span></span> <span data-ttu-id="25c0c-149">Jede Dimension wird durch einen DataModelName angezeigt.</span><span class="sxs-lookup"><span data-stu-id="25c0c-149">Each dimension is indicated by a DataModelName.</span></span>

   <span data-ttu-id="25c0c-150">b.</span><span class="sxs-lookup"><span data-stu-id="25c0c-150">b.</span></span> <span data-ttu-id="25c0c-151">Null oder mehr Filter.</span><span class="sxs-lookup"><span data-stu-id="25c0c-151">Zero or more filters.</span></span> <span data-ttu-id="25c0c-152">Jeder Filter verfügt über folgende Elemente:</span><span class="sxs-lookup"><span data-stu-id="25c0c-152">Each filter has:</span></span>

   - <span data-ttu-id="25c0c-153">DataModelName (die Dimension, für die der Filter gesetzt wird).</span><span class="sxs-lookup"><span data-stu-id="25c0c-153">DataModelName (the dimension that will have the filter set).</span></span>

   - <span data-ttu-id="25c0c-154">Wert (der Wert, der vom Operanden verglichen wird).</span><span class="sxs-lookup"><span data-stu-id="25c0c-154">Value (the value that will be compared by the operand).</span></span>

   - <span data-ttu-id="25c0c-155">Operand (Vergleichstyp, 0 bedeutet, dass "Gleich").</span><span class="sxs-lookup"><span data-stu-id="25c0c-155">Operand (comparison type, 0 means "Equal").</span></span>

     <span data-ttu-id="25c0c-156">c.</span><span class="sxs-lookup"><span data-stu-id="25c0c-156">c.</span></span> <span data-ttu-id="25c0c-157">Ein oder mehrere Messwerte.</span><span class="sxs-lookup"><span data-stu-id="25c0c-157">One or more measurements.</span></span>

2. <span data-ttu-id="25c0c-p116">Senden Sie die Anfrage per AJAX-Abruf an den Datendienst. Folgende Abfrageparameter müssen angegeben sein:</span><span class="sxs-lookup"><span data-stu-id="25c0c-p116">Send the query to Data Service via AJAX call. The following request parameters need to be provided:</span></span>

   <span data-ttu-id="25c0c-160">a.</span><span class="sxs-lookup"><span data-stu-id="25c0c-160">a.</span></span> <span data-ttu-id="25c0c-161">URL (http://[ServerName]/QoEDataService/RunQuery).</span><span class="sxs-lookup"><span data-stu-id="25c0c-161">url (which should be http://[ServerName]/QoEDataService/RunQuery).</span></span>

   <span data-ttu-id="25c0c-162">b.</span><span class="sxs-lookup"><span data-stu-id="25c0c-162">b.</span></span> <span data-ttu-id="25c0c-163">Daten (Dies ist die Zeichenfolgendarstellung der JSON-Objekt definiert, in der Variablen "Abfrage").</span><span class="sxs-lookup"><span data-stu-id="25c0c-163">data (this is the string representation of the JSON object defined in the 'query' variable).</span></span> <span data-ttu-id="25c0c-164">Der Datendienst gibt die Abfrageergebnisse als Parameter der Rückruffunktion „Erfolg“ zurück.</span><span class="sxs-lookup"><span data-stu-id="25c0c-164">Data Service will return the query results as a parameter of the call back function for success.</span></span>

   <span data-ttu-id="25c0c-165">c.</span><span class="sxs-lookup"><span data-stu-id="25c0c-165">c.</span></span> <span data-ttu-id="25c0c-166">Geben Sie (für QoEDataService, RunQuery akzeptiert nur ' veröffentlichen' Anfragen).</span><span class="sxs-lookup"><span data-stu-id="25c0c-166">type (for QoEDataService, RunQuery only accepts 'POST' requests).</span></span>

   <span data-ttu-id="25c0c-167">d.</span><span class="sxs-lookup"><span data-stu-id="25c0c-167">d.</span></span> <span data-ttu-id="25c0c-168">Asynchron (ein Flag, das anzeigt, ob der AJAX-Abruf synchron oder asynchron ablaufen soll).</span><span class="sxs-lookup"><span data-stu-id="25c0c-168">async (a flag indicating whether the AJAX call should be synchronous or asynchronous).</span></span>

   <span data-ttu-id="25c0c-169">e.</span><span class="sxs-lookup"><span data-stu-id="25c0c-169">e.</span></span> <span data-ttu-id="25c0c-170">ContentType (sollte "Application/Json" sein).</span><span class="sxs-lookup"><span data-stu-id="25c0c-170">contentType (should be "application/json").</span></span>

   <span data-ttu-id="25c0c-171">f.</span><span class="sxs-lookup"><span data-stu-id="25c0c-171">f.</span></span> <span data-ttu-id="25c0c-172">Erfolg (Rückruffunktion, wenn der Ajax-Abruf erfolgreich abgeschlossen wurde).</span><span class="sxs-lookup"><span data-stu-id="25c0c-172">success (call-back function for when the AJAX call finishes successfully).</span></span>

   <span data-ttu-id="25c0c-173">g.</span><span class="sxs-lookup"><span data-stu-id="25c0c-173">g.</span></span> <span data-ttu-id="25c0c-174">Fehler (Fehlerbehandlungsfunktion, wenn der AJAX-Abruf fehlschlägt).</span><span class="sxs-lookup"><span data-stu-id="25c0c-174">error (error handling function for when AJAX call fails).</span></span>

3. <span data-ttu-id="25c0c-175">Dateneingabe für die einzelnen Elemente in der HTML (im vorliegenden Beispiel für den Code geschieht dies über einen anonymen Funktionsabruf, nachdem die AJAX-Abfrage erfolgreich abgeschlossen wurde).</span><span class="sxs-lookup"><span data-stu-id="25c0c-175">Put data into div elements in the HTML (in the example in the code, this is done via the anonymous function call after the AJAX request is completed successfully).</span></span>

<span data-ttu-id="25c0c-p124">Nach Einfügen des Java Script-Codes in eine HTML-Seite erhält man eine ähnliche Berichtseite wie in der Abbildung. Die vollständige HTML sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="25c0c-p124">Enclosing the JavaScript code into an HTML page, and the page will show a report like the one shown in the figure. The full html is as follows:</span></span>

```
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

<span data-ttu-id="25c0c-p125">Bis hierher war der Bericht noch sehr einfach. Der Benutzer kann aber weitere Messwerte, Dimensionen oder Filter hinzufügen, um den Bericht nach seinen Wünschen zu gestalten. Wenn Sie beispielsweise den Prozentsatz an Anrufen schlechter Qualität für AppSharing darstellen möchten, müssen Sie einen neuen Messwert für AppSharing hinzufügen. Wenn Sie sämtliche TCP-Anrufe vs. UDP-Anrufe anzeigen möchten, müssen Sie eine neue Dimension für den Transporttyp hinzufügen. Wenn Sie die Anzahl an Anrufen schlechter Qualität innerhalb eines bestimmten Gebäudes anzeigen möchten, müssen Sie einen neuen Filter hinzufügen, damit nur die ein- und ausgehenden Anrufe dieses Gebäudes berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="25c0c-p125">So far, the report is still very simple. The user can add more measurements, dimensions, or filters to customize the report. For example, if you want to show AppSharing poor call percentage, then a new measurement regarding AppSharing needs to be added. If you want to show all TCP calls v.s. UDP calls, a new dimension regarding transportation type should be added. If you want to show the number of poor calls within a specific building, then a new filter should be added to select the calls to and from that building.</span></span>

 <span data-ttu-id="25c0c-184">**Beispiel 2: Beispiel für eine Berichtdefinition**</span><span class="sxs-lookup"><span data-stu-id="25c0c-184">**Example 2: Report definition sample**</span></span>

<span data-ttu-id="25c0c-p126">Beim Programmieren einer Abfrage kann es manchmal schwierig sein herauszufinden, wie man die vollständige Liste aus Messwerten/Dimensionen/Filtern mit den entsprechenden Werten erstellen soll. In diesem Fall können Sie zum Portal wechseln, einen Bericht mithilfe des Berichteditors definieren, sich dann die JSON-Zeichenfolge der Berichtdefinition anzeigen lassen und die Definition in einen neuen benutzerdefinierten Bericht kopieren.</span><span class="sxs-lookup"><span data-stu-id="25c0c-p126">It might be difficult for someone to figure out how to write the full list of measurements/dimensions/filters and their corresponding values when constructing a query. In this case, you can go to the Portal, build a report using the report editor, and view the JSON string of the report definition, and then copy the definition into a custom report.</span></span> 

<span data-ttu-id="25c0c-p127">In diesem Beispiel erstellen wir eine Webseite wie in der Abbildung, in der ein Benutzer die Kennung eines vorhandenen Berichtsatzes (oder Berichts) eingeben und die Definition des Berichtsatzes oder Berichts auf der Webseite anzeigen kann. Anschließend kann er die JSON-Zeichenfolge der einzelnen Berichte in einen Code ähnlich wie Beispiel 1 einfügen und jeden beliebigen benutzerdefinierten Bericht erstellen.</span><span class="sxs-lookup"><span data-stu-id="25c0c-p127">In this example, we will create a web page like the one shown in the figure where a user can enter the ID of any existing report set (or report) and show the definition of the report set or report on the web page. The user can then plug the JSON string of each report into code similar to the one shown in Example 1 and construct any customized report the user desires.</span></span> 

![CQD-Beispiel](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

<span data-ttu-id="25c0c-p128">Zur Erstellung eines Anzeigetools für die Berichtdefinition muss eine Anfrage an den Repository-Service gesendet werden, um die JSON-Zeichenfolgedarstellungen für die Definitionen des gewünschten Berichtsatzes abzurufen. Die Repository-API gibt daraufhin eine Berichtsatzdefinition zurück, die auf einer vorhandenen Berichtsatzkennung basiert.</span><span class="sxs-lookup"><span data-stu-id="25c0c-p128">To create the report definition viewer tool, we need to send calls to Repository Service to retrieve the JSON string representations of the definitions of every report-set we want. The Repository API will return report-set definition based on a given report set ID.</span></span> 

<span data-ttu-id="25c0c-192">Ein kurzes Beispiel ist wie folgt der Code einen Block enthält, die ein einfaches Beispiel zum Senden einer Abfrage mit dem Repository-Dienst den Inhalt eines Repository-Elements auf Grundlage seines Bezeichners abrufen.</span><span class="sxs-lookup"><span data-stu-id="25c0c-192">A quick example is as follows, the code contains a block that is a simple example to send a query to the Repository service to get the contents of a repository item based on its identifier.</span></span> <span data-ttu-id="25c0c-193">Und die nächsten Codeabschnitt (ProcessReportSetData-Methode) wird AJAX-Aufrufe, um die Definition für jeden Bericht in diesem Bericht Set zu senden.</span><span class="sxs-lookup"><span data-stu-id="25c0c-193">And the next portion of code (processReportSetData method) is sending AJAX calls to get the definition of each report within that report set.</span></span> <span data-ttu-id="25c0c-194">Da die in dem Webportal CQD-ID die ID einer Gruppe Bericht ist, gibt der AJAX-Aufruf ein Berichts Element festgelegt zurück.</span><span class="sxs-lookup"><span data-stu-id="25c0c-194">Since the ID in the CQD web portal is the ID of a report set, the AJAX call will return a report set item.</span></span> <span data-ttu-id="25c0c-195">Weitere Details zur Repository-API und insbesondere GetItems, finden Sie in der [Elemente abrufen](get-items.md).</span><span class="sxs-lookup"><span data-stu-id="25c0c-195">More detail on the Repository API and specifically, GetItems, can be found in the [Get Items](get-items.md).</span></span> 

```
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

<span data-ttu-id="25c0c-196">Die oben genannten führt zu einer Webseite wie in der Abbildung (ohne die Definition des Berichts beim ersten Besuch).</span><span class="sxs-lookup"><span data-stu-id="25c0c-196">The above will result in a web page like the one in the figure (without the report definition upon initial visit).</span></span> <span data-ttu-id="25c0c-197">Rufen Sie die Bericht Satz-ID aus CQD Portal (es wird nach dem Signieren / #/ CQD Portal URL (z. B.</span><span class="sxs-lookup"><span data-stu-id="25c0c-197">Get the report set ID from CQD portal (it is after '/#/' sign in CQD portal URL (E.g.</span></span> <span data-ttu-id="25c0c-198">in der ersten Abbildung des Berichts Satz-ID ist 3024), und platzieren Sie diese Berichts Satz-ID in der eingabeabschnitt dieser Webseite.</span><span class="sxs-lookup"><span data-stu-id="25c0c-198">in the first figure the report set ID is 3024), and put this report set ID into the input section of this web page.</span></span> <span data-ttu-id="25c0c-199">Drücken Sie die Taste "Load", und sehen Sie die vollständige Definition (Maßangaben, Dimensionen, Filter Listen) des Berichts ein.</span><span class="sxs-lookup"><span data-stu-id="25c0c-199">Press the "load" button and see the full definition (measurements, dimensions, filters lists) of the report set.</span></span>

<span data-ttu-id="25c0c-p131">Zusammengefasst gehen Sie wie folgt vor, um schnell die vollständige Definition eines Berichts/ Berichtsatzes zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="25c0c-p131">In summary, in order to quickly get the full definition of a report/report set. The steps are:</span></span>

1. <span data-ttu-id="25c0c-202">Besuchen Sie das Portal, und verwenden Sie den Abfrage-Editor zum Anpassen eines Berichts (klicken Sie auf "Bearbeiten" Schaltfläche oberhalb eines Berichts zu bearbeiten, hinzuzufügen, entfernen Sie die Maßangaben/Dimensionen/Filter aus, und speichern Sie den Bericht).</span><span class="sxs-lookup"><span data-stu-id="25c0c-202">Go to the Portal and use the query editor to customize a report (click the "Edit" button above a report to edit, add, remove measurements/dimensions/filters, and then save the report).</span></span>

2. <span data-ttu-id="25c0c-203">Rufen Sie die Berichts-ID aus der URL (die ganze Zahl nach / #/ sign in URL).</span><span class="sxs-lookup"><span data-stu-id="25c0c-203">Get the report set ID from URL (the integer after '/#/' sign in URL).</span></span>

3. <span data-ttu-id="25c0c-204">Starten Sie die Berichtdefinitions-Webseite, die in Beispiel 2 erstellt wurde, geben Sie die Berichtsatzkennung ein und rufen Sie die vollständige Definition eines Berichtsatzes ab (um ihn bei API-Abrufen zu verwenden).</span><span class="sxs-lookup"><span data-stu-id="25c0c-204">Launch this Report Definition web page created in Example 2, and enter the report set ID and retrieve the full definition of a report set (to use in Data API calls).</span></span>

   <span data-ttu-id="25c0c-205">**Beispiel 3: Beispiel mit einer Scorecard**</span><span class="sxs-lookup"><span data-stu-id="25c0c-205">**Example 3: Scorecard sample**</span></span>

<span data-ttu-id="25c0c-p132">Jetzt ist es an der Zeit für eine kompliziertere Aufgabe. Wie gehen wir vor, um eine Webseite wie in der Abbildung zu erstellen? Hierzu müssen wir Beispiel 1 aktualisieren (mithilfe der Webseite aus Beispiel 2, um die vollständige Definition eines beliebigen Berichts abzurufen), damit wir größere Datenmengen bewältigen können.</span><span class="sxs-lookup"><span data-stu-id="25c0c-p132">Time for a more complicated task. What if we want to create a web page like the figure? We need to update Example 1, (with the help of the web page generated in Example 2 to retrieve the full definition of any report) so that we can handle larger amount of data.</span></span>

<span data-ttu-id="25c0c-p133">In diesem Fall müssen wir die Liste der Messwerte und Dimensionen aktualisieren. Um einen Messwert und/oder eine Dimension hinzuzufügen oder zu bearbeiten, folgen Sie den Anweisungen aus Beispiel 2 und rufen Sie die vollständige Berichtdefinition (einschließlich der vollständigen Listen für Messwerte und Dimensionen) ab. Fügen Sie die vollständige Berichtdefinition in den Beispielcode ein.</span><span class="sxs-lookup"><span data-stu-id="25c0c-p133">In this case, we need to update the measurement and dimension list. The way to figure out how to add/edit a measurement and/or a dimension is to follow the instructions in Example 2, and retrieve the full report definition, including the full measurement and dimension lists. Plug the full report definition into the sample code.</span></span> 

<span data-ttu-id="25c0c-212">Im Folgenden erhalten Sie detaillierte Anweisungen zum Abruf der Scorecard-Seite in der Abbildung mit den Daten aus Beispiel 1:</span><span class="sxs-lookup"><span data-stu-id="25c0c-212">Here are the detailed steps to get to the scorecard page in the figure from the sample provided in Example 1:</span></span>

1. <span data-ttu-id="25c0c-213">Aktualisieren von Maßangaben in der Variablen "Abfrage" aus `[Measures].[Audio Good Streams JPDR Count]` und `[Measures].[Audio Poor Streams JPDR Count]` auf `[Measures].[AudioPoorJPDRPercentage]`.</span><span class="sxs-lookup"><span data-stu-id="25c0c-213">Update Measurements in the 'query' variable from  `[Measures].[Audio Good Streams JPDR Count]` and `[Measures].[Audio Poor Streams JPDR Count]` to `[Measures].[AudioPoorJPDRPercentage]`.</span></span> 

2. <span data-ttu-id="25c0c-214">Aktualisieren Sie die Filter.</span><span class="sxs-lookup"><span data-stu-id="25c0c-214">Update the filters.</span></span> <span data-ttu-id="25c0c-215">Die JSON-Daten für Filter in Beispiel 1 weist einen Filter, die auf die Dimension festgelegt ist `[StartDate].[Month]`.</span><span class="sxs-lookup"><span data-stu-id="25c0c-215">The JSON data for Filters in Example 1 has one filter, which is set on the dimension  `[StartDate].[Month]`.</span></span> <span data-ttu-id="25c0c-216">Da Filter JSON-Arrays sind, können zur Liste der Filter weitere Dimensionen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="25c0c-216">Since Filters is a JSON array, additional dimensions can be added to the list of filters.</span></span> <span data-ttu-id="25c0c-217">Wenn den Server-Client in verkabelten Aufrufen für die "CurrentMonth" erhalten möchten, sollten wir beispielsweise folgenden Filter haben:</span><span class="sxs-lookup"><span data-stu-id="25c0c-217">For example, to get the server-client inside wired calls for the "currentMonth", we should have the following filters:</span></span>

   ```
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

   <span data-ttu-id="25c0c-218">Hier die Dimension `[Scenarios].[ScenarioPair]` wird festgelegt, `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`.</span><span class="sxs-lookup"><span data-stu-id="25c0c-218">Here the dimension  `[Scenarios].[ScenarioPair]` is set to equal `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`.</span></span> <span data-ttu-id="25c0c-219">Die `[Scenario.][ScenarioPair]` ist eine spezielle Dimension erstellt, um den Bericht erstellen zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="25c0c-219">The  `[Scenario.][ScenarioPair]` is a special dimension created to simplify report creation.</span></span> <span data-ttu-id="25c0c-220">Sie hat sechs Werte: `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`.</span><span class="sxs-lookup"><span data-stu-id="25c0c-220">It has six values corresponding to `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`.</span></span> <span data-ttu-id="25c0c-221">Um ein Szenario definieren zu können, brauchen wir also anstelle einer Kombination von 6 Filtern nur 1 Filter.</span><span class="sxs-lookup"><span data-stu-id="25c0c-221">So instead of using a combination of 6 filters to define a scenario, we only need to use 1 filter.</span></span> <span data-ttu-id="25c0c-222">In unserem Beispiel der Wert `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` übersetzt für das Szenario, in dem: zuerst Server ist, Zweitens ist kein Server, zuerst ist innerhalb, Zweitens innerhalb, erste Verbindungstyp ist verkabelt und zweiten Verbindungstyp ist verkabelt, also die genaue Definition " Server-Client-Inside verkabelt".</span><span class="sxs-lookup"><span data-stu-id="25c0c-222">In our example, the value  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` translates to the scenario where: first is server, second is not server, first is inside, second is inside, first connection type is wired, and second connection type is wired, which is the exact definition of "Server-Client-Inside Wired".</span></span>

3. <span data-ttu-id="25c0c-p136">Erstellen Sie einen einzelnen Filtersatz pro Szenario. In der Abbildung steht jede Zeile in der Scorecard für ein anderes Szenario, das wiederum für einen anderen Filter steht (während Dimensionen und Messwerte gleich bleiben).</span><span class="sxs-lookup"><span data-stu-id="25c0c-p136">Create one filter set per scenario. Each row in the scorecard, in the figure, represents a different scenario, which will be a different filter (while the dimensions and measurements stay the same).</span></span> 

4. <span data-ttu-id="25c0c-p137">Analysieren Sie die Ergebnisse aus den AJAX-Abrufen und fügen Sie sie an der richtigen Stelle in der Tabelle ein. Da es sich hierbei in der Hauptsache um eine HTML- und JavaScript-Manipulation handelt, gehen wir nicht im Detail darauf ein. Den Code finden Sie in Anhang A.</span><span class="sxs-lookup"><span data-stu-id="25c0c-p137">Parse the results from the AJAX calls and place them in the correct position of the table. Since this is mostly HTML and JavaScript manipulation, we will not go into the details here. Instead, the code is provided in Appendix A.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="25c0c-228">Wenn Cross-Origin Resource Sharing (CORS) aktiviert ist, können Benutzer Fehler auftreten, wie "keine"Access-Steuerelement-zulassen-Ursprung"-Header auf die angeforderte Ressource vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="25c0c-228">If Cross-Origin Resource Sharing (CORS) is enabled, users may encounter errors like "No 'Access-Control-Allow-Origin' header is present on the requested resource.</span></span> <span data-ttu-id="25c0c-229">Ursprung "Null" ist daher nicht Zugriff zulässig".</span><span class="sxs-lookup"><span data-stu-id="25c0c-229">Origin 'null' is therefore not allowed access".</span></span> <span data-ttu-id="25c0c-230">Um das Problem zu lösen, speichern Sie die HTML-Datei in dem Ordner, in dem auch das Portal installiert ist (standardmäßig unter `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`.</span><span class="sxs-lookup"><span data-stu-id="25c0c-230">To resolve the issue, place the HTML file under the folder where the Portal is installed (by default, it should be `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`.</span></span> <span data-ttu-id="25c0c-231">Rufen Sie über einen beliebigen Browser mit der URL den HTML-Code `http://<servername>/cqd/<html_file_name>`.</span><span class="sxs-lookup"><span data-stu-id="25c0c-231">Then access the html through any browser with the URL  `http://<servername>/cqd/<html_file_name>`.</span></span> <span data-ttu-id="25c0c-232">(Die Standard-URL für lokale CQD Dashboard ist `http://<servername>/cqd.`)</span><span class="sxs-lookup"><span data-stu-id="25c0c-232">(The default URL for local CQD dashboard is  `http://<servername>/cqd.`)</span></span> 

### <a name="appendix-a"></a><span data-ttu-id="25c0c-233">Anhang A</span><span class="sxs-lookup"><span data-stu-id="25c0c-233">Appendix A</span></span>

<span data-ttu-id="25c0c-234">HTML-Code für Beispiel 3 (Scorecard-Beispiel):</span><span class="sxs-lookup"><span data-stu-id="25c0c-234">HTML code for Example 3 (Scorecard sample):</span></span>

```
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