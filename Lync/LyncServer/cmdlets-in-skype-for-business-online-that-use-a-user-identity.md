---
title: Cmdlets, in denen eine Benutzeridentität verwendet wird
TOCTitle: Cmdlets, in denen eine Benutzeridentität verwendet wird
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56269337
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cmdlets, in denen eine Benutzeridentität verwendet wird

 

_**Letztes Änderungsdatum des Themas:** 2015-06-22_

In Skype for Business Online gibt es mehrere Möglichkeiten, auf eine einzelne Benutzeridentität zu verweisen:

  - Sie können den Active Directory-Domänendienste-Anzeigenamen des Benutzers verwenden. Beispiel:
    
        -Identity "Ken Myer"

  - Sie können die SIP-Adresse des Benutzers verwenden. Beispiel:
    
        -Identity "sip:kenmyer@litwareinc.com"

  - Sie können den UPN des Benutzers verwenden. Beispiel:
    
        -Identity " kenmyer@litwareinc.com"

  - Sie können den Active Directory-Domänendienste-Distinguished Namen des Benutzers verwenden. Beispiel:
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online-Mandanten,DC=litwareinc,DC=com"

Für die folgenden Cmdlets kann eine Benutzeridentität angegeben werden.

  - [Disable-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Disable-CsMeetingRoom)

  - [Enable-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Enable-CsMeetingRoom)

  - [Get-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExUmContact)

  - [Get-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingRoom)

  - [Get-CsOnlineUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsOnlineUser?view=skype-ps)

  - [Get-CsUserAcp](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUserAcp)

  - [New-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExUmContact)

  - [Remove-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExUmContact)

  - [Remove-CsUserAcp](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsUserAcp)

  - [Set-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExUmContact)

  - [Set-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMeetingRoom)

  - [Set-CsUserAcp](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUserAcp)

Sie müssen keine Benutzeridentität angeben, wenn Sie eines der **Get-Cs**-Cmdlets aufrufen. Das jeweils aufgerufene Cmdlet gibt alle Instanzen des angegebenen Elements zurück. Der folgende Befehl gibt beispielsweise Informationen zu allen Benutzern zurück, die für Skype for Business Online aktiviert wurden:

    Get-CsOnlineUser

Der Parameter **Identity** ist nur erforderlich, wenn Informationen zu einem bestimmten Benutzer zurückgegeben werden sollen:

    Get-CsOnlineUser -Identity "Ken Myer"

## Siehe auch

#### Konzepte

[Identitäten, Bereiche und Mandanten](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Die Lync Online-Cmdlets](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

