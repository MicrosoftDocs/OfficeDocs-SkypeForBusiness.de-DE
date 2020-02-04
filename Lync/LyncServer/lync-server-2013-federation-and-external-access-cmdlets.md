---
title: 'Lync Server 2013: Cmdlets für Föderation und externen Zugriff'
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
ms.openlocfilehash: b206d8de27f2cdeebab5db0c125012c2a29c65b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="federation-and-external-access-cmdlets-in-lync-server-2013"></a>Cmdlets für Föderations-und externen Zugriff in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-26_

Föderation und externer Zugriff bieten zwei wichtige Funktionen: mithilfe der Föderation können Benutzer mit Personen außerhalb Ihrer Organisation kommunizieren, während der externe Zugriff Benutzern die Verbindung mit Microsoft lync Server 2013 von außerhalb des internen Netzwerks ermöglicht. Die für die Verwaltung des Föderations-und externen Zugriffs in lync Server 2013 verfügbaren Cmdlets ermöglichen Ihnen, festzustellen, mit wem Ihre Benutzer kommunizieren können (und können), und ermitteln, ob diese Benutzer eine Verbindung mit lync Server herstellen können, ohne sich beim internen anmelden zu müssen. Netzwerk.

<div>

## <a name="federation-and-external-access-cmdlets"></a>Cmdlets für Föderation und externen Zugriff

Die meisten Verwaltungsaufgaben, die für den Verbund und den externen Zugriff gelten, können über die lync Server-Systemsteuerung ausgeführt werden. Dieselben Aufgaben können mit Cmdlets aus der lync Server-Verwaltungsshell oder in einem Skript ausgeführt werden. durch die Verwendung eines Skripts können Sie bestimmte Aufgaben automatisieren. Die folgende Liste enthält Cmdlets, die sich direkt auf die Verwaltung des Föderations-und des externen Zugriffs beziehen:

  - <span></span>  
    [Get-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398164(v=OCS.15))

  - <span></span>  
    [Neu – CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398628(v=OCS.15))

  - <span></span>  
    [Remove-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398913(v=OCS.15))

  - <span></span>  
    [Satz-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398931(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398424(v=OCS.15))

  - <span></span>  
    [Neu – CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398822(v=OCS.15))

  - <span></span>  
    [Remove-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg425832(v=OCS.15))

  - <span></span>  
    [Satz-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398090(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))

  - <span></span>  
    [Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425942(v=OCS.15))

  - <span></span>  
    [Neu – CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398441(v=OCS.15))

  - <span></span>  
    [Remove-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg399057(v=OCS.15))

  - <span></span>  
    [Satz-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398916(v=OCS.15))

<!-- end list -->

  - [Get-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ204904(v=OCS.15))

  - [New-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205114(v=OCS.15))

  - [Remove-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205201(v=OCS.15))

  - [Set-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205084(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Deaktivieren-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398481(v=OCS.15))

  - <span></span>  
    [Enable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398166(v=OCS.15))

  - <span></span>  
    [Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))

  - <span></span>  
    [Neu – CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))

  - <span></span>  
    [Remove-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg425809(v=OCS.15))

  - <span></span>  
    [Satz-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Deaktivieren-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398984(v=OCS.15))

  - <span></span>  
    [Enable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398780(v=OCS.15))

  - <span></span>  
    [Get-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412945(v=OCS.15))

  - <span></span>  
    [Neu – CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398161(v=OCS.15))

  - <span></span>  
    [Remove-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412906(v=OCS.15))

  - <span></span>  
    [Satz-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg413087(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsFederatedPartner](https://technet.microsoft.com/en-us/library/Gg398281(v=OCS.15))

<!-- end list -->

  - [Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))

  - [New-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204631(v=OCS.15))

  - [Remove-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ205055(v=OCS.15))

  - [Set-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204686(v=OCS.15))

<!-- end list -->

  - [Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))

  - [Set-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204769(v=OCS.15))

<!-- end list -->

  - [Test-CsXmppIM](https://technet.microsoft.com/en-us/library/JJ205423(v=OCS.15))

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

