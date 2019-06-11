---
title: 'Lync Server 2013: Überwachen der Netzwerkleistung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2fa3c2685b4da32d5f2e3f123a938920b5ce9f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-network-performance-in-lync-server-2013"></a><span data-ttu-id="4d1fc-102">Überwachen der Netzwerkleistung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d1fc-102">Monitoring network performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d1fc-103">_**Letztes Änderungsdatum des Themas:** 2016-04-27_</span><span class="sxs-lookup"><span data-stu-id="4d1fc-103">_**Topic Last Modified:** 2016-04-27_</span></span>

<span data-ttu-id="4d1fc-104">Lync Server 2013 ist eine echt Zeit Kommunikationstechnologie, die stark vom Netzwerk abhängig ist, um die Kommunikation zwischen Benutzern zu ermöglichen – entweder durch Instant Messaging (im), Sprachanrufe oder Videokommunikation.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-104">Lync Server 2013 is a real-time communications technology that relies heavily on the network to enable communication between users—either through instant messaging (IM), voice calls, or video communication.</span></span> <span data-ttu-id="4d1fc-105">Daher ist es wichtig, die Netzwerkleistung kontinuierlich zu überwachen, um sicherzustellen, dass die von einem Benutzer gewählte Kommunikations Modalität die bestmögliche Nutzung bietet.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-105">It is therefore important to monitor the network performance continuously to help guarantee that a user’s chosen communication modality provides the best possible experience.</span></span>

<span data-ttu-id="4d1fc-106">Die Netzwerkleistung kann auf zwei Ebenen gemessen werden:</span><span class="sxs-lookup"><span data-stu-id="4d1fc-106">Network performance can be measured at two levels:</span></span>

  - <span data-ttu-id="4d1fc-107">**Gesamtnetzwerkleistung**   diese Stufe der Leistungsmessung ermöglicht es einer Organisation, eine "Big-Picture"-Ansicht Ihres Netzwerks zu erstellen und wird in der Regel über Netzwerk Überwachungssysteme von Drittanbietern implementiert.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-107">**Overall network performance**   This level of performance measurement will allow an organization to create a "big-picture" view of their network and is usually implemented through third-party network monitoring systems.</span></span> <span data-ttu-id="4d1fc-108">Diese Systeme empfangen Leistungs-und Kapazitätsdaten von Remotenetzwerk Geräten wie Routern und werden im gesamten Netzwerk gewechselt, damit Administratoren die Integrität einer bestimmten Netzwerkkomponente zu jeder Tageszeit ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-108">These systems will receive performance and capacity data from remote network devices such as routers and switched throughout the network to allow administrators to determine the health of any given network component at any time of day.</span></span>

  - <span data-ttu-id="4d1fc-109">**Individuelle Serverleistung**   diese Ebene der Leistungsmessung ist auf einen bestimmten Server limitiert und unterstützt Administratoren bei der Messung der Netzwerkleistung eines bestimmten Servers, um entweder bei der Problembehandlung einer bestimmten Leistung zu helfen. Sie können die Leistung des jeweiligen Servers während eines bestimmten Zeitraums im Rahmen eines Kapazitäts Planungsprozesses abwägen oder bewerten.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-109">**Individual server performance**   This level of performance measurement is limited to a specific server and will help administrators with gauging the network performance of a specific server to either help with troubleshooting a specific performance issue or to gauge the respective server’s performance over a given period as part of a capacity planning process.</span></span>

<span data-ttu-id="4d1fc-110">Sie können das Netzwerk überwachen, indem Sie die in den folgenden Abschnitten beschriebenen Tools verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-110">You can monitor the network by using the tools described in the following sections.</span></span>

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a><span data-ttu-id="4d1fc-111">Tools zur allgemeinen Netzwerk Leistungsüberwachung</span><span class="sxs-lookup"><span data-stu-id="4d1fc-111">Tools for Overall Network Performance Monitoring</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="4d1fc-112">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="4d1fc-112">System Center Operations Manager 2012</span></span>

<span data-ttu-id="4d1fc-113">System Center Operations Manager bietet eine End-to-End-Dienstverwaltung, die einfach angepasst und für verbesserte Dienstebenen in einer IT-Umgebung erweitert werden kann.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-113">System Center Operations Manager provides end-to-end service management that is easy to customize and extend for improved service levels across an IT environment.</span></span> <span data-ttu-id="4d1fc-114">Auf diese Weise können Operations-und IT-Verwaltungsteams Probleme erkennen und beheben, die sich auf die Integrität verteilter IT-Dienste auswirken.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-114">This enables Operations and IT Management teams to identify, and resolve issues affecting the health of distributed IT services.</span></span> <span data-ttu-id="4d1fc-115">Die End-to-End-Dienstverwaltung ist nicht auf Microsoft-basierte Umgebungen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-115">End-to-end service management is not restricted to Microsoft-based environments.</span></span> <span data-ttu-id="4d1fc-116">Unterstützung für Webdienste für die Verwaltung (WS-Management), SNMP (Simple Network Management Protocol) und Partnerlösungen ermöglichen Systeme, die keine Microsoft-Betriebssysteme und-Hardware ausführen, um in System Center in die Dienstüberwachung einbezogen zu werden. Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-116">Support for Web Services for Management (WS-Management), Simple Network Management Protocol (SNMP), and partner solutions allow for systems that do not run Microsoft operating systems and hardware to be included in service monitoring within System Center Operations Manager 2012.</span></span>

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a><span data-ttu-id="4d1fc-117">System Center Operations Manager 2012 und Netzwerkverwaltungslösungen von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="4d1fc-117">System Center Operations Manager 2012 and Third-Party Network Management Solutions</span></span>

<span data-ttu-id="4d1fc-118">**EMC Smarts**   EMC-Lösungen für Operations Manager unterstützen Sie bei der schnellen Behebung von Problemen, die sich auf die gesamten Serviceebenen auswirken.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-118">**EMC Smarts**   EMC Solutions for Operations Manager help you quickly resolve issues affecting service levels throughout.</span></span> <span data-ttu-id="4d1fc-119">Durch die Verwendung von EMC-Lösungen für Operations Manager können Sie Ihre gesamte IT-Service-Kette mit einer integrierten, automatisierten Lösung managen und überwachen.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-119">By using EMC Solutions for Operations Manager, you can manage and monitor your whole IT service chain with one integrated, automated solution.</span></span> <span data-ttu-id="4d1fc-120">Sie können die Ursachen von Problemen bei der Leistung und Verfügbarkeit einfach erkennen und schneller beheben, wodurch sich die Auswirkungen und Kosten verringern.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-120">You'll easily identify the root causes of performance and availability issues, and resolve them faster which reduces effects and costs.</span></span> <span data-ttu-id="4d1fc-121">Zu den wichtigsten Vorteilen gehören die folgenden:</span><span class="sxs-lookup"><span data-stu-id="4d1fc-121">Key benefits include the following:</span></span>

  - <span data-ttu-id="4d1fc-122">Ein fortschrittliches, nutzerfreundliches Management konzentriert sich auf die Bereitstellung von strategischem geschäftlichen Nutzen, anstatt die verwirrenden Warnungen manuell zu sortieren und zu filtern.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-122">Advanced, easy-to-use management   Focus on delivering strategic business value instead of manually sorting and filtering confusing alerts.</span></span>

  - <span data-ttu-id="4d1fc-123">**Schnellere Lösungen**   lösen IT-Probleme und reagieren auf geschäftliche Anforderungen schneller, wodurch sich die Wirkung und die Kosten verringern.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-123">**Faster resolution**   Solve IT issues and respond to business needs faster, reducing effect and cost.</span></span>

  - <span data-ttu-id="4d1fc-124">**Optimierte Vorgänge**   vermeiden IT-Komplexität durch Kombinieren mehrerer Verwaltungstools, Anwendungen und Terminals.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-124">**Streamlined operations**   Avoid IT complexity by combining multiple management tools, applications, and terminals.</span></span>

<span data-ttu-id="4d1fc-125">Weitere Informationen finden Sie hier:</span><span class="sxs-lookup"><span data-stu-id="4d1fc-125">More information can be found here:</span></span>

[<span data-ttu-id="4d1fc-126">Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="4d1fc-126">Microsoft System Center Operations Manager</span></span>](http://go.microsoft.com/fwlink/p/?linkid=243651)

[<span data-ttu-id="4d1fc-127">Lösungen für Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="4d1fc-127">Solutions for Microsoft System Center Operations Manager</span></span>](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a><span data-ttu-id="4d1fc-128">Lösungen von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="4d1fc-128">Third-Party Solutions</span></span>

<span data-ttu-id="4d1fc-129">**HP Network Management Center (vormals als HP OpenView bezeichnet)** Das    [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) bietet integriertes Fehler-und Leistungs Management, um die Netzwerkverfügbarkeit und-Leistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-129">**HP Network Management Center (previously known as HP OpenView)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) provides integrated fault and performance management to improve network availability and performance.</span></span> <span data-ttu-id="4d1fc-130">Network Management Center ist Teil der automatischen HP-Netzwerkverwaltungslösung, die Fehler-, Leistungs-, Konfigurations-und Änderungsverwaltung vereint.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-130">Network Management Center is part of the HP automated network management solution that unifies fault, performance, configuration, and change management.</span></span>

<span data-ttu-id="4d1fc-131">**Cisco-Netzwerkmanagement-und-Automatisierungsprodukte**   für das Unternehmen bietet Cisco verschiedene Verwaltungsprodukte, einschließlich der CiscoWorks-LAN-Verwaltungslösung und des Cisco-Netzwerkanalyse Moduls, um die operative Effizienz zu verbessern und reduzieren Sie die Netzwerkausfälle.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-131">**Cisco Network Management and Automation products**   For the Enterprise, Cisco has several management products available including CiscoWorks LAN Management Solution and Cisco Network Analysis Module, to help improve operational efficiency and reduce network downtime.</span></span> <span data-ttu-id="4d1fc-132">Weitere Informationen zu diesen Produkten finden Sie auf der Cisco-Website unter [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html).</span><span class="sxs-lookup"><span data-stu-id="4d1fc-132">For additional data on these products, refer to the Cisco website at [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html).</span></span>

<span data-ttu-id="4d1fc-133">SNMP (Simple Network Management Protocol, SNMP) ist ein Netzwerkverwaltungsstandard, der eine Strategie für die Verwaltung von TCP/IP-Netzwerken definiert.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-133">Simple Network Management Protocol (SNMP)   Simple Network Management Protocol (SNMP) is a network management standard that defines a strategy for managing TCP/IP networks.</span></span> <span data-ttu-id="4d1fc-134">SNMP ermöglicht Ihnen, Konfigurations-und Statusinformationen über das Netzwerk zu erfassen und die Informationen an einen festgelegten Computer zur Ereignisüberwachung zu senden.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-134">SNMP enables you to capture configuration and status information about the network, and send the information to a designated computer for event monitoring.</span></span> <span data-ttu-id="4d1fc-135">Dieses standardbasierte Netzwerkverwaltungsprotokoll verwendet eine verteilte Architektur, die Folgendes umfasst:</span><span class="sxs-lookup"><span data-stu-id="4d1fc-135">This standards based network management protocol uses a distributed architecture that includes the following:</span></span>

  - <span data-ttu-id="4d1fc-136">Mehrere verwaltete Knoten mit einer SNMP-Entität, die als Agent bezeichnet wird und Remotezugriff auf die Verwaltungsinstrumentation bietet.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-136">Multiple managed nodes, each with an SNMP entity called an agent which provides remote access to management instrumentation.</span></span>

  - <span data-ttu-id="4d1fc-137">Mindestens eine SNMP-Entität, die als Manager bezeichnet wird und Verwaltungsanwendungen ausführt, um verwaltete Elemente zu überwachen und zu steuern.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-137">At least one SNMP entity known as a manager which runs management applications to monitor and control managed elements.</span></span> <span data-ttu-id="4d1fc-138">Verwaltete Elemente sind Geräte wie Hosts, Router usw.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-138">Managed elements are devices such as hosts, routers, and so on.</span></span> <span data-ttu-id="4d1fc-139">Sie werden überwacht und kontrolliert, indem Sie auf Ihre Verwaltungsinformationen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-139">They are monitored and controlled by accessing their management information.</span></span>

  - <span data-ttu-id="4d1fc-140">Ein Verwaltungsprotokoll, SNMP, wird verwendet, um Verwaltungsinformationen zwischen den Verwaltungsstationen und Agents zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-140">A management protocol, SNMP, is used to communicate management information between the management stations and agents.</span></span> <span data-ttu-id="4d1fc-141">Verwaltungsinformationen bezieht sich auf eine Sammlung verwalteter Objekte, die in einem virtuellen Informationsspeicher (Management Information Base, MIB) enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-141">Management information refers to a collection of managed objects that live in a virtual information store called a Management Information Base (MIB).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4d1fc-142">Oben finden Sie Beispiele für Netzwerk Überwachungslösungen von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-142">Examples of third-party network monitoring solutions are provided above.</span></span> <span data-ttu-id="4d1fc-143">Diese Liste ist nicht endgültig, und Microsoft bevorzugt keine spezifische Anbieter Lösung.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-143">This list is not definitive and Microsoft does not favor any specific vendor solution.</span></span> <span data-ttu-id="4d1fc-144">Erkundigen Sie sich bei einem Netzwerkdienstanbieter und ihrem jeweiligen Technologieanbieter, wie Sie die beste Netzwerküberwachungslösung für Ihre Organisation ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-144">Consult with a network service provider and or your respective technology provider to determine the best network monitoring solution for your organization.</span></span>



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a><span data-ttu-id="4d1fc-145">Tools zum Überwachen der einzelnen Server Netzwerkleistung</span><span class="sxs-lookup"><span data-stu-id="4d1fc-145">Tools for Monitoring Individual Server Network Performance</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="4d1fc-146">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="4d1fc-146">System Center Operations Manager 2012</span></span>

<span data-ttu-id="4d1fc-147">Mit System Center Operations Manager 2012 können Administratoren die Netzwerkleistung einzelner Server über das Windows Server 2012-Management Pack anzeigen: das Windows Server-Betriebssystem-Management Pack enthält ein Management Pack für die Leistung Damit können Administratoren die Leistung des Netzwerkadapters und den Adapterstatus überwachen.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-147">System Center Operations Manager 2012 would allow administrators to view network performance of individual servers through the Windows Server 2012 Management Pack: The Windows Server operating system management pack includes a "Performance" management pack that would allow administrators to monitor Network Adapter performance and adapter health.</span></span>

</div>

<div>

## <a name="windows-network-monitor"></a><span data-ttu-id="4d1fc-148">Windows-Netzwerk Monitor</span><span class="sxs-lookup"><span data-stu-id="4d1fc-148">Windows Network Monitor</span></span>

<span data-ttu-id="4d1fc-149">Sammelt, zeigt, analysiert die Ressourcennutzung auf einem Server und misst den Netzwerkdatenverkehr.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-149">Collects, displays, analyzes resource usage on a server, and measures network traffic.</span></span> <span data-ttu-id="4d1fc-150">Netzwerkmonitor überwacht ausschließlich die Netzwerkaktivität.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-150">Network Monitor exclusively monitors network activity.</span></span> <span data-ttu-id="4d1fc-151">Durch die Erfassung und Analyse von Netzwerkdaten und die Verwendung dieser Daten mit Leistungsprotokollen können Sie die Netzwerkauslastung ermitteln, Netzwerkprobleme identifizieren und zukünftige Netzwerkanforderungen Vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-151">By capturing and analyzing network data, and using this data with performance logs, you can determine the network usage, identify network issues, and forecast future network needs.</span></span>

<span data-ttu-id="4d1fc-152">Weitere Informationen zu Netzwerkmonitor 3,4 und Informationen zum Installieren und Konfigurieren des Netzwerkmonitors sowie zum Aufzeichnen und Analysieren von Daten finden Sie in dieser Sitzung: Übersicht über den Netzwerkmonitor 3,3.</span><span class="sxs-lookup"><span data-stu-id="4d1fc-152">For more information about Network Monitor 3.4, and to learn how to install and configure Network Monitor and capture and analyze data, review this session: Network Monitor 3.3 Overview.</span></span> <span data-ttu-id="4d1fc-153">Überprüfen Sie außerdem den [Blog des Netzwerkmonitors](http://blogs.technet.com/b/netmon/).</span><span class="sxs-lookup"><span data-stu-id="4d1fc-153">Also, review the [Network Monitor blog](http://blogs.technet.com/b/netmon/).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

