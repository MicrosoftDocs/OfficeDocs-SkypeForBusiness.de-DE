---
title: Verwenden des CQD PSTN Direct Routing-Berichts
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies, fan.fan
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
description: Verwenden Sie den Microsoft Teams Call Quality Dashboard (CQD)) PSTN Direct Routing-Bericht, um PSTN-Anrufe in Microsoft Teams zu überwachen und zu beheben.
ms.openlocfilehash: e4662d80dbba88c1049c7ef98569dae408ca9ba0
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583102"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="7e0bb-103">Verwenden des CQD PSTN Direct Routing-Berichts</span><span class="sxs-lookup"><span data-stu-id="7e0bb-103">Using the CQD PSTN Direct Routing report</span></span>

<span data-ttu-id="7e0bb-104">Neu im März 2020 haben wir einen Microsoft Teams Call Quality Dashboard (CQD) PSTN Direct Routing-Bericht zu unseren herunterladbaren [Power BI-Abfragevorlagen für CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-104">New in March 2020, we've added a Microsoft Teams Call Quality Dashboard (CQD) PSTN Direct Routing report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="7e0bb-105">Der CQD PSTN Direct Routing-Bericht (CQD PSTN Direct Routing Report. PBit) hilft Ihnen, die Verwendungsmuster und die Qualität ihrer PSTN-Dienste zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-105">The CQD PSTN Direct Routing report (CQD PSTN Direct Routing Report.pbit) helps you understand the usage patterns and quality of your PSTN services.</span></span> <span data-ttu-id="7e0bb-106">Verwenden Sie diesen Bericht, um die Dienstnutzung zu überwachen, Informationen zu Ihrem Session Border Controller (SBC), zum Telefoniedienst, zu den Netzwerkparametern und zu den Details des Netzwerk Effektivitäts Verhältnisses.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-106">Use this report to monitor service usage, information about your Session Border Controller (SBC), the telephony service, network parameters, and Network Effectiveness Ratio details.</span></span> <span data-ttu-id="7e0bb-107">Diese Informationen können Ihnen helfen, Probleme zu erkennen, einschließlich des Grunds für gelöschte Anrufe.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-107">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="7e0bb-108">So können Sie beispielsweise feststellen, ob die Lautstärke sinkt oder wie viele Anrufe betroffen sind und aus welchem Grund.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-108">For example, you'll be able to see when volume drops, or how many calls get affected and for what reason.</span></span>


<span data-ttu-id="7e0bb-109">Der CQD PSTN Direct Routing-Bericht besteht aus vier Abschnitten:</span><span class="sxs-lookup"><span data-stu-id="7e0bb-109">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="7e0bb-110">PSTN-Übersicht</span><span class="sxs-lookup"><span data-stu-id="7e0bb-110">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="7e0bb-111">Dienst Details</span><span class="sxs-lookup"><span data-stu-id="7e0bb-111">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="7e0bb-112">Netzwerk-Effektivitäts Rate</span><span class="sxs-lookup"><span data-stu-id="7e0bb-112">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="7e0bb-113">Netzwerkparameter</span><span class="sxs-lookup"><span data-stu-id="7e0bb-113">Network Parameters</span></span>](#network-parameters)

## <a name="highlights"></a><span data-ttu-id="7e0bb-114">Hebt</span><span class="sxs-lookup"><span data-stu-id="7e0bb-114">Highlights</span></span>

1. <span data-ttu-id="7e0bb-115">Analysieren nach Anruftyp, SBC, Anrufer und Land des berufenen</span><span class="sxs-lookup"><span data-stu-id="7e0bb-115">Analyze by call type, SBC, caller and callee country</span></span>

   <span data-ttu-id="7e0bb-116">Der CQD PSTN Direct Routing-Bericht aggregiert die Zuverlässigkeits-und Nutzungs Metrik für alle SBCS Ihres Mandanten für die letzten 7, 30 oder 180 Tage (6 Monate).</span><span class="sxs-lookup"><span data-stu-id="7e0bb-116">The CQD PSTN Direct Routing report aggregates reliability and usage metrics for all SBCs on your tenant for the last 7, 30, or 180 days (6 months).</span></span> <span data-ttu-id="7e0bb-117">Sie können Daten nach Anruftyp, SBC, Rufnummernanzeige und Anruf Land analysieren.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-117">You can analyze data by call type, SBC, caller and callee country.</span></span> <span data-ttu-id="7e0bb-118">Wenn Sie an einem bestimmten SBC oder Land interessiert sind, werden Sie in der Lage sein, Änderungen an den Trends für den ausgewählten Zeitraum zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-118">If you're interested in a particular SBC or country, you'll be able to identify changes in trends over the selected time range.</span></span>
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Screenshot der im CQD PSTN Direct Routing-Bericht verfügbaren Filter":::
   
2. <span data-ttu-id="7e0bb-120">Nachvollziehen von Trends</span><span class="sxs-lookup"><span data-stu-id="7e0bb-120">Track trends</span></span>

    <span data-ttu-id="7e0bb-121">Die Trendanalyse ist wichtig, wenn Sie versuchen, die Dienstnutzung und Zuverlässigkeit zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-121">Trends analysis is essential when trying to understand service usage and reliability.</span></span> <span data-ttu-id="7e0bb-122">Stündliche Trends bieten einen Einblick in die tägliche Leistung, die bei der Ermittlung von echtzeitereignissen hilft.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-122">Hourly trends provide a close look at daily performance, which helps identify real-time incidents.</span></span> <span data-ttu-id="7e0bb-123">Mit den täglichen Trends können Sie Ihre Dienst Integrität aus einer langfristigen Perspektive sehen.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-123">Daily trends let you see your service health from a long-term perspective.</span></span> <span data-ttu-id="7e0bb-124">Es ist wichtig, in der Lage zu sein, zwischen diesen beiden Modi mit der entsprechenden Datengranularität zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-124">It's important to be able to shift between those two modes with appropriate data granularity.</span></span> <span data-ttu-id="7e0bb-125">Der CQD PSTN Direct Routing-Bericht bietet eine Übersicht über sechs Monats Trends, 7-und 30-Tage-Tagestrends sowie stündliche Trends, damit Sie die Leistung auf jeder Ebene analysieren können.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-125">The CQD PSTN Direct Routing report provides 6-month trends overview, 7- and 30-day daily trends, and hourly trends so you can analyze performance at each level.</span></span>
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Screenshot der Trenddiagramme in CQD PSTN Direct Routing-Bericht":::

3. <span data-ttu-id="7e0bb-127">Drillthrough zur SBC-oder Benutzerebene</span><span class="sxs-lookup"><span data-stu-id="7e0bb-127">Drill through to SBC or user level</span></span>

   <span data-ttu-id="7e0bb-128">Wir haben in CQD in vielen Datenkategorien eine Drill-Through-Funktion erstellt, mit der Sie die Verwendung oder Zuverlässigkeits Verteilung auf SBC-oder Benutzerebene schnell verstehen können.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-128">We've been building in drill-through capability on many data categories in CQD, which lets you quickly understand usage or reliability distribution at the SBC or user level.</span></span> <span data-ttu-id="7e0bb-129">Durch die Verwendung von Drill-Through können Sie Probleme schnell poinpoint und die Auswirkungen des realen Benutzers verstehen.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-129">By using drill through, you can quickly poinpoint issues and understand real user impact.</span></span> <span data-ttu-id="7e0bb-130">Die CQD PSTN Direct Routing-Berichtsfeatures durchlaufen die Metriken Dienstdetails und Netzwerk Effektivitäts Verhältnis.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-130">The CQD PSTN Direct Routing report features drill through on the Service Detail and Network Effectiveness Ratio metrics.</span></span> <span data-ttu-id="7e0bb-131">Klicken Sie auf den Datenpunkt, an dem Sie interessiert sind, um die Details auf SBC-oder Benutzerebene zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-131">Click the data point you're interested in to drill through to SBC- or user-level details.</span></span>
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Screenshot mit Drill-Through-Funktion auf einem Datenpunkt":::


## <a name="pstn-overview"></a><span data-ttu-id="7e0bb-133">PSTN-Übersicht</span><span class="sxs-lookup"><span data-stu-id="7e0bb-133">PSTN Overview</span></span>

<span data-ttu-id="7e0bb-134">Der CQD PSTN Direct-Routing Bericht enthält die folgenden Informationen zum Gesamtzustand des Diensts für die letzten 180 Tage.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-134">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="7e0bb-135">![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="7e0bb-135">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="7e0bb-136">Wenn Sie beispielsweise an der allgemeinen Nutzung und der Integrität für alle eingehenden Anrufe interessiert sind, die über SBC-ABC.BCA.adatum.biz mit uns als internes Land laufen, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="7e0bb-136">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="7e0bb-137">**Anrufen**</span><span class="sxs-lookup"><span data-stu-id="7e0bb-137">**Call Out**</span></span> | <span data-ttu-id="7e0bb-138">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="7e0bb-138">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="7e0bb-139">1</span><span class="sxs-lookup"><span data-stu-id="7e0bb-139">1</span></span>            | <span data-ttu-id="7e0bb-140">Sie können die Filter oben verwenden, um einen Drilldown durchführen und ByotIn als Anruftyp, ABC.BCA.contoso.com als Sitzungs Boarder-Controller und US als internes Land auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-140">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="7e0bb-141">2</span><span class="sxs-lookup"><span data-stu-id="7e0bb-141">2</span></span>            | <span data-ttu-id="7e0bb-142">Verwendungs Trend für die letzten 180 Tage.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-142">Usage trend for the past 180 days.</span></span> <span data-ttu-id="7e0bb-143">Sie finden den Verwendungs Detailbericht auf der Seite "Dienstdetails".</span><span class="sxs-lookup"><span data-stu-id="7e0bb-143">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="7e0bb-144">3</span><span class="sxs-lookup"><span data-stu-id="7e0bb-144">3</span></span>            | <span data-ttu-id="7e0bb-145">Nach Wahl Verzögerung, Latenz, Jitter und Paketverlust Trend für die letzten 180 Tage.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-145">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="7e0bb-146">Sie finden den Detailbericht auf der Seite Netzwerkparameter.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-146">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="7e0bb-147">4</span><span class="sxs-lookup"><span data-stu-id="7e0bb-147">4</span></span>            | <span data-ttu-id="7e0bb-148">Gleichzeitiger Anruf und Trend des täglichen aktiven Benutzers für die letzten 180 Tage.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-148">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="7e0bb-149">Dieses Diagramm kann Ihnen helfen, die maximale Lautstärke des Diensts zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-149">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="7e0bb-150">5</span><span class="sxs-lookup"><span data-stu-id="7e0bb-150">5</span></span>            | <span data-ttu-id="7e0bb-151">Der Grund für den oberen Anruf Ende hat die Servicequalität in den letzten 180 Tagen beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-151">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="7e0bb-152">Sie finden die Details zum Dienststatus auf der Seite Netzwerk effektives Verhältnis (ner).</span><span class="sxs-lookup"><span data-stu-id="7e0bb-152">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="7e0bb-153">Dienst Details</span><span class="sxs-lookup"><span data-stu-id="7e0bb-153">Service Details</span></span>

<span data-ttu-id="7e0bb-154">Auf dieser Seite werden die Trends für die Dienst Verwendung pro Tag und die Aufteilung der Benutzer Feedback nach geografischen Informationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-154">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="7e0bb-155">**Aufrufe für Gesamt Versuch –** Aufrufe für Gesamt Versuch in diesem Zeitraum, einschließlich Erfolg und fehlgeschlagener Anrufe</span><span class="sxs-lookup"><span data-stu-id="7e0bb-155">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="7e0bb-156">**Verbundene Anrufe insgesamt –** Gesamtzahl der verbundenen Anrufe in diesem Zeitraum</span><span class="sxs-lookup"><span data-stu-id="7e0bb-156">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="7e0bb-157">**Gesamtanzahl der Minuten –** Gesamt Minuten Verbrauch in diesem Zeitbereich</span><span class="sxs-lookup"><span data-stu-id="7e0bb-157">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="7e0bb-158">**Tägliche aktive Nutzer (Dau) –** Die Anzahl des täglichen aktiven Benutzers, der an diesem Tag mindestens einen verbundenen Anruf getätigt hat</span><span class="sxs-lookup"><span data-stu-id="7e0bb-158">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="7e0bb-159">**Gleichzeitige Anrufe –** Max. gleichzeitiger aktiver Anrufe in einer Minute</span><span class="sxs-lookup"><span data-stu-id="7e0bb-159">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="7e0bb-160">**Nutzer Feedback –** Die Punktzahl "meinen Anruf bewerten" stammt vom Nutzer.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-160">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="7e0bb-161">3-5 wird als guter Anruf angesehen.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-161">3-5 is considered as a good call.</span></span> <span data-ttu-id="7e0bb-162">1-2 wird als schlechter Anruf angesehen.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-162">1-2 is considered as a bad call.</span></span>

![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report2.png)

<span data-ttu-id="7e0bb-164">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7e0bb-164">For example:</span></span>

1.  <span data-ttu-id="7e0bb-165">Wenn die durchschnittliche Anrufdauer bei 02/14/2020 auf 0 fällt, können Sie zuerst überprüfen, ob die Anruflautstärke normal aussieht, und sehen, ob es eine große Diskrepanz zwischen Gesamt-Connect-anrufen und totalen Versuchs aufrufen gibt.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-165">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="7e0bb-166">Wechseln Sie dann zur Seite Netzwerk-Effektivitäts Rate, um aus Gründen des Anruf Fehlers zu investieren.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-166">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="7e0bb-167">Wenn in der Benutzer Feedback Karte steigende rote Punkte angezeigt werden, können Sie zur Seite Netzwerk-Effektivitäts Rate und Netzwerk Parameter wechseln, um festzustellen, ob es Anomalien gibt, und Sie können ein Ticket mit MS Service Desk auslösen.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-167">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="7e0bb-168">Netzwerk-Effektivitäts Rate</span><span class="sxs-lookup"><span data-stu-id="7e0bb-168">Network Effectiveness Ratio</span></span>

<span data-ttu-id="7e0bb-169">Dies ist die gleiche Metrik, die im allgemeinen Status-Dashboard angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-169">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="7e0bb-170">Sie können die Anzahl der stündlichen Unternehmen mit betroffenen Anrufdetails für beide Anruf Richtungen (eingehend/ausgehend) über das stündliche Netzwerk-Effektivitäts Verhältnis und das Grund Diagramm für das Ende des Anrufs nach unten prüfen.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-170">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="7e0bb-171">**Ner** -die Fähigkeit (%) eines Netzwerks, um Anrufe zu übermitteln, indem Sie die Anzahl der Anrufe im Vergleich zur Anzahl der Anrufe an einen Empfänger messen.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-171">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="7e0bb-172">**SIP-Antwortcode**– ein dreistelliger ganzzahliger Antwortcode zeigt den Anrufstatus an.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-172">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="7e0bb-173">**Microsoft Response Code**– ein Antwortcode, der von der Microsoft-Komponente gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-173">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="7e0bb-174">**Beschreibung** – die Grund Phase, die dem SIP-Antwortcode und dem Microsoft-Antwortcode entspricht.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-174">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="7e0bb-175">**Anzahl der betroffenen Anrufe** – die Gesamtzahl der Anrufe wurde während des ausgewählten Zeitbereichs beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-175">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="7e0bb-177">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7e0bb-177">For example:</span></span>

![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report4.png)

<span data-ttu-id="7e0bb-179">Wenn Sie täglich ein Bad auf 02/05/2020 haben, können Sie auf das Datum klicken, und andere Diagramme Zoomen auf das jeweilige Datum.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-179">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report5.png)

<span data-ttu-id="7e0bb-181">Ab dem guten prozentualen stündlichen Trend können Sie die DIP-Vorgänge rund um 21:00 finden.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-181">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="7e0bb-182">Klicken Sie dann erneut, um die Uhrzeit zu verkleinern, und überprüfen Sie die gewünschten Anruf Details, um zu sehen, wie viele Anrufe in dieser Stunde fehlschlugen und was die Gründe für das Anruf Ende sind.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-182">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="7e0bb-183">Sie können mit der selbst Behebung von Problemen bei SBC beginnen oder an Service Desk melden, wenn das Problem nicht mit SBC in Verbindung steht.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-183">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="7e0bb-184">Netzwerkparameter</span><span class="sxs-lookup"><span data-stu-id="7e0bb-184">Network Parameters</span></span>

<span data-ttu-id="7e0bb-185">Alle Netzwerkparameter werden von der direkten Routing Schnittstelle zum Session Border Controller gemessen.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-185">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="7e0bb-186">Informationen zu den empfohlenen Werten finden Sie unter [Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams](prepare-network.md)und untersuchen der empfohlenen Werte für den Kunden Rand zu Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-186">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="7e0bb-187">**Jitter** – ist das Millisekunden-Maß der Variation in der Verzögerungszeit für die Netzwerk Propagierung, die zwischen zwei Endpunkten mithilfe von RTCP (dem RTP-steuerelementprotokoll) berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-187">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="7e0bb-188">**Paketverlust** – ist ein Maß für ein Paket, das nicht ankommt; Sie wird zwischen zwei Endpunkten berechnet.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-188">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="7e0bb-189">**Latenz** – (auch als Roundtrip-Zeit bezeichnet) ist die Zeitdauer, die für das Senden eines Signals benötigt wird, sowie die Zeitdauer, die für die Empfangsbestätigung des Signals benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-189">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="7e0bb-190">Diese Zeitverzögerung besteht aus den Ausbreitungs Zeiten zwischen den beiden Punkten eines Signals.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-190">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report6.png)

<span data-ttu-id="7e0bb-192">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7e0bb-192">For example:</span></span>

<span data-ttu-id="7e0bb-193">Wenn Sie eine Spitze in einem der vier Diagramme (Latenz, Jitter, Paketverlust Rate, nach Wahl Verzögerung) für ein bestimmtes Datum sehen, beispielsweise Latenz auf 02/14/2020, klicken Sie auf den Datums Punkt.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-193">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="7e0bb-194">Und das stündliche Trenddiagramm unten wird aktualisiert, um die stündliche Zahl anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-194">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="7e0bb-195">Sie können das SBCS überprüfen oder ein Ticket mit MS Service Desk auslösen.</span><span class="sxs-lookup"><span data-stu-id="7e0bb-195">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="7e0bb-197">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7e0bb-197">Related topics</span></span>

[<span data-ttu-id="7e0bb-198">Verwenden von Power BI zum Analysieren von CQD-Daten für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7e0bb-198">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)

[<span data-ttu-id="7e0bb-199">Teams-Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="7e0bb-199">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)