---
title: 'Lync Server 2013: Cmdlets für Trunking-Konfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Trunking configuration cmdlets
ms:assetid: 2c36b03a-b80f-4321-a448-6ba26b9357f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416489(v=OCS.15)
ms:contentKeyID: 48183703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec65e877d480924f3fcc312b3972cc329ad4ed34
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="trunking-configuration-cmdlets-in-lync-server-2013"></a><span data-ttu-id="acf5a-102">Cmdlets für Trunking-Konfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acf5a-102">Trunking configuration cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acf5a-103">_**Letztes Änderungsdatum des Themas:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="acf5a-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="acf5a-104">Mithilfe von trunk Configuration-Cmdlets werden Einstellungen für eine Trunking-Peer Entität wie ein öffentliches Switched Telephone Network (PSTN)-Gateway, eine IP-Public Branch Exchange (PBX) oder ein Session Border Controller (SBC) beim Dienstanbieter definiert.</span><span class="sxs-lookup"><span data-stu-id="acf5a-104">Trunk configuration cmdlets are used to define settings for a trunking peer entity such as a public switched telephone network (PSTN) gateway, IP-public branch exchange (PBX), or Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="acf5a-105">Diese Einstellungen konfigurieren beispielsweise, ob die Medienumgehung auf diesem Trunk aktiviert ist, ob unter bestimmten Bedingungen RTCP-Pakete (Real-Time Transport Control Protocol) gesendet werden und ob die sichere SRTP-Verschlüsselung (Secure Real-Time Transport Protocol) erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="acf5a-105">These settings configure such things as whether media bypass is enabled on this trunk, whether real-time transport control protocol (RTCP) packets are sent under certain conditions, and whether to require secure real-time protocol (SRTP) encryption.</span></span>

<div>

## <a name="trunking-configuration-cmdlets"></a><span data-ttu-id="acf5a-106">Konfigurations-Cmdlets für Trunking</span><span class="sxs-lookup"><span data-stu-id="acf5a-106">Trunking Configuration Cmdlets</span></span>

<span data-ttu-id="acf5a-107">Verwenden Sie die folgenden Cmdlets für die trunk-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="acf5a-107">Use the following cmdlets for trunk configuration.</span></span>

<span data-ttu-id="acf5a-108">**Trunking-Konfiguration**</span><span class="sxs-lookup"><span data-stu-id="acf5a-108">**Trunking Configuration**</span></span>

  - <span data-ttu-id="acf5a-109">[Test-CsInterTrunkRouting](https://technet.microsoft.com/en-us/library/JJ204741(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="acf5a-109">[Test-CsInterTrunkRouting](https://technet.microsoft.com/en-us/library/JJ204741(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="acf5a-110">[Get-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204962(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="acf5a-110">[Get-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204962(v=OCS.15))</span></span>

  - <span data-ttu-id="acf5a-111">[New-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205097(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="acf5a-111">[New-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205097(v=OCS.15))</span></span>

  - <span data-ttu-id="acf5a-112">[Remove-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204836(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="acf5a-112">[Remove-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204836(v=OCS.15))</span></span>

  - <span data-ttu-id="acf5a-113">[Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205400(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="acf5a-113">[Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205400(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="acf5a-114">[Get-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398104(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="acf5a-114">[Get-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398104(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="acf5a-115">[Neu – CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg412803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="acf5a-115">[New-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg412803(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="acf5a-116">[Remove-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398556(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="acf5a-116">[Remove-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398556(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="acf5a-117">[Satz-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg413073(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="acf5a-117">[Set-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg413073(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="acf5a-118">[Get-CsTrunk](https://technet.microsoft.com/en-us/library/JJ205244(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="acf5a-118">[Get-CsTrunk](https://technet.microsoft.com/en-us/library/JJ205244(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="acf5a-119">[Get-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398224(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="acf5a-119">[Get-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398224(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="acf5a-120">[Neu – CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg413021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="acf5a-120">[New-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg413021(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="acf5a-121">[Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="acf5a-121">[Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="acf5a-122">[Satz-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="acf5a-122">[Set-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398238(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="acf5a-123">[Test-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398137(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="acf5a-123">[Test-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398137(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="acf5a-124">[Neu – CsVoiceRegex](https://technet.microsoft.com/en-us/library/Gg412751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="acf5a-124">[New-CsVoiceRegex](https://technet.microsoft.com/en-us/library/Gg412751(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="acf5a-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acf5a-125">See Also</span></span>


[<span data-ttu-id="acf5a-126">Lync Server PowerShell-Blog</span><span class="sxs-lookup"><span data-stu-id="acf5a-126">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

