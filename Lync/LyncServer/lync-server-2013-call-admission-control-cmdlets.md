---
title: 'Lync Server 2013: Cmdlets für die Anrufsteuerung'
description: 'Lync Server 2013: Cmdlets für die Anrufsteuerung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control cmdlets
ms:assetid: dd9d3912-b562-4839-a337-bfc5277cfb62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415676(v=OCS.15)
ms:contentKeyID: 48185602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d841273ef57c53b5bfa70ca5f2e54e679f70b7a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569201"
---
# <a name="call-admission-control-cmdlets-in-lync-server-2013"></a>Cmdlets für die Anrufsteuerung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-03-21_

Die Anrufsteuerung (Call Admission Control, CAC) ermittelt, ob ausreichend Netzwerkbandbreite für eine in Echtzeit durchgeführte Audio- oder Videositzung in akzeptabler Qualität vorhanden ist. Sie verwalten die Anrufsteuerung, indem Sie Einschränkungen und Einstellungen für Netzwerke, Standorte und Subnetze sowie die Interaktion zwischen diesen Komponenten konfigurieren.

<div>

## <a name="call-admission-control-cmdlets"></a>Cmdlets für die Anrufsteuerung

Verwenden Sie die folgenden Cmdlets zum Verwalten der Anrufsteuerung aus dem lync Server-Verwaltungsshell.

**Anrufsteuerung**

  - <span></span>  
    [Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412727(v=OCS.15))

  - <span></span>  
    [New-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398175(v=OCS.15))

  - <span></span>  
    [Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398877(v=OCS.15))

  - <span></span>  
    [Gruppe-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412863(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg425815(v=OCS.15))

  - <span></span>  
    [New-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398675(v=OCS.15))

  - <span></span>  
    [Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398609(v=OCS.15))

  - <span></span>  
    [Gruppe-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398338(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsNetworkBWAlternatePath](https://technet.microsoft.com/library/Gg398732(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsNetworkBWPolicy](https://technet.microsoft.com/library/Gg412916(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398140(v=OCS.15))

  - <span></span>  
    [Remove-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398938(v=OCS.15))

  - <span></span>  
    [Gruppe-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398927(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg425817(v=OCS.15))

  - <span></span>  
    [New-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398779(v=OCS.15))

  - <span></span>  
    [Remove-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398743(v=OCS.15))

  - <span></span>  
    [Gruppe-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398410(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg412769(v=OCS.15))

  - <span></span>  
    [New-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398994(v=OCS.15))

  - <span></span>  
    [Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398963(v=OCS.15))

  - <span></span>  
    [Gruppe-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398772(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkRegion](https://technet.microsoft.com/library/Gg398406(v=OCS.15))

  - <span></span>  
    [New-CsNetworkRegion](https://technet.microsoft.com/library/Gg425829(v=OCS.15))

  - <span></span>  
    [Remove-CsNetworkRegion](https://technet.microsoft.com/library/Gg398466(v=OCS.15))

  - <span></span>  
    [Gruppe-CsNetworkRegion](https://technet.microsoft.com/library/Gg413089(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398972(v=OCS.15))

  - <span></span>  
    [New-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398437(v=OCS.15))

  - <span></span>  
    [Remove-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg413012(v=OCS.15))

  - <span></span>  
    [Gruppe-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg412867(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkSite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))

  - <span></span>  
    [New-CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))

  - <span></span>  
    [Remove-CsNetworkSite](https://technet.microsoft.com/library/Gg398135(v=OCS.15))

  - <span></span>  
    [Gruppe-CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412825(v=OCS.15))

  - <span></span>  
    [New-CsNetworkSubnet](https://technet.microsoft.com/library/Gg398226(v=OCS.15))

  - <span></span>  
    [Remove-CsNetworkSubnet](https://technet.microsoft.com/library/Gg425726(v=OCS.15))

  - <span></span>  
    [Gruppe-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412739(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Übersicht über die Anrufsteuerung in lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)  


[Lync Server PowerShell-Blog](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

