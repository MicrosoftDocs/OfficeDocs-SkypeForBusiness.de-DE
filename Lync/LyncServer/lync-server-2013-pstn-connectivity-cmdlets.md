---
title: 'Lync Server 2013: Cmdlets für PSTN-Konnektivität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN connectivity cmdlets
ms:assetid: b19ba43c-3987-410d-a704-aba0a4fb0498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415670(v=OCS.15)
ms:contentKeyID: 48185142
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19d4ef9b42c57470ca5072b8a56d766a557e1101
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pstn-connectivity-cmdlets-in-lync-server-2013"></a>Cmdlets für PSTN-Konnektivität in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-09_

Eine Enterprise-VoIP-Lösung muss ein- und ausgehende PSTN-Anrufe (Public Switched Telephone Network, Telefonfestnetz) ermöglichen, ohne dass die Dienstqualität (Quality of Service, QoS) in irgendeiner Weise beeinträchtigt wird. Sie können diese Einstellungen über Cmdlets konfigurieren, die in der lync Server-Verwaltungsshell verfügbar sind.

<div>

## <a name="pstn-connectivity-cmdlets"></a>Cmdlets für die PSTN-Anbindung

Verwenden Sie die folgenden Cmdlets, um verschiedene Aspekte der PSTN-Anbindung zu konfigurieren.

**[Cmdlets für PSTN-Gateways in lync Server 2013](lync-server-2013-pstn-gateways-cmdlets.md)**

  - <span></span>  
    [Gruppe-CsPstnGateway](https://technet.microsoft.com/library/Gg398408(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsPstnOutboundCall](https://technet.microsoft.com/library/Gg398207(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/library/Gg398662(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Gruppe-csmediationserver begrenzen](https://technet.microsoft.com/library/Gg398213(v=OCS.15))

**[Cmdlets für statisches Routing in lync Server 2013](lync-server-2013-static-routing-cmdlets.md)**

  - <span></span>  
    [Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg398130(v=OCS.15))

  - <span></span>  
    [New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg413041(v=OCS.15))

  - <span></span>  
    [Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg412932(v=OCS.15))

  - <span></span>  
    [Gruppe-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg425895(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsStaticRoute](https://technet.microsoft.com/library/Gg398265(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398754(v=OCS.15))

  - <span></span>  
    [New-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg425811(v=OCS.15))

  - <span></span>  
    [Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398668(v=OCS.15))

  - <span></span>  
    [Gruppe-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398724(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyCustom](https://technet.microsoft.com/library/Gg425904(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyRealm](https://technet.microsoft.com/library/Gg413084(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyTCP](https://technet.microsoft.com/library/Gg425745(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyTLS](https://technet.microsoft.com/library/Gg398629(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyTransport](https://technet.microsoft.com/library/Gg398489(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyUseDefault](https://technet.microsoft.com/library/Gg398274(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyUseDefaultCert](https://technet.microsoft.com/library/Gg425858(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsIssuedCertId](https://technet.microsoft.com/library/Gg425814(v=OCS.15))

**[Cmdlets für die Trunking-Konfiguration in lync Server 2013](lync-server-2013-trunking-configuration-cmdlets.md)**

  - [Test-csintertrunkrouting "](https://technet.microsoft.com/library/JJ204741(v=OCS.15))

<!-- end list -->

  - [Get-csoutboundcallingnumbertranslationrule "](https://technet.microsoft.com/library/JJ204962(v=OCS.15))

  - [New-csoutboundcallingnumbertranslationrule "](https://technet.microsoft.com/library/JJ205097(v=OCS.15))

  - [Remove-csoutboundcallingnumbertranslationrule "](https://technet.microsoft.com/library/JJ204836(v=OCS.15))

  - [Gruppe-csoutboundcallingnumbertranslationrule "](https://technet.microsoft.com/library/JJ205400(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398104(v=OCS.15))

  - <span></span>  
    [New-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg412803(v=OCS.15))

  - <span></span>  
    [Remove-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398556(v=OCS.15))

  - <span></span>  
    [Gruppe-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg413073(v=OCS.15))

<!-- end list -->

  - [Get-cstrunk "](https://technet.microsoft.com/library/JJ205244(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398224(v=OCS.15))

  - <span></span>  
    [New-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg413021(v=OCS.15))

  - <span></span>  
    [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15))

  - <span></span>  
    [Gruppe-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398238(v=OCS.15))

  - <span></span>  
    [Test-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398137(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))

**[Cmdlets für das VoIP-Routing in lync Server 2013](lync-server-2013-voice-routing-cmdlets.md)**

  - <span></span>  
    [Get-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))

  - <span></span>  
    [New-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))

  - <span></span>  
    [Remove-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))

  - <span></span>  
    [Gruppe-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsVoiceRoute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))

  - <span></span>  
    [New-CsVoiceRoute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))

  - <span></span>  
    [Remove-CsVoiceRoute](https://technet.microsoft.com/library/Gg398468(v=OCS.15))

  - <span></span>  
    [Gruppe-CsVoiceRoute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))

  - <span></span>  
    [Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))

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

