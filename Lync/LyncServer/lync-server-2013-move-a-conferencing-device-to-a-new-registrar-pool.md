---
title: 'Lync Server 2013: Migrieren eines Konferenz Geräts in einen neuen registrierungsstellenpool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move a conferencing device to a new Registrar pool
ms:assetid: 26e02ca3-e881-4f90-8bf0-b13649108100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994025(v=OCS.15)
ms:contentKeyID: 51803934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e1fee1ce312812185b81089323469b8259574bb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-a-conferencing-device-to-a-new-registrar-pool-in-lync-server-2013"></a><span data-ttu-id="19e0d-102">Migrieren eines Konferenz Geräts in einen neuen registrierungsstellenpool in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19e0d-102">Move a conferencing device to a new Registrar pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19e0d-103">_**Letztes Änderungsstand des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="19e0d-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="19e0d-104">Verwenden Sie das Cmdlet " **csmeetingroom"** ", um ein Konferenzgerät von einem registrierungsstellenpool in einen anderen zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="19e0d-104">Move a conferencing device from one Registrar pool to another by using the **Move-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="19e0d-105">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="19e0d-105">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="19e0d-106">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="19e0d-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="moving-a-conferencing-device-to-a-new-registrar-pool"></a><span data-ttu-id="19e0d-107">Verschieben eines Konferenz Geräts in einen neuen Registrierungsstellen Pool</span><span class="sxs-lookup"><span data-stu-id="19e0d-107">Moving a Conferencing Device to a New Registrar Pool</span></span>

  - <span data-ttu-id="19e0d-108">Zum Verschieben eines Konferenz Geräts müssen Sie die Identität des zu verschiebenden Raums angeben und dann den Parameter Target auf den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Registrierungsstellen Pools festlegen, in den das Gerät verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="19e0d-108">To move a conferencing device, you must specify the identity of the room to be moved, and then set the Target parameter to the fully qualified domain name (FQDN) of the Registrar pool the device will be moved to.</span></span> <span data-ttu-id="19e0d-109">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="19e0d-109">For example:</span></span>
    
        Move-CsMeetingRoom -Target "atl-cs-001.litwareinc.com" -Identity "Room 14"

</div>

<span data-ttu-id="19e0d-110">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet " [csmeetingroom"](https://docs.microsoft.com/powershell/module/skype/Move-CsMeetingRoom) ".</span><span class="sxs-lookup"><span data-stu-id="19e0d-110">For details, see the Help topic for the [Move-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Move-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

