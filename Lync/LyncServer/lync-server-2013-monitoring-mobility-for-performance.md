---
title: 'Lync Server 2013: Überwachen der Mobilität für Leistung'
description: 'Lync Server 2013: Überwachen der Mobilität auf Leistung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6c366542e88406df043ba1a782ee12cd64bd804
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562901"
---
# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a><span data-ttu-id="d065d-103">Überwachen der Mobilität auf Leistung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d065d-103">Monitoring mobility for performance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d065d-104">_**Letztes Änderungsstand des Themas:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="d065d-104">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="d065d-105">Der lync Server Mobilitätsdienst (MCX) und die Unified Communications Web API (UCWA) die Last auf Front-End-Servern und Front-End-Pools zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="d065d-105">The Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="d065d-106">Mobile Geräte, die eine Verbindung mit dem Server auch dann aufrecht erhalten, wenn die Mobile Anwendung minimiert ist, wie etwa Android-und Nokia-Geräte, auf denen lync 2010 Mobile ausgeführt wird, sowie Android-und Apple-Geräte, auf denen lync 2013 Mobile ausgeführt wird, legen eine höhere Last als Geräte fest, die Ihre Verbindung mit dem Server beenden, wenn die Mobile Anwendung minimiert wird.</span><span class="sxs-lookup"><span data-stu-id="d065d-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="d065d-107">Wenn Ihre Mobilitäts Nutzung zunimmt, müssen Sie die Mobilitätsleistung überwachen, um zu ermitteln, wann Sie Ihre Kapazität erhöhen müssen.</span><span class="sxs-lookup"><span data-stu-id="d065d-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

<span data-ttu-id="d065d-108">Die Mobilitätsleistung wird durch mehrere Limits beeinflusst:</span><span class="sxs-lookup"><span data-stu-id="d065d-108">Several limits influence mobility performance:</span></span>

  - <span data-ttu-id="d065d-109">Verfügbarer Speicher</span><span class="sxs-lookup"><span data-stu-id="d065d-109">Available memory</span></span>

  - <span data-ttu-id="d065d-110">Anforderungswarteschlangenlimit</span><span class="sxs-lookup"><span data-stu-id="d065d-110">Request queue limit</span></span>

  - <span data-ttu-id="d065d-111">Gleichzeitige Verbindungen</span><span class="sxs-lookup"><span data-stu-id="d065d-111">Concurrent connections</span></span>

  - <span data-ttu-id="d065d-112">IIS-Warteschlangenlänge</span><span class="sxs-lookup"><span data-stu-id="d065d-112">IIS queue length</span></span>

<span data-ttu-id="d065d-113">Andere Grenzwerte für Server, die die Mobilitätsleistung beeinflussen können, sind maximal zwölf gleichzeitige Anmeldungen, Authentifizierungen, Sitzungs Verlängerungen und Terminierungen.</span><span class="sxs-lookup"><span data-stu-id="d065d-113">Other limits on servers that can influence mobility performance are a maximum of twelve concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="d065d-114">Diese Maximalwerte müssen für die meisten Bereitstellungen nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d065d-114">These maximums do not need to be modified for most deployments.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d065d-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d065d-115">In This Section</span></span>

  - [<span data-ttu-id="d065d-116">Überwachen der Kapazitätsgrenzwerte für Server Speicher in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d065d-116">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [<span data-ttu-id="d065d-117">Überwachen des mobilitätsdiensts und der UCWA Verwendung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d065d-117">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [<span data-ttu-id="d065d-118">Konfigurieren des mobilitätsdiensts für hohe Leistung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d065d-118">Configuring Mobility Service for high performance in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [<span data-ttu-id="d065d-119">Überwachen von Protokolldateien für die Protokollierung von IIS-Anforderungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d065d-119">Monitoring IIS request tracing log files in Lync Server 2013</span></span>](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [<span data-ttu-id="d065d-120">Mobilitäts Leistungsindikatoren in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d065d-120">Mobility performance counters in Lync Server 2013</span></span>](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

