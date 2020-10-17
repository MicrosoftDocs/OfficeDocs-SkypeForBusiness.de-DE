---
title: 'Lync Server 2013: Konfigurieren von DNS-Host Einträgen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e96c23741430f17b6d343606526df230f74c032
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537132"
---
# <a name="configure-dns-host-records-for-lync-server-2013"></a><span data-ttu-id="48e45-102">Konfigurieren von DNS-Host Einträgen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48e45-102">Configure DNS Host records for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48e45-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="48e45-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="48e45-104">Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie mindestens als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="48e45-104">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<div>

## <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="48e45-105">So konfigurieren Sie DNS-Hosteinträge (A)</span><span class="sxs-lookup"><span data-stu-id="48e45-105">To configure DNS Host A records</span></span>

1.  <span data-ttu-id="48e45-106">Klicken Sie auf dem DNS-Server (Domain Name System) auf **Start**, klicken Sie auf **Verwaltung** und anschließend auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="48e45-106">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="48e45-107">Erweitern Sie in der Konsolenstruktur für Ihre Domäne den Knoten **Forward-Lookupzonen**, und klicken Sie dann mit der rechten Maustaste auf die Domäne, in der lync Server 2013 installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="48e45-107">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="48e45-108">Klicken Sie auf **Neuer Host (A oder AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="48e45-108">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="48e45-109">Klicken Sie auf **Name**, und geben Sie den Hostnamen für den Pool ein (der Domänenname wird von der Zone abgeleitet, in welcher der Eintrag definiert ist, und muss nicht als Teil des A-Eintrags eingegeben werden).</span><span class="sxs-lookup"><span data-stu-id="48e45-109">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="48e45-110">Klicken Sie auf **IP-Adresse**, geben Sie die virtuelle IP (VIP) des Lastenausgleichs für die Front-End-Pool ein.</span><span class="sxs-lookup"><span data-stu-id="48e45-110">Click **IP Address**, type the virtual IP (VIP) of the load balancer for the Front End pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="48e45-111">In Bereitstellungen, die einen Director-Pool verwenden, sollten die Hosteinträge (A) für die einfachen URLs auf die VIP des Director-Lastenausgleichssystems zeigen.</span><span class="sxs-lookup"><span data-stu-id="48e45-111">In deployments that use a Director pool, the host (A) records for the simple URLs should point to the VIP of the Director load balancer.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="48e45-p101">Wenn Sie nur einen Enterprise Edition-Server oder Director bereitstellen, der ohne ein Lastenausgleichssystem mit der Topologie verbunden ist, oder wenn Sie einen Standard Edition-Server bereitstellen, geben Sie die IP-Adresse des Enterprise Edition-Servers, Standard Edition-Servers oder Directors ein. Ein Lastenausgleichssystem ist erforderlich, wenn sich mehrere Enterprise Edition-Server oder Directors in einem Pool befinden. Bei Standard Edition-Servern werden keine Lastenausgleichssysteme verwendet.</span><span class="sxs-lookup"><span data-stu-id="48e45-p101">If you deploy only one Enterprise Edition server or Director that is connected to the topology without a load balancer, or if you deploy a Standard Edition server, type the IP address of the Enterprise Edition server, Standard Edition server, or Director. A load balancer is required if you deploy more than one Enterprise Edition server or Director in a pool. Load balancers are not used with Standard Edition servers.</span></span>

    
    </div>

6.  <span data-ttu-id="48e45-115">Klicken Sie auf **Host hinzufügen** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="48e45-115">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="48e45-116">Wenn Sie einen zusätzlichen A-Eintrag erstellen möchten, wiederholen Sie die Schritte 4 und 5.</span><span class="sxs-lookup"><span data-stu-id="48e45-116">To create an additional A record, repeat steps 4 and 5.</span></span>

8.  <span data-ttu-id="48e45-117">Wenn Sie alle erforderlichen A-Einträge erstellt haben, klicken Sie auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="48e45-117">When you are finished creating all the A records that you need, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

