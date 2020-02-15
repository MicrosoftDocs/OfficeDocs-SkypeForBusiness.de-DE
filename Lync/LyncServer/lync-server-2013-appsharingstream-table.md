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
ms.openlocfilehash: 31a75ddd223816c57a69bd0c9e88b48845d4374e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029306"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="9a6c8-102">AppSharingStream-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a6c8-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a6c8-103">_**Letztes Änderungsstand des Themas:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="9a6c8-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="9a6c8-104">Die AppSharingStream-Tabelle enthält Metriken für die Qualität der Erfahrung für die Netzwerkstreams, die für die Anwendungsfreigabe verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="9a6c8-105">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a6c8-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="9a6c8-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="9a6c8-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="9a6c8-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="9a6c8-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="9a6c8-112">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="9a6c8-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9a6c8-113">Datum und Uhrzeit des Sitzungsbeginns.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-115">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-115">int</span></span></p></td>
<td><p><span data-ttu-id="9a6c8-116">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="9a6c8-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9a6c8-117">Sequenzielle ID, anhand der zwischen Sitzungen unterschieden wird, die an denselben Tag und zur derselben Uhrzeit gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="9a6c8-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9a6c8-120">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="9a6c8-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9a6c8-p102">Stellt den Videozeilentyp dar, der bei dem Anruf verwendet wurde. Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="9a6c8-123">0 – Audio</span><span class="sxs-lookup"><span data-stu-id="9a6c8-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="9a6c8-124">1 – Video</span><span class="sxs-lookup"><span data-stu-id="9a6c8-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="9a6c8-125">2 -- Panoramavideo</span><span class="sxs-lookup"><span data-stu-id="9a6c8-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="9a6c8-126">3 – Anwendungs-/Desktop Freigabe</span><span class="sxs-lookup"><span data-stu-id="9a6c8-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-127"><strong>Datenstrom-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-128">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-128">int</span></span></p></td>
<td><p><span data-ttu-id="9a6c8-129">Primary</span><span class="sxs-lookup"><span data-stu-id="9a6c8-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="9a6c8-130">Eindeutige ID des Anwendungsfreigabe-Datenstroms.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-132">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-133">Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="9a6c8-134">(Jitter ist ein Maß für die &quot;Zittern&quot; eines Aufrufs.) Hohe Jitter-Werte werden normalerweise durch Überlastung oder einen überladenen Medienserver verursacht und führen zu verzerrten oder verlorenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-136">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-137">Der maximale Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="9a6c8-138">(Jitter ist ein Maß für die &quot;Zittern&quot; eines Aufrufs.) Hohe Jitter-Werte werden normalerweise durch Überlastung oder einen überladenen Medienserver verursacht und führen zu verzerrten oder verlorenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-139"><strong>Roundtrip</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-140">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-p105">Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-Time Transport-Protokoll) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="9a6c8-p106">Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routing konfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-146">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-p107">Die maximale Zeit (in Millisekunden), die ein RTP-Paket (Real-Time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="9a6c8-p108">Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-152">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-p109">Die durchschnittliche Rate an RTP-Paketverlusten (Real-Time Transport-Protokoll; ein Protokoll für die Übertragung von Audio und Video über das Internet). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-157">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-p110">Die maximale Rate an RTP-Paketverlusten (Real-Time Transport-Protokoll). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-162">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-163">Die Anzahl der gesendeten Pakete.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-164"><strong>Bandbreite</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-165">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-p111">Die geschätzte unidirektionale Bandbreite, die am Ende der Sitzung verfügbar ist (in Bits pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-169">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-170">Beschreibung der Anwendungsfreigabe-Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-172">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-p112">Gesamter Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-176">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-p113">Durchschnittlicher Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-180">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-p114">Maximaler Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-184">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-p115">Undirektionale Burstvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-189">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-p116">Undirektionale Burstdichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-194">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-p117">Undirektionale Burstdauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-199">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-p118">Undirektionale Lückenvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-204">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-p119">Undirektionale Lückendichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-209">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-p120">Undirektionale Lückendauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="9a6c8-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-215">Anwendungsrolle (Freigebender Benutzer oder Betrachter) und Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-217">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-p121">Gesamte Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je höher der Gesamtwert, desto länger die Verzögerung bei der Wiedergabe.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-221">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-p122">Durchschnittliche Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je höher der Gesamtwert, desto länger die Verzögerung bei der Wiedergabe.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-225">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-p123">Maximale Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je höher der Gesamtwert, desto länger die Verzögerung bei der Wiedergabe.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-229">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-p124">Burstvorkommen in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-233">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-p125">Burstdichte in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-237">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-p126">Burstdauer in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-241">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-242">Lückenvorkommen in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP).</span><span class="sxs-lookup"><span data-stu-id="9a6c8-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-244">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-p127">Lückendichte in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je geringer die Lückendichte, desto besser das Wiedergabeerlebnis.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-248">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-p128">Lückendauer in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je kürzer die Lückendauer, desto besser das Wiedergabeerlebnis.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-252">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-253">Gesamtrate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="9a6c8-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-255">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-256">Durchschnittliche Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="9a6c8-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-258">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-259">Maximale Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="9a6c8-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-261">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-262">Burstvorkommen in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="9a6c8-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-264">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-265">Burstdichte in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="9a6c8-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-267">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-268">Burstdauer in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="9a6c8-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-270">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-271">Lückenvorkommen in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="9a6c8-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-273">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-274">Lückendichte in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="9a6c8-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-276">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-277">Lückendauer in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="9a6c8-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-279">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-280">Gesamtprozentsatz des Inhalts, der nicht angezeigt, sondern stattdessen verworfen und durch aktuellen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-282">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-283">Durchschnittlicher Prozentsatz des Inhalts, der nicht angezeigt, sondern stattdessen verworfen und durch aktuellen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-285">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-286">Maximaler Prozentsatz des Inhalts, der nicht angezeigt, sondern stattdessen verworfen und durch aktuellen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-288">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-289">Burstvorkommen für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch aktuellen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-291">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-292">Burstdichte für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-294">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-295">Burstdauer für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-297">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-298">Lückenvorkommen für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-300">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-301">Lückendichte für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-303">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-304">Lückendauer für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-306">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-307">Gesamtanzahl der Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-309">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-310">Durchschnittliche Anzahl der Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-312">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-313">Maximale Anzahl der Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-315">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-316">Burstvorkommen in den Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-318">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-319">Burstdichte in den Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-321">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-322">Burstdauer in den Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-324">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-325">Lückenvorkommen in den Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-327">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-328">Lückendichte in den Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-330">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-331">Lückendauer in den Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-333">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-334">Rate eingehender Frames insgesamt, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-336">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-337">Durchschnittliche Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-339">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-340">Durchschnittliche Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-342">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-343">Burstvorkommen in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-345">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-346">Burstdichte in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-348">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-349">Burstdauer in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-351">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-352">Lückenvorkommen in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-354">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-355">Lückendichte in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-357">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-358">Lückendauer in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-360">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-361">Rate eingehender Frames insgesamt, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-363">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-364">Durchschnittliche Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-366">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-367">Durchschnittliche Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-369">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-370">Burstvorkommen in der Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-372">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-373">Burstdichte in der Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-375">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-376">Burstdauer in der Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-378">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-379">Lückenvorkommen in der Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-381">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-382">Lückendichte in der Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-384">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-385">Lückendauer in der Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-387">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-388">Rate ausgehender Kacheln insgesamt für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-390">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-391">Durchschnittliche Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-393">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-394">Maximale Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-396">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-397">Burstvorkommen in der Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-399">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-400">Burstdichte in der Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-402">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-403">Burstdauer in der Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-405">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-406">Lückenvorkommen in der Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-408">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-409">Lückendichte in der Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-411">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-412">Lückendauer in der Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-414">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-415">Rate ausgehender Frames insgesamt für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-417">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-418">Durchschnittliche Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-420">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-421">Maximale Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-423">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-424">Burstvorkommen in der Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-426">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-427">Burstdichte in der Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-429">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-430">Burstdauer in der Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-432">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-433">Lückenvorkommen in der Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-435">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-436">Lückendichte in der Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-438">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="9a6c8-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-439">Lückendauer in der Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-441">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-442">Durchschnittliche Höhe der Videoauflösung in Pixeln.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-444">int</span><span class="sxs-lookup"><span data-stu-id="9a6c8-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-445">Durchschnittliche Breite der Videoauflösung in Pixeln.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-446"><strong>Eingehend</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-447">Bit</span><span class="sxs-lookup"><span data-stu-id="9a6c8-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-448">Durchschnittliche Framerate (in Frames pro Sekunde) für eingehende Übertragungen.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a6c8-449"><strong>Ausgehend</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-450">Bit</span><span class="sxs-lookup"><span data-stu-id="9a6c8-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-451">Durchschnittliche Framerate (in Frames pro Sekunde) für ausgehende Übertragungen.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a6c8-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="9a6c8-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="9a6c8-453">Bit</span><span class="sxs-lookup"><span data-stu-id="9a6c8-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a6c8-454">1 bedeutet, dass die Betrachter vom Anrufer zum Angerufenen verläuft.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="9a6c8-455">0 bedeutet, dass die Datenstromrichtung vom Angerufenen zum Anrufer verläuft.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

