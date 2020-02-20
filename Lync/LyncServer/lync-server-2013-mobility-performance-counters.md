---
title: 'Lync Server 2013: Leistungsindikatoren für die Mobilität'
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
ms.openlocfilehash: cb5363ef31f44abdb9c8ea07938668f17b95c471
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="4c428-102">Mobilitäts Leistungsindikatoren in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c428-102">Mobility performance counters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c428-103">_**Letztes Änderungsstand des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="4c428-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="4c428-104">In den folgenden Tabellen sind die Namen und Beschreibungen der Leistungsindikatoren aufgeführt, die Sie zum Überwachen von Servern mit dem Unified Communications Web API (UCWA) und dem lync Server 2013 MCX-Mobilitätsdienst verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4c428-104">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="4c428-105">Der Kategorienamen für die Leistungsindikatoren in der UCWA-Tabelle lautet **ls: "UCWA**".</span><span class="sxs-lookup"><span data-stu-id="4c428-105">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="4c428-106">Der Kategoriename für die Leistungsindikatoren in der MCX-Mobilitätsdienst Tabelle lautet **ls: mobiler Kommunikationsdienst**.</span><span class="sxs-lookup"><span data-stu-id="4c428-106">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="4c428-107">Leistungsindikatoren für UCWA</span><span class="sxs-lookup"><span data-stu-id="4c428-107">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c428-108">Leistungsindikator</span><span class="sxs-lookup"><span data-stu-id="4c428-108">Counter</span></span></th>
<th><span data-ttu-id="4c428-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c428-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c428-110">Anzahl aktiver Anwendungen</span><span class="sxs-lookup"><span data-stu-id="4c428-110">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="4c428-111">Die aktuelle Anzahl von Anwendungen</span><span class="sxs-lookup"><span data-stu-id="4c428-111">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-112">Anzahl aktiver Modality für die Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="4c428-112">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="4c428-113">Die aktuelle Anzahl von Modalitäten für die Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="4c428-113">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-114">Anzahl aktiver audiomodaler Daten</span><span class="sxs-lookup"><span data-stu-id="4c428-114">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="4c428-115">Die aktuelle Anzahl an audiomodalen Daten</span><span class="sxs-lookup"><span data-stu-id="4c428-115">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-116">Anzahl der aktiven Daten Zusammenarbeits Modalitäten</span><span class="sxs-lookup"><span data-stu-id="4c428-116">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="4c428-117">Die aktuelle Anzahl der Daten Zusammenarbeits Modalitäten</span><span class="sxs-lookup"><span data-stu-id="4c428-117">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-118">Wartezeit für Active Directory Photo get (MS)</span><span class="sxs-lookup"><span data-stu-id="4c428-118">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="4c428-119">Dieser Indikator zeigt die durchschnittliche Zeit (in Millisekunden) zum Abrufen eines Fotos aus Active Directory an.</span><span class="sxs-lookup"><span data-stu-id="4c428-119">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-120">Anzahl aktiver Messaging-Modalitäten</span><span class="sxs-lookup"><span data-stu-id="4c428-120">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="4c428-121">Die aktuelle Anzahl von Messaging Modalitäten</span><span class="sxs-lookup"><span data-stu-id="4c428-121">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-122">Anzahl aktiver Panorama-Video Modalitäten</span><span class="sxs-lookup"><span data-stu-id="4c428-122">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="4c428-123">Die aktuelle Anzahl der Panorama Video Modalitäten</span><span class="sxs-lookup"><span data-stu-id="4c428-123">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-124">Aktive ausstehende Get-Anzahl</span><span class="sxs-lookup"><span data-stu-id="4c428-124">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="4c428-125">Die Anzahl der derzeit aktiven ausstehenden Gets; lange gehaltene Verbindungen mit dem Server</span><span class="sxs-lookup"><span data-stu-id="4c428-125">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-126">Anzahl aktiver Sitzungen</span><span class="sxs-lookup"><span data-stu-id="4c428-126">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="4c428-127">Die aktuelle Anzahl von Endpunkten, die in UCWA pro Anwendung und Gesamtzahl registriert sind.</span><span class="sxs-lookup"><span data-stu-id="4c428-127">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-128">Anzahl der aktiven Benutzerinstanzen</span><span class="sxs-lookup"><span data-stu-id="4c428-128">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="4c428-129">Die aktuelle Anzahl von Benutzerinstanzen</span><span class="sxs-lookup"><span data-stu-id="4c428-129">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-130">Aktive Benutzerinstanzen ohne Anwendung</span><span class="sxs-lookup"><span data-stu-id="4c428-130">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="4c428-131">Die aktuelle Anzahl von Benutzerinstanzen ohne Anwendung</span><span class="sxs-lookup"><span data-stu-id="4c428-131">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-132">Anzahl aktiver Video Modalitäten</span><span class="sxs-lookup"><span data-stu-id="4c428-132">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="4c428-133">Die aktuelle Anzahl von Video Modalitäten</span><span class="sxs-lookup"><span data-stu-id="4c428-133">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-134">Empfangene Anwendungs Erstellungsanforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="4c428-134">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="4c428-135">Die Anzahl der empfangenen Anwendungs Erstellungsanforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="4c428-135">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-136">Als MCU-Join-Fehler</span><span class="sxs-lookup"><span data-stu-id="4c428-136">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="4c428-137">Die Anzahl der AS-MCU-Join-Fehler</span><span class="sxs-lookup"><span data-stu-id="4c428-137">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-138">AV-MCU-Join-Fehler</span><span class="sxs-lookup"><span data-stu-id="4c428-138">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="4c428-139">Die Anzahl der AV MCU Join-Fehler</span><span class="sxs-lookup"><span data-stu-id="4c428-139">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-140">Durchschnittliche Anwendungsstartzeit (MS)</span><span class="sxs-lookup"><span data-stu-id="4c428-140">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="4c428-141">Die durchschnittliche Startzeit der Anwendung in Millisekunden</span><span class="sxs-lookup"><span data-stu-id="4c428-141">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-142">Durchschnittliche Lebensdauer für Sitzung (MS)</span><span class="sxs-lookup"><span data-stu-id="4c428-142">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="4c428-143">Die durchschnittliche Dauer einer Sitzung in Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="4c428-143">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-144">Daten-MCU-Join-Fehler</span><span class="sxs-lookup"><span data-stu-id="4c428-144">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="4c428-145">Anzahl der Daten-MCU-Join-Fehler</span><span class="sxs-lookup"><span data-stu-id="4c428-145">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-146">Wartezeit für die Exchange-Kontakt Suche (MS)</span><span class="sxs-lookup"><span data-stu-id="4c428-146">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="4c428-147">Dieser Indikator zeigt die durchschnittliche Zeit (in Millisekunden) zum Suchen von Kontakten in Exchange an.</span><span class="sxs-lookup"><span data-stu-id="4c428-147">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-148">Wartezeit für Exchange HD Photo get (MS)</span><span class="sxs-lookup"><span data-stu-id="4c428-148">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="4c428-149">Dieser Indikator zeigt die durchschnittliche Zeit (in Millisekunden) zum Abrufen eines Fotos aus Exchange an.</span><span class="sxs-lookup"><span data-stu-id="4c428-149">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-150">HTTP-4xx-Antworten/Sekunde</span><span class="sxs-lookup"><span data-stu-id="4c428-150">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="4c428-151">Die pro Sekunde Rate von Antworten mit http-4xx-Code</span><span class="sxs-lookup"><span data-stu-id="4c428-151">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-152">HTTP-5xx-Antworten/Sekunde</span><span class="sxs-lookup"><span data-stu-id="4c428-152">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="4c428-153">Die pro Sekunde Rate von Antworten mit http-5xx-Code</span><span class="sxs-lookup"><span data-stu-id="4c428-153">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-154">Fehler im MCU-Join</span><span class="sxs-lookup"><span data-stu-id="4c428-154">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="4c428-155">Anzahl der im MCU-Join-Fehler</span><span class="sxs-lookup"><span data-stu-id="4c428-155">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-156">Anzahl Active Directory Fehler beim Abrufen von Fotos</span><span class="sxs-lookup"><span data-stu-id="4c428-156">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="4c428-157">Die Gesamtzahl der Fehler beim Abrufen von Fotos aus Active Directory</span><span class="sxs-lookup"><span data-stu-id="4c428-157">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-158">Anzahl der Fehler bei der Kontakt Suche</span><span class="sxs-lookup"><span data-stu-id="4c428-158">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="4c428-159">Die Gesamtzahl der Fehler beim Durchsuchen von Kontakten in Exchange</span><span class="sxs-lookup"><span data-stu-id="4c428-159">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-160">Anzahl der deserialisierungs Fehler</span><span class="sxs-lookup"><span data-stu-id="4c428-160">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="4c428-161">Die Gesamtzahl der deserialisierungs Fehler</span><span class="sxs-lookup"><span data-stu-id="4c428-161">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-162">Anzahl der Fehler bei HD Photo Get</span><span class="sxs-lookup"><span data-stu-id="4c428-162">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="4c428-163">Die Gesamtzahl der Fehler beim Abrufen von HD-Fotos aus Exchange</span><span class="sxs-lookup"><span data-stu-id="4c428-163">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-164">Über die maximalen Abonnements pro Anwendung</span><span class="sxs-lookup"><span data-stu-id="4c428-164">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="4c428-165">Die Anzahl der Abonnementanforderungen über den maximal zulässigen pro Anwendung</span><span class="sxs-lookup"><span data-stu-id="4c428-165">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-166">Über die maximalen Abonnements pro Batch</span><span class="sxs-lookup"><span data-stu-id="4c428-166">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="4c428-167">Die Anzahl der Abonnementanforderungen über den maximal zulässigen pro Batch</span><span class="sxs-lookup"><span data-stu-id="4c428-167">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-168">Fehler bei Anwesenheitsabonnements</span><span class="sxs-lookup"><span data-stu-id="4c428-168">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="4c428-169">Die Anzahl der Fehler beim Abonnieren der Anwesenheitsinformationen</span><span class="sxs-lookup"><span data-stu-id="4c428-169">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-170">Registrieren von Endpunkt Fehlern</span><span class="sxs-lookup"><span data-stu-id="4c428-170">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="4c428-171">Die Anzahl der Fehler beim Registrieren von Endpunkten</span><span class="sxs-lookup"><span data-stu-id="4c428-171">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-172">Empfangene Anforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="4c428-172">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="4c428-173">Die Anzahl der empfangenen Anforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="4c428-173">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-174">Erfolgreiche Anforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="4c428-174">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="4c428-175">Die Anzahl der erfolgreichen Anforderungen pro Sekunde (http-2xx/3xx-Antwortcodes)</span><span class="sxs-lookup"><span data-stu-id="4c428-175">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-176">Erfolgreiche Erstellung von Anwendungsanforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="4c428-176">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="4c428-177">Die Anzahl der erfolgreichen Anwendungs Erstellungsanforderungen pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="4c428-177">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-178">Timeout für ausstehende Get-Anzahl</span><span class="sxs-lookup"><span data-stu-id="4c428-178">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="4c428-179">Die Anzahl der ausstehenden ruft dieses Timeout ab.</span><span class="sxs-lookup"><span data-stu-id="4c428-179">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-180">Gesamtzahl der empfangenen Anwendungs Erstellungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="4c428-180">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="4c428-181">Die Gesamtzahl der seit dem Start des Diensts empfangenen Anwendungs Erstellungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="4c428-181">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-182">Gesamtzahl der http-4xx-Antworten</span><span class="sxs-lookup"><span data-stu-id="4c428-182">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="4c428-183">Die Gesamtzahl der http-4xx-Antworten</span><span class="sxs-lookup"><span data-stu-id="4c428-183">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-184">Gesamtzahl der http-5xx-Antworten</span><span class="sxs-lookup"><span data-stu-id="4c428-184">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="4c428-185">Die Gesamtzahl der http-5xx-Antworten</span><span class="sxs-lookup"><span data-stu-id="4c428-185">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-186">Insgesamt empfangene Anforderungen im Befehlskanal</span><span class="sxs-lookup"><span data-stu-id="4c428-186">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="4c428-187">Die Gesamtzahl der über den Befehlskanal empfangenen Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="4c428-187">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-188">Gesamtzahl der erfolgreichen Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4c428-188">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="4c428-189">Die Gesamtzahl der erfolgreichen Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="4c428-189">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-190">Gesamtzahl der initiierten Sitzungen</span><span class="sxs-lookup"><span data-stu-id="4c428-190">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="4c428-191">Die Gesamtzahl der Sitzungen, die seit dem Start des Diensts initiiert wurden.</span><span class="sxs-lookup"><span data-stu-id="4c428-191">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-192">Gesamtzahl der Sitzungen, die aufgrund eines Leerlauftimeouts beendet wurden</span><span class="sxs-lookup"><span data-stu-id="4c428-192">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="4c428-193">Die Gesamtzahl der Sitzungen, die beendet wurden, da das Leerlauftimeout des Benutzers erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="4c428-193">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-194">Insgesamt gedrosselte Anwendungen</span><span class="sxs-lookup"><span data-stu-id="4c428-194">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="4c428-195">Die Anzahl der gedrosselten Anwendungen</span><span class="sxs-lookup"><span data-stu-id="4c428-195">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="4c428-196">Leistungsindikatoren für den MCX-Mobilitätsdienst</span><span class="sxs-lookup"><span data-stu-id="4c428-196">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c428-197">Leistungsindikator</span><span class="sxs-lookup"><span data-stu-id="4c428-197">Counter</span></span></th>
<th><span data-ttu-id="4c428-198">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c428-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c428-199">Durchschnittliche Sitzungsdauer in Millisekunden</span><span class="sxs-lookup"><span data-stu-id="4c428-199">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="4c428-200">Die durchschnittliche Dauer einer Sitzung in Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="4c428-200">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-201">Aktuelle Pushbenachrichtigungsabonnements</span><span class="sxs-lookup"><span data-stu-id="4c428-201">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="4c428-202">Die aktuelle Anzahl von Pushbenachrichtigungsabonnements.</span><span class="sxs-lookup"><span data-stu-id="4c428-202">The current number of push notification subscriptions.</span></span> <span data-ttu-id="4c428-203">Diese Nummer steht in Verbindung mit der Anzahl der derzeit aktiven Sitzungen für die Teilmenge der derzeit aktiven Sitzungen, die für Windows Mobile-oder iPhone-Geräte registriert sind.</span><span class="sxs-lookup"><span data-stu-id="4c428-203">This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-204">Anzahl derzeit aktiver Netzwerkumfragen mit Timeout</span><span class="sxs-lookup"><span data-stu-id="4c428-204">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="4c428-205">Die Anzahl von Netzwerkumfragen, bei denen ein Timeout aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4c428-205">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-206">Anzahl derzeit aktiver Umfragen</span><span class="sxs-lookup"><span data-stu-id="4c428-206">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="4c428-207">Die Anzahl von derzeit aktiven Umfragen (lange gehaltene Verbindungen mit dem Server).</span><span class="sxs-lookup"><span data-stu-id="4c428-207">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-208">Anzahl derzeit aktiver Sitzungen</span><span class="sxs-lookup"><span data-stu-id="4c428-208">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="4c428-209">Die derzeitige Anzahl der im Mobilitätsdienst registrierten Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="4c428-209">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-210">Anzahl derzeit aktiver Sitzungen mit aktiven Anwesenheitsabonnements</span><span class="sxs-lookup"><span data-stu-id="4c428-210">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="4c428-211">Die Anzahl derzeit aktiver Sitzungen mit aktiven Anwesenheitsabonnements.</span><span class="sxs-lookup"><span data-stu-id="4c428-211">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-212">Gescheiterte Pushbenachrichtigungsanforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="4c428-212">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="4c428-213">Die Anzahl der gescheiterten Pushbenachrichtigungsanforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="4c428-213">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-214">Erfolgreiche Pushbenachrichtigungsanforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="4c428-214">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="4c428-215">Die Anzahl der erfolgreichen Pushbenachrichtigungsanforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="4c428-215">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-216">Gedrosselte Pushbenachrichtigungsanforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="4c428-216">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="4c428-217">Die Anzahl der gedrosselten Pushbenachrichtigungsanforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="4c428-217">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-218">Pushbenachrichtigungsanforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="4c428-218">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="4c428-219">Die Anzahl der gesendeten Pushbenachrichtigungsanforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="4c428-219">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-220">Gescheiterte Anforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="4c428-220">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="4c428-221">Die Anzahl der gescheiterten Anforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="4c428-221">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-222">Empfangene Anforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="4c428-222">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="4c428-223">Die Anzahl der empfangenen Anforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="4c428-223">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-224">Abgelehnte Anforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="4c428-224">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="4c428-225">Die Anzahl der abgelehnten Anforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="4c428-225">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-226">Erfolgreiche Anforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="4c428-226">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="4c428-227">Die Anzahl der erfolgreichen Anforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="4c428-227">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-228">Erfolgreiche Anforderungen zur Sitzungsinitiierung/Sekunde</span><span class="sxs-lookup"><span data-stu-id="4c428-228">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="4c428-p102">Die Anzahl der erfolgreichen Anforderungen zur Standortermittlung pro Sekunde. Anforderungen zum Initiieren einer Sitzung beanspruchen die meisten CPU-Ressourcen auf dem Server. Maximal wird eine Last von 12 Anforderungen/Sekunde unterstützt. Die Aufrechterhaltbarkeit hängt von anderen Lasten auf dem Server ab. Das Initiieren einer Sitzung bedeutet normalerweise, dass ein Benutzer angemeldet wird, der für einen längeren Zeitraum abgemeldet war.</span><span class="sxs-lookup"><span data-stu-id="4c428-p102">The per second rate of successful Get Location requests. Requests to initiate a session consume the most CPU on the server. Peak supported load is 12/second. Sustainability depends on other loads on the server. Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-234">Gesamtzahl der abgelehnten eingehenden Sprachanrufe</span><span class="sxs-lookup"><span data-stu-id="4c428-234">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="4c428-235">Die Gesamtzahl der abgelehnten eingehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="4c428-235">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-236">Gesamtzahl der gescheiterten eingehenden Sprachanrufe</span><span class="sxs-lookup"><span data-stu-id="4c428-236">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="4c428-237">Die Gesamtzahl der gescheiterten eingehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="4c428-237">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-238">Gesamtzahl der gescheiterten ausgehenden Sprachanrufe</span><span class="sxs-lookup"><span data-stu-id="4c428-238">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="4c428-239">Die Gesamtzahl der gescheiterten ausgehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="4c428-239">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-240">Gesamtzahl der vom Benutzer beendeten Sitzungen</span><span class="sxs-lookup"><span data-stu-id="4c428-240">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="4c428-241">Die Gesamtzahl der vom Benutzer beendeten Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="4c428-241">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-242">Gesamtzahl der Pushbenachrichtigungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="4c428-242">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="4c428-243">Die Gesamtzahl der Pushbenachrichtigungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="4c428-243">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-244">Gesamtzahl gescheiterter Pushbenachrichtigungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="4c428-244">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="4c428-245">Die Gesamtzahl der gescheiterten Pushbenachrichtigungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="4c428-245">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-246">Gesamtzahl erfolgreicher Pushbenachrichtigungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="4c428-246">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="4c428-247">Die Gesamtzahl der erfolgreichen Pushbenachrichtigungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="4c428-247">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-248">Gesamtzahl gedrosselter Pushbenachrichtigungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="4c428-248">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="4c428-249">Die Gesamtzahl der gedrosselten Pushbenachrichtigungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="4c428-249">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-250">Gesamtzahl der gescheiterten Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4c428-250">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="4c428-251">Die Gesamtzahl der gescheiterten Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="4c428-251">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-252">Gesamtzahl der über den Befehlskanal empfangenen Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4c428-252">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="4c428-253">Die Gesamtzahl der über den Befehlskanal empfangenen Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="4c428-253">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-254">Gesamtzahl der abgelehnten Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4c428-254">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="4c428-255">Die Gesamtzahl der abgelehnten Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="4c428-255">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-256">Gesamtzahl der erfolgreichen Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4c428-256">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="4c428-257">Die Gesamtzahl der an den Mobilitätsdienst gerichteten Anforderungen, die erfolgreich waren.</span><span class="sxs-lookup"><span data-stu-id="4c428-257">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-258">Gesamtzahl der initiierten Sitzungen</span><span class="sxs-lookup"><span data-stu-id="4c428-258">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="4c428-259">Die Gesamtzahl der Sitzungen, die seit dem Start des Mobilitätsdiensts initiiert wurden.</span><span class="sxs-lookup"><span data-stu-id="4c428-259">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-260">Gesamtzahl der Sitzungen, die aufgrund eines Leerlauftimeouts des Benutzers beendet wurden</span><span class="sxs-lookup"><span data-stu-id="4c428-260">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="4c428-261">Die Gesamtzahl der Sitzungen, die beendet wurden, da das Leerlauftimeout des Benutzers erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="4c428-261">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c428-262">Gesamtzahl der erfolgreichen eingehenden Sprachanrufe</span><span class="sxs-lookup"><span data-stu-id="4c428-262">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="4c428-263">Die Gesamtzahl der erfolgreichen eingehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="4c428-263">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c428-264">Gesamtzahl der erfolgreichen ausgehenden Sprachanrufe</span><span class="sxs-lookup"><span data-stu-id="4c428-264">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="4c428-265">Die Gesamtzahl der erfolgreichen ausgehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="4c428-265">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

