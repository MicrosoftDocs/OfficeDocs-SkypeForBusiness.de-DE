---
title: Bereitstellen eines Pilot-Edgeservers
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4245efe0faf5dfe947cc52fb22a447e46c0b3e8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="6d7be-102">Bereitstellen eines Pilot-Edgeservers</span><span class="sxs-lookup"><span data-stu-id="6d7be-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d7be-103">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="6d7be-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="6d7be-104">In diesem Thema werden Konfigurationseinstellungen hervorgehoben, die Sie vor der Bereitstellung Ihrer lync Server 2013 Edgeserver beachten sollten.</span><span class="sxs-lookup"><span data-stu-id="6d7be-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="6d7be-105">In diesem Abschnitt sind nur die wichtigsten zu beachtenden Punkte für die Bereitstellung Ihres Pilotedgepools hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="6d7be-105">This section only highlights key points you should consider as part of your pilot Edge pool deployment.</span></span> <span data-ttu-id="6d7be-106">Ausführliche Anweisungen finden Sie unter [Deploying External User Access in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation, in der der Bereitstellungsprozess beschrieben wird und der auch Konfigurationsinformationen für den Zugriff durch externe Benutzer enthält.</span><span class="sxs-lookup"><span data-stu-id="6d7be-106">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="6d7be-107">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span><span class="sxs-lookup"><span data-stu-id="6d7be-107">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="6d7be-108">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span><span class="sxs-lookup"><span data-stu-id="6d7be-108">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="6d7be-109">**Definieren eines Edgepools**</span><span class="sxs-lookup"><span data-stu-id="6d7be-109">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="6d7be-110">Öffnen Sie mithilfe des Topologie-Generators die Pilotpooltopologie.</span><span class="sxs-lookup"><span data-stu-id="6d7be-110">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="6d7be-111">Navigieren Sie zum Knoten lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6d7be-111">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="6d7be-112">Klicken Sie mit der rechten Maustaste auf **Edgepools**, und klicken Sie dann auf **Neuer Edgepool**.</span><span class="sxs-lookup"><span data-stu-id="6d7be-112">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="6d7be-113">![Definieren des Dialogfelds "neuer Edge-Pool"](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Definieren des Dialogfelds "neuer Edge-Pool"")</span><span class="sxs-lookup"><span data-stu-id="6d7be-113">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="6d7be-114">Ein Edgepool ist entweder ein **Pool mit mehreren Computern** oder ein **Pool mit einem Computer**.</span><span class="sxs-lookup"><span data-stu-id="6d7be-114">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="6d7be-115">![Definieren des Dialogfelds für den FQDN des Edge-Pools](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Definieren des Dialogfelds für den FQDN des Edge-Pools")</span><span class="sxs-lookup"><span data-stu-id="6d7be-115">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="6d7be-116">Aktivieren Sie auf der Seite **Funktionen auswählen** nicht den Verbund oder den XMPP-Partnerverbund.</span><span class="sxs-lookup"><span data-stu-id="6d7be-116">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="6d7be-117">Der Verbund und der XMPP-Verbund werden derzeit über die Legacy Office Communications Server 2007 R2 Edgeserver weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="6d7be-117">Federation and XMPP federation are currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="6d7be-118">Diese Funktionen werden in einer späteren Phase der Migration konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="6d7be-118">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="6d7be-119">![Dialogfeld ' Features auswählen '](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Dialogfeld ' Features auswählen '")</span><span class="sxs-lookup"><span data-stu-id="6d7be-119">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="6d7be-120">Bearbeiten Sie anschließend die folgenden Seiten des Assistenten: **IP-Optionen auswählen**, **Externe FQDNs**, **Interne IP-Adresse definieren** und **Externe IP-Adresse definieren**.</span><span class="sxs-lookup"><span data-stu-id="6d7be-120">Next, continue completing the following wizard pages: **Select IP options**, **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="6d7be-121">Wählen Sie auf der Seite **nächsten Hop definieren** den Director für den nächsten Hop des lync Server 2013 Edgepool aus.</span><span class="sxs-lookup"><span data-stu-id="6d7be-121">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2013 Edge pool.</span></span>
    
    <span data-ttu-id="6d7be-122">![Dialogfeld "neuen Edge-Pool definieren", Liste "Nächster Hop-Pool"](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Dialogfeld "neuen Edge-Pool definieren", Liste "Nächster Hop-Pool"")</span><span class="sxs-lookup"><span data-stu-id="6d7be-122">![Define New Edge Pool dialog, Next hop pool list](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Define New Edge Pool dialog, Next hop pool list")</span></span>

7.  <span data-ttu-id="6d7be-123">Ordnen Sie diesem Edgepool auf der Seite **Front-End-Pools zuordnen** keinen Pool zu diesem Zeitpunkt zu.</span><span class="sxs-lookup"><span data-stu-id="6d7be-123">On the **Associate Front End pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="6d7be-124">Der externe Mediendatenverkehr wird derzeit über die Legacy Office Communications Server 2007 R2 Edgeserver weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="6d7be-124">External media traffic is currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="6d7be-125">Diese Einstellung wird in einer späteren Phase der Migration konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="6d7be-125">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="6d7be-126">![Dialogfeld "neuen Edge-Pool definieren"](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Dialogfeld "neuen Edge-Pool definieren"")</span><span class="sxs-lookup"><span data-stu-id="6d7be-126">![Define New Edge Pool dialog](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Define New Edge Pool dialog")</span></span>

8.  <span data-ttu-id="6d7be-127">Klicken Sie auf **Fertig stellen**, und **veröffentlichen** Sie anschließend die Topologie.</span><span class="sxs-lookup"><span data-stu-id="6d7be-127">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="6d7be-128">Führen Sie die Schritte unter [install Edge Servers for lync Server 2013](lync-server-2013-install-edge-servers.md) in der Bereitstellungsdokumentation aus, um die Dateien auf dem neuen Edgeserver zu installieren, Zertifikate zu konfigurieren und die Dienste zu starten.</span><span class="sxs-lookup"><span data-stu-id="6d7be-128">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="6d7be-129">Es ist sehr wichtig, dass Sie die Richtlinien in den Themen befolgen, in denen der [externe Benutzer Zugriff in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="6d7be-129">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="6d7be-130">Dieser Abschnitt stellt lediglich einen Leitfaden für die Konfigurationseinstellungen beim Installieren dieser Serverrollen dar.</span><span class="sxs-lookup"><span data-stu-id="6d7be-130">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="6d7be-131">Sie sollten nun eine Legacy Office Communications Server 2007 R2-Edgeserver-Bereitstellung haben, die durch das vorhanden sein des BackCompatSite-Servers parallel zu einer lync Server 2013-Edge-Server-Bereitstellung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6d7be-131">You should now have a legacy Office Communications Server 2007 R2 Edge server deployment, indicated by the presence of the BackCompatSite, in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="6d7be-132">Der Verbund ist für die Verwendung des Office Communications Server 2007 R2 Directors konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="6d7be-132">Federation is configured to use the Office Communications Server 2007 R2 Director.</span></span> <span data-ttu-id="6d7be-133">Stellen Sie sicher, dass beide Bereitstellungen ordnungsgemäß ausgeführt werden, die Dienste gestartet sind, und Sie beide Bereitstellungen verwalten können, bevor Sie mit der nächsten Phase fortfahren.</span><span class="sxs-lookup"><span data-stu-id="6d7be-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

<span data-ttu-id="6d7be-134">![Topologie-Generator mit OCS-Edgeserver](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Topologie-Generator mit OCS-Edgeserver")</span><span class="sxs-lookup"><span data-stu-id="6d7be-134">![Topology Builder showing OCS Edge Server](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Topology Builder showing OCS Edge Server")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

