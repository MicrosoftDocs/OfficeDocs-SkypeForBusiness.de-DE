---
title: 'Lync Server 2013: QoE-Berichte'
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
ms.openlocfilehash: 958c67b1b10b25e44805d2582ffe2e9fab575568
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="a9dd0-102">QoE-Berichte in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9dd0-102">QoE reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9dd0-103">_**Letztes Änderungsstand des Themas:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="a9dd0-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="a9dd0-104">QoE-Zusammenfassung/Trendberichte</span><span class="sxs-lookup"><span data-stu-id="a9dd0-104">QoE summary/trend reports</span></span>

<span data-ttu-id="a9dd0-105">Die QoE-Zusammenfassung/Trends-Berichte sind nützlich, um die Spitzennutzungszeiten zu ermitteln und die Medienqualität zu überprüfen, um sicherzustellen, dass die Netzwerkressourcen Ihrer Organisation ausreichen.</span><span class="sxs-lookup"><span data-stu-id="a9dd0-105">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="a9dd0-106">Ihre Organisation kann auch die zahlreichen Filter verwenden, die im Bericht zur Verfügung stehen, um Leistungsnummern für bestimmte Standorte, Client-und Gerätetypen und Server zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="a9dd0-106">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="a9dd0-107">QoE-Zusammenfassung/Trendberichte bestehen aus:</span><span class="sxs-lookup"><span data-stu-id="a9dd0-107">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="a9dd0-108">UC-zu-UC-Zusammenfassung/Trend Bericht</span><span class="sxs-lookup"><span data-stu-id="a9dd0-108">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="a9dd0-109">PSTN-Zusammenfassung/Trend Bericht</span><span class="sxs-lookup"><span data-stu-id="a9dd0-109">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="a9dd0-110">Konferenz Zusammenfassung/Trend Bericht</span><span class="sxs-lookup"><span data-stu-id="a9dd0-110">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="a9dd0-111">QoE-Leistungsberichte</span><span class="sxs-lookup"><span data-stu-id="a9dd0-111">QoE performance reports</span></span>

<span data-ttu-id="a9dd0-112">QoE-Leistungsberichte enthalten Details zu den drei Berichten, die sich auf die QoE-Leistung von Vermittlungsservern, A/V-Konferenzservern und Endpunkt Standorten konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="a9dd0-112">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="a9dd0-113">Leistungsbericht für Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="a9dd0-113">Mediation server performance report</span></span>

<span data-ttu-id="a9dd0-114">Im Bericht Vermittlungsserver Leistung werden die Metriken aufgelistet, die von einer oder mehreren Vermittlungs Vorgängen während des angegebenen Zeitraums erreicht wurden.</span><span class="sxs-lookup"><span data-stu-id="a9dd0-114">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="a9dd0-115">Die Metriken für das Unified Communications (UC)-zu-Vermittlungsserver-Bein und das Vermittlungsserver-zu-Gateway-Bein jedes Anrufs werden separat angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9dd0-115">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="a9dd0-116">Verwenden Sie diesen Bericht, um den Umfang und die Leistung der verschiedenen Vermittlungsserver Ihrer Organisation zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="a9dd0-116">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="a9dd0-117">Für jede Vermittlungsserver (und für jedes Anruf Bein) wird im Bericht Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a9dd0-117">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="a9dd0-118">Anzahl der Anrufe</span><span class="sxs-lookup"><span data-stu-id="a9dd0-118">Number of calls</span></span>

  - <span data-ttu-id="a9dd0-119">Paketverlust</span><span class="sxs-lookup"><span data-stu-id="a9dd0-119">Packet Loss</span></span>

  - <span data-ttu-id="a9dd0-120">Round Trip-Zeit</span><span class="sxs-lookup"><span data-stu-id="a9dd0-120">Round Trip Time</span></span>

  - <span data-ttu-id="a9dd0-121">Jitter</span><span class="sxs-lookup"><span data-stu-id="a9dd0-121">Jitter</span></span>

  - <span data-ttu-id="a9dd0-122">Gesprächs Mittel-Meinungs Bewertung (MOS)</span><span class="sxs-lookup"><span data-stu-id="a9dd0-122">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="a9dd0-123">Senden von MOS</span><span class="sxs-lookup"><span data-stu-id="a9dd0-123">Sending MOS</span></span>

  - <span data-ttu-id="a9dd0-124">Abhören von MOS</span><span class="sxs-lookup"><span data-stu-id="a9dd0-124">Listening MOS</span></span>

  - <span data-ttu-id="a9dd0-125">Netzwerk-Mos</span><span class="sxs-lookup"><span data-stu-id="a9dd0-125">Network MOS</span></span>

  - <span data-ttu-id="a9dd0-126">Netzwerk-Mos-Beeinträchtigung</span><span class="sxs-lookup"><span data-stu-id="a9dd0-126">Network MOS Degradation</span></span>

  - <span data-ttu-id="a9dd0-127">Echo-Rückgabe</span><span class="sxs-lookup"><span data-stu-id="a9dd0-127">Echo Return</span></span>

  - <span data-ttu-id="a9dd0-128">Signal Pegel</span><span class="sxs-lookup"><span data-stu-id="a9dd0-128">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="a9dd0-129">Leistungsbericht A/V-Konferenzserver</span><span class="sxs-lookup"><span data-stu-id="a9dd0-129">A/V conferencing server performance report</span></span>

<span data-ttu-id="a9dd0-130">Der Bericht über A/V-Konferenzserver Leistung enthält eine Liste der Metriken, die von einem oder mehreren A/V-Konferenzservern während des angegebenen Zeitraums erreicht wurden.</span><span class="sxs-lookup"><span data-stu-id="a9dd0-130">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="a9dd0-131">Dieser Bericht kann verwendet werden, um den Umfang und die Leistung der verschiedenen A/V-Konferenzserver Ihrer Organisation zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="a9dd0-131">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="a9dd0-132">Ihre Organisation kann den Bericht auch isolieren, sodass nur die Benutzeroberfläche für bestimmte Clienttypen wie lync-Clients oder PSTN-Clients angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a9dd0-132">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="a9dd0-133">Für jeden A/V-Konferenzserver wird im Bericht Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a9dd0-133">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="a9dd0-134">Anzahl von Konferenzen</span><span class="sxs-lookup"><span data-stu-id="a9dd0-134">Number of conferences</span></span>

  - <span data-ttu-id="a9dd0-135">Paketverlust</span><span class="sxs-lookup"><span data-stu-id="a9dd0-135">Packet Loss</span></span>

  - <span data-ttu-id="a9dd0-136">Round Trip-Zeit</span><span class="sxs-lookup"><span data-stu-id="a9dd0-136">Round Trip Time</span></span>

  - <span data-ttu-id="a9dd0-137">Jitter</span><span class="sxs-lookup"><span data-stu-id="a9dd0-137">Jitter</span></span>

  - <span data-ttu-id="a9dd0-138">Gesprächs Mittel-Meinungs Bewertung (MOS)</span><span class="sxs-lookup"><span data-stu-id="a9dd0-138">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="a9dd0-139">Senden von MOS</span><span class="sxs-lookup"><span data-stu-id="a9dd0-139">Sending MOS</span></span>

  - <span data-ttu-id="a9dd0-140">Abhören von MOS</span><span class="sxs-lookup"><span data-stu-id="a9dd0-140">Listening MOS</span></span>

  - <span data-ttu-id="a9dd0-141">Netzwerk-Mos</span><span class="sxs-lookup"><span data-stu-id="a9dd0-141">Network MOS</span></span>

  - <span data-ttu-id="a9dd0-142">Netzwerk-Mos-Beeinträchtigung</span><span class="sxs-lookup"><span data-stu-id="a9dd0-142">Network MOS Degradation</span></span>

  - <span data-ttu-id="a9dd0-143">Echo-Rückgabe</span><span class="sxs-lookup"><span data-stu-id="a9dd0-143">Echo Return</span></span>

  - <span data-ttu-id="a9dd0-144">Signal Pegel</span><span class="sxs-lookup"><span data-stu-id="a9dd0-144">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="a9dd0-145">Standortbasierter Leistungsbericht</span><span class="sxs-lookup"><span data-stu-id="a9dd0-145">Location-based performance report</span></span>

<span data-ttu-id="a9dd0-146">Der standortbasierte Leistungsbericht enthält eine Liste der Netzwerkstandorte, und für jeden Standort wird die Anzahl der Anrufe in jedem vorab festgelegten Qualitätsbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9dd0-146">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="a9dd0-147">Das Ziel dieses Berichts besteht darin, Einblicke in die Medienqualität des Großteils der Telefonanrufe Ihrer Organisation für verschiedene Standorte zu geben, damit Sie schlecht durch führ Ende Standorte identifizieren und die verschiedenen Grade der Medienqualität in Ihrer Organisation anzeigen können. unterschiedliche Standorte.</span><span class="sxs-lookup"><span data-stu-id="a9dd0-147">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="a9dd0-148">Beim Anzeigen des Berichts werden verschiedene metrische Tabellen angezeigt – eine Tabelle für jede Metrik, für die Ihre Organisation einen Bericht beschließt.</span><span class="sxs-lookup"><span data-stu-id="a9dd0-148">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="a9dd0-149">Für diesen Bericht stehen Ihnen die folgenden Metriken zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="a9dd0-149">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="a9dd0-150">Gesprächs Mittel-Meinungs Bewertung (MOS)</span><span class="sxs-lookup"><span data-stu-id="a9dd0-150">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="a9dd0-151">Netzwerk-Mos</span><span class="sxs-lookup"><span data-stu-id="a9dd0-151">Network MOS</span></span>

  - <span data-ttu-id="a9dd0-152">Netzwerk-Mos-Beeinträchtigung</span><span class="sxs-lookup"><span data-stu-id="a9dd0-152">Network MOS Degradation</span></span>

  - <span data-ttu-id="a9dd0-153">Senden von MOS</span><span class="sxs-lookup"><span data-stu-id="a9dd0-153">Sending MOS</span></span>

  - <span data-ttu-id="a9dd0-154">Abhören von MOS</span><span class="sxs-lookup"><span data-stu-id="a9dd0-154">Listening MOS</span></span>

  - <span data-ttu-id="a9dd0-155">Paketverlust</span><span class="sxs-lookup"><span data-stu-id="a9dd0-155">Packet Loss</span></span>

  - <span data-ttu-id="a9dd0-156">Jitter</span><span class="sxs-lookup"><span data-stu-id="a9dd0-156">Jitter</span></span>

  - <span data-ttu-id="a9dd0-157">Wartezeit</span><span class="sxs-lookup"><span data-stu-id="a9dd0-157">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

