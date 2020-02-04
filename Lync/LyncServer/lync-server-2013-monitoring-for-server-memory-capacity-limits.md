---
title: 'Lync Server 2013: Überwachen der Speicher Kapazitätsgrenzwerte für Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5c9746240335b1c66606da24edf6ffa2a0e7bda
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a><span data-ttu-id="e71ba-102">Überwachen der Speicher Kapazitätsgrenzwerte von Servern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e71ba-102">Monitoring for server memory capacity limits in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e71ba-103">_**Letztes Änderungsdatum des Themas:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="e71ba-103">_**Topic Last Modified:** 2016-12-08_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> <span data-ttu-id="e71ba-104">Die Informationen in diesem Thema, die sich auf die Kapazitätsplanung beziehen, bezieht sich nur auf lync 2010-Mobile Clients und den Mobilitätsdienst (MCX).</span><span class="sxs-lookup"><span data-stu-id="e71ba-104">The information in this topic that refers to Capacity Planning pertains only to Lync 2010 Mobile clients and the Mobility Service (Mcx).</span></span> <span data-ttu-id="e71ba-105">Die Kapazitätsplanung für die Unified Communications Web-API (UCWA), die von den mobilen lync 2013-Clients verwendet wird, wird vom lync Server 2013, Planungs Tool, bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e71ba-105">Capacity Planning for the Unified Communications Web API (UCWA), used by the Lync 2013 Mobile clients, is provided by the Lync Server 2013, Planning Tool.</span></span>



</div>

<span data-ttu-id="e71ba-106">Zwei Mobilitäts Leistungsindikatoren können Ihnen dabei helfen, Ihre aktuelle Nutzung zu ermitteln und Ihnen bei der Planung der Kapazität für den lync Server 2013 Mobility Service (MCX) sowie beim Überwachen der Speicherauslastung für UCWA zu helfen.</span><span class="sxs-lookup"><span data-stu-id="e71ba-106">Two mobility performance counters can help you to determine your current usage and help you plan capacity for the Lync Server 2013 Mobility Service (Mcx), as well as to monitor memory usage for UCWA.</span></span> <span data-ttu-id="e71ba-107">Für UCWA ist die Indikatorkategorie **ls: Web – UCWA**.</span><span class="sxs-lookup"><span data-stu-id="e71ba-107">For UCWA, the counter category is **LS:WEB – UCWA**.</span></span> <span data-ttu-id="e71ba-108">Für den Mobilitätsdienst (Mobility Service, MCX) befinden sich die Leistungsindikatoren unter der Kategorie **ls: Web-Mobile Communication Service**.</span><span class="sxs-lookup"><span data-stu-id="e71ba-108">For the Mobility Service (Mcx), the counters are under the category **LS:WEB - Mobile Communication Service**.</span></span> <span data-ttu-id="e71ba-109">Die zu überwachenden Leistungsindikatoren sind:</span><span class="sxs-lookup"><span data-stu-id="e71ba-109">The counters to monitor are:</span></span>

  - <span data-ttu-id="e71ba-110">**Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements**: Dies ist die aktuelle Anzahl von Endpunkten, die über die UCWA oder den Mobilitätsdienst (Mcx) registriert wurden und aktive Anwesenheitsabonnements besitzen (Anzahl der immer verbundenen mobilen Benutzer).</span><span class="sxs-lookup"><span data-stu-id="e71ba-110">**Currently Active Session Count with Active Presence Subscriptions**, which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users)</span></span>

  - <span data-ttu-id="e71ba-111">**Anzahl der derzeit aktiven Sitzungen**: Dies ist die aktuelle Anzahl von Endpunkten, die über UCWA oder den Mobilitätsdienst registriert wurden.</span><span class="sxs-lookup"><span data-stu-id="e71ba-111">**Currently Active Session Count**, which is the current number of endpoints registered through UCWA or the Mobility Service</span></span>

<span data-ttu-id="e71ba-112">Wenn der Unterschied zwischen **Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements** und **Anzahl der derzeit aktiven Sitzungen** im Laufe der Zeit gering ist, bedeutet dies, dass die meisten Benutzer ein Mobilgerät verwenden, dass immer verbunden ist, beispielsweise ein Android- oder Nokia-Mobilgerät (nur für Mcx).</span><span class="sxs-lookup"><span data-stu-id="e71ba-112">If the difference between **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** is small over time, this means that most mobile device users have an always-connected device, such as an Android or Nokia mobile device (for Mcx only).</span></span> <span data-ttu-id="e71ba-113">UCWA immer angeschlossene Geräte sind Apple-und Android-Geräte, auf denen lync 2013 Mobile-Clients ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e71ba-113">UCWA always-connected devices include Apple and Android devices running Lync 2013 Mobile clients).</span></span> <span data-ttu-id="e71ba-114">Wenn die **Anzahl der derzeit aktiven Sitzungen** sehr viel höher ist als die **Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements**, weist dies darauf hin, dass mehr Benutzer ein Hintergrund-Endpunktgerät unter Mcx verwenden, z. B. ein Apple iOS-Gerät oder ein Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="e71ba-114">If **Currently Active Session Count** is much higher than **Currently Active Session Count with Active Presence Subscriptions**, this indicates that more users are using a background endpoint device, such as an Apple iOS device or Windows Phone under Mcx.</span></span> <span data-ttu-id="e71ba-115">(Windows Phone ist der einzige mobile lync 2013-Client, der als dieser registriert wird).</span><span class="sxs-lookup"><span data-stu-id="e71ba-115">(Windows Phone is the only Lync 2013 Mobile client that will register as this).</span></span>

<span data-ttu-id="e71ba-116">Sie sollten eine Grenze für die **derzeit aktive Sitzungsanzahl mit aktiven Anwesenheitsabonnements** und **derzeit aktiven Sitzungen zählen** -Leistungsindikatoren basierend auf ihrer erwarteten Nutzung, den Ergebnissen der Kapazitätsplanung und der laufenden Überwachung des mobilitätsdiensts und anderer Front-End-Server-Leistungsindikatoren festzulegen.</span><span class="sxs-lookup"><span data-stu-id="e71ba-116">You should set a limit on the **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** performance counters based on your expected usage, capacity planning results, and ongoing monitoring of Mobility Service and other Front End Server counters.</span></span> <span data-ttu-id="e71ba-117">Die festgelegten Beschränkungen sollten das Auswerten der Serverkapazität und das Auslösen von Warnungen bei einer Kapazitätsüberschreitung erlauben.</span><span class="sxs-lookup"><span data-stu-id="e71ba-117">The limits you set should enable you to evaluate server capacity and raise alerts when capacity is exceeded.</span></span>

<span data-ttu-id="e71ba-118">Um die entsprechenden Grenzwerte zu ermitteln, müssen Sie zunächst ermitteln, wie viel Arbeitsspeicher auf dem Front-End-Server für den Mobilitätsdienst zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="e71ba-118">To determine the appropriate limits, you need to first determine how much memory is available on the Front End Server for the Mobility Service.</span></span> <span data-ttu-id="e71ba-119">Überwachen Sie die Leistungsindikatoren, um anhand der folgenden Formel festzustellen, ob zusätzliche Kapazität eingeplant werden muss:</span><span class="sxs-lookup"><span data-stu-id="e71ba-119">Monitor the counters to determine when you need to plan for extra capacity, according to the following formula:</span></span>

<span data-ttu-id="e71ba-120">Gesamtspeicher des MCX-mobilitätsdiensts (MB) = 164 + (400 + 134)/1024 \* **derzeit aktive Sitzungsanzahl mit aktiven Anwesenheitsabonnements** + 400/1024 \* (**derzeit aktive Sitzungsanzahl** – derzeit aktive Sitzungsanzahl **mit aktiven Anwesenheitsabonnements**)</span><span class="sxs-lookup"><span data-stu-id="e71ba-120">Total memory used by the Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 \* **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 \* (**Currently Active Session Count** – **Currently Active Session Count with Active Presence Subscriptions**)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e71ba-121">Der Microsoft lync Server 2010-Kapazitäts Rechner ist eine Kalkulationstabelle, die alle Formeln enthält, mit denen ein Planner ermitteln kann, welche Anforderungen für die Server gelten, einschließlich CPU, Arbeitsspeicher und Festplatte.</span><span class="sxs-lookup"><span data-stu-id="e71ba-121">The Microsoft Lync Server 2010 Capacity Calculator is a spreadsheet that is prepopulated with all of the formulas that enable a planner to determine what the requirements will be for the servers, including CPU, memory, and hard drive.</span></span> <span data-ttu-id="e71ba-122">Sie können die Kalkulationstabelle und ein zugehöriges Dokument herunterladen unter:<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span><span class="sxs-lookup"><span data-stu-id="e71ba-122">You can download the spreadsheet and an associated document at: <A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span></span>



</div>

<span data-ttu-id="e71ba-123">Der Front-End-Server benötigt genügend Arbeitsspeicher, um den Mobilitätsdienst in Failover-Situationen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e71ba-123">The Front End Server needs enough available memory to support the Mobility Service in failover situations.</span></span> <span data-ttu-id="e71ba-124">Sie können den aktuellen verfügbaren Arbeitsspeicher auf dem Front-End-Server überwachen, indem Sie den **Speicher\\verfügbaren MBytes** -Indikator verwenden oder die oben erwähnte Formel verwenden, um die Menge des Arbeitsspeichers zu planen, den der Mobilitätsdienst zu verwenden erwartet.</span><span class="sxs-lookup"><span data-stu-id="e71ba-124">You can monitor the current available memory on the Front End Server by using the **Memory\\Available Mbytes** counter, or by using the equation mentioned earlier, to plan for the amount of memory that you expect the Mobility Service to use.</span></span>

<span data-ttu-id="e71ba-125">Wenn die auf dem Front-End-Server verfügbare Arbeitsspeichermenge unter 1.500 MB liegt, wenn Sie die erwartete Anzahl von Mobilitäts Benutzern planen, müssen Sie weitere Hardware hinzufügen, um den Mobilitätsdienst zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e71ba-125">If the amount of memory available on the Front End Server is lower than 1,500 MB when you plan for the expected number of mobility users, you need to add more hardware to support the Mobility Service.</span></span> <span data-ttu-id="e71ba-126">Weitere Informationen finden Sie unter über [Wachen der Mobilität für die Leistung in lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e71ba-126">For more details, see [Monitoring mobility for performance in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) in the Operations documentation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e71ba-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e71ba-127">See Also</span></span>


[<span data-ttu-id="e71ba-128">Überwachen der Mobilität für die Leistung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e71ba-128">Monitoring mobility for performance in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

