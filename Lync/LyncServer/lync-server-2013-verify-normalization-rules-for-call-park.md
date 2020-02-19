---
title: 'Lync Server 2013: Überprüfen der Normalisierungsregeln für das Parken von Anrufen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify normalization rules for Call Park
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398981(v=OCS.15)
ms:contentKeyID: 48185646
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dda9fe8d3e0ca9ebc4dec96a8e878fe36576fd41
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a><span data-ttu-id="0e6f1-102">Überprüfen der Normalisierungsregeln für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e6f1-102">Verify normalization rules for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e6f1-103">_**Letztes Änderungsstand des Themas:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="0e6f1-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="0e6f1-104">Orbits für das Parken von anrufen dürfen nicht normalisiert werden.</span><span class="sxs-lookup"><span data-stu-id="0e6f1-104">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="0e6f1-105">Überprüfen Sie Ihre Wählpläne, um sicherzustellen, dass Ihre Orbit-Nummern nicht normalisiert sind.</span><span class="sxs-lookup"><span data-stu-id="0e6f1-105">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="0e6f1-106">Wenn Sie eine zusätzliche Normalisierungsregel erstellen müssen, um zu verhindern, dass ihre Umlaufbahnen normalisiert werden, führen Sie das Verfahren unter [Create a Dial Plan in lync Server 2013](lync-server-2013-create-a-dial-plan.md) aus, um eine neue Normalisierungsregel zu definieren, sodass das **übereinstimmende Muster** den orbitbereich und das **Übersetzungsmuster** **$1**angibt.</span><span class="sxs-lookup"><span data-stu-id="0e6f1-106">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="0e6f1-107">Wenn Ihr orbitbereich für das Parken von Anrufen z. b. 7000 – 7999 ist, lautet das **übereinstimmende Muster** **^ (\\7 d{3}) $** und das **Übersetzungsmuster** ist **$1**.</span><span class="sxs-lookup"><span data-stu-id="0e6f1-107">For example, if your Call Park orbit range is 7000 – 7999, the **Pattern to match** is **^(7\\d{3})$** and **Translation pattern** is **$1**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0e6f1-108">Stellen Sie sicher, dass die Standard Normalisierungsregel in ihren Wählplänen nicht <STRONG>^ (\d \*)</STRONG>enthält.</span><span class="sxs-lookup"><span data-stu-id="0e6f1-108">Be sure that the default normalization rule in your dial plans does not contain <STRONG>^(\d\*)</STRONG>.</span></span> <span data-ttu-id="0e6f1-109">Andernfalls wird die Normalisierungsregel für das Parken von Anrufen nie ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0e6f1-109">Otherwise, your Call Park normalization rule will never run.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0e6f1-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e6f1-110">See Also</span></span>


[<span data-ttu-id="0e6f1-111">Erstellen von Wähleinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e6f1-111">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

