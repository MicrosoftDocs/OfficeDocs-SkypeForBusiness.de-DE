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
ms.openlocfilehash: 27a5ed5c138d1389f0a3d4882bcdd437b5e7919e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-conferencing-device-in-lync-server-2013"></a><span data-ttu-id="77c9f-102">Aktivieren oder Deaktivieren eines Konferenz Geräts in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77c9f-102">Enable or disable a conferencing device in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77c9f-103">_**Letztes Änderungsstand des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="77c9f-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="77c9f-104">Aktivieren und deaktivieren Sie ein Konferenzgerät mithilfe des Cmdlets **enable-csmeetingroom "** und dem Cmdlet **Disable-csmeetingroom"** .</span><span class="sxs-lookup"><span data-stu-id="77c9f-104">Enable and disable a conferencing device by using the **Enable-CsMeetingRoom** cmdlet and the **Disable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="77c9f-105">Diese Cmdlets können entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="77c9f-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77c9f-106">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="77c9f-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="enabling-a-conferencing-device"></a><span data-ttu-id="77c9f-107">Aktivieren eines Konferenz Geräts</span><span class="sxs-lookup"><span data-stu-id="77c9f-107">Enabling a Conferencing Device</span></span>

  - <span data-ttu-id="77c9f-108">Verwenden Sie das Cmdlet **enable-csmeetingroom "** , um ein Konferenzgerät zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="77c9f-108">To enable a conferencing device, use the **Enable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="77c9f-109">Wenn Sie ein Konferenzgerät aktivieren, müssen Sie ein) die Identität des Konferenz Geräts, b) den registrierungsstellenpool, in dem das Raum Konto verwaltet wird, und c) die SIP-Adresse, die diesem Konto zugewiesen werden soll, einschließen.</span><span class="sxs-lookup"><span data-stu-id="77c9f-109">When enabling a conferencing device, you must include a) the conferencing device identity, b) the Registrar pool where the room account will be homed, and c) the SIP address to be assigned to that account.</span></span>
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="disabling-a-conferencing-device"></a><span data-ttu-id="77c9f-110">Deaktivieren eines Konferenz Geräts</span><span class="sxs-lookup"><span data-stu-id="77c9f-110">Disabling a Conferencing Device</span></span>

  - <span data-ttu-id="77c9f-111">Verwenden Sie das Cmdlet **Disable-csmeetingroom "** , um ein Konferenzgerät zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="77c9f-111">To disable a conferencing device, use the **Disable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="77c9f-112">Stellen Sie sicher, dass Sie die Identität des Konferenz Geräts, das deaktiviert werden soll, angeben:</span><span class="sxs-lookup"><span data-stu-id="77c9f-112">Make sure that you specify the identity of the conferencing device to be disabled:</span></span>
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<span data-ttu-id="77c9f-113">Ausführliche Informationen finden Sie in den Hilfethemen zum Cmdlet [enable-csmeetingroom "](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) und im Cmdlet [Disable-csmeetingroom"](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="77c9f-113">For details, see the Help topics for the [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) cmdlet and the [Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

