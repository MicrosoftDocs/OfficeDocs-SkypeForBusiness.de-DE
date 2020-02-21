---
title: 'Lync Server 2013: Überwachen der Kapazitätsgrenzwerte für Server Speicher'
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
ms.openlocfilehash: e969de7198eecf43b57ea00fa0591bbeb06da0b1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a><span data-ttu-id="12197-102">Überwachen der Kapazitätsgrenzwerte für Server Speicher in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12197-102">Monitoring for server memory capacity limits in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12197-103">_**Letztes Änderungsstand des Themas:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="12197-103">_**Topic Last Modified:** 2016-12-08_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> <span data-ttu-id="12197-104">Die Informationen in diesem Thema, die sich auf die Kapazitätsplanung beziehen, beziehen sich nur auf lync 2010 Mobile-Clients und den Mobilitätsdienst (MCX).</span><span class="sxs-lookup"><span data-stu-id="12197-104">The information in this topic that refers to Capacity Planning pertains only to Lync 2010 Mobile clients and the Mobility Service (Mcx).</span></span> <span data-ttu-id="12197-105">Die Kapazitätsplanung für die Unified Communications Web API (UCWA), die von den lync 2013 mobilen Clients verwendet wird, wird vom Planungs Tool lync Server 2013 bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="12197-105">Capacity Planning for the Unified Communications Web API (UCWA), used by the Lync 2013 Mobile clients, is provided by the Lync Server 2013, Planning Tool.</span></span>



</div>

<span data-ttu-id="12197-106">Zwei Mobilitäts Leistungsindikatoren helfen Ihnen bei der Ermittlung Ihrer aktuellen Nutzung und unterstützen Sie bei der Planung der Kapazität für den lync Server 2013 Mobilitätsdienst (MCX) sowie beim Überwachen der Speicherauslastung für UCWA.</span><span class="sxs-lookup"><span data-stu-id="12197-106">Two mobility performance counters can help you to determine your current usage and help you plan capacity for the Lync Server 2013 Mobility Service (Mcx), as well as to monitor memory usage for UCWA.</span></span> <span data-ttu-id="12197-107">Für UCWA ist die Leistungsindikatorkategorie **ls: Online – UCWA**.</span><span class="sxs-lookup"><span data-stu-id="12197-107">For UCWA, the counter category is **LS:WEB – UCWA**.</span></span> <span data-ttu-id="12197-108">Für den Mobilitätsdienst (MCX) befinden sich die Leistungsindikatoren unter der Kategorie **ls: mobiler Kommunikationsdienst**.</span><span class="sxs-lookup"><span data-stu-id="12197-108">For the Mobility Service (Mcx), the counters are under the category **LS:WEB - Mobile Communication Service**.</span></span> <span data-ttu-id="12197-109">Zu überwachende Leistungsindikatoren sind:</span><span class="sxs-lookup"><span data-stu-id="12197-109">The counters to monitor are:</span></span>

  - <span data-ttu-id="12197-110">**Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements**(Dies ist die aktuelle Anzahl von Endpunkten, die über UCWA registriert sind) oder der Mobilitätsdienst (MCX) mit aktiven Anwesenheitsabonnements (Anzahl von immer verbundenen mobilen Benutzern)</span><span class="sxs-lookup"><span data-stu-id="12197-110">**Currently Active Session Count with Active Presence Subscriptions**, which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users)</span></span>

  - <span data-ttu-id="12197-111">**Anzahl der derzeit aktiven Sitzungen**, bei der es sich um die aktuelle Anzahl von Endpunkten handelt, die über UCWA oder den Mobilitätsdienst registriert sind</span><span class="sxs-lookup"><span data-stu-id="12197-111">**Currently Active Session Count**, which is the current number of endpoints registered through UCWA or the Mobility Service</span></span>

<span data-ttu-id="12197-112">Wenn der Unterschied zwischen der **Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements** und der **aktuell aktiven Sitzungsanzahl** im Laufe der Zeit gering ist, bedeutet dies, dass die meisten Benutzer eines mobilen Geräts über ein immer verbundenes Gerät wie ein Android-oder Nokia Mobilgerät verfügen (nur für MCX).</span><span class="sxs-lookup"><span data-stu-id="12197-112">If the difference between **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** is small over time, this means that most mobile device users have an always-connected device, such as an Android or Nokia mobile device (for Mcx only).</span></span> <span data-ttu-id="12197-113">UCWA immer verbundene Geräte sind Apple-und Android-Geräte, auf denen lync 2013 Mobile Clients installiert sind).</span><span class="sxs-lookup"><span data-stu-id="12197-113">UCWA always-connected devices include Apple and Android devices running Lync 2013 Mobile clients).</span></span> <span data-ttu-id="12197-114">Wenn die **Anzahl der derzeit aktiven Sitzungen** viel höher ist als die Anzahl der **derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements**, deutet dies darauf hin, dass mehr Benutzer ein Hintergrund Endgerät wie ein Apple IOS-Gerät oder Windows Phone unter MCX verwenden.</span><span class="sxs-lookup"><span data-stu-id="12197-114">If **Currently Active Session Count** is much higher than **Currently Active Session Count with Active Presence Subscriptions**, this indicates that more users are using a background endpoint device, such as an Apple iOS device or Windows Phone under Mcx.</span></span> <span data-ttu-id="12197-115">(Windows Phone ist der einzige lync 2013 Mobile Client, der sich als dieser registrieren wird).</span><span class="sxs-lookup"><span data-stu-id="12197-115">(Windows Phone is the only Lync 2013 Mobile client that will register as this).</span></span>

<span data-ttu-id="12197-116">Sie sollten einen Grenzwert für die **Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements** und **derzeit aktiven Sitzungs Zähl** Leistungsindikatoren auf der Grundlage ihrer erwarteten Nutzung, der Kapazitäts Planungsergebnisse und der laufenden Überwachung des mobilitätsdiensts und anderer Front-End-Server Indikatoren festlegen.</span><span class="sxs-lookup"><span data-stu-id="12197-116">You should set a limit on the **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** performance counters based on your expected usage, capacity planning results, and ongoing monitoring of Mobility Service and other Front End Server counters.</span></span> <span data-ttu-id="12197-117">Mit den von Ihnen festgelegten Grenzwerten sollten Sie die Serverkapazität auswerten und Warnungen auslösen können, wenn die Kapazität überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="12197-117">The limits you set should enable you to evaluate server capacity and raise alerts when capacity is exceeded.</span></span>

<span data-ttu-id="12197-118">Um die entsprechenden Grenzwerte zu ermitteln, müssen Sie zuerst bestimmen, wie viel Arbeitsspeicher im Front-End-Server für den Mobilitätsdienst verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="12197-118">To determine the appropriate limits, you need to first determine how much memory is available on the Front End Server for the Mobility Service.</span></span> <span data-ttu-id="12197-119">Überwachen Sie die Leistungsindikatoren, um zu bestimmen, wann Sie eine zusätzliche Kapazität planen müssen, entsprechend der folgenden Formel:</span><span class="sxs-lookup"><span data-stu-id="12197-119">Monitor the counters to determine when you need to plan for extra capacity, according to the following formula:</span></span>

<span data-ttu-id="12197-120">Gesamtarbeitsspeicher des MCX-mobilitätsdiensts (MB) = 164 + (400 + 134)/1024 \* **derzeit aktive Sitzungsanzahl mit aktiven Anwesenheitsabonnements** + 400/1024 \* (**derzeit aktive Sitzungsanzahl** – derzeit aktive Sitzungsanzahl **mit aktiven Anwesenheitsabonnements**)</span><span class="sxs-lookup"><span data-stu-id="12197-120">Total memory used by the Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 \* **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 \* (**Currently Active Session Count** – **Currently Active Session Count with Active Presence Subscriptions**)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="12197-121">Der Microsoft lync Server 2010 Kapazitäts Rechner ist eine Arbeitsmappe, die mit allen Formeln vorab aufgefüllt ist, mit denen ein Planer bestimmen kann, welche Anforderungen für die Server gelten, einschließlich CPU, Arbeitsspeicher und Festplatte.</span><span class="sxs-lookup"><span data-stu-id="12197-121">The Microsoft Lync Server 2010 Capacity Calculator is a spreadsheet that is prepopulated with all of the formulas that enable a planner to determine what the requirements will be for the servers, including CPU, memory, and hard drive.</span></span> <span data-ttu-id="12197-122">Sie können das Arbeitsblatt und ein zugehöriges Dokument herunterladen:<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span><span class="sxs-lookup"><span data-stu-id="12197-122">You can download the spreadsheet and an associated document at: <A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span></span>



</div>

<span data-ttu-id="12197-123">Der Front-End-Server benötigt genügend Arbeitsspeicher zur Unterstützung des mobilitätsdiensts in Failover-Situationen.</span><span class="sxs-lookup"><span data-stu-id="12197-123">The Front End Server needs enough available memory to support the Mobility Service in failover situations.</span></span> <span data-ttu-id="12197-124">Sie können den derzeit verfügbaren Arbeitsspeicher auf dem Front-End-Server überwachen, indem Sie den **Arbeits\\Speicher Verfügbare MBytes** verwenden oder die zuvor erwähnte Gleichung verwenden, um die Größe des Arbeitsspeichers zu planen, den Sie vom Mobilitätsdienst erwarten sollten.</span><span class="sxs-lookup"><span data-stu-id="12197-124">You can monitor the current available memory on the Front End Server by using the **Memory\\Available Mbytes** counter, or by using the equation mentioned earlier, to plan for the amount of memory that you expect the Mobility Service to use.</span></span>

<span data-ttu-id="12197-125">Wenn der verfügbare Arbeitsspeicher auf dem Front-End-Server niedriger als 1.500 MB ist, wenn Sie die erwartete Anzahl von Mobilitäts Benutzern planen, müssen Sie weitere Hardware zur Unterstützung des mobilitätsdiensts hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="12197-125">If the amount of memory available on the Front End Server is lower than 1,500 MB when you plan for the expected number of mobility users, you need to add more hardware to support the Mobility Service.</span></span> <span data-ttu-id="12197-126">Weitere Informationen finden Sie unter [Monitoring Mobility for Performance in lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="12197-126">For more details, see [Monitoring mobility for performance in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) in the Operations documentation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="12197-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12197-127">See Also</span></span>


[<span data-ttu-id="12197-128">Überwachen der Mobilität auf Leistung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12197-128">Monitoring mobility for performance in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

