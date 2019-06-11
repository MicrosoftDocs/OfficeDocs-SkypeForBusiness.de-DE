---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren eines Konferenz Geräts'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable a conferencing device
ms:assetid: d5140e38-d015-4706-9bde-cf2fa748c36b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994070(v=OCS.15)
ms:contentKeyID: 51803981
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 435c119e81923ec19e4f8a1e0d3fc35180b8508a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-conferencing-device-in-lync-server-2013"></a>Aktivieren oder Deaktivieren eines Konferenz Geräts in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-20_

Aktivieren und deaktivieren Sie ein Konferenzgerät mithilfe des Cmdlets **enable-CsMeetingRoom** und des Cmdlets **Disable-CsMeetingRoom** . Diese Cmdlets können entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.

<div>


> [!NOTE]  
> Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Remote-PowerShell" unter.



</div>

<div>


<div>

## <a name="enabling-a-conferencing-device"></a>Aktivieren eines Konferenz Geräts

  - Verwenden Sie zum Aktivieren eines Konferenz Geräts das Cmdlet **enable-CsMeetingRoom** . Wenn Sie ein Konferenzgerät aktivieren, müssen Sie ein) die Konferenzgeräte Identität, b) den Registrierungspool, in dem sich das Raum Konto befindet, und c) die SIP-Adresse einbeziehen, die diesem Konto zugewiesen werden soll.
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="disabling-a-conferencing-device"></a>Deaktivieren eines Konferenz Geräts

  - Verwenden Sie zum Deaktivieren eines Konferenz Geräts das Cmdlet **Disable-CsMeetingRoom** . Stellen Sie sicher, dass Sie die Identität des Konferenz Geräts angeben, das deaktiviert werden soll:
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

</div>

Ausführliche Informationen finden Sie in den Hilfethemen zum Cmdlet [enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) und dem Cmdlet [Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

