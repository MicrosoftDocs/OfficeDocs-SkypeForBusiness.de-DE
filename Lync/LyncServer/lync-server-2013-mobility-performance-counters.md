---
title: 'Lync Server 2013: Leistungsindikatoren für die Mobilität'
description: 'Lync Server 2013: Mobilitäts Leistungsindikatoren.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 922288f6c026f088d651dc61afdcb6ba04fed30a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550531"
---
# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="6d81d-103">Mobilitäts Leistungsindikatoren in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d81d-103">Mobility performance counters in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d81d-104">_**Letztes Änderungsstand des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="6d81d-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="6d81d-105">In den folgenden Tabellen sind die Namen und Beschreibungen der Leistungsindikatoren aufgeführt, die Sie zum Überwachen von Servern mit dem Unified Communications Web API (UCWA) und dem lync Server 2013 MCX-Mobilitätsdienst verwenden können.</span><span class="sxs-lookup"><span data-stu-id="6d81d-105">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="6d81d-106">Der Kategorienamen für die Leistungsindikatoren in der UCWA-Tabelle lautet **ls: "UCWA**".</span><span class="sxs-lookup"><span data-stu-id="6d81d-106">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="6d81d-107">Der Kategoriename für die Leistungsindikatoren in der MCX-Mobilitätsdienst Tabelle lautet **ls: mobiler Kommunikationsdienst**.</span><span class="sxs-lookup"><span data-stu-id="6d81d-107">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="6d81d-108">Leistungsindikatoren für UCWA</span><span class="sxs-lookup"><span data-stu-id="6d81d-108">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d81d-109">Leistungsindikator</span><span class="sxs-lookup"><span data-stu-id="6d81d-109">Counter</span></span></th>
<th><span data-ttu-id="6d81d-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6d81d-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-111">Anzahl aktiver Anwendungen</span><span class="sxs-lookup"><span data-stu-id="6d81d-111">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="6d81d-112">Die aktuelle Anzahl von Anwendungen</span><span class="sxs-lookup"><span data-stu-id="6d81d-112">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-113">Anzahl aktiver Modality für die Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="6d81d-113">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="6d81d-114">Die aktuelle Anzahl von Modalitäten für die Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="6d81d-114">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-115">Anzahl aktiver audiomodaler Daten</span><span class="sxs-lookup"><span data-stu-id="6d81d-115">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="6d81d-116">Die aktuelle Anzahl an audiomodalen Daten</span><span class="sxs-lookup"><span data-stu-id="6d81d-116">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-117">Anzahl der aktiven Daten Zusammenarbeits Modalitäten</span><span class="sxs-lookup"><span data-stu-id="6d81d-117">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="6d81d-118">Die aktuelle Anzahl der Daten Zusammenarbeits Modalitäten</span><span class="sxs-lookup"><span data-stu-id="6d81d-118">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-119">Wartezeit für Active Directory Photo get (MS)</span><span class="sxs-lookup"><span data-stu-id="6d81d-119">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="6d81d-120">Dieser Indikator zeigt die durchschnittliche Zeit (in Millisekunden) zum Abrufen eines Fotos aus Active Directory an.</span><span class="sxs-lookup"><span data-stu-id="6d81d-120">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-121">Anzahl aktiver Messaging-Modalitäten</span><span class="sxs-lookup"><span data-stu-id="6d81d-121">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="6d81d-122">Die aktuelle Anzahl von Messaging Modalitäten</span><span class="sxs-lookup"><span data-stu-id="6d81d-122">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-123">Anzahl aktiver Panorama-Video Modalitäten</span><span class="sxs-lookup"><span data-stu-id="6d81d-123">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="6d81d-124">Die aktuelle Anzahl der Panorama Video Modalitäten</span><span class="sxs-lookup"><span data-stu-id="6d81d-124">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-125">Aktive ausstehende Get-Anzahl</span><span class="sxs-lookup"><span data-stu-id="6d81d-125">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="6d81d-126">Die Anzahl der derzeit aktiven ausstehenden Gets; lange gehaltene Verbindungen mit dem Server</span><span class="sxs-lookup"><span data-stu-id="6d81d-126">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-127">Anzahl aktiver Sitzungen</span><span class="sxs-lookup"><span data-stu-id="6d81d-127">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="6d81d-128">Die aktuelle Anzahl von Endpunkten, die in UCWA pro Anwendung und Gesamtzahl registriert sind.</span><span class="sxs-lookup"><span data-stu-id="6d81d-128">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-129">Anzahl der aktiven Benutzerinstanzen</span><span class="sxs-lookup"><span data-stu-id="6d81d-129">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="6d81d-130">Die aktuelle Anzahl von Benutzerinstanzen</span><span class="sxs-lookup"><span data-stu-id="6d81d-130">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-131">Aktive Benutzerinstanzen ohne Anwendung</span><span class="sxs-lookup"><span data-stu-id="6d81d-131">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="6d81d-132">Die aktuelle Anzahl von Benutzerinstanzen ohne Anwendung</span><span class="sxs-lookup"><span data-stu-id="6d81d-132">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-133">Anzahl aktiver Video Modalitäten</span><span class="sxs-lookup"><span data-stu-id="6d81d-133">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="6d81d-134">Die aktuelle Anzahl von Video Modalitäten</span><span class="sxs-lookup"><span data-stu-id="6d81d-134">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-135">Empfangene Anwendungs Erstellungsanforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="6d81d-135">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="6d81d-136">Die Anzahl der empfangenen Anwendungs Erstellungsanforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="6d81d-136">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-137">Als MCU-Join-Fehler</span><span class="sxs-lookup"><span data-stu-id="6d81d-137">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="6d81d-138">Die Anzahl der AS-MCU-Join-Fehler</span><span class="sxs-lookup"><span data-stu-id="6d81d-138">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-139">AV-MCU-Join-Fehler</span><span class="sxs-lookup"><span data-stu-id="6d81d-139">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="6d81d-140">Die Anzahl der AV MCU Join-Fehler</span><span class="sxs-lookup"><span data-stu-id="6d81d-140">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-141">Durchschnittliche Anwendungsstartzeit (MS)</span><span class="sxs-lookup"><span data-stu-id="6d81d-141">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="6d81d-142">Die durchschnittliche Startzeit der Anwendung in Millisekunden</span><span class="sxs-lookup"><span data-stu-id="6d81d-142">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-143">Durchschnittliche Lebensdauer für Sitzung (MS)</span><span class="sxs-lookup"><span data-stu-id="6d81d-143">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="6d81d-144">Die durchschnittliche Dauer einer Sitzung in Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="6d81d-144">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-145">Daten-MCU-Join-Fehler</span><span class="sxs-lookup"><span data-stu-id="6d81d-145">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="6d81d-146">Anzahl der Daten-MCU-Join-Fehler</span><span class="sxs-lookup"><span data-stu-id="6d81d-146">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-147">Wartezeit für die Exchange-Kontakt Suche (MS)</span><span class="sxs-lookup"><span data-stu-id="6d81d-147">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="6d81d-148">Dieser Indikator zeigt die durchschnittliche Zeit (in Millisekunden) zum Suchen von Kontakten in Exchange an.</span><span class="sxs-lookup"><span data-stu-id="6d81d-148">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-149">Wartezeit für Exchange HD Photo get (MS)</span><span class="sxs-lookup"><span data-stu-id="6d81d-149">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="6d81d-150">Dieser Indikator zeigt die durchschnittliche Zeit (in Millisekunden) zum Abrufen eines Fotos aus Exchange an.</span><span class="sxs-lookup"><span data-stu-id="6d81d-150">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-151">HTTP-4xx-Antworten/Sekunde</span><span class="sxs-lookup"><span data-stu-id="6d81d-151">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="6d81d-152">Die pro Sekunde Rate von Antworten mit http-4xx-Code</span><span class="sxs-lookup"><span data-stu-id="6d81d-152">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-153">HTTP-5xx-Antworten/Sekunde</span><span class="sxs-lookup"><span data-stu-id="6d81d-153">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="6d81d-154">Die pro Sekunde Rate von Antworten mit http-5xx-Code</span><span class="sxs-lookup"><span data-stu-id="6d81d-154">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-155">Fehler im MCU-Join</span><span class="sxs-lookup"><span data-stu-id="6d81d-155">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="6d81d-156">Anzahl der im MCU-Join-Fehler</span><span class="sxs-lookup"><span data-stu-id="6d81d-156">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-157">Anzahl Active Directory Fehler beim Abrufen von Fotos</span><span class="sxs-lookup"><span data-stu-id="6d81d-157">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="6d81d-158">Die Gesamtzahl der Fehler beim Abrufen von Fotos aus Active Directory</span><span class="sxs-lookup"><span data-stu-id="6d81d-158">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-159">Anzahl der Fehler bei der Kontakt Suche</span><span class="sxs-lookup"><span data-stu-id="6d81d-159">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="6d81d-160">Die Gesamtzahl der Fehler beim Durchsuchen von Kontakten in Exchange</span><span class="sxs-lookup"><span data-stu-id="6d81d-160">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-161">Anzahl der deserialisierungs Fehler</span><span class="sxs-lookup"><span data-stu-id="6d81d-161">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="6d81d-162">Die Gesamtzahl der deserialisierungs Fehler</span><span class="sxs-lookup"><span data-stu-id="6d81d-162">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-163">Anzahl der Fehler bei HD Photo Get</span><span class="sxs-lookup"><span data-stu-id="6d81d-163">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="6d81d-164">Die Gesamtzahl der Fehler beim Abrufen von HD-Fotos aus Exchange</span><span class="sxs-lookup"><span data-stu-id="6d81d-164">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-165">Über die maximalen Abonnements pro Anwendung</span><span class="sxs-lookup"><span data-stu-id="6d81d-165">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="6d81d-166">Die Anzahl der Abonnementanforderungen über den maximal zulässigen pro Anwendung</span><span class="sxs-lookup"><span data-stu-id="6d81d-166">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-167">Über die maximalen Abonnements pro Batch</span><span class="sxs-lookup"><span data-stu-id="6d81d-167">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="6d81d-168">Die Anzahl der Abonnementanforderungen über den maximal zulässigen pro Batch</span><span class="sxs-lookup"><span data-stu-id="6d81d-168">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-169">Fehler bei Anwesenheitsabonnements</span><span class="sxs-lookup"><span data-stu-id="6d81d-169">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="6d81d-170">Die Anzahl der Fehler beim Abonnieren der Anwesenheitsinformationen</span><span class="sxs-lookup"><span data-stu-id="6d81d-170">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-171">Registrieren von Endpunkt Fehlern</span><span class="sxs-lookup"><span data-stu-id="6d81d-171">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="6d81d-172">Die Anzahl der Fehler beim Registrieren von Endpunkten</span><span class="sxs-lookup"><span data-stu-id="6d81d-172">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-173">Empfangene Anforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="6d81d-173">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="6d81d-174">Die Anzahl der empfangenen Anforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="6d81d-174">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-175">Erfolgreiche Anforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="6d81d-175">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="6d81d-176">Die Anzahl der erfolgreichen Anforderungen pro Sekunde (http-2xx/3xx-Antwortcodes)</span><span class="sxs-lookup"><span data-stu-id="6d81d-176">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-177">Erfolgreiche Erstellung von Anwendungsanforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="6d81d-177">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="6d81d-178">Die Anzahl der erfolgreichen Anwendungs Erstellungsanforderungen pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="6d81d-178">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-179">Timeout für ausstehende Get-Anzahl</span><span class="sxs-lookup"><span data-stu-id="6d81d-179">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="6d81d-180">Die Anzahl der ausstehenden ruft dieses Timeout ab.</span><span class="sxs-lookup"><span data-stu-id="6d81d-180">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-181">Gesamtzahl der empfangenen Anwendungs Erstellungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="6d81d-181">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="6d81d-182">Die Gesamtzahl der seit dem Start des Diensts empfangenen Anwendungs Erstellungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="6d81d-182">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-183">Gesamtzahl der http-4xx-Antworten</span><span class="sxs-lookup"><span data-stu-id="6d81d-183">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="6d81d-184">Die Gesamtzahl der http-4xx-Antworten</span><span class="sxs-lookup"><span data-stu-id="6d81d-184">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-185">Gesamtzahl der http-5xx-Antworten</span><span class="sxs-lookup"><span data-stu-id="6d81d-185">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="6d81d-186">Die Gesamtzahl der http-5xx-Antworten</span><span class="sxs-lookup"><span data-stu-id="6d81d-186">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-187">Insgesamt empfangene Anforderungen im Befehlskanal</span><span class="sxs-lookup"><span data-stu-id="6d81d-187">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="6d81d-188">Die Gesamtzahl der über den Befehlskanal empfangenen Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="6d81d-188">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-189">Gesamtzahl der erfolgreichen Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6d81d-189">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="6d81d-190">Die Gesamtzahl der erfolgreichen Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="6d81d-190">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-191">Gesamtzahl der initiierten Sitzungen</span><span class="sxs-lookup"><span data-stu-id="6d81d-191">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="6d81d-192">Die Gesamtzahl der Sitzungen, die seit dem Start des Diensts initiiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6d81d-192">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-193">Gesamtzahl der Sitzungen, die aufgrund eines Leerlauftimeouts beendet wurden</span><span class="sxs-lookup"><span data-stu-id="6d81d-193">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="6d81d-194">Die Gesamtzahl der Sitzungen, die beendet wurden, da das Leerlauftimeout des Benutzers erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="6d81d-194">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-195">Insgesamt gedrosselte Anwendungen</span><span class="sxs-lookup"><span data-stu-id="6d81d-195">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="6d81d-196">Die Anzahl der gedrosselten Anwendungen</span><span class="sxs-lookup"><span data-stu-id="6d81d-196">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="6d81d-197">Leistungsindikatoren für den MCX-Mobilitätsdienst</span><span class="sxs-lookup"><span data-stu-id="6d81d-197">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d81d-198">Leistungsindikator</span><span class="sxs-lookup"><span data-stu-id="6d81d-198">Counter</span></span></th>
<th><span data-ttu-id="6d81d-199">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6d81d-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-200">Durchschnittliche Sitzungsdauer in Millisekunden</span><span class="sxs-lookup"><span data-stu-id="6d81d-200">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="6d81d-201">Die durchschnittliche Dauer einer Sitzung in Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="6d81d-201">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-202">Aktuelle Pushbenachrichtigungsabonnements</span><span class="sxs-lookup"><span data-stu-id="6d81d-202">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="6d81d-203">Die aktuelle Anzahl von Pushbenachrichtigungsabonnements.</span><span class="sxs-lookup"><span data-stu-id="6d81d-203">The current number of push notification subscriptions.</span></span> <span data-ttu-id="6d81d-204">Diese Nummer steht in Verbindung mit der Anzahl der derzeit aktiven Sitzungen für die Teilmenge der derzeit aktiven Sitzungen, die für Windows Mobile-oder iPhone-Geräte registriert sind.</span><span class="sxs-lookup"><span data-stu-id="6d81d-204">This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-205">Anzahl derzeit aktiver Netzwerkumfragen mit Timeout</span><span class="sxs-lookup"><span data-stu-id="6d81d-205">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="6d81d-206">Die Anzahl von Netzwerkumfragen, bei denen ein Timeout aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="6d81d-206">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-207">Anzahl derzeit aktiver Umfragen</span><span class="sxs-lookup"><span data-stu-id="6d81d-207">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="6d81d-208">Die Anzahl von derzeit aktiven Umfragen (lange gehaltene Verbindungen mit dem Server).</span><span class="sxs-lookup"><span data-stu-id="6d81d-208">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-209">Anzahl derzeit aktiver Sitzungen</span><span class="sxs-lookup"><span data-stu-id="6d81d-209">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="6d81d-210">Die derzeitige Anzahl der im Mobilitätsdienst registrierten Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="6d81d-210">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-211">Anzahl derzeit aktiver Sitzungen mit aktiven Anwesenheitsabonnements</span><span class="sxs-lookup"><span data-stu-id="6d81d-211">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="6d81d-212">Die Anzahl derzeit aktiver Sitzungen mit aktiven Anwesenheitsabonnements.</span><span class="sxs-lookup"><span data-stu-id="6d81d-212">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-213">Gescheiterte Pushbenachrichtigungsanforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="6d81d-213">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="6d81d-214">Die Anzahl der gescheiterten Pushbenachrichtigungsanforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="6d81d-214">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-215">Erfolgreiche Pushbenachrichtigungsanforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="6d81d-215">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="6d81d-216">Die Anzahl der erfolgreichen Pushbenachrichtigungsanforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="6d81d-216">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-217">Gedrosselte Pushbenachrichtigungsanforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="6d81d-217">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="6d81d-218">Die Anzahl der gedrosselten Pushbenachrichtigungsanforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="6d81d-218">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-219">Pushbenachrichtigungsanforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="6d81d-219">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="6d81d-220">Die Anzahl der gesendeten Pushbenachrichtigungsanforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="6d81d-220">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-221">Gescheiterte Anforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="6d81d-221">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="6d81d-222">Die Anzahl der gescheiterten Anforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="6d81d-222">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-223">Empfangene Anforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="6d81d-223">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="6d81d-224">Die Anzahl der empfangenen Anforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="6d81d-224">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-225">Abgelehnte Anforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="6d81d-225">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="6d81d-226">Die Anzahl der abgelehnten Anforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="6d81d-226">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-227">Erfolgreiche Anforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="6d81d-227">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="6d81d-228">Die Anzahl der erfolgreichen Anforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="6d81d-228">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-229">Erfolgreiche Anforderungen zur Sitzungsinitiierung/Sekunde</span><span class="sxs-lookup"><span data-stu-id="6d81d-229">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="6d81d-p102">Die Anzahl der erfolgreichen Anforderungen zur Standortermittlung pro Sekunde. Anforderungen zum Initiieren einer Sitzung beanspruchen die meisten CPU-Ressourcen auf dem Server. Maximal wird eine Last von 12 Anforderungen/Sekunde unterstützt. Die Aufrechterhaltbarkeit hängt von anderen Lasten auf dem Server ab. Das Initiieren einer Sitzung bedeutet normalerweise, dass ein Benutzer angemeldet wird, der für einen längeren Zeitraum abgemeldet war.</span><span class="sxs-lookup"><span data-stu-id="6d81d-p102">The per second rate of successful Get Location requests. Requests to initiate a session consume the most CPU on the server. Peak supported load is 12/second. Sustainability depends on other loads on the server. Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-235">Gesamtzahl der abgelehnten eingehenden Sprachanrufe</span><span class="sxs-lookup"><span data-stu-id="6d81d-235">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="6d81d-236">Die Gesamtzahl der abgelehnten eingehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="6d81d-236">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-237">Gesamtzahl der gescheiterten eingehenden Sprachanrufe</span><span class="sxs-lookup"><span data-stu-id="6d81d-237">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="6d81d-238">Die Gesamtzahl der gescheiterten eingehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="6d81d-238">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-239">Gesamtzahl der gescheiterten ausgehenden Sprachanrufe</span><span class="sxs-lookup"><span data-stu-id="6d81d-239">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="6d81d-240">Die Gesamtzahl der gescheiterten ausgehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="6d81d-240">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-241">Gesamtzahl der vom Benutzer beendeten Sitzungen</span><span class="sxs-lookup"><span data-stu-id="6d81d-241">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="6d81d-242">Die Gesamtzahl der vom Benutzer beendeten Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="6d81d-242">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-243">Gesamtzahl der Pushbenachrichtigungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="6d81d-243">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="6d81d-244">Die Gesamtzahl der Pushbenachrichtigungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="6d81d-244">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-245">Gesamtzahl gescheiterter Pushbenachrichtigungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="6d81d-245">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="6d81d-246">Die Gesamtzahl der gescheiterten Pushbenachrichtigungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="6d81d-246">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-247">Gesamtzahl erfolgreicher Pushbenachrichtigungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="6d81d-247">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="6d81d-248">Die Gesamtzahl der erfolgreichen Pushbenachrichtigungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="6d81d-248">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-249">Gesamtzahl gedrosselter Pushbenachrichtigungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="6d81d-249">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="6d81d-250">Die Gesamtzahl der gedrosselten Pushbenachrichtigungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="6d81d-250">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-251">Gesamtzahl der gescheiterten Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6d81d-251">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="6d81d-252">Die Gesamtzahl der gescheiterten Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="6d81d-252">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-253">Gesamtzahl der über den Befehlskanal empfangenen Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6d81d-253">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="6d81d-254">Die Gesamtzahl der über den Befehlskanal empfangenen Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="6d81d-254">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-255">Gesamtzahl der abgelehnten Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6d81d-255">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="6d81d-256">Die Gesamtzahl der abgelehnten Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="6d81d-256">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-257">Gesamtzahl der erfolgreichen Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6d81d-257">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="6d81d-258">Die Gesamtzahl der an den Mobilitätsdienst gerichteten Anforderungen, die erfolgreich waren.</span><span class="sxs-lookup"><span data-stu-id="6d81d-258">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-259">Gesamtzahl der initiierten Sitzungen</span><span class="sxs-lookup"><span data-stu-id="6d81d-259">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="6d81d-260">Die Gesamtzahl der Sitzungen, die seit dem Start des Mobilitätsdiensts initiiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6d81d-260">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-261">Gesamtzahl der Sitzungen, die aufgrund eines Leerlauftimeouts des Benutzers beendet wurden</span><span class="sxs-lookup"><span data-stu-id="6d81d-261">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="6d81d-262">Die Gesamtzahl der Sitzungen, die beendet wurden, da das Leerlauftimeout des Benutzers erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="6d81d-262">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d81d-263">Gesamtzahl der erfolgreichen eingehenden Sprachanrufe</span><span class="sxs-lookup"><span data-stu-id="6d81d-263">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="6d81d-264">Die Gesamtzahl der erfolgreichen eingehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="6d81d-264">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d81d-265">Gesamtzahl der erfolgreichen ausgehenden Sprachanrufe</span><span class="sxs-lookup"><span data-stu-id="6d81d-265">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="6d81d-266">Die Gesamtzahl der erfolgreichen ausgehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="6d81d-266">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

