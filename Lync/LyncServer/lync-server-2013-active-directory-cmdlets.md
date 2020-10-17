---
title: 'Lync Server 2013: Active Directory-Cmdlets'
description: 'Lync Server 2013: Active Directory-Cmdlets.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory cmdlets
ms:assetid: 313d73cb-f3db-4bc4-8708-de4da1d719c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415640(v=OCS.15)
ms:contentKeyID: 48183769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c5e87cda24d5517b9c4501523fd06804ea20020
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571081"
---
# <a name="active-directory-cmdlets-in-lync-server-2013"></a><span data-ttu-id="a76e9-103">Active Directory-Cmdlets in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a76e9-103">Active Directory cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a76e9-104">_**Letztes Änderungsstand des Themas:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="a76e9-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="a76e9-105">Die Active Directory-Cmdlets werden in der Regel vom Setup verwendet und von einem Administrator nur selten direkt aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="a76e9-105">The Active Directory cmdlets are typically used by Setup, and will rarely be called directly by an administrator.</span></span> <span data-ttu-id="a76e9-106">Administratoren können diese Cmdlets jedoch verwenden, um eine Domäne oder Gesamtstruktur für Microsoft lync Server 2013 vorzubereiten (oder aufzubereiten) und die erforderlichen Active Directory Schemadateien zu installieren.</span><span class="sxs-lookup"><span data-stu-id="a76e9-106">However, administrators can use these cmdlets to prepare (or unprepare) a domain or forest for Microsoft Lync Server 2013, and to install the required Active Directory schema files.</span></span>

<div>

## <a name="active-directory-cmdlets"></a><span data-ttu-id="a76e9-107">Active Directory-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="a76e9-107">Active Directory Cmdlets</span></span>

<span data-ttu-id="a76e9-108">Im folgenden finden Sie eine Liste der Cmdlets, die direkt mit der Verwaltung von lync Server 2013 Active Directory Einstellungen in Zusammenhangstehen:</span><span class="sxs-lookup"><span data-stu-id="a76e9-108">The following is a list of cmdlets that relate directly to managing Lync Server 2013 Active Directory settings:</span></span>

<span data-ttu-id="a76e9-109">**Active Directory**</span><span class="sxs-lookup"><span data-stu-id="a76e9-109">**Active Directory**</span></span>

  - <span></span>  
    <span data-ttu-id="a76e9-110">[Disable-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a76e9-110">[Disable-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a76e9-111">[Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a76e9-111">[Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a76e9-112">[Get-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a76e9-112">[Get-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a76e9-113">[Disable-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a76e9-113">[Disable-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a76e9-114">[Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a76e9-114">[Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a76e9-115">[Get-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a76e9-115">[Get-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a76e9-116">[Get-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a76e9-116">[Get-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a76e9-117">[Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a76e9-117">[Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a76e9-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a76e9-118">See Also</span></span>


[<span data-ttu-id="a76e9-119">Lync Server PowerShell-Blog</span><span class="sxs-lookup"><span data-stu-id="a76e9-119">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

