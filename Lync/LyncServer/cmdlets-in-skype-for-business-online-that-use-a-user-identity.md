---
title: Cmdlets in Skype for Business Online, die eine Benutzeridentität verwenden
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce46e700a65f00625aeebad1032c54a5affeaa19
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233113"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a><span data-ttu-id="a0905-102">Cmdlets in Skype for Business Online, die eine Benutzeridentität verwenden</span><span class="sxs-lookup"><span data-stu-id="a0905-102">Cmdlets in Skype for Business Online that use a user identity</span></span>

 


<span data-ttu-id="a0905-103">In Skype for Business Online gibt es eine Reihe von unterschiedlichen Möglichkeiten, auf eine einzelne Benutzeridentität zu verweisen:</span><span class="sxs-lookup"><span data-stu-id="a0905-103">In Skype for Business Online, there are a number of different ways to reference an individual user Identity:</span></span>

  - <span data-ttu-id="a0905-104">Verwenden Sie den Anzeigenamen der Active Directory-Domänendienste des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="a0905-104">Use the user’s Active Directory Domain Services display name.</span></span> <span data-ttu-id="a0905-105">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a0905-105">For example:</span></span>
    
        -Identity "Ken Myer"

  - <span data-ttu-id="a0905-106">Verwenden Sie die SIP-Adresse des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="a0905-106">Use the user’s SIP address.</span></span> <span data-ttu-id="a0905-107">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a0905-107">For example:</span></span>
    
        -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="a0905-108">Verwenden Sie den UPN des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="a0905-108">Use the user’s UPN.</span></span> <span data-ttu-id="a0905-109">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a0905-109">For example:</span></span>
    
        -Identity " kenmyer@litwareinc.com"

  - <span data-ttu-id="a0905-110">Verwenden Sie den Distinguished Name für den Active Directory-Domänendienst des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="a0905-110">Use the user’s Active Directory Domain Services distinguished name.</span></span> <span data-ttu-id="a0905-111">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a0905-111">For example:</span></span>
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

<span data-ttu-id="a0905-112">Die folgenden Cmdlets akzeptieren eine Benutzeridentität:</span><span class="sxs-lookup"><span data-stu-id="a0905-112">The following cmdlets accept a user Identity:</span></span>

  - <span data-ttu-id="a0905-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a0905-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a0905-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a0905-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a0905-115">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a0905-115">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a0905-116">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a0905-116">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a0905-117">[Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a0905-117">[Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a0905-118">[Get-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a0905-118">[Get-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a0905-119">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a0905-119">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a0905-120">[Remove-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a0905-120">[Remove-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a0905-121">[Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a0905-121">[Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a0905-122">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a0905-122">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a0905-123">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a0905-123">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a0905-124">[Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a0905-124">[Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))</span></span>

<span data-ttu-id="a0905-125">Beachten Sie, dass Sie beim Aufrufen eines der **Get-CS-** Cmdlets keine Benutzeridentität angeben müssen.</span><span class="sxs-lookup"><span data-stu-id="a0905-125">Note that you do not need to specify a user Identity when calling one of the **Get-Cs** cmdlets.</span></span> <span data-ttu-id="a0905-126">In diesem Fall geben die Cmdlets alle Instanzen des angegebenen Elements zurück.</span><span class="sxs-lookup"><span data-stu-id="a0905-126">In this case, the cmdlets return all the instances of the specified item.</span></span> <span data-ttu-id="a0905-127">Dieser Befehl gibt beispielsweise Informationen zu allen Benutzern zurück, die für Skype for Business Online aktiviert wurden:</span><span class="sxs-lookup"><span data-stu-id="a0905-127">For example, this command returns information about all the users who have been enabled for Skype for Business Online:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="a0905-128">Der Parameter Identity ist nur erforderlich, wenn Sie Informationen für einen bestimmten Benutzer zurückgeben möchten:</span><span class="sxs-lookup"><span data-stu-id="a0905-128">The Identity parameter is required only if you want to return information for a specific user:</span></span>

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a><span data-ttu-id="a0905-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0905-129">See Also</span></span>


[<span data-ttu-id="a0905-130">Identitäten, Bereiche und Mandanten in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a0905-130">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="a0905-131">[Die Lync Online-Cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a0905-131">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

