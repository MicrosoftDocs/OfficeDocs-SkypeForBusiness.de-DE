---
title: 'Lync Server 2013: Überwachen der Netzwerkleistung'
description: 'Lync Server 2013: Überwachen der Netzwerkleistung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ead7e3f9001b06c783c9b22327581e795a20322
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549451"
---
# <a name="monitoring-network-performance-in-lync-server-2013"></a><span data-ttu-id="82810-103">Überwachen der Netzwerkleistung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82810-103">Monitoring network performance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82810-104">_**Letztes Änderungsstand des Themas:** 2016-04-27_</span><span class="sxs-lookup"><span data-stu-id="82810-104">_**Topic Last Modified:** 2016-04-27_</span></span>

<span data-ttu-id="82810-105">Lync Server 2013 ist eine echt Zeit Kommunikationstechnologie, die in hohem Maße auf das Netzwerk angewiesen ist, um die Kommunikation zwischen Benutzern zu ermöglichen – entweder über Sofortnachrichten (Chat), Sprachanrufe oder Videokommunikation.</span><span class="sxs-lookup"><span data-stu-id="82810-105">Lync Server 2013 is a real-time communications technology that relies heavily on the network to enable communication between users—either through instant messaging (IM), voice calls, or video communication.</span></span> <span data-ttu-id="82810-106">Es ist daher wichtig, die Netzwerkleistung kontinuierlich zu überwachen, um sicherzustellen, dass die gewählte Kommunikations Modalität eines Benutzers die bestmögliche Erfahrung bietet.</span><span class="sxs-lookup"><span data-stu-id="82810-106">It is therefore important to monitor the network performance continuously to help guarantee that a user’s chosen communication modality provides the best possible experience.</span></span>

<span data-ttu-id="82810-107">Die Netzwerkleistung kann auf zwei Ebenen gemessen werden:</span><span class="sxs-lookup"><span data-stu-id="82810-107">Network performance can be measured at two levels:</span></span>

  - <span data-ttu-id="82810-108">**Gesamtnetzwerkleistung**     Diese Leistungsmessung ermöglicht es einer Organisation, eine "Big-Picture"-Ansicht Ihres Netzwerks zu erstellen, die in der Regel über Netzwerk Überwachungssysteme von Drittanbietern implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="82810-108">**Overall network performance**   This level of performance measurement will allow an organization to create a "big-picture" view of their network and is usually implemented through third-party network monitoring systems.</span></span> <span data-ttu-id="82810-109">Auf diesen Systemen werden Leistungs-und Kapazitätsdaten von Remotenetzwerk Geräten wie Router empfangen und im Netzwerk umgeschaltet, sodass Administratoren zu jeder Tageszeit die Integrität einer bestimmten Netzwerkkomponente bestimmen können.</span><span class="sxs-lookup"><span data-stu-id="82810-109">These systems will receive performance and capacity data from remote network devices such as routers and switched throughout the network to allow administrators to determine the health of any given network component at any time of day.</span></span>

  - <span data-ttu-id="82810-110">**Individuelle Serverleistung**     Diese Leistungsmessung ist auf einen bestimmten Server limitiert und unterstützt Administratoren bei der Bewertung der Netzwerkleistung eines bestimmten Servers, um entweder bei der Problembehandlung eines bestimmten Leistungsproblems behilflich zu sein oder um die Leistung des jeweiligen Servers über einen bestimmten Zeitraum im Rahmen eines Kapazitäts Planungsprozesses zu messen.</span><span class="sxs-lookup"><span data-stu-id="82810-110">**Individual server performance**   This level of performance measurement is limited to a specific server and will help administrators with gauging the network performance of a specific server to either help with troubleshooting a specific performance issue or to gauge the respective server’s performance over a given period as part of a capacity planning process.</span></span>

<span data-ttu-id="82810-111">Sie können das Netzwerk überwachen, indem Sie die in den folgenden Abschnitten beschriebenen Tools verwenden.</span><span class="sxs-lookup"><span data-stu-id="82810-111">You can monitor the network by using the tools described in the following sections.</span></span>

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a><span data-ttu-id="82810-112">Tools für die allgemeine Überwachung der Netzwerkleistung</span><span class="sxs-lookup"><span data-stu-id="82810-112">Tools for Overall Network Performance Monitoring</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="82810-113">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="82810-113">System Center Operations Manager 2012</span></span>

<span data-ttu-id="82810-114">System Center Operations Manager bietet eine End-to-End-Dienstverwaltung, die einfach angepasst und für verbesserte Dienstebenen in einer IT-Umgebung erweitert werden kann.</span><span class="sxs-lookup"><span data-stu-id="82810-114">System Center Operations Manager provides end-to-end service management that is easy to customize and extend for improved service levels across an IT environment.</span></span> <span data-ttu-id="82810-115">Auf diese Weise können Betriebs-und IT-Verwaltungsteams Probleme identifizieren und beheben, die sich auf die Integrität verteilter IT-Dienste auswirken.</span><span class="sxs-lookup"><span data-stu-id="82810-115">This enables Operations and IT Management teams to identify, and resolve issues affecting the health of distributed IT services.</span></span> <span data-ttu-id="82810-116">Die End-to-End-Dienstverwaltung ist nicht auf Microsoft-basierte Umgebungen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="82810-116">End-to-end service management is not restricted to Microsoft-based environments.</span></span> <span data-ttu-id="82810-117">Unterstützung für Webdienste für Verwaltung (WS-Management), SNMP (Simple Network Management Protocol) und Partnerlösungen ermöglichen Systemen, die Microsoft-Betriebssysteme und-Hardware nicht ausführen, die in der Dienstüberwachung in System Center Operations Manager 2012 enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="82810-117">Support for Web Services for Management (WS-Management), Simple Network Management Protocol (SNMP), and partner solutions allow for systems that do not run Microsoft operating systems and hardware to be included in service monitoring within System Center Operations Manager 2012.</span></span>

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a><span data-ttu-id="82810-118">System Center Operations Manager 2012 und Netzwerkverwaltungslösungen von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="82810-118">System Center Operations Manager 2012 and Third-Party Network Management Solutions</span></span>

<span data-ttu-id="82810-119">**EMC Smarts**     EMC Lösungen für Operations Manager unterstützen Sie bei der schnellen Behebung von Problemen, die sich auf die Dienstebenen auswirken.</span><span class="sxs-lookup"><span data-stu-id="82810-119">**EMC Smarts**   EMC Solutions for Operations Manager help you quickly resolve issues affecting service levels throughout.</span></span> <span data-ttu-id="82810-120">Durch die Verwendung von EMC Lösungen für Operations Manager können Sie Ihre gesamte IT-Servicekette mit einer integrierten, automatisierten Lösung verwalten und überwachen.</span><span class="sxs-lookup"><span data-stu-id="82810-120">By using EMC Solutions for Operations Manager, you can manage and monitor your whole IT service chain with one integrated, automated solution.</span></span> <span data-ttu-id="82810-121">Sie können die Ursachen von Problemen mit der Leistung und der Verfügbarkeit leicht erkennen und schneller beheben, wodurch Effekte und Kosten reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="82810-121">You'll easily identify the root causes of performance and availability issues, and resolve them faster which reduces effects and costs.</span></span> <span data-ttu-id="82810-122">Zu den wichtigsten Vorteilen zählen folgende:</span><span class="sxs-lookup"><span data-stu-id="82810-122">Key benefits include the following:</span></span>

  - <span data-ttu-id="82810-123">Fortschrittliches, einfach zu bedienendes Management konzentrieren Sie sich auf die Bereitstellungeines strategischen Geschäftswerts anstelle von manueller Sortierung und Filterung verwirrender Warnungen.</span><span class="sxs-lookup"><span data-stu-id="82810-123">Advanced, easy-to-use management   Focus on delivering strategic business value instead of manually sorting and filtering confusing alerts.</span></span>

  - <span data-ttu-id="82810-124">**Schnellere Auflösung**     Lösen Sie IT-Probleme, und reagieren Sie schneller auf geschäftliche Anforderungen, wodurch sich Wirkung und Kosten reduzieren.</span><span class="sxs-lookup"><span data-stu-id="82810-124">**Faster resolution**   Solve IT issues and respond to business needs faster, reducing effect and cost.</span></span>

  - <span data-ttu-id="82810-125">**Optimierte Vorgänge**     Vermeiden Sie IT-Komplexität durch Kombinieren mehrerer Verwaltungstools, Anwendungen und Terminals.</span><span class="sxs-lookup"><span data-stu-id="82810-125">**Streamlined operations**   Avoid IT complexity by combining multiple management tools, applications, and terminals.</span></span>

<span data-ttu-id="82810-126">Weitere Informationen finden Sie hier:</span><span class="sxs-lookup"><span data-stu-id="82810-126">More information can be found here:</span></span>

[<span data-ttu-id="82810-127">Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="82810-127">Microsoft System Center Operations Manager</span></span>](https://go.microsoft.com/fwlink/p/?linkid=243651)

[<span data-ttu-id="82810-128">Lösungen für Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="82810-128">Solutions for Microsoft System Center Operations Manager</span></span>](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a><span data-ttu-id="82810-129">Lösungen von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="82810-129">Third-Party Solutions</span></span>

<span data-ttu-id="82810-130">HP **Network Management Center (bisher als HP OpenView bezeichnet)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) bietet integriertes Fehler-und Leistungs Management zur Verbesserung der Netzwerkverfügbarkeit und-Leistung.</span><span class="sxs-lookup"><span data-stu-id="82810-130">**HP Network Management Center (previously known as HP OpenView)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) provides integrated fault and performance management to improve network availability and performance.</span></span> <span data-ttu-id="82810-131">Network Management Center ist Teil der HP Automated Network Management-Lösung, die Fehler-, Leistungs-, Konfigurations-und Änderungsverwaltung vereint.</span><span class="sxs-lookup"><span data-stu-id="82810-131">Network Management Center is part of the HP automated network management solution that unifies fault, performance, configuration, and change management.</span></span>

<span data-ttu-id="82810-132">**Cisco-Netzwerk Management-und Automatisierungsprodukte**     Für das Unternehmen stehen verschiedene Verwaltungsprodukte zur Verfügung, einschließlich CiscoWorks LAN-Verwaltungslösung und Cisco-Netzwerkanalyse Modul, um die betriebliche Effizienz zu verbessern und die Ausfallzeit des Netzwerks zu verringern.</span><span class="sxs-lookup"><span data-stu-id="82810-132">**Cisco Network Management and Automation products**   For the Enterprise, Cisco has several management products available including CiscoWorks LAN Management Solution and Cisco Network Analysis Module, to help improve operational efficiency and reduce network downtime.</span></span> <span data-ttu-id="82810-133">Weitere Informationen zu diesen Produkten finden Sie auf der Cisco-Website unter [https://www.cisco.com/en/US/products/sw/netmgtsw/index.html](https://www.cisco.com/en/us/products/sw/netmgtsw/index.html) .</span><span class="sxs-lookup"><span data-stu-id="82810-133">For additional data on these products, refer to the Cisco website at [https://www.cisco.com/en/US/products/sw/netmgtsw/index.html](https://www.cisco.com/en/us/products/sw/netmgtsw/index.html).</span></span>

<span data-ttu-id="82810-134">SNMP (Simple Network Management Protocol) Simple Network Management Protocol (SNMP) ist ein Netzwerkverwaltungsstandard, der eine Strategie für die Verwaltung von TCP/IP-Netzwerken definiert.</span><span class="sxs-lookup"><span data-stu-id="82810-134">Simple Network Management Protocol (SNMP)   Simple Network Management Protocol (SNMP) is a network management standard that defines a strategy for managing TCP/IP networks.</span></span> <span data-ttu-id="82810-135">SNMP ermöglicht es Ihnen, Konfigurations-und Statusinformationen zum Netzwerk zu erfassen und die Informationen an einen bestimmten Computer für die Ereignisüberwachung zu senden.</span><span class="sxs-lookup"><span data-stu-id="82810-135">SNMP enables you to capture configuration and status information about the network, and send the information to a designated computer for event monitoring.</span></span> <span data-ttu-id="82810-136">Dieses standardbasierte Netzwerkverwaltungsprotokoll verwendet eine verteilte Architektur, die Folgendes umfasst:</span><span class="sxs-lookup"><span data-stu-id="82810-136">This standards based network management protocol uses a distributed architecture that includes the following:</span></span>

  - <span data-ttu-id="82810-137">Mehrere verwaltete Knoten mit jeweils einer SNMP-Entität, die als Agent bezeichnet wird und den Remotezugriff auf Verwaltungsinstrumentation ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="82810-137">Multiple managed nodes, each with an SNMP entity called an agent which provides remote access to management instrumentation.</span></span>

  - <span data-ttu-id="82810-138">Mindestens eine SNMP-Entität, die als Manager bezeichnet wird und Verwaltungsanwendungen zum Überwachen und Steuern verwalteter Elemente ausführt.</span><span class="sxs-lookup"><span data-stu-id="82810-138">At least one SNMP entity known as a manager which runs management applications to monitor and control managed elements.</span></span> <span data-ttu-id="82810-139">Verwaltete Elemente sind Geräte wie Hosts, Router usw.</span><span class="sxs-lookup"><span data-stu-id="82810-139">Managed elements are devices such as hosts, routers, and so on.</span></span> <span data-ttu-id="82810-140">Sie werden durch Zugriff auf Ihre Verwaltungsinformationen überwacht und gesteuert.</span><span class="sxs-lookup"><span data-stu-id="82810-140">They are monitored and controlled by accessing their management information.</span></span>

  - <span data-ttu-id="82810-141">Ein Verwaltungsprotokoll, SNMP, wird verwendet, um Verwaltungsinformationen zwischen den Verwaltungsstationen und Agents zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="82810-141">A management protocol, SNMP, is used to communicate management information between the management stations and agents.</span></span> <span data-ttu-id="82810-142">Verwaltungsinformationen bezieht sich auf eine Sammlung von verwalteten Objekten, die in einem virtuellen Informationsspeicher mit dem Namen "Management Information Base (MIB)" Leben.</span><span class="sxs-lookup"><span data-stu-id="82810-142">Management information refers to a collection of managed objects that live in a virtual information store called a Management Information Base (MIB).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="82810-143">Beispiele für Netzwerk Überwachungslösungen von Drittanbietern werden oben bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="82810-143">Examples of third-party network monitoring solutions are provided above.</span></span> <span data-ttu-id="82810-144">Diese Liste ist nicht endgültig, und Microsoft favorisiert keine bestimmte Anbieter Lösung.</span><span class="sxs-lookup"><span data-stu-id="82810-144">This list is not definitive and Microsoft does not favor any specific vendor solution.</span></span> <span data-ttu-id="82810-145">Wenden Sie sich an einen Netzwerkdienstanbieter und ihren jeweiligen Technologieanbieter, um die beste Netzwerküberwachungslösung für Ihre Organisation zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="82810-145">Consult with a network service provider and or your respective technology provider to determine the best network monitoring solution for your organization.</span></span>



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a><span data-ttu-id="82810-146">Tools zum Überwachen der einzelnen Server Netzwerkleistung</span><span class="sxs-lookup"><span data-stu-id="82810-146">Tools for Monitoring Individual Server Network Performance</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="82810-147">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="82810-147">System Center Operations Manager 2012</span></span>

<span data-ttu-id="82810-148">Mit System Center Operations Manager 2012 können Administratoren die Netzwerkleistung einzelner Server über das Windows Server 2012 Management Pack anzeigen: das Windows Server-Betriebssystem-Management Pack enthält ein Management Pack für die Leistung, mit dem Administratoren die Leistung von Netzwerkadaptern und die Adapter Integrität überwachen können.</span><span class="sxs-lookup"><span data-stu-id="82810-148">System Center Operations Manager 2012 would allow administrators to view network performance of individual servers through the Windows Server 2012 Management Pack: The Windows Server operating system management pack includes a "Performance" management pack that would allow administrators to monitor Network Adapter performance and adapter health.</span></span>

</div>

<div>

## <a name="windows-network-monitor"></a><span data-ttu-id="82810-149">Windows-Netzwerk Monitor</span><span class="sxs-lookup"><span data-stu-id="82810-149">Windows Network Monitor</span></span>

<span data-ttu-id="82810-150">Sammelt, zeigt, analysiert die Ressourcennutzung auf einem Server und misst den Netzwerkdatenverkehr.</span><span class="sxs-lookup"><span data-stu-id="82810-150">Collects, displays, analyzes resource usage on a server, and measures network traffic.</span></span> <span data-ttu-id="82810-151">Netzwerkmonitor überwacht ausschließlich die Netzwerkaktivität.</span><span class="sxs-lookup"><span data-stu-id="82810-151">Network Monitor exclusively monitors network activity.</span></span> <span data-ttu-id="82810-152">Durch das erfassen und Analysieren von Netzwerkdaten und die Verwendung dieser Daten mit Leistungsprotokollen können Sie die Netzwerkauslastung ermitteln, Netzwerkprobleme identifizieren und zukünftige Netzwerkanforderungen prognostizieren.</span><span class="sxs-lookup"><span data-stu-id="82810-152">By capturing and analyzing network data, and using this data with performance logs, you can determine the network usage, identify network issues, and forecast future network needs.</span></span>

<span data-ttu-id="82810-153">Weitere Informationen zu Netzwerkmonitor 3,4 und Informationen zum Installieren und Konfigurieren des Netzwerkmonitors sowie zum Erfassen und Analysieren von Daten finden Sie in dieser Sitzung: Network Monitor 3,3 Overview.</span><span class="sxs-lookup"><span data-stu-id="82810-153">For more information about Network Monitor 3.4, and to learn how to install and configure Network Monitor and capture and analyze data, review this session: Network Monitor 3.3 Overview.</span></span> <span data-ttu-id="82810-154">Überprüfen Sie außerdem den [Blog Netzwerk Monitor](https://blogs.technet.com/b/netmon/).</span><span class="sxs-lookup"><span data-stu-id="82810-154">Also, review the [Network Monitor blog](https://blogs.technet.com/b/netmon/).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

