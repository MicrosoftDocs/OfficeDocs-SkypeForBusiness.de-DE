---
title: Überprüfen der Normalisierungsregeln für das Parken von Anrufen in Skype für Unternehmen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Informationen Sie zu Normalisierungsregeln für das Parken von Anrufen in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 6f27daca3ef3f1bcdc4c70f04b92ccaa29a569a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892265"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a><span data-ttu-id="ebd7e-103">Überprüfen der Normalisierungsregeln für das Parken von Anrufen in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="ebd7e-103">Verify normalization rules for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="ebd7e-104">Informationen Sie zu Normalisierungsregeln für das Parken von Anrufen in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="ebd7e-105">Parken Orbits müssen nicht normalisiert werden.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="ebd7e-106">Überprüfen Sie Ihren Wählplänen, um sicherzustellen, dass Ihre orbitnummern nicht normalisiert werden.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="ebd7e-107">Wenn Sie eine zusätzliche Normalisierungsregel aus, um zu verhindern, dass Ihre Orbits normalisierende erstellen müssen, führen Sie das Verfahren in [Erstellen oder Ändern von Wähleinstellungen in Skype für Business Server](dial-plans.md) so definieren Sie eine neue Normalisierungsregel also dieses **Muster abgleichen** identifiziert den orbitbereich und **übersetzungsmuster** **$1**ist.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="ebd7e-108">Angenommen, Ihr orbitbereich zum Parken von Anrufen 7000-7999, das **Vergleichsmuster** ist **^(7\d{3})$** und **übersetzungsmuster** **$1**ist.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ebd7e-109">Achten Sie darauf, dass die Standard-Normalisierungsregel in Ihren Wählplänen keine enthält **^(\d\*)**.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="ebd7e-110">Andernfalls wird die Normalisierungsregel Parken niemals ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ebd7e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebd7e-111">See also</span></span>

[<span data-ttu-id="ebd7e-112">Erstellen oder Ändern von Wähleinstellungen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="ebd7e-112">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

