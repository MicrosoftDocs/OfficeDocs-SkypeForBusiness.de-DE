---
title: Verwenden des CQD PSTN Direct Routing-Berichts
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
description: Verwenden Sie den CQD PSTN Direct-Routing Bericht, um PSTN-Anrufe in Microsoft Teams zu überwachen und zu beheben.
ms.openlocfilehash: 32d91d56e51c5706c3e460029312f3b6bb6948c3
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559488"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="f0780-103">Verwenden des CQD PSTN Direct Routing-Berichts</span><span class="sxs-lookup"><span data-stu-id="f0780-103">Using the CQD PSTN Direct Routing Report</span></span>

<span data-ttu-id="f0780-104">Neu im März 2020 haben wir unseren herunterladbaren [Power BI-Abfragevorlagen für CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)einen CQD PSTN Direct-Routing Bericht hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f0780-104">New in March 2020, we've added a CQD PSTN Direct Routing Report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="f0780-105">Der CQD PSTN Direct Routing-Bericht hilft Kunden, die Nutzungsmuster und die Qualität ihrer PSTN-Dienste zu verstehen, die Informationen zu Ihrem SBC, dem Telefoniedienst, den Netzwerkparametern sowie Details zur Netzwerk Effektivitäts Rate und zur Verwendung der Dienst.</span><span class="sxs-lookup"><span data-stu-id="f0780-105">The CQD PSTN Direct Routing Report helps customers to understand the usage patterns and quality of their PSTN services monitor information about your SBC, the telephony service, the network parameters, and Network Effectiveness Ratio details and usage of the service.</span></span> <span data-ttu-id="f0780-106">Diese Informationen können Ihnen helfen, Probleme zu erkennen, einschließlich des Grunds für gelöschte Anrufe.</span><span class="sxs-lookup"><span data-stu-id="f0780-106">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="f0780-107">So können Sie beispielsweise feststellen, wann die Lautstärke sinkt, wie viele Anrufe von welchem Grund betroffen werden.</span><span class="sxs-lookup"><span data-stu-id="f0780-107">For example, you will be able to know when volume drops, how many calls get affected by what reason.</span></span>

<span data-ttu-id="f0780-108">Der CQD PSTN Direct Routing-Bericht besteht aus vier Abschnitten:</span><span class="sxs-lookup"><span data-stu-id="f0780-108">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="f0780-109">PSTN-Übersicht</span><span class="sxs-lookup"><span data-stu-id="f0780-109">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="f0780-110">Dienst Details</span><span class="sxs-lookup"><span data-stu-id="f0780-110">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="f0780-111">Netzwerk-Effektivitäts Rate</span><span class="sxs-lookup"><span data-stu-id="f0780-111">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="f0780-112">Netzwerkparameter</span><span class="sxs-lookup"><span data-stu-id="f0780-112">Network Parameters</span></span>](#network-parameters)

## <a name="pstn-overview"></a><span data-ttu-id="f0780-113">PSTN-Übersicht</span><span class="sxs-lookup"><span data-stu-id="f0780-113">PSTN Overview</span></span>

<span data-ttu-id="f0780-114">Der CQD PSTN Direct-Routing Bericht enthält die folgenden Informationen zum Gesamtzustand des Diensts für die letzten 180 Tage.</span><span class="sxs-lookup"><span data-stu-id="f0780-114">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="f0780-115">![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="f0780-115">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="f0780-116">Wenn Sie beispielsweise an der allgemeinen Nutzung und der Integrität für alle eingehenden Anrufe interessiert sind, die über SBC-ABC.BCA.adatum.biz mit uns als internes Land laufen, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="f0780-116">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="f0780-117">**Anrufen**</span><span class="sxs-lookup"><span data-stu-id="f0780-117">**Call Out**</span></span> | <span data-ttu-id="f0780-118">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f0780-118">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="f0780-119">1</span><span class="sxs-lookup"><span data-stu-id="f0780-119">1</span></span>            | <span data-ttu-id="f0780-120">Sie können die Filter oben verwenden, um einen Drilldown durchführen und ByotIn als Anruftyp, ABC.BCA.contoso.com als Sitzungs Boarder-Controller und US als internes Land auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f0780-120">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="f0780-121">2</span><span class="sxs-lookup"><span data-stu-id="f0780-121">2</span></span>            | <span data-ttu-id="f0780-122">Verwendungs Trend für die letzten 180 Tage.</span><span class="sxs-lookup"><span data-stu-id="f0780-122">Usage trend for the past 180 days.</span></span> <span data-ttu-id="f0780-123">Sie finden den Verwendungs Detailbericht auf der Seite "Dienstdetails".</span><span class="sxs-lookup"><span data-stu-id="f0780-123">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="f0780-124">3</span><span class="sxs-lookup"><span data-stu-id="f0780-124">3</span></span>            | <span data-ttu-id="f0780-125">Nach Wahl Verzögerung, Latenz, Jitter und Paketverlust Trend für die letzten 180 Tage.</span><span class="sxs-lookup"><span data-stu-id="f0780-125">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="f0780-126">Sie finden den Detailbericht auf der Seite Netzwerkparameter.</span><span class="sxs-lookup"><span data-stu-id="f0780-126">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="f0780-127">4</span><span class="sxs-lookup"><span data-stu-id="f0780-127">4</span></span>            | <span data-ttu-id="f0780-128">Gleichzeitiger Anruf und Trend des täglichen aktiven Benutzers für die letzten 180 Tage.</span><span class="sxs-lookup"><span data-stu-id="f0780-128">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="f0780-129">Dieses Diagramm kann Ihnen helfen, die maximale Lautstärke des Diensts zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="f0780-129">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="f0780-130">5</span><span class="sxs-lookup"><span data-stu-id="f0780-130">5</span></span>            | <span data-ttu-id="f0780-131">Der Grund für den oberen Anruf Ende hat die Servicequalität in den letzten 180 Tagen beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="f0780-131">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="f0780-132">Sie finden die Details zum Dienststatus auf der Seite Netzwerk effektives Verhältnis (ner).</span><span class="sxs-lookup"><span data-stu-id="f0780-132">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="f0780-133">Dienst Details</span><span class="sxs-lookup"><span data-stu-id="f0780-133">Service Details</span></span>

<span data-ttu-id="f0780-134">Auf dieser Seite werden die Trends für die Dienst Verwendung pro Tag und die Aufteilung der Benutzer Feedback nach geografischen Informationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f0780-134">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="f0780-135">**Aufrufe für Gesamt Versuch –** Aufrufe für Gesamt Versuch in diesem Zeitraum, einschließlich Erfolg und fehlgeschlagener Anrufe</span><span class="sxs-lookup"><span data-stu-id="f0780-135">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="f0780-136">**Verbundene Anrufe insgesamt –** Gesamtzahl der verbundenen Anrufe in diesem Zeitraum</span><span class="sxs-lookup"><span data-stu-id="f0780-136">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="f0780-137">**Gesamtanzahl der Minuten –** Gesamt Minuten Verbrauch in diesem Zeitbereich</span><span class="sxs-lookup"><span data-stu-id="f0780-137">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="f0780-138">**Tägliche aktive Nutzer (Dau) –** Die Anzahl des täglichen aktiven Benutzers, der an diesem Tag mindestens einen verbundenen Anruf getätigt hat</span><span class="sxs-lookup"><span data-stu-id="f0780-138">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="f0780-139">**Gleichzeitige Anrufe –** Max. gleichzeitiger aktiver Anrufe in einer Minute</span><span class="sxs-lookup"><span data-stu-id="f0780-139">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="f0780-140">**Nutzer Feedback –** Die Punktzahl "meinen Anruf bewerten" stammt vom Nutzer.</span><span class="sxs-lookup"><span data-stu-id="f0780-140">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="f0780-141">3-5 wird als guter Anruf angesehen.</span><span class="sxs-lookup"><span data-stu-id="f0780-141">3-5 is considered as a good call.</span></span> <span data-ttu-id="f0780-142">1-2 wird als schlechter Anruf angesehen.</span><span class="sxs-lookup"><span data-stu-id="f0780-142">1-2 is considered as a bad call.</span></span>

![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report2.png)

<span data-ttu-id="f0780-144">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f0780-144">For example:</span></span>

1.  <span data-ttu-id="f0780-145">Wenn die durchschnittliche Anrufdauer bei 02/14/2020 auf 0 fällt, können Sie zuerst überprüfen, ob die Anruflautstärke normal aussieht, und sehen, ob es eine große Diskrepanz zwischen Gesamt-Connect-anrufen und totalen Versuchs aufrufen gibt.</span><span class="sxs-lookup"><span data-stu-id="f0780-145">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="f0780-146">Wechseln Sie dann zur Seite Netzwerk-Effektivitäts Rate, um aus Gründen des Anruf Fehlers zu investieren.</span><span class="sxs-lookup"><span data-stu-id="f0780-146">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="f0780-147">Wenn in der Benutzer Feedback Karte steigende rote Punkte angezeigt werden, können Sie zur Seite Netzwerk-Effektivitäts Rate und Netzwerk Parameter wechseln, um festzustellen, ob es Anomalien gibt, und Sie können ein Ticket mit MS Service Desk auslösen.</span><span class="sxs-lookup"><span data-stu-id="f0780-147">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="f0780-148">Netzwerk-Effektivitäts Rate</span><span class="sxs-lookup"><span data-stu-id="f0780-148">Network Effectiveness Ratio</span></span>

<span data-ttu-id="f0780-149">Dies ist die gleiche Metrik, die im allgemeinen Status-Dashboard angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f0780-149">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="f0780-150">Sie können die Anzahl der stündlichen Unternehmen mit betroffenen Anrufdetails für beide Anruf Richtungen (eingehend/ausgehend) über das stündliche Netzwerk-Effektivitäts Verhältnis und das Grund Diagramm für das Ende des Anrufs nach unten prüfen.</span><span class="sxs-lookup"><span data-stu-id="f0780-150">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="f0780-151">**Ner** -die Fähigkeit (%) eines Netzwerks, um Anrufe zu übermitteln, indem Sie die Anzahl der Anrufe im Vergleich zur Anzahl der Anrufe an einen Empfänger messen.</span><span class="sxs-lookup"><span data-stu-id="f0780-151">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="f0780-152">**SIP-Antwortcode**– ein dreistelliger ganzzahliger Antwortcode zeigt den Anrufstatus an.</span><span class="sxs-lookup"><span data-stu-id="f0780-152">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="f0780-153">**Microsoft Response Code**– ein Antwortcode, der von der Microsoft-Komponente gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="f0780-153">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="f0780-154">**Beschreibung** – die Grund Phase, die dem SIP-Antwortcode und dem Microsoft-Antwortcode entspricht.</span><span class="sxs-lookup"><span data-stu-id="f0780-154">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="f0780-155">**Anzahl der betroffenen Anrufe** – die Gesamtzahl der Anrufe wurde während des ausgewählten Zeitbereichs beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="f0780-155">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="f0780-157">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f0780-157">For example:</span></span>

![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report4.png)

<span data-ttu-id="f0780-159">Wenn Sie täglich ein Bad auf 02/05/2020 haben, können Sie auf das Datum klicken, und andere Diagramme Zoomen auf das jeweilige Datum.</span><span class="sxs-lookup"><span data-stu-id="f0780-159">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report5.png)

<span data-ttu-id="f0780-161">Ab dem guten prozentualen stündlichen Trend können Sie die DIP-Vorgänge rund um 21:00 finden.</span><span class="sxs-lookup"><span data-stu-id="f0780-161">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="f0780-162">Klicken Sie dann erneut, um die Uhrzeit zu verkleinern, und überprüfen Sie die gewünschten Anruf Details, um zu sehen, wie viele Anrufe in dieser Stunde fehlschlugen und was die Gründe für das Anruf Ende sind.</span><span class="sxs-lookup"><span data-stu-id="f0780-162">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="f0780-163">Sie können mit der selbst Behebung von Problemen bei SBC beginnen oder an Service Desk melden, wenn das Problem nicht mit SBC in Verbindung steht.</span><span class="sxs-lookup"><span data-stu-id="f0780-163">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="f0780-164">Netzwerkparameter</span><span class="sxs-lookup"><span data-stu-id="f0780-164">Network Parameters</span></span>

<span data-ttu-id="f0780-165">Alle Netzwerkparameter werden von der direkten Routing Schnittstelle zum Session Border Controller gemessen.</span><span class="sxs-lookup"><span data-stu-id="f0780-165">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="f0780-166">Informationen zu den empfohlenen Werten finden Sie unter [Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams](prepare-network.md)und untersuchen der empfohlenen Werte für den Kunden Rand zu Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="f0780-166">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="f0780-167">**Jitter** – ist das Millisekunden-Maß der Variation in der Verzögerungszeit für die Netzwerk Propagierung, die zwischen zwei Endpunkten mithilfe von RTCP (dem RTP-steuerelementprotokoll) berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="f0780-167">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="f0780-168">**Paketverlust** – ist ein Maß für ein Paket, das nicht ankommt; Sie wird zwischen zwei Endpunkten berechnet.</span><span class="sxs-lookup"><span data-stu-id="f0780-168">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="f0780-169">**Latenz** – (auch als Roundtrip-Zeit bezeichnet) ist die Zeitdauer, die für das Senden eines Signals benötigt wird, sowie die Zeitdauer, die für die Empfangsbestätigung des Signals benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="f0780-169">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="f0780-170">Diese Zeitverzögerung besteht aus den Ausbreitungs Zeiten zwischen den beiden Punkten eines Signals.</span><span class="sxs-lookup"><span data-stu-id="f0780-170">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report6.png)

<span data-ttu-id="f0780-172">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f0780-172">For example:</span></span>

<span data-ttu-id="f0780-173">Wenn Sie eine Spitze in einem der vier Diagramme (Latenz, Jitter, Paketverlust Rate, nach Wahl Verzögerung) für ein bestimmtes Datum sehen, beispielsweise Latenz auf 02/14/2020, klicken Sie auf den Datums Punkt.</span><span class="sxs-lookup"><span data-stu-id="f0780-173">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="f0780-174">Und das stündliche Trenddiagramm unten wird aktualisiert, um die stündliche Zahl anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f0780-174">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="f0780-175">Sie können das SBCS überprüfen oder ein Ticket mit MS Service Desk auslösen.</span><span class="sxs-lookup"><span data-stu-id="f0780-175">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![Screenshot: PSTN-CQD-Bericht](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="f0780-177">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f0780-177">Related topics</span></span>

[<span data-ttu-id="f0780-178">Verwenden von Power BI zum Analysieren von CQD-Daten für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f0780-178">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)