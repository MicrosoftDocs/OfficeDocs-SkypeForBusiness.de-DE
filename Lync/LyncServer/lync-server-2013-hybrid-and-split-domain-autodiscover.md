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
ms.openlocfilehash: 0340e1226d3fb7abc475769892f0cd675c838c89
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528162"
---
# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a><span data-ttu-id="4e99e-102">Hybrid-und Split-Domain-AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e99e-102">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e99e-103">_**Letztes Änderungsstand des Themas:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="4e99e-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="4e99e-104">Ein freigegebener SIP-Adressraum, auch bekannt als *geteilte Domänen* Bereitstellung oder *Hybrid* Bereitstellung, ist eine Konfiguration, in der Benutzer über eine lokale Bereitstellung und eine Online Umgebung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4e99e-104">A shared SIP address space, also known as a *split-domain* deployment, or a *hybrid* deployment, is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="4e99e-105">Das gewünschte Ergebnis besteht darin, dass ein Benutzer unabhängig davon, wo sich sein Heimatserver befindet (lokal oder Online), sich bei der Bereitstellung einloggt und zu seinem Standort umgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="4e99e-105">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="4e99e-106">Um dies zu erreichen, wird das Auto Ermittlungs Feature von lync Server 2013 verwendet, um den Online Benutzer zur Online Topologie umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="4e99e-106">To accomplish this, the Autodiscover feature of Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="4e99e-107">Sie können dies tun, indem Sie die URL (Uniform Resource Locator) der AutoErmittlung mithilfe der lync Server-Verwaltungsshell, des Cmdlets **Get-CsHostingProvider** und des Cmdlets **CsHostingProvider festlegen** konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4e99e-107">You can do this by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell, the **Get-CsHostingProvider** cmdlet, and the **Set-CsHostingProvider** cmdlet.</span></span>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="4e99e-108">Mobilität für die Bereitstellung geteilter Domänen</span><span class="sxs-lookup"><span data-stu-id="4e99e-108">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="4e99e-109">Sie müssen folgende bereitgestellte Attribute erfassen und aufzeichnen:</span><span class="sxs-lookup"><span data-stu-id="4e99e-109">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="4e99e-110">Geben Sie im lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="4e99e-110">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="4e99e-111">Suchen Sie in den Ergebnissen den Onlineanbieter mit dem Attribut **ProxyFQDN**.</span><span class="sxs-lookup"><span data-stu-id="4e99e-111">In the results, find the online provider with the attribute **ProxyFQDN**.</span></span> <span data-ttu-id="4e99e-112">Beispiel: sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4e99e-112">For example, sipfed.online.lync.com.</span></span>

  - <span data-ttu-id="4e99e-113">Notieren Sie den Wert des ProxyFQDN.</span><span class="sxs-lookup"><span data-stu-id="4e99e-113">Record the value of the ProxyFQDN.</span></span>

  - <span data-ttu-id="4e99e-114">Aktivieren Sie den Partnerverbund im lokalen lync Server-Systemsteuerung, sodass der Verbund mit dem Onlineanbieter zugelassen wird.</span><span class="sxs-lookup"><span data-stu-id="4e99e-114">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider.</span></span>

  - <span data-ttu-id="4e99e-115">Aktivieren Sie den Partnerverbund für den Onlineanbieter.</span><span class="sxs-lookup"><span data-stu-id="4e99e-115">Enable federation for the online provider.</span></span> <span data-ttu-id="4e99e-116">Standardmäßig sind alle Online Benutzer für den Domänen Verbund aktiviert und können mit allen Domänen kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="4e99e-116">By default, all online users are enabled for domain federation and can communicate with all domains.</span></span>

  - <span data-ttu-id="4e99e-117">Wenn Sie blockierte und zugelassene Domänen definieren, bestimmen Sie die Domänen, die Sie explizit zulassen oder explizit blockieren.</span><span class="sxs-lookup"><span data-stu-id="4e99e-117">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block.</span></span>

  - <span data-ttu-id="4e99e-118">Für den Online Verbund müssen Sie Firewall-Ausnahmen, Zertifikate und DNS-Hosteinträge (A oder AAAA, bei Verwendung von IPv6) planen.</span><span class="sxs-lookup"><span data-stu-id="4e99e-118">For online federation, you must plan for firewall exceptions, certificates, and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="4e99e-119">Außerdem müssen Sie Verbundrichtlinien konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4e99e-119">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="4e99e-120">Ausführliche Informationen finden Sie unter [Planung für lync Server 2013 und Office Communications Server Partnerverbund](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span><span class="sxs-lookup"><span data-stu-id="4e99e-120">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

