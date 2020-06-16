---
title: Cmdlets in Skype for Business Online, die keinen Bereich oder eine Identität verwenden
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ade4dee78fff151530e0d76279fdbfaeade720b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755315"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a><span data-ttu-id="bb482-102">Cmdlets in Skype for Business Online, die keinen Bereich oder eine Identität verwenden</span><span class="sxs-lookup"><span data-stu-id="bb482-102">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>

 


<span data-ttu-id="bb482-103">Die beim Ändern der zulässigen Listen und blockierten Listen verwendeten Cmdlets (Listen, die bestimmen, mit welchen externen Organisationen ihre Benutzer kommunizieren dürfen) verwenden weder einen Bereich noch eine Identität.</span><span class="sxs-lookup"><span data-stu-id="bb482-103">The cmdlets used when modifying the allowed lists and blocked lists (lists that determine which outside organizations your users are allowed to communicate with) do not use either a scope or an Identity.</span></span> <span data-ttu-id="bb482-104">Das **New-CsEdgeAllowAllKnownDomains-** Cmdlet hat tatsächlich keine Parameter.</span><span class="sxs-lookup"><span data-stu-id="bb482-104">In fact, the **New-CsEdgeAllowAllKnownDomains** cmdlet does not have any parameters whatsoever.</span></span> <span data-ttu-id="bb482-105">Die Cmdlets, die weder einen Bereich noch eine Identität verwenden, sind:</span><span class="sxs-lookup"><span data-stu-id="bb482-105">The cmdlets that do not use either a scope or an Identity are:</span></span>

  - <span data-ttu-id="bb482-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/library/jj994088\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="bb482-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/library/jj994088\(v=ocs.15\))</span></span>

  - <span data-ttu-id="bb482-107">[New-CsEdgeAllowList](https://technet.microsoft.com/library/jj994023\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="bb482-107">[New-CsEdgeAllowList](https://technet.microsoft.com/library/jj994023\(v=ocs.15\))</span></span>

  - <span data-ttu-id="bb482-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/library/jj994040\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="bb482-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/library/jj994040\(v=ocs.15\))</span></span>

<span data-ttu-id="bb482-109">Beachten Sie, dass Sie mit dem **New-CsEdgeAllowList** -Cmdlet und dem **New-CsEdgeDomainPattern-** Cmdlet den Domain-Parameter einschließen müssen.</span><span class="sxs-lookup"><span data-stu-id="bb482-109">Note that, with both the **New-CsEdgeAllowList** cmdlet and the **New-CsEdgeDomainPattern** cmdlet, you must include the Domain parameter.</span></span> <span data-ttu-id="bb482-110">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bb482-110">For example:</span></span>

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a><span data-ttu-id="bb482-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb482-111">See Also</span></span>


[<span data-ttu-id="bb482-112">Identitäten, Bereiche und Mandanten in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bb482-112">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="bb482-113">[Die Skype for Business Online-Cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="bb482-113">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

