---
title: 'Lync Server 2013: Cmdlets für Migration und Koexistenz'
description: 'Lync Server 2013: Cmdlets für Migration und Koexistenz.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration and coexistence cmdlets
ms:assetid: ff1a56e0-e883-473d-92fe-ca77ea4eb63b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415682(v=OCS.15)
ms:contentKeyID: 48185968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eecd1adad53d8f917d7db7ca201b25442a7d5e85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561011"
---
# <a name="migration-and-coexistence-cmdlets-in-lync-server-2013"></a><span data-ttu-id="ed90d-103">Cmdlets für Migration und Koexistenz in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed90d-103">Migration and coexistence cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed90d-104">_**Letztes Änderungsstand des Themas:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="ed90d-104">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="ed90d-105">Das Cmdlet " [CsLegacyUser](https://technet.microsoft.com/library/Gg413025(v=OCS.15)) " bietet Ihnen die Möglichkeit, Benutzerkonten aus Office Communications Server 2007 oder Microsoft lync Server 2010 in Microsoft lync Server 2013 zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="ed90d-105">The [Move-CsLegacyUser](https://technet.microsoft.com/library/Gg413025(v=OCS.15)) cmdlet provides a way for you to move user accounts from Office Communications Server 2007 or Microsoft Lync Server 2010 to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="ed90d-106">Wenn Sie ein Benutzerkonto "rückwärts" verschieben müssen (beispielsweise von Microsoft lync Server 2013 in Microsoft lync Server 2010), verwenden Sie das Cmdlet " [verschieben-CsUser](https://technet.microsoft.com/library/Gg398528(v=OCS.15)) ".</span><span class="sxs-lookup"><span data-stu-id="ed90d-106">If you need to move a user account "backward" (for example, from Microsoft Lync Server 2013 to Microsoft Lync Server 2010) use the [Move-CsUser](https://technet.microsoft.com/library/Gg398528(v=OCS.15)) cmdlet.</span></span>

  - <span></span>  
    <span data-ttu-id="ed90d-107">[Import-CsLegacyConferenceDirectory](https://technet.microsoft.com/library/Gg398418(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ed90d-107">[Import-CsLegacyConferenceDirectory](https://technet.microsoft.com/library/Gg398418(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ed90d-108">[Import-CsLegacyConfiguration](https://technet.microsoft.com/library/Gg412923(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ed90d-108">[Import-CsLegacyConfiguration](https://technet.microsoft.com/library/Gg412923(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ed90d-109">[Merge-CsLegacyTopology](https://technet.microsoft.com/library/Gg425870(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ed90d-109">[Merge-CsLegacyTopology](https://technet.microsoft.com/library/Gg425870(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ed90d-110">[CsApplicationEndpoint](https://technet.microsoft.com/library/Gg398188(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ed90d-110">[Move-CsApplicationEndpoint](https://technet.microsoft.com/library/Gg398188(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ed90d-111">[CsLegacyUser](https://technet.microsoft.com/library/Gg413025(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ed90d-111">[Move-CsLegacyUser](https://technet.microsoft.com/library/Gg413025(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="ed90d-112">[Convert-csuserdata "](https://technet.microsoft.com/library/JJ205337(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ed90d-112">[Convert-CsUserData](https://technet.microsoft.com/library/JJ205337(v=OCS.15))</span></span>

  - <span data-ttu-id="ed90d-113">[Export-csuserdata "](https://technet.microsoft.com/library/JJ204897(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ed90d-113">[Export-CsUserData](https://technet.microsoft.com/library/JJ204897(v=OCS.15))</span></span>

  - <span data-ttu-id="ed90d-114">[Import-csuserdata "](https://technet.microsoft.com/library/JJ205373(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ed90d-114">[Import-CsUserData](https://technet.microsoft.com/library/JJ205373(v=OCS.15))</span></span>

  - <span data-ttu-id="ed90d-115">[Update-csuserdata "](https://technet.microsoft.com/library/JJ205358(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ed90d-115">[Update-CsUserData](https://technet.microsoft.com/library/JJ205358(v=OCS.15))</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ed90d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed90d-116">See Also</span></span>


[<span data-ttu-id="ed90d-117">Lync Server PowerShell-Blog</span><span class="sxs-lookup"><span data-stu-id="ed90d-117">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

