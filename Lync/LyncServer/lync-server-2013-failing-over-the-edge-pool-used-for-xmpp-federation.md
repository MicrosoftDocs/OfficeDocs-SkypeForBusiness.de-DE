---
title: 'Lync Server 2013: Ausführen eines Failovers für den Edgepool, der für den XMPP-Partnerverbund verwendet wird'
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
ms.openlocfilehash: 9d1c76dc37ce1abb2d34c474d4144b0894d93a0f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="54121-102">Ausführen eines Failovers für den Edgepool in Lync Server 2013, der für den XMPP-Partnerverbund verwendet wird</span><span class="sxs-lookup"><span data-stu-id="54121-102">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54121-103">_**Letztes Änderungsdatum des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="54121-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="54121-104">In Ihrer Organisation gibt es einen Edge-Pool, der als Pool für XMPP-Föderationen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="54121-104">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="54121-105">Wenn dieser Pool ausfällt, müssen Sie die XMPP-Föderation nicht verwenden, um einen anderen Edge-Pool zu verwenden, bevor die XMPP-Föderation wieder funktionieren kann.</span><span class="sxs-lookup"><span data-stu-id="54121-105">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="54121-106">Wenn Sie Edge-Pools zum ersten Mal installieren und die XMPP-Föderation aktivieren, können Sie den Disaster Recovery-Prozess vereinfachen, indem Sie externe DNS-SRV-Einträge für alle Ihre Edge-Pools für XMPP Federation einrichten, und nicht nur eine.</span><span class="sxs-lookup"><span data-stu-id="54121-106">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="54121-107">Jeder dieser SRV-Einträge muss einen anderen Prioritäts Satz aufweisen.</span><span class="sxs-lookup"><span data-stu-id="54121-107">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="54121-108">Der gesamte XMPP-Verbunddatenverkehr durchläuft den Pool mit dem SRV-Eintrag mit der höchsten Priorität.</span><span class="sxs-lookup"><span data-stu-id="54121-108">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> <span data-ttu-id="54121-109">Weitere Informationen zum Aktivieren und Einrichten von XMPP Federation finden Sie unter [Einrichten von XMPP Federation in lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="54121-109">For more information on enabling and setting up XMPP federation, see [Setting up XMPP federation in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span></span>

<span data-ttu-id="54121-110">In der folgenden Vorgehensweise ist EdgePool1 der Pool, in dem die XMPP-Föderation ursprünglich gehostet wurde, und EdgePool2 ist der Pool, der nun XMPP-Föderation hostet.</span><span class="sxs-lookup"><span data-stu-id="54121-110">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="54121-111">Failover des für die XMPP-Föderation verwendeten Edge-Pools</span><span class="sxs-lookup"><span data-stu-id="54121-111">Failing Over the Edge Pool Used for XMPP Federation</span></span>

1.  <span data-ttu-id="54121-112">Wenn Sie noch keinen anderen Edge-Pool bereitgestellt haben (außer dem, der zurzeit nicht vorhanden ist), stellen Sie diesen Pool bereit.</span><span class="sxs-lookup"><span data-stu-id="54121-112">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> <span data-ttu-id="54121-113">Ausführliche Informationen finden Sie unter [Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="54121-113">For details, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

2.  <span data-ttu-id="54121-114">Führen Sie auf jedem Edgeserver des neuen Edge-Pools, in dem nun XMPP Federation (EdgePool2) gehostet wird, das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="54121-114">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="54121-115">Führen Sie das folgende Cmdlet aus, um die XMPP-Föderations Route auf EdgePool2 zu verweisen:</span><span class="sxs-lookup"><span data-stu-id="54121-115">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="54121-116">In diesem Beispiel ist site2 die Website, die den Edge-Pool enthält, auf dem nun die XMPP-Föderations Route gehostet wird, und EdgeServer2.contoso.com ist der FQDN eines Edgeserver in diesem Pool.</span><span class="sxs-lookup"><span data-stu-id="54121-116">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="54121-117">Ändern Sie auf dem externen DNS-Server den DNS-A-Eintrag für XMPP-Föderation, um auf EdgeServer2.contoso.com zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="54121-117">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="54121-118">Wenn Sie noch keinen DNS-SRV-Eintrag für die XMPP-Föderation haben, der in den Edge-Pool aufgelöst wird, der nun XMPP-Föderation hostet, müssen Sie ihn wie im folgenden Beispiel hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="54121-118">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="54121-119">Dieser SRV-Eintrag muss einen Portwert von 5269 aufweisen.</span><span class="sxs-lookup"><span data-stu-id="54121-119">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="54121-120">Überprüfen Sie, ob der Edge-Pool, auf dem nun der XMPP-Verbund gehostet wird, Port 5269 extern geöffnet hat.</span><span class="sxs-lookup"><span data-stu-id="54121-120">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="54121-121">Starten Sie die Dienste auf allen Edgeserver im Edge-Pool, die nun die XMPP-Föderation hosten:</span><span class="sxs-lookup"><span data-stu-id="54121-121">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

