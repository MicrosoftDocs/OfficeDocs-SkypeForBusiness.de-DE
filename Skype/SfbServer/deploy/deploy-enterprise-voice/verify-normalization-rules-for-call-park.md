---
title: Überprüfen von Normalisierungsregeln für den Parken von Anrufen in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Informieren Sie sich über Normalisierungsregeln für den Parken von Anrufen in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 769d9f9becccf4df24a33a11e8814350cfb091e8
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766888"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a><span data-ttu-id="6c70e-103">Überprüfen von Normalisierungsregeln für den Parken von Anrufen in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6c70e-103">Verify normalization rules for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="6c70e-104">Informieren Sie sich über Normalisierungsregeln für den Parken von Anrufen in Skype for Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="6c70e-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="6c70e-105">Orbits für das Parken von anrufen dürfen nicht normalisiert werden.</span><span class="sxs-lookup"><span data-stu-id="6c70e-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="6c70e-106">Überprüfen Sie Ihre Wählpläne, um sicherzustellen, dass Ihre Orbit-Nummern nicht normalisiert sind.</span><span class="sxs-lookup"><span data-stu-id="6c70e-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="6c70e-107">Wenn Sie eine zusätzliche Normalisierungsregel erstellen müssen, um zu verhindern, dass ihre Umlaufbahnen normalisiert werden, führen Sie die Schritte unter [erstellen oder Ändern eines Wählplans in Skype for Business Server](dial-plans.md) aus, um eine neue Normalisierungsregel zu definieren, damit das **übereinstimmende Muster** den Umlaufbahn Bereich und das **Übersetzungsmuster** auf **$1**angibt.</span><span class="sxs-lookup"><span data-stu-id="6c70e-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="6c70e-108">Wenn beispielsweise der Orbit-Bereich Ihres Anruf Parks 7000-7999 ist, ist das **Muster, das übereinstimmen** soll, **^ (7 \ d{3}) $** , und das **Übersetzungsmuster** ist **$1**.</span><span class="sxs-lookup"><span data-stu-id="6c70e-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6c70e-109">Stellen Sie sicher, dass die Standard Normalisierungsregel in ihren Wählplänen **^ (\d\*)** nicht enthält.</span><span class="sxs-lookup"><span data-stu-id="6c70e-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="6c70e-110">Andernfalls wird Ihre Normalisierungsregel für den Anruf Park nie ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6c70e-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6c70e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c70e-111">See also</span></span>

[<span data-ttu-id="6c70e-112">Erstellen oder Ändern eines Wählplans in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6c70e-112">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

