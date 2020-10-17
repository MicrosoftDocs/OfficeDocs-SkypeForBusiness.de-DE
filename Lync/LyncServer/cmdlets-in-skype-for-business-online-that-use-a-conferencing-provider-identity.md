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

