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
ms.openlocfilehash: 4454b7fbcaffc1fc302d5c434666cfdfa93ada36
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="9f899-102">AppSharingStream-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f899-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f899-103">_**Letztes Änderungsstand des Themas:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="9f899-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="9f899-104">Die AppSharingStream-Tabelle enthält Metriken für die Qualität der Erfahrung für die Netzwerkstreams, die für die Anwendungsfreigabe verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9f899-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="9f899-105">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9f899-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f899-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="9f899-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="9f899-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="9f899-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f899-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="9f899-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="9f899-112">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="9f899-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9f899-113">Datum und Uhrzeit des Sitzungsbeginns.</span><span class="sxs-lookup"><span data-stu-id="9f899-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-115">int</span><span class="sxs-lookup"><span data-stu-id="9f899-115">int</span></span></p></td>
<td><p><span data-ttu-id="9f899-116">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="9f899-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9f899-117">Sequenzielle ID, anhand der zwischen Sitzungen unterschieden wird, die an denselben Tag und zur derselben Uhrzeit gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="9f899-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="9f899-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9f899-120">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="9f899-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9f899-p102">Stellt den Videozeilentyp dar, der bei dem Anruf verwendet wurde. Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="9f899-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="9f899-123">0 – Audio</span><span class="sxs-lookup"><span data-stu-id="9f899-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="9f899-124">1 – Video</span><span class="sxs-lookup"><span data-stu-id="9f899-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="9f899-125">2 -- Panoramavideo</span><span class="sxs-lookup"><span data-stu-id="9f899-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="9f899-126">3 – Anwendungs-/Desktop Freigabe</span><span class="sxs-lookup"><span data-stu-id="9f899-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-127"><strong>Datenstrom-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-128">int</span><span class="sxs-lookup"><span data-stu-id="9f899-128">int</span></span></p></td>
<td><p><span data-ttu-id="9f899-129">Primary</span><span class="sxs-lookup"><span data-stu-id="9f899-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="9f899-130">Eindeutige ID des Anwendungsfreigabe-Datenstroms.</span><span class="sxs-lookup"><span data-stu-id="9f899-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-132">int</span><span class="sxs-lookup"><span data-stu-id="9f899-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-133">Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="9f899-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="9f899-134">(Jitter ist ein Maß für die &quot;Zittern&quot; eines Aufrufs.) Hohe Jitter-Werte werden normalerweise durch Überlastung oder einen überladenen Medienserver verursacht und führen zu verzerrten oder verlorenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="9f899-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-136">int</span><span class="sxs-lookup"><span data-stu-id="9f899-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-137">Der maximale Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="9f899-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="9f899-138">(Jitter ist ein Maß für die &quot;Zittern&quot; eines Aufrufs.) Hohe Jitter-Werte werden normalerweise durch Überlastung oder einen überladenen Medienserver verursacht und führen zu verzerrten oder verlorenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="9f899-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-139"><strong>Roundtrip</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-140">int</span><span class="sxs-lookup"><span data-stu-id="9f899-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-p105">Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-Time Transport-Protokoll) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.</span><span class="sxs-lookup"><span data-stu-id="9f899-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="9f899-p106">Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routing konfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="9f899-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-146">int</span><span class="sxs-lookup"><span data-stu-id="9f899-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-p107">Die maximale Zeit (in Millisekunden), die ein RTP-Paket (Real-Time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.</span><span class="sxs-lookup"><span data-stu-id="9f899-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="9f899-p108">Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="9f899-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-152">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-p109">Die durchschnittliche Rate an RTP-Paketverlusten (Real-Time Transport-Protokoll; ein Protokoll für die Übertragung von Audio und Video über das Internet). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="9f899-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-157">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-p110">Die maximale Rate an RTP-Paketverlusten (Real-Time Transport-Protokoll). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="9f899-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-162">int</span><span class="sxs-lookup"><span data-stu-id="9f899-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-163">Die Anzahl der gesendeten Pakete.</span><span class="sxs-lookup"><span data-stu-id="9f899-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-164"><strong>Bandbreite</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-165">int</span><span class="sxs-lookup"><span data-stu-id="9f899-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-p111">Die geschätzte unidirektionale Bandbreite, die am Ende der Sitzung verfügbar ist (in Bits pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="9f899-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-169">int</span><span class="sxs-lookup"><span data-stu-id="9f899-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-170">Beschreibung der Anwendungsfreigabe-Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="9f899-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-172">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-p112">Gesamter Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="9f899-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-176">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-p113">Durchschnittlicher Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="9f899-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-180">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-p114">Maximaler Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="9f899-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-184">int</span><span class="sxs-lookup"><span data-stu-id="9f899-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-p115">Undirektionale Burstvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="9f899-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-189">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-p116">Undirektionale Burstdichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="9f899-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-194">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-p117">Undirektionale Burstdauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="9f899-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-199">int</span><span class="sxs-lookup"><span data-stu-id="9f899-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-p118">Undirektionale Lückenvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="9f899-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-204">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-p119">Undirektionale Lückendichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="9f899-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-209">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-p120">Undirektionale Lückendauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="9f899-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="9f899-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-215">Anwendungsrolle (Freigebender Benutzer oder Betrachter) und Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="9f899-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-217">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-p121">Gesamte Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je höher der Gesamtwert, desto länger die Verzögerung bei der Wiedergabe.</span><span class="sxs-lookup"><span data-stu-id="9f899-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-221">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-p122">Durchschnittliche Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je höher der Gesamtwert, desto länger die Verzögerung bei der Wiedergabe.</span><span class="sxs-lookup"><span data-stu-id="9f899-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-225">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-p123">Maximale Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je höher der Gesamtwert, desto länger die Verzögerung bei der Wiedergabe.</span><span class="sxs-lookup"><span data-stu-id="9f899-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-229">int</span><span class="sxs-lookup"><span data-stu-id="9f899-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-p124">Burstvorkommen in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="9f899-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-233">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-p125">Burstdichte in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="9f899-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-237">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-p126">Burstdauer in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="9f899-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-241">int</span><span class="sxs-lookup"><span data-stu-id="9f899-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-242">Lückenvorkommen in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP).</span><span class="sxs-lookup"><span data-stu-id="9f899-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-244">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-p127">Lückendichte in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je geringer die Lückendichte, desto besser das Wiedergabeerlebnis.</span><span class="sxs-lookup"><span data-stu-id="9f899-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-248">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-p128">Lückendauer in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je kürzer die Lückendauer, desto besser das Wiedergabeerlebnis.</span><span class="sxs-lookup"><span data-stu-id="9f899-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-252">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-253">Gesamtrate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="9f899-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-255">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-256">Durchschnittliche Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="9f899-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-258">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-259">Maximale Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="9f899-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-261">int</span><span class="sxs-lookup"><span data-stu-id="9f899-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-262">Burstvorkommen in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="9f899-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-264">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-265">Burstdichte in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="9f899-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-267">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-268">Burstdauer in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="9f899-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-270">int</span><span class="sxs-lookup"><span data-stu-id="9f899-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-271">Lückenvorkommen in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="9f899-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-273">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-274">Lückendichte in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="9f899-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-276">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-277">Lückendauer in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="9f899-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-279">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-280">Gesamtprozentsatz des Inhalts, der nicht angezeigt, sondern stattdessen verworfen und durch aktuellen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="9f899-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-282">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-283">Durchschnittlicher Prozentsatz des Inhalts, der nicht angezeigt, sondern stattdessen verworfen und durch aktuellen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="9f899-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-285">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-286">Maximaler Prozentsatz des Inhalts, der nicht angezeigt, sondern stattdessen verworfen und durch aktuellen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="9f899-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-288">int</span><span class="sxs-lookup"><span data-stu-id="9f899-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-289">Burstvorkommen für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch aktuellen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="9f899-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-291">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-292">Burstdichte für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="9f899-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-294">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-295">Burstdauer für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="9f899-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-297">int</span><span class="sxs-lookup"><span data-stu-id="9f899-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-298">Lückenvorkommen für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="9f899-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-300">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-301">Lückendichte für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="9f899-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-303">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-304">Lückendauer für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="9f899-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-306">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-307">Gesamtanzahl der Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="9f899-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-309">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-310">Durchschnittliche Anzahl der Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="9f899-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-312">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-313">Maximale Anzahl der Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="9f899-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-315">int</span><span class="sxs-lookup"><span data-stu-id="9f899-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-316">Burstvorkommen in den Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="9f899-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-318">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-319">Burstdichte in den Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="9f899-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-321">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-322">Burstdauer in den Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="9f899-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-324">int</span><span class="sxs-lookup"><span data-stu-id="9f899-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-325">Lückenvorkommen in den Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="9f899-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-327">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-328">Lückendichte in den Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="9f899-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-330">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-331">Lückendauer in den Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="9f899-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-333">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-334">Rate eingehender Frames insgesamt, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9f899-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-336">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-337">Durchschnittliche Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9f899-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-339">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-340">Durchschnittliche Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9f899-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-342">int</span><span class="sxs-lookup"><span data-stu-id="9f899-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-343">Burstvorkommen in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9f899-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-345">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-346">Burstdichte in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9f899-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-348">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-349">Burstdauer in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9f899-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-351">int</span><span class="sxs-lookup"><span data-stu-id="9f899-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-352">Lückenvorkommen in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9f899-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-354">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-355">Lückendichte in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9f899-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-357">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-358">Lückendauer in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9f899-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-360">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-361">Rate eingehender Frames insgesamt, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9f899-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-363">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-364">Durchschnittliche Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9f899-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-366">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-367">Durchschnittliche Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9f899-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-369">int</span><span class="sxs-lookup"><span data-stu-id="9f899-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-370">Burstvorkommen in der Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9f899-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-372">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-373">Burstdichte in der Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9f899-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-375">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-376">Burstdauer in der Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9f899-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-378">int</span><span class="sxs-lookup"><span data-stu-id="9f899-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-379">Lückenvorkommen in der Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9f899-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-381">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-382">Lückendichte in der Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9f899-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-384">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-385">Lückendauer in der Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9f899-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-387">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-388">Rate ausgehender Kacheln insgesamt für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9f899-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-390">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-391">Durchschnittliche Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9f899-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-393">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-394">Maximale Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9f899-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-396">int</span><span class="sxs-lookup"><span data-stu-id="9f899-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-397">Burstvorkommen in der Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9f899-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-399">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-400">Burstdichte in der Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9f899-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-402">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-403">Burstdauer in der Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9f899-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-405">int</span><span class="sxs-lookup"><span data-stu-id="9f899-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-406">Lückenvorkommen in der Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9f899-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-408">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-409">Lückendichte in der Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9f899-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-411">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-412">Lückendauer in der Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9f899-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-414">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-415">Rate ausgehender Frames insgesamt für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9f899-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-417">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-418">Durchschnittliche Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9f899-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-420">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-421">Maximale Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9f899-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-423">int</span><span class="sxs-lookup"><span data-stu-id="9f899-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-424">Burstvorkommen in der Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9f899-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-426">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-427">Burstdichte in der Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9f899-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-429">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-430">Burstdauer in der Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9f899-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-432">int</span><span class="sxs-lookup"><span data-stu-id="9f899-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-433">Lückenvorkommen in der Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9f899-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-435">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-436">Lückendichte in der Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9f899-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-438">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9f899-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-439">Lückendauer in der Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9f899-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-441">int</span><span class="sxs-lookup"><span data-stu-id="9f899-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-442">Durchschnittliche Höhe der Videoauflösung in Pixeln.</span><span class="sxs-lookup"><span data-stu-id="9f899-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-444">int</span><span class="sxs-lookup"><span data-stu-id="9f899-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-445">Durchschnittliche Breite der Videoauflösung in Pixeln.</span><span class="sxs-lookup"><span data-stu-id="9f899-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-446"><strong>Eingehend</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-447">Bit</span><span class="sxs-lookup"><span data-stu-id="9f899-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-448">Durchschnittliche Framerate (in Frames pro Sekunde) für eingehende Übertragungen.</span><span class="sxs-lookup"><span data-stu-id="9f899-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f899-449"><strong>Ausgehend</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-450">Bit</span><span class="sxs-lookup"><span data-stu-id="9f899-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-451">Durchschnittliche Framerate (in Frames pro Sekunde) für ausgehende Übertragungen.</span><span class="sxs-lookup"><span data-stu-id="9f899-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f899-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="9f899-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="9f899-453">Bit</span><span class="sxs-lookup"><span data-stu-id="9f899-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f899-454">1 bedeutet, dass die Betrachter vom Anrufer zum Angerufenen verläuft.</span><span class="sxs-lookup"><span data-stu-id="9f899-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="9f899-455">0 bedeutet, dass die Datenstromrichtung vom Angerufenen zum Anrufer verläuft.</span><span class="sxs-lookup"><span data-stu-id="9f899-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

