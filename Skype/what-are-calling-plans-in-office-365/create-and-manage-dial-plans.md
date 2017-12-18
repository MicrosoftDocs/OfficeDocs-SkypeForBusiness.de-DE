---
title: "Erstellen und Verwalten von Wählpläne"
ms.author: tonysmit
author: tonysmit
ms.date: 11/10/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
description: "Learn how to create calling dial plans (PSTN Calling dial plans) in Office 365 and how to manage them. "
---

# Erstellen und Verwalten von Wählpläne

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den [Haftungsausschluss](7af17c94-5f8f-4452-ae1d-01f495b4dc94.md#MT_Footer).  
  
Nachdem Sie geplanter Wählpläne für Ihre Organisation und fest, die Normalisierungsregeln, die erstellt werden, für das Anrufrouting müssen alle haben, müssen Sie mithilfe von Windows PowerShell Wählpläne erstellen und ändern Sie die Einstellung.
  
> [!NOTE]
> Das Skype for Business Admin Center können Sie nicht zum Erstellen und Verwalten von Wählplänen verwenden. 
  
## Überprüfen und Starten von Remote-PowerShell

 **Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**
  
1. Zum Überprüfen, ob Version 3.0 oder höher ausgeführt wird, gehen Sie wie folgt vor: Klicken Sie im Startmenü **** auf **Windows PowerShell**.
    
2. Überprüfen Sie die Version, indem Sie im Fenster **Windows PowerShell** die Zeichenfolge _Get-Host_ eingeben.
    
3. Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
4. Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx).
  
 **Starten einer Windows PowerShell-Sitzung**
  
1. Wechseln Sie über das Startmenü **** zu **Windows PowerShell**.
    
2. Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:
    
    > [!NOTE]
    > Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

Weitere Informationen zum Starten von Windows PowerShell finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx) oder[Herstellen der Verbindung zu Skype for Business Online mit Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).
  
## Erstellen und Verwalten Ihrer Wählpläne

Sie können ein einzelnes Cmdlet oder ein PowerShell-Skript verwenden, um Mandantenwählpläne zu erstellen und zu verwalten.
  
### Verwenden einzelner Cmdlets

- Um einen neuen Wählplan zu erstellen, führen Sie folgenden Befehl aus:
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    Weitere Beispiele und Parameter finden Sie unter [New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx).
    
- Um die Einstellung Änderungen an einem vorhandenen Wählplan vornehmen möchten, führen Sie Folgendes aus:
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    Weitere Beispiele und Parameter finden Sie unter [Set-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx).
    
- Um Benutzer zu einem Wählplan hinzuzufügen, führen Sie folgenden Befehl aus:
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    Weitere Beispiele und Parameter finden Sie unter [Grant-CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx).
    
- Wenn Sie die Einstellungen eines Wählplans anzeigen möchten, führen Sie Folgendes aus:
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    Weitere Beispiele und Parameter finden Sie unter [Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx).
    
- Führen Sie zum Löschen eines Wählplans aus:
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    Weitere Beispiele und Parameter finden Sie unter [Remove-CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx).
    
- Wenn die Einstellungen des effektiven Wählplans anzeigen möchten, führen Sie Folgendes aus:
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    Weitere Beispiele und Parameter finden Sie unter [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx).
    
- Um die gültigen Einstellungen eines Wählplans zu testen, führen Sie folgenden Befehl aus:
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255551234 -Identity 1849827b-a810-40a8-8f77-e94250d4680b_US_TenantDialPlanRedmond
  ```

    Weitere Beispiele und Parameter finden Sie unter [Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx).
    
### Verwenden eines PowerShell-Skripts

Führen Sie das folgende Skript aus, um eine Normalisierungsregel zu löschen, die einem Mandantenwählplan zugeordnet ist, ohne zuerst den Mandantenwählplan löschen zu müssen:
  
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
```

```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
```

```
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
```

```
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
```

```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```

Führen Sie hier, um die folgende Regel Normalisierung mit dem vorhandenen Mandanten Wählplan mit dem Namen RedmondDialPlan hinzuzufügen.
  
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
```

```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```

Führen Sie das folgende Skript aus, um die folgende Normalisierungsregel aus dem vorhandenen Wählplan „RedmondDialPlan" zu entfernen.
  
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
```

```
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

Führen Sie Folgendes, wenn Sie auch die vorhandenen Normalisierungsregeln untersuchen, bestimmen, welche eine Sie löschen möchten, und verwenden Sie dann den Index um zu entfernen möchten. Die Matrix von Normalisierungsregeln beginnt mit dem Index 0. Wir möchten entfernen Sie die Regel 3-stelliges Normalisierung, also das heißt Index 1.
  
```
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
```

```
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
```

```
$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
```

```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

Führen Sie das folgende Skript aus, um alle Benutzer zu suchen, denen der Mandantenwählplan „RedmondDialPlan" gewährt wurde.
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

Führen Sie diese Option, wenn Sie hinzufügen möchten, dass die vorhandenen lokalen Plan mit dem Namen OPDP1 als einen Mandanten Wählplan für Ihre Organisation einwählen. Sie müssen zuerst Speichern der lokalen Wählplan in eine XML-Datendatei, und verwenden sie dann den neuen Mandanten Wählplan zu erstellen.
  
Führen Sie hier, um dem lokalen Wählplan zu der XML-Datei zu speichern.
  
```
$DPName = "OPDP1"
```

```
$DPFileName = "dialplan.xml"
```

```
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

Führen Sie das folgende Skript aus, um den neuen Mandantenwählplan zu erstellen.
  
```
$DPFileName = "dialplan.xml"
```

```
$DP = Import-Clixml $DPFileName
```

```
$NormRules = @()
```

```
ForEach($nr in $dp.NormalizationRules)
```

```
{
```

```
 $id1 = "Global/" +$nr.Name
```

```
$nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation  -IsInternalExtension $nr.IsInternalExtension -InMemory
```

```
$NormRules += $nr2
```

```
}
```

```
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```

## Möchten Sie mehr über Windows PowerShell erfahren?

- In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell zum Ausführen häufiger Skype for Business Online-Verwaltungsaufgaben](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  

