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
description: Erfahren Sie, wie Sie das Microsoft Teams Admin Center oder Windows PowerShell zum Erstellen und Verwalten von Wählplänen (PSTN-Anrufpläne) verwenden.
ms.openlocfilehash: 0b2c8c64d1e4e01843c6565d43a07e0ebdb24d71
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120807"
---
# <a name="create-and-manage-dial-plans"></a>Erstellen und Verwalten von Wählplänen

Nachdem Sie die Wählpläne für Ihre Organisation geplant und alle Normalisierungsregeln für die Anrufrouting erstellt haben, können Sie die Wählpläne erstellen. Sie können das Microsoft Teams Admin Center oder Windows PowerShell verwenden, um Wählpläne zu erstellen und zu verwalten.  

## <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

### <a name="create-a-dial-plan"></a>Erstellen eines Wählplans

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu  >  **Sprachwahlplan.**
2. Klicken **Sie auf** Hinzufügen , und geben Sie dann einen Namen und eine Beschreibung für den Wählplan ein.
    ![Screenshot der Seite Hinzufügen zum Erstellen eines Wählplans](media/create-dial-plan.png)
3. Geben **Sie unter** Wählplandetails ein externes Wählpräfix an, wenn Benutzer eine oder mehrere zusätzliche führende Ziffern (z. B. 9) wählen müssen, um eine externe Leitung zu erhalten. Gehen Sie dazu so vor:
    1. Geben Sie **im Feld Externes Wählpräfix** ein externes Wählpräfix ein. Das Präfix kann bis zu vier Zeichen (#,*und 0-9) umfassen.
    2. Aktivieren Sie **Optimierte Gerätewählung.** Wenn Sie ein externes Wählpräfix angeben, müssen Sie diese Einstellung auch aktivieren, um das Präfix anzuwenden, damit Anrufe außerhalb Ihrer Organisation vorgenommen werden können.
4. Konfigurieren **und ordnen Sie unter** Normalisierungsregeln eine oder mehrere [Normalisierungsregeln](what-are-dial-plans.md#normalization-rules) für den Wählplan zu. Jedem Wählplan muss mindestens eine Normalisierungsregel zugeordnet sein.  Gehen Sie dazu mit einer oder mehreren der folgenden Schritte vor:
    - Wenn Sie eine neue Normalisierungsregel erstellen und dem Wählplan zuordnen möchten, klicken Sie auf **Hinzufügen**, und definieren Sie dann die Regel.
    - Wenn Sie eine Normalisierungsregel bearbeiten möchten, die bereits dem Wählplan zugeordnet ist, wählen Sie die Regel aus, indem Sie links vom Regelnamen klicken und dann auf **Bearbeiten klicken.** Nehmen Sie die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann auf **Speichern.**
    - Wenn Sie eine Normalisierungsregel aus dem Wählplan entfernen möchten, wählen Sie die Regel aus, indem Sie links vom Regelnamen klicken und dann auf **Entfernen klicken.**
5. Ordnen Sie die Normalisierungsregeln in der reihenfolge an, die Sie wünschen. Klicken **Sie auf Nach oben** oder Nach **unten,** um die Position von Regeln in der Liste zu ändern.

    > [!NOTE]
    > Teams durchläuft die Liste der Normalisierungsregeln von oben nach unten und verwendet die erste Regel, die der gewählten Nummer entspricht. Wenn Sie einen Wählplan so einrichten, dass eine Wählnummer mehr als einer Normalisierungsregel entsprechen kann, stellen Sie sicher, dass die restriktiveren Regeln über den weniger restriktiven Regeln sortiert sind.

6. Klicken Sie auf **Speichern**.
7. Wenn Sie den Wählplan testen möchten, geben Sie unter **Wählplan testen** eine Telefonnummer ein, und klicken Sie dann auf **Testen.**

### <a name="edit-a-dial-plan"></a>Bearbeiten eines Wählplans

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu  >  **Sprachwahlplan.**
2. Wählen Sie den Wählplan aus, indem Sie links vom Namen des Wählplans klicken und dann auf **Bearbeiten klicken.**
3. Nehmen Sie die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann auf **Speichern.**

### <a name="assign-a-dial-plan-to-users"></a>Zuweisen eines Wählplans zu Benutzern

Sie weisen einen Wählplan auf die gleiche Weise zu, wie Sie Richtlinien zuweisen. [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a>Verwendung von PowerShell
  
### <a name="start-powershell"></a>Starten von PowerShell
- Öffnen Sie eine Windows PowerShell Eingabeaufforderung, und führen Sie die folgenden Befehle aus:

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

    Weitere Beispiele und Parameter finden Sie unter [New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan).
    
- Führen Sie zum Bearbeiten der Einstellungen eines vorhandenen Wählplans aus:
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    Weitere Beispiele und Parameter finden Sie unter [Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan).
    
- Führen Sie zum Hinzufügen von Benutzern zu einem Wählplan aus:
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    Weitere Beispiele und Parameter finden Sie unter [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan).
    
- Führen Sie zum Anzeigen der Einstellungen in einem Wählplan aus:
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    Weitere Beispiele und Parameter finden Sie unter [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps).
    
- Führen Sie zum Löschen eines Wählplans aus:
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    Weitere Beispiele und Parameter finden Sie unter [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).
    
- Führen Sie zum Sehen der Einstellungen des effektiven Wählplans aus:
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    Weitere Beispiele und Parameter finden Sie unter [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan).
    
- Führen Sie zum Testen der effektiven Einstellungen eines Wählplans aus:
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    Weitere Beispiele und Parameter finden Sie unter [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).
    
#### <a name="using-a-powershell-script"></a>Verwenden eines PowerShell-Skripts

Führen Sie dies aus, um eine Normalisierungsregel zu löschen, die einem Mandantenwählplan zugeordnet ist, ohne zuerst den Mandantenwählplan löschen zu müssen:
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
Führen Sie dies aus, um dem vorhandenen Mandantenwählplan mit dem Namen RedmondDialPlan die folgende Normalisierungsregel hinzuzufügen.
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
Führen Sie dies aus, um die folgende Normalisierungsregel aus dem vorhandenen Mandantenwählplan namens RedmondDialPlan zu entfernen.
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

Führen Sie Folgendes aus, wenn Sie auch die vorhandenen Normalisierungsregeln untersuchen, bestimmen möchten, welche Sie löschen möchten, und verwenden Sie dann den Index, um ihn zu entfernen. Das Array der Normalisierungsregeln beginnt mit Index 0. Wir möchten die dreistellige Normalisierungsregel entfernen, d. h. Index 1.
  
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

Führen Sie dies aus, um alle Benutzer zu finden, denen der Wählplan des RedmondDialPlan-Mandanten gewährt wurde.
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

Führen Sie dies aus, um alle zugewiesenen TenantDialPlan von allen Benutzern zu entfernen, die über einen HostingProvider von sipfed.online.lync.com.
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

Führen Sie diese aus, um den vorhandenen lokalen Wählplan namens OPDP1 als Mandantenwählplan für Ihre Organisation hinzuzufügen. Sie müssen den lokalen Wählplan zuerst in einer XML-Datei speichern und dann zum Erstellen des neuen Mandantenwählplans verwenden.
  
Führen Sie dies aus, um den lokalen Wählplan in der XML-Datei zu speichern.
  
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