---
title: 'Lync Server 2013: Bereitstellen von Enterprise-VoIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf57d55899d556ddfde633c975ae9f0516e48e14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="91af7-102">Bereitstellen von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91af7-102">Deploying Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91af7-103">_**Letztes Änderungsdatum des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="91af7-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="91af7-104">Lync Server 2013, Enterprise-VoIP ist Teil der lync Server 2013-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="91af7-104">Lync Server 2013, Enterprise Voice is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="91af7-105">Zur Bereitstellung von Enterprise-VoIP müssen Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="91af7-105">Deploying Enterprise Voice requires that you:</span></span>

<div id="sectionSection0" class="section">

1.  <span data-ttu-id="91af7-106">Lesen Sie den Abschnitt [Planning for Enterprise Voice in lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="91af7-106">Review the [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) section of the Planning documentation.</span></span>

2.  <span data-ttu-id="91af7-107">Abschließen von Plänen für Features und Komponenten, die mit dieser Arbeitsauslastung bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="91af7-107">Finalize plans for features and components to deploy with this workload.</span></span>

3.  <span data-ttu-id="91af7-108">Führen Sie das Planungs Tool aus, um eine Topologie zu entwerfen, die ihre Bereitstellungsentscheidungen widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="91af7-108">Run Planning Tool to design a topology that reflects your deployment decisions.</span></span>

4.  <span data-ttu-id="91af7-109">Öffnen Sie den Topologie-Entwurf im Topologie-Generator, wie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in der Bereitstellungsdokumentation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="91af7-109">Open the topology design in Topology Builder, as described in [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="91af7-110">Die Installation des Topologie-Generators ist Teil des Bereitstellungsprozesses für den internen Pool.</span><span class="sxs-lookup"><span data-stu-id="91af7-110">Installation of Topology Builder is part of the deployment process for the internal pool.</span></span> <span data-ttu-id="91af7-111">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-install-lync-server-administrative-tools.md">Installieren von lync Server 2013-Verwaltungstools</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="91af7-111">For details, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="91af7-112">Darüber hinaus müssen Sie lync Server, Enterprise Edition, auf zentralen Websites und Zweigstellen bereitgestellt haben, die der von Ihnen bereitzustellenden Referenztopologie entsprechen.</span><span class="sxs-lookup"><span data-stu-id="91af7-112">Additionally, you must have already deployed Lync Server, Enterprise Edition at central sites and branch sites that correspond to the reference topology that you choose to deploy.</span></span> <span data-ttu-id="91af7-113">Sie können Enterprise-VoIP-Komponenten erst bereitstellen, nachdem Sie Dateien für mindestens einen internen Pool definiert, veröffentlicht und installiert haben, und Sie müssen den Topologie-Generator verwenden, um einen internen Pool zu definieren und zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="91af7-113">You can’t deploy Enterprise Voice components until you have defined, published, and installed files for at least one internal pool, and you must use Topology Builder to define and publish an internal pool.</span></span>

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

<span data-ttu-id="91af7-114">Informationen zum Anzeigen von Referenz Topologien mit Beispielen für die Bereitstellung von Enterprise-VoIP-Serverrollen (und deren Beziehung zu einem anderen und anderen lync Server 2013-Serverrollen) finden Sie unter [Referenz Topologien in lync Server 2013](lync-server-2013-reference-topologies.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="91af7-114">To view reference topologies with examples of where Enterprise Voice server roles can be deployed (and their relationship to one another and other Lync Server 2013 server roles), see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span>

<span data-ttu-id="91af7-115">Informationen zum Anzeigen einer Referenztopologie, die eine Beispielbereitstellung für die Anrufsteuerung, einschließlich netzwerkregionen, Netzwerk Websites und Subnetzen, veranschaulicht und erläutert, finden Sie unter [Beispiel: Sammeln Ihrer Anforderungen für die Anrufsteuerung in lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="91af7-115">To view a reference topology that illustrates and explains a sample call admission control deployment, including network regions, network sites, and subnets, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> <span data-ttu-id="91af7-116">Wenn Sie Enterprise-VoIP an einem zentralen Standort bereitstellen möchten, lesen Sie die Themen in diesem Abschnitt weiter.</span><span class="sxs-lookup"><span data-stu-id="91af7-116">To deploy Enterprise Voice at a central site, continue reading the topics in this section.</span></span> <span data-ttu-id="91af7-117">Wenn Sie Enterprise-VoIP an einer Zweigstelle bereitstellen möchten, wechseln Sie zum bereit <A href="lync-server-2013-deploying-branch-sites.md">Stellen von Zweigstellen in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="91af7-117">To deploy Enterprise Voice at a branch site, skip to <A href="lync-server-2013-deploying-branch-sites.md">Deploying branch sites in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="91af7-118">Dieser Abschnitt enthält Verfahren für Bereitstellungen, in denen ein Vermittlungsserver wie empfohlen auf jedem Front-End-Server oder Standard Edition-Server gemeinsam ausgeführt wird und auch für Bereitstellungen mit einem eigenständigen Vermittlungsserverpool.</span><span class="sxs-lookup"><span data-stu-id="91af7-118">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="91af7-119">Sie können den folgenden Inhalt überspringen, wenn Sie mithilfe des Topologie-Generators eine Topologie definiert und veröffentlicht haben, die einen Vermittlungsserver auf jedem Front-End-Server oder Standard Edition-Server Kollokatoren, weil die Dateien von dem Bereitstellungs-Assistenten bereits automatisch installiert wurden Vermittlungsserver, wenn Sie Dateien für Ihren Front-End-Serverpool oder Standard Edition-Server installiert haben:</span><span class="sxs-lookup"><span data-stu-id="91af7-119">You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>

  - [<span data-ttu-id="91af7-120">Konfigurieren von Trunks in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91af7-120">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

<span data-ttu-id="91af7-121">Wenn Sie den Topologie-Generator zum Definieren und Veröffentlichen eines Vermittlungsservers in einem eigenständigen Pool verwendet haben, können Sie den folgenden Inhalt verwenden:</span><span class="sxs-lookup"><span data-stu-id="91af7-121">If you used Topology Builder to define and publish a Mediation Server in a stand-alone pool, you can use the following content:</span></span>

  - <span data-ttu-id="91af7-122">Überprüfen Sie, ob Ihre Topologie die erforderlichen Software-und Umgebungsvoraussetzungen erfüllt, wie in [Enterprise-VoIP-Voraussetzungen für lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="91af7-122">Verify that your topology meets the software and environment prerequisites, as described in [Enterprise Voice prerequisites for Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="91af7-123">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="91af7-123">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="91af7-124">Voraussetzungen für Enterprise-VoIP für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91af7-124">Enterprise Voice prerequisites for Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [<span data-ttu-id="91af7-125">Bereitstellen von Vermittlungsservern und Definieren von Peers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91af7-125">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [<span data-ttu-id="91af7-126">Konfigurieren von Trunks in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91af7-126">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [<span data-ttu-id="91af7-127">Konfigurieren von Wählplänen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91af7-127">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [<span data-ttu-id="91af7-128">Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91af7-128">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [<span data-ttu-id="91af7-129">Exportieren und Importieren einer VoIP-Routingkonfiguration in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91af7-129">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="91af7-130">Testen des VoIP-Routings in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91af7-130">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [<span data-ttu-id="91af7-131">Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91af7-131">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="91af7-132">Bereitstellen lokaler Exchange Unified Messaging-Dienste zur Unterstützung von Lync Server 2013-Voicemail</span><span class="sxs-lookup"><span data-stu-id="91af7-132">Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail</span></span>](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [<span data-ttu-id="91af7-133">Bereitstellen von Voicemail für Benutzer von Lync Server 2013 für gehostete Exchange Unified Messaging-Dienste</span><span class="sxs-lookup"><span data-stu-id="91af7-133">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [<span data-ttu-id="91af7-134">Konfigurieren der lokalen lync Server 2013-Integration in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="91af7-134">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [<span data-ttu-id="91af7-135">Bereitstellen von erweiterten Enterprise-VoIP-Features in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91af7-135">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [<span data-ttu-id="91af7-136">Informationen zu Netzwerkregionen, Standorten und Subnetzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91af7-136">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [<span data-ttu-id="91af7-137">Erstellen oder Ändern eines Netzwerkbereichs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91af7-137">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [<span data-ttu-id="91af7-138">Erstellen oder Ändern eines Netzwerkstandorts in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91af7-138">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [<span data-ttu-id="91af7-139">Zuordnen eines Subnetzes zu einem Netzwerkstandort in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91af7-139">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [<span data-ttu-id="91af7-140">Konfigurieren der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91af7-140">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)
    
      - [<span data-ttu-id="91af7-141">Konfigurieren von E9-1-1 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91af7-141">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [<span data-ttu-id="91af7-142">Konfigurieren der Medienumgehung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91af7-142">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [<span data-ttu-id="91af7-143">Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91af7-143">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="91af7-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91af7-144">See Also</span></span>


[<span data-ttu-id="91af7-145">Bereitstellen von Zweigstellen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91af7-145">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)  
[<span data-ttu-id="91af7-146">Konfigurieren von Einwahlkonferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91af7-146">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)  
[<span data-ttu-id="91af7-147">Konfigurieren des Parkens von Anrufen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91af7-147">Configuring Call Park in Lync Server 2013</span></span>](lync-server-2013-configuring-call-park.md)  
[<span data-ttu-id="91af7-148">Konfigurieren von Ansagen für nicht zugewiesene Nummern in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91af7-148">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[<span data-ttu-id="91af7-149">Bereitstellen der Überwachung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91af7-149">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

