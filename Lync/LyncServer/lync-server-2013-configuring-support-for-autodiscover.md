---
title: 'Lync Server 2013: Konfigurieren der Unterstützung für die AutoErmittlung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79511202ddc9e413e313d12f881e7079f088c473
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="85f68-102">Konfigurieren der Unterstützung für die AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85f68-102">Configuring support for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85f68-103">_**Letztes Änderungsstand des Themas:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="85f68-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="85f68-104">Der **AutoErmittlungsdienst** für lync Server-Webdienste erschien zunächst im lync Server 2010 kumulativen Update: November 2011.</span><span class="sxs-lookup"><span data-stu-id="85f68-104">The Lync Server web services **Autodiscover service** first appeared in the Lync Server 2010 Cumulative Update: November 2011.</span></span> <span data-ttu-id="85f68-105">Dieses Update wurde von der ersten Version von lync Mobile-Clients begleitet.</span><span class="sxs-lookup"><span data-stu-id="85f68-105">This update was accompanied by the initial release of Lync Mobile clients.</span></span> <span data-ttu-id="85f68-106">Der AutoErmittlungsdienst hat die Mobilitätsdienste verfügbar gemacht, die als MCX-Dienst bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="85f68-106">The autodiscover service exposed the mobility services, known as the Mcx service.</span></span>

<span data-ttu-id="85f68-107">Der AutoErmittlungsdienst fungiert als ein einzelner Standort für alle Clients, um Informationen darüber anzufordern, welche Dienste und Features verfügbar sind, und wie Sie mit den Vermittlern Kontakt aufnehmen können – entweder durch einen vollqualifizierten Domänennamen oder eine webuniform Resource Locator-Referenz.</span><span class="sxs-lookup"><span data-stu-id="85f68-107">The autodiscover service acts as a single location for all clients to request information on what services and features are available, and how to contact the sevices – either by a fully qualified domain name or a web uniform resource locator reference.</span></span> <span data-ttu-id="85f68-108">Die AutoErmittlung macht eine Reihe von Features verfügbar, und jeder Client stellt Anforderungen basierend auf den Features, die der Client verwenden kann, zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="85f68-108">Autodiscover exposes a number of features, and each client will make requests based on the features that the client can use.</span></span> <span data-ttu-id="85f68-109">Beispielsweise verwendet ein Desktop lync 2013-Client autodiscvoer, um die externen Webdienste zu ermitteln, verwendet jedoch nicht die Mobilitätsdienste (MCX).</span><span class="sxs-lookup"><span data-stu-id="85f68-109">For example, a desktop Lync 2013 client will use autodiscvoer to determine the external web services, but will not use the mobility (Mcx) services.</span></span> <span data-ttu-id="85f68-110">Um Ihre Clients ordnungsgemäß zu definieren und zu aktivieren, um die verfügbaren Features zu verwenden, sollten die Szenarien definiert werden, die es einem Client ermöglichen, Auto Ermittlungs Einträge effektiv zu finden und zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="85f68-110">To properly define and enable your clients to use the features available to them, the scenarios that allow a client to effectively find and use autodiscover entries should be defined.</span></span> <span data-ttu-id="85f68-111">Für die Verwendung von autodoscover erfordert die Bereitstellung, dass ein Reverseproxy die lync Server-Webdienste veröffentlicht, dass DNS-Einträge so konfiguriert sind, dass DNS-Abfragen für den lync Server AutoErmittlungsdienst und lync Server Webdienste aufgelöst werden und dass die Zertifikatdienste für Ihr spezifisches Szenario ordnungsgemäß konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="85f68-111">To use autodoscover, your deployment requires that a reverse proxy publishes the Lync Server web services, that DNS records are configured to resolve DNS queries for the Lync Server autodiscover service and Lync Server web services, and that certificate services are properly configured for your specific scenario.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="85f68-112">Technische Details zu den Elementen in der Anforderung/Antwort der AutoErmittlung finden Sie unter <A href="lync-server-2013-understanding-autodiscover.md">Understanding AutoErmittlung in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="85f68-112">For technical details on what the elements within the autodiscover request/response do, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="85f68-113">Die folgenden Informationen und Tabellen definieren pro Szenario, welche Konfigurationen (falls vorhanden) Sie implementieren müssen, um die vollständige und effektive Verwendung des AutoErmittlungsdiensts bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="85f68-113">The following information and tables define, per scenario, what configurations (if any) you need to implement to provide the full and effective use of the autodiscover service.</span></span> <span data-ttu-id="85f68-114">Die Informationen in den folgenden Themen sind spezifisch für Microsoft lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85f68-114">The information in the following topics is specific to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="85f68-115">Informationen zum Planen der Mobilität für lync Server 2010 finden Sie unter [http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113).</span><span class="sxs-lookup"><span data-stu-id="85f68-115">If you are looking for guidance on how to plan Mobility for Lync Server 2010, see [http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113).</span></span> <span data-ttu-id="85f68-116">Informationen zum Bereitstellen von Mobilität für lync Server 2010 finden Sie unter[http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)</span><span class="sxs-lookup"><span data-stu-id="85f68-116">To deploy Mobility for Lync Server 2010, see [http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="85f68-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="85f68-117">In This Section</span></span>

  - [<span data-ttu-id="85f68-118">Konfigurieren von DNS für die AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85f68-118">Configuring DNS for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [<span data-ttu-id="85f68-119">Konfigurieren von Zertifikaten für die AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85f68-119">Configuring certificates for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [<span data-ttu-id="85f68-120">Konfigurieren eines Reverse-Proxys für die AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85f68-120">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [<span data-ttu-id="85f68-121">Konfigurieren der AutoErmittlung in lync Server 2013 für hybridbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="85f68-121">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

