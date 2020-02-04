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
ms.openlocfilehash: 3a4a0f582f57d4e096001d508d3983facdded74c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-conferencing-device-in-lync-server-2013"></a><span data-ttu-id="0b43e-102">Aktivieren oder Deaktivieren eines Konferenz Geräts in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b43e-102">Enable or disable a conferencing device in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b43e-103">_**Letztes Änderungsdatum des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="0b43e-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="0b43e-104">Aktivieren und deaktivieren Sie ein Konferenzgerät mithilfe des Cmdlets **enable-CsMeetingRoom** und des Cmdlets **Disable-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="0b43e-104">Enable and disable a conferencing device by using the **Enable-CsMeetingRoom** cmdlet and the **Disable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="0b43e-105">Diese Cmdlets können entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0b43e-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b43e-106">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="0b43e-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="enabling-a-conferencing-device"></a><span data-ttu-id="0b43e-107">Aktivieren eines Konferenz Geräts</span><span class="sxs-lookup"><span data-stu-id="0b43e-107">Enabling a Conferencing Device</span></span>

  - <span data-ttu-id="0b43e-108">Verwenden Sie zum Aktivieren eines Konferenz Geräts das Cmdlet **enable-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="0b43e-108">To enable a conferencing device, use the **Enable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="0b43e-109">Wenn Sie ein Konferenzgerät aktivieren, müssen Sie ein) die Konferenzgeräte Identität, b) den Registrierungspool, in dem sich das Raum Konto befindet, und c) die SIP-Adresse einbeziehen, die diesem Konto zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="0b43e-109">When enabling a conferencing device, you must include a) the conferencing device identity, b) the Registrar pool where the room account will be homed, and c) the SIP address to be assigned to that account.</span></span>
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="disabling-a-conferencing-device"></a><span data-ttu-id="0b43e-110">Deaktivieren eines Konferenz Geräts</span><span class="sxs-lookup"><span data-stu-id="0b43e-110">Disabling a Conferencing Device</span></span>

  - <span data-ttu-id="0b43e-111">Verwenden Sie zum Deaktivieren eines Konferenz Geräts das Cmdlet **Disable-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="0b43e-111">To disable a conferencing device, use the **Disable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="0b43e-112">Stellen Sie sicher, dass Sie die Identität des Konferenz Geräts angeben, das deaktiviert werden soll:</span><span class="sxs-lookup"><span data-stu-id="0b43e-112">Make sure that you specify the identity of the conferencing device to be disabled:</span></span>
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<span data-ttu-id="0b43e-113">Ausführliche Informationen finden Sie in den Hilfethemen zum Cmdlet [enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) und dem Cmdlet [Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="0b43e-113">For details, see the Help topics for the [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) cmdlet and the [Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

