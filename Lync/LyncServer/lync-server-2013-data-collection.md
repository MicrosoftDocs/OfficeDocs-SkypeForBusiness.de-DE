---
title: 'Lync Server 2013: Datensammlung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e6ef9454912b2d421302d7e696350a6f83bc9fd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="data-collection-in-lync-server-2013"></a><span data-ttu-id="2c193-102">Datensammlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c193-102">Data collection in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c193-103">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="2c193-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="2c193-104">In Microsoft lync Server 2013 Kommunikationssoftware können Sie das Planungs Tool Microsoft lync Server 2013 ausführen, ohne Ihre vorhandenen und vorgeschlagenen IP-Adressen und Edgeserver vollqualifizierten Domänennamen (FQDNs) zu dokumentieren, dies ist jedoch wesentlich schwieriger ohne Konfigurationsfehler zu verursachen.</span><span class="sxs-lookup"><span data-stu-id="2c193-104">In Microsoft Lync Server 2013 communications software, you can run the Microsoft Lync Server 2013, Planning Tool without documenting your existing and proposed IP addresses and Edge Server fully qualified domain names (FQDNs), but it is significantly harder to do so without causing configuration errors.</span></span> <span data-ttu-id="2c193-105">Wenn beispielsweise die Koexistenz für einen bestimmten Zeitraum erforderlich ist, besteht ein häufiger Fehler darin, FQDNs aus einer vorhandenen Edge-Bereitstellung für Ihre lync Server 2013-Edge-Bereitstellung wiederzuverwenden.</span><span class="sxs-lookup"><span data-stu-id="2c193-105">For example, if coexistence is required for a period of time, a common mistake is to reuse FQDNs from an existing Edge deployment for your Lync Server 2013 Edge deployment.</span></span> <span data-ttu-id="2c193-106">Durch das aufschreiben vorhandener und vorgeschlagener IP-Adressen und FQDNs in einer Tabellenkalkulation, Tabelle oder in einem anderen visuellen Formular können Sie während der Installation Installationsprobleme vermeiden.</span><span class="sxs-lookup"><span data-stu-id="2c193-106">By having the existing and proposed IP addresses and FQDNs written down in a spreadsheet, table, or other visual form, you help prevent setup problems during installation.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="2c193-107">Wenn Sie frühere Versionen des Planungstools verwendet haben, haben Sie das Tool möglicherweise zum Erstellen Ihrer Topologie und des exportierten Topologie-Dokuments zur Verwendung im Topologie-Generator zum Veröffentlichen Ihrer Topologie verwendet.</span><span class="sxs-lookup"><span data-stu-id="2c193-107">If you have used previous versions of the Planning Tool, you may have used the tool to create your topology and the exported the topology document for use in Topology Builder to publish your topology.</span></span> <span data-ttu-id="2c193-108">Die Möglichkeit, die Topologie zu exportieren, wurde aus dem Planungs Tool entfernt.</span><span class="sxs-lookup"><span data-stu-id="2c193-108">The ability to export the topology was removed from Planning Tool.</span></span> <span data-ttu-id="2c193-109">Das Verwenden einer früheren Version des Planungstools zum Erstellen eines Topologie-Dokuments für lync Server 2013 wird dringend empfohlen, und es werden unerwartete Ergebnisse erzielt.</span><span class="sxs-lookup"><span data-stu-id="2c193-109">Using a previous version of the Planning Tool to create a topology document for Lync Server 2013 is strongly discouraged, and will produce unexpected results.</span></span>



</div>

<span data-ttu-id="2c193-110">Daher empfiehlt es sich, die folgende Daten Sammlungs Vorlage zu verwenden, die ihrer Edge-Topologie entspricht, um die verschiedenen FQDN-und IP-Adressen zu erfassen, die Sie in das Planungs Tool eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="2c193-110">Therefore, the recommended approach is to use the following data collection template, which corresponds to your Edge topology, to gather the various FQDN and IP addresses that you will need to enter into the Planning Tool.</span></span> <span data-ttu-id="2c193-111">Durch das Dokumentieren der aktuellen und vorgeschlagenen Konfiguration können Sie die Werte in den richtigen Kontext für Ihre Produktionsumgebung setzen.</span><span class="sxs-lookup"><span data-stu-id="2c193-111">By documenting the current and proposed configuration, you can put the values in the proper context for your production environment.</span></span> <span data-ttu-id="2c193-112">Gleichzeitig müssen Sie die Konfiguration von Koexistenz und Features, wie z. B. einfachen URLs, Dateifreigaben und Lastenausgleich, planen.</span><span class="sxs-lookup"><span data-stu-id="2c193-112">And, you are forced to think about how you will configure coexistence and features such as simple URLs, file shares, and load balancing.</span></span>

<span data-ttu-id="2c193-113">Um Microsoft lync Server 2013 erfolgreich bereitzustellen, müssen Sie die Interaktion von und das Vertrauen auf die einzelnen Komponenten verstehen.</span><span class="sxs-lookup"><span data-stu-id="2c193-113">To successfully deploy Microsoft Lync Server 2013, you need to understand the interaction of and reliance on the individual components.</span></span> <span data-ttu-id="2c193-114">Durch das Sammeln von Daten aus Ihrer vorhandenen Netzwerk-und Serverinfrastruktur und die Anwendung der Planungsanleitung in diesen Abschnitten können Sie lync Server 2013 Edgeserver-Komponenten in Ihre Infrastruktur integrieren.</span><span class="sxs-lookup"><span data-stu-id="2c193-114">By collecting data from your existing network and server infrastructure, and applying the planning guidance in these sections, you can integrate Lync Server 2013 Edge Server components into your infrastructure.</span></span>

<span data-ttu-id="2c193-115">Bei der [Auswahl einer Topologie in lync Server 2013](lync-server-2013-choosing-a-topology.md)werden drei Hauptarchitekturen mit zwei Variationen für insgesamt fünf mögliche Bereitstellungsszenarien eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2c193-115">Introduced in [Choosing a topology in Lync Server 2013](lync-server-2013-choosing-a-topology.md), there are three main architectures with two variations, for a total of five possible deployment scenarios.</span></span> <span data-ttu-id="2c193-116">Eines dieser Szenarien ist der Ausgangspunkt für die Datenerfassung.</span><span class="sxs-lookup"><span data-stu-id="2c193-116">One of these scenarios will be the starting point for your data collection.</span></span> <span data-ttu-id="2c193-117">Die IP-Adressen, Servernamen und Domänennamen sind Beispiele, die den Zertifikat-, Firewall und DNS-Diagrammen entsprechen, welche die erforderlichen Informationen für eine umfassende Planungslösung enthalten.</span><span class="sxs-lookup"><span data-stu-id="2c193-117">The IP addresses, server names, and domain names are examples that coincide with the matching certificate, firewall, and DNS diagrams that detail the information required for a complete planning solution.</span></span> <span data-ttu-id="2c193-118">Die Diagramme und die Angabe der erforderlichen Werte für Zertifikate, DNS und Firewalls spielen bei der teamübergreifenden Kommunikation eine besonders wichtige Rolle, bei der die Verwaltung von Zertifizierungsstelle, Firewallkonfiguration und DNS von anderen Teams als dem Team, das die Bereitstellung plant, ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2c193-118">The diagrams and filling in your required certificate, DNS and firewall values is especially important in cross-team communications where the management of the certification authority, firewall configuration and DNS is managed by teams other than the team that plans the deployment.</span></span> <span data-ttu-id="2c193-119">Die Diagramme liefern Informationen zu erforderlichen Komponenten, die für die Weitergabe dieser Anforderungen für die teamübergreifende Zusammenarbeit verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="2c193-119">The diagrams provide information on required components that can be used to communicate these requirements for cross-team collaboration.</span></span>

<span data-ttu-id="2c193-120">Die bereitgestellten Diagramme sind absichtlich generisch, ermöglichen jedoch die Sammlung aller relevanten Daten, die für die Kommunikation von Anforderungen in einem teamübergreifenden Szenario erforderlich wären, in dem Netzwerk, Firewall, Zertifikaterstellung und-Verwaltung, Server die Bereitstellung und die Serververwaltung werden von verschiedenen Gruppen verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="2c193-120">The provided diagrams are intentionally generic, but allow for the collection of all pertinent data that would be necessary for communication of requirements in a cross team scenario where networking, firewall, certificate creation and management, server deployment, and server management are handled by different groups.</span></span> <span data-ttu-id="2c193-121">Die erforderlichen Details für die Konfiguration von Netzwerken, Firewalls, Ports und Protokollen, Zertifikaten und Servern sind von unschätzbarem Wert, wenn die Bereitstellung von lync Server fortgeschritten ist.</span><span class="sxs-lookup"><span data-stu-id="2c193-121">Having the required details for configuration of networking, firewalls, ports and protocols, certificates, and servers is invaluable when the deployment of Lync Server is underway.</span></span>

<span data-ttu-id="2c193-122">**Edgeserver und Edgepool**</span><span class="sxs-lookup"><span data-stu-id="2c193-122">**Edge Server and Edge pool**</span></span>

<span data-ttu-id="2c193-123">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span><span class="sxs-lookup"><span data-stu-id="2c193-123">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span></span>

<span data-ttu-id="2c193-124">**Reverseproxy**</span><span class="sxs-lookup"><span data-stu-id="2c193-124">**Reverse Proxy**</span></span>

<span data-ttu-id="2c193-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span><span class="sxs-lookup"><span data-stu-id="2c193-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span></span>

<span data-ttu-id="2c193-126">**Director oder Director-Pool**</span><span class="sxs-lookup"><span data-stu-id="2c193-126">**Director or Director pool**</span></span>

<span data-ttu-id="2c193-127">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span><span class="sxs-lookup"><span data-stu-id="2c193-127">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

