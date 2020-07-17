---
title: Cmdlets in Skype for Business Online, die eine Benutzeridentität verwenden
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8aee680c6e55de62ff9d49724d3e480c00159aa4
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755107"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a><span data-ttu-id="ce34d-102">Cmdlets in Skype for Business Online, die eine Benutzeridentität verwenden</span><span class="sxs-lookup"><span data-stu-id="ce34d-102">Cmdlets in Skype for Business Online that use a user identity</span></span>

 


<span data-ttu-id="ce34d-103">In Skype for Business Online gibt es eine Reihe unterschiedlicher Methoden, um auf eine einzelne Benutzeridentität zu verweisen:</span><span class="sxs-lookup"><span data-stu-id="ce34d-103">In Skype for Business Online, there are a number of different ways to reference an individual user Identity:</span></span>

  - <span data-ttu-id="ce34d-104">Verwenden Sie den Active Directory-Domänendienste Anzeigenamen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="ce34d-104">Use the user’s Active Directory Domain Services display name.</span></span> <span data-ttu-id="ce34d-105">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ce34d-105">For example:</span></span>
    
        -Identity "Ken Myer"

  - <span data-ttu-id="ce34d-106">Verwenden Sie die SIP-Adresse des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="ce34d-106">Use the user’s SIP address.</span></span> <span data-ttu-id="ce34d-107">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ce34d-107">For example:</span></span>
    
        -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="ce34d-108">Verwenden Sie den UPN des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="ce34d-108">Use the user’s UPN.</span></span> <span data-ttu-id="ce34d-109">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ce34d-109">For example:</span></span>
    
        -Identity " kenmyer@litwareinc.com"

  - <span data-ttu-id="ce34d-110">Verwenden Sie den Distinguished Name des Benutzers Active Directory-Domänendienste.</span><span class="sxs-lookup"><span data-stu-id="ce34d-110">Use the user’s Active Directory Domain Services distinguished name.</span></span> <span data-ttu-id="ce34d-111">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ce34d-111">For example:</span></span>
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

<span data-ttu-id="ce34d-112">Die folgenden Cmdlets akzeptieren eine Benutzeridentität:</span><span class="sxs-lookup"><span data-stu-id="ce34d-112">The following cmdlets accept a user Identity:</span></span>

  - <span data-ttu-id="ce34d-113">[Disable-csmeetingroom "](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ce34d-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ce34d-114">[Enable-csmeetingroom "](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ce34d-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ce34d-115">[Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ce34d-115">[Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ce34d-116">[Get-csmeetingroom "](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ce34d-116">[Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ce34d-117">[Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ce34d-117">[Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ce34d-118">[Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ce34d-118">[Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ce34d-119">[New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ce34d-119">[New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ce34d-120">[Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ce34d-120">[Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ce34d-121">[Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ce34d-121">[Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ce34d-122">[Gruppe-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ce34d-122">[Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ce34d-123">[Gruppe-csmeetingroom "](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ce34d-123">[Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ce34d-124">[Gruppe-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ce34d-124">[Set-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span></span>

<span data-ttu-id="ce34d-125">Beachten Sie, dass beim Aufruf eines der Cmdlets **Get-CS** keine Benutzeridentität angegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="ce34d-125">Note that you do not need to specify a user Identity when calling one of the **Get-Cs** cmdlets.</span></span> <span data-ttu-id="ce34d-126">In diesem Fall geben die Cmdlets alle Instanzen des angegebenen Elements zurück.</span><span class="sxs-lookup"><span data-stu-id="ce34d-126">In this case, the cmdlets return all the instances of the specified item.</span></span> <span data-ttu-id="ce34d-127">Mit diesem Befehl werden beispielsweise Informationen zu allen Benutzern zurückgegeben, die für Skype for Business Online aktiviert wurden:</span><span class="sxs-lookup"><span data-stu-id="ce34d-127">For example, this command returns information about all the users who have been enabled for Skype for Business Online:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="ce34d-128">Der Parameter Identity ist nur erforderlich, wenn Sie Informationen für einen bestimmten Benutzer zurückgeben möchten:</span><span class="sxs-lookup"><span data-stu-id="ce34d-128">The Identity parameter is required only if you want to return information for a specific user:</span></span>

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a><span data-ttu-id="ce34d-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce34d-129">See Also</span></span>


[<span data-ttu-id="ce34d-130">Identitäten, Bereiche und Mandanten in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ce34d-130">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="ce34d-131">[Die Skype for Business Online-Cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ce34d-131">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

