---
title: 'Lync Server 2013: AppSharingStream-Tabelle'
description: 'Lync Server 2013: AppSharingStream-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b530af5b489e090e5d0d00fbb01b2b950bafbe5a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574721"
---
# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="05a15-103">AppSharingStream-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05a15-103">AppSharingStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05a15-104">_**Letztes Änderungsstand des Themas:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="05a15-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="05a15-105">Die AppSharingStream-Tabelle enthält Metriken für die Qualität der Erfahrung für die Netzwerkstreams, die für die Anwendungsfreigabe verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="05a15-105">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="05a15-106">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="05a15-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05a15-107"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="05a15-108"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="05a15-109"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="05a15-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05a15-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-112">dateTime</span><span class="sxs-lookup"><span data-stu-id="05a15-112">dateTime</span></span></p></td>
<td><p><span data-ttu-id="05a15-113">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="05a15-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="05a15-114">Datum und Uhrzeit des Sitzungsbeginns.</span><span class="sxs-lookup"><span data-stu-id="05a15-114">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-116">int</span><span class="sxs-lookup"><span data-stu-id="05a15-116">int</span></span></p></td>
<td><p><span data-ttu-id="05a15-117">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="05a15-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="05a15-118">Sequenzielle ID, anhand der zwischen Sitzungen unterschieden wird, die an denselben Tag und zur derselben Uhrzeit gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="05a15-118">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="05a15-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="05a15-121">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="05a15-121">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="05a15-p102">Stellt den Videozeilentyp dar, der bei dem Anruf verwendet wurde. Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="05a15-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="05a15-124">0 – Audio</span><span class="sxs-lookup"><span data-stu-id="05a15-124">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="05a15-125">1 – Video</span><span class="sxs-lookup"><span data-stu-id="05a15-125">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="05a15-126">2 -- Panoramavideo</span><span class="sxs-lookup"><span data-stu-id="05a15-126">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="05a15-127">3 – Anwendungs-/Desktop Freigabe</span><span class="sxs-lookup"><span data-stu-id="05a15-127">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-128"><strong>Datenstrom-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-128"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-129">int</span><span class="sxs-lookup"><span data-stu-id="05a15-129">int</span></span></p></td>
<td><p><span data-ttu-id="05a15-130">Primary</span><span class="sxs-lookup"><span data-stu-id="05a15-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="05a15-131">Eindeutige ID des Anwendungsfreigabe-Datenstroms.</span><span class="sxs-lookup"><span data-stu-id="05a15-131">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-132"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-132"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-133">int</span><span class="sxs-lookup"><span data-stu-id="05a15-133">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-134">Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="05a15-134">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="05a15-135">(Jitter ist ein Maß für die &quot; Zittern eines &quot; Aufrufs.) Hohe Jitter-Werte werden normalerweise durch Überlastung oder einen überladenen Medienserver verursacht und führen zu verzerrten oder verlorenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="05a15-135">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-136"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-136"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-137">int</span><span class="sxs-lookup"><span data-stu-id="05a15-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-138">Der maximale Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="05a15-138">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="05a15-139">(Jitter ist ein Maß für die &quot; Zittern eines &quot; Aufrufs.) Hohe Jitter-Werte werden normalerweise durch Überlastung oder einen überladenen Medienserver verursacht und führen zu verzerrten oder verlorenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="05a15-139">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-140"><strong>Roundtrip</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-140"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-141">int</span><span class="sxs-lookup"><span data-stu-id="05a15-141">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-p105">Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-Time Transport-Protokoll) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.</span><span class="sxs-lookup"><span data-stu-id="05a15-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="05a15-p106">Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="05a15-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-146"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-146"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-147">int</span><span class="sxs-lookup"><span data-stu-id="05a15-147">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-p107">Die maximale Zeit (in Millisekunden), die ein RTP-Paket (Real-Time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.</span><span class="sxs-lookup"><span data-stu-id="05a15-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="05a15-p108">Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="05a15-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-152"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-152"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-153">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-p109">Die durchschnittliche Rate an RTP-Paketverlusten (Real-Time Transport-Protokoll; ein Protokoll für die Übertragung von Audio und Video über das Internet). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="05a15-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-157"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-157"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-158">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-158">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-p110">Die maximale Rate an RTP-Paketverlusten (Real-Time Transport-Protokoll). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="05a15-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-162"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-162"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-163">int</span><span class="sxs-lookup"><span data-stu-id="05a15-163">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-164">Die Anzahl der gesendeten Pakete.</span><span class="sxs-lookup"><span data-stu-id="05a15-164">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-165"><strong>Bandbreite</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-165"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-166">int</span><span class="sxs-lookup"><span data-stu-id="05a15-166">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-p111">Die geschätzte unidirektionale Bandbreite, die am Ende der Sitzung verfügbar ist (in Bits pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="05a15-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-169"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-169"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-170">int</span><span class="sxs-lookup"><span data-stu-id="05a15-170">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-171">Beschreibung der Anwendungsfreigabe-Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="05a15-171">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-172"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-172"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-173">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-173">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-p112">Gesamter Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="05a15-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-176"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-176"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-177">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-177">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-p113">Durchschnittlicher Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="05a15-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-180"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-180"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-181">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-181">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-p114">Maximaler Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="05a15-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-184"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-184"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-185">int</span><span class="sxs-lookup"><span data-stu-id="05a15-185">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-p115">Undirektionale Burstvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="05a15-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-189"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-189"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-190">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-190">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-p116">Undirektionale Burstdichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="05a15-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-194"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-194"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-195">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-195">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-p117">Undirektionale Burstdauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="05a15-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-199"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-199"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-200">int</span><span class="sxs-lookup"><span data-stu-id="05a15-200">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-p118">Undirektionale Lückenvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="05a15-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-204"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-204"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-205">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-205">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-p119">Undirektionale Lückendichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="05a15-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-209"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-209"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-210">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-210">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-p120">Undirektionale Lückendauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="05a15-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-214"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-214"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-215">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="05a15-215">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-216">Anwendungsrolle (Freigebender Benutzer oder Betrachter) und Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="05a15-216">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-217"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-217"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-218">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-218">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-p121">Gesamte Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je höher der Gesamtwert, desto länger die Verzögerung bei der Wiedergabe.</span><span class="sxs-lookup"><span data-stu-id="05a15-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-221"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-221"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-222">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-222">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-p122">Durchschnittliche Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je höher der Gesamtwert, desto länger die Verzögerung bei der Wiedergabe.</span><span class="sxs-lookup"><span data-stu-id="05a15-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-225"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-225"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-226">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-226">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-p123">Maximale Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je höher der Gesamtwert, desto länger die Verzögerung bei der Wiedergabe.</span><span class="sxs-lookup"><span data-stu-id="05a15-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-229"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-229"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-230">int</span><span class="sxs-lookup"><span data-stu-id="05a15-230">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-p124">Burstvorkommen in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="05a15-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-233"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-233"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-234">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-234">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-p125">Burstdichte in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="05a15-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-237"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-237"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-238">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-238">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-p126">Burstdauer in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="05a15-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-241"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-241"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-242">int</span><span class="sxs-lookup"><span data-stu-id="05a15-242">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-243">Lückenvorkommen in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP).</span><span class="sxs-lookup"><span data-stu-id="05a15-243">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-244"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-244"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-245">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-245">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-p127">Lückendichte in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je geringer die Lückendichte, desto besser das Wiedergabeerlebnis.</span><span class="sxs-lookup"><span data-stu-id="05a15-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-248"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-248"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-249">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-249">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-p128">Lückendauer in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je kürzer die Lückendauer, desto besser das Wiedergabeerlebnis.</span><span class="sxs-lookup"><span data-stu-id="05a15-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-252"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-252"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-253">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-254">Gesamtrate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="05a15-254">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-255"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-255"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-256">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-257">Durchschnittliche Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="05a15-257">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-258"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-258"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-259">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-259">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-260">Maximale Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="05a15-260">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-261"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-261"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-262">int</span><span class="sxs-lookup"><span data-stu-id="05a15-262">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-263">Burstvorkommen in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="05a15-263">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-264"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-264"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-265">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-265">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-266">Burstdichte in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="05a15-266">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-267"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-267"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-268">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-268">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-269">Burstdauer in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="05a15-269">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-270"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-270"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-271">int</span><span class="sxs-lookup"><span data-stu-id="05a15-271">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-272">Lückenvorkommen in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="05a15-272">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-273"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-273"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-274">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-275">Lückendichte in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="05a15-275">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-276"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-276"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-277">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-277">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-278">Lückendauer in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="05a15-278">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-279"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-279"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-280">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-281">Gesamtprozentsatz des Inhalts, der nicht angezeigt, sondern stattdessen verworfen und durch aktuellen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="05a15-281">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-282"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-282"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-283">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-283">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-284">Durchschnittlicher Prozentsatz des Inhalts, der nicht angezeigt, sondern stattdessen verworfen und durch aktuellen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="05a15-284">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-285"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-285"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-286">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-287">Maximaler Prozentsatz des Inhalts, der nicht angezeigt, sondern stattdessen verworfen und durch aktuellen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="05a15-287">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-288"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-288"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-289">int</span><span class="sxs-lookup"><span data-stu-id="05a15-289">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-290">Burstvorkommen für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch aktuellen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="05a15-290">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-291"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-291"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-292">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-293">Burstdichte für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="05a15-293">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-294"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-294"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-295">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-295">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-296">Burstdauer für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="05a15-296">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-297"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-297"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-298">int</span><span class="sxs-lookup"><span data-stu-id="05a15-298">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-299">Lückenvorkommen für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="05a15-299">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-300"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-300"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-301">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-302">Lückendichte für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="05a15-302">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-303"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-303"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-304">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-304">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-305">Lückendauer für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="05a15-305">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-306"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-306"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-307">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-308">Gesamtanzahl der Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="05a15-308">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-309"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-309"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-310">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-310">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-311">Durchschnittliche Anzahl der Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="05a15-311">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-312"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-312"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-313">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-313">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-314">Maximale Anzahl der Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="05a15-314">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-315"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-315"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-316">int</span><span class="sxs-lookup"><span data-stu-id="05a15-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-317">Burstvorkommen in den Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="05a15-317">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-318"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-318"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-319">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-320">Burstdichte in den Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="05a15-320">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-321"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-321"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-322">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-322">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-323">Burstdauer in den Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="05a15-323">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-324"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-324"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-325">int</span><span class="sxs-lookup"><span data-stu-id="05a15-325">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-326">Lückenvorkommen in den Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="05a15-326">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-327"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-327"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-328">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-328">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-329">Lückendichte in den Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="05a15-329">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-330"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-330"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-331">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-332">Lückendauer in den Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="05a15-332">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-333"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-333"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-334">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-334">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-335">Rate eingehender Frames insgesamt, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="05a15-335">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-336"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-336"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-337">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-337">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-338">Durchschnittliche Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="05a15-338">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-339"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-339"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-340">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-340">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-341">Durchschnittliche Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="05a15-341">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-342"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-342"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-343">int</span><span class="sxs-lookup"><span data-stu-id="05a15-343">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-344">Burstvorkommen in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="05a15-344">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-345"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-345"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-346">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-346">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-347">Burstdichte in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="05a15-347">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-348"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-348"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-349">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-350">Burstdauer in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="05a15-350">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-351"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-351"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-352">int</span><span class="sxs-lookup"><span data-stu-id="05a15-352">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-353">Lückenvorkommen in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="05a15-353">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-354"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-354"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-355">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-355">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-356">Lückendichte in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="05a15-356">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-357"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-357"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-358">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-358">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-359">Lückendauer in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="05a15-359">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-360"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-360"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-361">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-361">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-362">Rate eingehender Frames insgesamt, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="05a15-362">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-363"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-363"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-364">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-364">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-365">Durchschnittliche Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="05a15-365">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-366"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-366"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-367">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-367">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-368">Durchschnittliche Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="05a15-368">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-369"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-369"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-370">int</span><span class="sxs-lookup"><span data-stu-id="05a15-370">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-371">Burstvorkommen in der Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="05a15-371">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-372"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-372"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-373">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-374">Burstdichte in der Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="05a15-374">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-375"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-375"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-376">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-376">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-377">Burstdauer in der Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="05a15-377">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-378"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-378"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-379">int</span><span class="sxs-lookup"><span data-stu-id="05a15-379">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-380">Lückenvorkommen in der Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="05a15-380">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-381"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-381"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-382">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-382">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-383">Lückendichte in der Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="05a15-383">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-384"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-384"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-385">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-386">Lückendauer in der Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="05a15-386">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-387"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-387"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-388">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-388">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-389">Rate ausgehender Kacheln insgesamt für den Absender.</span><span class="sxs-lookup"><span data-stu-id="05a15-389">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-390"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-390"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-391">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-391">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-392">Durchschnittliche Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="05a15-392">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-393"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-393"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-394">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-394">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-395">Maximale Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="05a15-395">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-396"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-396"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-397">int</span><span class="sxs-lookup"><span data-stu-id="05a15-397">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-398">Burstvorkommen in der Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="05a15-398">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-399"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-399"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-400">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-400">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-401">Burstdichte in der Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="05a15-401">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-402"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-402"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-403">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-403">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-404">Burstdauer in der Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="05a15-404">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-405"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-405"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-406">int</span><span class="sxs-lookup"><span data-stu-id="05a15-406">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-407">Lückenvorkommen in der Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="05a15-407">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-408"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-408"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-409">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-409">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-410">Lückendichte in der Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="05a15-410">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-411"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-411"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-412">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-412">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-413">Lückendauer in der Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="05a15-413">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-414"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-414"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-415">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-415">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-416">Rate ausgehender Frames insgesamt für den Absender.</span><span class="sxs-lookup"><span data-stu-id="05a15-416">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-417"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-417"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-418">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-418">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-419">Durchschnittliche Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="05a15-419">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-420"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-420"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-421">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-421">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-422">Maximale Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="05a15-422">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-423"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-423"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-424">int</span><span class="sxs-lookup"><span data-stu-id="05a15-424">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-425">Burstvorkommen in der Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="05a15-425">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-426"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-426"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-427">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-427">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-428">Burstdichte in der Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="05a15-428">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-429"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-429"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-430">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-430">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-431">Burstdauer in der Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="05a15-431">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-432"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-432"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-433">int</span><span class="sxs-lookup"><span data-stu-id="05a15-433">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-434">Lückenvorkommen in der Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="05a15-434">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-435"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-435"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-436">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-436">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-437">Lückendichte in der Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="05a15-437">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-438"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-438"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-439">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="05a15-439">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-440">Lückendauer in der Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="05a15-440">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-441"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-441"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-442">int</span><span class="sxs-lookup"><span data-stu-id="05a15-442">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-443">Durchschnittliche Höhe der Videoauflösung in Pixeln.</span><span class="sxs-lookup"><span data-stu-id="05a15-443">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-444"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-444"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-445">int</span><span class="sxs-lookup"><span data-stu-id="05a15-445">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-446">Durchschnittliche Breite der Videoauflösung in Pixeln.</span><span class="sxs-lookup"><span data-stu-id="05a15-446">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-447"><strong>Eingehende</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-447"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-448">Bit</span><span class="sxs-lookup"><span data-stu-id="05a15-448">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-449">Durchschnittliche Framerate (in Frames pro Sekunde) für eingehende Übertragungen.</span><span class="sxs-lookup"><span data-stu-id="05a15-449">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a15-450"><strong>Ausgehende</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-450"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-451">Bit</span><span class="sxs-lookup"><span data-stu-id="05a15-451">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-452">Durchschnittliche Framerate (in Frames pro Sekunde) für ausgehende Übertragungen.</span><span class="sxs-lookup"><span data-stu-id="05a15-452">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a15-453"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="05a15-453"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="05a15-454">Bit</span><span class="sxs-lookup"><span data-stu-id="05a15-454">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a15-455">1 bedeutet, dass die Betrachter vom Anrufer zum Angerufenen verläuft.</span><span class="sxs-lookup"><span data-stu-id="05a15-455">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="05a15-456">0 bedeutet, dass die Datenstromrichtung vom Angerufenen zum Anrufer verläuft.</span><span class="sxs-lookup"><span data-stu-id="05a15-456">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

