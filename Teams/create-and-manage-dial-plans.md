---
title: Erstellen und Verwalten von Wählplänen
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie Microsoft Teams Admin Center oder Windows PowerShell zum Erstellen und Verwalten von Wählplänen (Wählpläne für PSTN-Anrufe) verwenden.
ms.openlocfilehash: bb5574893ec940129a0669608d2bb89d474fb0b6
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2021
ms.locfileid: "58233300"
---
# <a name="create-and-manage-dial-plans"></a>Erstellen und Verwalten von Wählplänen

Nachdem Sie die Wählpläne für Ihre Organisation geplant und alle Normalisierungsregeln herauseriert haben, die für die Sprachrouting erstellt werden müssen, können Sie die Wählpläne erstellen. Bei einem Administratorkonto, das über eine gültige Teams-Lizenz verfügt, können Sie das Microsoft Teams Admin Center oder Windows PowerShell verwenden, um Wählpläne zu erstellen und zu verwalten.  

## <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

### <a name="create-a-dial-plan"></a>Erstellen eines Wählplans

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu  >  **Sprachwählplan**.
2. Klicken **Sie auf** Hinzufügen , und geben Sie einen Namen und eine Beschreibung für den Wählplan ein.
    ![Screenshot der Seite "Hinzufügen" zum Erstellen eines Wählplans](media/create-dial-plan.png)
3. Geben **Sie unter** Wählplandetails ein externes Wählpräfix an, wenn Benutzer eine oder mehrere zusätzliche führende Ziffern (z. B. 9) wählen müssen, um eine externe Leitung zu erhalten. Gehen Sie dazu so vor:
    1. Geben Sie **im Feld Externes Wählpräfix** ein externes Wählpräfix ein. Das Präfix kann bis zu vier Zeichen (#,* und 0-9) enthalten.
    2. Aktivieren Sie **die optimierte Wähleinrichtung für Geräte.** Wenn Sie ein externes Wählpräfix angeben, müssen Sie diese Einstellung auch aktivieren, um das Präfix anzuwenden, damit Anrufe außerhalb Ihrer Organisation vorgenommen werden können.
4. Konfigurieren **und ordnen Sie unter Normalisierungsregeln** eine oder mehrere [Normalisierungsregeln](what-are-dial-plans.md#normalization-rules) für den Wählplan zu. Jedem Wählplan muss mindestens eine Normalisierungsregel zugeordnet sein.  Dazu gehen Sie wie folgt vor:
    - Wenn Sie eine neue Normalisierungsregel erstellen und dem Wählplan zuordnen möchten, klicken Sie auf Hinzufügen **,** und definieren Sie dann die Regel.
    - Zum Bearbeiten einer Normalisierungsregel, die bereits mit dem Wählplan verknüpft ist, wählen Sie die Regel aus, indem Sie links des Regelnamens und dann auf **Bearbeiten klicken.** Nehmen Sie die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann auf **Speichern.**
    - Wenn Sie eine Normalisierungsregel aus dem Wählplan entfernen möchten, wählen Sie die Regel aus, indem Sie links des Regelnamens und dann auf **Entfernen klicken.**
5. Ordnen Sie die Normalisierungsregeln in der von Ihnen zu ändernden Reihenfolge an. Klicken **Sie auf Nach** oben oder Nach **unten,** um die Position von Regeln in der Liste zu ändern.

    > [!NOTE]
    > Teams die Liste der Normalisierungsregeln von oben nach unten durchläuft und die erste Regel verwendet, die der gewählten Nummer entspricht. Wenn Sie einen Wählplan so einrichten, dass eine gewählte Nummer mehreren Normalisierungsregeln entsprechen kann, stellen Sie sicher, dass die restriktiveren Regeln über den weniger restriktiven Regeln sortiert sind. Wenn Sie einen Wählplan einrichten, der eine gewählte Nummer ohne "+" normalisiert, versucht der Anrufdienst erneut, die Nummer mithilfe von Mandanten- und regionalen Wählplanregeln zu normalisieren. Um eine doppelte Normalisierung zu vermeiden, wird empfohlen, dass alle Normalisierungsregeln dazu führen, dass Zahlen mit einem "+" beginnen. Kunden mit Direct Routing können [die Regeln für die Trunkübersetzung](direct-routing-translate-numbers.md) verwenden, um das Pluszeichen (+) bei Bedarf zu entfernen. 

6. Klicken Sie auf **Speichern**.
7. Wenn Sie den Wählplan testen möchten, geben Sie unter **Wählplan** testen eine Telefonnummer ein, und klicken Sie dann auf **Testen.**

### <a name="edit-a-dial-plan"></a>Bearbeiten eines Wählplans

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu  >  **Sprachwählplan**.
2. Wählen Sie den Wählplan aus, indem Sie links vom Namen des Wählplans klicken und dann auf **Bearbeiten klicken.**
3. Nehmen Sie die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann auf **Speichern.**

### <a name="assign-a-dial-plan-to-users"></a>Zuweisen eines Wählplans zu Benutzern

Sie weisen einen Wählplan auf die gleiche Weise wie Richtlinien zu. [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a>Verwendung von PowerShell
  
### <a name="start-powershell"></a>Starten von PowerShell
- Öffnen Sie eine Windows PowerShell-Eingabeaufforderung, und führen Sie die folgenden Befehle aus:

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
  
### <a name="create-and-manage-your-dial-plans"></a>Erstellen und Verwalten Ihrer Wählpläne

Sie können entweder ein einzelnes Cmdlet oder ein PowerShell-Skript verwenden, um Mandantenwählpläne zu erstellen und zu verwalten.
  
#### <a name="using-single-cmdlets"></a>Verwenden einzelner Cmdlets

- Führen Sie zum Erstellen eines neuen Wählplans die
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    Weitere Beispiele und Parameter finden Sie unter [New-CsTenantDialPlan.](/powershell/module/skype/new-cstenantdialplan)
    
- Führen Sie zum Bearbeiten der Einstellungen eines vorhandenen Wählplans die
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    Weitere Beispiele und Parameter finden Sie unter [Set-CsTenantDialPlan.](/powershell/module/skype/set-cstenantdialplan)
    
- Führen Sie zum Hinzufügen von Benutzern zu einem Wählplan die
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    Weitere Beispiele und Parameter finden Sie unter [Grant-CsTenantDialPlan.](/powershell/module/skype/grant-cstenantdialplan)
    
- Führen Sie zum Anzeigen der Einstellungen in einem Wählplan die
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    Weitere Beispiele und Parameter finden Sie unter [Get-CsTenantDialPlan.](/powershell/module/skype/get-cstenantdialplan?view=skype-ps)
    
- Führen Sie zum Löschen eines Wählplans die
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    Weitere Beispiele und Parameter finden Sie unter [Remove-CsTenantDialPlan.](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps)
    
- Um die Einstellungen des effektiven Wählplans zu sehen, führen Sie die
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    Weitere Beispiele und Parameter finden Sie unter [Get-CsEffectiveTenantDialPlan.](/powershell/module/skype/get-cseffectivetenantdialplan)
    
- Um die effektiven Einstellungen eines Wählplans zu testen, führen Sie die
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    Weitere Beispiele und Parameter finden Sie unter [Test-CsEffectiveTenantDialPlan.](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps)
    
#### <a name="using-a-powershell-script"></a>Verwenden eines PowerShell-Skripts

Führen Sie dies aus, um eine Normalisierungsregel zu löschen, die einem Mandantenwählplan zugeordnet ist, ohne zuerst den Mandantenwählplan löschen zu müssen:
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
Führen Sie diese Schritte aus, um dem vorhandenen Mandantenwählplan "RedmondDialPlan" die folgende Normalisierungsregel hinzuzufügen.
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
Führen Sie diese Schritte aus, um die folgende Normalisierungsregel aus dem vorhandenen Mandantenwählplan namens RedmondDialPlan zu entfernen.
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

Führen Sie die folgenden Schritte aus, wenn Sie auch die vorhandenen Normalisierungsregeln untersuchen, bestimmen möchten, welche gelöscht werden sollen, und dann den Index verwenden möchten, um sie zu entfernen. Das Array der Normalisierungsregeln beginnt mit Index 0. Wir möchten die Normalisierungsregel für drei Stellen entfernen, das heißt Index 1.
  
```PowerShell
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
Description         : 4-digit
Pattern             : ^(\\d{4})$
Translation         : +1426666$1
Name                : NR2
IsInternalExtension : False

Description         : 3-digit
Pattern             : ^(\\d{3})$
Translation         : +14255551$1
Name                : NR12
IsInternalExtension : False

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

Führen Sie dies aus, um alle Benutzer zu finden, denen der Mandantenwählplan "RedmondDialPlan" gewährt wurde.
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

Führen Sie dies aus, um alle zugewiesenen TenantDialPlan-Dateien von allen Benutzern zu entfernen, die über einen HostProvider von sipfed.online.lync.com.
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

Führen Sie diese aus, um den vorhandenen lokalen Wählplan mit dem Namen OPDP1 als Mandantenwählplan für Ihre Organisation hinzuzufügen. Sie müssen zuerst den lokalen Wählplan in einer .xml speichern und dann damit den neuen Mandantenwählplan erstellen.
  
Führen Sie dies aus, um den lokalen Wählplan in der .xml speichern.
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

Führen Sie dies aus, um den neuen Mandantenwählplan zu erstellen.
  
```PowerShell
$DPFileName = "dialplan.xml"
$dp = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" + $nr.Name
 $nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation -IsInternalExtension $nr.IsInternalExtension -InMemory
 $NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
    
## <a name="related-topics"></a>Verwandte Themen

- [Was sind Wählpläne?](what-are-dial-plans.md)
- [Übertragen von Telefonnummern – häufig gestellte Fragen](./phone-number-calling-plans/port-order-overview.md)
- [Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)
- [Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
