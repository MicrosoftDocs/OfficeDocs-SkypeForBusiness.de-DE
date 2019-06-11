---
title: Überprüfen der Office Communications Server 2007 R2-Umgebung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9369ad631b772e0a73677ab3214e24083426148a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a><span data-ttu-id="82de3-102">Überprüfen der Office Communications Server 2007 R2-Umgebung</span><span class="sxs-lookup"><span data-stu-id="82de3-102">Verify Office Communications Server 2007 R2 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82de3-103">_**Letztes Änderungsdatum des Themas:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="82de3-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="82de3-104">Bevor Sie lync Server 2013 in einem koexistenzstatus mit Office Communications Server 2007 R2 bereitstellen, müssen Sie überprüfen, ob die Office Communications Server 2007 R2-Dienste konfiguriert und gestartet sind.</span><span class="sxs-lookup"><span data-stu-id="82de3-104">Prior to deploying Lync Server 2013 in a coexistence state with Office Communications Server 2007 R2, you need to verify the Office Communications Server 2007 R2 services are configured and started.</span></span>

<span data-ttu-id="82de3-105">**Überprüfen, ob der Pool mit dem Office Communications Server 2007 R2-Verwaltungs Tool gestartet wurde**</span><span class="sxs-lookup"><span data-stu-id="82de3-105">**Verify the Pool is started using the Office Communications Server 2007 R2 Administrative Tool**</span></span>

1.  <span data-ttu-id="82de3-106">Öffnen Sie das Office Communications Server 2007 R2-Verwaltungstool.</span><span class="sxs-lookup"><span data-stu-id="82de3-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="82de3-107">Erweitern Sie den Knoten **Gesamtstruktur** , erweitern Sie den Knoten **Standard Edition-Server** oder **Enterprise-Pools** , und erweitern Sie dann den Pool-oder Servernamen.</span><span class="sxs-lookup"><span data-stu-id="82de3-107">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="82de3-108">Stellen Sie sicher, dass die Dienste auf dem Standard Edition-Server oder Enterprise-Pool ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="82de3-108">Ensure that the services are running on the Standard Edition server or Enterprise pool.</span></span>
    
    <span data-ttu-id="82de3-109">![Office Communications Server 2007 R2-Verwaltungskonsole] (images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2-Verwaltungskonsole")</span><span class="sxs-lookup"><span data-stu-id="82de3-109">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>

<span data-ttu-id="82de3-110">**Überprüfen der Benutzer, die für Office Communications Server 2007 R2 konfiguriert sind**</span><span class="sxs-lookup"><span data-stu-id="82de3-110">**Review Users configured for Office Communications Server 2007 R2**</span></span>

1.  <span data-ttu-id="82de3-111">Öffnen Sie das Office Communications Server 2007 R2-Verwaltungstool.</span><span class="sxs-lookup"><span data-stu-id="82de3-111">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="82de3-112">Erweitern Sie den Knoten **Gesamtstruktur** , erweitern Sie den Knoten **Standard Edition-Server** oder **Enterprise-Pools** , und erweitern Sie dann den Pool-oder Servernamen.</span><span class="sxs-lookup"><span data-stu-id="82de3-112">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="82de3-113">Klicken Sie auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="82de3-113">Click **Users**.</span></span>

4.  <span data-ttu-id="82de3-114">Überprüfen Sie die Liste der Benutzer von Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="82de3-114">Verify the list of Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="82de3-115">![Liste FO-Benutzer im OCS-Administrator Tool] (images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "Liste FO-Benutzer im OCS-Administrator Tool")</span><span class="sxs-lookup"><span data-stu-id="82de3-115">![List fo users in OCS Admin tool](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "List fo users in OCS Admin tool")</span></span>

<span data-ttu-id="82de3-116">**Überprüfen der Konfiguration von Legacy-XMPP-Verbundpartnern**</span><span class="sxs-lookup"><span data-stu-id="82de3-116">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="82de3-117">Navigieren Sie vom Legacy-XMPP-Server zum Applet Dienste\\für Verwaltungs Tools.</span><span class="sxs-lookup"><span data-stu-id="82de3-117">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="82de3-118">Überprüfen Sie, ob der Office Communications Server-XMPP-Gatewayserver gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="82de3-118">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="82de3-119">![Office Communications Server-XMPP] -Gatewaydienst (images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server-XMPP") -Gatewaydienst</span><span class="sxs-lookup"><span data-stu-id="82de3-119">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

