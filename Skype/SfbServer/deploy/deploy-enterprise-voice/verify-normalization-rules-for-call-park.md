---
title: Überprüfen der Normalisierungsregeln für das Parken von Anrufen in Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Informationen Sie zu Normalisierungsregeln für das Parken von Anrufen in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: c637240d4c193bbec05228d167d77f7bd18c0d04
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business-2015"></a><span data-ttu-id="9a975-103">Überprüfen der Normalisierungsregeln für das Parken von Anrufen in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="9a975-103">Verify normalization rules for Call Park in Skype for Business 2015</span></span>
 
<span data-ttu-id="9a975-104">Informationen Sie zu Normalisierungsregeln für das Parken von Anrufen in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="9a975-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="9a975-105">Parken Orbits müssen nicht normalisiert werden.</span><span class="sxs-lookup"><span data-stu-id="9a975-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="9a975-106">Überprüfen Sie Ihren Wählplänen, um sicherzustellen, dass Ihre orbitnummern nicht normalisiert werden.</span><span class="sxs-lookup"><span data-stu-id="9a975-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="9a975-107">Wenn Sie eine zusätzliche Normalisierungsregel aus, um zu verhindern, dass Ihre Orbits normalisierende erstellen müssen, führen Sie das Verfahren in [Erstellen oder Ändern von Wähleinstellungen in Skype für Business Server 2015](dial-plans.md) so definieren Sie eine neue Normalisierungsregel also dieses **Muster abgleichen** identifiziert den orbitbereich und **übersetzungsmuster** **$1**ist.</span><span class="sxs-lookup"><span data-stu-id="9a975-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server 2015](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="9a975-108">Angenommen, Ihr orbitbereich zum Parken von Anrufen 7000-7999, das **Vergleichsmuster** ist **^(7\d{3})$** und **übersetzungsmuster** **$1**ist.</span><span class="sxs-lookup"><span data-stu-id="9a975-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9a975-109">Achten Sie darauf, dass die Standard-Normalisierungsregel in Ihren Wählplänen keine enthält **^(\d\*)**.</span><span class="sxs-lookup"><span data-stu-id="9a975-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="9a975-110">Andernfalls wird die Normalisierungsregel Parken niemals ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9a975-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9a975-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a975-111">See also</span></span>

#### 

[<span data-ttu-id="9a975-112">Erstellen oder Ändern von Wähleinstellungen in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9a975-112">Create or modify a dial plan in Skype for Business Server 2015</span></span>](dial-plans.md)

