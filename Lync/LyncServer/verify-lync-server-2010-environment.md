---
title: Überprüfen der lync Server 2010 Umgebung
description: Überprüfen Sie lync Server 2010 Umgebung.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 570fd2a9efdc90899ff4f91146b7aeb1991f6764
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555581"
---
# <a name="verify-lync-server-2010-environment"></a><span data-ttu-id="1f7ec-103">Überprüfen der lync Server 2010 Umgebung</span><span class="sxs-lookup"><span data-stu-id="1f7ec-103">Verify Lync Server 2010 environment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f7ec-104">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="1f7ec-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="1f7ec-105">Bevor Sie lync Server 2013 im koexistenzstatus mit lync Server 2010 bereitstellen, müssen Sie überprüfen, ob lync Server 2010 Dienste konfiguriert und gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="1f7ec-105">Before deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you need to verify that Lync Server 2010 services have been configured and started.</span></span> <span data-ttu-id="1f7ec-106">Es ist wichtig, wichtige Dienste und Features zu identifizieren, die in ihrer Vorgänger Umgebung vorhanden sind, bevor Sie einen lync Server 2013-Pilot Pool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1f7ec-106">It is important to identify key services and features that exist in your legacy environment, prior to deploying a Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="1f7ec-107">Bevor Sie Microsoft lync Server 2013 xmpp in einem koexistenzstatus mit einer älteren XMPP-Bereitstellung bereitstellen, müssen Sie überprüfen, ob die älteren XMPP-Dienste konfiguriert und gestartet wurden, und ermitteln, welcher Verbundpartner von der älteren XMPP-Konfiguration unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="1f7ec-107">Before deploying Microsoft Lync Server 2013 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="1f7ec-108">Die Überprüfung Ihrer Legacy-lync Server 2010-Bereitstellung umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1f7ec-108">Verifying your legacy Lync Server 2010 deployment entails the following:</span></span>

  - <span data-ttu-id="1f7ec-109">Überprüfen, ob die lync Server 2010 Dienste gestartet wurden</span><span class="sxs-lookup"><span data-stu-id="1f7ec-109">Verifying the Lync Server 2010 services are started</span></span>

  - <span data-ttu-id="1f7ec-110">Überprüfen der Topologie und der Benutzer in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1f7ec-110">Reviewing the topology and users in Lync Server 2010.</span></span>

  - <span data-ttu-id="1f7ec-111">Überprüfen der Partnerverbund- und Edgeservereinstellungen</span><span class="sxs-lookup"><span data-stu-id="1f7ec-111">Verifying the federation and Edge server settings.</span></span>

  - <span data-ttu-id="1f7ec-112">Überprüfen der XMPP-Dienste und Verbundpartner</span><span class="sxs-lookup"><span data-stu-id="1f7ec-112">Verifying XMPP services and federated partners.</span></span>

<span data-ttu-id="1f7ec-113">**Überprüfen, lync Server 2010 Dienste gestartet wurden**</span><span class="sxs-lookup"><span data-stu-id="1f7ec-113">**Verify Lync Server 2010 Services are started**</span></span>

1.  <span data-ttu-id="1f7ec-114">Navigieren Sie im lync Server 2010 Front-End-Server zum Applet Dienste für administrative Tools \\ .</span><span class="sxs-lookup"><span data-stu-id="1f7ec-114">From the Lync Server 2010 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="1f7ec-115">Überprüfen Sie, ob die folgenden Dienste auf dem Front-End-Server ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="1f7ec-115">Verify that the following services are running on the Front End Server:</span></span>
    
    <span data-ttu-id="1f7ec-116">![Liste der auf Front-End-Server ausgeführten Dienste](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "Liste der auf Front-End-Server ausgeführten Dienste")</span><span class="sxs-lookup"><span data-stu-id="1f7ec-116">![List of services running on Front End Server](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "List of services running on Front End Server")</span></span>

<span data-ttu-id="1f7ec-117">**Überprüfen der lync Server 2010 Topologie in lync Server-Systemsteuerung**</span><span class="sxs-lookup"><span data-stu-id="1f7ec-117">**Review the Lync Server 2010 topology in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="1f7ec-118">Melden Sie sich über ein Konto, das Mitglied der Gruppe RTCUniversalServerAdmins oder der Administratorrolle CsAdministrator oder CsUserAdministrator ist, am Front-End-Server an.</span><span class="sxs-lookup"><span data-stu-id="1f7ec-118">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="1f7ec-119">Öffnen Sie die Lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="1f7ec-119">Open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="1f7ec-120">Wählen Sie **Topologie** aus.</span><span class="sxs-lookup"><span data-stu-id="1f7ec-120">Select **Topology**.</span></span> <span data-ttu-id="1f7ec-121">Stellen Sie sicher, dass die verschiedenen Server in ihrer lync Server 2010-Bereitstellung aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="1f7ec-121">Verify that the various servers in your Lync Server 2010 deployment are listed.</span></span>
    
    <span data-ttu-id="1f7ec-122">![Lync Server 2010-topologieseite "Systemsteuerung"](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010-topologieseite "Systemsteuerung"")</span><span class="sxs-lookup"><span data-stu-id="1f7ec-122">![Lync Server 2010 Control Panel topology page](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 Control Panel topology page")</span></span>

<span data-ttu-id="1f7ec-123">**So überprüfen Sie lync Server 2010 Benutzer in lync Server-Systemsteuerung**</span><span class="sxs-lookup"><span data-stu-id="1f7ec-123">**To review Lync Server 2010 users in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="1f7ec-124">Öffnen Sie die Lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="1f7ec-124">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="1f7ec-125">Wählen Sie **Benutzer** aus, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="1f7ec-125">Select **Users** and then click **Find**.</span></span>

3.  <span data-ttu-id="1f7ec-126">Stellen Sie sicher, dass die Spalte **Registrierungspool** für jeden aufgelisteten Benutzer auf den lync Server 2010 Pool zeigt.</span><span class="sxs-lookup"><span data-stu-id="1f7ec-126">Verify that the **Registrar Pool** column points to the Lync Server 2010 pool for each user listed.</span></span>
    
    <span data-ttu-id="1f7ec-127">![Lync Server 2010 Systemsteuerung, die Benutzer auflistet](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 Systemsteuerung, die Benutzer auflistet")</span><span class="sxs-lookup"><span data-stu-id="1f7ec-127">![Lync Server 2010 Control Panel listing users](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 Control Panel listing users")</span></span>

<span data-ttu-id="1f7ec-128">**So überprüfen Sie lync Server 2010 Edge-und Verbund Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="1f7ec-128">**To verify Lync Server 2010 Edge and Federation Settings**</span></span>

1.  <span data-ttu-id="1f7ec-129">Starten Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="1f7ec-129">Start Topology Builder.</span></span>

2.  <span data-ttu-id="1f7ec-130">Wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen** aus.</span><span class="sxs-lookup"><span data-stu-id="1f7ec-130">Select **Download Topology from existing deployment**.</span></span>

3.  <span data-ttu-id="1f7ec-131">Wählen Sie einen Dateinamen aus, und speichern Sie die Topologie als standardmäßigen TBXML-Dateityp.</span><span class="sxs-lookup"><span data-stu-id="1f7ec-131">Choose a file name and save the topology with the default .tbxml file type.</span></span>

4.  <span data-ttu-id="1f7ec-132">Erweitern Sie den Knoten lync Server 2010, um die verschiedenen Server Rollen in der Bereitstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1f7ec-132">Expand the Lync Server 2010 node to reveal the various server roles in the deployment.</span></span>

5.  <span data-ttu-id="1f7ec-133">Wählen Sie den Knoten Website aus, und überprüfen Sie, ob ein **Standort Verbund-Routen Zuordnungs** Wert festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="1f7ec-133">Select the site node and verify if a **Site federation route assignment** value is set.</span></span>
    
    <span data-ttu-id="1f7ec-134">![Topologie-Generator, Standort Verbund Route](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Topologie-Generator, Standort Verbund Route")</span><span class="sxs-lookup"><span data-stu-id="1f7ec-134">![Topology Builder, Site Federation Route](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Topology Builder, Site Federation Route")</span></span>

6.  <span data-ttu-id="1f7ec-p103">Wählen Sie anschließend den Standard Edition Server- oder Enterprise Edition-Front-End-Pool aus. Bestimmen Sie, ob unter **Zuordnungen** ein Edgepool für Medien konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="1f7ec-p103">Next, select the Standard Edition Server or Enterprise Edition front end pool. Determine if an Edge pool has been configured for Media below **Associations**.</span></span>
    
    <span data-ttu-id="1f7ec-137">![Topologie-Generator mit Servern und Pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Topologie-Generator mit Servern und Pools")</span><span class="sxs-lookup"><span data-stu-id="1f7ec-137">![Topology Builder showing servers and pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Topology Builder showing servers and pools")</span></span>

7.  <span data-ttu-id="1f7ec-138">Wählen Sie schließlich den Edgepool aus, und identifizieren Sie, ob für **Auswahl für nächsten Hop** ein nächster Hoppool konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="1f7ec-138">Finally, select the Edge pool and identify if a Next hop pool is configured below **Next hop selection**.</span></span>
    
    <span data-ttu-id="1f7ec-139">![Topologie-Generator, Auswahl des nächsten Hops](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Topologie-Generator, Auswahl des nächsten Hops")</span><span class="sxs-lookup"><span data-stu-id="1f7ec-139">![Topology Builder, Next hop selection](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Topology Builder, Next hop selection")</span></span>

<span data-ttu-id="1f7ec-140">**Überprüfen der XMPP-Verbundpartnerkonfiguration der Vorversion**</span><span class="sxs-lookup"><span data-stu-id="1f7ec-140">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="1f7ec-141">Navigieren Sie auf dem vorversions-XMPP-Server zum Applet Dienste für administrative Tools \\ .</span><span class="sxs-lookup"><span data-stu-id="1f7ec-141">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="1f7ec-142">Überprüfen Sie, ob der Office Communications Server-XMPP-Gatewaydienst gestartet ist.</span><span class="sxs-lookup"><span data-stu-id="1f7ec-142">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="1f7ec-143">![Office Communications Server XMPP-Gatewaydienst](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP-Gatewaydienst")</span><span class="sxs-lookup"><span data-stu-id="1f7ec-143">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

