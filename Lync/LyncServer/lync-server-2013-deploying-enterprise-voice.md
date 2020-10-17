---
title: 'Lync Server 2013: Bereitstellen von Enterprise-VoIP'
description: 'Lync Server 2013: Deploying Enterprise Voice.'
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
ms.openlocfilehash: 5cc1c891d81db158c1d28e4a3e918a9dae37744c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557811"
---
# <a name="deploying-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="2f057-103">Bereitstellen von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f057-103">Deploying Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f057-104">_**Letztes Änderungsstand des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="2f057-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="2f057-105">Lync Server 2013 ist Enterprise-VoIP Teil der lync Server 2013-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="2f057-105">Lync Server 2013, Enterprise Voice is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="2f057-106">Zum Bereitstellen der Enterprise-VoIP müssen Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="2f057-106">Deploying Enterprise Voice requires that you:</span></span>

<div id="sectionSection0" class="section">

1.  <span data-ttu-id="2f057-107">Lesen Sie den Abschnitt [Planung für Enterprise-VoIP in lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2f057-107">Review the [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) section of the Planning documentation.</span></span>

2.  <span data-ttu-id="2f057-108">Die Planung von Features und Komponenten abschließen, um diese Arbeitslast bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2f057-108">Finalize plans for features and components to deploy with this workload.</span></span>

3.  <span data-ttu-id="2f057-109">Führen Sie das Planungs Tool aus, um eine Topologie zu entwerfen, die ihre Bereitstellungsentscheidungen widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="2f057-109">Run Planning Tool to design a topology that reflects your deployment decisions.</span></span>

4.  <span data-ttu-id="2f057-110">Öffnen Sie den Topologie-Entwurf im Topologie-Generator, wie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in der Bereitstellungsdokumentation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2f057-110">Open the topology design in Topology Builder, as described in [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2f057-111">Die Installation des Topologie-Generators ist Teil des Bereitstellungsprozesses für den internen Pool.</span><span class="sxs-lookup"><span data-stu-id="2f057-111">Installation of Topology Builder is part of the deployment process for the internal pool.</span></span> <span data-ttu-id="2f057-112">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-install-lync-server-administrative-tools.md">install lync Server 2013 Administration Tools</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2f057-112">For details, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="2f057-113">Darüber hinaus müssen Sie bereits lync Server Enterprise Edition an zentralen Standorten und Zweigstellenstandorten bereitgestellt haben, die der Referenztopologie entsprechen, die Sie bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="2f057-113">Additionally, you must have already deployed Lync Server, Enterprise Edition at central sites and branch sites that correspond to the reference topology that you choose to deploy.</span></span> <span data-ttu-id="2f057-114">Sie können Enterprise-VoIP-Komponenten erst bereitstellen, nachdem Sie Dateien für mindestens einen internen Pool definiert, veröffentlicht und installiert haben, und Sie müssen den Topologie-Generator verwenden, um einen internen Pool zu definieren und zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="2f057-114">You can’t deploy Enterprise Voice components until you have defined, published, and installed files for at least one internal pool, and you must use Topology Builder to define and publish an internal pool.</span></span>

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

<span data-ttu-id="2f057-115">Informationen zum Anzeigen von Referenz Topologien mit Beispielen dafür, wo Enterprise-VoIP-Serverrollen bereitgestellt werden können (und ihre Beziehung zu einem anderen und anderen lync Server 2013-Serverrollen), finden Sie unter [Referenz Topologien in lync Server 2013](lync-server-2013-reference-topologies.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2f057-115">To view reference topologies with examples of where Enterprise Voice server roles can be deployed (and their relationship to one another and other Lync Server 2013 server roles), see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span>

<span data-ttu-id="2f057-116">Informationen zum Anzeigen einer Referenztopologie, die eine Beispielbereitstellung für die Anrufsteuerung, einschließlich netzwerkregionen, Netzwerkstandorten und Subnetzen, veranschaulicht und erläutert, finden Sie unter [example: Gathering your Requirements for Call Admission Control in lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2f057-116">To view a reference topology that illustrates and explains a sample call admission control deployment, including network regions, network sites, and subnets, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2f057-117">Lesen Sie die Themen in diesem Abschnitt weiter, um Enterprise-VoIP an einem zentralen Standort bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2f057-117">To deploy Enterprise Voice at a central site, continue reading the topics in this section.</span></span> <span data-ttu-id="2f057-118">Um Enterprise-VoIP an einem Zweigstellenstandort bereitzustellen, fahren Sie mit dem <A href="lync-server-2013-deploying-branch-sites.md">Bereitstellen von Zweigstellenstandorten in lync Server 2013</A> in der Bereitstellungsdokumentation fort.</span><span class="sxs-lookup"><span data-stu-id="2f057-118">To deploy Enterprise Voice at a branch site, skip to <A href="lync-server-2013-deploying-branch-sites.md">Deploying branch sites in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="2f057-119">Dieser Abschnitt enthält Verfahren für Bereitstellungen, in denen ein Vermittlungsserver wie empfohlen auf jedem Front-End-Server oder Standard Edition-Server gemeinsam ausgeführt wird, und auch für Bereitstellungen mit einem eigenständigen Vermittlungsserverpool.</span><span class="sxs-lookup"><span data-stu-id="2f057-119">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="2f057-120">Sie können den folgenden Inhalt überspringen, wenn Sie den Topologie-Generator verwendet haben, um eine Topologie zu definieren und zu veröffentlichen, die eine Vermittlungsserver auf jedem Front-End-Server oder Standard Edition-Server Kollokatoren, da der Bereitstellungs-Assistent die Dateien für Vermittlungsserver bereits automatisch installiert hat, als Sie Dateien für den Front-End-Server Pool oder Standard Edition-Server installiert haben:</span><span class="sxs-lookup"><span data-stu-id="2f057-120">You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>

  - [<span data-ttu-id="2f057-121">Konfigurieren von Trunks in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f057-121">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

<span data-ttu-id="2f057-122">Wenn Sie den Topologie-Generator zum Definieren und Veröffentlichen eines Vermittlungsserver in einem eigenständigen Pool verwendet haben, können Sie den folgenden Inhalt verwenden:</span><span class="sxs-lookup"><span data-stu-id="2f057-122">If you used Topology Builder to define and publish a Mediation Server in a stand-alone pool, you can use the following content:</span></span>

  - <span data-ttu-id="2f057-123">Stellen Sie sicher, dass Ihre Topologie die erforderlichen Software-und Umgebungsvoraussetzungen erfüllt, wie unter [Enterprise-VoIP-Voraussetzungen für lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2f057-123">Verify that your topology meets the software and environment prerequisites, as described in [Enterprise Voice prerequisites for Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2f057-124">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2f057-124">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="2f057-125">Voraussetzungen für Enterprise-VoIP für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f057-125">Enterprise Voice prerequisites for Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [<span data-ttu-id="2f057-126">Bereitstellen von Vermittlungsservern und Definieren von Peers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f057-126">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [<span data-ttu-id="2f057-127">Konfigurieren von Trunks in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f057-127">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [<span data-ttu-id="2f057-128">Konfigurieren von Wählplänen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f057-128">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [<span data-ttu-id="2f057-129">Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f057-129">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [<span data-ttu-id="2f057-130">Exportieren und Importieren der VoIP-Routingkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f057-130">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="2f057-131">Testen des VoIP-Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f057-131">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [<span data-ttu-id="2f057-132">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f057-132">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="2f057-133">Bereitstellen von lokaler Exchange um zur Bereitstellung von lync Server 2013-Voicemail</span><span class="sxs-lookup"><span data-stu-id="2f057-133">Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail</span></span>](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [<span data-ttu-id="2f057-134">Bereitstellen von Voicemail für lync Server 2013-Benutzer in gehosteten Exchange um</span><span class="sxs-lookup"><span data-stu-id="2f057-134">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [<span data-ttu-id="2f057-135">Konfigurieren der lokalen lync Server 2013 Integration in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2f057-135">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [<span data-ttu-id="2f057-136">Bereitstellen von erweiterten Enterprise-VoIP-Funktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f057-136">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [<span data-ttu-id="2f057-137">Informationen zu netzwerkregionen, Standorten und Subnetzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f057-137">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [<span data-ttu-id="2f057-138">Erstellen oder Ändern einer netzwerkregion in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f057-138">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [<span data-ttu-id="2f057-139">Erstellen oder Ändern eines Netzwerkstandorts in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f057-139">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [<span data-ttu-id="2f057-140">Zuordnen eines Subnetzes zu einem Netzwerkstandort in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f057-140">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [<span data-ttu-id="2f057-141">Konfigurieren der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f057-141">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)
    
      - [<span data-ttu-id="2f057-142">Konfigurieren von Enhanced 9-1-1 in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f057-142">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [<span data-ttu-id="2f057-143">Konfigurieren der medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f057-143">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [<span data-ttu-id="2f057-144">Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f057-144">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2f057-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f057-145">See Also</span></span>


[<span data-ttu-id="2f057-146">Bereitstellen von Zweigstellenstandorten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f057-146">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)  
[<span data-ttu-id="2f057-147">Konfigurieren von Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f057-147">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)  
[<span data-ttu-id="2f057-148">Konfigurieren des Parkens von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f057-148">Configuring Call Park in Lync Server 2013</span></span>](lync-server-2013-configuring-call-park.md)  
[<span data-ttu-id="2f057-149">Konfigurieren von Ankündigungen für nicht zugewiesene Nummern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f057-149">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[<span data-ttu-id="2f057-150">Bereitstellen der Überwachung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f057-150">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

