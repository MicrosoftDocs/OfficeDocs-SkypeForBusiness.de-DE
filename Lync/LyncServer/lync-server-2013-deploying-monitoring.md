---
title: 'Lync Server 2013: Bereitstellen der Überwachung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e10cd492679cb412c57ea37698df198eef7721b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a><span data-ttu-id="ff38a-102">Bereitstellen der Überwachung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff38a-102">Deploying monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff38a-103">_**Letztes Änderungsstand des Themas:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="ff38a-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="ff38a-104">An der Microsoft lync Server 2013-Überwachungsinfrastruktur wurden wesentliche Änderungen vorgenommen, beginnend mit der Tatsache, dass die Monitoring Server Rolle veraltet ist.</span><span class="sxs-lookup"><span data-stu-id="ff38a-104">Major changes have been made to the Microsoft Lync Server 2013 monitoring infrastructure, beginning with the fact that the Monitoring Server role has been deprecated.</span></span> <span data-ttu-id="ff38a-105">Anstatt separater Überwachungsserverrollen (für die Organisationen in der Regel dedizierte Computer einrichten mussten, die als Überwachungsserver dienten) werden Überwachungsdienste jetzt auf jedem Front-End-Server gemeinsam ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ff38a-105">Instead of separate Monitoring Server roles (which typically required organizations to set up dedicated computers to act as Monitoring servers) monitoring services are now collocated on each Front End server.</span></span> <span data-ttu-id="ff38a-106">Unter anderem sorgt diese Änderung für folgende Vorteile:</span><span class="sxs-lookup"><span data-stu-id="ff38a-106">Among other things, this change helps to:</span></span>

  - <span data-ttu-id="ff38a-107">Verringern Sie die Anzahl der Serverrollen, die bei der Implementierung von lync Server 2013 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ff38a-107">Decrease the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="ff38a-108">In diesem Fall kann das Verringern der Überwachungsserverrolle auch Kosten sparen, da keine dedizierten Server für die Überwachung mehr erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ff38a-108">In this case, decrementing the Monitoring Server server role also helps to reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="ff38a-109">Verringern Sie die Komplexität von lync Server Einrichtung und Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="ff38a-109">Reduce the complexity of Lync Server setup and administration.</span></span> <span data-ttu-id="ff38a-110">Da die Überwachungsdienste auf jedem Front-End-Server automatisch gemeinsam ausgeführt werden, müssen Sie die Überwachungsserverrolle nicht mehr installieren, konfigurieren und verwalten.</span><span class="sxs-lookup"><span data-stu-id="ff38a-110">By automatically collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ff38a-111">Die Archivierungsserver Rolle wurde auch in lync Server 2013 veraltet.</span><span class="sxs-lookup"><span data-stu-id="ff38a-111">The Archiving Server role has also been deprecated in Lync Server 2013.</span></span> <span data-ttu-id="ff38a-112">Wie bei den Überwachungsdiensten werden nun lync Server 2013 Archivierungsdienste auf jedem Front-End-Server zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="ff38a-112">Like the monitoring services, Lync Server 2013 archiving services are now collocated on each Front End server.</span></span> <span data-ttu-id="ff38a-113">Dies sollte beachtet werden, da Überwachung und Archivierung oft auf derselben SQL Server-Datenbankinstanz ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ff38a-113">This is important to note simply because monitoring and archiving often share the same SQL Server database instance.</span></span>



</div>

<span data-ttu-id="ff38a-114">Wie Sie vielleicht erwarten, haben diese Änderungen erhebliche Auswirkungen auf die Installation und Verwaltung von Überwachungsdiensten.</span><span class="sxs-lookup"><span data-stu-id="ff38a-114">As you might expect, these changes have a major impact on how monitoring services are installed and managed.</span></span> <span data-ttu-id="ff38a-115">Da die Monitoring Server Rolle beispielsweise nicht mehr vorhanden ist, wurde der Monitoring Server Knoten aus dem lync Server Topologie-Generator entfernt. Das bedeutet wiederum, dass Sie den neuen Monitoring Server-Assistenten für den Topologie-Generator nicht mehr verwenden, um Ihrer Topologie einen neuen Monitoring Server hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ff38a-115">For example, because the Monitoring Server role no longer exists, the Monitoring Server node has been removed from the Lync Server Topology Builder; in turn, that means you no longer use Topology Builder's New Monitoring Server Wizard in order to add a new Monitoring Server to your topology.</span></span> <span data-ttu-id="ff38a-116">(Der Assistent ist nicht mehr vorhanden.) Stattdessen implementieren Sie in der Regel Überwachungsdienste in der Topologie, indem Sie die folgenden zwei Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="ff38a-116">(That wizard no longer exists.) Instead, you will typically implement monitoring services within your topology by completing the following two steps:</span></span>

1.  <span data-ttu-id="ff38a-117">Aktivieren der Überwachung bei gleichzeitiger Einrichtung eines neuen lync Server Pools.</span><span class="sxs-lookup"><span data-stu-id="ff38a-117">Enabling monitoring at the same time you set up a new Lync Server pool.</span></span> <span data-ttu-id="ff38a-118">(In lync Server 2013 ist die Überwachung auf Pool-zu-Pool-Basis aktiviert oder deaktiviert.) Beachten Sie, dass Sie die Überwachung für einen Pool aktivieren können, ohne Überwachungsdaten tatsächlich zu erfassen, ein Prozess, der in dieser Dokumentation im Abschnitt Konfigurieren der Aufzeichnung von Anrufdetails und der Einstellungen für die Qualität der Erfahrung erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="ff38a-118">(In Lync Server 2013, monitoring is enabled or disabled on a pool-by-pool basis.) Note that you can enable monitoring for a pool without actually collecting monitoring data, a process explained in the Configuring Call Detail Recording and Quality of Experience Settings section of this documentation.</span></span>

2.  <span data-ttu-id="ff38a-p107">Zuordnen eines Überwachungsspeichers (d. h. einer Überwachungsdatenbank) an den neuen Pool. Ein einzelner Überwachungsspeicher kann mehreren Pools zugeordnet werden. Anhängig von der Anzahl von Benutzern, die in Ihren Registrierungsstellenpools verwaltet werden, bedeutet dies, dass Sie keine separate Überwachungsdatenbank für jeden Pool einrichten müssen. Stattdessen können einzelne Überwachungsspeicher von mehreren Pools verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ff38a-p107">Associating a monitoring store (that is, a monitoring database) with the new pool. Note that a single monitoring store can be associated with multiple pools. Depending on the number of users homed on your Registrar pools, that means that you do not have to set up a separate monitoring database for each of your pools. Instead, single monitoring store can be used by multiple pools.</span></span>

<span data-ttu-id="ff38a-p108">Oft ist es zwar einfacher, die Überwachung gleichzeitig mit der Erstellung eines neuen Pool zu aktivieren, es ist jedoch auch möglich, bei deaktivierter Überwachung einen neuen Pool zu erstellen. In diesem Fall können Sie später den Topologie-Generator verwenden, um den Dienst zu aktivieren. Mithilfe des Topologie-Generators kann die Überwachung für einen Pool aktiviert bzw deaktiviert, oder ein Pool kann einem anderen Überwachungsspeicher zugeordnet werden. Beachten Sie, dass weiterhin mindestens ein Überwachungsspeicher erstellt werden muss, auch wenn keine Überwachungsserverrolle mehr vorhanden ist: Back-End-Datenbanken, die zum Speichern der vom Überwachungsdienst gesammelten Daten dienen. Diese Back-End-Datenbanken können mithilfe von Microsoft SQL Server 2008 R2 oder Microsoft SQL Server 2012 erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ff38a-p108">Although it's often easier to enable monitoring at the same time that you create a new pool, it's also possible to create a new pool with monitoring disabled. If you do that, you can later use Topology Builder to enable the service: Topology Builder provides a way to enable or disable monitoring for a pool, or to associate a pool with a different monitoring store. Keep in mind that even though there is no longer a Monitoring Server role you will still need to create one or more monitoring stores: backend databases used to store the data gathered by the monitoring service. These backend databases can be created using either Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ff38a-127">Wenn die Überwachung für einen Pool aktiviert wurde, können Sie den Prozess des Sammelns von Überwachungsdaten deaktivieren, ohne Ihre Topologie ändern zu müssen: lync Server-Verwaltungsshell bietet Ihnen die Möglichkeit, die Aufzeichnung von Kommunikationsdatensätzen (KDS) oder die Qualität zu deaktivieren (und später erneut zu aktivieren). QoE-Datenerfassung (Experience of Experience).</span><span class="sxs-lookup"><span data-stu-id="ff38a-127">If monitoring has been enabled for a pool you can disable the process of collecting monitoring data without having to change your topology: Lync Server Management Shell provides a way for you to disable (and then later re-enable) call detail recording (CDR) or Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="ff38a-128">Weitere Informationen finden Sie in diesem Dokument im Abschnitt "Konfigurieren von KDS (Aufzeichnung von Kommunikationsdatensätzen) und QoE (Quality of Experience)-Einstellungen".</span><span class="sxs-lookup"><span data-stu-id="ff38a-128">For more information, see the Configuring Call Detail Recording and Quality of Experience Settings section of this document.</span></span>



</div>

<span data-ttu-id="ff38a-129">Eine weitere wichtige Verbesserung der Überwachung in lync Server 2013 ist die Tatsache, dass lync Server Überwachungsberichte jetzt IPv6 unterstützen: Berichte, die das Feld IP-Adresse verwenden, werden je nach der verwendeten SQL-Abfrage entweder IPv4-oder IPv6-Adressen angezeigt. und, 2) wo die IPv6-Adresse in der Überwachungsdatenbank gespeichert ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="ff38a-129">One other important enhancement to monitoring in Lync Server 2013 is the fact that Lync Server Monitoring Reports now support IPv6: reports that use the IP Address field will display either IPv4 or IPv6 addresses depending on : 1) the SQL query being used; and, 2) where or not the IPv6 address is stored in the monitoring database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ff38a-130">Stellen Sie sicher, dass der Starttyp des SQL Server-Agent-Diensts automatisch ist und der SQL Server-Agentdienst für die SQL-Instanz ausgeführt wird, in der die Überwachungsdatenbanken gespeichert sind, sodass die Standard Überwachungs SQL Server Wartungsaufträge auf Ihrer geplanten Basis ausgeführt werden können. unter Kontrolle des SQL Server-Agent-Diensts.</span><span class="sxs-lookup"><span data-stu-id="ff38a-130">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Monitoring databases, so that the Default Monitoring SQL Server Maintenance Jobs can run on their scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

<span data-ttu-id="ff38a-131">In dieser Dokumentation werden Sie durch den Prozess der Installation und Konfiguration von Überwachungs-und Überwachungsberichten für lync Server 2013 geleitet.</span><span class="sxs-lookup"><span data-stu-id="ff38a-131">This documentation walks you through the process of installing and configuring monitoring and Monitoring Reports for Lync Server 2013.</span></span> <span data-ttu-id="ff38a-132">Die Dokumentation enthält Schritt-für-Schritt-Anleitungen für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ff38a-132">The documentation provides step-by-step instructions that will help you to:</span></span>

  - <span data-ttu-id="ff38a-133">Aktivieren der Überwachung in Ihrer Topologie und Zuordnen eines Überwachungsspeichers zu einem Front-End-Pool.</span><span class="sxs-lookup"><span data-stu-id="ff38a-133">Enable monitoring in your topology and associate a monitoring store with a Front End pool.</span></span>

  - <span data-ttu-id="ff38a-134">Installieren Sie SQL Server Reporting Services und die lync Server-Überwachungsberichte.</span><span class="sxs-lookup"><span data-stu-id="ff38a-134">Install SQL Server Reporting Services and the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="ff38a-135">Überwachungsberichte sind vorkonfigurierte Berichte, die verschiedene Einsichten in die in einer Überwachungsdatenbank gespeicherten Informationen bieten.</span><span class="sxs-lookup"><span data-stu-id="ff38a-135">Monitoring Reports are preconfigured reports that provide different views into the information stored in a monitoring database.</span></span>

  - <span data-ttu-id="ff38a-136">Konfigurieren der Aufzeichnung von Kommunikationsdatensätzen (KDS) und der Sammlung von QoE (Quality of Experience)-Daten.</span><span class="sxs-lookup"><span data-stu-id="ff38a-136">Configure call detail recording (CDR) and Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="ff38a-137">Die Aufzeichnung von Kommunikationsdatensätzen bietet Ihnen die Möglichkeit, die Verwendung von lync Server Funktionen wie VoIP-Telefon anrufen (Voice over IP) nachzuverfolgen. Instant Messaging (Sofortnachrichten); Dateiübertragungen; Audio/Video-Konferenzen (A/V); und Anwendungsfreigabesitzungen.</span><span class="sxs-lookup"><span data-stu-id="ff38a-137">Call detail recording provides a way for you to track usage of Lync Server capabilities such as Voice over IP (VoIP) phone calls; instant messaging (IM); file transfers; audio/video (A/V) conferencing; and application sharing sessions.</span></span> <span data-ttu-id="ff38a-138">QoE-Metriken dienen der Überwachung der Qualität von Audio- und Videoanrufen in Ihrer Organisation, z. B. der Anzahl der verloren gegangenen Netzwerkpakete, von Hintergrundgeräuschen und der Unterschiede bei Paketverzögerung (Jitter).</span><span class="sxs-lookup"><span data-stu-id="ff38a-138">QoE metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span>

  - <span data-ttu-id="ff38a-139">Manuelles Löschen von KDS und QoE-Datensätzen aus der Überwachungsdatenbank.</span><span class="sxs-lookup"><span data-stu-id="ff38a-139">Manually purge CDR and/or QoE records from the monitoring database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

