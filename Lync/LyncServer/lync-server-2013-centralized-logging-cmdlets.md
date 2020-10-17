---
title: 'Lync Server 2013: Cmdlets für die zentralisierte Protokollierung'
description: 'Lync Server 2013: Cmdlets für die zentralisierte Protokollierung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Centralized Logging cmdlets
ms:assetid: 8ba5bcae-8b99-489c-9355-6e77d4ad9100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205064(v=OCS.15)
ms:contentKeyID: 48184743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98457564de22b719e0741a6f5364c409e2b4d3ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544341"
---
# <a name="centralized-logging-cmdlets-in-lync-server-2013"></a><span data-ttu-id="d165d-103">Cmdlets für die zentralisierte Protokollierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d165d-103">Centralized Logging cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d165d-104">_**Letztes Änderungsstand des Themas:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="d165d-104">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="d165d-105">Die Cmdlets für die zentralisierte Protokollierung bieten Administratoren die Möglichkeit, die in Microsoft lync Server 2013 eingeführten zentralisierten Protokollierungsfunktionen zu verwalten und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d165d-105">The centralized logging cmdlets provide a way for administrators to manage and configure the centralized logging capabilities introduced in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="d165d-106">Durch die zentralisierte Protokollierung können Administratoren die Ereignisablaufverfolgung auf mehreren Computern gleichzeitig aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d165d-106">Centralized logging allows administrators to simultaneously enable or disable event tracing on multiple computers.</span></span>

<div>

## <a name="centralized-logging-cmdlets"></a><span data-ttu-id="d165d-107">Zentralisierte Protokollierungs-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="d165d-107">Centralized Logging Cmdlets</span></span>

<span data-ttu-id="d165d-108">Mit den Cmdlets für die zentralisierte Protokollierung können Sie den in lync Server 2013 eingeführten zentralisierten Protokollierungsdienst verwalten:</span><span class="sxs-lookup"><span data-stu-id="d165d-108">The centralized logging cmdlets enable you to manage the centralized logging service introduced in Lync Server 2013:</span></span>

<span data-ttu-id="d165d-109">**Zentralisierte Protokollierungs-Cmdlets**</span><span class="sxs-lookup"><span data-stu-id="d165d-109">**Centralized Logging Cmdlets**</span></span>

  - <span data-ttu-id="d165d-110">[Get-csclsconfiguration "](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-110">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span></span>

  - <span data-ttu-id="d165d-111">[New-csclsconfiguration "](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-111">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span></span>

  - <span data-ttu-id="d165d-112">[Remove-csclsconfiguration "](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-112">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span></span>

  - <span data-ttu-id="d165d-113">[Gruppe-csclsconfiguration "](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-113">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="d165d-114">[Suche-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-114">[Search-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15))</span></span>

  - <span data-ttu-id="d165d-115">[Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-115">[Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15))</span></span>

  - <span data-ttu-id="d165d-116">[Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-116">[Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15))</span></span>

  - <span data-ttu-id="d165d-117">[Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-117">[Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15))</span></span>

  - <span data-ttu-id="d165d-118">[Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-118">[Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15))</span></span>

  - <span data-ttu-id="d165d-119">[Update-CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-119">[Update-CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="d165d-120">[New-CsClsProvider](https://technet.microsoft.com/library/JJ619187(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-120">[New-CsClsProvider](https://technet.microsoft.com/library/JJ619187(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="d165d-121">[Get-CsClsRegion](https://technet.microsoft.com/library/JJ204879(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-121">[Get-CsClsRegion](https://technet.microsoft.com/library/JJ204879(v=OCS.15))</span></span>

  - <span data-ttu-id="d165d-122">[New-CsClsRegion](https://technet.microsoft.com/library/JJ204658(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-122">[New-CsClsRegion](https://technet.microsoft.com/library/JJ204658(v=OCS.15))</span></span>

  - <span data-ttu-id="d165d-123">[Remove-CsClsRegion](https://technet.microsoft.com/library/JJ204971(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-123">[Remove-CsClsRegion](https://technet.microsoft.com/library/JJ204971(v=OCS.15))</span></span>

  - <span data-ttu-id="d165d-124">[Gruppe-CsClsRegion](https://technet.microsoft.com/library/JJ204746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-124">[Set-CsClsRegion](https://technet.microsoft.com/library/JJ204746(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="d165d-125">[Get-CsClsScenario](https://technet.microsoft.com/library/JJ205091(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-125">[Get-CsClsScenario](https://technet.microsoft.com/library/JJ205091(v=OCS.15))</span></span>

  - <span data-ttu-id="d165d-126">[New-CsClsScenario](https://technet.microsoft.com/library/JJ205022(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-126">[New-CsClsScenario](https://technet.microsoft.com/library/JJ205022(v=OCS.15))</span></span>

  - <span data-ttu-id="d165d-127">[Remove-CsClsScenario](https://technet.microsoft.com/library/JJ205010(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-127">[Remove-CsClsScenario](https://technet.microsoft.com/library/JJ205010(v=OCS.15))</span></span>

  - <span data-ttu-id="d165d-128">[Gruppe-CsClsScenario](https://technet.microsoft.com/library/JJ204622(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-128">[Set-CsClsScenario](https://technet.microsoft.com/library/JJ204622(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="d165d-129">[Get-CsClsSearchTerm](https://technet.microsoft.com/library/JJ205061(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-129">[Get-CsClsSearchTerm](https://technet.microsoft.com/library/JJ205061(v=OCS.15))</span></span>

  - <span data-ttu-id="d165d-130">[Gruppe-CsClsSearchTerm](https://technet.microsoft.com/library/JJ204911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-130">[Set-CsClsSearchTerm](https://technet.microsoft.com/library/JJ204911(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="d165d-131">[Get-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205285(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-131">[Get-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205285(v=OCS.15))</span></span>

  - <span data-ttu-id="d165d-132">[New-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205359(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-132">[New-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205359(v=OCS.15))</span></span>

  - <span data-ttu-id="d165d-133">[Remove-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204958(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-133">[Remove-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204958(v=OCS.15))</span></span>

  - <span data-ttu-id="d165d-134">[Gruppe-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204700(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d165d-134">[Set-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204700(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

