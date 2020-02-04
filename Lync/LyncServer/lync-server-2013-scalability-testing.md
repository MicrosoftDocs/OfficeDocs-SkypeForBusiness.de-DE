---
title: Testen von lync Server 2013-Skalierbarkeit
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
ms.openlocfilehash: d702b0a197e6e81fbc6833ca58968a10d8dd3fff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a><span data-ttu-id="13bb6-102">Skalierbarkeitstests in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13bb6-102">Scalability testing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13bb6-103">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="13bb6-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="13bb6-104">Lync Server 2013 stellt die Server Infrastruktur für alle lync Server-Echtzeitkommunikationen bereit, einschließlich Instant Messaging (im) und Anwesenheits-, Konferenz-und Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="13bb6-104">Lync Server 2013 provides the server infrastructure for all Lync Server real-time communications, including instant messaging (IM) and presence, conferencing, and Enterprise Voice.</span></span> <span data-ttu-id="13bb6-105">Dazu gehören alle Features, die die Hardwareressourcen eines lync Server 2013-Pools verwenden und sich daher auf Leistung und Skalierung auswirken.</span><span class="sxs-lookup"><span data-stu-id="13bb6-105">This includes any features that use the hardware resources of a Lync Server 2013 pool and, therefore, affect performance and scale.</span></span> <span data-ttu-id="13bb6-106">Alle Organisationen verwenden nicht alle Funktionen gleichermaßen.</span><span class="sxs-lookup"><span data-stu-id="13bb6-106">All organizations do not use all features equally.</span></span>

<span data-ttu-id="13bb6-107">Beispielsweise können einige Organisationen Video in Konferenzen sehr stark verwenden, während andere wenig oder gar keine Videonutzung haben könnten.</span><span class="sxs-lookup"><span data-stu-id="13bb6-107">For example, some organizations might use video in conferences very heavily while others might have little or no video usage.</span></span> <span data-ttu-id="13bb6-108">Einige Organisationen bevorzugen die PowerPoint-Folien Freigabe für die Anwendungsfreigabe, während andere das Gegenteil bevorzugen.</span><span class="sxs-lookup"><span data-stu-id="13bb6-108">Some organizations prefer PowerPoint slide sharing to application sharing, while others prefer the opposite.</span></span> <span data-ttu-id="13bb6-109">Organisationen, die Enterprise-VoIP bereitstellen, können die reaktionsgruppenanwendung möglicherweise stark verwenden oder nicht.</span><span class="sxs-lookup"><span data-stu-id="13bb6-109">Those organizations that deploy Enterprise Voice might or might not use the Response Group application heavily.</span></span> <span data-ttu-id="13bb6-110">In den meisten Organisationen werden Überwachungsserver bereitgestellt, aber nicht viele von Ihnen stellen Archivierungsserver bereit.</span><span class="sxs-lookup"><span data-stu-id="13bb6-110">Most organizations deploy Monitoring Servers, but not many of them deploy Archiving Servers.</span></span> <span data-ttu-id="13bb6-111">Darüber hinaus verfügen Organisationen nicht alle über die gleichen Infrastrukturen wie Hardwarekapazitäten, Netzwerkkapazitäten und die Anzahl der Pools und die Größe der bereitgestellten Pools.</span><span class="sxs-lookup"><span data-stu-id="13bb6-111">Additionally, organizations do not all have the same infrastructures, including hardware capacities, network capacities, and the number of pools and size of pools deployed.</span></span> <span data-ttu-id="13bb6-112">Die Vielfalt der Features und Infrastrukturen stellt eine Herausforderung für Skalierbarkeitstests dar – es ist nicht möglich, alle möglichen Kombinationen von Features und Infrastrukturen zu simulieren.</span><span class="sxs-lookup"><span data-stu-id="13bb6-112">The diversity of features and infrastructures poses a challenge to scalability testing – it is not possible to simulate all possible combinations of features and infrastructures.</span></span>

<span data-ttu-id="13bb6-113">Um die Unterstützung der Skalierbarkeit für lync Server zu ermitteln, führen wir Tests mit allen lync Server-Features gleichzeitig aus, basierend auf einem durchschnittlichen Nutzungsmodell (Benutzermodell).</span><span class="sxs-lookup"><span data-stu-id="13bb6-113">To determine scalability support for Lync Server, we conduct testing by using all Lync Server features concurrently, based on an average usage model (user model).</span></span> <span data-ttu-id="13bb6-114">Um ein geeignetes Benutzermodell für lync Server-Arbeitsauslastungen zu ermitteln, analysieren wir viele Datenpunkte, einschließlich Kundenbefragungen, Feedback aus dem Microsoft-Programm zur Verbesserung der Benutzerfreundlichkeit, lync Server-Nutzungsdaten aus der internen IT-Abteilung bei Microsoft, und Daten, die aus unserem Live Meeting-Service gewonnen wurden.</span><span class="sxs-lookup"><span data-stu-id="13bb6-114">To determine an appropriate user model for Lync Server workloads, we analyze many data points, including customer surveys, feedback from the Microsoft customer experience improvement program, Lync Server usage data from the internal IT department at Microsoft, and data mined from our Live Meeting Service.</span></span> <span data-ttu-id="13bb6-115">In vielen Fällen weist das Benutzermodell eine Neigung zu schwereren Lasten auf, um einen bequemen Seitenrand für die Verwendung innerhalb einer Organisation bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="13bb6-115">In many cases, the user model has a bias towards heavier loads to provide a comfortable margin for usage within an organization.</span></span>

<span data-ttu-id="13bb6-116">In unseren Skalierbarkeitstests richten wir lync Server 2013-Pools entsprechend den empfohlenen Hardware-und Software Spezifikationen ein, einschließlich Infrastrukturkomponenten wie Active Directory-Domänendienste, Hardwarelastenausgleichs und Firewalls.</span><span class="sxs-lookup"><span data-stu-id="13bb6-116">In our scalability tests, we set up Lync Server 2013 pools according to the recommended hardware and software specifications, including infrastructure components, such as Active Directory Domain Services, hardware load balancers, and firewalls.</span></span> <span data-ttu-id="13bb6-117">Wir haben lync Server-Umgebungen so eingerichtet, dass Sie den typischen Umgebungen in der realen Welt entsprechen.</span><span class="sxs-lookup"><span data-stu-id="13bb6-117">We set up Lync Server environments as closely as possible to typical real-world environments.</span></span> <span data-ttu-id="13bb6-118">Anschließend verwenden wir das Stress-und Leistungs Tool von lync Server 2013, um lync Server 2013-Lasten zu simulieren (basierend auf unserem Benutzermodell).</span><span class="sxs-lookup"><span data-stu-id="13bb6-118">We then use the Lync Server 2013 Stress and Performance Tool to simulate Lync Server 2013 loads (based on our user model).</span></span> <span data-ttu-id="13bb6-119">.</span><span class="sxs-lookup"><span data-stu-id="13bb6-119">.</span></span>

<span data-ttu-id="13bb6-120">Wir führen mehrere Iterationen von Skalierbarkeitstests durch, einschließlich mehrerer dreiwöchiger Test Läufe.</span><span class="sxs-lookup"><span data-stu-id="13bb6-120">We do multiple iterations of scalability tests (including multiple three-week test runs).</span></span> <span data-ttu-id="13bb6-121">Wir verwenden die Ergebnisse aller Tests, um bei der Leistungsoptimierung zu helfen und die Unterstützung für die Skalierbarkeits Nummern in unserem Benutzermodell zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="13bb6-121">We use the results of all tests to help with performance tuning and to verify support for the scalability numbers in our user model.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

