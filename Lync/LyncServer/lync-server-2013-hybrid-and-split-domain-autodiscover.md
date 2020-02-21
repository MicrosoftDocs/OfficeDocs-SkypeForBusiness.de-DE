---
title: 'Lync Server 2013: Hybrid-und Split-Domain-AutoErmittlung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hybrid and split-domain - Autodiscover
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945652(v=OCS.15)
ms:contentKeyID: 51541520
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fca0097f6ad0264755dd9d0a80a296e9ebf60b9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a><span data-ttu-id="b7bd0-102">Hybrid-und Split-Domain-AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7bd0-102">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7bd0-103">_**Letztes Änderungsstand des Themas:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="b7bd0-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="b7bd0-104">Ein freigegebener SIP-Adressraum, auch bekannt als *geteilte Domänen* Bereitstellung oder *Hybrid* Bereitstellung, ist eine Konfiguration, in der Benutzer über eine lokale Bereitstellung und eine Online Umgebung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b7bd0-104">A shared SIP address space, also known as a *split-domain* deployment, or a *hybrid* deployment, is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="b7bd0-105">Das gewünschte Ergebnis besteht darin, dass ein Benutzer unabhängig davon, wo sich sein Heimatserver befindet (lokal oder Online), sich bei der Bereitstellung einloggt und zu seinem Standort umgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="b7bd0-105">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="b7bd0-106">Um dies zu erreichen, wird das Auto Ermittlungs Feature von lync Server 2013 verwendet, um den Online Benutzer zur Online Topologie umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="b7bd0-106">To accomplish this, the Autodiscover feature of Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="b7bd0-107">Sie können dies tun, indem Sie die URL (Uniform Resource Locator) der AutoErmittlung mithilfe der lync Server-Verwaltungsshell, des Cmdlets **Get-CsHostingProvider** und des Cmdlets **CsHostingProvider festlegen** konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b7bd0-107">You can do this by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell, the **Get-CsHostingProvider** cmdlet, and the **Set-CsHostingProvider** cmdlet.</span></span>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="b7bd0-108">Mobilität für die Bereitstellung geteilter Domänen</span><span class="sxs-lookup"><span data-stu-id="b7bd0-108">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="b7bd0-109">Sie müssen folgende bereitgestellte Attribute erfassen und aufzeichnen:</span><span class="sxs-lookup"><span data-stu-id="b7bd0-109">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="b7bd0-110">Geben Sie im lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="b7bd0-110">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="b7bd0-111">Suchen Sie in den Ergebnissen den Onlineanbieter mit dem Attribut **ProxyFQDN**.</span><span class="sxs-lookup"><span data-stu-id="b7bd0-111">In the results, find the online provider with the attribute **ProxyFQDN**.</span></span> <span data-ttu-id="b7bd0-112">Beispiel: sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b7bd0-112">For example, sipfed.online.lync.com.</span></span>

  - <span data-ttu-id="b7bd0-113">Notieren Sie den Wert des ProxyFQDN.</span><span class="sxs-lookup"><span data-stu-id="b7bd0-113">Record the value of the ProxyFQDN.</span></span>

  - <span data-ttu-id="b7bd0-114">Aktivieren Sie den Partnerverbund im lokalen lync Server-Systemsteuerung, sodass der Verbund mit dem Onlineanbieter zugelassen wird.</span><span class="sxs-lookup"><span data-stu-id="b7bd0-114">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider.</span></span>

  - <span data-ttu-id="b7bd0-115">Aktivieren Sie den Partnerverbund für den Onlineanbieter.</span><span class="sxs-lookup"><span data-stu-id="b7bd0-115">Enable federation for the online provider.</span></span> <span data-ttu-id="b7bd0-116">Standardmäßig sind alle Online Benutzer für den Domänen Verbund aktiviert und können mit allen Domänen kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="b7bd0-116">By default, all online users are enabled for domain federation and can communicate with all domains.</span></span>

  - <span data-ttu-id="b7bd0-117">Wenn Sie blockierte und zugelassene Domänen definieren, bestimmen Sie die Domänen, die Sie explizit zulassen oder explizit blockieren.</span><span class="sxs-lookup"><span data-stu-id="b7bd0-117">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block.</span></span>

  - <span data-ttu-id="b7bd0-118">Für den Online Verbund müssen Sie Firewall-Ausnahmen, Zertifikate und DNS-Hosteinträge (A oder AAAA, bei Verwendung von IPv6) planen.</span><span class="sxs-lookup"><span data-stu-id="b7bd0-118">For online federation, you must plan for firewall exceptions, certificates, and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="b7bd0-119">Außerdem müssen Sie Verbundrichtlinien konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b7bd0-119">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="b7bd0-120">Ausführliche Informationen finden Sie unter [Planung für lync Server 2013 und Office Communications Server Partnerverbund](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span><span class="sxs-lookup"><span data-stu-id="b7bd0-120">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

