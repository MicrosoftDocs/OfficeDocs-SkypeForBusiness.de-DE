---
title: Cmdlets, die keinen Bereich oder keine Identität verwenden
TOCTitle: Cmdlets, die keinen Bereich oder keine Identität verwenden
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56269310
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cmdlets, die keinen Bereich oder keine Identität verwenden

 

_**Letztes Änderungsdatum des Themas:** 2015-06-22_

Die Cmdlets, mit denen die Liste der zulässigen Domänen oder die Liste der blockierten Domänen geändert wird (Listen, mit denen festgelegt wird, mit welchen externen Organisationen Ihre Benutzer kommunizieren dürfen), verwenden weder einen Bereich, noch eine Identität. Tatsächlich gibt es für das Cmdlet **New-CsEdgeAllowAllKnownDomains** keinerlei Parameter. Die Cmdlets, die weder einen Bereich, noch eine Identität verwenden, sind:

  - [New-CsEdgeAllowAllKnownDomains](https://docs.microsoft.com/powershell/module/skype/New-CsEdgeAllowAllKnownDomains)

  - [New-CsEdgeAllowList](https://docs.microsoft.com/powershell/module/skype/New-CsEdgeAllowList)

  - [New-CsEdgeDomainPattern](https://docs.microsoft.com/powershell/module/skype/New-CsEdgeDomainPattern)

Beachten Sie jedoch, dass Sie bei den beiden Cmdlets **New-CsEdgeAllowList** und **New-CsEdgeDomainPattern** den Parameter **Domain** angeben müssen. parameter. Beispiel:

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## Siehe auch

#### Konzepte

[Identitäten, Bereiche und Mandanten](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Die Lync Online-Cmdlets](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

