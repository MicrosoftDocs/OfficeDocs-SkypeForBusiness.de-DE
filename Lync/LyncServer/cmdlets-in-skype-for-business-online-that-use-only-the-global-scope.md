---
title: Cmdlets, die nur den globalen Gültigkeitsbereich verwenden
TOCTitle: Cmdlets, die nur den globalen Gültigkeitsbereich verwenden
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56269250
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cmdlets, die nur den globalen Gültigkeitsbereich verwenden

 

_**Letztes Änderungsdatum des Themas:** 2015-06-22_

Eine Reihe von Skype for Business Online-Einstellungen stehen nur im *globalen Gültigkeitsbereich* zur Verfügung. Dies bedeutet, dass es eine einzelne Auflistung von Einstellungen gibt, die für alle Benutzer gelten, die diesem Mandanten zugeordnet sind. (Jeder Mandant verfügt über eine eigene eindeutige Auflistung von globalen Einstellungen.) Wenn Sie Cmdlets verwenden, die auf den globalen Gültigkeitsbereich beschränkt sind, ist der Parameter **Identity** optional. Zum Abrufen von Besprechungskonfigurationseinstellungen können beispielsweise den folgenden Befehl verwenden:

    Get-CsMeetingConfiguration -Identity "global"

Alternativ können Sie den Parameter **Identity** auslassen und stattdessen diesen einfacheren Befehl verwenden:

    Get-CsMeetingConfiguration

Da es nur eine einzige globale Auflistung von Besprechungskonfigurationseinstellungen gibt, geben beide Befehle exakt die gleichen Informationen zurück. Der Parameter **Identity** kann auch ausgelassen werden, wenn Sie eines der **Set-Cs**-Cmdlets verwenden. Diese beiden Befehle sind identisch:

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

Die beiden Befehle sind identisch, da Windows PowerShell standardmäßig die globale Auflistung ändert, auch wenn Sie den Parameter **Identity** nicht einschließen.

Die folgenden Cmdlets funktionieren nur im globalen Gültigkeitsbereich:

  - [Get-CsImFilterConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsImFilterConfiguration)

  - [Get-CsMeetingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingConfiguration)

  - [Get-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPrivacyConfiguration)

  - [Get-CsTenantFederationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTenantFederationConfiguration)

  - [Get-CsTenantHybridConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenantHybridConfiguration)

  - [Get-CsTenantLicensingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenantLicensingConfiguration)

  - [Get-CsTenantPublicProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsTenantPublicProvider)

  - [Remove-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsVoicePolicy)

  - [Set-CsMeetingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMeetingConfiguration)

  - [Set-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPrivacyConfiguration)

Beachten Sie, dass das Cmdlet **Remove-CsVoicePolicy** eine Art von Anomalie darstellt. Zum Ersten setzt dieses Cmdlet nicht voraus, dass Sie den Parameter **Identity** angeben:

    Remove-CsVoicePolicy -Identity "global"

Zum Zweiten wird die globale VoIP-Richtlinie mit dem Cmdlet **Remove-CsVoicePolicy** nicht wirklich gelöscht; Skype for Business Online lässt nicht zu, dass Sie globale Richtlinien oder Konfigurationseinstellungen löschen. Das Cmdlet versetzt Sie lediglich in die Lage, alle Eigenschaften in der globalen VoIP-Richtlinie auf die Standardwerte zurückzusetzen. So ist die Eigenschaft **AllowCallForwarding** beispielsweise standardmäßig auf **False** festgelegt. **AllowCallForwarding** könnte jedoch geändert worden sein, sodass der Wert jetzt **True** lautet. Wenn Sie das Cmdlet **Remove-CsVoicePolicy** ausführen, wird die Eigenschaft **AllowCallForwarding** auf ihren Standardwert **False** zurückgesetzt. Eine Übersicht über dieses Szenario finden Sie in der folgenden Tabelle.


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
<td><p>False</p></td>
<td><p>Standardwert</p></td>
</tr>
<tr class="even">
<td><p>True</p></td>
<td><p>Nachdem die globale Richtlinie geändert wurde</p></td>
</tr>
<tr class="odd">
<td><p>False</p></td>
<td><p>Nachdem das Cmdlet <strong>Remove-CsVoicePolicy</strong> ausgeführt wurde</p></td>
</tr>
</tbody>
</table>


## Siehe auch

#### Konzepte

[Identitäten, Bereiche und Mandanten](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Die Lync Online-Cmdlets](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

