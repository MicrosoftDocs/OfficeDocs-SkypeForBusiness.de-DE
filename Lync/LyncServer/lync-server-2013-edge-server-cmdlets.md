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
ms.openlocfilehash: 60081dc4d56c65e3cbef29a9231f855578d07054
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="edge-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="8c053-102">Edgeserver-Cmdlets in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c053-102">Edge Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c053-103">_**Letztes Änderungsstand des Themas:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="8c053-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="8c053-104">Edgeserver bieten Ihnen die Möglichkeit, die Funktionen von Microsoft lync Server 2013 auf Personen auszudehnen, die nicht bei Ihrem internen Netzwerk angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="8c053-104">Edge Servers provide a way for you to extend the capabilities of Microsoft Lync Server 2013 to people who are not logged on to your internal network.</span></span> <span data-ttu-id="8c053-105">Wenn Sie beispielsweise Remotebenutzer haben – authentifizierte Benutzer, die sich bei lync Server 2013 über das Internet anmelden, statt über das interne Netzwerk, müssen Sie eine Edgeserver einrichten, in der die lync Server Zugriffs-Edgedienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8c053-105">For example, if you have remote users -- authenticated users who log on to Lync Server 2013 over the Internet rather than through the internal network -- you will need to set up an Edge Server that runs the Lync Server Access Edge service.</span></span> <span data-ttu-id="8c053-106">Außerdem sind Edgeserver erforderlich, wenn Sie einen Partnerverbund mit einer anderen Organisation einrichten möchten oder Ihren Benutzern das Recht geben möchten, mit Personen zu kommunizieren, die über Konten mit einem öffentlichen Chatdienst wie Yahoo\!, AOL oder MSN verfügen.</span><span class="sxs-lookup"><span data-stu-id="8c053-106">Additionally, Edge Servers are required if you want to establish federation with another organization or if you want to give your users the right to communicate with people who have accounts with a public instant messaging service such as Yahoo\!, AOL, or MSN.</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="8c053-107">Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für neue oder erneuerte Verträge verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8c053-107">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="8c053-108">Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="8c053-108">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="8c053-109">Messenger, bis der Dienst das Datum heruntergefahren hat.</span><span class="sxs-lookup"><span data-stu-id="8c053-109">Messenger until the service shut down date.</span></span> <span data-ttu-id="8c053-110">Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="8c053-110">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="8c053-111">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="8c053-111">has been announced.</span></span> <span data-ttu-id="8c053-112">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8c053-112">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="8c053-113">Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server für die Zusammensetzung mit Yahoo! erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="8c053-113">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="8c053-114">Messenger.</span><span class="sxs-lookup"><span data-stu-id="8c053-114">Messenger.</span></span> <span data-ttu-id="8c053-115">Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die die Rückabwicklung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="8c053-115">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="8c053-116">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="8c053-116">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="8c053-117">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8c053-117">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="8c053-118">Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.</span><span class="sxs-lookup"><span data-stu-id="8c053-118">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<div>

## <a name="edge-server-cmdlets"></a><span data-ttu-id="8c053-119">Cmdlets für Edgeserver</span><span class="sxs-lookup"><span data-stu-id="8c053-119">Edge Server Cmdlets</span></span>

<span data-ttu-id="8c053-120">In der folgenden Liste werden Cmdlets aufgeführt, die im Rahmen der Edgeserververwaltung eingesetzt werden:</span><span class="sxs-lookup"><span data-stu-id="8c053-120">The following is a list of cmdlets that relate directly to managing Edge Servers:</span></span>

<span data-ttu-id="8c053-121">**Edgeserver**</span><span class="sxs-lookup"><span data-stu-id="8c053-121">**Edge Server**</span></span>

  - <span></span>  
    <span data-ttu-id="8c053-122">[Get-csaccessedgeconfiguration nicht angeben](https://technet.microsoft.com/library/Gg398574(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8c053-122">[Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8c053-123">[Gruppe-csaccessedgeconfiguration nicht angeben](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8c053-123">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8c053-124">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8c053-124">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8c053-125">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8c053-125">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8c053-126">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8c053-126">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="8c053-127">[Gruppe-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8c053-127">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8c053-128">[Test-csavedgeconnectivity "](https://technet.microsoft.com/library/JJ205138(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8c053-128">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="8c053-129">[Gruppe-CsEdgeServer](https://technet.microsoft.com/library/Gg398859(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8c053-129">[Set-CsEdgeServer](https://technet.microsoft.com/library/Gg398859(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8c053-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c053-130">See Also</span></span>


[<span data-ttu-id="8c053-131">Lync Server PowerShell-Blog</span><span class="sxs-lookup"><span data-stu-id="8c053-131">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

