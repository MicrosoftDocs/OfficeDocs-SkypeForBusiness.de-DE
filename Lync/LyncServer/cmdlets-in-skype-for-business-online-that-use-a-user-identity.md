---
title: Cmdlets in Skype for Business Online, die eine Benutzeridentität verwenden
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 8310d5e25b5fc3dd3ada43fcf3c8f899f60e5a7e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001260"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a><span data-ttu-id="78efc-102">Cmdlets in Skype for Business Online, die eine Benutzeridentität verwenden</span><span class="sxs-lookup"><span data-stu-id="78efc-102">Cmdlets in Skype for Business Online that use a user identity</span></span>

 


<span data-ttu-id="78efc-103">In Skype for Business Online gibt es eine Reihe unterschiedlicher Methoden, um auf eine einzelne Benutzeridentität zu verweisen:</span><span class="sxs-lookup"><span data-stu-id="78efc-103">In Skype for Business Online, there are a number of different ways to reference an individual user Identity:</span></span>

  - <span data-ttu-id="78efc-104">Verwenden Sie den Active Directory-Domänendienste Anzeigenamen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="78efc-104">Use the user’s Active Directory Domain Services display name.</span></span> <span data-ttu-id="78efc-105">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="78efc-105">For example:</span></span>
    
        -Identity "Ken Myer"

  - <span data-ttu-id="78efc-106">Verwenden Sie die SIP-Adresse des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="78efc-106">Use the user’s SIP address.</span></span> <span data-ttu-id="78efc-107">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="78efc-107">For example:</span></span>
    
        -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="78efc-108">Verwenden Sie den UPN des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="78efc-108">Use the user’s UPN.</span></span> <span data-ttu-id="78efc-109">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="78efc-109">For example:</span></span>
    
        -Identity " kenmyer@litwareinc.com"

  - <span data-ttu-id="78efc-110">Verwenden Sie den Distinguished Name des Benutzers Active Directory-Domänendienste.</span><span class="sxs-lookup"><span data-stu-id="78efc-110">Use the user’s Active Directory Domain Services distinguished name.</span></span> <span data-ttu-id="78efc-111">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="78efc-111">For example:</span></span>
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

<span data-ttu-id="78efc-112">Die folgenden Cmdlets akzeptieren eine Benutzeridentität:</span><span class="sxs-lookup"><span data-stu-id="78efc-112">The following cmdlets accept a user Identity:</span></span>

  - <span data-ttu-id="78efc-113">[Disable-csmeetingroom "](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="78efc-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span></span>

  - <span data-ttu-id="78efc-114">[Enable-csmeetingroom "](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="78efc-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span></span>

  - <span data-ttu-id="78efc-115">[Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="78efc-115">[Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span></span>

  - <span data-ttu-id="78efc-116">[Get-csmeetingroom "](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="78efc-116">[Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span></span>

  - <span data-ttu-id="78efc-117">[Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="78efc-117">[Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span></span>

  - <span data-ttu-id="78efc-118">[Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="78efc-118">[Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span></span>

  - <span data-ttu-id="78efc-119">[New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="78efc-119">[New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span></span>

  - <span data-ttu-id="78efc-120">[Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="78efc-120">[Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span></span>

  - <span data-ttu-id="78efc-121">[Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="78efc-121">[Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span></span>

  - <span data-ttu-id="78efc-122">[Gruppe-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="78efc-122">[Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span></span>

  - <span data-ttu-id="78efc-123">[Gruppe-csmeetingroom "](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="78efc-123">[Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span></span>

  - <span data-ttu-id="78efc-124">[Gruppe-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="78efc-124">[Set-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span></span>

<span data-ttu-id="78efc-125">Beachten Sie, dass beim Aufruf eines der Cmdlets **Get-CS** keine Benutzeridentität angegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="78efc-125">Note that you do not need to specify a user Identity when calling one of the **Get-Cs** cmdlets.</span></span> <span data-ttu-id="78efc-126">In diesem Fall geben die Cmdlets alle Instanzen des angegebenen Elements zurück.</span><span class="sxs-lookup"><span data-stu-id="78efc-126">In this case, the cmdlets return all the instances of the specified item.</span></span> <span data-ttu-id="78efc-127">Mit diesem Befehl werden beispielsweise Informationen zu allen Benutzern zurückgegeben, die für Skype for Business Online aktiviert wurden:</span><span class="sxs-lookup"><span data-stu-id="78efc-127">For example, this command returns information about all the users who have been enabled for Skype for Business Online:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="78efc-128">Der Parameter Identity ist nur erforderlich, wenn Sie Informationen für einen bestimmten Benutzer zurückgeben möchten:</span><span class="sxs-lookup"><span data-stu-id="78efc-128">The Identity parameter is required only if you want to return information for a specific user:</span></span>

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a><span data-ttu-id="78efc-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78efc-129">See Also</span></span>


[<span data-ttu-id="78efc-130">Identitäten, Bereiche und Mandanten in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="78efc-130">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="78efc-131">[Die Skype for Business Online-Cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="78efc-131">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

