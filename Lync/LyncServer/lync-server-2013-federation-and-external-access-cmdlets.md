---
title: 'Lync Server 2013: Cmdlets für den Verbund und den externen Zugriff'
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
ms.openlocfilehash: a125329cd7c76d5f5f8e40c4dae1dd78dcabc3dd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="federation-and-external-access-cmdlets-in-lync-server-2013"></a>Cmdlets für den Verbund und den externen Zugriff in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-26_

Partnerverbund und externer Zugriff bieten zwei wichtige Funktionen: mit dem Verbund können Benutzer mit Personen außerhalb Ihrer Organisation kommunizieren, während der externe Zugriff Benutzern das Herstellen einer Verbindung mit Microsoft lync Server 2013 von außerhalb des internen Netzwerks ermöglicht. Mit den verfügbaren Cmdlets für die Verwaltung von Verbund und externem Zugriff in lync Server 2013 können Sie bestimmen, mit wem Ihre Benutzer kommunizieren können (und können) und bestimmen, ob diese Benutzer eine Verbindung mit lync Server herstellen können, ohne sich bei der internen Anmeldung anmelden zu müssen. Netzwerk.

<div>

## <a name="federation-and-external-access-cmdlets"></a>Cmdlets für Partnerverbund und externen Zugriff

Die meisten Verwaltungsaufgaben, die für den Verbund und den externen Zugriff gelten, können in der lync Server-Systemsteuerung ausgeführt werden. Dieselben Aufgaben können mit Cmdlets aus dem lync Server-Verwaltungsshell oder in einem Skript ausgeführt werden; mit einem Skript können Sie bestimmte Aufgaben automatisieren. Im folgenden finden Sie eine Liste der Cmdlets, die sich direkt auf die Verwaltung des Verbunds und des externen Zugriffs beziehen:

  - <span></span>  
    [Get-CsAllowedDomain](https://technet.microsoft.com/library/Gg398164(v=OCS.15))

  - <span></span>  
    [New-CsAllowedDomain](https://technet.microsoft.com/library/Gg398628(v=OCS.15))

  - <span></span>  
    [Remove-CsAllowedDomain](https://technet.microsoft.com/library/Gg398913(v=OCS.15))

  - <span></span>  
    [Gruppe-CsAllowedDomain](https://technet.microsoft.com/library/Gg398931(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsBlockedDomain](https://technet.microsoft.com/library/Gg398424(v=OCS.15))

  - <span></span>  
    [New-CsBlockedDomain](https://technet.microsoft.com/library/Gg398822(v=OCS.15))

  - <span></span>  
    [Remove-CsBlockedDomain](https://technet.microsoft.com/library/Gg425832(v=OCS.15))

  - <span></span>  
    [Gruppe-CsBlockedDomain](https://technet.microsoft.com/library/Gg398090(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))

  - <span></span>  
    [Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425942(v=OCS.15))

  - <span></span>  
    [New-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398441(v=OCS.15))

  - <span></span>  
    [Remove-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg399057(v=OCS.15))

  - <span></span>  
    [Gruppe-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398916(v=OCS.15))

<!-- end list -->

  - [Get-csfipsconfiguration "](https://technet.microsoft.com/library/JJ204904(v=OCS.15))

  - [New-csfipsconfiguration "](https://technet.microsoft.com/library/JJ205114(v=OCS.15))

  - [Remove-csfipsconfiguration "](https://technet.microsoft.com/library/JJ205201(v=OCS.15))

  - [Gruppe-csfipsconfiguration "](https://technet.microsoft.com/library/JJ205084(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable-CsHostingProvider](https://technet.microsoft.com/library/Gg398481(v=OCS.15))

  - <span></span>  
    [Enable-CsHostingProvider](https://technet.microsoft.com/library/Gg398166(v=OCS.15))

  - <span></span>  
    [Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))

  - <span></span>  
    [New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))

  - <span></span>  
    [Remove-CsHostingProvider](https://technet.microsoft.com/library/Gg425809(v=OCS.15))

  - <span></span>  
    [Gruppe-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable-CsPublicProvider](https://technet.microsoft.com/library/Gg398984(v=OCS.15))

  - <span></span>  
    [Enable-CsPublicProvider](https://technet.microsoft.com/library/Gg398780(v=OCS.15))

  - <span></span>  
    [Get-CsPublicProvider](https://technet.microsoft.com/library/Gg412945(v=OCS.15))

  - <span></span>  
    [New-CsPublicProvider](https://technet.microsoft.com/library/Gg398161(v=OCS.15))

  - <span></span>  
    [Remove-CsPublicProvider](https://technet.microsoft.com/library/Gg412906(v=OCS.15))

  - <span></span>  
    [Gruppe-CsPublicProvider](https://technet.microsoft.com/library/Gg413087(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsFederatedPartner](https://technet.microsoft.com/library/Gg398281(v=OCS.15))

<!-- end list -->

  - [Get-csxmppallowedpartner "](https://technet.microsoft.com/library/JJ204981(v=OCS.15))

  - [New-csxmppallowedpartner "](https://technet.microsoft.com/library/JJ204631(v=OCS.15))

  - [Remove-csxmppallowedpartner "](https://technet.microsoft.com/library/JJ205055(v=OCS.15))

  - [Gruppe-csxmppallowedpartner "](https://technet.microsoft.com/library/JJ204686(v=OCS.15))

<!-- end list -->

  - [Get-csxmppgatewayconfiguration "stehen](https://technet.microsoft.com/library/JJ204869(v=OCS.15))

  - [Gruppe-csxmppgatewayconfiguration "stehen](https://technet.microsoft.com/library/JJ204769(v=OCS.15))

<!-- end list -->

  - [Test-csxmppim "](https://technet.microsoft.com/library/JJ205423(v=OCS.15))

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

