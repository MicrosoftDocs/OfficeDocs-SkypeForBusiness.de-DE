---
title: 'Lync Server 2013: Verwenden von Überwachungsberichten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Monitoring Reports
ms:assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558662(v=OCS.15)
ms:contentKeyID: 48184480
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c37cd0f96ea0dd8e3fa63a851c3c93caf5988c7d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-monitoring-reports-in-lync-server-2013"></a><span data-ttu-id="93259-102">Verwenden von Überwachungsberichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93259-102">Using Monitoring Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93259-103">_**Letztes Änderungsstand des Themas:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="93259-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="93259-104">Lync Server 2013 enthält eine Reihe von Standardberichten, die von Microsoft SQL Server Reporting Service veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="93259-104">Lync Server 2013 includes a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="93259-105">Diese Berichte, auf die über einen Webbrowser zugegriffen werden kann, liefern Informationen zu Nutzung, Anrufdiagnose und Medienqualität basierend auf den KDS- und QoE-Datensätzen in den KDS- und QoE-Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="93259-105">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span>

<span data-ttu-id="93259-106">Um diese Berichte verwenden zu können, müssen Sie Überwachungsberichte auf einem Computer installieren, auf dem eine Instanz der SQL Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="93259-106">In order to use these reports, you must install Monitoring Reports on a computer that is running an instance of the SQL Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="93259-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="93259-107">In This Section</span></span>

  - <span data-ttu-id="93259-108">[Mithilfe des Überwachungs Dashboards in lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)   erhalten Administratoren einen schnellen Überblick über die Systemintegrität und Systemauslastung.</span><span class="sxs-lookup"><span data-stu-id="93259-108">[Using the Monitoring Dashboard in Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)   Provides administrators with a quick overview of their system health and system usage.</span></span>

  - <span data-ttu-id="93259-109">[Die System Nutzungsberichte in lync Server 2013](lync-server-2013-system-usage-reports.md)   bieten Informationen zur Systemnutzung auf der Grundlage von KDS-Daten, die von lync Server gesammelt wurden.</span><span class="sxs-lookup"><span data-stu-id="93259-109">[System usage reports in Lync Server 2013](lync-server-2013-system-usage-reports.md)   Provides system usage information based on CDR data collected by Lync Server.</span></span>

  - <span data-ttu-id="93259-110">[Anruf Diagnoseberichte (pro Benutzer) in lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)   bieten benutzerbezogene Informationen zu fehlgeschlagenen Peer-to-Peer-und Konferenzsitzungen.</span><span class="sxs-lookup"><span data-stu-id="93259-110">[Call Diagnostic Reports (per user) in Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)   Provides per-user information about failed peer-to-peer and conferencing sessions.</span></span>

  - <span data-ttu-id="93259-111">[Anruf Diagnoseberichte in lync Server 2013](lync-server-2013-call-diagnostic-reports.md)   enthält zusammenfassende Informationen und Diagnosedaten für fehlgeschlagene Peer-to-Peer-und Konferenzsitzungen.</span><span class="sxs-lookup"><span data-stu-id="93259-111">[Call Diagnostic Reports in Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)   Provides summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

  - <span data-ttu-id="93259-112">[Die Medien Qualitäts Diagnoseberichte in lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)   enthält Informationen zur Anrufqualität sowie Diagnose-und Problembehandlungsinformationen für fehlgeschlagene Anrufe.</span><span class="sxs-lookup"><span data-stu-id="93259-112">[Media Quality Diagnostic Reports in Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)   Provides information about call quality as well as diagnostic and troubleshooting information for failed calls.</span></span>

</div>

<div>

## <a name="locating-records"></a><span data-ttu-id="93259-113">Suchen von Datensätzen</span><span class="sxs-lookup"><span data-stu-id="93259-113">Locating Records</span></span>

<span data-ttu-id="93259-p102">In Monitoring Server-Berichten wird jeweils immer nur eine begrenzte Anzahl von Datensätzen auf dem Bildschirm angezeigt. Die tatsächlich auf einem Bildschirm angezeigte Anzahl von Datensätzen hängt vom jeweiligen Bericht ab. Wenn Sie die Datensätze anzeigen möchten, die aktuell nicht auf dem Bildschirm sichtbar sind, können Sie die standardmäßigen Steuerelemente für die Rückwärts- bzw. Vorwärtsnavigation (die in der Symbolleiste jedes Berichts vorhanden sind) verwenden, mit denen Sie in den Daten blättern können. Darüber hinaus können Sie schnell zur ersten oder letzten Seite des Datasets springen.</span><span class="sxs-lookup"><span data-stu-id="93259-p102">Monitoring Reports only show a limited number of records on the screen at any one time. The actual number of records displayed on a screen varies depending on the report. To view the records that are not currently shown on the screen you can use the standard forward and backward control (found on each report’s toolbar) that enable you to page through the data. You can also quickly jump to the first page or the last page of the dataset.</span></span>

<span data-ttu-id="93259-118">Neben der Verwendung der Steuerelemente für die Rückwärts- bzw. Vorwärtsnavigation können Sie auch zu jeder beliebigen Seite im Dataset navigieren, indem Sie einfach in das Feld **Aktuelle Seite** die Seitennummer eingeben und dann die EINGABETASTE drücken.</span><span class="sxs-lookup"><span data-stu-id="93259-118">In addition to using the forward and backward controls, you can also jump to any page in the dataset simply by typing the page number in the **Current Page** box, and then press ENTER.</span></span>

<span data-ttu-id="93259-p103">Sie können aber nicht nur in den Daten blättern. Jeder Bericht bietet eine eingeschränkte Suchfunktion für Datensätze. Für die Suche nach Datensätzen anhand eines bestimmten Werts geben Sie den gewünschten Wert in das Feld **Suchen** ein, und klicken Sie dann auf **Suchen**. Die Daten werden nun durchsucht. Die Suchfunktion wird bei der ersten gefundenen Instanz des Werts, den Sie in das Feld **Suchen** eingegeben haben, angehalten. Klicken Sie auf **Weiter**, um nach dem nächsten Datensatz zu suchen, der die Suchkriterien erfüllt.</span><span class="sxs-lookup"><span data-stu-id="93259-p103">In addition to providing the ability to page through the data, each report also includes the limited ability to find records. To find records based on a given value, type that value into the **Find** box, and then click **Find**. The report begins searching through the data and stops on the first instance of the value that you entered in the **Find** box. To find the next record that meets the search criteria, click **Next**.</span></span>

<span data-ttu-id="93259-p104">Wie bereits erwähnt, weisen die Monitoring Server-Berichte nur die grundlegendsten Suchfunktionen auf. Beispielsweise können Sie nicht angeben, in welchem Feld nach dem Wert gesucht werden soll. Der Suchmechanismus sucht automatisch in jedem Feld jedes Datensatzes nach Übereinstimmungen. Die Verwendung von Platzhaltern ist bei der Suche nicht möglich, und bei allen Suchvorgängen wird nach Teilübereinstimmungen gesucht. Wenn Sie also nach „111“ suchen, wird nicht nur der Wert „111“ zurückgegeben, sondern auch die Werte „11100“, „811“, „3112“, „611A5B“ sowie alle anderen Felder, die den Wert „111“ irgendwo in diesem Feld aufweisen.</span><span class="sxs-lookup"><span data-stu-id="93259-p104">As noted, the Monitoring Reports provide only the most basic search functions. For example, you cannot specify which field the value should be found in. The search mechanism automatically searches for matching values in every field in every record. You cannot use wildcards in your searches, and all searches look for partial values. That means that if you search for 111 the search returns the value 111 along with the values 11100, 811, 3112, 611A5B, and any other fields that include the value 111 anywhere within that field.</span></span>

<span data-ttu-id="93259-p105">Berichte sind so konfiguriert, dass ein Standardsatz von Datensätzen angezeigt wird. Beispielsweise enthält der Bericht über Benutzerregistrierung standardmäßig Benutzerregistrierungsaktivitäten für die letzte Woche. Dies kann in manchen Fällen zu einem Bericht ohne Datensätze führen. In diesem Fall bedeutet dies, dass in der letzten Woche keine Benutzerregistrierungen ausgeführt wurden. Falls die Meldung Es stimmen keine Ergebnisse mit den Berichtfiltern überein angezeigt wird, sollten Sie die Filterwerte ändern (legen Sie z. B. als Zeitraum nicht die letzte Woche, sondern den letzten Monat fest) und die Abfrage erneut ausführen. Ausführliche Informationen finden Sie unter "Filtern von Daten" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="93259-p105">Each report is configured to show a default set of records. For example, by default the User Registration Report shows user registration activities for the past week. In some cases, this might result in a report that returns no records. In this case, it means that no user registrations have taken place in the past week. If you see the message “No results match the report filters,” try changing the filter values (for example, change the time period to the past month rather than the past week) and rerun the query. For details, see the "Filtering Data" section later in this topic.</span></span>

</div>

<div>

## <a name="filtering-data"></a><span data-ttu-id="93259-134">Filtern von Daten</span><span class="sxs-lookup"><span data-stu-id="93259-134">Filtering Data</span></span>

<span data-ttu-id="93259-p106">Es wird immer wieder vorkommen, dass Sie nur einen Teil der Datensätze anzeigen möchten. Beispielsweise nur Peer-zu-Peer-Sitzungen anstelle von Peer-zu-Peer-Sitzungen und Konferenzsitzungen. Entsprechend werden Sie hin und wieder die Anzahl der zurückgegebenen Datensätze reduzieren müssen. In einem Bericht können standardmäßig nur die ersten 1.000 Datensätze eines Datasets angezeigt werden. Zu diesem Zweck gibt es in den meisten Berichten eine Reihe von Filteroptionen. Wenn Sie beispielsweise nur Datensätze für den Zeitraum vom 1. Januar 2011 bis zum 15. Januar 2011 anzeigen möchten, können Sie in den meisten Berichten „1. Januar 2011“ in das Feld **Von** und „15. Januar 2011“ in das Feld **Bis** eingeben. Wenn Sie dann auf **Bericht anzeigen** klicken, werden die zurückgegebenen Daten auf Aktivitäten beschränkt, die zwischen dem 1 Januar 2011 und dem 15. Januar 2011 stattfanden.</span><span class="sxs-lookup"><span data-stu-id="93259-p106">There will likely be times when you want to look at only a subset of records. For example, only peer-to-peer sessions as opposed to both peer-to-peer sessions and conference sessions. Likewise, there will be times when you need to reduce the number of records that are returned. By default, a report can only display the first 1,000 records in a data set. To address these issues, most reports include a number of filtering options. For example, if you want to view only records for the time period January 1, 2011 through January 15, 2011, you can enter January 1, 2011 in the **From** box and January 15, 2011 in the **To** box. If you then click **View Report**, the returned data will be limited to activities that took place between January 1, 2011 and January 15, 2011.</span></span>

<span data-ttu-id="93259-p107">Die verfügbaren Filter hängen vom jeweils angezeigten Bericht ab. Ausführliche Informationen zu einem bestimmten Bericht finden Sie im Hilfethema für diesen Bericht.</span><span class="sxs-lookup"><span data-stu-id="93259-p107">The filters available to you vary depending on the report that you are viewing. For details about a specific report, see the help topic for that report.</span></span>

</div>

<div>

## <a name="exporting-data"></a><span data-ttu-id="93259-144">Exportieren von Daten</span><span class="sxs-lookup"><span data-stu-id="93259-144">Exporting Data</span></span>

<span data-ttu-id="93259-p108">In den Monitoring Server-Berichten gibt es mindestens zwei verschiedene Methoden zum Exportieren der Berichtsdaten. Sie können die Option **Exportieren** in der Symbolleiste verwenden, die oben in jedem Bericht angezeigt wird. Wählen Sie zur Verwendung dieser Option in der Dropdownliste **Format auswählen** das gewünschte Exportformat aus. Die folgenden Formate sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="93259-p108">The Monitoring Reports provide at least two different ways to export the data included in a report. You can use the **Export** option in the toolbar that appears at the top of each report. To use this option, select the desired export format from the **Select a format** drop-down list. The following formats are available to you:</span></span>

  - <span data-ttu-id="93259-149">XML-Datei mit Berichtsdaten</span><span class="sxs-lookup"><span data-stu-id="93259-149">XML file with report data</span></span>

  - <span data-ttu-id="93259-150">CSV (Komma als Trennzeichen)</span><span class="sxs-lookup"><span data-stu-id="93259-150">CSV (comma delimited)</span></span>

  - <span data-ttu-id="93259-151">Acrobat (PDF)-Datei</span><span class="sxs-lookup"><span data-stu-id="93259-151">Acrobat (PDF) file</span></span>

  - <span data-ttu-id="93259-152">MHTML (Webarchiv)</span><span class="sxs-lookup"><span data-stu-id="93259-152">MHTML (web archive)</span></span>

  - <span data-ttu-id="93259-153">Excel</span><span class="sxs-lookup"><span data-stu-id="93259-153">Excel</span></span>

  - <span data-ttu-id="93259-154">TIFF-Datei</span><span class="sxs-lookup"><span data-stu-id="93259-154">TIFF file</span></span>

  - <span data-ttu-id="93259-155">Word</span><span class="sxs-lookup"><span data-stu-id="93259-155">Word</span></span>

<span data-ttu-id="93259-p109">Klicken Sie nach der Auswahl eines Formats auf **Exportieren**. Klicken Sie auf **Speichern**, wenn das Dialogfeld **Dateidownload** angezeigt wird. Wählen Sie im Dialogfeld **Speichern unter** einen Zielordner aus, geben Sie einen Dateinamen ein, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="93259-p109">After selecting a format, click **Export**. When the **File Download** dialog box appears, click **Save**. In the **Save As** dialog box, select a destination folder, enter a file name, and then click **Save**.</span></span>

<span data-ttu-id="93259-p110">Wenn Sie Microsoft OneNote installiert haben, können Sie die Berichtsdaten nach OneNote kopieren. Klicken Sie dazu in der Symbolleiste mit der rechten Maustaste auf die Schaltfläche **Bericht anzeigen**. Wählen Sie im Dialogfeld **Speicherort in OneNote auswählen** den Bereich in OneNote aus, in den Sie die Daten kopieren möchten, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="93259-p110">If you have Microsoft OneNote installed, you can also copy the report data to OneNote. To do this, right-click the **View Report** button on the toolbar. In the **Select Location in OneNote** dialog box select the section in OneNote where you want to copy the data, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

