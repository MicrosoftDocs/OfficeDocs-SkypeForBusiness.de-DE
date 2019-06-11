---
title: 'Lync Server 2013: Mobilitäts Leistungsindikatoren'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c0759ccd6a9203dfac87f0ec55f555d49d19ccc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827116"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="2c844-102">Mobilitäts Leistungsindikatoren in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c844-102">Mobility performance counters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c844-103">_**Letztes Änderungsdatum des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="2c844-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="2c844-104">In den folgenden Tabellen sind die Namen und Beschreibungen der Leistungsindikatoren aufgeführt, die Sie zum Überwachen von Servern mit der Unified Communications Web-API (UCWA) und dem lync Server 2013 MCX-Mobilitätsdienst verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2c844-104">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="2c844-105">Der Kategoriename für die Leistungsindikatoren in der UCWA-Tabelle ist **LS:WEB – UCWA**.</span><span class="sxs-lookup"><span data-stu-id="2c844-105">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="2c844-106">Der Kategoriename für die Leistungsindikatoren in der Mcx-Mobilitätsdiensttabelle ist **LS:WEB - Mobile Communication Service**.</span><span class="sxs-lookup"><span data-stu-id="2c844-106">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="2c844-107">Leistungsindikatoren für UCWA</span><span class="sxs-lookup"><span data-stu-id="2c844-107">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c844-108">Leistungsindikator</span><span class="sxs-lookup"><span data-stu-id="2c844-108">Counter</span></span></th>
<th><span data-ttu-id="2c844-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c844-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c844-110">Anzahl aktiver Anwendungen</span><span class="sxs-lookup"><span data-stu-id="2c844-110">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="2c844-111">Die aktuelle Anzahl von Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="2c844-111">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-112">Anzahl der aktiven Anwendungsfreigabemodalitäten</span><span class="sxs-lookup"><span data-stu-id="2c844-112">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="2c844-113">Die aktuelle Anzahl der Anwendungsfreigabemodalitäten.</span><span class="sxs-lookup"><span data-stu-id="2c844-113">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-114">Anzahl der aktiven Audiomodalitäten</span><span class="sxs-lookup"><span data-stu-id="2c844-114">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="2c844-115">Die aktuelle Anzahl der Audiomodalitäten.</span><span class="sxs-lookup"><span data-stu-id="2c844-115">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-116">Anzahl der aktiven Datenzusammenarbeitsmodalitäten</span><span class="sxs-lookup"><span data-stu-id="2c844-116">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="2c844-117">Die aktuelle Anzahl der Datenzusammenarbeitsmodalitäten.</span><span class="sxs-lookup"><span data-stu-id="2c844-117">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-118">Wartezeit bei Active Directory-HD-Fotoabruf (ms)</span><span class="sxs-lookup"><span data-stu-id="2c844-118">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="2c844-119">Dieser Leistungsindikator zeigt die durchschnittliche Zeit (in Millisekunden) zum Abrufen eines Fotos aus Active Directory an.</span><span class="sxs-lookup"><span data-stu-id="2c844-119">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-120">Anzahl der aktiven Messaging-Modalitäten</span><span class="sxs-lookup"><span data-stu-id="2c844-120">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="2c844-121">Die aktuelle Anzahl der Messaging-Modalitäten.</span><span class="sxs-lookup"><span data-stu-id="2c844-121">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-122">Anzahl der aktiven Panoramavideomodalitäten</span><span class="sxs-lookup"><span data-stu-id="2c844-122">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="2c844-123">Die aktuelle Anzahl der Panoramavideomodalitäten.</span><span class="sxs-lookup"><span data-stu-id="2c844-123">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-124">Anzahl aktiver ausstehender GET-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2c844-124">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="2c844-125">Die Anzahl der derzeit aktiven ausstehenden GET-Anforderungen; lange gehaltene Verbindungen mit dem Server.</span><span class="sxs-lookup"><span data-stu-id="2c844-125">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-126">Anzahl aktiver Sitzungen</span><span class="sxs-lookup"><span data-stu-id="2c844-126">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="2c844-127">Die aktuelle Gesamtzahl der Endpunkte, die in UCWA pro Anwendung registriert sind.</span><span class="sxs-lookup"><span data-stu-id="2c844-127">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-128">Anzahl aktiver Benutzerinstanzen</span><span class="sxs-lookup"><span data-stu-id="2c844-128">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="2c844-129">Die aktuelle Anzahl von Benutzerinstanzen.</span><span class="sxs-lookup"><span data-stu-id="2c844-129">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-130">Aktive Benutzerinstanzen ohne Anwendung</span><span class="sxs-lookup"><span data-stu-id="2c844-130">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="2c844-131">Die aktuelle Anzahl von Benutzerinstanzen ohne Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2c844-131">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-132">Anzahl der aktiven Videomodalitäten</span><span class="sxs-lookup"><span data-stu-id="2c844-132">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="2c844-133">Die aktuelle Anzahl der Videomodalitäten.</span><span class="sxs-lookup"><span data-stu-id="2c844-133">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-134">Empfangene Anwendungserstellungsanforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="2c844-134">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="2c844-135">Die Rate der empfangenen Anwendungserstellungsanforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="2c844-135">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-136">AS-MCU-Teilnahmefehler</span><span class="sxs-lookup"><span data-stu-id="2c844-136">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="2c844-137">Die Anzahl der AS-MCU-Teilnahmefehler.</span><span class="sxs-lookup"><span data-stu-id="2c844-137">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-138">Audio-Video-MCU-Teilnahmefehler</span><span class="sxs-lookup"><span data-stu-id="2c844-138">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="2c844-139">Die Anzahl der Audio-Video-MCU-Teilnahmefehler.</span><span class="sxs-lookup"><span data-stu-id="2c844-139">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-140">Durchschnittliche Anwendungsstartzeit (ms)</span><span class="sxs-lookup"><span data-stu-id="2c844-140">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="2c844-141">Die durchschnittliche Anwendungsstartzeit in Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="2c844-141">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-142">Durchschnittliche Sitzungsdauer (ms)</span><span class="sxs-lookup"><span data-stu-id="2c844-142">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="2c844-143">Die durchschnittliche Dauer einer Sitzung in Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="2c844-143">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-144">Daten-MCU-Teilnahmefehler</span><span class="sxs-lookup"><span data-stu-id="2c844-144">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="2c844-145">Die Anzahl der Daten-MCU-Teilnahmefehler.</span><span class="sxs-lookup"><span data-stu-id="2c844-145">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-146">Wartezeit bei Exchange-Kontaktsuche (ms)</span><span class="sxs-lookup"><span data-stu-id="2c844-146">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="2c844-147">Dieser Leistungsindikator zeigt die durchschnittliche Zeit (in Millisekunden) bei der Suche eines Kontakts in Exchange an.</span><span class="sxs-lookup"><span data-stu-id="2c844-147">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-148">Wartezeit bei Exchange-HD-Fotoabruf (ms)</span><span class="sxs-lookup"><span data-stu-id="2c844-148">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="2c844-149">Dieser Leistungsindikator zeigt die durchschnittliche Zeit (in Millisekunden) zum Abrufen eines Fotos aus Exchange an.</span><span class="sxs-lookup"><span data-stu-id="2c844-149">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-150">HTTP-4xx-Antworten/Sekunde</span><span class="sxs-lookup"><span data-stu-id="2c844-150">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="2c844-151">Die Rate der Antworten mit dem HTTP-Code 4xx pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="2c844-151">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-152">HTTP-5xx-Antworten/Sekunde</span><span class="sxs-lookup"><span data-stu-id="2c844-152">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="2c844-153">Die Rate der Antworten mit dem HTTP-Code 5xx pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="2c844-153">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-154">Chat-MCU-Teilnahmefehler</span><span class="sxs-lookup"><span data-stu-id="2c844-154">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="2c844-155">Die Anzahl der Chat-MCU-Teilnahmefehler.</span><span class="sxs-lookup"><span data-stu-id="2c844-155">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-156">Anzahl von Fehlern beim Abruf von Fotos aus Active Directory</span><span class="sxs-lookup"><span data-stu-id="2c844-156">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="2c844-157">Die Gesamtzahl der Fehler beim Abrufen von Fotos aus Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2c844-157">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-158">Anzahl von Fehlern bei Kontaktsuche</span><span class="sxs-lookup"><span data-stu-id="2c844-158">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="2c844-159">Die Gesamtzahl von Fehlern bei der Kontaktsuche in Exchange.</span><span class="sxs-lookup"><span data-stu-id="2c844-159">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-160">Anzahl von Deserialisierungsfehlern</span><span class="sxs-lookup"><span data-stu-id="2c844-160">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="2c844-161">Die Gesamtzahl der Deserialisierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="2c844-161">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-162">Anzahl der HD-fotofehler erhalten</span><span class="sxs-lookup"><span data-stu-id="2c844-162">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="2c844-163">Die Gesamtzahl der Fehler beim Abrufen von HD-Fotos aus Exchange.</span><span class="sxs-lookup"><span data-stu-id="2c844-163">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-164">Über Maximum an Abonnements pro Anwendung</span><span class="sxs-lookup"><span data-stu-id="2c844-164">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="2c844-165">Die Anzahl der Abonnementanforderungen über der maximal pro Anwendung erlaubten Anzahl.</span><span class="sxs-lookup"><span data-stu-id="2c844-165">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-166">Über Maximum an Abonnements pro Batch</span><span class="sxs-lookup"><span data-stu-id="2c844-166">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="2c844-167">Die Anzahl der Abonnementanforderungen über der maximal pro Batch erlaubten Anzahl.</span><span class="sxs-lookup"><span data-stu-id="2c844-167">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-168">Fehler beim Abonnieren der Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="2c844-168">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="2c844-169">Die Anzahl der Fehler beim Abonnieren der Anwesenheit.</span><span class="sxs-lookup"><span data-stu-id="2c844-169">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-170">Fehler beim Registrieren von Endpunkten</span><span class="sxs-lookup"><span data-stu-id="2c844-170">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="2c844-171">Die Anzahl der Fehler beim Registrieren von Endpunkten.</span><span class="sxs-lookup"><span data-stu-id="2c844-171">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-172">Empfangene Anforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="2c844-172">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="2c844-173">Die Anzahl der empfangenen Anforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="2c844-173">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-174">Erfolgreiche Anforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="2c844-174">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="2c844-175">Die Anzahl der erfolgreichen Anforderungen pro Sekunde (HTTP-Antwortcodes 2xx/3xx).</span><span class="sxs-lookup"><span data-stu-id="2c844-175">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-176">Erfolgreiche Anwendungserstellungsanforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="2c844-176">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="2c844-177">Die Rate der erfolgreichen Anwendungserstellungsanforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="2c844-177">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-178">Anzahl der GET-Anforderungen mit Timeout</span><span class="sxs-lookup"><span data-stu-id="2c844-178">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="2c844-179">Die Anzahl der ausstehenden GET-Anforderungen, bei denen das Zeitlimit überschritten wurde.</span><span class="sxs-lookup"><span data-stu-id="2c844-179">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-180">Gesamtzahl der empfangenen Anwendungserstellungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="2c844-180">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="2c844-181">Die Gesamtzahl der Anwendungserstellungsanforderungen, die seit dem Start des Diensts empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="2c844-181">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-182">Gesamtzahl der HTTP-4xx-Antworten</span><span class="sxs-lookup"><span data-stu-id="2c844-182">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="2c844-183">Die Gesamtzahl der HTTP-Antworten vom Typ 4xx.</span><span class="sxs-lookup"><span data-stu-id="2c844-183">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-184">Gesamtzahl der HTTP-5xx-Antworten</span><span class="sxs-lookup"><span data-stu-id="2c844-184">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="2c844-185">Die Gesamtzahl der HTTP-Antworten vom Typ 5xx.</span><span class="sxs-lookup"><span data-stu-id="2c844-185">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-186">Gesamtzahl der über den Befehlskanal empfangenen Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2c844-186">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="2c844-187">Die Gesamtzahl der über den Befehlskanal empfangenen Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="2c844-187">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-188">Gesamtzahl der erfolgreichen Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2c844-188">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="2c844-189">Die Gesamtzahl der erfolgreichen Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="2c844-189">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-190">Gesamtzahl der initiierten Sitzungen</span><span class="sxs-lookup"><span data-stu-id="2c844-190">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="2c844-191">Die Gesamtzahl der Sitzungen, die seit dem Start des Diensts initiiert wurden.</span><span class="sxs-lookup"><span data-stu-id="2c844-191">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-192">Gesamtzahl der Sitzungen, die aufgrund eines Leerlauftimeouts beendet wurden</span><span class="sxs-lookup"><span data-stu-id="2c844-192">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="2c844-193">Die Gesamtzahl der Sitzungen, die beendet wurden, da das Leerlauftimeout des Benutzers erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="2c844-193">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-194">Gesamtzahl der gedrosselten Anwendungen</span><span class="sxs-lookup"><span data-stu-id="2c844-194">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="2c844-195">Die Anzahl der gedrosselten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="2c844-195">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="2c844-196">Leistungsindikatoren für den Mcx-Mobilitätsdienst</span><span class="sxs-lookup"><span data-stu-id="2c844-196">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c844-197">Leistungsindikator</span><span class="sxs-lookup"><span data-stu-id="2c844-197">Counter</span></span></th>
<th><span data-ttu-id="2c844-198">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c844-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c844-199">Durchschnittliche Sitzungsdauer in Millisekunden</span><span class="sxs-lookup"><span data-stu-id="2c844-199">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="2c844-200">Die durchschnittliche Dauer einer Sitzung in Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="2c844-200">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-201">Aktuelle Pushbenachrichtigungsabonnements</span><span class="sxs-lookup"><span data-stu-id="2c844-201">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="2c844-p101">Die aktuelle Anzahl von Pushbenachrichtigungsabonnements. Diese Anzahl in Verbindung mit „Anzahl derzeit aktiver Sitzungen“ stellt eine Teilmenge der derzeit aktiven Sitzungen dar, die für Windows Mobile- oder iPhone-Geräte registriert sind.</span><span class="sxs-lookup"><span data-stu-id="2c844-p101">The current number of push notification subscriptions. This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-204">Anzahl derzeit aktiver Netzwerkumfragen mit Timeout</span><span class="sxs-lookup"><span data-stu-id="2c844-204">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="2c844-205">Die Anzahl von Netzwerkumfragen, bei denen ein Timeout aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="2c844-205">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-206">Anzahl derzeit aktiver Umfragen</span><span class="sxs-lookup"><span data-stu-id="2c844-206">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="2c844-207">Die Anzahl von derzeit aktiven Umfragen (lange gehaltene Verbindungen mit dem Server).</span><span class="sxs-lookup"><span data-stu-id="2c844-207">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-208">Anzahl derzeit aktiver Sitzungen</span><span class="sxs-lookup"><span data-stu-id="2c844-208">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="2c844-209">Die derzeitige Anzahl der im Mobilitätsdienst registrierten Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="2c844-209">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-210">Anzahl derzeit aktiver Sitzungen mit aktiven Anwesenheitsabonnements</span><span class="sxs-lookup"><span data-stu-id="2c844-210">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="2c844-211">Die Anzahl derzeit aktiver Sitzungen mit aktiven Anwesenheitsabonnements.</span><span class="sxs-lookup"><span data-stu-id="2c844-211">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-212">Gescheiterte Pushbenachrichtigungsanforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="2c844-212">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="2c844-213">Die Anzahl der gescheiterten Pushbenachrichtigungsanforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="2c844-213">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-214">Erfolgreiche Pushbenachrichtigungsanforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="2c844-214">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="2c844-215">Die Anzahl der erfolgreichen Pushbenachrichtigungsanforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="2c844-215">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-216">Gedrosselte Pushbenachrichtigungsanforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="2c844-216">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="2c844-217">Die Anzahl der gedrosselten Pushbenachrichtigungsanforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="2c844-217">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-218">Pushbenachrichtigungsanforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="2c844-218">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="2c844-219">Die Anzahl der gesendeten Pushbenachrichtigungsanforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="2c844-219">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-220">Gescheiterte Anforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="2c844-220">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="2c844-221">Die Anzahl der gescheiterten Anforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="2c844-221">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-222">Empfangene Anforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="2c844-222">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="2c844-223">Die Anzahl der empfangenen Anforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="2c844-223">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-224">Abgelehnte Anforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="2c844-224">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="2c844-225">Die Anzahl der abgelehnten Anforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="2c844-225">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-226">Erfolgreiche Anforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="2c844-226">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="2c844-227">Die Anzahl der erfolgreichen Anforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="2c844-227">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-228">Erfolgreiche Anforderungen zur Sitzungsinitiierung/Sekunde</span><span class="sxs-lookup"><span data-stu-id="2c844-228">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="2c844-p102">Die Anzahl der erfolgreichen Anforderungen zur Standortermittlung pro Sekunde. Anforderungen zum Initiieren einer Sitzung beanspruchen die meisten CPU-Ressourcen auf dem Server. Maximal wird eine Last von 12 Anforderungen/Sekunde unterstützt. Die Aufrechterhaltbarkeit hängt von anderen Lasten auf dem Server ab. Das Initiieren einer Sitzung bedeutet normalerweise, dass ein Benutzer angemeldet wird, der für einen längeren Zeitraum abgemeldet war.</span><span class="sxs-lookup"><span data-stu-id="2c844-p102">The per second rate of successful Get Location requests. Requests to initiate a session consume the most CPU on the server. Peak supported load is 12/second. Sustainability depends on other loads on the server. Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-234">Gesamtzahl der abgelehnten eingehenden Sprachanrufe</span><span class="sxs-lookup"><span data-stu-id="2c844-234">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="2c844-235">Die Gesamtzahl der abgelehnten eingehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="2c844-235">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-236">Gesamtzahl der gescheiterten eingehenden Sprachanrufe</span><span class="sxs-lookup"><span data-stu-id="2c844-236">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="2c844-237">Die Gesamtzahl der gescheiterten eingehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="2c844-237">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-238">Gesamtzahl der gescheiterten ausgehenden Sprachanrufe</span><span class="sxs-lookup"><span data-stu-id="2c844-238">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="2c844-239">Die Gesamtzahl der gescheiterten ausgehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="2c844-239">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-240">Gesamtzahl der vom Benutzer beendeten Sitzungen</span><span class="sxs-lookup"><span data-stu-id="2c844-240">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="2c844-241">Die Gesamtzahl der vom Benutzer beendeten Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="2c844-241">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-242">Gesamtzahl der Pushbenachrichtigungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="2c844-242">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="2c844-243">Die Gesamtzahl der Pushbenachrichtigungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="2c844-243">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-244">Gesamtzahl gescheiterter Pushbenachrichtigungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="2c844-244">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="2c844-245">Die Gesamtzahl der gescheiterten Pushbenachrichtigungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="2c844-245">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-246">Gesamtzahl erfolgreicher Pushbenachrichtigungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="2c844-246">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="2c844-247">Die Gesamtzahl der erfolgreichen Pushbenachrichtigungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="2c844-247">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-248">Gesamtzahl gedrosselter Pushbenachrichtigungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="2c844-248">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="2c844-249">Die Gesamtzahl der gedrosselten Pushbenachrichtigungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="2c844-249">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-250">Gesamtzahl der gescheiterten Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2c844-250">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="2c844-251">Die Gesamtzahl der gescheiterten Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="2c844-251">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-252">Gesamtzahl der über den Befehlskanal empfangenen Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2c844-252">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="2c844-253">Die Gesamtzahl der über den Befehlskanal empfangenen Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="2c844-253">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-254">Gesamtzahl der abgelehnten Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2c844-254">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="2c844-255">Die Gesamtzahl der abgelehnten Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="2c844-255">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-256">Gesamtzahl der erfolgreichen Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2c844-256">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="2c844-257">Die Gesamtzahl der an den Mobilitätsdienst gerichteten Anforderungen, die erfolgreich waren.</span><span class="sxs-lookup"><span data-stu-id="2c844-257">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-258">Gesamtzahl der initiierten Sitzungen</span><span class="sxs-lookup"><span data-stu-id="2c844-258">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="2c844-259">Die Gesamtzahl der Sitzungen, die seit dem Start des Mobilitätsdiensts initiiert wurden.</span><span class="sxs-lookup"><span data-stu-id="2c844-259">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-260">Gesamtzahl der Sitzungen, die aufgrund eines Leerlauftimeouts des Benutzers beendet wurden</span><span class="sxs-lookup"><span data-stu-id="2c844-260">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="2c844-261">Die Gesamtzahl der Sitzungen, die beendet wurden, da das Leerlauftimeout des Benutzers erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="2c844-261">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c844-262">Gesamtzahl der erfolgreichen eingehenden Sprachanrufe</span><span class="sxs-lookup"><span data-stu-id="2c844-262">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="2c844-263">Die Gesamtzahl der erfolgreichen eingehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="2c844-263">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c844-264">Gesamtzahl der erfolgreichen ausgehenden Sprachanrufe</span><span class="sxs-lookup"><span data-stu-id="2c844-264">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="2c844-265">Die Gesamtzahl der erfolgreichen ausgehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="2c844-265">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

