---
title: Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec73f8d25237d7d056282cc7c88685802eb50f16
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="f9419-102">Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion</span><span class="sxs-lookup"><span data-stu-id="f9419-102">Verify pilot pool coexistence with legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9419-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f9419-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a><span data-ttu-id="f9419-104">Überprüfen des Pools im Verwaltungstool von Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="f9419-104">Verify the Pool in Office Communications Server 2007 R2 Administrative Tool</span></span>

1.  <span data-ttu-id="f9419-105">Öffnen Sie das Office Communications Server 2007 R2 Verwaltungstool.</span><span class="sxs-lookup"><span data-stu-id="f9419-105">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="f9419-106">Erweitern Sie den Knoten **Gesamtstruktur**, den Knoten **Standard Edition-Server** oder **Enterprise-Pools** und dann den Pool- oder Servernamen.</span><span class="sxs-lookup"><span data-stu-id="f9419-106">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="f9419-107">Stellen Sie sicher, dass die Office Communications Server 2007 R2 Dienste im Pool aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="f9419-107">Ensure that the Office Communications Server 2007 R2 services are running on the pool.</span></span>
    
    <span data-ttu-id="f9419-108">![Office Communications Server 2007 R2-Verwaltungskonsole](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2-Verwaltungskonsole")</span><span class="sxs-lookup"><span data-stu-id="f9419-108">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a><span data-ttu-id="f9419-109">Überprüfen des Pilot Pools in lync Server 2013 Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="f9419-109">Verify the Pilot Pool in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="f9419-110">Melden Sie sich über ein Benutzerkonto, das Mitglied der CsAdministrator-Rolle ist, am lync Server 2013 Front-End-Server an.</span><span class="sxs-lookup"><span data-stu-id="f9419-110">From a user account that is a member of the CsAdministrator role, log on to the Lync Server 2013 Front End server.</span></span>

2.  <span data-ttu-id="f9419-111">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f9419-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f9419-112">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f9419-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f9419-113">Klicken Sie auf **Topologie**.</span><span class="sxs-lookup"><span data-stu-id="f9419-113">Click **Topology**.</span></span>

4.  <span data-ttu-id="f9419-114">Überprüfen Sie, ob die bereitgestellten Server im Pilotpool vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f9419-114">Verify that the servers you deployed are present in your pilot pool.</span></span>
    
    <span data-ttu-id="f9419-115">![Seite "lync Server-Systemsteuerung Topologie"](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Seite "lync Server-Systemsteuerung Topologie"")</span><span class="sxs-lookup"><span data-stu-id="f9419-115">![Lync Server Control Panel Topology page](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Lync Server Control Panel Topology page")</span></span>  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a><span data-ttu-id="f9419-116">Überprüfen, ob lync Server 2013 Dienste gestartet wurden</span><span class="sxs-lookup"><span data-stu-id="f9419-116">Verify Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="f9419-117">Öffnen Sie im lync Server 2013 Front-End-Server das Applet **Dienste** in der Gruppe **Verwaltung** .</span><span class="sxs-lookup"><span data-stu-id="f9419-117">On the Lync Server 2013 Front End Server, open the **Services** applet from the **Administrative Tools** group.</span></span>

2.  <span data-ttu-id="f9419-118">Überprüfen Sie, ob die aufgeführten Dienste mit der Liste in der nachfolgenden Abbildung übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f9419-118">Verify that the services listed match the list in the following figure.</span></span>
    
    <span data-ttu-id="f9419-119">![Dienstseite mit gestarteten lync-Diensten](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Dienstseite mit gestarteten lync-Diensten")</span><span class="sxs-lookup"><span data-stu-id="f9419-119">![Services page showing Lync services started](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Services page showing Lync services started")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

