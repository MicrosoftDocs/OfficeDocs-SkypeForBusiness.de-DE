---
title: "Erstellen und Verwalten von Wähleinstellungen"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: "Erfahren Sie, wie aufrufende Wählpläne (Aufrufen von PSTN-Wählpläne) in Office 365 erstellen und deren Verwaltung. "
ms.openlocfilehash: 890ea8193f72301aef9ef0d4feacd2d259bba2b4
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="create-and-manage-dial-plans"></a>Erstellen und Verwalten von Wähleinstellungen

Nachdem Sie Wähleinstellungen für Ihre Organisation geplant und herausgefunden, dass alle Normalisierungsregeln, die zum Weiterleiten von Anrufen erstellt werden müssen, müssen Sie mithilfe von Windows PowerShell Wählpläne erstellen und ändern Sie die Einstellung.
  
> [!NOTE]
> Die Skype für Business-Verwaltungskonsole kann nicht für das Erstellen und Verwalten von Wählplänen verwendet werden. 
  
## <a name="verifying-and-starting-remote-powershell"></a>Überprüfen und Starten von Remote-PowerShell

 **Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**
  
1. Um sicherzustellen, dass Sie Version 3.0 oder höher ausgeführt werden: **Im Menü Start** > **Windows PowerShell**.
    
2. Überprüfen Sie die Version, indem Sie im Fenster **Windows PowerShell** die Zeichenfolge _Get-Host_ eingeben.
    
3. Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
4. Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
  
 **Starten einer Windows PowerShell-Sitzung**
  
1. Über das **Startmenü** > **Windows PowerShell**.
    
2. Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:
    
    > [!NOTE]
    > Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.
  
> 
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

Wenn Sie weitere Informationen zu Windows PowerShell starten möchten, finden Sie unter [Connect auf alle Office 365-Dienste in einem einzelnen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx) oder [Herstellen einer Verbindung mit Skype für Business Online mithilfe von Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
## <a name="creating-and-managing-your-dial-plans"></a>Erstellen und Verwalten von Wählplänen

Sie können Verwenden eines einzelnen Cmdlets oder ein PowerShell-Skript erstellen und Verwalten von Mandanten-Wählpläne.
  
### <a name="using-single-cmdlets"></a>Verwenden von einzelnen cmdlets

- So erstellen Sie einen neuen Wählplan, führen Sie Folgendes aus:
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    Andere Beispiele und Parametern finden Sie unter [New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx).
    
- Um einem vorhandenen Wählplan Einstellung geändert haben, führen Sie Folgendes aus:
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    Andere Beispiele und Parametern finden Sie unter [Set-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx).
    
- Führen Sie zum Hinzufügen von Benutzern zu einem Wählplan aus:
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    Andere Beispiele und Parametern finden Sie unter [Grant-CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx).
    
- Um die Einstellungen für einen Wählplan anzuzeigen, führen Sie Folgendes aus:
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    Andere Beispiele und Parametern finden Sie unter [Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx).
    
- Um einen Wählplan zu löschen, führen Sie Folgendes aus:
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    Andere Beispiele und Parametern finden Sie unter [Remove-CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx).
    
- Um die Einstellungen des Wählplans effektiven angezeigt wird, führen Sie Folgendes aus:
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    Andere Beispiele und Parametern finden Sie unter [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx).
    
- Um den effektiven Einstellungen von einem Wählplan zu testen, führen Sie Folgendes aus:
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255551234 -Identity 1849827b-a810-40a8-8f77-e94250d4680b_US_TenantDialPlanRedmond
  ```

    Andere Beispiele und Parametern finden Sie unter [Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx).
    
### <a name="using-a-powershell-script"></a>Mithilfe eines PowerShell-Skripts

Führen Sie diese Option, um eine Normalisierungsregel zu löschen, die ein Mandant zugeordnet ist Wählplan ohne den Mandanten Wählplan zuerst zu löschen:
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
Führen Sie diese Option, damit die folgenden Normalisierungsregel mit dem vorhandenen Mandanten Wählplan mit dem Namen RedmondDialPlan hinzufügen.
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
Führen Sie diese Option, damit die folgenden Normalisierungsregel aus dem vorhandenen Mandanten Wählplan mit dem Namen RedmondDialPlan entfernen möchten.
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

Führen Sie Folgendes, wenn Sie auch untersuchen Sie die vorhandenen Normalisierungsregeln, bestimmen, welche Art Sie löschen möchten und klicken Sie dann den Index verwenden, um ihn entfernen möchten. Das Array von Normalisierungsregeln beginnt mit dem Index 0. Wir möchten entfernen Sie die Normalisierungsregel 3 Ziffern, also so Index 1.
  
```
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

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[Number 1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

Führen Sie diese Option, damit alle Benutzer zu suchen, die sich die RedmondDialPlan erteilt wurden Mandanten Wählplan.
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

Führen Sie diese zum Hinzufügen, dass die vorhandenen lokalen Wähleinstellungen namens OPDP1 als einen Mandanten Wählplan für Ihre Organisation. Sie müssen zuerst Speichern der lokalen Wähleinstellungen eine XML-Datei, und verwenden Sie es zum Erstellen der neuen Mandanten-Wählplans.
  
Führen Sie diese Option, damit die Wähleinstellungen: lokal in der XML-Datei zu speichern.
  
```
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

Führen Sie diese Option, damit den neue Mandanten Wählplan zu erstellen.
  
```
$DPFileName = "dialplan.xml"
$DP = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" +$nr.Name
$nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation  -IsInternalExtension $nr.IsInternalExtension -InMemory
$NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie weitere Informationen zu Windows Powershell wissen?

- In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Warum müssen Sie mithilfe von Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Verwandte Themen
[Transferring phone numbers common questions](transferring-phone-numbers-common-questions.md)

[Verschiedene Arten von Telefonnummern für den Aufruf von plant verwendet](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Telefonnummern für Ihre Organisation verwalten](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://go.microsoft.com/fwlink/?LinkID=692099)

