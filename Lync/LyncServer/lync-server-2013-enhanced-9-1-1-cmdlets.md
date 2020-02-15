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
ms.openlocfilehash: 39ce5e70214f48aa9384a73b5138a789c29bc5c9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enhanced-9-1-1-cmdlets-in-lync-server-2013"></a>Erweiterte 9-1-1-Cmdlets in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-20_

Microsoft lync Server 2013 werden mit Cmdlets ausgeliefert, mit denen Sie die Enhanced 9-1-1 (E9-1-1)-Implementierung einer Enterprise-VoIP-Lösung implementieren und verwalten können. Verwenden Sie diese Cmdlets, um Verbindungspunkte physischen Adressen zuzuordnen und erforderliche Einstellungen für Enterprise-VoIP-Benutzer zu konfigurieren, damit Notrufe erfolgreich getätigt werden können und automatisch ein Standort an den Anbieter für die Notrufunterstützung gesendet wird. Sie können E9-1-1 nicht aus dem lync Server-Systemsteuerung konfigurieren, sondern Sie müssen Cmdlets verwenden.

<div>

## <a name="enhanced-9-1-1-cmdlets"></a>E9-1-1-Cmdlets

Verwenden Sie die folgenden Cmdlets zum Konfigurieren von E9-1-1.

**E9-1-1**

  - <span></span>  
    [Get-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg412877(v=OCS.15))

  - <span></span>  
    [Remove-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg425810(v=OCS.15))

  - <span></span>  
    [Gruppe-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg398620(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsLisCivicAddress](https://technet.microsoft.com/library/Gg398459(v=OCS.15))

  - <span></span>  
    [Test-CsLisCivicAddress](https://technet.microsoft.com/library/Gg425914(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Export-CsLisConfiguration](https://technet.microsoft.com/library/Gg398539(v=OCS.15))

  - <span></span>  
    [Import-CsLisConfiguration](https://technet.microsoft.com/library/Gg398380(v=OCS.15))

  - <span></span>  
    [Debug-CsLisConfiguration](https://technet.microsoft.com/library/Gg398710(v=OCS.15))

  - <span></span>  
    [Test-CsLisConfiguration](https://technet.microsoft.com/library/Gg398497(v=OCS.15))

  - <span></span>  
    [Veröffentlichen-CsLisConfiguration](https://technet.microsoft.com/library/Gg398364(v=OCS.15))

  - <span></span>  
    [Aufheben der Veröffentlichung-CsLisConfiguration](unhttps://technet.microsoft.com/library/Gg398364(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsLisLocation](https://technet.microsoft.com/library/Gg412834(v=OCS.15))

  - <span></span>  
    [Remove-CsLisLocation](https://technet.microsoft.com/library/Gg425722(v=OCS.15))

  - <span></span>  
    [Gruppe-CsLisLocation](https://technet.microsoft.com/library/Gg398757(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsLisPort](https://technet.microsoft.com/library/Gg398820(v=OCS.15))

  - <span></span>  
    [Remove-CsLisPort](https://technet.microsoft.com/library/Gg412899(v=OCS.15))

  - <span></span>  
    [Gruppe-CsLisPort](https://technet.microsoft.com/library/Gg398700(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsLisServiceProvider](https://technet.microsoft.com/library/Gg398116(v=OCS.15))

  - <span></span>  
    [Remove-CsLisServiceProvider](https://technet.microsoft.com/library/Gg398904(v=OCS.15))

  - <span></span>  
    [Gruppe-CsLisServiceProvider](https://technet.microsoft.com/library/Gg425911(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsLisSubnet](https://technet.microsoft.com/library/Gg398473(v=OCS.15))

  - <span></span>  
    [Remove-CsLisSubnet](https://technet.microsoft.com/library/Gg413053(v=OCS.15))

  - <span></span>  
    [Gruppe-CsLisSubnet](https://technet.microsoft.com/library/Gg399016(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsLisSwitch](https://technet.microsoft.com/library/Gg425769(v=OCS.15))

  - <span></span>  
    [Remove-CsLisSwitch](https://technet.microsoft.com/library/Gg398352(v=OCS.15))

  - <span></span>  
    [Gruppe-CsLisSwitch](https://technet.microsoft.com/library/Gg412823(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398117(v=OCS.15))

  - <span></span>  
    [Remove-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398461(v=OCS.15))

  - <span></span>  
    [Gruppe-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg412723(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsLocationPolicy](https://technet.microsoft.com/library/Gg398911(v=OCS.15))

  - <span></span>  
    [Grant-CsLocationPolicy](https://technet.microsoft.com/library/Gg413049(v=OCS.15))

  - <span></span>  
    [New-CsLocationPolicy](https://technet.microsoft.com/library/Gg398231(v=OCS.15))

  - <span></span>  
    [Remove-CsLocationPolicy](https://technet.microsoft.com/library/Gg398727(v=OCS.15))

  - <span></span>  
    [Gruppe-CsLocationPolicy](https://technet.microsoft.com/library/Gg412987(v=OCS.15))

  - <span></span>  
    [Test-CsLocationPolicy](https://technet.microsoft.com/library/Gg425962(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkSite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))

  - <span></span>  
    [New-CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))

  - <span></span>  
    [Remove-CsNetworkSite](https://technet.microsoft.com/library/Gg398135(v=OCS.15))

  - <span></span>  
    [Gruppe-CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Lync Server PowerShell-Blog](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

