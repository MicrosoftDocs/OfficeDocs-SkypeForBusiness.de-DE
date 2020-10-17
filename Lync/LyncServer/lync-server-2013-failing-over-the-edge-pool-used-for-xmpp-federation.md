---
title: 'Lync Server 2013: Failover des für XMPP-Verbund verwendeten Edgepools'
description: 'Lync Server 2013: Fehler bei der Edgepool, die für den XMPP-Partnerverbund verwendet wird.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccdfe119258b4d09ddedefb22d0272d72003bf04
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554901"
---
# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="a4e89-103">Failover der Edgepool, die für den XMPP-Verbund in lync Server 2013 verwendet wurden</span><span class="sxs-lookup"><span data-stu-id="a4e89-103">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4e89-104">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="a4e89-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="a4e89-p101">Ein Edgepool in Ihrer Organisation wurde als Pool für den XMPP-Verbund festgelegt. Wenn dieser Pool ausfällt, müssen Sie einen Failover des XMPP-Verbunds zu einem anderen Edgepool ausführen, um den XMPP-Verbund wieder verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="a4e89-p101">In your organization, there is one Edge pool designated as the pool to use for XMPP federation. If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="a4e89-107">Wenn Sie Edgepools zum ersten Mal installieren und den XMPP-Verbund aktivieren, können Sie den Notfallwiederherstellungsprozess vereinfachen, indem Sie externe DNS-SRV-Einträge für alle Edgepools des XMPP-Verbunds anstatt nur einen einzigen einrichten.</span><span class="sxs-lookup"><span data-stu-id="a4e89-107">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="a4e89-108">Jeder SRV-Eintrag muss über eine eigene Priorität verfügen.</span><span class="sxs-lookup"><span data-stu-id="a4e89-108">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="a4e89-109">Der gesamte XMPP-Verbunddatenverkehr wird über den Pool mit dem SRV-Eintrag abgewickelt, der über die höchste Priorität verfügt.</span><span class="sxs-lookup"><span data-stu-id="a4e89-109">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> <span data-ttu-id="a4e89-110">Weitere Informationen zum Aktivieren und Einrichten von XMPP-Verbund finden Sie unter [Einrichten von XMPP-Verbund in lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="a4e89-110">For more information on enabling and setting up XMPP federation, see [Setting up XMPP federation in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span></span>

<span data-ttu-id="a4e89-111">Im folgenden Verfahren stellt EdgePool1 den Pool dar, in dem der XMPP-Verbund ursprünglich gehostet wurde; EdgePool2 ist der Pool, in dem der XMPP-Verbund jetzt gehostet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a4e89-111">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="a4e89-112">Failover des Edgepools für den XMPP-Verbund</span><span class="sxs-lookup"><span data-stu-id="a4e89-112">Failing Over the Edge Pool Used for XMPP Federation</span></span>

1.  <span data-ttu-id="a4e89-113">Wenn Sie (neben dem ausgefallenen) noch keinen weiteren Edgepool bereitgestellt haben, stellen Sie den Pool jetzt bereit.</span><span class="sxs-lookup"><span data-stu-id="a4e89-113">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> <span data-ttu-id="a4e89-114">Ausführliche Informationen finden Sie unter [Deploying External User Access in lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="a4e89-114">For details, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

2.  <span data-ttu-id="a4e89-115">Führen Sie auf jedem Edgeserver im neuen Edgepool, in dem jetzt der XMPP-Verbund gehostet wird (EdgePool2), das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="a4e89-115">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="a4e89-116">Führen Sie das folgende Cmdlet aus, damit die XMPP-Verbundroute wieder auf EdgePool2 zeigt:</span><span class="sxs-lookup"><span data-stu-id="a4e89-116">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="a4e89-117">In diesem Beispiel stellt Site2 den Standort mit dem Edgepool dar, in dem jetzt die XMPP-Verbundroute gehostet wird, und EdgeServer2.contoso.com ist der FQDN eines Edgeservers in diesem Pool.</span><span class="sxs-lookup"><span data-stu-id="a4e89-117">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="a4e89-118">Ändern Sie auf dem externen DNS-Server den DNS-A-Eintrag für den XMPP-Verbund, sodass dieser auf EdgeServer2.contoso.com verweist.</span><span class="sxs-lookup"><span data-stu-id="a4e89-118">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="a4e89-p104">Wenn Sie noch nicht über einen DNS-SRV-Eintrag für den XMPP-Verbund verfügen, der in den Edgepool aufgelöst wird, in dem jetzt der XMPP-Verbund gehostet wird, müssen Sie diesen hinzufügen, wie im folgenden Beispiel veranschaulicht. Dieser SRV-Eintrag muss den Portwert 5269 aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a4e89-p104">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="a4e89-121">Vergewissern Sie sich, dass in dem Edgepool, in dem der XMPP-Verbund jetzt gehostet wird, der Port 5269 für die externe Kommunikation geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="a4e89-121">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="a4e89-122">Starten Sie die Dienste auf allen Edgeservern in dem Edgepool, in dem der XMPP-Verbund jetzt gehostet wird:</span><span class="sxs-lookup"><span data-stu-id="a4e89-122">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

