---
title: 'Lync Server 2013: QoE-Berichte'
description: 'Lync Server 2013: QoE-Berichte.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE reports
ms:assetid: 49c827af-b8dd-4c6e-b0dc-b4bc6d60e9a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720913(v=OCS.15)
ms:contentKeyID: 63969601
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55965d246b7f0ddd71eaeeec99d218eaf8819c2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571401"
---
# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="01cf6-103">QoE-Berichte in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01cf6-103">QoE reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01cf6-104">_**Letztes Änderungsstand des Themas:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="01cf6-104">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="01cf6-105">QoE-Zusammenfassung/Trendberichte</span><span class="sxs-lookup"><span data-stu-id="01cf6-105">QoE summary/trend reports</span></span>

<span data-ttu-id="01cf6-106">Die QoE-Zusammenfassung/Trends-Berichte sind nützlich, um die Spitzennutzungszeiten zu ermitteln und die Medienqualität zu überprüfen, um sicherzustellen, dass die Netzwerkressourcen Ihrer Organisation ausreichen.</span><span class="sxs-lookup"><span data-stu-id="01cf6-106">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="01cf6-107">Ihre Organisation kann auch die zahlreichen Filter verwenden, die im Bericht zur Verfügung stehen, um Leistungsnummern für bestimmte Standorte, Client-und Gerätetypen und Server zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="01cf6-107">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="01cf6-108">QoE-Zusammenfassung/Trendberichte bestehen aus:</span><span class="sxs-lookup"><span data-stu-id="01cf6-108">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="01cf6-109">UC-zu-UC-Zusammenfassung/Trend Bericht</span><span class="sxs-lookup"><span data-stu-id="01cf6-109">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="01cf6-110">PSTN-Zusammenfassung/Trend Bericht</span><span class="sxs-lookup"><span data-stu-id="01cf6-110">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="01cf6-111">Konferenz Zusammenfassung/Trend Bericht</span><span class="sxs-lookup"><span data-stu-id="01cf6-111">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="01cf6-112">QoE-Leistungsberichte</span><span class="sxs-lookup"><span data-stu-id="01cf6-112">QoE performance reports</span></span>

<span data-ttu-id="01cf6-113">QoE-Leistungsberichte enthalten Details zu den drei Berichten, die sich auf die QoE-Leistung von Vermittlungsservern, A/V-Konferenzservern und Endpunkt Standorten konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="01cf6-113">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="01cf6-114">Leistungsbericht für Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="01cf6-114">Mediation server performance report</span></span>

<span data-ttu-id="01cf6-115">Im Bericht Vermittlungsserver Leistung werden die Metriken aufgelistet, die von einer oder mehreren Vermittlungs Vorgängen während des angegebenen Zeitraums erreicht wurden.</span><span class="sxs-lookup"><span data-stu-id="01cf6-115">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="01cf6-116">Die Metriken für das Unified Communications (UC)-zu-Vermittlungsserver-Bein und das Vermittlungsserver-zu-Gateway-Bein jedes Anrufs werden separat angezeigt.</span><span class="sxs-lookup"><span data-stu-id="01cf6-116">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="01cf6-117">Verwenden Sie diesen Bericht, um den Umfang und die Leistung der verschiedenen Vermittlungsserver Ihrer Organisation zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="01cf6-117">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="01cf6-118">Für jede Vermittlungsserver (und für jedes Anruf Bein) wird im Bericht Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="01cf6-118">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="01cf6-119">Anzahl der Anrufe</span><span class="sxs-lookup"><span data-stu-id="01cf6-119">Number of calls</span></span>

  - <span data-ttu-id="01cf6-120">Paketverlust</span><span class="sxs-lookup"><span data-stu-id="01cf6-120">Packet Loss</span></span>

  - <span data-ttu-id="01cf6-121">Round Trip-Zeit</span><span class="sxs-lookup"><span data-stu-id="01cf6-121">Round Trip Time</span></span>

  - <span data-ttu-id="01cf6-122">Jitter</span><span class="sxs-lookup"><span data-stu-id="01cf6-122">Jitter</span></span>

  - <span data-ttu-id="01cf6-123">Gesprächs Mittel-Meinungs Bewertung (MOS)</span><span class="sxs-lookup"><span data-stu-id="01cf6-123">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="01cf6-124">Senden von MOS</span><span class="sxs-lookup"><span data-stu-id="01cf6-124">Sending MOS</span></span>

  - <span data-ttu-id="01cf6-125">Abhören von MOS</span><span class="sxs-lookup"><span data-stu-id="01cf6-125">Listening MOS</span></span>

  - <span data-ttu-id="01cf6-126">Netzwerk-Mos</span><span class="sxs-lookup"><span data-stu-id="01cf6-126">Network MOS</span></span>

  - <span data-ttu-id="01cf6-127">Netzwerk-Mos-Beeinträchtigung</span><span class="sxs-lookup"><span data-stu-id="01cf6-127">Network MOS Degradation</span></span>

  - <span data-ttu-id="01cf6-128">Echo-Rückgabe</span><span class="sxs-lookup"><span data-stu-id="01cf6-128">Echo Return</span></span>

  - <span data-ttu-id="01cf6-129">Signal Pegel</span><span class="sxs-lookup"><span data-stu-id="01cf6-129">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="01cf6-130">Leistungsbericht A/V-Konferenzserver</span><span class="sxs-lookup"><span data-stu-id="01cf6-130">A/V conferencing server performance report</span></span>

<span data-ttu-id="01cf6-131">Der Bericht über A/V-Konferenzserver Leistung enthält eine Liste der Metriken, die von einem oder mehreren A/V-Konferenzservern während des angegebenen Zeitraums erreicht wurden.</span><span class="sxs-lookup"><span data-stu-id="01cf6-131">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="01cf6-132">Dieser Bericht kann verwendet werden, um den Umfang und die Leistung der verschiedenen A/V-Konferenzserver Ihrer Organisation zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="01cf6-132">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="01cf6-133">Ihre Organisation kann den Bericht auch isolieren, sodass nur die Benutzeroberfläche für bestimmte Clienttypen wie lync-Clients oder PSTN-Clients angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="01cf6-133">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="01cf6-134">Für jeden A/V-Konferenzserver wird im Bericht Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="01cf6-134">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="01cf6-135">Anzahl von Konferenzen</span><span class="sxs-lookup"><span data-stu-id="01cf6-135">Number of conferences</span></span>

  - <span data-ttu-id="01cf6-136">Paketverlust</span><span class="sxs-lookup"><span data-stu-id="01cf6-136">Packet Loss</span></span>

  - <span data-ttu-id="01cf6-137">Round Trip-Zeit</span><span class="sxs-lookup"><span data-stu-id="01cf6-137">Round Trip Time</span></span>

  - <span data-ttu-id="01cf6-138">Jitter</span><span class="sxs-lookup"><span data-stu-id="01cf6-138">Jitter</span></span>

  - <span data-ttu-id="01cf6-139">Gesprächs Mittel-Meinungs Bewertung (MOS)</span><span class="sxs-lookup"><span data-stu-id="01cf6-139">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="01cf6-140">Senden von MOS</span><span class="sxs-lookup"><span data-stu-id="01cf6-140">Sending MOS</span></span>

  - <span data-ttu-id="01cf6-141">Abhören von MOS</span><span class="sxs-lookup"><span data-stu-id="01cf6-141">Listening MOS</span></span>

  - <span data-ttu-id="01cf6-142">Netzwerk-Mos</span><span class="sxs-lookup"><span data-stu-id="01cf6-142">Network MOS</span></span>

  - <span data-ttu-id="01cf6-143">Netzwerk-Mos-Beeinträchtigung</span><span class="sxs-lookup"><span data-stu-id="01cf6-143">Network MOS Degradation</span></span>

  - <span data-ttu-id="01cf6-144">Echo-Rückgabe</span><span class="sxs-lookup"><span data-stu-id="01cf6-144">Echo Return</span></span>

  - <span data-ttu-id="01cf6-145">Signal Pegel</span><span class="sxs-lookup"><span data-stu-id="01cf6-145">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="01cf6-146">Standortbasierter Leistungsbericht</span><span class="sxs-lookup"><span data-stu-id="01cf6-146">Location-based performance report</span></span>

<span data-ttu-id="01cf6-147">Der Bericht über die Location-Based Leistung enthält eine Liste der Netzwerkstandorte und für jeden Standort die Anzahl der Anrufe in jedem vorab festgelegten Qualitätsbereich.</span><span class="sxs-lookup"><span data-stu-id="01cf6-147">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="01cf6-148">Das Ziel dieses Berichts besteht darin, Einblicke in die Medienqualität des Großteils der Telefonanrufe Ihrer Organisation für verschiedene Standorte zu geben, damit Sie schlecht darstellende Standorte identifizieren und die unterschiedlichen Grade der Medienqualität in den verschiedenen Standorten Ihrer Organisation anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="01cf6-148">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="01cf6-149">Beim Anzeigen des Berichts werden verschiedene metrische Tabellen angezeigt – eine Tabelle für jede Metrik, für die Ihre Organisation einen Bericht beschließt.</span><span class="sxs-lookup"><span data-stu-id="01cf6-149">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="01cf6-150">Für diesen Bericht stehen Ihnen die folgenden Metriken zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="01cf6-150">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="01cf6-151">Gesprächs Mittel-Meinungs Bewertung (MOS)</span><span class="sxs-lookup"><span data-stu-id="01cf6-151">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="01cf6-152">Netzwerk-Mos</span><span class="sxs-lookup"><span data-stu-id="01cf6-152">Network MOS</span></span>

  - <span data-ttu-id="01cf6-153">Netzwerk-Mos-Beeinträchtigung</span><span class="sxs-lookup"><span data-stu-id="01cf6-153">Network MOS Degradation</span></span>

  - <span data-ttu-id="01cf6-154">Senden von MOS</span><span class="sxs-lookup"><span data-stu-id="01cf6-154">Sending MOS</span></span>

  - <span data-ttu-id="01cf6-155">Abhören von MOS</span><span class="sxs-lookup"><span data-stu-id="01cf6-155">Listening MOS</span></span>

  - <span data-ttu-id="01cf6-156">Paketverlust</span><span class="sxs-lookup"><span data-stu-id="01cf6-156">Packet Loss</span></span>

  - <span data-ttu-id="01cf6-157">Jitter</span><span class="sxs-lookup"><span data-stu-id="01cf6-157">Jitter</span></span>

  - <span data-ttu-id="01cf6-158">Wartezeit</span><span class="sxs-lookup"><span data-stu-id="01cf6-158">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

