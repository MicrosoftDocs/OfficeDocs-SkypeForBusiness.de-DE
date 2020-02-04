---
title: 'Lync Server 2013: Mobilitäts Leistungsindikatoren'
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
ms.openlocfilehash: 439c179476c89de8a5245e80e26586d42f4f6e3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="d0f60-102">Mobilitäts Leistungsindikatoren in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0f60-102">Mobility performance counters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0f60-103">_**Letztes Änderungsdatum des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="d0f60-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="d0f60-104">In den folgenden Tabellen sind die Namen und Beschreibungen der Leistungsindikatoren aufgeführt, die Sie zum Überwachen von Servern mit der Unified Communications Web-API (UCWA) und dem lync Server 2013 MCX-Mobilitätsdienst verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d0f60-104">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="d0f60-105">Der Kategoriename für die Leistungsindikatoren in der UCWA-Tabelle ist **LS:WEB – UCWA**.</span><span class="sxs-lookup"><span data-stu-id="d0f60-105">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="d0f60-106">Der Kategoriename für die Leistungsindikatoren in der Mcx-Mobilitätsdiensttabelle ist **LS:WEB - Mobile Communication Service**.</span><span class="sxs-lookup"><span data-stu-id="d0f60-106">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="d0f60-107">Leistungsindikatoren für UCWA</span><span class="sxs-lookup"><span data-stu-id="d0f60-107">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0f60-108">Leistungsindikator</span><span class="sxs-lookup"><span data-stu-id="d0f60-108">Counter</span></span></th>
<th><span data-ttu-id="d0f60-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d0f60-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-110">Anzahl aktiver Anwendungen</span><span class="sxs-lookup"><span data-stu-id="d0f60-110">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="d0f60-111">Die aktuelle Anzahl von Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="d0f60-111">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-112">Anzahl der aktiven Anwendungsfreigabemodalitäten</span><span class="sxs-lookup"><span data-stu-id="d0f60-112">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="d0f60-113">Die aktuelle Anzahl der Anwendungsfreigabemodalitäten.</span><span class="sxs-lookup"><span data-stu-id="d0f60-113">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-114">Anzahl der aktiven Audiomodalitäten</span><span class="sxs-lookup"><span data-stu-id="d0f60-114">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="d0f60-115">Die aktuelle Anzahl der Audiomodalitäten.</span><span class="sxs-lookup"><span data-stu-id="d0f60-115">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-116">Anzahl der aktiven Datenzusammenarbeitsmodalitäten</span><span class="sxs-lookup"><span data-stu-id="d0f60-116">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="d0f60-117">Die aktuelle Anzahl der Datenzusammenarbeitsmodalitäten.</span><span class="sxs-lookup"><span data-stu-id="d0f60-117">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-118">Wartezeit bei Active Directory-HD-Fotoabruf (ms)</span><span class="sxs-lookup"><span data-stu-id="d0f60-118">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="d0f60-119">Dieser Leistungsindikator zeigt die durchschnittliche Zeit (in Millisekunden) zum Abrufen eines Fotos aus Active Directory an.</span><span class="sxs-lookup"><span data-stu-id="d0f60-119">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-120">Anzahl der aktiven Messaging-Modalitäten</span><span class="sxs-lookup"><span data-stu-id="d0f60-120">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="d0f60-121">Die aktuelle Anzahl der Messaging-Modalitäten.</span><span class="sxs-lookup"><span data-stu-id="d0f60-121">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-122">Anzahl der aktiven Panoramavideomodalitäten</span><span class="sxs-lookup"><span data-stu-id="d0f60-122">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="d0f60-123">Die aktuelle Anzahl der Panoramavideomodalitäten.</span><span class="sxs-lookup"><span data-stu-id="d0f60-123">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-124">Anzahl aktiver ausstehender GET-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d0f60-124">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="d0f60-125">Die Anzahl der derzeit aktiven ausstehenden GET-Anforderungen; lange gehaltene Verbindungen mit dem Server.</span><span class="sxs-lookup"><span data-stu-id="d0f60-125">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-126">Anzahl aktiver Sitzungen</span><span class="sxs-lookup"><span data-stu-id="d0f60-126">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="d0f60-127">Die aktuelle Gesamtzahl der Endpunkte, die in UCWA pro Anwendung registriert sind.</span><span class="sxs-lookup"><span data-stu-id="d0f60-127">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-128">Anzahl aktiver Benutzerinstanzen</span><span class="sxs-lookup"><span data-stu-id="d0f60-128">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="d0f60-129">Die aktuelle Anzahl von Benutzerinstanzen.</span><span class="sxs-lookup"><span data-stu-id="d0f60-129">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-130">Aktive Benutzerinstanzen ohne Anwendung</span><span class="sxs-lookup"><span data-stu-id="d0f60-130">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="d0f60-131">Die aktuelle Anzahl von Benutzerinstanzen ohne Anwendung.</span><span class="sxs-lookup"><span data-stu-id="d0f60-131">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-132">Anzahl der aktiven Videomodalitäten</span><span class="sxs-lookup"><span data-stu-id="d0f60-132">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="d0f60-133">Die aktuelle Anzahl der Videomodalitäten.</span><span class="sxs-lookup"><span data-stu-id="d0f60-133">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-134">Empfangene Anwendungserstellungsanforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="d0f60-134">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="d0f60-135">Die Rate der empfangenen Anwendungserstellungsanforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="d0f60-135">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-136">AS-MCU-Teilnahmefehler</span><span class="sxs-lookup"><span data-stu-id="d0f60-136">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="d0f60-137">Die Anzahl der AS-MCU-Teilnahmefehler.</span><span class="sxs-lookup"><span data-stu-id="d0f60-137">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-138">Audio-Video-MCU-Teilnahmefehler</span><span class="sxs-lookup"><span data-stu-id="d0f60-138">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="d0f60-139">Die Anzahl der Audio-Video-MCU-Teilnahmefehler.</span><span class="sxs-lookup"><span data-stu-id="d0f60-139">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-140">Durchschnittliche Anwendungsstartzeit (ms)</span><span class="sxs-lookup"><span data-stu-id="d0f60-140">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="d0f60-141">Die durchschnittliche Anwendungsstartzeit in Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="d0f60-141">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-142">Durchschnittliche Sitzungsdauer (ms)</span><span class="sxs-lookup"><span data-stu-id="d0f60-142">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="d0f60-143">Die durchschnittliche Dauer einer Sitzung in Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="d0f60-143">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-144">Daten-MCU-Teilnahmefehler</span><span class="sxs-lookup"><span data-stu-id="d0f60-144">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="d0f60-145">Die Anzahl der Daten-MCU-Teilnahmefehler.</span><span class="sxs-lookup"><span data-stu-id="d0f60-145">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-146">Wartezeit bei Exchange-Kontaktsuche (ms)</span><span class="sxs-lookup"><span data-stu-id="d0f60-146">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="d0f60-147">Dieser Leistungsindikator zeigt die durchschnittliche Zeit (in Millisekunden) bei der Suche eines Kontakts in Exchange an.</span><span class="sxs-lookup"><span data-stu-id="d0f60-147">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-148">Wartezeit bei Exchange-HD-Fotoabruf (ms)</span><span class="sxs-lookup"><span data-stu-id="d0f60-148">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="d0f60-149">Dieser Leistungsindikator zeigt die durchschnittliche Zeit (in Millisekunden) zum Abrufen eines Fotos aus Exchange an.</span><span class="sxs-lookup"><span data-stu-id="d0f60-149">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-150">HTTP-4xx-Antworten/Sekunde</span><span class="sxs-lookup"><span data-stu-id="d0f60-150">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="d0f60-151">Die Rate der Antworten mit dem HTTP-Code 4xx pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="d0f60-151">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-152">HTTP-5xx-Antworten/Sekunde</span><span class="sxs-lookup"><span data-stu-id="d0f60-152">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="d0f60-153">Die Rate der Antworten mit dem HTTP-Code 5xx pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="d0f60-153">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-154">Chat-MCU-Teilnahmefehler</span><span class="sxs-lookup"><span data-stu-id="d0f60-154">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="d0f60-155">Die Anzahl der Chat-MCU-Teilnahmefehler.</span><span class="sxs-lookup"><span data-stu-id="d0f60-155">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-156">Anzahl von Fehlern beim Abruf von Fotos aus Active Directory</span><span class="sxs-lookup"><span data-stu-id="d0f60-156">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="d0f60-157">Die Gesamtzahl der Fehler beim Abrufen von Fotos aus Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d0f60-157">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-158">Anzahl von Fehlern bei Kontaktsuche</span><span class="sxs-lookup"><span data-stu-id="d0f60-158">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="d0f60-159">Die Gesamtzahl von Fehlern bei der Kontaktsuche in Exchange.</span><span class="sxs-lookup"><span data-stu-id="d0f60-159">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-160">Anzahl von Deserialisierungsfehlern</span><span class="sxs-lookup"><span data-stu-id="d0f60-160">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="d0f60-161">Die Gesamtzahl der Deserialisierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="d0f60-161">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-162">Anzahl der HD-fotofehler erhalten</span><span class="sxs-lookup"><span data-stu-id="d0f60-162">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="d0f60-163">Die Gesamtzahl der Fehler beim Abrufen von HD-Fotos aus Exchange.</span><span class="sxs-lookup"><span data-stu-id="d0f60-163">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-164">Über Maximum an Abonnements pro Anwendung</span><span class="sxs-lookup"><span data-stu-id="d0f60-164">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="d0f60-165">Die Anzahl der Abonnementanforderungen über der maximal pro Anwendung erlaubten Anzahl.</span><span class="sxs-lookup"><span data-stu-id="d0f60-165">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-166">Über Maximum an Abonnements pro Batch</span><span class="sxs-lookup"><span data-stu-id="d0f60-166">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="d0f60-167">Die Anzahl der Abonnementanforderungen über der maximal pro Batch erlaubten Anzahl.</span><span class="sxs-lookup"><span data-stu-id="d0f60-167">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-168">Fehler beim Abonnieren der Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="d0f60-168">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="d0f60-169">Die Anzahl der Fehler beim Abonnieren der Anwesenheit.</span><span class="sxs-lookup"><span data-stu-id="d0f60-169">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-170">Fehler beim Registrieren von Endpunkten</span><span class="sxs-lookup"><span data-stu-id="d0f60-170">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="d0f60-171">Die Anzahl der Fehler beim Registrieren von Endpunkten.</span><span class="sxs-lookup"><span data-stu-id="d0f60-171">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-172">Empfangene Anforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="d0f60-172">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="d0f60-173">Die Anzahl der empfangenen Anforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="d0f60-173">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-174">Erfolgreiche Anforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="d0f60-174">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="d0f60-175">Die Anzahl der erfolgreichen Anforderungen pro Sekunde (HTTP-Antwortcodes 2xx/3xx).</span><span class="sxs-lookup"><span data-stu-id="d0f60-175">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-176">Erfolgreiche Anwendungserstellungsanforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="d0f60-176">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="d0f60-177">Die Rate der erfolgreichen Anwendungserstellungsanforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="d0f60-177">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-178">Anzahl der GET-Anforderungen mit Timeout</span><span class="sxs-lookup"><span data-stu-id="d0f60-178">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="d0f60-179">Die Anzahl der ausstehenden GET-Anforderungen, bei denen das Zeitlimit überschritten wurde.</span><span class="sxs-lookup"><span data-stu-id="d0f60-179">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-180">Gesamtzahl der empfangenen Anwendungserstellungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="d0f60-180">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="d0f60-181">Die Gesamtzahl der Anwendungserstellungsanforderungen, die seit dem Start des Diensts empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="d0f60-181">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-182">Gesamtzahl der HTTP-4xx-Antworten</span><span class="sxs-lookup"><span data-stu-id="d0f60-182">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="d0f60-183">Die Gesamtzahl der HTTP-Antworten vom Typ 4xx.</span><span class="sxs-lookup"><span data-stu-id="d0f60-183">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-184">Gesamtzahl der HTTP-5xx-Antworten</span><span class="sxs-lookup"><span data-stu-id="d0f60-184">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="d0f60-185">Die Gesamtzahl der HTTP-Antworten vom Typ 5xx.</span><span class="sxs-lookup"><span data-stu-id="d0f60-185">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-186">Gesamtzahl der über den Befehlskanal empfangenen Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d0f60-186">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="d0f60-187">Die Gesamtzahl der über den Befehlskanal empfangenen Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="d0f60-187">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-188">Gesamtzahl der erfolgreichen Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d0f60-188">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="d0f60-189">Die Gesamtzahl der erfolgreichen Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="d0f60-189">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-190">Gesamtzahl der initiierten Sitzungen</span><span class="sxs-lookup"><span data-stu-id="d0f60-190">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="d0f60-191">Die Gesamtzahl der Sitzungen, die seit dem Start des Diensts initiiert wurden.</span><span class="sxs-lookup"><span data-stu-id="d0f60-191">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-192">Gesamtzahl der Sitzungen, die aufgrund eines Leerlauftimeouts beendet wurden</span><span class="sxs-lookup"><span data-stu-id="d0f60-192">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="d0f60-193">Die Gesamtzahl der Sitzungen, die beendet wurden, da das Leerlauftimeout des Benutzers erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="d0f60-193">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-194">Gesamtzahl der gedrosselten Anwendungen</span><span class="sxs-lookup"><span data-stu-id="d0f60-194">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="d0f60-195">Die Anzahl der gedrosselten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="d0f60-195">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="d0f60-196">Leistungsindikatoren für den Mcx-Mobilitätsdienst</span><span class="sxs-lookup"><span data-stu-id="d0f60-196">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0f60-197">Leistungsindikator</span><span class="sxs-lookup"><span data-stu-id="d0f60-197">Counter</span></span></th>
<th><span data-ttu-id="d0f60-198">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d0f60-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-199">Durchschnittliche Sitzungsdauer in Millisekunden</span><span class="sxs-lookup"><span data-stu-id="d0f60-199">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="d0f60-200">Die durchschnittliche Dauer einer Sitzung in Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="d0f60-200">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-201">Aktuelle Pushbenachrichtigungsabonnements</span><span class="sxs-lookup"><span data-stu-id="d0f60-201">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="d0f60-p101">Die aktuelle Anzahl von Pushbenachrichtigungsabonnements. Diese Anzahl in Verbindung mit „Anzahl derzeit aktiver Sitzungen“ stellt eine Teilmenge der derzeit aktiven Sitzungen dar, die für Windows Mobile- oder iPhone-Geräte registriert sind.</span><span class="sxs-lookup"><span data-stu-id="d0f60-p101">The current number of push notification subscriptions. This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-204">Anzahl derzeit aktiver Netzwerkumfragen mit Timeout</span><span class="sxs-lookup"><span data-stu-id="d0f60-204">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="d0f60-205">Die Anzahl von Netzwerkumfragen, bei denen ein Timeout aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="d0f60-205">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-206">Anzahl derzeit aktiver Umfragen</span><span class="sxs-lookup"><span data-stu-id="d0f60-206">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="d0f60-207">Die Anzahl von derzeit aktiven Umfragen (lange gehaltene Verbindungen mit dem Server).</span><span class="sxs-lookup"><span data-stu-id="d0f60-207">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-208">Anzahl derzeit aktiver Sitzungen</span><span class="sxs-lookup"><span data-stu-id="d0f60-208">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="d0f60-209">Die derzeitige Anzahl der im Mobilitätsdienst registrierten Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="d0f60-209">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-210">Anzahl derzeit aktiver Sitzungen mit aktiven Anwesenheitsabonnements</span><span class="sxs-lookup"><span data-stu-id="d0f60-210">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="d0f60-211">Die Anzahl derzeit aktiver Sitzungen mit aktiven Anwesenheitsabonnements.</span><span class="sxs-lookup"><span data-stu-id="d0f60-211">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-212">Gescheiterte Pushbenachrichtigungsanforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="d0f60-212">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="d0f60-213">Die Anzahl der gescheiterten Pushbenachrichtigungsanforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="d0f60-213">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-214">Erfolgreiche Pushbenachrichtigungsanforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="d0f60-214">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="d0f60-215">Die Anzahl der erfolgreichen Pushbenachrichtigungsanforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="d0f60-215">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-216">Gedrosselte Pushbenachrichtigungsanforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="d0f60-216">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="d0f60-217">Die Anzahl der gedrosselten Pushbenachrichtigungsanforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="d0f60-217">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-218">Pushbenachrichtigungsanforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="d0f60-218">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="d0f60-219">Die Anzahl der gesendeten Pushbenachrichtigungsanforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="d0f60-219">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-220">Gescheiterte Anforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="d0f60-220">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="d0f60-221">Die Anzahl der gescheiterten Anforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="d0f60-221">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-222">Empfangene Anforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="d0f60-222">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="d0f60-223">Die Anzahl der empfangenen Anforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="d0f60-223">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-224">Abgelehnte Anforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="d0f60-224">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="d0f60-225">Die Anzahl der abgelehnten Anforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="d0f60-225">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-226">Erfolgreiche Anforderungen/Sekunde</span><span class="sxs-lookup"><span data-stu-id="d0f60-226">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="d0f60-227">Die Anzahl der erfolgreichen Anforderungen pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="d0f60-227">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-228">Erfolgreiche Anforderungen zur Sitzungsinitiierung/Sekunde</span><span class="sxs-lookup"><span data-stu-id="d0f60-228">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="d0f60-p102">Die Anzahl der erfolgreichen Anforderungen zur Standortermittlung pro Sekunde. Anforderungen zum Initiieren einer Sitzung beanspruchen die meisten CPU-Ressourcen auf dem Server. Maximal wird eine Last von 12 Anforderungen/Sekunde unterstützt. Die Aufrechterhaltbarkeit hängt von anderen Lasten auf dem Server ab. Das Initiieren einer Sitzung bedeutet normalerweise, dass ein Benutzer angemeldet wird, der für einen längeren Zeitraum abgemeldet war.</span><span class="sxs-lookup"><span data-stu-id="d0f60-p102">The per second rate of successful Get Location requests. Requests to initiate a session consume the most CPU on the server. Peak supported load is 12/second. Sustainability depends on other loads on the server. Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-234">Gesamtzahl der abgelehnten eingehenden Sprachanrufe</span><span class="sxs-lookup"><span data-stu-id="d0f60-234">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="d0f60-235">Die Gesamtzahl der abgelehnten eingehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="d0f60-235">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-236">Gesamtzahl der gescheiterten eingehenden Sprachanrufe</span><span class="sxs-lookup"><span data-stu-id="d0f60-236">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="d0f60-237">Die Gesamtzahl der gescheiterten eingehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="d0f60-237">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-238">Gesamtzahl der gescheiterten ausgehenden Sprachanrufe</span><span class="sxs-lookup"><span data-stu-id="d0f60-238">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="d0f60-239">Die Gesamtzahl der gescheiterten ausgehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="d0f60-239">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-240">Gesamtzahl der vom Benutzer beendeten Sitzungen</span><span class="sxs-lookup"><span data-stu-id="d0f60-240">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="d0f60-241">Die Gesamtzahl der vom Benutzer beendeten Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="d0f60-241">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-242">Gesamtzahl der Pushbenachrichtigungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="d0f60-242">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="d0f60-243">Die Gesamtzahl der Pushbenachrichtigungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="d0f60-243">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-244">Gesamtzahl gescheiterter Pushbenachrichtigungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="d0f60-244">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="d0f60-245">Die Gesamtzahl der gescheiterten Pushbenachrichtigungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="d0f60-245">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-246">Gesamtzahl erfolgreicher Pushbenachrichtigungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="d0f60-246">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="d0f60-247">Die Gesamtzahl der erfolgreichen Pushbenachrichtigungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="d0f60-247">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-248">Gesamtzahl gedrosselter Pushbenachrichtigungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="d0f60-248">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="d0f60-249">Die Gesamtzahl der gedrosselten Pushbenachrichtigungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="d0f60-249">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-250">Gesamtzahl der gescheiterten Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d0f60-250">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="d0f60-251">Die Gesamtzahl der gescheiterten Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="d0f60-251">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-252">Gesamtzahl der über den Befehlskanal empfangenen Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d0f60-252">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="d0f60-253">Die Gesamtzahl der über den Befehlskanal empfangenen Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="d0f60-253">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-254">Gesamtzahl der abgelehnten Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d0f60-254">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="d0f60-255">Die Gesamtzahl der abgelehnten Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="d0f60-255">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-256">Gesamtzahl der erfolgreichen Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d0f60-256">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="d0f60-257">Die Gesamtzahl der an den Mobilitätsdienst gerichteten Anforderungen, die erfolgreich waren.</span><span class="sxs-lookup"><span data-stu-id="d0f60-257">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-258">Gesamtzahl der initiierten Sitzungen</span><span class="sxs-lookup"><span data-stu-id="d0f60-258">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="d0f60-259">Die Gesamtzahl der Sitzungen, die seit dem Start des Mobilitätsdiensts initiiert wurden.</span><span class="sxs-lookup"><span data-stu-id="d0f60-259">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-260">Gesamtzahl der Sitzungen, die aufgrund eines Leerlauftimeouts des Benutzers beendet wurden</span><span class="sxs-lookup"><span data-stu-id="d0f60-260">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="d0f60-261">Die Gesamtzahl der Sitzungen, die beendet wurden, da das Leerlauftimeout des Benutzers erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="d0f60-261">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0f60-262">Gesamtzahl der erfolgreichen eingehenden Sprachanrufe</span><span class="sxs-lookup"><span data-stu-id="d0f60-262">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="d0f60-263">Die Gesamtzahl der erfolgreichen eingehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="d0f60-263">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0f60-264">Gesamtzahl der erfolgreichen ausgehenden Sprachanrufe</span><span class="sxs-lookup"><span data-stu-id="d0f60-264">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="d0f60-265">Die Gesamtzahl der erfolgreichen ausgehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="d0f60-265">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

