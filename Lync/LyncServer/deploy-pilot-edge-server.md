---
title: Bereitstellen von Pilot Edgeserver
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b519256d254b5862dae904830620ba09d184d5df
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="5d53e-102">Bereitstellen von Pilot Edgeserver</span><span class="sxs-lookup"><span data-stu-id="5d53e-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d53e-103">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="5d53e-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="5d53e-104">In diesem Thema werden Konfigurationseinstellungen hervorgehoben, die Sie vor der Bereitstellung Ihrer lync Server 2013 Edgeserver beachten sollten.</span><span class="sxs-lookup"><span data-stu-id="5d53e-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="5d53e-105">Die Bereitstellungs-und Konfigurationsprozesse für lync Server 2013 ähneln lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5d53e-105">The deployment and configuration processes for Lync Server 2013 are very similar to Lync Server 2010.</span></span> <span data-ttu-id="5d53e-106">In diesem Abschnitt sind nur die wichtigsten zu beachtenden Punkte für die Bereitstellung Ihres Pilotpools hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="5d53e-106">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="5d53e-107">Ausführliche Anweisungen finden Sie unter [Deploying External User Access in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation, in der der Bereitstellungsprozess beschrieben wird und der auch Konfigurationsinformationen für den Zugriff durch externe Benutzer enthält.</span><span class="sxs-lookup"><span data-stu-id="5d53e-107">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="5d53e-p102">Überprüfen Sie beim Navigieren durch den Assistenten zum **Definieren eines neuen Edgepools** die in den folgenden Schritten dargestellten wichtigen Konfigurationseinstellungen. Beachten Sie, dass nur einige der Seiten des Assistenten zum **Definieren eines neuen Edgepools** abgebildet sind.</span><span class="sxs-lookup"><span data-stu-id="5d53e-p102">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="5d53e-110">**Definieren eines Edgepools**</span><span class="sxs-lookup"><span data-stu-id="5d53e-110">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="5d53e-111">Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="5d53e-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="5d53e-112">Navigieren Sie zum Knoten lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d53e-112">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="5d53e-113">Klicken Sie mit der rechten Maustaste auf **Edgepools**, und klicken Sie dann auf **Neuer Edgepool**.</span><span class="sxs-lookup"><span data-stu-id="5d53e-113">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="5d53e-114">![Definieren des Dialogfelds "neuer Edge-Pool"](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Definieren des Dialogfelds "neuer Edge-Pool"")</span><span class="sxs-lookup"><span data-stu-id="5d53e-114">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="5d53e-115">Ein Edgepool ist entweder ein **Pool mit mehreren Computern** oder ein **Pool mit einem Computer**.</span><span class="sxs-lookup"><span data-stu-id="5d53e-115">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="5d53e-116">![Definieren des Dialogfelds für den FQDN des Edge-Pools](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Definieren des Dialogfelds für den FQDN des Edge-Pools")</span><span class="sxs-lookup"><span data-stu-id="5d53e-116">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="5d53e-117">Aktivieren Sie auf der Seite **Funktionen auswählen** nicht den Verbund oder den XMPP-Partnerverbund.</span><span class="sxs-lookup"><span data-stu-id="5d53e-117">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="5d53e-118">Der Partnerverbund und der XMPP-Verbund werden derzeit über die Legacy lync Server 2010 Edgeserver weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="5d53e-118">Federation and XMPP federation are both currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="5d53e-119">Diese Funktionen werden in einer späteren Phase der Migration konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="5d53e-119">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="5d53e-120">![Dialogfeld ' Features auswählen '](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Dialogfeld ' Features auswählen '")</span><span class="sxs-lookup"><span data-stu-id="5d53e-120">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="5d53e-121">Bearbeiten Sie anschließend die folgenden Seiten des Assistenten: **Externe FQDNs**, **	Interne IP-Adresse definieren** und **Externe IP-Adresse definieren**.</span><span class="sxs-lookup"><span data-stu-id="5d53e-121">Next, continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="5d53e-122">Wählen Sie auf der Seite **nächsten Hop definieren** den Director für den nächsten Hop des lync Server 2010 Edgepool aus.</span><span class="sxs-lookup"><span data-stu-id="5d53e-122">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2010 Edge pool.</span></span>
    
    <span data-ttu-id="5d53e-123">![Definieren des nächsten Hops (Dialogfeld)](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Definieren des nächsten Hops (Dialogfeld)")</span><span class="sxs-lookup"><span data-stu-id="5d53e-123">![Define the Next Hop dialog box](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Define the Next Hop dialog box")</span></span>

7.  <span data-ttu-id="5d53e-124">Verknüpfen Sie auf der Seite **Front-End-oder Vermittlungs Pools zuordnen** keinen Pool mit diesem Edgepool zu diesem Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="5d53e-124">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="5d53e-125">Der externe Mediendatenverkehr wird derzeit über die Legacy lync Server 2010 Edgeserver weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="5d53e-125">External media traffic is currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="5d53e-126">Diese Einstellung wird in einer späteren Phase der Migration konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="5d53e-126">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="5d53e-127">![Dialogfeld "Front-End-Pools zuordnen"](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Dialogfeld "Front-End-Pools zuordnen"")</span><span class="sxs-lookup"><span data-stu-id="5d53e-127">![Associate Front End Pools dialog box](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Associate Front End Pools dialog box")</span></span>

8.  <span data-ttu-id="5d53e-128">Klicken Sie auf **Fertig stellen**, und **veröffentlichen** Sie anschließend die Topologie.</span><span class="sxs-lookup"><span data-stu-id="5d53e-128">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="5d53e-129">Führen Sie die Schritte unter [install Edge Servers for lync Server 2013](lync-server-2013-install-edge-servers.md) in der Bereitstellungsdokumentation aus, um die Dateien auf dem neuen Edgeserver zu installieren, Zertifikate zu konfigurieren und die Dienste zu starten.</span><span class="sxs-lookup"><span data-stu-id="5d53e-129">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="5d53e-130">Es ist sehr wichtig, dass Sie die Richtlinien in den Themen befolgen, in denen der [externe Benutzer Zugriff in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5d53e-130">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="5d53e-131">Dieser Abschnitt stellt lediglich einen Leitfaden für die Konfigurationseinstellungen beim Installieren dieser Serverrollen dar.</span><span class="sxs-lookup"><span data-stu-id="5d53e-131">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="5d53e-132">Sie sollten nun über ein Legacy-lync Server 2010 verfügen, Edgeserver parallel mit einer lync Server 2013-Edge-Server-Bereitstellung bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5d53e-132">You should now have a legacy Lync Server 2010 Edge Server deployed in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="5d53e-133">Stellen Sie sicher, dass beide Bereitstellungen ordnungsgemäß ausgeführt werden, die Dienste gestartet sind, und Sie beide Bereitstellungen verwalten können, bevor Sie mit der nächsten Phase fortfahren.</span><span class="sxs-lookup"><span data-stu-id="5d53e-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

