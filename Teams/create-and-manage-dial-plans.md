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
description: Hier erfahren Sie, wie Sie das Microsoft Teams Admin Center oder Windows PowerShell zum Erstellen und Verwalten von Wählplänen (PSTN-Wählpläne) verwenden.
ms.openlocfilehash: 966ac2e21d3bc57dd32a0b2732e0be285b9fdf0d
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691341"
---
# <a name="create-and-manage-dial-plans"></a>Erstellen und Verwalten von Wählplänen

Nachdem Sie die Wählpläne für Ihre Organisation geplant und alle Normalisierungsregeln herausgefunden haben, die für das Anrufrouting erstellt werden müssen, können Sie die Wählpläne erstellen. Sie können das Microsoft Teams Admin Center oder Windows PowerShell verwenden, um Wählpläne zu erstellen und zu verwalten.  

## <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

### <a name="create-a-dial-plan"></a>Erstellen eines Wählplans

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **sprach**  >  **Wähl**Einstellungen.
2. Klicken Sie auf **Hinzufügen**, und geben Sie dann einen Namen und eine Beschreibung für den Wählplan ein.
    ![Screenshot der Seite "hinzufügen" zum Erstellen eines Wählplans](media/create-dial-plan.png)
3. Geben Sie unter **Wähl Plan Details**eine externe Wähl Vorwahl an, wenn Benutzer eine oder mehrere zusätzliche führende stellen (beispielsweise 9) wählen müssen, um eine externe Leitung zu erhalten. Gehen Sie dazu so vor:
    1. Geben Sie im Feld **externe Wähl Vorwahl** eine externe Wähl Vorwahl ein. Das Präfix kann bis zu vier Zeichen (#, * und 0-9) aufweisen.
    2. Aktivieren Sie die **optimierte Gerätewahl**. Wenn Sie eine externe Wähl Vorwahl angeben, müssen Sie auch diese Einstellung aktivieren, um das Präfix anzuwenden, damit Anrufe außerhalb Ihrer Organisation getätigt werden können.
4. Konfigurieren und verknüpfen Sie unter **Normalisierungsregeln**eine oder mehrere [Normalisierungsregeln](what-are-dial-plans.md#normalization-rules) für den Wählplan. Jedem Wählplan muss mindestens eine Normalisierungsregel zugeordnet sein.  Führen Sie dazu eine oder mehrere der folgenden Aktionen aus:
    - Wenn Sie eine neue Normalisierungsregel erstellen und dem Wählplan zuordnen möchten, klicken Sie auf **Hinzufügen**, und definieren Sie die Regel.
    - Wenn Sie eine Normalisierungsregel bearbeiten möchten, die dem Wählplan bereits zugeordnet ist, wählen Sie die Regel aus, indem Sie links neben dem Regelnamen klicken, und klicken Sie dann auf **Bearbeiten**. Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.
    - Wenn Sie eine Normalisierungsregel aus dem Wählplan entfernen möchten, wählen Sie die Regel aus, indem Sie links neben dem Regelnamen klicken, und klicken Sie dann auf **Entfernen**.
5. Ordnen Sie die Normalisierungsregeln in der gewünschten Reihenfolge an. Klicken Sie auf nach **oben** oder nach **unten** , um die Position der Regeln in der Liste zu ändern.

    > [!NOTE]
    > Teams durchlaufen die Liste der Normalisierungsregeln von oben nach unten und verwenden die erste Regel, die der gewählten Nummer entspricht. Wenn Sie einen Wählplan so einrichten, dass eine gewählte Nummer mit mehr als einer Normalisierungsregel übereinstimmen kann, stellen Sie sicher, dass die restriktiveren Regeln über die weniger restriktiven Regeln sortiert werden.

6. Klicken Sie auf **Speichern**.
7. Wenn Sie den Wählplan testen möchten, geben Sie unter **Wähleinstellungen testen**eine Telefonnummer ein, und klicken Sie dann auf **Testen**.

### <a name="edit-a-dial-plan"></a>Bearbeiten von Wählplänen

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **sprach**  >  **Wähl**Einstellungen.
2. Wählen Sie den Wählplan aus, indem Sie links neben dem Namen des Wählplans klicken, und klicken Sie dann auf **Bearbeiten**.
3. Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.

### <a name="add-users-to-a-dial-plan"></a>Hinzufügen von Benutzern zu einem Wählplan

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Benutzer**.
2. Wählen Sie den Benutzer aus, indem Sie auf den Anzeige Namen klicken.
3. Wählen Sie die Registerkarte **Richtlinien** aus.
4. Klicken Sie rechts neben zugewiesene Richtlinien auf **Bearbeiten** .
5. Wählen Sie im Dropdownmenü **Wählplan** den Wählplan aus, den Sie dem Benutzer zuweisen möchten, und klicken Sie dann auf über **nehmen**.

## <a name="using-powershell"></a>Verwendung von PowerShell
  
### <a name="verify-and-start-remote-powershell"></a>Überprüfen und starten von Remote-PowerShell

 **Überprüfen Sie, ob Sie Windows PowerShell, Version 3,0 oder höher, ausführen.**
  
1. So überprüfen Sie, ob Sie Version 3,0 oder höher ausführen: **Startmenü**von  >  **Windows PowerShell**.
    
2. Überprüfen Sie die Version, indem Sie im Fenster _Windows PowerShell_ die Zeichenfolge **Get-Host** eingeben.
    
3. Wenn Sie nicht über Version 3,0 oder höher verfügen, laden Sie Updates für Windows PowerShell herunter, und installieren Sie Sie. Informationen zum herunterladen und Aktualisieren von Windows PowerShell auf Version 4,0 finden Sie unter [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
4. Außerdem müssen Sie das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Sie können dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, im [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)herunterladen. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit allen Microsoft 365-oder Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).
  
 **Starten einer Windows PowerShell-Sitzung**
  
1. Klicken **Start**Sie auf  >  **Windows PowerShell**starten.
    
2. Stellen Sie im **Windows PowerShell** -Fenster eine Verbindung mit Microsoft 365 oder Office 365 her, indem Sie Folgendes ausführen:
    
    > [!NOTE]
    > Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.
  

    ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a>Erstellen und Verwalten von Wählplänen

Sie können entweder ein einzelnes Cmdlet oder ein PowerShell-Skript verwenden, um Mandanten-Wählpläne zu erstellen und zu verwalten.
  
#### <a name="using-single-cmdlets"></a>Verwenden einzelner Cmdlets

- Wenn Sie einen neuen Wählplan erstellen möchten, führen Sie Folgendes aus:
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    Weitere Beispiele und Parameter finden Sie unter [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).
    
- Um die Einstellungen eines vorhandenen Wählplans zu bearbeiten, führen Sie Folgendes aus:
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    Weitere Beispiele und Parameter finden Sie unter [Satz-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).
    
- Führen Sie Folgendes aus, um Benutzer zu einem Wählplan hinzuzufügen:
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    Weitere Beispiele und Parameter finden Sie unter [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).
    
- Führen Sie die folgenden Optionen aus, um die Einstellungen für einen Wählplan anzuzeigen:
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    Weitere Beispiele und Parameter finden Sie unter [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).
    
- Um einen Wählplan zu löschen, führen Sie Folgendes aus:
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    Weitere Beispiele und Parameter finden Sie unter [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).
    
- Um die Einstellungen des effektiven Wählplans anzuzeigen, führen Sie Folgendes aus:
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    Weitere Beispiele und Parameter finden Sie unter [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).
    
- Um die effektiven Einstellungen eines Wählplans zu testen, führen Sie Folgendes aus:
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    Weitere Beispiele und Parameter finden Sie unter [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).
    
#### <a name="using-a-powershell-script"></a>Verwenden eines PowerShell-Skripts

Führen Sie diese Aktion aus, um eine Normalisierungsregel zu löschen, die einem Mandanten Wählplan zugeordnet ist, ohne zuerst den Mandanten Wähl Plan löschen zu müssen:
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
Führen Sie diese Schritte aus, um die folgende Normalisierungsregel zum vorhandenen Mandanten Wähl Plan mit dem Namen redmonddialplan "hinzuzufügen.
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
Führen Sie diese Option aus, um die folgende Normalisierungsregel aus dem vorhandenen Mandanten Wähl Plan mit dem Namen redmonddialplan "zu entfernen.
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

Führen Sie die folgenden Schritte aus, wenn Sie auch die vorhandenen Normalisierungsregeln untersuchen, ermitteln möchten, welche Sie löschen möchten, und dann deren Index verwenden, um Sie zu entfernen. Das Array von Normalisierungsregeln beginnt mit Index 0. Wir möchten die dreistellige Normalisierungsregel entfernen, also Index 1.
  
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

Führen Sie diese Aktion aus, um alle Benutzer zu finden, denen der redmonddialplan "-Mandanten Wählplan gewährt wurde.
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

Führen Sie diesen Vorgang aus, um alle zugewiesenen TenantDialPlan von allen Benutzern zu entfernen, die über einen Hostinganbieter von sipfed.online.lync.com verfügen.
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

Führen Sie diese aus, um den vorhandenen lokalen Wählplan mit dem Namen OPDP1 als Mandanten Wähl Plan für Ihre Organisation hinzuzufügen. Sie müssen den lokalen Wählplan zunächst in einer XML-Datei speichern und dann zum Erstellen des neuen Mandanten Wähl Plans verwenden.
  
Führen Sie diese Aktion aus, um den lokalen Wählplan in der XML-Datei zu speichern.
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

Führen Sie diese Aktion aus, um den neuen Mandanten Wählplan zu erstellen.
  
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
- [Übertragen von Telefonnummern – häufig gestellte Fragen](transferring-phone-numbers-common-questions.md)
- [Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)
- [Disclaimer-Label für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
