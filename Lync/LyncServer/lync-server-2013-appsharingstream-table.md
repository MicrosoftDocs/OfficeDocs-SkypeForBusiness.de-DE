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
ms.openlocfilehash: 9b729112aa0fb064a518c50212a6a041a6661be3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499502"
---
# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="1dc2c-102">AppSharingStream-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1dc2c-102">AppSharingStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1dc2c-103">_**Letztes Änderungsstand des Themas:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="1dc2c-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="1dc2c-104">Die AppSharingStream-Tabelle enthält Metriken für die Qualität der Erfahrung für die Netzwerkstreams, die für die Anwendungsfreigabe verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="1dc2c-105">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1dc2c-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="1dc2c-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="1dc2c-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="1dc2c-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="1dc2c-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="1dc2c-112">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="1dc2c-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1dc2c-113">Datum und Uhrzeit des Sitzungsbeginns.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-115">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-115">int</span></span></p></td>
<td><p><span data-ttu-id="1dc2c-116">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="1dc2c-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1dc2c-117">Sequenzielle ID, anhand der zwischen Sitzungen unterschieden wird, die an denselben Tag und zur derselben Uhrzeit gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="1dc2c-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1dc2c-120">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="1dc2c-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1dc2c-p102">Stellt den Videozeilentyp dar, der bei dem Anruf verwendet wurde. Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="1dc2c-123">0 – Audio</span><span class="sxs-lookup"><span data-stu-id="1dc2c-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="1dc2c-124">1 – Video</span><span class="sxs-lookup"><span data-stu-id="1dc2c-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="1dc2c-125">2 -- Panoramavideo</span><span class="sxs-lookup"><span data-stu-id="1dc2c-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="1dc2c-126">3 – Anwendungs-/Desktop Freigabe</span><span class="sxs-lookup"><span data-stu-id="1dc2c-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-127"><strong>Datenstrom-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-128">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-128">int</span></span></p></td>
<td><p><span data-ttu-id="1dc2c-129">Primary</span><span class="sxs-lookup"><span data-stu-id="1dc2c-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="1dc2c-130">Eindeutige ID des Anwendungsfreigabe-Datenstroms.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-132">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-133">Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="1dc2c-134">(Jitter ist ein Maß für die &quot; Zittern eines &quot; Aufrufs.) Hohe Jitter-Werte werden normalerweise durch Überlastung oder einen überladenen Medienserver verursacht und führen zu verzerrten oder verlorenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-136">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-137">Der maximale Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="1dc2c-138">(Jitter ist ein Maß für die &quot; Zittern eines &quot; Aufrufs.) Hohe Jitter-Werte werden normalerweise durch Überlastung oder einen überladenen Medienserver verursacht und führen zu verzerrten oder verlorenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-139"><strong>Roundtrip</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-140">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-p105">Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-Time Transport-Protokoll) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="1dc2c-p106">Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-146">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-p107">Die maximale Zeit (in Millisekunden), die ein RTP-Paket (Real-Time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="1dc2c-p108">Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-152">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-p109">Die durchschnittliche Rate an RTP-Paketverlusten (Real-Time Transport-Protokoll; ein Protokoll für die Übertragung von Audio und Video über das Internet). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-157">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-p110">Die maximale Rate an RTP-Paketverlusten (Real-Time Transport-Protokoll). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-162">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-163">Die Anzahl der gesendeten Pakete.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-164"><strong>Bandbreite</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-165">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-p111">Die geschätzte unidirektionale Bandbreite, die am Ende der Sitzung verfügbar ist (in Bits pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-169">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-170">Beschreibung der Anwendungsfreigabe-Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-172">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-p112">Gesamter Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-176">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-p113">Durchschnittlicher Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-180">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-p114">Maximaler Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-184">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-p115">Undirektionale Burstvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-189">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-p116">Undirektionale Burstdichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-194">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-p117">Undirektionale Burstdauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-199">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-p118">Undirektionale Lückenvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-204">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-p119">Undirektionale Lückendichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-209">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-p120">Undirektionale Lückendauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="1dc2c-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-215">Anwendungsrolle (Freigebender Benutzer oder Betrachter) und Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-217">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-p121">Gesamte Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je höher der Gesamtwert, desto länger die Verzögerung bei der Wiedergabe.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-221">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-p122">Durchschnittliche Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je höher der Gesamtwert, desto länger die Verzögerung bei der Wiedergabe.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-225">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-p123">Maximale Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je höher der Gesamtwert, desto länger die Verzögerung bei der Wiedergabe.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-229">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-p124">Burstvorkommen in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-233">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-p125">Burstdichte in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-237">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-p126">Burstdauer in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-241">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-242">Lückenvorkommen in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP).</span><span class="sxs-lookup"><span data-stu-id="1dc2c-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-244">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-p127">Lückendichte in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je geringer die Lückendichte, desto besser das Wiedergabeerlebnis.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-248">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-p128">Lückendauer in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je kürzer die Lückendauer, desto besser das Wiedergabeerlebnis.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-252">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-253">Gesamtrate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="1dc2c-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-255">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-256">Durchschnittliche Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="1dc2c-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-258">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-259">Maximale Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="1dc2c-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-261">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-262">Burstvorkommen in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="1dc2c-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-264">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-265">Burstdichte in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="1dc2c-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-267">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-268">Burstdauer in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="1dc2c-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-270">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-271">Lückenvorkommen in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="1dc2c-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-273">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-274">Lückendichte in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="1dc2c-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-276">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-277">Lückendauer in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="1dc2c-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-279">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-280">Gesamtprozentsatz des Inhalts, der nicht angezeigt, sondern stattdessen verworfen und durch aktuellen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-282">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-283">Durchschnittlicher Prozentsatz des Inhalts, der nicht angezeigt, sondern stattdessen verworfen und durch aktuellen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-285">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-286">Maximaler Prozentsatz des Inhalts, der nicht angezeigt, sondern stattdessen verworfen und durch aktuellen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-288">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-289">Burstvorkommen für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch aktuellen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-291">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-292">Burstdichte für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-294">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-295">Burstdauer für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-297">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-298">Lückenvorkommen für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-300">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-301">Lückendichte für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-303">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-304">Lückendauer für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-306">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-307">Gesamtanzahl der Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-309">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-310">Durchschnittliche Anzahl der Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-312">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-313">Maximale Anzahl der Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-315">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-316">Burstvorkommen in den Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-318">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-319">Burstdichte in den Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-321">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-322">Burstdauer in den Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-324">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-325">Lückenvorkommen in den Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-327">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-328">Lückendichte in den Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-330">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-331">Lückendauer in den Scrapingframes aus der Grafikquelle.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-333">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-334">Rate eingehender Frames insgesamt, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-336">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-337">Durchschnittliche Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-339">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-340">Durchschnittliche Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-342">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-343">Burstvorkommen in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-345">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-346">Burstdichte in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-348">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-349">Burstdauer in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-351">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-352">Lückenvorkommen in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-354">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-355">Lückendichte in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-357">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-358">Lückendauer in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-360">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-361">Rate eingehender Frames insgesamt, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-363">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-364">Durchschnittliche Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-366">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-367">Durchschnittliche Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-369">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-370">Burstvorkommen in der Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-372">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-373">Burstdichte in der Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-375">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-376">Burstdauer in der Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-378">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-379">Lückenvorkommen in der Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-381">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-382">Lückendichte in der Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-384">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-385">Lückendauer in der Rate eingehender Frames, die vom Betrachter empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-387">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-388">Rate ausgehender Kacheln insgesamt für den Absender.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-390">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-391">Durchschnittliche Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-393">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-394">Maximale Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-396">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-397">Burstvorkommen in der Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-399">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-400">Burstdichte in der Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-402">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-403">Burstdauer in der Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-405">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-406">Lückenvorkommen in der Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-408">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-409">Lückendichte in der Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-411">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-412">Lückendauer in der Rate ausgehender Kacheln für den Absender.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-414">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-415">Rate ausgehender Frames insgesamt für den Absender.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-417">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-418">Durchschnittliche Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-420">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-421">Maximale Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-423">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-424">Burstvorkommen in der Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-426">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-427">Burstdichte in der Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-429">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-430">Burstdauer in der Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-432">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-433">Lückenvorkommen in der Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-435">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-436">Lückendichte in der Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-438">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="1dc2c-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-439">Lückendauer in der Rate ausgehender Frames für den Absender.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-441">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-442">Durchschnittliche Höhe der Videoauflösung in Pixeln.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-444">int</span><span class="sxs-lookup"><span data-stu-id="1dc2c-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-445">Durchschnittliche Breite der Videoauflösung in Pixeln.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-446"><strong>Eingehende</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-447">Bit</span><span class="sxs-lookup"><span data-stu-id="1dc2c-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-448">Durchschnittliche Framerate (in Frames pro Sekunde) für eingehende Übertragungen.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc2c-449"><strong>Ausgehende</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-450">Bit</span><span class="sxs-lookup"><span data-stu-id="1dc2c-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-451">Durchschnittliche Framerate (in Frames pro Sekunde) für ausgehende Übertragungen.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc2c-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="1dc2c-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc2c-453">Bit</span><span class="sxs-lookup"><span data-stu-id="1dc2c-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc2c-454">1 bedeutet, dass die Betrachter vom Anrufer zum Angerufenen verläuft.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="1dc2c-455">0 bedeutet, dass die Datenstromrichtung vom Angerufenen zum Anrufer verläuft.</span><span class="sxs-lookup"><span data-stu-id="1dc2c-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

