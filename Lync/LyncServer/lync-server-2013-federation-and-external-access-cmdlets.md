---
title: 'Lync Server 2013: Cmdlets für den Verbund und den externen Zugriff'
description: 'Lync Server 2013: Cmdlets für den Verbund und den externen Zugriff.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Federation and external access cmdlets
ms:assetid: 4a384a57-257f-47a6-98d9-54cea2c647b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415651(v=OCS.15)
ms:contentKeyID: 48184018
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 930de66a54d3f8db07394baf2d8470affe5090e9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543391"
---
# <a name="federation-and-external-access-cmdlets-in-lync-server-2013"></a><span data-ttu-id="c563d-103">Cmdlets für den Verbund und den externen Zugriff in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c563d-103">Federation and external access cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c563d-104">_**Letztes Änderungsstand des Themas:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="c563d-104">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="c563d-105">Partnerverbund und externer Zugriff bieten zwei wichtige Funktionen: mit dem Verbund können Benutzer mit Personen außerhalb Ihrer Organisation kommunizieren, während der externe Zugriff Benutzern das Herstellen einer Verbindung mit Microsoft lync Server 2013 von außerhalb des internen Netzwerks ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="c563d-105">Federation and external access provide two important capabilities: federation enables users to communicate with people outside your organization, while external access enables users to connect to Microsoft Lync Server 2013 from outside the internal network.</span></span> <span data-ttu-id="c563d-106">Mit den verfügbaren Cmdlets für die Verwaltung von Verbund und externem Zugriff in lync Server 2013 können Sie bestimmen, mit wem Ihre Benutzer kommunizieren können (und können) und bestimmen, ob diese Benutzer eine Verbindung mit lync Server herstellen dürfen, ohne sich beim internen Netzwerk anmelden zu müssen.</span><span class="sxs-lookup"><span data-stu-id="c563d-106">The cmdlets available for managing federation and external access in Lync Server 2013 let you determine who your users can (and cannot) communicate with, and determine whether or not those users can connect to Lync Server without having to log on to the internal network.</span></span>

<div>

## <a name="federation-and-external-access-cmdlets"></a><span data-ttu-id="c563d-107">Cmdlets für Partnerverbund und externen Zugriff</span><span class="sxs-lookup"><span data-stu-id="c563d-107">Federation and External Access Cmdlets</span></span>

<span data-ttu-id="c563d-108">Die meisten Verwaltungsaufgaben, die für den Verbund und den externen Zugriff gelten, können in der lync Server-Systemsteuerung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c563d-108">Most management tasks that apply to federation and external access can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="c563d-109">Dieselben Aufgaben können mit Cmdlets aus dem lync Server-Verwaltungsshell oder in einem Skript ausgeführt werden; mit einem Skript können Sie bestimmte Aufgaben automatisieren.</span><span class="sxs-lookup"><span data-stu-id="c563d-109">These same tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script; using a script enables you to automate certain tasks.</span></span> <span data-ttu-id="c563d-110">Im folgenden finden Sie eine Liste der Cmdlets, die sich direkt auf die Verwaltung des Verbunds und des externen Zugriffs beziehen:</span><span class="sxs-lookup"><span data-stu-id="c563d-110">The following is a list of cmdlets that relate directly to managing federation and external access:</span></span>

  - <span></span>  
    <span data-ttu-id="c563d-111">[Get-CsAllowedDomain](https://technet.microsoft.com/library/Gg398164(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-111">[Get-CsAllowedDomain](https://technet.microsoft.com/library/Gg398164(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c563d-112">[New-CsAllowedDomain](https://technet.microsoft.com/library/Gg398628(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-112">[New-CsAllowedDomain](https://technet.microsoft.com/library/Gg398628(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c563d-113">[Remove-CsAllowedDomain](https://technet.microsoft.com/library/Gg398913(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-113">[Remove-CsAllowedDomain](https://technet.microsoft.com/library/Gg398913(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c563d-114">[Gruppe-CsAllowedDomain](https://technet.microsoft.com/library/Gg398931(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-114">[Set-CsAllowedDomain](https://technet.microsoft.com/library/Gg398931(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c563d-115">[Get-CsBlockedDomain](https://technet.microsoft.com/library/Gg398424(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-115">[Get-CsBlockedDomain](https://technet.microsoft.com/library/Gg398424(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c563d-116">[New-CsBlockedDomain](https://technet.microsoft.com/library/Gg398822(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-116">[New-CsBlockedDomain](https://technet.microsoft.com/library/Gg398822(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c563d-117">[Remove-CsBlockedDomain](https://technet.microsoft.com/library/Gg425832(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-117">[Remove-CsBlockedDomain](https://technet.microsoft.com/library/Gg425832(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c563d-118">[Gruppe-CsBlockedDomain](https://technet.microsoft.com/library/Gg398090(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-118">[Set-CsBlockedDomain](https://technet.microsoft.com/library/Gg398090(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c563d-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c563d-120">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425942(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-120">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425942(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c563d-121">[New-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398441(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-121">[New-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398441(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c563d-122">[Remove-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg399057(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-122">[Remove-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg399057(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c563d-123">[Gruppe-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398916(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-123">[Set-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398916(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c563d-124">[Get-csfipsconfiguration "](https://technet.microsoft.com/library/JJ204904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-124">[Get-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ204904(v=OCS.15))</span></span>

  - <span data-ttu-id="c563d-125">[New-csfipsconfiguration "](https://technet.microsoft.com/library/JJ205114(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-125">[New-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205114(v=OCS.15))</span></span>

  - <span data-ttu-id="c563d-126">[Remove-csfipsconfiguration "](https://technet.microsoft.com/library/JJ205201(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-126">[Remove-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205201(v=OCS.15))</span></span>

  - <span data-ttu-id="c563d-127">[Gruppe-csfipsconfiguration "](https://technet.microsoft.com/library/JJ205084(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-127">[Set-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205084(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c563d-128">[Disable-CsHostingProvider](https://technet.microsoft.com/library/Gg398481(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-128">[Disable-CsHostingProvider](https://technet.microsoft.com/library/Gg398481(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c563d-129">[Enable-CsHostingProvider](https://technet.microsoft.com/library/Gg398166(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-129">[Enable-CsHostingProvider](https://technet.microsoft.com/library/Gg398166(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c563d-130">[Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-130">[Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c563d-131">[New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-131">[New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c563d-132">[Remove-CsHostingProvider](https://technet.microsoft.com/library/Gg425809(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-132">[Remove-CsHostingProvider](https://technet.microsoft.com/library/Gg425809(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c563d-133">[Gruppe-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-133">[Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c563d-134">[Disable-CsPublicProvider](https://technet.microsoft.com/library/Gg398984(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-134">[Disable-CsPublicProvider](https://technet.microsoft.com/library/Gg398984(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c563d-135">[Enable-CsPublicProvider](https://technet.microsoft.com/library/Gg398780(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-135">[Enable-CsPublicProvider](https://technet.microsoft.com/library/Gg398780(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c563d-136">[Get-CsPublicProvider](https://technet.microsoft.com/library/Gg412945(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-136">[Get-CsPublicProvider](https://technet.microsoft.com/library/Gg412945(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c563d-137">[New-CsPublicProvider](https://technet.microsoft.com/library/Gg398161(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-137">[New-CsPublicProvider](https://technet.microsoft.com/library/Gg398161(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c563d-138">[Remove-CsPublicProvider](https://technet.microsoft.com/library/Gg412906(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-138">[Remove-CsPublicProvider](https://technet.microsoft.com/library/Gg412906(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c563d-139">[Gruppe-CsPublicProvider](https://technet.microsoft.com/library/Gg413087(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-139">[Set-CsPublicProvider](https://technet.microsoft.com/library/Gg413087(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c563d-140">[Test-CsFederatedPartner](https://technet.microsoft.com/library/Gg398281(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-140">[Test-CsFederatedPartner](https://technet.microsoft.com/library/Gg398281(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c563d-141">[Get-csxmppallowedpartner "](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-141">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span></span>

  - <span data-ttu-id="c563d-142">[New-csxmppallowedpartner "](https://technet.microsoft.com/library/JJ204631(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-142">[New-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204631(v=OCS.15))</span></span>

  - <span data-ttu-id="c563d-143">[Remove-csxmppallowedpartner "](https://technet.microsoft.com/library/JJ205055(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-143">[Remove-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ205055(v=OCS.15))</span></span>

  - <span data-ttu-id="c563d-144">[Gruppe-csxmppallowedpartner "](https://technet.microsoft.com/library/JJ204686(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-144">[Set-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204686(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c563d-145">[Get-csxmppgatewayconfiguration "stehen](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-145">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span></span>

  - <span data-ttu-id="c563d-146">[Gruppe-csxmppgatewayconfiguration "stehen](https://technet.microsoft.com/library/JJ204769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-146">[Set-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204769(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c563d-147">[Test-csxmppim "](https://technet.microsoft.com/library/JJ205423(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c563d-147">[Test-CsXmppIM](https://technet.microsoft.com/library/JJ205423(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c563d-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c563d-148">See Also</span></span>


[<span data-ttu-id="c563d-149">Lync Server PowerShell-Blog</span><span class="sxs-lookup"><span data-stu-id="c563d-149">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

