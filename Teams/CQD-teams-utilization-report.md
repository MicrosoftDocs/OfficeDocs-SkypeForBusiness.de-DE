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
description: Verwenden Sie die Power BI-Berichte der Teams-Auslastung für den Zugriff auf Microsoft Teams Call Quality Dashboard-Daten (CQD), um die Verwendung von Microsoft Teams in Ihrer Organisation zu überwachen.
ms.openlocfilehash: bd1a95a683da881a78acb5d4849bba0ac55f4898
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085581"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="22fb5-103">Anzeigen der Microsoft Teams-Auslastung in Power BI mithilfe von CQD-Daten</span><span class="sxs-lookup"><span data-stu-id="22fb5-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="22fb5-104">Neu im März 2020 haben wir unseren herunterladbaren [Power BI-Abfragevorlagen für CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)einen Bericht zur Nutzung von Teams hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="22fb5-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="22fb5-105">In diesen Berichten zur neuen Teams-Auslastung können Sie sehen, wie (und wie viel) Ihre Benutzer Microsoft Teams verwenden, indem Sie auf die CQD-Daten (Teams Call Quality Dashboard) zugreifen.</span><span class="sxs-lookup"><span data-stu-id="22fb5-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams by accessing Teams Call Quality Dashboard (CQD) data.</span></span> <span data-ttu-id="22fb5-106">Bei diesen Berichten handelt es sich um einen zentralen Standort, an dem sowohl Administratoren als auch Unternehmensleiter schnell zu diesen Daten wechseln können.</span><span class="sxs-lookup"><span data-stu-id="22fb5-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="22fb5-107">Der Power BI-Bericht "Teams-Auslastung" besteht aus zwei Hauptberichten: Zusammenfassung der **[Anruf Anzahl](#call-count-summary-report)** und **[Zusammenfassung der audiominuten](#audio-minutes-summary-report)**.</span><span class="sxs-lookup"><span data-stu-id="22fb5-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="22fb5-108">Die [tägliche Nutzung](#daily-usage), [regionale Audiodetails](#regional-audio-details), [Konferenzdetails](#conference-details) und [Benutzerlisten](#user-list) Berichte kommen in den Spielzustand, wenn ein Benutzer die Drilldown-Berichte nutzt, die in den folgenden Beschreibungen aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="22fb5-108">The [Daily Usage](#daily-usage), [Regional Audio Details](#regional-audio-details), [Conference Details](#conference-details) and [User List](#user-list) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="22fb5-109">Gebäude-und subnetzdaten müssen ausgefüllt werden, um regionale und Netzwerkfilter Funktionen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="22fb5-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="22fb5-110">Zusammenfassungsbericht "Anruf Anzahl"</span><span class="sxs-lookup"><span data-stu-id="22fb5-110">Call Count Summary Report</span></span>

<span data-ttu-id="22fb5-111">Auf der Hauptseite (Zusammenfassung der Anruf Anzahl) werden die Anzahl der Audio-, Video-und Bildschirmfreigabe Sitzungen über die letzten 30 und 90 Tage, wie im Abschnittstitel angegeben, sofort bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="22fb5-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="22fb5-112">Die anfänglich angezeigten Daten sind für die gesamte Organisation und können mithilfe der Dropdownoptionen für datenschnitt auf der linken Seite der Seite gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="22fb5-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![Screenshot: Teams-Auslastungsberichte](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="22fb5-114">Rechts neben der Dropdownliste der datenschnitte wird die Anzahl der Anrufe nach Medientyp in den letzten dreißig Tagen in eine interne/externe Ansicht aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="22fb5-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="22fb5-115">Der obige Screenshot zeigt, dass weitere Anrufe von außerhalb der Unternehmensstandorte ablaufen, was in der aktuellen globalen Umgebung Sinn macht.</span><span class="sxs-lookup"><span data-stu-id="22fb5-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="22fb5-116">![Screenshot: Teams-Auslastungsberichte](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="22fb5-116">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="22fb5-117">Rechts neben dem Feld "Medientyp Anzahl" haben wir die monatlichen Anruf Anzahl nach Medientyp für die letzten 90 Tage.</span><span class="sxs-lookup"><span data-stu-id="22fb5-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="22fb5-118">Jede Spalte und jeder Medientyp können mit der Maus eingeblendet werden, um die Anzahl für einen vorherigen Monat oder den aktuellen Monat bis dato anzuzeigen, wobei Trendinformationen zur Verwendung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="22fb5-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="22fb5-119">![Screenshot: Teams-Auslastungsberichte](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="22fb5-119">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report3.png)</span></span>
 

1. <span data-ttu-id="22fb5-120">Das mittlere Diagramm funktioniert wie das 90-Tage-Diagramm, bietet jedoch eine tägliche Nutzungs Ansicht für die letzten 30 Tage und ermöglicht einem Benutzer, mit der rechten Maustaste zu klicken und Details für einen bestimmten Tag zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="22fb5-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="22fb5-121">![Screenshot: Teams-Auslastungsberichte](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="22fb5-121">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="22fb5-122">In der unteren linken Ecke der Seite befindet sich eine Tabelle, in der die Gesamtwerte für die einzelnen Medientypen im letzten Jahr bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="22fb5-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="22fb5-123">![Screenshot: Teams-Auslastungsberichte ](media/CQD-teams-utilization-report5.png) ![ – Screenshot: Berichte zur Auslastung von Teams](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="22fb5-123">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report5.png) ![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report6.png)</span></span>   

<span data-ttu-id="22fb5-124">Rechts neben der Tabelle werden in einem Balkendiagramm die Clients angezeigt, die in den letzten 30 Tagen die meisten Verwendungszwecke (Anrufe/Streams) verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="22fb5-124">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="22fb5-125">![Screenshot: Teams-Auslastungsberichte](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="22fb5-125">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report7.png)</span></span>

<span data-ttu-id="22fb5-126">In der letzten Gruppe von Diagrammen für diese Seite werden die einzelnen Medientypen einzeln angezeigt, wobei die Verwendung von Konferenz-und P2P-Daten eine Unterbrechung zeigt.</span><span class="sxs-lookup"><span data-stu-id="22fb5-126">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="22fb5-127">Die folgenden Diagramme zeigen, dass im Vergleich zu P2P eine deutlich höhere Anzahl von Konferenz Nutzungen vorliegt.</span><span class="sxs-lookup"><span data-stu-id="22fb5-127">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="22fb5-128">![Screenshot: Teams-Auslastungsberichte](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="22fb5-128">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="22fb5-129">Zusammenfassungsbericht für Audio-Minuten</span><span class="sxs-lookup"><span data-stu-id="22fb5-129">Audio Minutes Summary Report</span></span>

<span data-ttu-id="22fb5-130">Im Bericht "audiominuten-Nutzung" wird die Gesamt Minuten Nutzung in einigen verschiedenen Ansichten bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="22fb5-130">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="22fb5-131">Wir haben die Zusammenfassung der dreißigtägigen Verwendung neben den datenschnitten als einfach zu verwendende Textfelder angezeigt.</span><span class="sxs-lookup"><span data-stu-id="22fb5-131">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="22fb5-132">Die obere Zahl zeigt die 30-Tage-Summe, wobei die internen und externen Ausfälle darunter liegen.</span><span class="sxs-lookup"><span data-stu-id="22fb5-132">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![Screenshot: Teams-Auslastungsberichte](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="22fb5-134">Das obere rechte Balkendiagramm bietet eine ganzjährige Ansicht der Nutzung der Konferenz Audiofunktionen.</span><span class="sxs-lookup"><span data-stu-id="22fb5-134">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="22fb5-135">Zeigen Sie mit der Maus auf den Monat, um die Gesprächsminuten für die Konferenz anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="22fb5-135">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="22fb5-136">Um die Unterschiede zwischen P2P-und Konferenz-Audio anzuzeigen, nimmt das untere linke Diagramm alle Audiodaten für das vergangene Jahr auf und unterbricht es zwischen den beiden Typen.</span><span class="sxs-lookup"><span data-stu-id="22fb5-136">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

![Screenshot: Teams-Auslastungsberichte](media/CQD-teams-utilization-report10.png)

<span data-ttu-id="22fb5-138">Das letzte Diagramm für die Seite "audiominuten" zeigt die Verwendung der audiominuten auf einem globalen Karten-Overlay an.</span><span class="sxs-lookup"><span data-stu-id="22fb5-138">The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="22fb5-139">Dieses Diagramm funktioniert nur, wenn Gebäude-und Subnetdaten in den Mandanten hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="22fb5-139">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="22fb5-140">Das Kreisdiagramm-Overlay auf der Karte kann gebohrt werden, um anschließend die regionale audionutzung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="22fb5-140">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![Screenshot: Teams-Auslastungsberichte](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a><span data-ttu-id="22fb5-142">Drill-Through-Funktionen</span><span class="sxs-lookup"><span data-stu-id="22fb5-142">Drill-through capabilities</span></span>

<span data-ttu-id="22fb5-143">Wie bereits erwähnt, können Benutzer einen Drilldown in die Berichte für tägliche und regionale Nutzung durchführen.</span><span class="sxs-lookup"><span data-stu-id="22fb5-143">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="22fb5-144">Tägliche Nutzung</span><span class="sxs-lookup"><span data-stu-id="22fb5-144">Daily Usage</span></span>

<span data-ttu-id="22fb5-145">Der Bericht "tägliche Nutzung" ermöglicht es einem Administrator, die höchst Verbrauchs Zeiten im Laufe eines Tages zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="22fb5-145">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="22fb5-146">Neben der Nutzung sind wir auch in der Lage, die gesamte Benutzer Stimmung und das Feedback für diesen Tag zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="22fb5-146">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![Screenshot: Teams-Auslastungsberichte](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="22fb5-148">Der Bericht "tägliche Nutzung" zeigt die Anzahl der Audio-, Video-und Bildschirm Freigaben für den ausgewählten Tag mit der zusätzlichen Möglichkeit, zwischen interner und externer Konnektivität zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="22fb5-148">The Daily usage report displays the number of Audio, Video and Screen shares for the selected day with the added ability to differentiate between internal and external connectivity.</span></span> <span data-ttu-id="22fb5-149">Eine Konferenz und eine Peer-to-Peer-Aufteilung erfolgt unmittelbar rechts neben dem Feld Modalwert.</span><span class="sxs-lookup"><span data-stu-id="22fb5-149">A Conference and Peer to Peer breakdown is to the immediate right of the modality total box.</span></span> <span data-ttu-id="22fb5-150">Oben rechts im Bericht finden Sie eine Liste der Konferenzen mit den zugehörigen IDs und Teilnehmern für den Tag.</span><span class="sxs-lookup"><span data-stu-id="22fb5-150">The top right of the report provides a list of conferences with their associated ID and participants for the day.</span></span> <span data-ttu-id="22fb5-151">Die Konferenzliste bietet einen zusätzlichen Drilldown zum Konferenz Detailbericht.</span><span class="sxs-lookup"><span data-stu-id="22fb5-151">The conference list provides an additional drill down to the Conference Details report as well.</span></span> <span data-ttu-id="22fb5-152">Grafik ersetzen</span><span class="sxs-lookup"><span data-stu-id="22fb5-152">REPLACE GRAPHIC</span></span>

![Screenshot: Teams-Auslastungsberichte](media/CQD-teams-utilization-report13.png)

<span data-ttu-id="22fb5-154">Das Balkendiagramm im mittleren Bereich ermöglicht es dem Benutzer, Spitzenverbrauchs Perioden im Laufe eines Tages zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="22fb5-154">The bar graph in the center area allows the user to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="22fb5-155">Benutzer können einen Drilldown in die im Diagramm dargestellte Stunde durchführen, in der der Benutzerlisten Bericht für die Stunde vorliegt.</span><span class="sxs-lookup"><span data-stu-id="22fb5-155">Users may drill down into the hour represented on the graph which will present the User List report for the hour.</span></span>

<span data-ttu-id="22fb5-156">Rechts neben dem Balkendiagramm wird das Feedback des Benutzers in einem visuellen Format angezeigt.</span><span class="sxs-lookup"><span data-stu-id="22fb5-156">To the right of the bar graph, User Feedback is presented in a visual format.</span></span> <span data-ttu-id="22fb5-157">Während die Benutzer Empfindung subjektiv sein kann, bietet Sie eine Einsicht, die verwendet werden kann, um potenzielle Probleme zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="22fb5-157">While user sentiment can be subjective, it does provide insight that can be used to identify potential issues.</span></span>

<span data-ttu-id="22fb5-158">Die untere Tabelle enthält eine Reihe von Metriken für den Tag.</span><span class="sxs-lookup"><span data-stu-id="22fb5-158">The bottom table provides a range of metrics for the day.</span></span> <span data-ttu-id="22fb5-159">Schlechte Prozentwerte sowie Ausfallraten können einem Administrator potenzielle Verbesserungsmöglichkeiten bieten.</span><span class="sxs-lookup"><span data-stu-id="22fb5-159">Poor percentages along with failure rates can provide an administrator with potential areas of improvement.</span></span> <span data-ttu-id="22fb5-160">Jede Stunde kann auch einzeln ausgewählt werden, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="22fb5-160">Each hour can also be selected individually as shown below.</span></span>

<span data-ttu-id="22fb5-161">Diese Daten können verwendet werden, um Regionen zu identifizieren, die Probleme bei Spitzenverbrauchszeiten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="22fb5-161">This data can be used to identify regions having problems during peak consumption times.</span></span>


<span data-ttu-id="22fb5-162">Klicken Sie auf die Spalte für diesen Tag, um Metriken für diese Stunde anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="22fb5-162">Click on the column for that day to display metrics for that hour.</span></span>
<span data-ttu-id="22fb5-163">![Screenshot: Teams-Auslastungsberichte](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="22fb5-163">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report14.png)</span></span>
  
  1.  <span data-ttu-id="22fb5-164">In der Tabelle unter dem Diagramm werden die Metriken für diese Stunde angezeigt.</span><span class="sxs-lookup"><span data-stu-id="22fb5-164">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="22fb5-165">Dies kann nach jeder Spaltenüberschrift sortiert werden. Wir wären jedoch daran interessiert, problematische Bereiche zu finden.</span><span class="sxs-lookup"><span data-stu-id="22fb5-165">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
    ![Screenshot: Teams-Auslastungsberichte](media/CQD-teams-utilization-report15.png)
    
  2.  <span data-ttu-id="22fb5-167">Wir sehen, dass die IND-Region während dieses Zeitraums eine schlechte Videoleistung in Konferenzen erlebt.</span><span class="sxs-lookup"><span data-stu-id="22fb5-167">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="22fb5-168">Anschließend können die CQD-QER Microsoft-Berichte verwendet werden, um die problematische Position zu verkleinern, während der Bereich und der Zeitrahmen identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="22fb5-168">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="conference-details"></a><span data-ttu-id="22fb5-169">Konferenz Details</span><span class="sxs-lookup"><span data-stu-id="22fb5-169">Conference Details</span></span>

<span data-ttu-id="22fb5-170">Der Bericht "Konferenz Details" bietet zusätzliche Einblicke für Besprechungen, von einer Teilnehmerliste bis zu den Medientypen, die während der Sitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="22fb5-170">The Conference Details report provides additional insight for meetings, from an attendee list, to the media types used during the session.</span></span>

<span data-ttu-id="22fb5-171">Klicken Sie mit der rechten Maustaste auf eine Konferenz die Teilnehmer Leiste im Diagramm Konferenz-ID auf der Seite tägliche Nutzung, um einen Drilldown in die Konferenzdetails durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="22fb5-171">Right click a conference the participant bar in the conference ID chart on the Daily usage page to drill down into the conference details.</span></span>

![Screenshot: Teams-Auslastungsberichte](media/CQD-teams-utilization-report24.png)

![Screenshot: Teams-Auslastungsberichte](media/CQD-teams-utilization-report25.png)
  

<span data-ttu-id="22fb5-174">Wir können die Teilnehmer der Konferenz sowie alle relevanten Informationen bis hin zu Paketverlust und Jitter sehen, um mögliche Problembehandlungsschritte in der unteren Tabelle zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="22fb5-174">We can see the participants in the conference as well as all the pertinent information down to packet loss and jitter to assist with potential troubleshooting efforts in the bottom table.</span></span>

![Screenshot: Teams-Auslastungsberichte](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a><span data-ttu-id="22fb5-176">Regionale Audiodaten</span><span class="sxs-lookup"><span data-stu-id="22fb5-176">Regional Audio Details</span></span>

<span data-ttu-id="22fb5-177">Im Bereich "regionale Audiodetails" wird die audiominuten-Verwendung für die ausgewählte Region speziell angezeigt.</span><span class="sxs-lookup"><span data-stu-id="22fb5-177">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="22fb5-178">Benutzer mit Zugriff auf CQD können die Nutzungstrends sowohl für P2P-als auch für Konferenz-Audio in der ausgewählten Region sehen.</span><span class="sxs-lookup"><span data-stu-id="22fb5-178">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="22fb5-179">Klicken Sie auf der Zusammenfassungsseite Anruf Anzahl auf eine bestimmte Region durch die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="22fb5-179">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="22fb5-180">![Screenshot: Teams-Auslastungsberichte](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="22fb5-180">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="22fb5-181">Wählen Sie die Zeile mit dem Bereich aus, für den zusätzliche Informationen benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="22fb5-181">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="22fb5-182">![Screenshot: Teams-Auslastungsberichte](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="22fb5-182">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="22fb5-183">Die Datentrends zeigen eine beträchtliche Anzahl von Minuten an, die im internen Netzwerk verwendet werden, wobei Conferencing die P2P-Nutzung weit übertrifft.</span><span class="sxs-lookup"><span data-stu-id="22fb5-183">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="22fb5-184">![Screenshot: Teams-Auslastungsberichte](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="22fb5-184">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="22fb5-185">Der regionale audiotrend kann verwendet werden, um zu zeigen, wie Benutzer von externen Einflüssen in der Welt beeinflusst werden.</span><span class="sxs-lookup"><span data-stu-id="22fb5-185">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="22fb5-186">Im Moment würden wir davon ausgehen, dass die externe Verwendung für die Regionen EMEA und APAC mit Personen, die zur Remote Arbeit aufgefordert werden, zunehmen wird.</span><span class="sxs-lookup"><span data-stu-id="22fb5-186">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>


### <a name="user-list"></a><span data-ttu-id="22fb5-187">Benutzerliste</span><span class="sxs-lookup"><span data-stu-id="22fb5-187">User List</span></span>

<span data-ttu-id="22fb5-188">Der Drilldown für Benutzerlisten bietet, wie man erwarten kann, benutzerspezifische Informationen für eine bestimmte Stunde, die von der Person, die den Bericht anzeigt, ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="22fb5-188">The User List drill down provides, as one might expect, user specific information for a specific hour selected by the person viewing the report.</span></span> <span data-ttu-id="22fb5-189">Der Benutzerlisten Bericht kann über einen Drilldown im Diagramm "stündliche Trends" im Bericht "tägliche Verwendung" aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="22fb5-189">The User List report is accessible through a drill down in the Hourly Trends graph on the Daily Usage report.</span></span> <span data-ttu-id="22fb5-190">Klicken Sie mit der rechten Maustaste auf die Stunde, um weitere Informationen zu erhalten, und wählen Sie Drillthrough und Benutzerliste aus, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="22fb5-190">Right click on the hour additional information is needed for and select Drill through and User List, as shown below.</span></span>

![Screenshot: Teams-Auslastungsberichte](media/CQD-teams-utilization-report19.png)

<span data-ttu-id="22fb5-192">Der Bericht "Benutzerliste" zeigt die interne/externe Konnektivität über das Ringdiagramm oben in der Mitte der Seite an.</span><span class="sxs-lookup"><span data-stu-id="22fb5-192">The User List report shows internal/external connectivity through the doughnut chart in the top center of the page.</span></span> <span data-ttu-id="22fb5-193">Wir können festzustellen, dass es in der folgenden Abbildung eine große Beteiligung von außerhalb des Unternehmensnetzwerks gibt.</span><span class="sxs-lookup"><span data-stu-id="22fb5-193">We can see that there is a large amount of participation from Outside the corporate network in the below image.</span></span>

<span data-ttu-id="22fb5-194">Oben rechts im Diagramm wird die Anzahl der Anrufe angezeigt, die von jedem Benutzer innerhalb dieser Stunde getätigt wurden.</span><span class="sxs-lookup"><span data-stu-id="22fb5-194">The top right of the graph shows the number of calls made by each user within that hour.</span></span>

![Screenshot: Teams-Auslastungsberichte](media/CQD-teams-utilization-report20.png)

<span data-ttu-id="22fb5-196">Die untere Tabelle enthält detaillierte Informationen zu den Sitzungen, an denen jeder Benutzer während dieser Stunde teilgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="22fb5-196">The bottom table provides detailed information for the sessions each user participated in during that hour.</span></span> <span data-ttu-id="22fb5-197">Die Spalte Fehlertyp ist nützlich, um zu ermitteln, was zu einem Anruf geführt hat.</span><span class="sxs-lookup"><span data-stu-id="22fb5-197">The Failure Type column is useful in determining what caused a call to drop.</span></span> <span data-ttu-id="22fb5-198">Die Spalten für das erfassen und Rendern von Geräten sind hilfreich, um zu ermitteln, warum ein Anruf mit schlechter Qualität gemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="22fb5-198">The Capture and Render Device columns are useful in identifying why a call was reported having poor quality.</span></span>


## <a name="related-topics"></a><span data-ttu-id="22fb5-199">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="22fb5-199">Related topics</span></span>

[<span data-ttu-id="22fb5-200">Im Anrufqualitäts-Dashboard verfügbare Dimensionen und Kennzahlen</span><span class="sxs-lookup"><span data-stu-id="22fb5-200">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="22fb5-201">Datenstromklassifizierung im Dashboard für Anrufqualität</span><span class="sxs-lookup"><span data-stu-id="22fb5-201">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="22fb5-202">Einrichten der Anrufanalyse von Skype for Business</span><span class="sxs-lookup"><span data-stu-id="22fb5-202">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="22fb5-203">Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln</span><span class="sxs-lookup"><span data-stu-id="22fb5-203">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="22fb5-204">Anrufanalyse- und Anrufqualitäts-Dashboard</span><span class="sxs-lookup"><span data-stu-id="22fb5-204">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

[<span data-ttu-id="22fb5-205">Teams-Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="22fb5-205">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
 