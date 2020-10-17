---
title: Testen der lync Server 2013 Skalierbarkeit
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41e23cd1bf0382a392cba951d90cd9dfa80c4880
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511012"
---
# <a name="scalability-testing-in-lync-server-2013"></a><span data-ttu-id="67595-102">Skalierbarkeitstests in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67595-102">Scalability testing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67595-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="67595-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="67595-104">Lync Server 2013 stellt die Server Infrastruktur für alle lync Server Echtzeitkommunikation bereit, einschließlich Instant Messaging (Sofortnachrichten) und Anwesenheit, Konferenzen und Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="67595-104">Lync Server 2013 provides the server infrastructure for all Lync Server real-time communications, including instant messaging (IM) and presence, conferencing, and Enterprise Voice.</span></span> <span data-ttu-id="67595-105">Dies umfasst alle Features, die die Hardwareressourcen eines lync Server 2013 Pools verwenden und sich daher auf Leistung und Skalierung auswirken.</span><span class="sxs-lookup"><span data-stu-id="67595-105">This includes any features that use the hardware resources of a Lync Server 2013 pool and, therefore, affect performance and scale.</span></span> <span data-ttu-id="67595-106">Nicht alle Organisationen verwenden alle Features gleichermaßen.</span><span class="sxs-lookup"><span data-stu-id="67595-106">All organizations do not use all features equally.</span></span>

<span data-ttu-id="67595-107">Einige Organisationen können beispielsweise Videos in Konferenzen sehr stark verwenden, während andere möglicherweise wenig oder gar keine Videonutzung haben.</span><span class="sxs-lookup"><span data-stu-id="67595-107">For example, some organizations might use video in conferences very heavily while others might have little or no video usage.</span></span> <span data-ttu-id="67595-108">Einige Organisationen bevorzugen PowerPoint-Folien Freigaben für die Anwendungsfreigabe, während andere das Gegenteil bevorzugen.</span><span class="sxs-lookup"><span data-stu-id="67595-108">Some organizations prefer PowerPoint slide sharing to application sharing, while others prefer the opposite.</span></span> <span data-ttu-id="67595-109">Für Organisationen, die Enterprise-VoIP bereitstellen, wird die Reaktionsgruppenanwendung möglicherweise stark verwendet.</span><span class="sxs-lookup"><span data-stu-id="67595-109">Those organizations that deploy Enterprise Voice might or might not use the Response Group application heavily.</span></span> <span data-ttu-id="67595-110">In den meisten Organisationen werden Monitoring Server bereitgestellt, aber nicht viele von Ihnen stellen Archivierungsserver bereit.</span><span class="sxs-lookup"><span data-stu-id="67595-110">Most organizations deploy Monitoring Servers, but not many of them deploy Archiving Servers.</span></span> <span data-ttu-id="67595-111">Darüber hinaus verfügen Organisationen nicht alle über die gleichen Infrastrukturen, einschließlich Hardwarekapazitäten, Netzwerkkapazitäten und der Anzahl der bereitgestellten Pools und der Größe von Pools.</span><span class="sxs-lookup"><span data-stu-id="67595-111">Additionally, organizations do not all have the same infrastructures, including hardware capacities, network capacities, and the number of pools and size of pools deployed.</span></span> <span data-ttu-id="67595-112">Die Vielfalt an Features und Infrastrukturen stellt eine Herausforderung für Skalierbarkeitstests dar – es ist nicht möglich, alle möglichen Kombinationen von Features und Infrastrukturen zu simulieren.</span><span class="sxs-lookup"><span data-stu-id="67595-112">The diversity of features and infrastructures poses a challenge to scalability testing – it is not possible to simulate all possible combinations of features and infrastructures.</span></span>

<span data-ttu-id="67595-113">Um die Skalierbarkeits Unterstützung für lync Server zu ermitteln, führen wir Tests durch, indem wir alle lync Server Funktionen gleichzeitig verwenden, basierend auf einem durchschnittlichen Verwendungsmodell (Benutzermodell).</span><span class="sxs-lookup"><span data-stu-id="67595-113">To determine scalability support for Lync Server, we conduct testing by using all Lync Server features concurrently, based on an average usage model (user model).</span></span> <span data-ttu-id="67595-114">Zur Bestimmung eines geeigneten Benutzermodells für lync Server Arbeitslasten analysieren wir zahlreiche Datenpunkte, einschließlich Kundenumfragen, Feedback aus dem Microsoft-Programm zur Verbesserung der Benutzerfreundlichkeit, lync Server Nutzungsdaten aus der internen IT-Abteilung bei Microsoft sowie Daten, die aus unserem Live Meeting-Dienst gewonnen wurden.</span><span class="sxs-lookup"><span data-stu-id="67595-114">To determine an appropriate user model for Lync Server workloads, we analyze many data points, including customer surveys, feedback from the Microsoft customer experience improvement program, Lync Server usage data from the internal IT department at Microsoft, and data mined from our Live Meeting Service.</span></span> <span data-ttu-id="67595-115">In vielen Fällen ist das Benutzermodell für umfangreichere Auslastungen ausgelegt, um eine bequeme Nutzung innerhalb einer Organisation zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="67595-115">In many cases, the user model has a bias towards heavier loads to provide a comfortable margin for usage within an organization.</span></span>

<span data-ttu-id="67595-116">In unseren Skalierbarkeitstests richten wir lync Server 2013 Pools gemäß den empfohlenen Hardware-und Software Spezifikationen ein, einschließlich Infrastrukturkomponenten wie Active Directory-Domänendienste, Hardwarelastenausgleich und Firewalls.</span><span class="sxs-lookup"><span data-stu-id="67595-116">In our scalability tests, we set up Lync Server 2013 pools according to the recommended hardware and software specifications, including infrastructure components, such as Active Directory Domain Services, hardware load balancers, and firewalls.</span></span> <span data-ttu-id="67595-117">Wir richten lync Server Umgebungen so nah wie möglich an typischen Umgebungen in der realen Welt ein.</span><span class="sxs-lookup"><span data-stu-id="67595-117">We set up Lync Server environments as closely as possible to typical real-world environments.</span></span> <span data-ttu-id="67595-118">Anschließend verwenden wir das lync Server 2013 Stress and Performance-Tool, um lync Server 2013 Lasten zu simulieren (basierend auf unserem Benutzermodell).</span><span class="sxs-lookup"><span data-stu-id="67595-118">We then use the Lync Server 2013 Stress and Performance Tool to simulate Lync Server 2013 loads (based on our user model).</span></span> <span data-ttu-id="67595-119">.</span><span class="sxs-lookup"><span data-stu-id="67595-119">.</span></span>

<span data-ttu-id="67595-p105">Wir führen die Skalierbarkeitstests mehrmals aus (einschließlich mehrerer dreiwöchiger Testläufe). Die Ergebnisse aller Tests verwenden wir dann zur Leistungsoptimierung und zum Überprüfen der Unterstützung der Skalierbarkeitszahlen in unserem Benutzermodell.</span><span class="sxs-lookup"><span data-stu-id="67595-p105">We do multiple iterations of scalability tests (including multiple three-week test runs). We use the results of all tests to help with performance tuning and to verify support for the scalability numbers in our user model.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

