---
title: Cmdlets in Skype for Business Online, die eine Konferenzanbieter Identität verwenden
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 9dc5438a0fe246b1e988d60a0e6ce1ac3d3f6d67
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726715"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a>Cmdlets in Skype for Business Online, die eine Konferenzanbieter Identität verwenden

 


Wenn Sie Informationen zu allen Audiokonferenz-Anbietern zurückgeben möchten, mit denen Ihre Organisation einen Vertrag abgeschlossen hat, können Sie einfach das Cmdlet [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\)) ohne Parameter aufrufen:

    Get-CsAudioConferencingProvider

Wenn Sie die zurückgegebenen Daten auf einen einzelnen Anbieter einschränken möchten (in diesem Beispiel den Anbieter Contoso-Audiodienste), verwenden Sie den Parameter Identity:

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

Es gibt nur ein Skype for Business Online-Cmdlet, das eine Audiokonferenz-Anbieter-ID akzeptiert:

  - [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\))

## <a name="see-also"></a>Siehe auch


[Identitäten, Bereiche und Mandanten in Skype for Business Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Die Lync Online-Cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

