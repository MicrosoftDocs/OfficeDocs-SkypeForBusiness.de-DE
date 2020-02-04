---
title: 'Lync Server 2013: Edgeserver-Cmdlets'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server cmdlets
ms:assetid: 1a5427f4-a0d1-4652-8135-91333158ffc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415635(v=OCS.15)
ms:contentKeyID: 48183534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d142bc2a98fbbb1d8147943e379ae1e1a243b18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="f99fb-102">Edge-Server-Cmdlets in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f99fb-102">Edge Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f99fb-103">_**Letztes Änderungsdatum des Themas:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="f99fb-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="f99fb-104">Edgeserver bieten Ihnen die Möglichkeit, die Funktionen von Microsoft lync Server 2013 auf Personen zu erweitern, die nicht bei Ihrem internen Netzwerk angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="f99fb-104">Edge Servers provide a way for you to extend the capabilities of Microsoft Lync Server 2013 to people who are not logged on to your internal network.</span></span> <span data-ttu-id="f99fb-105">Wenn Sie beispielsweise über Remotebenutzer-authentifizierte Benutzer verfügen, die sich bei lync Server 2013 über das Internet und nicht über das interne Netzwerk anmelden, müssen Sie einen Edgeserver einrichten, auf dem der lync Server Access-Edgedienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f99fb-105">For example, if you have remote users -- authenticated users who log on to Lync Server 2013 over the Internet rather than through the internal network -- you will need to set up an Edge Server that runs the Lync Server Access Edge service.</span></span> <span data-ttu-id="f99fb-106">Darüber hinaus sind Edgeserver erforderlich, wenn Sie einen Verbund mit einer anderen Organisation einrichten möchten oder wenn Sie Ihren Benutzern das Recht geben möchten, mit Personen zu kommunizieren, die über Konten bei einem öffentlichen Instant Messaging-\!Dienst wie Yahoo, AOL oder MSN verfügen.</span><span class="sxs-lookup"><span data-stu-id="f99fb-106">Additionally, Edge Servers are required if you want to establish federation with another organization or if you want to give your users the right to communicate with people who have accounts with a public instant messaging service such as Yahoo\!, AOL, or MSN.</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="f99fb-107">Ab dem 1. September, 2012, ist die Microsoft lync Public im Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für den Kauf von neuen oder erneuernden Vereinbarungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f99fb-107">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="f99fb-108">Kunden mit aktiven Lizenzen sind in der Lage, weiterhin mit Yahoo! zu verbünden</span><span class="sxs-lookup"><span data-stu-id="f99fb-108">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="f99fb-109">Messenger, bis der Dienst das Datum beendet hat.</span><span class="sxs-lookup"><span data-stu-id="f99fb-109">Messenger until the service shut down date.</span></span> <span data-ttu-id="f99fb-110">Datum des Endes des Lebenszyklus von Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="f99fb-110">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="f99fb-111">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="f99fb-111">has been announced.</span></span> <span data-ttu-id="f99fb-112">Ausführliche Informationen finden Sie <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">unter Unterstützung für öffentliche Instant Messenger-Konnektivität in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f99fb-112">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="f99fb-113">Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für die Föderation von lync Server oder Office Communications Server mit Yahoo! erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f99fb-113">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="f99fb-114">Messenger.</span><span class="sxs-lookup"><span data-stu-id="f99fb-114">Messenger.</span></span> <span data-ttu-id="f99fb-115">Die Möglichkeit von Microsoft, diesen Dienst bereitzustellen, war von der Unterstützung durch Yahoo! abhängig, deren zugrunde liegende Vereinbarung abgewickelt wird.</span><span class="sxs-lookup"><span data-stu-id="f99fb-115">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="f99fb-116">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen Organisationen und Personen in der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="f99fb-116">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="f99fb-117">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-und Gerätelizenzen außerhalb der lync-Standard CAL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f99fb-117">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="f99fb-118">Skype Federation wird dieser Liste hinzugefügt und ermöglicht es lync-Benutzern, Hunderte von Millionen von Personen mit Chat und Sprache zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="f99fb-118">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<div>

## <a name="edge-server-cmdlets"></a><span data-ttu-id="f99fb-119">Edgeserver-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="f99fb-119">Edge Server Cmdlets</span></span>

<span data-ttu-id="f99fb-120">Die folgende Liste enthält Cmdlets, die sich direkt auf die Verwaltung von Edge-Servern beziehen:</span><span class="sxs-lookup"><span data-stu-id="f99fb-120">The following is a list of cmdlets that relate directly to managing Edge Servers:</span></span>

<span data-ttu-id="f99fb-121">**Edgeserver**</span><span class="sxs-lookup"><span data-stu-id="f99fb-121">**Edge Server**</span></span>

  - <span></span>  
    <span data-ttu-id="f99fb-122">[Get-csaccessedgeconfiguration nicht angeben](https://technet.microsoft.com/en-us/library/Gg398574(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f99fb-122">[Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398574(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f99fb-123">[Satz-csaccessedgeconfiguration nicht angeben](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f99fb-123">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f99fb-124">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413008(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f99fb-124">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413008(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f99fb-125">[Neu – CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f99fb-125">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f99fb-126">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f99fb-126">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f99fb-127">[Satz-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f99fb-127">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f99fb-128">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/en-us/library/JJ205138(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f99fb-128">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/en-us/library/JJ205138(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f99fb-129">[Satz-CsEdgeServer](https://technet.microsoft.com/en-us/library/Gg398859(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f99fb-129">[Set-CsEdgeServer](https://technet.microsoft.com/en-us/library/Gg398859(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f99fb-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f99fb-130">See Also</span></span>


[<span data-ttu-id="f99fb-131">Lync Server PowerShell-Blog</span><span class="sxs-lookup"><span data-stu-id="f99fb-131">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

