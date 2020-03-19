---
title: Anzeigen der Microsoft Teams-Auslastung in Power BI mithilfe von CQD-Daten
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Verwenden Sie die Power BI-Berichte der Teams-Auslastung, um die Verwendung von Microsoft Teams in Ihrer Organisation zu überwachen.
ms.openlocfilehash: 7eb39d043fafae0464ac52aa1e328c24b22d73f3
ms.sourcegitcommit: 86366b66b15870fe83cbb76e1ae7aa1ce9b3bfe1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42858760"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="11f9e-103">Anzeigen der Microsoft Teams-Auslastung in Power BI mithilfe von CQD-Daten</span><span class="sxs-lookup"><span data-stu-id="11f9e-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="11f9e-104">Neu im März 2020 haben wir unseren herunterladbaren [Power BI-Abfragevorlagen für CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)einen Bericht zur Nutzung von Teams hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="11f9e-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="11f9e-105">In diesem Bericht zur neuen Teams-Auslastung können Sie sehen, wie (und wie viel) Ihre Benutzer Microsoft Teams verwenden.</span><span class="sxs-lookup"><span data-stu-id="11f9e-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams.</span></span> <span data-ttu-id="11f9e-106">Bei diesen Berichten handelt es sich um einen zentralen Standort, an dem sowohl Administratoren als auch Unternehmensleiter schnell zu diesen Daten wechseln können.</span><span class="sxs-lookup"><span data-stu-id="11f9e-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="11f9e-107">Der Power BI-Bericht "Teams-Auslastung" besteht aus zwei Hauptberichten: Zusammenfassung der **[Anruf Anzahl](#call-count-summary-report)** und **[Zusammenfassung der audiominuten](#audio-minutes-summary-report)**.</span><span class="sxs-lookup"><span data-stu-id="11f9e-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="11f9e-108">Die Berichte " [tägliche Nutzung](#daily-usage) " und " [regionale Audiodetails](#regional-audio-details) " werden angezeigt, wenn ein Benutzer die Drilldown-Berichte nutzt, die in den folgenden Beschreibungen aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="11f9e-108">The [Daily Usage](#daily-usage) and [Regional Audio Details](#regional-audio-details) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="11f9e-109">Gebäude-und subnetzdaten müssen ausgefüllt werden, um regionale und Netzwerkfilter Funktionen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="11f9e-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="11f9e-110">Zusammenfassungsbericht "Anruf Anzahl"</span><span class="sxs-lookup"><span data-stu-id="11f9e-110">Call Count Summary Report</span></span>

<span data-ttu-id="11f9e-111">Auf der Hauptseite (Zusammenfassung der Anruf Anzahl) werden die Anzahl der Audio-, Video-und Bildschirmfreigabe Sitzungen über die letzten 30 und 90 Tage, wie im Abschnittstitel angegeben, sofort bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="11f9e-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="11f9e-112">Die anfänglich angezeigten Daten sind für die gesamte Organisation und können mithilfe der Dropdownoptionen für datenschnitt auf der linken Seite der Seite gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="11f9e-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![Screenshot: Anruf Grafschaft-Zusammenfassungsbericht](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="11f9e-114">Rechts neben der Dropdownliste der datenschnitte wird die Anzahl der Anrufe nach Medientyp in den letzten dreißig Tagen in eine interne/externe Ansicht aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="11f9e-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="11f9e-115">Der obige Screenshot zeigt, dass weitere Anrufe von außerhalb der Unternehmensstandorte ablaufen, was in der aktuellen globalen Umgebung Sinn macht.</span><span class="sxs-lookup"><span data-stu-id="11f9e-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="11f9e-116">![Screenshot: Anruf Grafschaft-Zusammenfassungsbericht](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="11f9e-116">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="11f9e-117">Rechts neben dem Feld "Medientyp Anzahl" haben wir die monatlichen Anruf Anzahl nach Medientyp für die letzten 90 Tage.</span><span class="sxs-lookup"><span data-stu-id="11f9e-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="11f9e-118">Jede Spalte und jeder Medientyp können mit der Maus eingeblendet werden, um die Anzahl für einen vorherigen Monat oder den aktuellen Monat bis dato anzuzeigen, wobei Trendinformationen zur Verwendung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="11f9e-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="11f9e-119">![Screenshot: Anruf Grafschaft-Zusammenfassungsbericht](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="11f9e-119">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report3.png)</span></span>

1. <span data-ttu-id="11f9e-120">Das mittlere Diagramm funktioniert wie das 90-Tage-Diagramm, bietet jedoch eine tägliche Nutzungs Ansicht für die letzten 30 Tage und ermöglicht einem Benutzer, mit der rechten Maustaste zu klicken und Details für einen bestimmten Tag zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="11f9e-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="11f9e-121">![Screenshot: Anruf Grafschaft-Zusammenfassungsbericht](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="11f9e-121">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="11f9e-122">In der unteren linken Ecke der Seite befindet sich eine Tabelle, in der die Gesamtwerte für die einzelnen Medientypen im letzten Jahr bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="11f9e-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="11f9e-123">![Screenshot: Anruf Grafschaft-Zusammenfassungsbericht](media/CQD-teams-utilization-report5.png)</span><span class="sxs-lookup"><span data-stu-id="11f9e-123">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report5.png)</span></span>
  
<span data-ttu-id="11f9e-124">Die Tabelle enthält auch einen verfügbaren Drilldown, in dem Sie einen regionalen Datenaufschlüsselung sehen können.</span><span class="sxs-lookup"><span data-stu-id="11f9e-124">The table also has an available drill down where you can see a regional data breakdown.</span></span>
    <span data-ttu-id="11f9e-125">![Screenshot: Anruf Grafschaft-Zusammenfassungsbericht](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="11f9e-125">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report6.png)</span></span>

<span data-ttu-id="11f9e-126">Rechts neben der Tabelle werden in einem Balkendiagramm die Clients angezeigt, die in den letzten 30 Tagen die meisten Verwendungszwecke (Anrufe/Streams) verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="11f9e-126">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="11f9e-127">![Screenshot: Anruf Grafschaft-Zusammenfassungsbericht](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="11f9e-127">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report7.png)</span></span>


<span data-ttu-id="11f9e-128">In der letzten Gruppe von Diagrammen für diese Seite werden die einzelnen Medientypen einzeln angezeigt, wobei die Verwendung von Konferenz-und P2P-Daten eine Unterbrechung zeigt.</span><span class="sxs-lookup"><span data-stu-id="11f9e-128">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="11f9e-129">Die folgenden Diagramme zeigen, dass im Vergleich zu P2P eine deutlich höhere Anzahl von Konferenz Nutzungen vorliegt.</span><span class="sxs-lookup"><span data-stu-id="11f9e-129">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="11f9e-130">![Screenshot: Anruf Grafschaft-Zusammenfassungsbericht](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="11f9e-130">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="11f9e-131">Zusammenfassungsbericht für Audio-Minuten</span><span class="sxs-lookup"><span data-stu-id="11f9e-131">Audio Minutes Summary Report</span></span>

<span data-ttu-id="11f9e-132">Im Bericht "audiominuten-Nutzung" wird die Gesamt Minuten Nutzung in einigen verschiedenen Ansichten bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="11f9e-132">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="11f9e-133">Wir haben die Zusammenfassung der dreißigtägigen Verwendung neben den datenschnitten als einfach zu verwendende Textfelder angezeigt.</span><span class="sxs-lookup"><span data-stu-id="11f9e-133">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="11f9e-134">Die obere Zahl zeigt die 30-Tage-Summe, wobei die internen und externen Ausfälle darunter liegen.</span><span class="sxs-lookup"><span data-stu-id="11f9e-134">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![Screenshot: Anruf Grafschaft-Zusammenfassungsbericht](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="11f9e-136">Das obere rechte Balkendiagramm bietet eine ganzjährige Ansicht der Nutzung der Konferenz Audiofunktionen.</span><span class="sxs-lookup"><span data-stu-id="11f9e-136">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="11f9e-137">Zeigen Sie mit der Maus auf den Monat, um die Gesprächsminuten für die Konferenz anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="11f9e-137">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="11f9e-138">Um die Unterschiede zwischen P2P-und Konferenz-Audio anzuzeigen, nimmt das untere linke Diagramm alle Audiodaten für das vergangene Jahr auf und unterbricht es zwischen den beiden Typen.</span><span class="sxs-lookup"><span data-stu-id="11f9e-138">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

<span data-ttu-id="11f9e-139">![Screenshot: Anruf Grafschaft-Zusammenfassungsbericht](media/CQD-teams-utilization-report10.png) das letzte Diagramm für die Seite "audiominuten" zeigt die Audio-Minuten Nutzung auf einem globalen Karten-Overlay an.</span><span class="sxs-lookup"><span data-stu-id="11f9e-139">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report10.png) The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="11f9e-140">Dieses Diagramm funktioniert nur, wenn Gebäude-und Subnetdaten in den Mandanten hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="11f9e-140">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="11f9e-141">Das Kreisdiagramm-Overlay auf der Karte kann gebohrt werden, um anschließend die regionale audionutzung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="11f9e-141">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![Screenshot: Anruf Grafschaft-Zusammenfassungsbericht](media/CQD-teams-utilization-report11.png)

## <a name="drill-through-capabilities"></a><span data-ttu-id="11f9e-143">Drill-Through-Funktionen</span><span class="sxs-lookup"><span data-stu-id="11f9e-143">Drill-through capabilities</span></span>

<span data-ttu-id="11f9e-144">Wie bereits erwähnt, können Benutzer einen Drilldown in die Berichte für tägliche und regionale Nutzung durchführen.</span><span class="sxs-lookup"><span data-stu-id="11f9e-144">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="11f9e-145">Tägliche Nutzung</span><span class="sxs-lookup"><span data-stu-id="11f9e-145">Daily Usage</span></span>

<span data-ttu-id="11f9e-146">Der Bericht "tägliche Nutzung" ermöglicht es einem Administrator, die höchst Verbrauchs Zeiten im Laufe eines Tages zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="11f9e-146">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="11f9e-147">Neben der Nutzung sind wir auch in der Lage, die gesamte Benutzer Stimmung und das Feedback für diesen Tag zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="11f9e-147">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![Screenshot: Anruf Grafschaft-Zusammenfassungsbericht](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="11f9e-149">Diese Daten können verwendet werden, um Regionen zu identifizieren, die Probleme bei Spitzenverbrauchszeiten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="11f9e-149">This data can be used to identify regions having problems during peak consumption times.</span></span>

1.  <span data-ttu-id="11f9e-150">Führen Sie auf der Zusammenfassungsseite "Anruf Anzahl" einen Drillthrough zu einem bestimmten Datum durch.</span><span class="sxs-lookup"><span data-stu-id="11f9e-150">On the Call Count Summary page, drill-through on a specific date.</span></span> <span data-ttu-id="11f9e-151">Schauen Sie sich den stündlichen Trend an diesem Tag an, um die höchst Auslastung zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="11f9e-151">Look at the hourly trend that day to find the peak utilization.</span></span>
  <span data-ttu-id="11f9e-152">![Screenshot: Anruf Grafschaft-Zusammenfassungsbericht](media/CQD-teams-utilization-report13.png)</span><span class="sxs-lookup"><span data-stu-id="11f9e-152">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report13.png)</span></span>

2.  <span data-ttu-id="11f9e-153">Klicken Sie auf die Spalte für diesen Tag, um Metriken für diese Stunde anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="11f9e-153">Click on the column for that day to display metrics for that hour.</span></span>
  <span data-ttu-id="11f9e-154">![Screenshot: Anruf Grafschaft-Zusammenfassungsbericht](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="11f9e-154">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report14.png)</span></span>
    
    1.  <span data-ttu-id="11f9e-155">In der Tabelle unter dem Diagramm werden die Metriken für diese Stunde angezeigt.</span><span class="sxs-lookup"><span data-stu-id="11f9e-155">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="11f9e-156">Dies kann nach jeder Spaltenüberschrift sortiert werden. Wir wären jedoch daran interessiert, problematische Bereiche zu finden.</span><span class="sxs-lookup"><span data-stu-id="11f9e-156">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
        ![Screenshot: Anruf Grafschaft-Zusammenfassungsbericht](media/CQD-teams-utilization-report15.png)
    
    2.  <span data-ttu-id="11f9e-158">Wir sehen, dass die IND-Region während dieses Zeitraums eine schlechte Videoleistung in Konferenzen erlebt.</span><span class="sxs-lookup"><span data-stu-id="11f9e-158">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="11f9e-159">Anschließend können die CQD-QER Microsoft-Berichte verwendet werden, um die problematische Position zu verkleinern, während der Bereich und der Zeitrahmen identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="11f9e-159">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="regional-audio-details"></a><span data-ttu-id="11f9e-160">Regionale Audiodaten</span><span class="sxs-lookup"><span data-stu-id="11f9e-160">Regional Audio Details</span></span>

<span data-ttu-id="11f9e-161">Im Bereich "regionale Audiodetails" wird die audiominuten-Verwendung für die ausgewählte Region speziell angezeigt.</span><span class="sxs-lookup"><span data-stu-id="11f9e-161">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="11f9e-162">Benutzer mit Zugriff auf CQD können die Nutzungstrends sowohl für P2P-als auch für Konferenz-Audio in der ausgewählten Region sehen.</span><span class="sxs-lookup"><span data-stu-id="11f9e-162">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="11f9e-163">Klicken Sie auf der Zusammenfassungsseite Anruf Anzahl auf eine bestimmte Region durch die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="11f9e-163">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="11f9e-164">![Screenshot: Anruf Grafschaft-Zusammenfassungsbericht](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="11f9e-164">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="11f9e-165">Wählen Sie die Zeile mit dem Bereich aus, für den zusätzliche Informationen benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="11f9e-165">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="11f9e-166">![Screenshot: Anruf Grafschaft-Zusammenfassungsbericht](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="11f9e-166">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="11f9e-167">Die Datentrends zeigen eine beträchtliche Anzahl von Minuten an, die im internen Netzwerk verwendet werden, wobei Conferencing die P2P-Nutzung weit übertrifft.</span><span class="sxs-lookup"><span data-stu-id="11f9e-167">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="11f9e-168">![Screenshot: Anruf Grafschaft-Zusammenfassungsbericht](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="11f9e-168">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="11f9e-169">Der regionale audiotrend kann verwendet werden, um zu zeigen, wie Benutzer von externen Einflüssen in der Welt beeinflusst werden.</span><span class="sxs-lookup"><span data-stu-id="11f9e-169">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="11f9e-170">Im Moment würden wir davon ausgehen, dass die externe Verwendung für die Regionen EMEA und APAC mit Personen, die zur Remote Arbeit aufgefordert werden, zunehmen wird.</span><span class="sxs-lookup"><span data-stu-id="11f9e-170">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>



## <a name="related-topics"></a><span data-ttu-id="11f9e-171">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="11f9e-171">Related topics</span></span>

[<span data-ttu-id="11f9e-172">Im Anrufqualitäts-Dashboard verfügbare Dimensionen und Kennzahlen</span><span class="sxs-lookup"><span data-stu-id="11f9e-172">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="11f9e-173">Datenstromklassifizierung im Dashboard für Anrufqualität</span><span class="sxs-lookup"><span data-stu-id="11f9e-173">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="11f9e-174">Einrichten der Anrufanalyse von Skype for Business</span><span class="sxs-lookup"><span data-stu-id="11f9e-174">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="11f9e-175">Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln</span><span class="sxs-lookup"><span data-stu-id="11f9e-175">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="11f9e-176">Anrufanalyse- und Anrufqualitäts-Dashboard</span><span class="sxs-lookup"><span data-stu-id="11f9e-176">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)
 