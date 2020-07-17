---
title: Cmdlets in Skype for Business Online, die den Parameter "Mandant" verwenden
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 352a33fcff5db306b62535c28fb4a2b2dd766bea
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755041"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a><span data-ttu-id="f735f-102">Cmdlets in Skype for Business Online, die den Parameter "Mandant" verwenden</span><span class="sxs-lookup"><span data-stu-id="f735f-102">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>

 


<span data-ttu-id="f735f-103">Wenn Sie Ihre Einstellungen für öffentliche Anbieter ändern, müssen Sie immer eine Mandanten Identität angeben. Dies gilt auch dann, wenn Sie nur einen einzigen Mandanten haben.</span><span class="sxs-lookup"><span data-stu-id="f735f-103">When modifying your public provider settings, you always need to supply a Tenant identity; this is true even if you only have a single tenant.</span></span> <span data-ttu-id="f735f-104">Mit dem folgenden Befehl wird beispielsweise Windows Live als einziger öffentlicher Anbieter festgelegt, mit dem Ihre Benutzer kommunizieren können:</span><span class="sxs-lookup"><span data-stu-id="f735f-104">For example, this command sets Windows Live as the only public provider your users are allowed to communicate with:</span></span>

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

<span data-ttu-id="f735f-105">Glücklicherweise müssen Sie nicht jedes Mal, wenn Sie eines dieser Cmdlets ausführen, die Mandanten-ID eingeben (beispielsweise bf19b7db-6960-41e5-A139-2aa373474354).</span><span class="sxs-lookup"><span data-stu-id="f735f-105">Fortunately, you do not need to type the Tenant ID (for example, bf19b7db-6960-41e5-a139-2aa373474354) each time you run one of these cmdlets.</span></span> <span data-ttu-id="f735f-106">Stattdessen können Sie die Mandanten-ID abrufen, indem Sie das Cmdlet [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) ausführen, die Mandanten-ID in einer Variablen speichern und diese Variable dann verwenden, wenn Sie eines der anderen Cmdlets aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f735f-106">Instead, you can retrieve the Tenant ID by running the [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) cmdlet, storing the Tenant ID in a variable, and then using that variable when you call one of the other cmdlets.</span></span> <span data-ttu-id="f735f-107">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f735f-107">For example:</span></span>

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

<span data-ttu-id="f735f-108">Alternativ können Sie dies in einem einzigen Befehl durchführen, indem Sie die Mandanten-ID abrufen und diesen Wert dann an das Cmdlet "Cmdlet" "CsTenantPublicProvider" weiterleiten:</span><span class="sxs-lookup"><span data-stu-id="f735f-108">Alternatively, you can do this in a single command by retrieving the Tenant ID and then piping that value to the Set-CsTenantPublicProvider cmdlet:</span></span>

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

<span data-ttu-id="f735f-109">Sie müssen die Mandanten-ID nicht angeben, wenn Sie das **Get-CsTenant-** Cmdlet aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f735f-109">You do not need to specify the tenant ID when calling the **Get-CsTenant** cmdlet.</span></span> <span data-ttu-id="f735f-110">Dieser Befehl gibt Informationen zu Ihrem Mandanten zurück:</span><span class="sxs-lookup"><span data-stu-id="f735f-110">This command returns information about your tenant:</span></span>

    Get-CsTenant

<span data-ttu-id="f735f-111">Die folgenden Cmdlets akzeptieren eine Mandanten Identität.</span><span class="sxs-lookup"><span data-stu-id="f735f-111">The following cmdlets accept a tenant identity.</span></span> <span data-ttu-id="f735f-112">In diesen Fällen ist der Parameter jedoch optional und muss beim Aufruf des Cmdlets nicht eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f735f-112">However, in these cases, the parameter is optional and does not need to be entered when calling the cmdlet.</span></span> <span data-ttu-id="f735f-113">Stattdessen werden Windows PowerShell die Mandanten Identität basierend auf dem Skype for Business Online Mandanten, mit dem Sie derzeit verbunden sind, effektiv eingeben:</span><span class="sxs-lookup"><span data-stu-id="f735f-113">Instead, Windows PowerShell will effectively enter the tenant identity for you based on the Skype for Business Online tenant you are currently connected to:</span></span>

  - <span data-ttu-id="f735f-114">[Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="f735f-114">[Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span></span>

  - <span data-ttu-id="f735f-115">[Gruppe-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="f735f-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span></span>

  - <span data-ttu-id="f735f-116">[Gruppe-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="f735f-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span></span>

  - <span data-ttu-id="f735f-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="f735f-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="f735f-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="f735f-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="f735f-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="f735f-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span></span>

<span data-ttu-id="f735f-120">Beispielsweise kann das **Get-CsTenantFederationConfiguration-** Cmdlet mithilfe dieses Befehls aufgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="f735f-120">For example, the **Get-CsTenantFederationConfiguration** cmdlet can be called by using this command:</span></span>

    Get-CsTenantFederationConfiguration

<span data-ttu-id="f735f-121">Obwohl dies nicht erforderlich ist, können Sie den Parameter Mandanten einschließen, wenn Sie Get-CsTenantFederationConfiguration aufrufen:</span><span class="sxs-lookup"><span data-stu-id="f735f-121">Although not required, you can include the Tenant parameter when calling Get-CsTenantFederationConfiguration :</span></span>

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a><span data-ttu-id="f735f-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f735f-122">See Also</span></span>


[<span data-ttu-id="f735f-123">Identitäten, Bereiche und Mandanten in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f735f-123">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="f735f-124">[Die Skype for Business Online-Cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="f735f-124">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

