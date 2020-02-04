---
title: 'Lync Server 2013: Erweiterte 9-1-1-Cmdlets'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enhanced 9-1-1 cmdlets
ms:assetid: e560c688-7b34-4bd7-8104-24f390644105
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415678(v=OCS.15)
ms:contentKeyID: 48185650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59b626f05bdbb2d8a93f23f2f5afdb3cc03e07b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enhanced-9-1-1-cmdlets-in-lync-server-2013"></a><span data-ttu-id="35a62-102">Erweiterte 9-1-1-Cmdlets in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35a62-102">Enhanced 9-1-1 cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35a62-103">_**Letztes Änderungsdatum des Themas:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="35a62-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="35a62-104">Microsoft lync Server 2013 wird mit Cmdlets ausgeliefert, mit denen Sie die erweiterte 9-1-1-Implementierung (E9-1-1) einer Enterprise-VoIP-Lösung implementieren und verwalten können.</span><span class="sxs-lookup"><span data-stu-id="35a62-104">Microsoft Lync Server 2013 ships with cmdlets that allow you to implement and manage the Enhanced 9-1-1 (E9-1-1) implementation of an Enterprise Voice solution.</span></span> <span data-ttu-id="35a62-105">Verwenden Sie diese Cmdlets, um Verbindungspunkte zu physikalischen Adressen zuzuordnen und Einstellungen zu konfigurieren, die für Enterprise-VoIP-Benutzer erforderlich sind, um Notrufe erfolgreich abzuschließen und automatisch einen Standort an den Notrufdienst Anbieter zu senden.</span><span class="sxs-lookup"><span data-stu-id="35a62-105">Use these cmdlets to map connection points to physical addresses and to configure settings required for Enterprise Voice users to successfully complete emergency calls and automatically send a location to the emergency services provider.</span></span> <span data-ttu-id="35a62-106">Sie können E9-1-1 nicht über die lync Server-Systemsteuerung konfigurieren, sondern müssen Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="35a62-106">You cannot configure E9-1-1 from the Lync Server Control Panel, you must use cmdlets.</span></span>

<div>

## <a name="enhanced-9-1-1-cmdlets"></a><span data-ttu-id="35a62-107">Erweiterte 9-1-1-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="35a62-107">Enhanced 9-1-1 Cmdlets</span></span>

<span data-ttu-id="35a62-108">Verwenden Sie die folgenden Cmdlets, um E9-1-1 zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="35a62-108">Use the following cmdlets to configure E9-1-1.</span></span>

<span data-ttu-id="35a62-109">**Enhanced 9-1-1**</span><span class="sxs-lookup"><span data-stu-id="35a62-109">**Enhanced 9-1-1**</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-110">[Get-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg412877(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-110">[Get-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg412877(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-111">[Remove-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425810(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-111">[Remove-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425810(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-112">[Satz-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398620(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-112">[Set-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398620(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="35a62-113">[Get-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg398459(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-113">[Get-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg398459(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-114">[Test-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg425914(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-114">[Test-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg425914(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="35a62-115">[Export-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398539(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-115">[Export-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398539(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-116">[Import-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398380(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-116">[Import-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398380(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-117">[Debug-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398710(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-117">[Debug-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398710(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-118">[Test-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398497(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-118">[Test-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398497(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-119">[Publish-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-119">[Publish-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-120">[Unpublish-CsLisConfiguration](unhttps://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-120">[Unpublish-CsLisConfiguration](unhttps://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="35a62-121">[Get-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg412834(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-121">[Get-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg412834(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-122">[Remove-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg425722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-122">[Remove-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg425722(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-123">[Satz-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg398757(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-123">[Set-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg398757(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="35a62-124">[Get-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-124">[Get-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398820(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-125">[Remove-CsLisPort](https://technet.microsoft.com/en-us/library/Gg412899(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-125">[Remove-CsLisPort](https://technet.microsoft.com/en-us/library/Gg412899(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-126">[Satz-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398700(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-126">[Set-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398700(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="35a62-127">[Get-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398116(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-127">[Get-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398116(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-128">[Remove-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-128">[Remove-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398904(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-129">[Satz-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg425911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-129">[Set-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg425911(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="35a62-130">[Get-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg398473(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-130">[Get-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg398473(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-131">[Remove-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg413053(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-131">[Remove-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg413053(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-132">[Satz-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg399016(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-132">[Set-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg399016(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="35a62-133">[Get-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg425769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-133">[Get-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg425769(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-134">[Remove-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg398352(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-134">[Remove-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg398352(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-135">[Satz-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg412823(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-135">[Set-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg412823(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="35a62-136">[Get-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398117(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-136">[Get-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398117(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-137">[Remove-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398461(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-137">[Remove-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398461(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-138">[Satz-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg412723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-138">[Set-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg412723(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="35a62-139">[Get-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-139">[Get-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398911(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-140">[Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg413049(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-140">[Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg413049(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-141">[Neu – CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398231(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-141">[New-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398231(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-142">[Remove-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398727(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-142">[Remove-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398727(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-143">[Satz-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg412987(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-143">[Set-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg412987(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-144">[Test-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg425962(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-144">[Test-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg425962(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="35a62-145">[Get-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-145">[Get-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-146">[New-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-146">[New-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-147">[Remove-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-147">[Remove-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="35a62-148">[Set-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="35a62-148">[Set-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="35a62-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35a62-149">See Also</span></span>


[<span data-ttu-id="35a62-150">Lync Server PowerShell-Blog</span><span class="sxs-lookup"><span data-stu-id="35a62-150">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

