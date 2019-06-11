---
title: Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f67b113a4619d90345df9858f348d663383066d7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="b9862-102">Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion</span><span class="sxs-lookup"><span data-stu-id="b9862-102">Verify pilot pool coexistence with legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9862-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b9862-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a><span data-ttu-id="b9862-104">Überprüfen des Pools im Office Communications Server 2007 R2-Verwaltungs Tool</span><span class="sxs-lookup"><span data-stu-id="b9862-104">Verify the Pool in Office Communications Server 2007 R2 Administrative Tool</span></span>

1.  <span data-ttu-id="b9862-105">Öffnen Sie das Office Communications Server 2007 R2-Verwaltungstool.</span><span class="sxs-lookup"><span data-stu-id="b9862-105">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="b9862-106">Erweitern Sie den Knoten **Gesamtstruktur** , erweitern Sie den Knoten **Standard Edition-Server** oder **Enterprise-Pools** , und erweitern Sie dann den Pool-oder Servernamen.</span><span class="sxs-lookup"><span data-stu-id="b9862-106">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="b9862-107">Stellen Sie sicher, dass die Office Communications Server 2007 R2-Dienste im Pool ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b9862-107">Ensure that the Office Communications Server 2007 R2 services are running on the pool.</span></span>
    
    <span data-ttu-id="b9862-108">![Office Communications Server 2007 R2-Verwaltungskonsole] (images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2-Verwaltungskonsole")</span><span class="sxs-lookup"><span data-stu-id="b9862-108">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a><span data-ttu-id="b9862-109">Überprüfen des Pilot Pools in der lync Server 2013-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="b9862-109">Verify the Pilot Pool in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="b9862-110">Melden Sie sich von einem Benutzerkonto, das ein Mitglied der CsAdministrator-Rolle ist, beim lync Server 2013-Front-End-Server an.</span><span class="sxs-lookup"><span data-stu-id="b9862-110">From a user account that is a member of the CsAdministrator role, log on to the Lync Server 2013 Front End server.</span></span>

2.  <span data-ttu-id="b9862-111">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b9862-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b9862-112">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b9862-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b9862-113">Klicken Sie auf **Topologie**.</span><span class="sxs-lookup"><span data-stu-id="b9862-113">Click **Topology**.</span></span>

4.  <span data-ttu-id="b9862-114">Überprüfen Sie, ob die von Ihnen bereitgestellten Server in Ihrem Pilot Pool vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b9862-114">Verify that the servers you deployed are present in your pilot pool.</span></span>
    
    <span data-ttu-id="b9862-115">![Seite "Topologie der lync Server-Systemsteuerung"] (images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Seite \"Topologie der lync Server-Systemsteuerung\"")</span><span class="sxs-lookup"><span data-stu-id="b9862-115">![Lync Server Control Panel Topology page](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Lync Server Control Panel Topology page")</span></span>  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a><span data-ttu-id="b9862-116">Überprüfen, ob die lync Server 2013-Dienste gestartet wurden</span><span class="sxs-lookup"><span data-stu-id="b9862-116">Verify Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="b9862-117">Öffnen Sie auf dem lync Server 2013-Front-End-Server das Applet **Dienste** in der Gruppe **Verwaltungs Tools** .</span><span class="sxs-lookup"><span data-stu-id="b9862-117">On the Lync Server 2013 Front End Server, open the **Services** applet from the **Administrative Tools** group.</span></span>

2.  <span data-ttu-id="b9862-118">Überprüfen Sie, ob die aufgeführten Dienste der Liste in der folgenden Abbildung entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b9862-118">Verify that the services listed match the list in the following figure.</span></span>
    
    <span data-ttu-id="b9862-119">![Seite "Dienste" mit gestarteten lync-Diensten] (images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Seite \"Dienste\" mit gestarteten lync-Diensten")</span><span class="sxs-lookup"><span data-stu-id="b9862-119">![Services page showing Lync services started](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Services page showing Lync services started")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

