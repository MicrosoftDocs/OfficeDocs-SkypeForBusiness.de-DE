---
title: Cmdlets in Skype for Business Online, die keinen Bereich oder keine Identität verwenden
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3dfc2ee8cd812b597f363934475d1996f2e42a0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727595"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a><span data-ttu-id="ff2e1-102">Cmdlets in Skype for Business Online, die keinen Bereich oder keine Identität verwenden</span><span class="sxs-lookup"><span data-stu-id="ff2e1-102">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>

 


<span data-ttu-id="ff2e1-103">Die beim Ändern der zulässigen Listen und blockierten Listen verwendeten Cmdlets (Listen, die ermitteln, mit welchen externen Organisationen ihre Benutzer kommunizieren dürfen) verwenden weder einen Bereich noch eine Identität.</span><span class="sxs-lookup"><span data-stu-id="ff2e1-103">The cmdlets used when modifying the allowed lists and blocked lists (lists that determine which outside organizations your users are allowed to communicate with) do not use either a scope or an Identity.</span></span> <span data-ttu-id="ff2e1-104">In der Tat hat das Cmdlet **New-CsEdgeAllowAllKnownDomains** keinerlei Parameter.</span><span class="sxs-lookup"><span data-stu-id="ff2e1-104">In fact, the **New-CsEdgeAllowAllKnownDomains** cmdlet does not have any parameters whatsoever.</span></span> <span data-ttu-id="ff2e1-105">Bei den Cmdlets, die weder einen Bereich noch eine Identität verwenden, handelt es sich um folgende:</span><span class="sxs-lookup"><span data-stu-id="ff2e1-105">The cmdlets that do not use either a scope or an Identity are:</span></span>

  - <span data-ttu-id="ff2e1-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ff2e1-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ff2e1-107">[New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ff2e1-107">[New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ff2e1-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ff2e1-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))</span></span>

<span data-ttu-id="ff2e1-109">Beachten Sie, dass Sie mit dem Cmdlet **New-CsEdgeAllowList** und dem Cmdlet **New-CsEdgeDomainPattern** den Parameter Domain angeben müssen.</span><span class="sxs-lookup"><span data-stu-id="ff2e1-109">Note that, with both the **New-CsEdgeAllowList** cmdlet and the **New-CsEdgeDomainPattern** cmdlet, you must include the Domain parameter.</span></span> <span data-ttu-id="ff2e1-110">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ff2e1-110">For example:</span></span>

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a><span data-ttu-id="ff2e1-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff2e1-111">See Also</span></span>


[<span data-ttu-id="ff2e1-112">Identitäten, Bereiche und Mandanten in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ff2e1-112">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="ff2e1-113">[Die Lync Online-Cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ff2e1-113">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

