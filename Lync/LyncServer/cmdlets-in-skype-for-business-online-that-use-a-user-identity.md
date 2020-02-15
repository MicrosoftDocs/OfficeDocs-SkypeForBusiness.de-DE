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
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a>Cmdlets in Skype for Business Online, die eine Benutzeridentität verwenden

 


In Skype for Business Online gibt es eine Reihe unterschiedlicher Methoden, um auf eine einzelne Benutzeridentität zu verweisen:

  - Verwenden Sie den Active Directory-Domänendienste Anzeigenamen des Benutzers. Beispiel:
    
        -Identity "Ken Myer"

  - Verwenden Sie die SIP-Adresse des Benutzers. Beispiel:
    
        -Identity "sip:kenmyer@litwareinc.com"

  - Verwenden Sie den UPN des Benutzers. Beispiel:
    
        -Identity " kenmyer@litwareinc.com"

  - Verwenden Sie den Distinguished Name des Benutzers Active Directory-Domänendienste. Beispiel:
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

Die folgenden Cmdlets akzeptieren eine Benutzeridentität:

  - [Disable-csmeetingroom "](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))

  - [Enable-csmeetingroom "](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))

  - [Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))

  - [Get-csmeetingroom "](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))

  - [Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))

  - [Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))

  - [New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))

  - [Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))

  - [Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))

  - [Gruppe-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))

  - [Gruppe-csmeetingroom "](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))

  - [Gruppe-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))

Beachten Sie, dass beim Aufruf eines der Cmdlets **Get-CS** keine Benutzeridentität angegeben werden muss. In diesem Fall geben die Cmdlets alle Instanzen des angegebenen Elements zurück. Mit diesem Befehl werden beispielsweise Informationen zu allen Benutzern zurückgegeben, die für Skype for Business Online aktiviert wurden:

    Get-CsOnlineUser

Der Parameter Identity ist nur erforderlich, wenn Sie Informationen für einen bestimmten Benutzer zurückgeben möchten:

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a>Siehe auch


[Identitäten, Bereiche und Mandanten in Skype for Business Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Die Skype for Business Online-Cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

