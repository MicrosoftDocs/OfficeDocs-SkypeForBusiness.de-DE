---
title: 'Lync Server 2013: Active Directory-Cmdlets'
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
ms.openlocfilehash: f77009f20cfbd3e76f5cfc3786bcd9fa9ba2be9b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-cmdlets-in-lync-server-2013"></a><span data-ttu-id="bf2f2-102">Active Directory-Cmdlets in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf2f2-102">Active Directory cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf2f2-103">_**Letztes Änderungsdatum des Themas:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="bf2f2-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="bf2f2-104">Die Active Directory-Cmdlets werden in der Regel vom Setup verwendet und werden selten direkt von einem Administrator aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="bf2f2-104">The Active Directory cmdlets are typically used by Setup, and will rarely be called directly by an administrator.</span></span> <span data-ttu-id="bf2f2-105">Administratoren können diese Cmdlets jedoch verwenden, um eine Domäne oder Gesamtstruktur für Microsoft lync Server 2013 vorzubereiten (oder aufzubereiten) und die erforderlichen Active Directory-Schemadateien zu installieren.</span><span class="sxs-lookup"><span data-stu-id="bf2f2-105">However, administrators can use these cmdlets to prepare (or unprepare) a domain or forest for Microsoft Lync Server 2013, and to install the required Active Directory schema files.</span></span>

<div>

## <a name="active-directory-cmdlets"></a><span data-ttu-id="bf2f2-106">Active Directory-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="bf2f2-106">Active Directory Cmdlets</span></span>

<span data-ttu-id="bf2f2-107">Die folgende Liste enthält Cmdlets, die sich direkt auf die Verwaltung von lync Server 2013 Active Directory-Einstellungen beziehen:</span><span class="sxs-lookup"><span data-stu-id="bf2f2-107">The following is a list of cmdlets that relate directly to managing Lync Server 2013 Active Directory settings:</span></span>

<span data-ttu-id="bf2f2-108">**Active Directory**</span><span class="sxs-lookup"><span data-stu-id="bf2f2-108">**Active Directory**</span></span>

  - <span></span>  
    <span data-ttu-id="bf2f2-109">[Deaktivieren-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bf2f2-109">[Disable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398785(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="bf2f2-110">[Enable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg412764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bf2f2-110">[Enable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg412764(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="bf2f2-111">[Get-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398453(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bf2f2-111">[Get-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398453(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="bf2f2-112">[Deaktivieren-CsAdForest](https://technet.microsoft.com/en-us/library/Gg398122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bf2f2-112">[Disable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg398122(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="bf2f2-113">[Enable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg425713(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bf2f2-113">[Enable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg425713(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="bf2f2-114">[Get-CsAdForest](https://technet.microsoft.com/en-us/library/Gg412995(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bf2f2-114">[Get-CsAdForest](https://technet.microsoft.com/en-us/library/Gg412995(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="bf2f2-115">[Get-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg413070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bf2f2-115">[Get-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg413070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="bf2f2-116">[Installieren-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg398681(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bf2f2-116">[Install-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg398681(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bf2f2-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf2f2-117">See Also</span></span>


[<span data-ttu-id="bf2f2-118">Lync Server PowerShell-Blog</span><span class="sxs-lookup"><span data-stu-id="bf2f2-118">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

