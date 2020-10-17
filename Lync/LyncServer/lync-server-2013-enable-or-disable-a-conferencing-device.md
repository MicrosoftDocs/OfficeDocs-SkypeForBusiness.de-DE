---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren eines Konferenz Geräts'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a conferencing device
ms:assetid: d5140e38-d015-4706-9bde-cf2fa748c36b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994070(v=OCS.15)
ms:contentKeyID: 51803981
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5ebbebde30d39a95879a766280d3f34a830683e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528652"
---
# <a name="enable-or-disable-a-conferencing-device-in-lync-server-2013"></a>Aktivieren oder Deaktivieren eines Konferenz Geräts in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-20_

Aktivieren und deaktivieren Sie ein Konferenzgerät mithilfe des Cmdlets **enable-csmeetingroom "** und dem Cmdlet **Disable-csmeetingroom"** . Diese Cmdlets können entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.

<div>


> [!NOTE]  
> Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .



</div>

<div>


<div>

## <a name="enabling-a-conferencing-device"></a>Aktivieren eines Konferenz Geräts

  - Verwenden Sie das Cmdlet **enable-csmeetingroom "** , um ein Konferenzgerät zu aktivieren. Wenn Sie ein Konferenzgerät aktivieren, müssen Sie ein) die Identität des Konferenz Geräts, b) den registrierungsstellenpool, in dem das Raum Konto verwaltet wird, und c) die SIP-Adresse, die diesem Konto zugewiesen werden soll, einschließen.
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="disabling-a-conferencing-device"></a>Deaktivieren eines Konferenz Geräts

  - Verwenden Sie das Cmdlet **Disable-csmeetingroom "** , um ein Konferenzgerät zu deaktivieren. Stellen Sie sicher, dass Sie die Identität des Konferenz Geräts, das deaktiviert werden soll, angeben:
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

</div>

Ausführliche Informationen finden Sie in den Hilfethemen zum Cmdlet [enable-csmeetingroom "](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) und im Cmdlet [Disable-csmeetingroom"](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

