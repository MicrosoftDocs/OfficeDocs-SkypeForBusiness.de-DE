---
title: Cmdlets in Skype for Business Online, die nur den globalen Bereich verwenden
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: b97f3c8d9ca7dda0b96db211192350184cbf27b1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755097"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a>Cmdlets in Skype for Business Online, die nur den globalen Bereich verwenden

 


Eine Reihe von Skype for Business Online Einstellungen sind nur auf *globaler*Ebene verfügbar. Dies bedeutet, dass es eine einzelne Auflistung von Einstellungen gibt, die für alle Benutzer gilt, die diesem Mandanten zugewiesen sind. (Jeder Mandant verfügt über eine eigene eindeutige Auflistung globaler Einstellungen.) Wenn Sie Cmdlets verwenden, die auf den globalen Bereich beschränkt sind, ist der Parameter Identity optional. Wenn Sie beispielsweise Besprechungs Konfigurationseinstellungen abrufen möchten, können Sie diesen Befehl verwenden:

    Get-CsMeetingConfiguration -Identity "global"

Alternativ können Sie den Parameter Identity weglassen und stattdessen diesen einfacheren Befehl verwenden:

    Get-CsMeetingConfiguration

Da nur eine globale Auflistung von Besprechungs Konfigurationseinstellungen vorhanden ist, geben die beiden Befehle exakt dieselben Informationen zurück. Der Parameter Identity kann auch ausgelassen werden, wenn eines der Cmdlets der **Gruppe-cs** verwendet wird. Diese beiden Befehle sind identisch:

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

Die beiden Befehle sind identisch, da Windows PowerShell standardmäßig die globale Auflistung ändert, wenn Sie den Parameter Identity nicht einschließen.

Die folgenden Cmdlets funktionieren nur auf globaler Ebene:

  - [Get-CsImFilterConfiguration](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))

  - [Get-CsMeetingConfiguration](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))

  - [Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))

  - [Get-CsTenantPublicProvider](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))

  - [Remove-CsVoicePolicy](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))

  - [Gruppe-CsMeetingConfiguration](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))

  - [Gruppe-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))

Beachten Sie, dass das Cmdlet **Remove-CsVoicePolicy** so etwas wie eine Anomalie ist. Für dieses Cmdlet müssen Sie zunächst den Parameter Identity einschließen:

    Remove-CsVoicePolicy -Identity "global"

Zweitens löscht das Cmdlet **Remove-CsVoicePolicy** die globale VoIP-Richtlinie nicht tatsächlich; In Skype for Business Online können globale Richtlinien oder Konfigurationseinstellungen nicht gelöscht werden. Das Cmdlet macht es möglich, dass Sie alle Eigenschaften in der globalen VoIP-Richtlinie auf ihre Standardwerte zurücksetzen. Beispielsweise ist die AllowCallForwarding-Eigenschaft standardmäßig auf false festgelegt. AllowCallForwarding wurde jedoch möglicherweise geändert, wobei der Wert nun auf true festgelegt wurde. Wenn Sie das Cmdlet **Remove-CsVoicePolicy** ausführen, wird die AllowCallForwarding-Eigenschaft auf den Standardwert zurückgesetzt: false. In der folgenden Tabelle wird dieses Szenario zusammengefasst:


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
<td><p>Nach dem Ausführen des Cmdlets " <strong>Remove-CsVoicePolicy</strong> "</p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a>Siehe auch


[Identitäten, Bereiche und Mandanten in Skype for Business Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Die Skype for Business Online-Cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

