---
title: Bereitstellen eines Pilot-Edgeservers
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd8fddd611422562c9384a52748623623d4e6f68
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="4a237-102">Bereitstellen eines Pilot-Edgeservers</span><span class="sxs-lookup"><span data-stu-id="4a237-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a237-103">_**Letztes Änderungsdatum des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="4a237-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="4a237-104">In diesem Thema werden die Konfigurationseinstellungen hervorgehoben, die Sie vor der Bereitstellung Ihres lync Server 2013-Edgeserver beachten sollten.</span><span class="sxs-lookup"><span data-stu-id="4a237-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="4a237-105">Die Bereitstellungs-und Konfigurationsprozesse für lync Server 2013 sind mit lync Server 2010 sehr ähnlich.</span><span class="sxs-lookup"><span data-stu-id="4a237-105">The deployment and configuration processes for Lync Server 2013 are very similar to Lync Server 2010.</span></span> <span data-ttu-id="4a237-106">In diesem Abschnitt werden nur wichtige Punkte hervorgehoben, die Sie im Rahmen der Bereitstellung des pilotpools berücksichtigen sollten.</span><span class="sxs-lookup"><span data-stu-id="4a237-106">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="4a237-107">Detaillierte Anweisungen finden Sie unter [Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation, in der der Bereitstellungsprozess beschrieben wird, sowie Konfigurationsinformationen für den Zugriff durch externe Benutzer.</span><span class="sxs-lookup"><span data-stu-id="4a237-107">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="4a237-108">Wenn Sie im Assistenten zum **Definieren eines neuen Edge-Pools** navigieren, überprüfen Sie die wichtigsten Konfigurationseinstellungen, die in den folgenden Schritten gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4a237-108">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="4a237-109">Beachten Sie, dass nur wenige Seiten des Assistenten zum **Definieren eines neuen Edge-Pools** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4a237-109">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="4a237-110">**Definieren eines Edge-Pools**</span><span class="sxs-lookup"><span data-stu-id="4a237-110">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="4a237-111">Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="4a237-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="4a237-112">Navigieren Sie zum lync Server 2013-Knoten.</span><span class="sxs-lookup"><span data-stu-id="4a237-112">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="4a237-113">Klicken Sie mit der rechten Maustaste auf **Edge-Pools**, und klicken Sie auf **neuer Edge-Pool**.</span><span class="sxs-lookup"><span data-stu-id="4a237-113">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="4a237-114">![Dialogfeld ' neuen Edge-Pool definieren] ' (images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Dialogfeld ' neuen Edge-Pool definieren") '</span><span class="sxs-lookup"><span data-stu-id="4a237-114">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="4a237-115">Ein Edge-Pool kann ein Pool mit **mehreren Computern** oder ein **einzelner Computerpool**sein.</span><span class="sxs-lookup"><span data-stu-id="4a237-115">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="4a237-116">![Definieren des Dialogfelds "FQDN des Edge-Pools"] (images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Definieren des Dialogfelds \"FQDN des Edge-Pools\"")</span><span class="sxs-lookup"><span data-stu-id="4a237-116">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="4a237-117">Aktivieren Sie auf der Seite **"Features auswählen** " die Föderation oder den XMPP-Verbund nicht.</span><span class="sxs-lookup"><span data-stu-id="4a237-117">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="4a237-118">Föderation und XMPP-Föderation sind beide derzeit über den Legacy-Edgeserver von lync Server 2010 weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="4a237-118">Federation and XMPP federation are both currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="4a237-119">Diese Features werden in einer späteren Migrationsphase konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="4a237-119">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="4a237-120">![Dialogfeld ' Features auswählen] ' (images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Dialogfeld ' Features auswählen") '</span><span class="sxs-lookup"><span data-stu-id="4a237-120">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="4a237-121">Führen Sie als nächstes die folgenden Assistentenseiten aus: **externe FQDNs**, **definieren Sie die interne IP-Adresse**, und definieren Sie **die externe IP-Adresse**.</span><span class="sxs-lookup"><span data-stu-id="4a237-121">Next, continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="4a237-122">Wählen Sie auf der Seite **Nächster Hop definieren** den Director für den nächsten Hop des lync Server 2010-Edge-Pools aus.</span><span class="sxs-lookup"><span data-stu-id="4a237-122">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2010 Edge pool.</span></span>
    
    <span data-ttu-id="4a237-123">![Dialogfeld ' nächster Hop definieren] ' (images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Dialogfeld ' nächster Hop definieren") '</span><span class="sxs-lookup"><span data-stu-id="4a237-123">![Define the Next Hop dialog box](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Define the Next Hop dialog box")</span></span>

7.  <span data-ttu-id="4a237-124">Verbinden Sie auf der Seite **Front-End-oder Mediations Pools zuordnen** keinen Pool mit diesem Edge-Pool zu diesem Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="4a237-124">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="4a237-125">Der externe Mediendatenverkehr wird derzeit über den Legacy-Edgeserver von lync Server 2010 weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="4a237-125">External media traffic is currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="4a237-126">Diese Einstellung wird in einer späteren Migrationsphase konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="4a237-126">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="4a237-127">![Dialogfeld ' Front-End-Pools zuordnen] ' (images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Dialogfeld ' Front-End-Pools zuordnen") '</span><span class="sxs-lookup"><span data-stu-id="4a237-127">![Associate Front End Pools dialog box](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Associate Front End Pools dialog box")</span></span>

8.  <span data-ttu-id="4a237-128">Klicken Sie auf **Fertig stellen** , und **veröffentlichen** Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="4a237-128">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="4a237-129">Führen Sie die Schritte unter [Installieren von Edge-Servern für lync Server 2013](lync-server-2013-install-edge-servers.md) in der Bereitstellungsdokumentation aus, um die Dateien auf dem neuen Edgeserver zu installieren, Zertifikate zu konfigurieren und die Dienste zu starten.</span><span class="sxs-lookup"><span data-stu-id="4a237-129">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="4a237-130">Es ist sehr wichtig, dass Sie die Richtlinien in den Themen zum [Bereitstellen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation befolgen.</span><span class="sxs-lookup"><span data-stu-id="4a237-130">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="4a237-131">Dieser Abschnitt enthält lediglich einige Anleitungen zu Konfigurationseinstellungen beim Installieren dieser Serverrollen.</span><span class="sxs-lookup"><span data-stu-id="4a237-131">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="4a237-132">Sie sollten jetzt einen Legacy-lync Server 2010-Edgeserver parallel zu einer lync Server 2013-Edgeserver-Bereitstellung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4a237-132">You should now have a legacy Lync Server 2010 Edge Server deployed in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="4a237-133">Überprüfen Sie, ob beide Bereitstellungen ordnungsgemäß ausgeführt werden, Dienste gestartet sind, und Sie können jede Bereitstellung verwalten, bevor Sie in die nächste Phase wechseln.</span><span class="sxs-lookup"><span data-stu-id="4a237-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

