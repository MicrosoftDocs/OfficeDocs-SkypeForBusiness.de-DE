---
title: 'Lync Server 2013: Konferenz-Cmdlets'
description: 'Lync Server 2013: Konferenz-Cmdlets.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing cmdlets
ms:assetid: 7ff94637-6319-4c45-9230-be34e8d81ede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398641(v=OCS.15)
ms:contentKeyID: 48184640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b7cd9843c971d5bf8611c4e64548b2ff608f1b0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561181"
---
# <a name="conferencing-cmdlets-in-lync-server-2013"></a>Konferenz-Cmdlets in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-09_

Microsoft lync Server 2013 ermöglicht Benutzern die Teilnahme an Konferenzen auf zwei verschiedene Arten: indem Sie eine Konferenz Anwendung wie lync 2013 verwenden oder sich über ein Telefon einwählen. Benutzer, die per Einwahl an einer Konferenz teilnehmen, können Funktionen wie die Anzeige von Folien oder den Austausch von Sofortnachrichten nicht nutzen, sie können jedoch am Audioteil einer Konferenz vollständig teilnehmen.

<div>

## <a name="conferencing-cmdlets"></a>Cmdlets für Konferenzen

Die **CsDialInConferencing** -Cmdlets werden verwendet, um die Eigenschaften von Einwahlkonferenzen zu konfigurieren, einschließlich der Angabe der Telefonnummern, die Benutzer anrufen können, um einer Konferenz an den Tastenbefehlen für die Teilnahme an einer Konferenz teilzunehmen (beispielsweise 6 drücken, um das Telefon stummzuschalten oder stummzuschalten). Die meisten anderen Features einer Konferenz (beispielsweise können Benutzer die Konferenz aufzeichnen, können Benutzer Anwendungen während der Konferenz freigeben usw.) werden mithilfe der **CsConferencingPolicy** -Cmdlets verwaltet.

**[Cmdlets für Einwahlkonferenzen in lync Server 2013](lync-server-2013-dial-in-conferencing-cmdlets.md)**

  - <span></span>  
    [Get-CsConferenceDirectory](https://technet.microsoft.com/library/Gg425771(v=OCS.15))

  - <span></span>  
    [CsConferenceDirectory](https://technet.microsoft.com/library/Gg412968(v=OCS.15))

  - <span></span>  
    [New-CsConferenceDirectory](https://technet.microsoft.com/library/Gg413080(v=OCS.15))

  - <span></span>  
    [Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/library/Gg412968(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsDialInConferencing](https://technet.microsoft.com/library/Gg399013(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg413015(v=OCS.15))

  - <span></span>  
    [New-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg398818(v=OCS.15))

  - <span></span>  
    [Remove-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg412782(v=OCS.15))

  - <span></span>  
    [Gruppe-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg425770(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398575(v=OCS.15))

  - <span></span>  
    [New-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg412816(v=OCS.15))

  - <span></span>  
    [Remove-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398174(v=OCS.15))

  - <span></span>  
    [Gruppe-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg425825(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg398578(v=OCS.15))

  - <span></span>  
    [New-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425792(v=OCS.15))

  - <span></span>  
    [Remove-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425894(v=OCS.15))

  - <span></span>  
    [Gruppe-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg398860(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDialInConferencingLanguageList](https://technet.microsoft.com/library/Gg425869(v=OCS.15))

**[Webkonferenz-Cmdlets in lync Server 2013](lync-server-2013-web-conferencing-cmdlets.md)**

  - <span></span>  
    [Get-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg425714(v=OCS.15))

  - <span></span>  
    [Remove-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398243(v=OCS.15))

  - <span></span>  
    [Gruppe-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398776(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Gruppe-CsConferenceServer](https://technet.microsoft.com/library/Gg398738(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg398965(v=OCS.15))

  - <span></span>  
    [New-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412967(v=OCS.15))

  - <span></span>  
    [Remove-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412767(v=OCS.15))

  - <span></span>  
    [Gruppe-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412969(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398293(v=OCS.15))

  - <span></span>  
    [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/Gg425937(v=OCS.15))

  - <span></span>  
    [New-CsConferencingPolicy](https://technet.microsoft.com/library/Gg413019(v=OCS.15))

  - <span></span>  
    [Remove-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398728(v=OCS.15))

  - <span></span>  
    [Gruppe-CsConferencingPolicy](https://technet.microsoft.com/library/Gg425788(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg425875(v=OCS.15))

  - <span></span>  
    [New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15))

  - <span></span>  
    [Remove-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15))

  - <span></span>  
    [Gruppe-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398648(v=OCS.15))

<!-- end list -->

  - [Disable-csmeetingroom "](https://technet.microsoft.com/library/JJ204723(v=OCS.15))

  - [Enable-csmeetingroom "](https://technet.microsoft.com/library/JJ205062(v=OCS.15))

  - [Get-csmeetingroom "](https://technet.microsoft.com/library/JJ205277(v=OCS.15))

  - [Csmeetingroom "](https://technet.microsoft.com/library/JJ204889(v=OCS.15))

  - [Gruppe-csmeetingroom "](https://technet.microsoft.com/library/JJ204831(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-csasconference "](https://technet.microsoft.com/library/JJ205227(v=OCS.15))

  - <span></span>  
    [Test-CsAVConference](https://technet.microsoft.com/library/Gg412749(v=OCS.15))

  - <span></span>  
    [Test-csdataconference "](https://technet.microsoft.com/library/JJ205219(v=OCS.15))

  - <span></span>  
    [Test-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))

  - <span></span>  
    [Test-CsWebAppAnonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))

  - <span></span>  
    [Test-cswebscheduler "](https://technet.microsoft.com/library/JJ204829(v=OCS.15))

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

