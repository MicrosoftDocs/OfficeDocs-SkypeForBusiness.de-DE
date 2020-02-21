---
title: 'Lync Server 2013: Cmdlets für Telefone und Geräte'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Phones and devices cmdlets
ms:assetid: 6ebeba4b-43ce-4a31-9060-50d249b7564c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415657(v=OCS.15)
ms:contentKeyID: 48184467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c28f1949e39d42b78173538b9f80df5812325c5a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phones-and-devices-cmdlets-in-lync-server-2013"></a>Cmdlets für Telefone und Geräte in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-28_

Microsoft lync Server 2013 enthält eine Reihe von Cmdlets, mit denen Sie Telefone und andere Hardwaregeräte verwalten können. Dies umfasst beispielsweise VoIP-Telefone (Voice over IP); Telefone in öffentlichen Bereichen (beispielsweise ein Telefon in einer Gebäude Lobby, eine Cafeteria oder ein anderer öffentlicher Standort); und sogar analoge Telefone, Telefone, die nicht in der Lage sind, lync Phone Edition auszuführen.

<div>

## <a name="phones-and-devices-cmdlets"></a>Cmdlets für Telefone und Geräte

Die **CsDeviceUpdate** -Cmdlets werden zum Verwalten des Geräte Update-Webdiensts, einer lync Server Komponente, die Administratoren das Verteilen von Firmware-Updates an Telefone und andere Geräte mit lync Phone Edition ermöglicht, verwendet.

  - <span></span>  
    [Get-CsAnalogDevice](https://technet.microsoft.com/library/Gg398748(v=OCS.15))

  - <span></span>  
    [CsAnalogDevice](https://technet.microsoft.com/library/Gg398816(v=OCS.15))

  - <span></span>  
    [New-CsAnalogDevice](https://technet.microsoft.com/library/Gg412937(v=OCS.15))

  - <span></span>  
    [Remove-CsAnalogDevice](rehttps://technet.microsoft.com/library/Gg398816(v=OCS.15))

  - <span></span>  
    [Gruppe-CsAnalogDevice](https://technet.microsoft.com/library/Gg412843(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg412934(v=OCS.15))

  - <span></span>  
    [CsCommonAreaPhone](https://technet.microsoft.com/library/Gg412837(v=OCS.15))

  - <span></span>  
    [New-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398430(v=OCS.15))

  - <span></span>  
    [Remove-CsCommonAreaPhone](rehttps://technet.microsoft.com/library/Gg412837(v=OCS.15))

  - <span></span>  
    [Gruppe-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398579(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398070(v=OCS.15))

  - <span></span>  
    [New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))

  - <span></span>  
    [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15))

  - <span></span>  
    [Gruppe-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg413042(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Import-CsDeviceUpdate](https://technet.microsoft.com/library/Gg398861(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg399030(v=OCS.15))

  - <span></span>  
    [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15))

  - <span></span>  
    [Remove-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425933(v=OCS.15))

  - <span></span>  
    [Gruppe-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Clear-CsDeviceUpdateFile](https://technet.microsoft.com/library/Gg425835(v=OCS.15))

  - <span></span>  
    [Clear-CsDeviceUpdateLog](https://technet.microsoft.com/library/Gg412738(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Genehmigen-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398949(v=OCS.15))

  - <span></span>  
    [Get-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398215(v=OCS.15))

  - <span></span>  
    [Remove-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg425930(v=OCS.15))

  - <span></span>  
    [Reset-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398181(v=OCS.15))

  - <span></span>  
    [Restore-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398305(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-csphonebootstrap aus](https://technet.microsoft.com/library/Gg412852(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsTestDevice](https://technet.microsoft.com/library/Gg398304(v=OCS.15))

  - <span></span>  
    [New-CsTestDevice](https://technet.microsoft.com/library/Gg425899(v=OCS.15))

  - <span></span>  
    [Remove-CsTestDevice](https://technet.microsoft.com/library/Gg398790(v=OCS.15))

  - <span></span>  
    [Gruppe-CsTestDevice](https://technet.microsoft.com/library/Gg398156(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Lync Server PowerShell-Blog](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

