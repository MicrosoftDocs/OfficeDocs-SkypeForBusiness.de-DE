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
ms.openlocfilehash: 9eead17e9cd08267f941d80cb25460f4d456d896
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="3da52-102">QoE-Berichte in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3da52-102">QoE reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3da52-103">_**Letztes Änderungsdatum des Themas:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="3da52-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="3da52-104">QoE-Zusammenfassung/Trendberichte</span><span class="sxs-lookup"><span data-stu-id="3da52-104">QoE summary/trend reports</span></span>

<span data-ttu-id="3da52-105">Die Berichte QoE-Zusammenfassung/Trends sind hilfreich, um die Spitzenzeiten für die Nutzung zu ermitteln und die Medienqualität in diesen Zeiten zu untersuchen, um sicherzustellen, dass die Netzwerkressourcen Ihrer Organisation ausreichend sind.</span><span class="sxs-lookup"><span data-stu-id="3da52-105">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="3da52-106">Ihre Organisation kann auch die zahlreichen im Bericht verfügbaren Filter verwenden, um Leistungsnummern für bestimmte Speicherorte, Client-und Gerätetypen und Server zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="3da52-106">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="3da52-107">QoE-Zusammenfassung/Trendberichte bestehen aus:</span><span class="sxs-lookup"><span data-stu-id="3da52-107">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="3da52-108">UC-zu-UC-Zusammenfassung/Trend Bericht</span><span class="sxs-lookup"><span data-stu-id="3da52-108">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="3da52-109">PSTN-Zusammenfassung/Trend Bericht</span><span class="sxs-lookup"><span data-stu-id="3da52-109">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="3da52-110">Konferenz Zusammenfassung/Trend Bericht</span><span class="sxs-lookup"><span data-stu-id="3da52-110">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="3da52-111">QoE-Leistungsberichte</span><span class="sxs-lookup"><span data-stu-id="3da52-111">QoE performance reports</span></span>

<span data-ttu-id="3da52-112">QoE-Leistungsberichte bieten Details zu den drei Berichten, die sich auf die QoE-Leistung von Mediations Servern, A/V-Konferenzservern und Endpunkt Speicherorten konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="3da52-112">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="3da52-113">Bericht zur Vermittlungsserver Leistung</span><span class="sxs-lookup"><span data-stu-id="3da52-113">Mediation server performance report</span></span>

<span data-ttu-id="3da52-114">Im Bericht "Vermittlungs Server Leistung" werden die Metriken aufgelistet, die von einer oder mehreren Mediation während des angegebenen Zeitraums erreicht wurden.</span><span class="sxs-lookup"><span data-stu-id="3da52-114">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="3da52-115">Die Metriken für das Unified Communications (UC)-to-Mediation-Server Bein und das Vermittlungsserver-zu-Gateway-Bein jedes Anrufs werden separat gemeldet.</span><span class="sxs-lookup"><span data-stu-id="3da52-115">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="3da52-116">Mit diesem Bericht können Sie die Lautstärke und Leistung der verschiedenen Vermittlungsserver Ihrer Organisation vergleichen.</span><span class="sxs-lookup"><span data-stu-id="3da52-116">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="3da52-117">Für jeden Vermittlungs Server (und für jedes Anruf Bein) wird im Bericht Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="3da52-117">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="3da52-118">Anzahl der Anrufe</span><span class="sxs-lookup"><span data-stu-id="3da52-118">Number of calls</span></span>

  - <span data-ttu-id="3da52-119">Paketverlust</span><span class="sxs-lookup"><span data-stu-id="3da52-119">Packet Loss</span></span>

  - <span data-ttu-id="3da52-120">Round-Trip-Zeit</span><span class="sxs-lookup"><span data-stu-id="3da52-120">Round Trip Time</span></span>

  - <span data-ttu-id="3da52-121">Jitter</span><span class="sxs-lookup"><span data-stu-id="3da52-121">Jitter</span></span>

  - <span data-ttu-id="3da52-122">Conversational Mean Opinion Score (MOS)</span><span class="sxs-lookup"><span data-stu-id="3da52-122">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="3da52-123">Senden von MOS</span><span class="sxs-lookup"><span data-stu-id="3da52-123">Sending MOS</span></span>

  - <span data-ttu-id="3da52-124">Anhören von MOS</span><span class="sxs-lookup"><span data-stu-id="3da52-124">Listening MOS</span></span>

  - <span data-ttu-id="3da52-125">Netzwerk-Mos</span><span class="sxs-lookup"><span data-stu-id="3da52-125">Network MOS</span></span>

  - <span data-ttu-id="3da52-126">Netzwerk-Mos-Verschlechterung</span><span class="sxs-lookup"><span data-stu-id="3da52-126">Network MOS Degradation</span></span>

  - <span data-ttu-id="3da52-127">Echo-Rückgabe</span><span class="sxs-lookup"><span data-stu-id="3da52-127">Echo Return</span></span>

  - <span data-ttu-id="3da52-128">Signal Pegel</span><span class="sxs-lookup"><span data-stu-id="3da52-128">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="3da52-129">A/V-Konferenzserver-Leistungsbericht</span><span class="sxs-lookup"><span data-stu-id="3da52-129">A/V conferencing server performance report</span></span>

<span data-ttu-id="3da52-130">Der Leistungsbericht a/v Conferencing Server bietet Listen mit Metriken, die von einem oder mehreren a/v-Konferenzservern während des angegebenen Zeitraums erreicht wurden.</span><span class="sxs-lookup"><span data-stu-id="3da52-130">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="3da52-131">Dieser Bericht kann verwendet werden, um die Lautstärke und Leistung der verschiedenen A/V-Konferenzserver Ihrer Organisation zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="3da52-131">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="3da52-132">Ihre Organisation kann den Bericht auch isolieren, um nur die Benutzeroberfläche für bestimmte Clienttypen wie lync-Clients oder PSTN-Clients anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3da52-132">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="3da52-133">Für jeden A/V-Konferenz Server wird im Bericht Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="3da52-133">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="3da52-134">Anzahl von Konferenzen</span><span class="sxs-lookup"><span data-stu-id="3da52-134">Number of conferences</span></span>

  - <span data-ttu-id="3da52-135">Paketverlust</span><span class="sxs-lookup"><span data-stu-id="3da52-135">Packet Loss</span></span>

  - <span data-ttu-id="3da52-136">Round-Trip-Zeit</span><span class="sxs-lookup"><span data-stu-id="3da52-136">Round Trip Time</span></span>

  - <span data-ttu-id="3da52-137">Jitter</span><span class="sxs-lookup"><span data-stu-id="3da52-137">Jitter</span></span>

  - <span data-ttu-id="3da52-138">Conversational Mean Opinion Score (MOS)</span><span class="sxs-lookup"><span data-stu-id="3da52-138">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="3da52-139">Senden von MOS</span><span class="sxs-lookup"><span data-stu-id="3da52-139">Sending MOS</span></span>

  - <span data-ttu-id="3da52-140">Anhören von MOS</span><span class="sxs-lookup"><span data-stu-id="3da52-140">Listening MOS</span></span>

  - <span data-ttu-id="3da52-141">Netzwerk-Mos</span><span class="sxs-lookup"><span data-stu-id="3da52-141">Network MOS</span></span>

  - <span data-ttu-id="3da52-142">Netzwerk-Mos-Verschlechterung</span><span class="sxs-lookup"><span data-stu-id="3da52-142">Network MOS Degradation</span></span>

  - <span data-ttu-id="3da52-143">Echo-Rückgabe</span><span class="sxs-lookup"><span data-stu-id="3da52-143">Echo Return</span></span>

  - <span data-ttu-id="3da52-144">Signal Pegel</span><span class="sxs-lookup"><span data-stu-id="3da52-144">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="3da52-145">Bericht zur standortbasierten Leistung</span><span class="sxs-lookup"><span data-stu-id="3da52-145">Location-based performance report</span></span>

<span data-ttu-id="3da52-146">Der standortbasierte Leistungsbericht enthält eine Liste der Netzwerkspeicherorte und für jeden Standort wird die Anzahl der Anrufe in jedem zuvor festgelegten Qualitätsbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3da52-146">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="3da52-147">Ziel dieses Berichts ist es, Einblicke in die Medienqualität des Großteils der Telefonanrufe Ihrer Organisation an verschiedenen Standorten zu geben, damit Sie schlecht funktionierende Speicherorte erkennen und die unterschiedlichen Grade der Medienqualität in Ihrer Organisation sehen können. verschiedenen Speicherorten.</span><span class="sxs-lookup"><span data-stu-id="3da52-147">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="3da52-148">Beim Anzeigen des Berichts werden unterschiedliche Tabellen mit Metriken angezeigt – eine Tabelle für jede Metrik, über die Ihre Organisation berichten möchte.</span><span class="sxs-lookup"><span data-stu-id="3da52-148">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="3da52-149">Sie können aus den folgenden Metriken für diesen Bericht wählen:</span><span class="sxs-lookup"><span data-stu-id="3da52-149">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="3da52-150">Conversational Mean Opinion Score (MOS)</span><span class="sxs-lookup"><span data-stu-id="3da52-150">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="3da52-151">Netzwerk-Mos</span><span class="sxs-lookup"><span data-stu-id="3da52-151">Network MOS</span></span>

  - <span data-ttu-id="3da52-152">Netzwerk-Mos-Verschlechterung</span><span class="sxs-lookup"><span data-stu-id="3da52-152">Network MOS Degradation</span></span>

  - <span data-ttu-id="3da52-153">Senden von MOS</span><span class="sxs-lookup"><span data-stu-id="3da52-153">Sending MOS</span></span>

  - <span data-ttu-id="3da52-154">Anhören von MOS</span><span class="sxs-lookup"><span data-stu-id="3da52-154">Listening MOS</span></span>

  - <span data-ttu-id="3da52-155">Paketverlust</span><span class="sxs-lookup"><span data-stu-id="3da52-155">Packet Loss</span></span>

  - <span data-ttu-id="3da52-156">Jitter</span><span class="sxs-lookup"><span data-stu-id="3da52-156">Jitter</span></span>

  - <span data-ttu-id="3da52-157">Latenz</span><span class="sxs-lookup"><span data-stu-id="3da52-157">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

