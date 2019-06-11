---
title: 'Lync Server 2013: Problembehandlung bei Enterprise-VoIP-Cmdlets'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Troubleshooting Enterprise Voice cmdlets
ms:assetid: 28ec32d2-6d1e-40e6-b2a8-065803288e8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415638(v=OCS.15)
ms:contentKeyID: 48183697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b569270a92808e03648042f84dbd491c80e61cf8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-enterprise-voice-cmdlets-in-lync-server-2013"></a><span data-ttu-id="5d45e-102">Problembehandlung bei Enterprise-VoIP-Cmdlets in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d45e-102">Troubleshooting Enterprise Voice cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d45e-103">_**Letztes Änderungsdatum des Themas:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="5d45e-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="5d45e-104">Das Einrichten von Enterprise-VoIP im Rahmen Ihrer Microsoft lync Server 2013-Implementierung umfasst das Erstellen von Routen, Richtlinien und Regeln, die alle zusammenarbeiten müssen, um sicherzustellen, dass eingehende und ausgehende Anrufe wie erwartet abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="5d45e-104">Setting up Enterprise Voice as part of your Microsoft Lync Server 2013 implementation involves creating routes, policies and rules that must all work together to ensure incoming and outgoing calls are completed as expected.</span></span> <span data-ttu-id="5d45e-105">Die lync Server-Verwaltungsshell umfasst Cmdlets, die zum Testen von Verbindungen und Pfaden sowie zur Behandlung von Problemen, die während der Implementierung auftreten können, verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="5d45e-105">Lync Server Management Shell includes cmdlets that can be used to test connections and paths and to troubleshoot issues that may arise during implementation.</span></span>

<div>

## <a name="troubleshooting-enterprise-voice-cmdlets"></a><span data-ttu-id="5d45e-106">Problembehandlung bei Enterprise-VoIP-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="5d45e-106">Troubleshooting Enterprise Voice Cmdlets</span></span>

<span data-ttu-id="5d45e-107">Die folgenden Cmdlets können verwendet werden, um Enterprise-VoIP-Verbindungen zu testen und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="5d45e-107">The following cmdlets can be used to test and troubleshoot Enterprise Voice connections.</span></span>

<span data-ttu-id="5d45e-108">**Problembehandlung bei Enterprise-VoIP-Cmdlets**</span><span class="sxs-lookup"><span data-stu-id="5d45e-108">**Troubleshooting Enterprise Voice Cmdlets**</span></span>

  - <span></span>  
    <span data-ttu-id="5d45e-109">[Get-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d45e-109">[Get-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d45e-110">[Remove-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d45e-110">[Remove-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398804(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d45e-111">[Satz-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d45e-111">[Set-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398967(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5d45e-112">[Get-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d45e-112">[Get-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412957(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d45e-113">[Neu – CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398961(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d45e-113">[New-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398961(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d45e-114">[Remove-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d45e-114">[Remove-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412813(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d45e-115">[Satz-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398614(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d45e-115">[Set-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398614(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5d45e-116">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398260(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d45e-116">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398260(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5d45e-117">[Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d45e-117">[Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5d45e-118">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg399003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d45e-118">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg399003(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5d45e-119">[Test-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d45e-119">[Test-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5d45e-120">[Test-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d45e-120">[Test-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5d45e-121">[Test-CsVoiceUser](https://technet.microsoft.com/en-us/library/Gg413013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5d45e-121">[Test-CsVoiceUser](https://technet.microsoft.com/en-us/library/Gg413013(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5d45e-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d45e-122">See Also</span></span>


[<span data-ttu-id="5d45e-123">Enterprise-VoIP-Cmdlets in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d45e-123">Enterprise Voice cmdlets in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-cmdlets.md)  


[<span data-ttu-id="5d45e-124">Lync Server PowerShell-Blog</span><span class="sxs-lookup"><span data-stu-id="5d45e-124">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

