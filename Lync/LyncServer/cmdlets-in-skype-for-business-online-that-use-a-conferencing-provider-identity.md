---
title: Cmdlets, in denen eine Konferenzanbieteridentität verwendet wird
TOCTitle: Cmdlets, in denen eine Konferenzanbieteridentität verwendet wird
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56269342
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cmdlets, in denen eine Konferenzanbieteridentität verwendet wird

 

_**Letztes Änderungsdatum des Themas:** 2015-06-22_

Wenn Sie Informationen zu allen Audiokonferenzanbietern abrufen möchten, mit denen Ihre Organisation Verträge abgeschlossen hat, rufen Sie einfach das Cmdlet [Get-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsAudioConferencingProvider) ohne einen Parameter auf:

    Get-CsAudioConferencingProvider

Wenn Sie nur die Daten für einen einzigen Anbieter abrufen möchten (in diesem Beispiel der Anbieter Contoso Audiodienste), verwenden Sie den Parameter **Identity**:

    Get-CsAudioConferencingProvider -Identity "Contoso Audiodienste"

Es gibt nur ein Skype for Business Online-Cmdlet, das die ID eines Audiokonferenzanbieters akzeptiert:

  - [Get-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsAudioConferencingProvider)

## Siehe auch

#### Konzepte

[Identitäten, Bereiche und Mandanten](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Die Lync Online-Cmdlets](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

