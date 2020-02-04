---
title: 'Lync Server 2013: Überwachen der Mobilität für die Leistung'
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
ms.openlocfilehash: 53bd9c3450617d4fd1db54b52efe0b0938c84c8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a><span data-ttu-id="82c04-102">Überwachen der Mobilität für die Leistung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82c04-102">Monitoring mobility for performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82c04-103">_**Letztes Änderungsdatum des Themas:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="82c04-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="82c04-104">Der lync Server Mobility Service (MCX) und die Unified Communications Web-API (UCWA) erhöhen die Auslastung von Front-End-Servern und Front-End-Pools.</span><span class="sxs-lookup"><span data-stu-id="82c04-104">The Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="82c04-105">Mobile Geräte, die eine Verbindung mit dem Server beibehalten, auch wenn die Mobile Anwendung minimiert ist, wie etwa Android-und Nokia-Geräte mit lync 2010 Mobile sowie Android-und Apple-Geräte, auf denen lync 2013 Mobile ausgeführt wird, stellen eine größere Belastung als Geräte dar, die die Verbindung zum Server wird beendet, wenn die Mobile Anwendung minimiert wird.</span><span class="sxs-lookup"><span data-stu-id="82c04-105">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="82c04-106">Nimmt die Nutzung der Mobilitätsdienste zu, müssen Sie die Mobilitätsleistung überwachen, um festzustellen, ob die Kapazität erhöht werden muss.</span><span class="sxs-lookup"><span data-stu-id="82c04-106">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

<span data-ttu-id="82c04-107">Die Mobilitätsleistung wird durch mehrere Limits beeinflusst:</span><span class="sxs-lookup"><span data-stu-id="82c04-107">Several limits influence mobility performance:</span></span>

  - <span data-ttu-id="82c04-108">Verfügbarer Speicher</span><span class="sxs-lookup"><span data-stu-id="82c04-108">Available memory</span></span>

  - <span data-ttu-id="82c04-109">Anforderungswarteschlangenlimit</span><span class="sxs-lookup"><span data-stu-id="82c04-109">Request queue limit</span></span>

  - <span data-ttu-id="82c04-110">Gleichzeitige Verbindungen</span><span class="sxs-lookup"><span data-stu-id="82c04-110">Concurrent connections</span></span>

  - <span data-ttu-id="82c04-111">IIS-Warteschlangenlänge</span><span class="sxs-lookup"><span data-stu-id="82c04-111">IIS queue length</span></span>

<span data-ttu-id="82c04-112">Andere Grenzwerte für Server, die die Mobilitätsleistung beeinflussen können, sind maximal zwölf gleichzeitige Anmeldungen, Authentifizierungen, Sitzungs Verlängerungen und Kündigungen.</span><span class="sxs-lookup"><span data-stu-id="82c04-112">Other limits on servers that can influence mobility performance are a maximum of twelve concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="82c04-113">Diese Höchstwerte müssen für die meisten Bereitstellungen nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="82c04-113">These maximums do not need to be modified for most deployments.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="82c04-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="82c04-114">In This Section</span></span>

  - [<span data-ttu-id="82c04-115">Überwachen der Speicher Kapazitätsgrenzwerte von Servern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82c04-115">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [<span data-ttu-id="82c04-116">Überwachen des mobilitätsdiensts und der UCWA-Verwendung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82c04-116">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [<span data-ttu-id="82c04-117">Konfigurieren des mobilitätsdiensts für die Höchstleistung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82c04-117">Configuring Mobility Service for high performance in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [<span data-ttu-id="82c04-118">Überwachen von IIS-Anforderungs Protokollierungs Protokolldateien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82c04-118">Monitoring IIS request tracing log files in Lync Server 2013</span></span>](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [<span data-ttu-id="82c04-119">Mobilitäts Leistungsindikatoren in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82c04-119">Mobility performance counters in Lync Server 2013</span></span>](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

