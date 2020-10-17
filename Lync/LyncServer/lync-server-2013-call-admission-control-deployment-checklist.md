---
title: 'Lync Server 2013: Prüfliste zur Bereitstellung der Anrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e16c4c77876064ca0ab9210b96d7c13d68cc4218
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537242"
---
# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="d28d2-102">Prüfliste zur Bereitstellung der Anrufsteuerung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d28d2-102">Call admission control deployment checklist for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d28d2-103">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="d28d2-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="d28d2-104">Überprüfen Sie anhand der folgenden Liste, ob Sie alle erforderlichen Konfigurationsaufgaben für die Bereitstellung der Anrufsteuerung (Call Admission Control, CAC) abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="d28d2-104">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy call admission control (CAC).</span></span>

  - <span data-ttu-id="d28d2-p101">Wenn ein oder mehrere Edgeserver bereitgestellt wurden, muss die IP-Adresse jeder externen Schnittstelle der Subnetzliste in den Netzwerkkonfigurationseinstellungen mit der Bitmaske 32 hinzugefügt werden. Sie sollten dieses Subnetz (IP-Adresse) außerdem der Netzwerkstandort-ID für den geografischen Standort zuordnen, an dem der A/V-Edgedienst bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="d28d2-p101">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32. You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d28d2-107">Zum Implementieren der Anrufsteuerung sind keine Edgeserver erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d28d2-107">Edge servers are not required to implement CAC.</span></span>

    
    </div>

  - <span data-ttu-id="d28d2-108">Stellen Sie sicher, dass die Anrufsteuerung aktiviert ist, entweder über lync Server-Systemsteuerung oder durch Ausführen des Cmdlets, wie in [enable Call Admission Control in lync Server 2013](lync-server-2013-enable-call-admission-control.md)angegeben.</span><span class="sxs-lookup"><span data-stu-id="d28d2-108">Make sure that CAC is enabled, either through Lync Server Control Panel or by running the cmdlet as specified in [Enable call admission control in Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span></span>

  - <span data-ttu-id="d28d2-109">Stellen Sie sicher, dass die Anrufsteuerung an allen zentralen Standorten aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d28d2-109">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="d28d2-110">Dies kann über den Topologie-Generator erfolgen.</span><span class="sxs-lookup"><span data-stu-id="d28d2-110">This can be done through the Topology Builder.</span></span> <span data-ttu-id="d28d2-111">Wenn beim Veröffentlichen eine Warnung generiert wird, ignorieren Sie diese *nicht*.</span><span class="sxs-lookup"><span data-stu-id="d28d2-111">If a warning is generated when you publish, *do not* ignore it.</span></span>

  - <span data-ttu-id="d28d2-112">Stellen Sie sicher, dass alle im Unternehmensnetzwerk verwalteten Subnetze in den Netzwerkkonfigurationseinstellungen konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="d28d2-112">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="d28d2-113">Außerdem ist es wichtig, dass jedem Subnetz ein Netzwerkstandort zugeordnet ist, wie in Zuordnen eines Subnetzes [mit einem Netzwerkstandort in lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)erläutert.</span><span class="sxs-lookup"><span data-stu-id="d28d2-113">It is also essential that every subnet be associated to a network site, as explained in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

  - <span data-ttu-id="d28d2-114">Stellen Sie sicher, dass die Subnetz- oder IP-Adressen aller Front-End-Server, Survivable Branch Appliances (SBAs), A/V-Konferenzserver (sofern in einem separaten Pool bereitgestellt) und Vermittlungsserver in den Netzwerkkonfigurationseinstellungen konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="d28d2-114">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

