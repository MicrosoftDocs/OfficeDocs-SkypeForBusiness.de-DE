---
title: 'Lync Server 2013: tägliche Aufgaben'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Daily tasks
ms:assetid: f7a5f99e-5d2b-445d-9ba1-cbfcfeff16ae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720351(v=OCS.15)
ms:contentKeyID: 63969666
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 777d0fdfc8857022c0a54fcb1cd237b90f68d9d9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516642"
---
# <a name="daily-tasks-in-lync-server-2013"></a><span data-ttu-id="6c546-102">Tägliche Aufgaben in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c546-102">Daily tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c546-103">_**Letztes Änderungsstand des Themas:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="6c546-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="6c546-104">Um die Verfügbarkeit und Zuverlässigkeit der lync Server 2013-Bereitstellung sicherzustellen, sollten Sie im Rahmen der täglichen Routineüberwachung und Testen von Elementen, die für die Funktionsweise des Systems wichtig sind, die die physische Plattform, das Betriebssystem und alle wichtigen lync Server 2013 Dienste umfassen.</span><span class="sxs-lookup"><span data-stu-id="6c546-104">To help ensure the availability and reliability of the Lync Server 2013 deployment, you should as part of daily routine monitor and test elements that are very important to the functioning of the system, which includes the physical platform, the operating system, and all important Lync Server 2013 services.</span></span> <span data-ttu-id="6c546-105">Vorbeugende Wartung und proaktive Überwachung helfen Ihnen bei der Ermittlung möglicher Fehler und Probleme, die sich negativ auf die lync Server 2013-Bereitstellung auswirken können.</span><span class="sxs-lookup"><span data-stu-id="6c546-105">Preventive maintenance and proactive monitoring will help you identify potential errors and issues that may adversely affect the Lync Server 2013 deployment.</span></span>

<span data-ttu-id="6c546-106">Das Überwachen der lync Server 2013-Bereitstellung umfasst das Überprüfen auf Probleme mit Verbindungen, Diensten, Server Ressourcen und Systemressourcen.</span><span class="sxs-lookup"><span data-stu-id="6c546-106">Monitoring the Lync Server 2013 deployment involves checking for issues with connections, services, server resources, and system resources.</span></span> <span data-ttu-id="6c546-107">Windows Server-Betriebssysteme, zusammen mit System Center Operations Manager und lync Server Ihnen zahlreiche Überwachungstools und-Dienste zur Verfügung stellen, um sicherzustellen, dass die lync Server Organisation reibungslos ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6c546-107">Windows Server operating systems, together with System Center Operations Manager, and Lync Server give you many monitoring tools and services to help ensure that the Lync Server organization is running smoothly.</span></span> <span data-ttu-id="6c546-108">Wenn diese Technologien gemeinsam implementiert werden, können Administratoren Warnungen erhalten, wenn oder bevor Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="6c546-108">When these technologies are implemented together, administrators will be able to receive alerts when or before issues occur.</span></span>

<span data-ttu-id="6c546-109">Im Folgenden werden die wichtigsten Vorteile der täglichen Überwachung vorgestellt:</span><span class="sxs-lookup"><span data-stu-id="6c546-109">The key advantages to daily monitoring are as follows:</span></span>

  - <span data-ttu-id="6c546-110">Erfüllen der Leistungs-und Verfügbarkeitsanforderungen definierter SLAs</span><span class="sxs-lookup"><span data-stu-id="6c546-110">Meeting the performance and availability requirements of defined SLAs.</span></span>

  - <span data-ttu-id="6c546-111">Erfolgreiche Ausführung bestimmter administrativer Aufgaben wie tägliche Sicherungsvorgänge und Überprüfen der Serverintegrität.</span><span class="sxs-lookup"><span data-stu-id="6c546-111">Successfully completing specific administrative tasks, such as daily backup operations, and checking server health.</span></span>

  - <span data-ttu-id="6c546-112">Erkennen und Beheben von Problemen wie Engpässen in der Serverleistung oder benötigen zusätzlicher Ressourcen, bevor diese die Produktivität beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="6c546-112">Detecting and addressing issues, such as bottlenecks in the server performance, or need for additional resources before they affect productivity.</span></span>

<span data-ttu-id="6c546-113">Tägliche Wartungsaufgaben unterstützen das Verwaltungsteam beim Definieren oder Festlegen von Kriterien oder Grundlinien für normale Systemvorgänge innerhalb der Organisation und zum erkennen anormaler Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="6c546-113">Daily maintenance tasks help the administrative team to define or establish a criteria or baseline for normal systems operations within the organization, and to detect any abnormal activity.</span></span> <span data-ttu-id="6c546-114">Es ist wichtig, diese täglichen Wartungsaufgaben zu implementieren, damit das Verwaltungsteam Daten über die lync Server 2013 Infrastruktur erfassen und verwalten kann, wie etwa Nutzungsgrade, mögliche Leistungsengpässe und administrative Änderungen.</span><span class="sxs-lookup"><span data-stu-id="6c546-114">It is important to implement these daily maintenance tasks so that the administrative team can capture and maintain data about the Lync Server 2013 infrastructure, such as usage levels, possible performance bottlenecks, and administrative changes.</span></span>

<span data-ttu-id="6c546-115">Zur Unterstützung der Organisation der Leistung von täglichen Aufgaben verwenden Sie die [Checkliste tägliche Aufgaben](lync-server-2013-operations-checklists.md).</span><span class="sxs-lookup"><span data-stu-id="6c546-115">To help organize the performance of daily tasks, use the [Daily task checklist](lync-server-2013-operations-checklists.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="6c546-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c546-116">See Also</span></span>


[<span data-ttu-id="6c546-117">Prüfliste für tägliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="6c546-117">Daily task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

