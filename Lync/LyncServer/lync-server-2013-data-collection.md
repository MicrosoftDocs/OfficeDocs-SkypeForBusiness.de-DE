---
title: 'Lync Server 2013: Datenerfassung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df4f19df012dfeac7576cc5b39d749564a4350a1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="data-collection-in-lync-server-2013"></a><span data-ttu-id="6b534-102">Datenerfassung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b534-102">Data collection in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b534-103">_**Letztes Änderungsdatum des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="6b534-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="6b534-104">In der Microsoft lync Server 2013-Kommunikationssoftware können Sie Microsoft lync Server 2013, Planungs Tool ausführen, ohne Ihre vorhandenen und vorgeschlagenen IP-Adressen und vollqualifizierten Domänennamen (FQDNs) für Edgeserver zu dokumentieren, doch ist dies wesentlich schwieriger ohne Konfigurationsfehler zu verursachen.</span><span class="sxs-lookup"><span data-stu-id="6b534-104">In Microsoft Lync Server 2013 communications software, you can run the Microsoft Lync Server 2013, Planning Tool without documenting your existing and proposed IP addresses and Edge Server fully qualified domain names (FQDNs), but it is significantly harder to do so without causing configuration errors.</span></span> <span data-ttu-id="6b534-105">Wenn beispielsweise die Koexistenz für eine bestimmte Zeitdauer erforderlich ist, besteht ein häufiger Fehler darin, FQDNs aus einer vorhandenen Edge-Bereitstellung für Ihre lync Server 2013-Edge-Bereitstellung wieder zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6b534-105">For example, if coexistence is required for a period of time, a common mistake is to reuse FQDNs from an existing Edge deployment for your Lync Server 2013 Edge deployment.</span></span> <span data-ttu-id="6b534-106">Indem Sie die vorhandenen und vorgeschlagenen IP-Adressen und FQDNs in einer Tabelle, einer Tabelle oder einer anderen visuellen Form aufgeschrieben haben, können Sie während der Installation Setup Probleme verhindern.</span><span class="sxs-lookup"><span data-stu-id="6b534-106">By having the existing and proposed IP addresses and FQDNs written down in a spreadsheet, table, or other visual form, you help prevent setup problems during installation.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="6b534-107">Wenn Sie frühere Versionen des Planungstools verwendet haben, haben Sie möglicherweise das Tool zum Erstellen Ihrer Topologie und des exportierten Topologie-Dokuments für die Verwendung in Topology Builder verwendet, um Ihre Topologie zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="6b534-107">If you have used previous versions of the Planning Tool, you may have used the tool to create your topology and the exported the topology document for use in Topology Builder to publish your topology.</span></span> <span data-ttu-id="6b534-108">Die Möglichkeit, die Topologie zu exportieren, wurde aus dem Planungs Tool entfernt.</span><span class="sxs-lookup"><span data-stu-id="6b534-108">The ability to export the topology was removed from Planning Tool.</span></span> <span data-ttu-id="6b534-109">Mit einer früheren Version des Planungstools zum Erstellen eines Topologie-Dokuments für lync Server 2013 wird dringend abgeraten, und es entstehen unerwartete Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="6b534-109">Using a previous version of the Planning Tool to create a topology document for Lync Server 2013 is strongly discouraged, and will produce unexpected results.</span></span>



</div>

<span data-ttu-id="6b534-110">Daher empfiehlt es sich, die folgende Daten Sammlungs Vorlage, die ihrer Edge-Topologie entspricht, zu verwenden, um die verschiedenen FQDN-und IP-Adressen zu sammeln, die Sie in das Planungs Tool eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="6b534-110">Therefore, the recommended approach is to use the following data collection template, which corresponds to your Edge topology, to gather the various FQDN and IP addresses that you will need to enter into the Planning Tool.</span></span> <span data-ttu-id="6b534-111">Indem Sie die aktuelle und vorgeschlagene Konfiguration dokumentieren, können Sie die Werte in den richtigen Kontext für Ihre Produktionsumgebung setzen.</span><span class="sxs-lookup"><span data-stu-id="6b534-111">By documenting the current and proposed configuration, you can put the values in the proper context for your production environment.</span></span> <span data-ttu-id="6b534-112">Und Sie müssen darüber nachdenken, wie Sie die Koexistenz und Features wie einfache URLs, Dateifreigaben und Lastenausgleich konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6b534-112">And, you are forced to think about how you will configure coexistence and features such as simple URLs, file shares, and load balancing.</span></span>

<span data-ttu-id="6b534-113">Damit Sie Microsoft lync Server 2013 erfolgreich bereitstellen können, müssen Sie sich mit der Interaktion und dem Vertrauen auf die einzelnen Komponenten vertraut machen.</span><span class="sxs-lookup"><span data-stu-id="6b534-113">To successfully deploy Microsoft Lync Server 2013, you need to understand the interaction of and reliance on the individual components.</span></span> <span data-ttu-id="6b534-114">Wenn Sie Daten aus Ihrer vorhandenen Netzwerk-und Serverinfrastruktur sammeln und die Planungsanleitungen in diesen Abschnitten anwenden, können Sie die Komponenten von lync Server 2013-Edgeserver in Ihre Infrastruktur integrieren.</span><span class="sxs-lookup"><span data-stu-id="6b534-114">By collecting data from your existing network and server infrastructure, and applying the planning guidance in these sections, you can integrate Lync Server 2013 Edge Server components into your infrastructure.</span></span>

<span data-ttu-id="6b534-115">Bei der [Auswahl einer Topologie in lync Server 2013](lync-server-2013-choosing-a-topology.md)wurden drei Hauptarchitekturen mit zwei Variationen für insgesamt fünf mögliche Bereitstellungsszenarien vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="6b534-115">Introduced in [Choosing a topology in Lync Server 2013](lync-server-2013-choosing-a-topology.md), there are three main architectures with two variations, for a total of five possible deployment scenarios.</span></span> <span data-ttu-id="6b534-116">Eines dieser Szenarien ist der Ausgangspunkt für Ihre Datensammlung.</span><span class="sxs-lookup"><span data-stu-id="6b534-116">One of these scenarios will be the starting point for your data collection.</span></span> <span data-ttu-id="6b534-117">Die IP-Adressen, Servernamen und Domänennamen sind Beispiele, die mit den entsprechenden Zertifikat-, Firewall-und DNS-Diagrammen übereinstimmen, die die für eine vollständige Planungslösung erforderlichen Informationen detailliert beschreiben.</span><span class="sxs-lookup"><span data-stu-id="6b534-117">The IP addresses, server names, and domain names are examples that coincide with the matching certificate, firewall, and DNS diagrams that detail the information required for a complete planning solution.</span></span> <span data-ttu-id="6b534-118">Die Diagramme und das Ausfüllen ihrer erforderlichen Zertifikat-, DNS-und firewallwerte sind besonders wichtig in teamübergreifenden Kommunikationen, bei denen die Verwaltung der Zertifizierungsstelle, die Firewall-Konfiguration und DNS von anderen Teams als dem Team verwaltet werden, das plant die Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="6b534-118">The diagrams and filling in your required certificate, DNS and firewall values is especially important in cross-team communications where the management of the certification authority, firewall configuration and DNS is managed by teams other than the team that plans the deployment.</span></span> <span data-ttu-id="6b534-119">Die Diagramme enthalten Informationen zu erforderlichen Komponenten, die verwendet werden können, um diese Anforderungen für die teamübergreifende Zusammenarbeit zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="6b534-119">The diagrams provide information on required components that can be used to communicate these requirements for cross-team collaboration.</span></span>

<span data-ttu-id="6b534-120">Die bereitgestellten Diagramme sind absichtlich generisch, ermöglichen jedoch die Sammlung aller relevanten Daten, die für die Kommunikation der Anforderungen in einem teamübergreifenden Szenario erforderlich sind, in dem Netzwerk, Firewall, Zertifikatserstellung und-Verwaltung, Server Bereitstellung und Serververwaltung werden von verschiedenen Gruppen gehandhabt.</span><span class="sxs-lookup"><span data-stu-id="6b534-120">The provided diagrams are intentionally generic, but allow for the collection of all pertinent data that would be necessary for communication of requirements in a cross team scenario where networking, firewall, certificate creation and management, server deployment, and server management are handled by different groups.</span></span> <span data-ttu-id="6b534-121">Die erforderlichen Details für die Konfiguration von Netzwerk, Firewalls, Ports und Protokollen, Zertifikaten und Servern sind von unschätzbarem Wert, wenn die Bereitstellung von lync Server im Gange ist.</span><span class="sxs-lookup"><span data-stu-id="6b534-121">Having the required details for configuration of networking, firewalls, ports and protocols, certificates, and servers is invaluable when the deployment of Lync Server is underway.</span></span>

<span data-ttu-id="6b534-122">**Edge-Server und Edge-Pool**</span><span class="sxs-lookup"><span data-stu-id="6b534-122">**Edge Server and Edge pool**</span></span>

<span data-ttu-id="6b534-123">![7624717a-ce99-4ae8-A929-2c4d74a2e47d] (images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-A929-2c4d74a2e47d")</span><span class="sxs-lookup"><span data-stu-id="6b534-123">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span></span>

<span data-ttu-id="6b534-124">**Reverseproxy**</span><span class="sxs-lookup"><span data-stu-id="6b534-124">**Reverse Proxy**</span></span>

<span data-ttu-id="6b534-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb] (images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span><span class="sxs-lookup"><span data-stu-id="6b534-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span></span>

<span data-ttu-id="6b534-126">**Director-oder Director-Pool**</span><span class="sxs-lookup"><span data-stu-id="6b534-126">**Director or Director pool**</span></span>

<span data-ttu-id="6b534-127">![56ba29ff-1309-4d5d-bf5c-35372169e947] (images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span><span class="sxs-lookup"><span data-stu-id="6b534-127">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

