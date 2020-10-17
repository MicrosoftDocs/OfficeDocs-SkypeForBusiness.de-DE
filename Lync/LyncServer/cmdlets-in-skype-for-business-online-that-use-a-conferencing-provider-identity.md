---
title: Cmdlets in Skype for Business Online, die eine Konferenzanbieter Identität verwenden
description: Cmdlets in Skype for Business Online, die die Identität eines Konferenz Anbieters verwenden.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a conferencing provider identity
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56558858
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61ab4fb410878ca73314b73737948d9961462c87
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545731"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a><span data-ttu-id="bfd40-103">Cmdlets in Skype for Business Online, die eine Konferenzanbieter Identität verwenden</span><span class="sxs-lookup"><span data-stu-id="bfd40-103">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>

 


<span data-ttu-id="bfd40-104">Wenn Sie Informationen zu allen Audiokonferenz-Anbietern zurückgeben möchten, mit denen Ihre Organisation zusammengeschlossen hat, können Sie einfach das [Get-CsAudioConferencingProvider-](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) Cmdlet ohne Parameter aufrufen:</span><span class="sxs-lookup"><span data-stu-id="bfd40-104">To return information about all of the audio conferencing providers that your organization has contracted with, you can simply call the [Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) cmdlet without any parameters:</span></span>

    Get-CsAudioConferencingProvider

<span data-ttu-id="bfd40-105">Wenn Sie die zurückgegebenen Daten auf einen einzelnen Anbieter begrenzen möchten (in diesem Beispiel den Anbieter "Contoso Audio Services"), verwenden Sie den Parameter "Identity":</span><span class="sxs-lookup"><span data-stu-id="bfd40-105">If you want to limit the returned data to a single provider (in this example, the provider Contoso Audio Services), then use the Identity parameter:</span></span>

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

<span data-ttu-id="bfd40-106">Es gibt nur ein Skype for Business Online-Cmdlet, das eine Anbieter-ID für Audiokonferenzen akzeptiert:</span><span class="sxs-lookup"><span data-stu-id="bfd40-106">There is only one Skype for Business Online cmdlet that accepts an audio conferencing provider ID:</span></span>

  - <span data-ttu-id="bfd40-107">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="bfd40-107">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="bfd40-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bfd40-108">See Also</span></span>


[<span data-ttu-id="bfd40-109">Identitäten, Bereiche und Mandanten in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bfd40-109">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="bfd40-110">[Die Skype for Business Online-Cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="bfd40-110">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

