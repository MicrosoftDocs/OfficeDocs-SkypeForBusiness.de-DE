---
title: 'Lync Server 2013: Tägliche Aufgaben'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Daily tasks
ms:assetid: f7a5f99e-5d2b-445d-9ba1-cbfcfeff16ae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720351(v=OCS.15)
ms:contentKeyID: 63969666
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4375b11511d3b2c88222ea36575c18ca6fcc7dfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="daily-tasks-in-lync-server-2013"></a><span data-ttu-id="66a5b-102">Tägliche Aufgaben in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66a5b-102">Daily tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66a5b-103">_**Letztes Änderungsdatum des Themas:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="66a5b-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="66a5b-104">Um die Verfügbarkeit und Zuverlässigkeit der lync Server 2013-Bereitstellung zu gewährleisten, sollten Sie im Rahmen des täglichen routinemäßigen Monitors und der Testelemente, die für die Funktionsweise des Systems wichtig sind, einschließlich der physikalischen Plattform, des Betriebssystems und alle wichtigen lync Server 2013-Dienste.</span><span class="sxs-lookup"><span data-stu-id="66a5b-104">To help ensure the availability and reliability of the Lync Server 2013 deployment, you should as part of daily routine monitor and test elements that are very important to the functioning of the system, which includes the physical platform, the operating system, and all important Lync Server 2013 services.</span></span> <span data-ttu-id="66a5b-105">Vorbeugende Wartung und proaktive Überwachung helfen Ihnen bei der Ermittlung potenzieller Fehler und Probleme, die sich negativ auf die lync Server 2013-Bereitstellung auswirken können.</span><span class="sxs-lookup"><span data-stu-id="66a5b-105">Preventive maintenance and proactive monitoring will help you identify potential errors and issues that may adversely affect the Lync Server 2013 deployment.</span></span>

<span data-ttu-id="66a5b-106">Das Überwachen der lync Server 2013-Bereitstellung umfasst das Überprüfen auf Probleme mit Verbindungen, Diensten, Server Ressourcen und Systemressourcen.</span><span class="sxs-lookup"><span data-stu-id="66a5b-106">Monitoring the Lync Server 2013 deployment involves checking for issues with connections, services, server resources, and system resources.</span></span> <span data-ttu-id="66a5b-107">Windows Server-Betriebssysteme, zusammen mit System Center Operations Manager und lync Server, bieten Ihnen zahlreiche Überwachungstools und-Dienste, um sicherzustellen, dass die lync Server-Organisation reibungslos läuft.</span><span class="sxs-lookup"><span data-stu-id="66a5b-107">Windows Server operating systems, together with System Center Operations Manager, and Lync Server give you many monitoring tools and services to help ensure that the Lync Server organization is running smoothly.</span></span> <span data-ttu-id="66a5b-108">Wenn diese Technologien gemeinsam implementiert werden, können Administratoren Warnungen erhalten, wenn oder bevor Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="66a5b-108">When these technologies are implemented together, administrators will be able to receive alerts when or before issues occur.</span></span>

<span data-ttu-id="66a5b-109">Eine tägliche Überwachung bietet unter anderem die folgenden Vorteile:</span><span class="sxs-lookup"><span data-stu-id="66a5b-109">The key advantages to daily monitoring are as follows:</span></span>

  - <span data-ttu-id="66a5b-110">Erfüllen der Leistungs- und Verfügbarkeitsanforderungen definierter SLAs</span><span class="sxs-lookup"><span data-stu-id="66a5b-110">Meeting the performance and availability requirements of defined SLAs.</span></span>

  - <span data-ttu-id="66a5b-111">Erfolgreiches Abschließen spezieller administrativer Aufgaben wie tägliche Sicherungsvorgänge und Überprüfen der Serverintegrität</span><span class="sxs-lookup"><span data-stu-id="66a5b-111">Successfully completing specific administrative tasks, such as daily backup operations, and checking server health.</span></span>

  - <span data-ttu-id="66a5b-112">Erkennen und Behandeln von Problemen wie Engpässe in der Serverleistung oder ein Bedarf für zusätzliche Ressourcen, bevor sich die Probleme auf die Produktivität auswirken</span><span class="sxs-lookup"><span data-stu-id="66a5b-112">Detecting and addressing issues, such as bottlenecks in the server performance, or need for additional resources before they affect productivity.</span></span>

<span data-ttu-id="66a5b-113">Mithilfe von täglichen Wartungsaufgaben kann das Administrationsteam ein Kriterium oder eine Baseline für den normalen Systembetrieb in der Organisation definieren oder einrichten und anormale Aktivitäten erkennen.</span><span class="sxs-lookup"><span data-stu-id="66a5b-113">Daily maintenance tasks help the administrative team to define or establish a criteria or baseline for normal systems operations within the organization, and to detect any abnormal activity.</span></span> <span data-ttu-id="66a5b-114">Es ist wichtig, diese täglichen Wartungsaufgaben zu implementieren, damit das Verwaltungsteam Daten zur lync Server 2013-Infrastruktur erfassen und verwalten kann, wie etwa Nutzungs Ebenen, mögliche Leistungsengpässe und administrative Änderungen.</span><span class="sxs-lookup"><span data-stu-id="66a5b-114">It is important to implement these daily maintenance tasks so that the administrative team can capture and maintain data about the Lync Server 2013 infrastructure, such as usage levels, possible performance bottlenecks, and administrative changes.</span></span>

<span data-ttu-id="66a5b-115">Verwenden Sie die [Tägliche Aufgabenprüfliste](lync-server-2013-operations-checklists.md), um die Leistung täglicher Aufgaben zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="66a5b-115">To help organize the performance of daily tasks, use the [Daily task checklist](lync-server-2013-operations-checklists.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="66a5b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66a5b-116">See Also</span></span>


[<span data-ttu-id="66a5b-117">Tägliche Aufgabenprüfliste</span><span class="sxs-lookup"><span data-stu-id="66a5b-117">Daily task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

