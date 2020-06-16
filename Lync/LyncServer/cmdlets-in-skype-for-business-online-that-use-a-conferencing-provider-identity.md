---
title: Cmdlets in Skype for Business Online, die eine Konferenzanbieter Identität verwenden
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
ms.openlocfilehash: accaad94f5e29863ac948ea64d061d23b811105f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755127"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a>Cmdlets in Skype for Business Online, die eine Konferenzanbieter Identität verwenden

 


Wenn Sie Informationen zu allen Audiokonferenz-Anbietern zurückgeben möchten, mit denen Ihre Organisation zusammengeschlossen hat, können Sie einfach das [Get-CsAudioConferencingProvider-](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) Cmdlet ohne Parameter aufrufen:

    Get-CsAudioConferencingProvider

Wenn Sie die zurückgegebenen Daten auf einen einzelnen Anbieter begrenzen möchten (in diesem Beispiel den Anbieter "Contoso Audio Services"), verwenden Sie den Parameter "Identity":

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

Es gibt nur ein Skype for Business Online-Cmdlet, das eine Anbieter-ID für Audiokonferenzen akzeptiert:

  - [Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))

## <a name="see-also"></a>Siehe auch


[Identitäten, Bereiche und Mandanten in Skype for Business Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Die Skype for Business Online-Cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

