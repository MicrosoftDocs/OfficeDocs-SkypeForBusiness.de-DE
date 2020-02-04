---
title: 'Lync Server 2013: AppSharingStream-Tabelle'
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
ms.openlocfilehash: c00a606981ab09d370d5aac390aa244a31063f24
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="b0fff-102">AppSharingStream-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0fff-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0fff-103">_**Letztes Änderungsdatum des Themas:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="b0fff-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="b0fff-104">Die AppSharingStream-Tabelle enthält die Qualität der Erfahrungswerte für die netzwerkdatenströme, die für die Anwendungsfreigabe verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b0fff-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="b0fff-105">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b0fff-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0fff-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b0fff-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b0fff-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b0fff-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-111">DateTime</span><span class="sxs-lookup"><span data-stu-id="b0fff-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="b0fff-112">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="b0fff-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0fff-113">Das Datum und die Uhrzeit, zu der die Sitzung gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="b0fff-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-115">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-115">int</span></span></p></td>
<td><p><span data-ttu-id="b0fff-116">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="b0fff-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0fff-117">Sequenzielle Kennung, die verwendet wird, um zwischen Sitzungen zu unterscheiden, die am gleichen Datum und zur gleichen Zeit gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="b0fff-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="b0fff-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b0fff-120">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="b0fff-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b0fff-121">Stellt den Typ der im Anruf verwendeten Videozeile dar.</span><span class="sxs-lookup"><span data-stu-id="b0fff-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="b0fff-122">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="b0fff-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="b0fff-123">0 – Audio</span><span class="sxs-lookup"><span data-stu-id="b0fff-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="b0fff-124">1 – Video</span><span class="sxs-lookup"><span data-stu-id="b0fff-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="b0fff-125">2 – Panorama Video</span><span class="sxs-lookup"><span data-stu-id="b0fff-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="b0fff-126">3 – Anwendung/Desktop Freigabe</span><span class="sxs-lookup"><span data-stu-id="b0fff-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-127"><strong>Datenstrom-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-128">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-128">int</span></span></p></td>
<td><p><span data-ttu-id="b0fff-129">Primary</span><span class="sxs-lookup"><span data-stu-id="b0fff-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="b0fff-130">Eindeutiger Bezeichner des Anwendungsfreigabe Datenstroms.</span><span class="sxs-lookup"><span data-stu-id="b0fff-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-132">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-133">Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="b0fff-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="b0fff-134">(Jitter ist ein Maß für die &quot;Zittern&quot; eines Anrufs.) Starke Jitterwerte werden in der Regel durch Überlastung oder einen überladenen Medienserver verursacht, was zu verzerrten oder verlorenen Audiodaten führt.</span><span class="sxs-lookup"><span data-stu-id="b0fff-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-136">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-137">Maximaler Jitter zwischen den Ankünften des RTP-Pakets.</span><span class="sxs-lookup"><span data-stu-id="b0fff-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="b0fff-138">(Jitter ist ein Maß für die &quot;Zittern&quot; eines Anrufs.) Starke Jitterwerte werden in der Regel durch Überlastung oder einen überladenen Medienserver verursacht, was zu verzerrten oder verlorenen Audiodaten führt.</span><span class="sxs-lookup"><span data-stu-id="b0fff-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-139"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-140">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-p105">Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-Time Transport-Protokoll) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.</span><span class="sxs-lookup"><span data-stu-id="b0fff-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="b0fff-p106">Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="b0fff-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-146">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-147">Der Höchstbetrag (in Millisekunden), der für ein echt Zeit Transport Protokoll Paket erforderlich ist, um zu einem anderen Endpunkt zu wechseln und dann zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="b0fff-147">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="b0fff-148">Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.</span><span class="sxs-lookup"><span data-stu-id="b0fff-148">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="b0fff-p108">Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="b0fff-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-152">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-p109">Die durchschnittliche Rate an RTP-Paketverlusten (Real-Time Transport-Protokoll; ein Protokoll für die Übertragung von Audio und Video über das Internet). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="b0fff-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-157">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-158">Maximale Rate des RTP-Paketverlusts (Real-Time Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="b0fff-158">Maximum rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="b0fff-159">(Paketverlust tritt auf, wenn RTP-Pakete, ein Protokoll, das für die Übertragung von Audio und Video über das Internet verwendet wird, das Ziel nicht erreicht haben.) In der Regel sind die großen Verlustraten auf Engpässe zurückzuführen. mangelnde Bandbreite; WLAN-Überlastung oder Störungen; oder einen überladenen Medienserver.</span><span class="sxs-lookup"><span data-stu-id="b0fff-159">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="b0fff-160">Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="b0fff-160">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-162">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-163">Die Anzahl der gesendeten Pakete.</span><span class="sxs-lookup"><span data-stu-id="b0fff-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-164"><strong>Bandbreite</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-165">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-166">Geschätzte einseitige Bandbreite, die am Ende der Sitzung zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="b0fff-166">Estimated one-way bandwidth available at the end of the session.</span></span> <span data-ttu-id="b0fff-167">In Bits pro Sekunde gemeldet.</span><span class="sxs-lookup"><span data-stu-id="b0fff-167">Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-169">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-170">Beschreibung der Anwendungsfreigabe Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="b0fff-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-172">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-173">Gesamtzahl der unidirektionalen Latenzzeit.</span><span class="sxs-lookup"><span data-stu-id="b0fff-173">Total amount of one-way latency.</span></span> <span data-ttu-id="b0fff-174">Die relative unidirektionale Latenz misst die Verzögerung zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="b0fff-174">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-176">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-177">Durchschnittliche Anzahl der unidirektionalen Latenzzeit.</span><span class="sxs-lookup"><span data-stu-id="b0fff-177">Average amount of one-way latency.</span></span> <span data-ttu-id="b0fff-178">Die relative unidirektionale Latenz misst die Verzögerung zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="b0fff-178">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-180">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-181">Maximale Anzahl von unidirektionalen Latenzzeiten.</span><span class="sxs-lookup"><span data-stu-id="b0fff-181">Maximum amount of one-way latency.</span></span> <span data-ttu-id="b0fff-182">Die relative unidirektionale Latenz misst die Verzögerung zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="b0fff-182">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-184">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-185">Gesamtzahl der einseitigen Burst-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="b0fff-185">Total one-way burst occurrences.</span></span> <span data-ttu-id="b0fff-186">Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen.</span><span class="sxs-lookup"><span data-stu-id="b0fff-186">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="b0fff-187">Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="b0fff-187">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-189">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-190">Totale unidirektionale Burst Dichte.</span><span class="sxs-lookup"><span data-stu-id="b0fff-190">Total one-way burst density.</span></span> <span data-ttu-id="b0fff-191">Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen.</span><span class="sxs-lookup"><span data-stu-id="b0fff-191">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="b0fff-192">Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="b0fff-192">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-194">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-195">Gesamtdauer des einseitigen Bursts.</span><span class="sxs-lookup"><span data-stu-id="b0fff-195">Total one-way burst duration.</span></span> <span data-ttu-id="b0fff-196">Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen.</span><span class="sxs-lookup"><span data-stu-id="b0fff-196">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="b0fff-197">Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="b0fff-197">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-199">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-200">Gesamtanzahl der einseitigen Lücken.</span><span class="sxs-lookup"><span data-stu-id="b0fff-200">Total one-way gap occurrences.</span></span> <span data-ttu-id="b0fff-201">Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Bursts hin.</span><span class="sxs-lookup"><span data-stu-id="b0fff-201">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="b0fff-202">Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="b0fff-202">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-204">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-205">Gesamtdichte für einseitigen Abstand.</span><span class="sxs-lookup"><span data-stu-id="b0fff-205">Total one-way gap density.</span></span> <span data-ttu-id="b0fff-206">Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Bursts hin.</span><span class="sxs-lookup"><span data-stu-id="b0fff-206">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="b0fff-207">Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="b0fff-207">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-209">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-210">Gesamtdauer der einseitigen Lücke</span><span class="sxs-lookup"><span data-stu-id="b0fff-210">Total one-way gap duration.</span></span> <span data-ttu-id="b0fff-211">Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Bursts hin.</span><span class="sxs-lookup"><span data-stu-id="b0fff-211">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="b0fff-212">Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="b0fff-212">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="b0fff-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-215">Anwendungsrolle (mitbenutzender oder Viewer) und Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="b0fff-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-217">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-218">Gesamtverarbeitungszeit für RDP-Kacheln (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="b0fff-218">Total processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="b0fff-219">Eine höhere Gesamtsumme entspricht einer längeren Verzögerung bei der Anzeige.</span><span class="sxs-lookup"><span data-stu-id="b0fff-219">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-221">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-222">Durchschnittliche Verarbeitungszeit für RDP-Kacheln (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="b0fff-222">Average processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="b0fff-223">Eine höhere Gesamtsumme entspricht einer längeren Verzögerung bei der Anzeige.</span><span class="sxs-lookup"><span data-stu-id="b0fff-223">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-225">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-226">Maximale Verarbeitungszeit für RDP-Kacheln (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="b0fff-226">Maximum processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="b0fff-227">Eine höhere Gesamtsumme entspricht einer längeren Verzögerung bei der Anzeige.</span><span class="sxs-lookup"><span data-stu-id="b0fff-227">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-229">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-230">Burst-Vorkommen in der Verarbeitungszeit für RDP-Kacheln (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="b0fff-230">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="b0fff-231">Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen.</span><span class="sxs-lookup"><span data-stu-id="b0fff-231">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-233">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-234">Burst Dichte in der Verarbeitungszeit für RDP-Kacheln (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="b0fff-234">Burst density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="b0fff-235">Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen.</span><span class="sxs-lookup"><span data-stu-id="b0fff-235">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-237">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-238">Burst Dauer in der Verarbeitungszeit für RDP-Kacheln (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="b0fff-238">Burst duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="b0fff-239">Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen.</span><span class="sxs-lookup"><span data-stu-id="b0fff-239">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-241">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-242">Lücken Vorkommen in der Verarbeitungszeit für RDP-Kacheln (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="b0fff-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-244">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-245">Lücken Dichte in der Verarbeitungszeit für RDP-Kacheln (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="b0fff-245">Gap density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="b0fff-246">Eine geringe Spalt Dichte entspricht einer besseren Anzeige Erfahrung.</span><span class="sxs-lookup"><span data-stu-id="b0fff-246">Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-248">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-249">Lücken Dauer in der Verarbeitungszeit für RDP-Kacheln (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="b0fff-249">Gap duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="b0fff-250">Kurze Lücken dauern sind mit einer besseren Anzeige Erfahrung identisch.</span><span class="sxs-lookup"><span data-stu-id="b0fff-250">Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-252">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-253">Gesamtrate der erfassten Kacheln (in Kacheln pro Sekunde)</span><span class="sxs-lookup"><span data-stu-id="b0fff-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-255">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-256">Durchschnittliche Rate der erfassten Kacheln (in Kacheln pro Sekunde)</span><span class="sxs-lookup"><span data-stu-id="b0fff-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-258">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-259">Maximale Rate der erfassten Kacheln (in Kacheln pro Sekunde)</span><span class="sxs-lookup"><span data-stu-id="b0fff-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-261">in t</span><span class="sxs-lookup"><span data-stu-id="b0fff-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-262">Burst-Vorkommen in der Rate der erfassten Kacheln (in Kacheln pro Sekunde)</span><span class="sxs-lookup"><span data-stu-id="b0fff-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-264">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-265">Burst Dichte in der Rate der aufgenommenen Kacheln (in Kacheln pro Sekunde)</span><span class="sxs-lookup"><span data-stu-id="b0fff-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-267">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-268">Burst Dauer in der Rate der erfassten Kacheln (in Kacheln pro Sekunde)</span><span class="sxs-lookup"><span data-stu-id="b0fff-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-270">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-271">Lücken Vorkommen in der Rate der erfassten Kacheln (in Kacheln pro Sekunde)</span><span class="sxs-lookup"><span data-stu-id="b0fff-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-273">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-274">Spalt Dichte in der Rate der erfassten Kacheln (in Kacheln pro Sekunde)</span><span class="sxs-lookup"><span data-stu-id="b0fff-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-276">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-277">Dauer der Lücke in der Rate der erfassten Kacheln (in Kacheln pro Sekunde)</span><span class="sxs-lookup"><span data-stu-id="b0fff-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-279">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-280">Der Gesamtprozentsatz des Inhalts, der den Betrachter nicht erreicht hat, aber stattdessen von neuem Inhalt verworfen und überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="b0fff-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-282">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-283">Der durchschnittliche Prozentsatz des Inhalts, der den Betrachter nicht erreicht hat, aber stattdessen von neuem Inhalt verworfen und überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="b0fff-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-285">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-286">Der maximale Prozentsatz des Inhalts, der den Betrachter nicht erreicht hat, aber stattdessen von neuem Inhalt verworfen und überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="b0fff-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-288">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-289">Burst-Vorkommen für den Inhalt, der den Betrachter nicht erreicht hat, aber stattdessen von neuem Inhalt verworfen und überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="b0fff-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-291">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-292">Burst Dichte für den Inhalt, der den Betrachter nicht erreicht hat, aber stattdessen von neuem Inhalt verworfen und überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="b0fff-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-294">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-295">Burst Dauer für den Inhalt, der den Betrachter nicht erreicht hat, aber stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="b0fff-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-297">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-298">Lücken auftreten für den Inhalt, der den Betrachter nicht erreicht hat, aber stattdessen von neuem Inhalt verworfen und überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="b0fff-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-300">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-301">Lücken Dichte für den Inhalt, der den Betrachter nicht erreicht hat, aber stattdessen von neuem Inhalt verworfen und überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="b0fff-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-303">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-304">Abstands Dauer für den Inhalt, der den Betrachter nicht erreicht hat, aber stattdessen von neuem Inhalt verworfen und überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="b0fff-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-306">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-307">Gesamtzahl der Frames, die aus der grafikquelle ausgekratzt wurden.</span><span class="sxs-lookup"><span data-stu-id="b0fff-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-309">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-310">Die durchschnittliche Anzahl von Frames, die aus der grafikquelle ausgekratzt wurden.</span><span class="sxs-lookup"><span data-stu-id="b0fff-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-312">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-313">Die maximale Anzahl von Frames, die aus der grafikquelle ausgekratzt wurden.</span><span class="sxs-lookup"><span data-stu-id="b0fff-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-315">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-316">Burst-Vorkommen in den Frames, die aus der grafikquelle ausgekratzt wurden.</span><span class="sxs-lookup"><span data-stu-id="b0fff-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-318">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-319">Burst Dichte in den Frames, die aus der grafikquelle ausgekratzt wurden.</span><span class="sxs-lookup"><span data-stu-id="b0fff-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-321">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-322">Burst Dauer in den Frames, die aus der grafikquelle ausgekratzt wurden.</span><span class="sxs-lookup"><span data-stu-id="b0fff-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-324">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-325">Lücken Vorkommen in den Frames, die aus der grafikquelle ausgekratzt wurden.</span><span class="sxs-lookup"><span data-stu-id="b0fff-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-327">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-328">Spalt Dichte in den Frames, die aus der grafikquelle ausgekratzt wurden.</span><span class="sxs-lookup"><span data-stu-id="b0fff-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-330">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-331">Lücken Dauer in den Frames, die aus der grafikquelle ausgekratzt wurden.</span><span class="sxs-lookup"><span data-stu-id="b0fff-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-333">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-334">Gesamtzahl der eingehenden Bilder, wie Sie vom Betrachter empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="b0fff-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-336">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-337">Durchschnittliche eingehende Frame-Rate, wie Sie vom Betrachter empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="b0fff-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-339">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-340">Die maximale eingehende Kachel Rate, wie Sie vom Betrachter empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="b0fff-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-342">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-343">Burst-Vorkommen in der eingehenden Kachel Rate, wie Sie vom Betrachter empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="b0fff-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-345">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-346">Burst Dichte in der eingehenden Kachel Rate, wie Sie vom Betrachter empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="b0fff-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-348">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-349">Burst Dauer in der eingehenden Kachel Rate, wie Sie vom Betrachter empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="b0fff-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-351">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-352">Lücken Vorkommen in der eingehenden Kachel Rate, wie Sie vom Betrachter empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="b0fff-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-354">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-355">Abstands Dichte in der eingehenden Kachel Rate, wie Sie vom Betrachter empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="b0fff-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-357">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-358">Lücken Dauer in der eingehenden Kachel Rate, wie Sie vom Betrachter empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="b0fff-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-360">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-361">Gesamtzahl der eingehenden Bilder, wie Sie vom Betrachter empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="b0fff-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-363">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-364">Durchschnittliche eingehende Frame-Rate, wie Sie vom Betrachter empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="b0fff-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-366">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-367">Die maximale eingehende Frame-Rate, wie Sie vom Betrachter empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="b0fff-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-369">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-370">Burst-Vorkommen in der eingehenden Framerate, wie Sie vom Betrachter empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="b0fff-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-372">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-373">Burst Dichte in der eingehenden Framerate, wie Sie vom Betrachter empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="b0fff-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-375">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-376">Burst Dauer in der eingehenden Framerate, wie Sie vom Betrachter empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="b0fff-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-378">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-379">Lücken Vorkommen in der eingehenden Framerate, wie Sie vom Betrachter empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="b0fff-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-381">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-382">Abstands Dichte in der eingehenden Framerate, wie Sie vom Betrachter empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="b0fff-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-384">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-385">Die Unterbrechungsdauer in der eingehenden Framerate, wie Sie vom Betrachter empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="b0fff-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-387">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-388">Gesamtanzahl der ausgehenden Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="b0fff-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-390">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-391">Durchschnittliche Ausgangs Kachel Rate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="b0fff-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-393">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-394">Maximale Anzahl der ausgehenden Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="b0fff-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-396">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-397">Burst-Vorkommen in der ausgehenden Kachel Rate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="b0fff-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-399">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-400">Burst Dichte in der ausgehenden Kachel Rate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="b0fff-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-402">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-403">Burst Dauer in der ausgehenden Kachel Rate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="b0fff-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-405">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-406">Lücken Vorkommen in der ausgehenden Kachel Rate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="b0fff-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-408">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-409">Abstands Dichte in der ausgehenden Kachel Rate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="b0fff-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-411">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-412">Abstands Dauer in der ausgehenden Kachel Rate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="b0fff-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-414">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-415">Die gesamte Ausgangsbildrate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="b0fff-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-417">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-418">durchschnittliche Ausgangsbildrate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="b0fff-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-420">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-421">Maximale Ausgangsbildrate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="b0fff-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-423">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-424">Burst-Vorkommen in der Ausgangsbildrate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="b0fff-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-426">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-427">Burst Dichte in der Ausgangsbildrate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="b0fff-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-429">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-430">Burst Dauer in der Ausgangsbildrate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="b0fff-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-432">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-433">Lücken Vorkommen in der ausgehenden Framerate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="b0fff-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-435">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-436">Abstands Dichte in der Ausgangsbildrate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="b0fff-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-438">float</span><span class="sxs-lookup"><span data-stu-id="b0fff-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-439">Lücken Dauer in der ausgehenden Framerate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="b0fff-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-441">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-442">Durchschnittliche Höhe der Videoauflösung in Pixeln.</span><span class="sxs-lookup"><span data-stu-id="b0fff-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-444">int</span><span class="sxs-lookup"><span data-stu-id="b0fff-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-445">Durchschnittliche Breite der Videoauflösung in Pixeln.</span><span class="sxs-lookup"><span data-stu-id="b0fff-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-446"><strong>Inbound</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-447">bit</span><span class="sxs-lookup"><span data-stu-id="b0fff-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-448">Durchschnittliche Bildwiederholrate (in Frames pro Sekunde) für eingehende Übertragungen.</span><span class="sxs-lookup"><span data-stu-id="b0fff-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0fff-449"><strong>Ausgehend</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-450">bit</span><span class="sxs-lookup"><span data-stu-id="b0fff-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-451">Durchschnittliche Bildwiederholrate (in Frames pro Sekunde) für ausgehende Übertragungen.</span><span class="sxs-lookup"><span data-stu-id="b0fff-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0fff-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="b0fff-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="b0fff-453">bit</span><span class="sxs-lookup"><span data-stu-id="b0fff-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0fff-454">1 bedeutet, dass die Datenstrom Richtung vom Aufrufer zu aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b0fff-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="b0fff-455">0 bedeutet, dass die Datenstrom Richtung vom aufgerufenen zum Aufrufer ist.</span><span class="sxs-lookup"><span data-stu-id="b0fff-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

