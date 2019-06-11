---
title: 'Lync Server 2013: Konferenz-Cmdlets'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferencing cmdlets
ms:assetid: 7ff94637-6319-4c45-9230-be34e8d81ede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398641(v=OCS.15)
ms:contentKeyID: 48184640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bd951904e14d864c165ff98c50088b96e42f04f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-cmdlets-in-lync-server-2013"></a>Konferenz-Cmdlets in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-09_

Microsoft lync Server 2013 ermöglicht Benutzern die Teilnahme an Konferenzen auf zwei verschiedene Arten: mithilfe einer Konferenz Anwendung wie lync 2013 oder durch Einwählen über ein Telefon. Einwahlbenutzer sind nicht in der Lage, solche Dinge wie das Anzeigen von Folien oder das Austauschen von Sofortnachrichten zu tun, Sie können jedoch in vollem Umfang am Audioteil einer Konferenz teilnehmen.

<div>

## <a name="conferencing-cmdlets"></a>Konferenz-Cmdlets

Die **CsDialInConferencing** -Cmdlets werden verwendet, um die Eigenschaften von Einwahlkonferenzen zu konfigurieren, einschließlich aller von der Angabe der Telefonnummern, die Benutzer anrufen können, um an einer Konferenz teilzunehmen, um die für Sie verfügbaren Tastenkombinationen anzuzeigen, nachdem Sie an einer Konferenz (beispielsweisedurch Drücken von 6, um Ihr Telefon stummzuschalten oder die Stummschaltung aufzuheben). Die meisten anderen Features einer Konferenz (beispielsweise können Benutzer die Konferenz aufzeichnen, können Benutzer während der Konferenzanwendungen freigeben usw.) werden mithilfe der **CsConferencingPolicy** -Cmdlets verwaltet.

**[Cmdlets für Einwahlkonferenzen in lync Server 2013](lync-server-2013-dial-in-conferencing-cmdlets.md)**

  - <span></span>  
    [Get-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg425771(v=OCS.15))

  - <span></span>  
    [Move-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))

  - <span></span>  
    [New-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg413080(v=OCS.15))

  - <span></span>  
    [Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsDialInConferencing](https://technet.microsoft.com/en-us/library/Gg399013(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg413015(v=OCS.15))

  - <span></span>  
    [New-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg398818(v=OCS.15))

  - <span></span>  
    [Remove-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg412782(v=OCS.15))

  - <span></span>  
    [Set-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg425770(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398575(v=OCS.15))

  - <span></span>  
    [New-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412816(v=OCS.15))

  - <span></span>  
    [Remove-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398174(v=OCS.15))

  - <span></span>  
    [Set-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg425825(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398578(v=OCS.15))

  - <span></span>  
    [New-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425792(v=OCS.15))

  - <span></span>  
    [Remove-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425894(v=OCS.15))

  - <span></span>  
    [Set-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398860(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDialInConferencingLanguageList](https://technet.microsoft.com/en-us/library/Gg425869(v=OCS.15))

**[Webkonferenz-Cmdlets in lync Server 2013](lync-server-2013-web-conferencing-cmdlets.md)**

  - <span></span>  
    [Get-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425714(v=OCS.15))

  - <span></span>  
    [Remove-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398243(v=OCS.15))

  - <span></span>  
    [Satz-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398776(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Satz-CsConferenceServer](https://technet.microsoft.com/en-us/library/Gg398738(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398965(v=OCS.15))

  - <span></span>  
    [New-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412967(v=OCS.15))

  - <span></span>  
    [Remove-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412767(v=OCS.15))

  - <span></span>  
    [Set-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412969(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398293(v=OCS.15))

  - <span></span>  
    [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425937(v=OCS.15))

  - <span></span>  
    [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg413019(v=OCS.15))

  - <span></span>  
    [Remove-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398728(v=OCS.15))

  - <span></span>  
    [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425788(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg425875(v=OCS.15))

  - <span></span>  
    [New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15))

  - <span></span>  
    [Remove-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15))

  - <span></span>  
    [Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398648(v=OCS.15))

<!-- end list -->

  - [Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204723(v=OCS.15))

  - [Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205062(v=OCS.15))

  - [Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205277(v=OCS.15))

  - [Move-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204889(v=OCS.15))

  - [Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204831(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsASConference](https://technet.microsoft.com/en-us/library/JJ205227(v=OCS.15))

  - <span></span>  
    [Test-CsAVConference](https://technet.microsoft.com/en-us/library/Gg412749(v=OCS.15))

  - <span></span>  
    [Test-CsDataConference](https://technet.microsoft.com/en-us/library/JJ205219(v=OCS.15))

  - <span></span>  
    [Test-CsWebApp](https://technet.microsoft.com/en-us/library/Hh689989(v=OCS.15))

  - <span></span>  
    [Test-CsWebAppAnonymous](https://technet.microsoft.com/en-us/library/Hh690041(v=OCS.15))

  - <span></span>  
    [Test-CsWebScheduler](https://technet.microsoft.com/en-us/library/JJ204829(v=OCS.15))

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

