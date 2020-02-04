---
title: Cmdlets in Skype for Business Online, die nur den globalen Bereich verwenden
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use only the global scope
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56558800
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5610649295fdf4089372d9c59e4ccb51228c1fc2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728105"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a>Cmdlets in Skype for Business Online, die nur den globalen Bereich verwenden

 


Eine Reihe von Skype for Business Online-Einstellungen steht nur im *globalen Bereich*zur Verfügung. Das bedeutet, dass es eine einzelne Sammlung von Einstellungen gibt, die für alle Benutzer gelten, die diesem Mandanten zugewiesen sind. (Jeder Mandant hat eine eigene eindeutige Sammlung globaler Einstellungen.) Wenn Sie Cmdlets verwenden, die auf den globalen Bereich beschränkt sind, ist der Parameter Identity optional. Wenn Sie beispielsweise die Einstellungen für die besprechungskonfiguration abrufen möchten, können Sie diesen Befehl verwenden:

    Get-CsMeetingConfiguration -Identity "global"

Alternativ können Sie den Parameter Identity weglassen und stattdessen diesen einfacheren Befehl verwenden:

    Get-CsMeetingConfiguration

Da nur eine globale Sammlung von Einstellungen für die besprechungskonfiguration vorhanden ist, geben die beiden Befehle exakt dieselben Informationen zurück. Der Parameter Identity kann auch bei Verwendung eines der Cmdlets für die **Satz-CS-** Cmdlets ausgelassen werden. Diese beiden Befehle sind identisch:

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

Die beiden Befehle sind identisch, da Windows PowerShell standardmäßig die globale Sammlung ändert, wenn Sie den Parameter Identity nicht hinzufügen.

Die folgenden Cmdlets werden nur im globalen Bereich ausgeführt:

  - [Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))

  - [Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))

  - [Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))

  - [Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))

  - [Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))

  - [Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))

  - [Satz-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))

Beachten Sie, dass es sich bei dem Cmdlet **Remove-CsVoicePolicy** um eine Anomalie handelt. Zunächst müssen Sie mit diesem Cmdlet den Parameter Identity einbeziehen:

    Remove-CsVoicePolicy -Identity "global"

Zweitens löscht das Cmdlet **Remove-CsVoicePolicy** die globale VoIP-Richtlinie nicht tatsächlich; In Skype for Business Online ist es nicht möglich, globale Richtlinien oder Konfigurationseinstellungen zu löschen. Mit dem Cmdlet können Sie alle Eigenschaften in der globalen VoIP-Richtlinie auf ihre Standardwerte zurücksetzen. Standardmäßig ist die AllowCallForwarding-Eigenschaft beispielsweise auf false festgelegt. AllowCallForwarding wurde jedoch möglicherweise geändert, wobei der Wert nun auf true festgelegt ist. Wenn Sie das Cmdlet **Remove-CsVoicePolicy** ausführen, wird die AllowCallForwarding-Eigenschaft auf den Standardwert zurückgesetzt: false. In der folgenden Tabelle ist dieses Szenario zusammengefasst:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>AllowCallForwarding-Wert</th>
<th>Szenario</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Falsch</p></td>
<td><p>Standardwert</p></td>
</tr>
<tr class="even">
<td><p>Wahr</p></td>
<td><p>Nachdem die globale Richtlinie geändert wurde</p></td>
</tr>
<tr class="odd">
<td><p>Falsch</p></td>
<td><p>Nachdem das Cmdlet " <strong>Remove-CsVoicePolicy</strong> " ausgeführt wurde</p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a>Siehe auch


[Identitäten, Bereiche und Mandanten in Skype for Business Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Die Lync Online-Cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

