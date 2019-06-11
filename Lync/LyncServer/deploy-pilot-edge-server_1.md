---
title: Bereitstellen eines Pilot-Edgeservers
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9cfe98069d3c90f4e021b34f6a7d31c583e7565
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="a37f3-102">Bereitstellen eines Pilot-Edgeservers</span><span class="sxs-lookup"><span data-stu-id="a37f3-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a37f3-103">_**Letztes Änderungsdatum des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="a37f3-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="a37f3-104">In diesem Thema werden die Konfigurationseinstellungen hervorgehoben, die Sie vor der Bereitstellung Ihres lync Server 2013-Edgeserver beachten sollten.</span><span class="sxs-lookup"><span data-stu-id="a37f3-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="a37f3-105">In diesem Abschnitt werden nur wichtige Punkte hervorgehoben, die Sie als Teil der Bereitstellung des Pilot Edge-Pools berücksichtigen sollten.</span><span class="sxs-lookup"><span data-stu-id="a37f3-105">This section only highlights key points you should consider as part of your pilot Edge pool deployment.</span></span> <span data-ttu-id="a37f3-106">Detaillierte Anweisungen finden Sie unter [Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation, in der der Bereitstellungsprozess beschrieben wird, sowie Konfigurationsinformationen für den Zugriff durch externe Benutzer.</span><span class="sxs-lookup"><span data-stu-id="a37f3-106">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="a37f3-107">Wenn Sie im Assistenten zum **Definieren eines neuen Edge-Pools** navigieren, überprüfen Sie die wichtigsten Konfigurationseinstellungen, die in den folgenden Schritten gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a37f3-107">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="a37f3-108">Beachten Sie, dass nur wenige Seiten des Assistenten zum **Definieren eines neuen Edge-Pools** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a37f3-108">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="a37f3-109">**Definieren eines Edge-Pools**</span><span class="sxs-lookup"><span data-stu-id="a37f3-109">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="a37f3-110">Öffnen Sie die Topologie des pilotpools mithilfe des Topologie-Generators.</span><span class="sxs-lookup"><span data-stu-id="a37f3-110">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="a37f3-111">Navigieren Sie zum lync Server 2013-Knoten.</span><span class="sxs-lookup"><span data-stu-id="a37f3-111">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="a37f3-112">Klicken Sie mit der rechten Maustaste auf **Edge-Pools**, und klicken Sie auf **neuer Edge-Pool**.</span><span class="sxs-lookup"><span data-stu-id="a37f3-112">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="a37f3-113">![Dialogfeld ' neuen Edge-Pool definieren] ' (images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Dialogfeld ' neuen Edge-Pool definieren") '</span><span class="sxs-lookup"><span data-stu-id="a37f3-113">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="a37f3-114">Ein Edge-Pool kann ein Pool mit **mehreren Computern** oder ein **einzelner Computerpool**sein.</span><span class="sxs-lookup"><span data-stu-id="a37f3-114">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="a37f3-115">![Definieren des Dialogfelds "FQDN des Edge-Pools"] (images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Definieren des Dialogfelds \"FQDN des Edge-Pools\"")</span><span class="sxs-lookup"><span data-stu-id="a37f3-115">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="a37f3-116">Aktivieren Sie auf der Seite **"Features auswählen** " die Föderation oder den XMPP-Verbund nicht.</span><span class="sxs-lookup"><span data-stu-id="a37f3-116">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="a37f3-117">Föderations-und XMPP-Föderation werden derzeit über den Legacy Office Communications Server 2007 R2 Edge-Server weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="a37f3-117">Federation and XMPP federation are currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="a37f3-118">Diese Features werden in einer späteren Migrationsphase konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="a37f3-118">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="a37f3-119">![Dialogfeld ' Features auswählen] ' (images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Dialogfeld ' Features auswählen") '</span><span class="sxs-lookup"><span data-stu-id="a37f3-119">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="a37f3-120">Führen Sie als nächstes die folgenden Assistentenseiten **aus: Wählen Sie IP-Optionen**, **externe FQDNs**aus, **definieren Sie die interne IP-Adresse**, und definieren Sie **die externe IP-Adresse**.</span><span class="sxs-lookup"><span data-stu-id="a37f3-120">Next, continue completing the following wizard pages: **Select IP options**, **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="a37f3-121">Wählen Sie auf der Seite **Nächster Hop definieren** den Director für den nächsten Hop des lync Server 2013-Edge-Pools aus.</span><span class="sxs-lookup"><span data-stu-id="a37f3-121">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2013 Edge pool.</span></span>
    
    <span data-ttu-id="a37f3-122">![Dialogfeld "neuen Edge-Pool definieren", Liste des nächsten Hop-Pools] (images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Dialogfeld \"neuen Edge-Pool definieren\", Liste des nächsten Hop-Pools")</span><span class="sxs-lookup"><span data-stu-id="a37f3-122">![Define New Edge Pool dialog, Next hop pool list](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Define New Edge Pool dialog, Next hop pool list")</span></span>

7.  <span data-ttu-id="a37f3-123">Verbinden Sie auf der Seite **Front-End-Pools zuordnen** keinen Pool mit diesem Edge-Pool zu diesem Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="a37f3-123">On the **Associate Front End pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="a37f3-124">Der externe Mediendatenverkehr wird derzeit über den Legacy Office Communications Server 2007 R2-Edgeserver weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="a37f3-124">External media traffic is currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="a37f3-125">Diese Einstellung wird in einer späteren Migrationsphase konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="a37f3-125">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="a37f3-126">![Dialogfeld "neuen Edge-Pool definieren"] (images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Dialogfeld \"neuen Edge-Pool definieren\"")</span><span class="sxs-lookup"><span data-stu-id="a37f3-126">![Define New Edge Pool dialog](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Define New Edge Pool dialog")</span></span>

8.  <span data-ttu-id="a37f3-127">Klicken Sie auf **Fertig stellen** , und **veröffentlichen** Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="a37f3-127">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="a37f3-128">Führen Sie die Schritte unter [Installieren von Edge-Servern für lync Server 2013](lync-server-2013-install-edge-servers.md) in der Bereitstellungsdokumentation aus, um die Dateien auf dem neuen Edgeserver zu installieren, Zertifikate zu konfigurieren und die Dienste zu starten.</span><span class="sxs-lookup"><span data-stu-id="a37f3-128">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="a37f3-129">Es ist sehr wichtig, dass Sie die Richtlinien in den Themen zum [Bereitstellen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation befolgen.</span><span class="sxs-lookup"><span data-stu-id="a37f3-129">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="a37f3-130">Dieser Abschnitt enthält lediglich einige Anleitungen zu Konfigurationseinstellungen beim Installieren dieser Serverrollen.</span><span class="sxs-lookup"><span data-stu-id="a37f3-130">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="a37f3-131">Sie sollten nun über eine Legacy Office Communications Server 2007 R2 Edge Server-Bereitstellung verfügen, die durch das vorhanden sein des BackCompatSite parallel zu einer lync Server 2013-Edgeserver-Bereitstellung angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a37f3-131">You should now have a legacy Office Communications Server 2007 R2 Edge server deployment, indicated by the presence of the BackCompatSite, in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="a37f3-132">Der Verbund ist für die Verwendung des Office Communications Server 2007 R2-Directors konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="a37f3-132">Federation is configured to use the Office Communications Server 2007 R2 Director.</span></span> <span data-ttu-id="a37f3-133">Überprüfen Sie, ob beide Bereitstellungen ordnungsgemäß ausgeführt werden, Dienste gestartet sind, und Sie können jede Bereitstellung verwalten, bevor Sie in die nächste Phase wechseln.</span><span class="sxs-lookup"><span data-stu-id="a37f3-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

<span data-ttu-id="a37f3-134">![Topologie-Generator mit OCS] -Edgeserver (images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Topologie-Generator mit OCS") -Edgeserver</span><span class="sxs-lookup"><span data-stu-id="a37f3-134">![Topology Builder showing OCS Edge Server](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Topology Builder showing OCS Edge Server")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

