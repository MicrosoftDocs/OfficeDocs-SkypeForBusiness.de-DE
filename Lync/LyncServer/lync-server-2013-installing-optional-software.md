---
title: 'Lync Server 2013: Installieren von optionaler Software'
description: 'Lync Server 2013: Installieren von optionaler Software.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing optional software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615032(v=OCS.15)
ms:contentKeyID: 51541509
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7423c0d54b762fb4af7cedc8d7ba8745fd94bdf7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573911"
---
# <a name="installing-optional-software-in-lync-server-2013"></a><span data-ttu-id="7e4b4-103">Installieren von optionaler Software in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e4b4-103">Installing optional software in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e4b4-104">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="7e4b4-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="7e4b4-105">Das Planungs Tool für Microsoft lync Server 2013 wurde für den Export in Microsoft Excel und Microsoft Visio entwickelt.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-105">The Microsoft Lync Server 2013, Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="7e4b4-106">Diese Anwendungen sind zwar für den Betrieb des Planungstools nicht erforderlich, fügen jedoch für die Bereitstellung und Dokumentation Ihres Entwurfs einen erheblichen Mehrwert hinzu.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-106">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

<div>

## <a name="optional-software"></a><span data-ttu-id="7e4b4-107">Optionale Software</span><span class="sxs-lookup"><span data-stu-id="7e4b4-107">Optional Software</span></span>

<div>

## <a name="microsoft-excel"></a><span data-ttu-id="7e4b4-108">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="7e4b4-108">Microsoft Excel</span></span>

<span data-ttu-id="7e4b4-109">Wenn Sie Ihren Entwurf in Microsoft Excel exportieren, wird ein Bericht erstellt, in dem sieben Registerkarten im Arbeitsblatt angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="7e4b4-109">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

  - <span data-ttu-id="7e4b4-110">Zusammenfassung – zeigt Informationen zur Websitekonfiguration an, einschließlich Benutzeranzahl, Kapazitätseinstellungen und Server Profilinformationen.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-110">Summary – Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

  - <span data-ttu-id="7e4b4-111">Hardwareprofil – Zeigt einen Bericht zu den empfohlenen Hardwarekonfigurationen für Server an, die in der Topologie angegeben sind (einschließlich CPU, Arbeitsspeicher, Datenträger und Netzwerkschnittstelle).</span><span class="sxs-lookup"><span data-stu-id="7e4b4-111">Hardware Profile – Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="7e4b4-112">Die Menge und die empfohlenen Spezifikationen für die Server Komponenten sind ebenfalls enthalten.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-112">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="7e4b4-113">Darüber hinaus wird jeder Server durch die Website definiert, um eine vollständige Darstellung der Server Anforderungen nach Standort bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-113">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

  - <span data-ttu-id="7e4b4-114">Ports Requirements – zeigt einen Bericht über alle aktivierten Ports sowie die Zuordnung zu Domänennamen System-Lastenausgleich (DNS lb) und Hardwarelastenausgleichs (HLB) an.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-114">Ports Requirements – Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="7e4b4-115">Verwenden Sie diesen Bericht, um Ihre Firewall-und DNS-lb-und HLB-Konfigurationen zu planen.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-115">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

  - <span data-ttu-id="7e4b4-116">Zusammenfassender Bericht – zeigt die allgemeine Zusammenfassung der Einstellungen an, die zum Einrichten Ihres Edgeserver Netzwerks erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-116">Summary Report – Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

  - <span data-ttu-id="7e4b4-117">Certificates Report – zeigt den Antragstellernamen und die alternativen Antragstellernamen an, die für die für die Ausführung der Edgeserver erforderlichen Zertifikate erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-117">Certificates Report – Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

  - <span data-ttu-id="7e4b4-118">Firewallbericht – zeigt die Quell-und Zielports sowie IP-Adressen sowohl für externe als auch für interne Schnittstellen an.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-118">Firewall Report – Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

  - <span data-ttu-id="7e4b4-119">DNS-Bericht – zeigt den vollqualifizierten Domänennamen (FQDN) und die IP/VIP-Adressen an, die für jeden von Ihnen erstellten DNS-Eintrag erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-119">DNS Report – Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

</div>

<div>

## <a name="microsoft-visio"></a><span data-ttu-id="7e4b4-120">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="7e4b4-120">Microsoft Visio</span></span>

<span data-ttu-id="7e4b4-p104">Beim Exportieren Ihres Entwurfs nach Microsoft Visio wird ein Diagramm erstellt, das Sie zur Dokumentation Ihrer konfigurierten Topologie und Infrastruktur verwenden können. Das importierte Diagramm kann bearbeitet und neu angeordnet werden, um Ihre Dokumentationsanforderungen zu erfüllen. Das typische Visio-Diagramm umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7e4b4-p104">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure. The imported diagram can be edited and rearranged to meet your documentation needs. The typical Visio diagram will include:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7e4b4-124">Wenn Ihr Entwurf groß genug ist, um mehr als drei Front-End-Server zu erfordern, wird eine zusätzliche Seite für die Front-End-Pool, die Front-End-Server, den Computer mit SQL Server, IP-Adressen und FQDNs erstellt.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-124">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>



</div>

  - <span data-ttu-id="7e4b4-125">Globale Topologie – Diagramm der konfigurierten lync Server 2013 Websites.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-125">Global Topology – Diagram of configured Lync Server 2013 sites.</span></span>

  - <span data-ttu-id="7e4b4-126">Registerkarte "Website Name" – zeigt die Standort Konfigurationstopologie mit Edgeserver, einer Firewall, einem PSTN (Public Switched Telephone Network) und Gateways sowie der internen Server Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-126">Site Name tab – Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="7e4b4-127">Die interne Bereitstellung besteht aus konfigurierten Servern und Pools, einschließlich der Front-End-Pools, SQL Server basierten Servern, Active Directory-Domänendienste, Directors, Exchange Unified Messaging (um) Servern, Exchange-Postfachservern, Office-webapps-Servern, Vermittlungsservern und Servern für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-127">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

  - <span data-ttu-id="7e4b4-128">Edge-Netzwerkdiagramm – Diagramm, in dem die Edgeserver Konfiguration mit zugeordneten IP-Adressen und FQDNs erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-128">Edge Network Diagram – Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="7e4b4-129">DNS-Lastenausgleich und Hardwarelastenausgleich sind ebenfalls enthalten.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-129">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="7e4b4-130">Darüber hinaus werden Directors und die Front-End-Server oder Front-End-Pool mit zugeordneten DNS lb oder HLB und der zugewiesenen IP-Adresse (das Planungs Tool unterstützt sowohl IPv4-als auch IPv6-Adressen) und FQDN angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7e4b4-130">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7e4b4-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e4b4-131">See Also</span></span>


[<span data-ttu-id="7e4b4-132">Installieren des Planungstools in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e4b4-132">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

