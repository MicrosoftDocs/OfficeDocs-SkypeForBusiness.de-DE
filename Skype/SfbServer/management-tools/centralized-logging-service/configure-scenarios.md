---
title: Konfigurieren von Szenarien für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 'Zusammenfassung: Informationen Sie zum Erstellen, ändern und Szenarien für die zentralisierte Protokollierungsdienst in Skype für Business Server 2015 zu entfernen.'
ms.openlocfilehash: e80324d4228aec503c887927459e42188741837f
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373930"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Konfigurieren von Szenarien für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie das Erstellen, ändern und Szenarien für die zentralisierte Protokollierungsdienst in Skype für Business Server 2015 zu entfernen.
  
Szenarien definieren des Bereichs (d. h., global, Standort, Pool oder Computer) und welche Anbieter in der zentralisierte Protokollierungsdienst verwenden. Mithilfe von Szenarien können Sie die Ablaufverfolgung für Dienstanbieter aktivieren oder deaktivieren (z. B. bezüglich S4, SIPStack, IM und Anwesenheit). Durch das Konfigurieren eines Szenarios können Sie alle Dienstanbieter für eine bestimmte logische Sammlung gruppieren, die sich mit einem bestimmten Problemzustand befassen. Wenn Sie feststellen, dass ein Szenario werden, um die Problembehandlung und Protokollierung Anforderungen erfüllen geändert muss, enthält die Skype für Business Server 2015-Tools zum Debuggen einer Windows PowerShell-Modul mit dem Namen ClsScenarioEdit.psm1, die eine Funktion NamedEdit-CsClsScenario enthält. Dieses Modul soll dazu dienen, die Eigenschaften des betreffenden Szenarios zu bearbeiten. Beispiele für die Funktionsweise des Moduls erhalten Sie in diesem Thema. Herunterladen Sie die Skype für Business Server 2015 [Debugtools](https://go.microsoft.com/fwlink/p/?LinkId=285257) bevor Sie fortfahren alle.
  
> [!IMPORTANT]
> Für eine angegebenen Bereich – globale Website, Pool oder Computer – Sie können bis zu zwei Szenarien zu einem bestimmten Zeitpunkt ausführen. Um zu ermitteln, welche Szenarien derzeit ausgeführt werden, verwenden Sie Windows PowerShell und [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps). Mithilfe von Windows PowerShell und [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)können Sie dynamisch ändern, welche Szenarien ausgeführt werden. Sie können ändern, welche Szenarien ausgeführt werden, während eine protokollierungssitzung anpassen oder verfeinern, die Sie sammeln Daten und über welche Anbieter. 
  
Um die Centralized Logging Service-Funktionen mit der Skype für Business Server-Verwaltungsshell ausführen, müssen Sie Mitglied der Administratorrolle CsAdministrator oder der Sicherheitsgruppen CsServerAdministrator rollenbasierten Zugriffssteuerung (RBAC) oder eine benutzerdefinierte RBAC-Rolle sein, enthält eine der beiden Gruppen. Zum Zurückgeben einer Liste von allen RBAC Befehl Rollen, die dieses Cmdlet, einschließlich Sie selbst erstellt haben alle benutzerdefinierten RBAC-Rollen zugewiesen wurde dem folgenden aus der Skype für Business Server-Verwaltungsshell oder der Windows PowerShell-Eingabeaufforderung:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Beispiel:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Nachfolgend wird beschrieben, wie Sie ein Szenario definieren, ein Szenario ändern, wie Sie abrufen, welche Szenarien ausgeführt werden, wie Sie ein Szenario entfernen und wie Sie die Inhalte eines Szenarios auf eine optimale Problembehandlung abstimmen können. Sie können die Skype für Business Server-Verwaltungsshell zum Ausstellen von Windows PowerShell-Befehle verwenden. Wenn Sie Windows PowerShell verwenden, können Sie neue Szenarien für die Verwendung in Ihrer protokollierungssitzungen definieren.
  
Wie in [Centralized Logging Service in Skype für Business 2015](centralized-logging-service.md)eingeführt, sind die Elemente eines Szenarios:
  
- **Anbieter** Wenn Sie mit OCSLogger vertraut sind, sind Anbieter die Komponenten, die Sie angeben, dass OCSLogger feststellen, welche die Verfolgung Engine Protokolle erfassen sollten. Der Anbieter sind die gleichen Komponenten und in vielen Fällen haben, die denselben Namen wie die Komponenten in OCSLogger. Wenn Sie nicht mit OCSLogger vertraut sind, sind Anbieter für bestimmte Komponenten von Server-Rolle, dass der zentralisierte Protokollierungsdienst sammeln können Protokolle aus. Ausführliche Informationen zur Konfiguration der Anbieter finden Sie unter [Konfigurieren von Anbietern für Centralized Logging Service in Skype für Business Server 2015](configure-providers.md).
    
- **Identität** Der Parameter-Identität festgelegt, den Bereich und den Namen des Szenarios. Beispielsweise konnte Sie einen Bereich von "global" festgelegt und das Szenario mit "LyssServiceScenario" identifizieren. Wenn Sie die beiden kombinieren, definieren Sie die Identität (z. B. "global/LyssServiceScenario").
    
    Optional können Sie die - Name "und" – Parent-Parameter. Sie definieren den Parameter „Name“, um das Szenario eindeutig zu identifizieren. Wenn Sie „Name“ verwenden, müssen Sie auch „Parent“ verwenden, um das Szenario entweder einem globalen oder einem standortweiten Geltungsbereich hinzuzufügen. 
    
    > [!IMPORTANT]
    > Wenn Sie den Namen "und" Parent-Parameter verwenden, können keine der **-Identität** Parameter.
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>So erstellen Sie ein neues Szenario mit dem Cmdlet „New-CsClsScenario“

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Um ein neues Szenario für eine protokollierungssitzung zu erstellen, verwenden Sie [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) , und legen Sie den Namen des Szenarios (d. h., wie eindeutig identifiziert wird). Wählen Sie als Typ für das Protokollierungsformat entweder WPP (Windows-Präprozessorformat für die Softwareablaufverfolgung, Standard), EventLog (Windows-Ereignisprotokoll-Format) oder IISLog (Datei im ASCII-Format basierend auf dem IIS-Protokolldatei-Format). Definieren Sie anschließend den Protokolliergrad (gemäß der Definition im entsprechenden Abschnitt in diesem Thema) und die Flags (gemäß der Definition im entsprechenden Abschnitt in diesem Thema).
    
    Für dieses Beispielszenario verwenden wir LyssProvider als Beispiel für die Anbietervariable.
    
    Geben Sie zum Erstellen eines Szenarios mit den definierten Optionen Folgendes ein:
    
   ```
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    Beispiel:
    
   ```
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    Alternatives Format mithilfe von-Name "und" – Parent:
    
   ```
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>So erstellen Sie ein neues Szenario mit mehreren Anbietern mithilfe des Cmdlets „New-CsClsScenario“

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Für jeweils einen Geltungsbereich können Sie nur zwei Szenarien erstellen. Sie sind jedoch nicht auf eine feste Anzahl von Anbietern beschränkt. In diesem Beispiel wird davon ausgegangen, dass drei Anbieter erstellt wurden, die Sie allesamt dem Szenario zuweisen möchten, das Sie soeben erstellen. Die Variablennamen der Anbieter lauten „LyssProvider“, „ABServerProvider“ und „SIPStackProvider“. Um zu definieren, und weisen Sie mehreren Anbietern zu einem Szenario, geben Sie an einer Skype für Business Server-Verwaltungsshell oder mit Windows PowerShell-Eingabeaufforderung Folgendes ein:
    
   ```
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > Wie in folgende Konvention für die Erstellung einer Hashtabelle von Werten mithilfe von Windows PowerShell bekannt ist `@{<variable>=<value1>, <value2>, <value>…}` Assplatting bekannt ist. Ausführliche Informationen zu Splatting in Windows PowerShell finden Sie unter [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760). 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>So ändern Sie ein vorhandenes Szenario mithilfe des Cmdlets „Set-CsClsScenario“

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Es gilt eine Beschränkung auf zwei Szenarien pro Geltungsbereich. Sie können jederzeit ändern, welche Szenarien ausgeführt werden, auch wenn gerade eine Protokollerfassungssitzung läuft. Falls Sie die ausgeführten Szenarien neu definieren, verwendet die aktuelle Protokollierungssitzung ab diesem Zeitpunkt nicht mehr das entfernte Szenario, sondern stattdessen das neue Szenario. Die Protokollinformationen, die im Rahmen des entfernten Szenarios erfasst wurden, verbleiben jedoch in den erfassten Protokollen. Um ein neues Szenario zu definieren, gehen Sie folgendermaßen (, die das Hinzufügen eines bereits definierten-Anbieters mit dem Namen "S4Provider" vorausgesetzt wird):
    
   ```
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    Beispiel:
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    Falls Sie Anbieter ersetzen möchten, definieren Sie einen einzelnen Anbieter oder eine kommagetrennte Liste mit Anbietern, um die aktuelle Gruppe zu ersetzen. Für den Fall, dass Sie nur einen von vielen Anbietern ersetzen möchten, fügen Sie die aktuellen Anbieter zu den neuen Anbietern hinzu, um eine neue Gruppe von Anbietern zu erstellen, die sowohl die neuen als auch die zuvor vorhandenen Anbieter enthält. Geben Sie Folgendes ein, um sämtliche Anbieter durch eine neue Gruppe zu ersetzen:
    
   ```
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    Beispiel, bei dem die aktuelle aus „$LyssProvider“, „$ABServerProvider“ und „$SIPStackProvider“ bestehende Gruppe durch „$LyssServiceProvider“ ersetzt wird:
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    Geben Sie Folgendes ein, um lediglich den Anbieter „$LyssProvider“ aus der aktuellen Gruppe mit „$LyssProvider“, „$ABServerProvider“ und „$SIPStackProvider“ durch den Anbieter „$LyssServiceProvider“ zu ersetzen:
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>So entfernen Sie ein vorhandenes Szenario mithilfe des Cmdlets „Remove-CsClsScenario“

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Wenn Sie ein Szenario entfernen möchten, das zuvor definiert wurde, geben Sie Folgendes ein:
    
   ```
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    Beispiel für das Entfernen des Szenarios „site:Redmond/LyssServiceScenario“:
    
   ```
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

Das Cmdlet **Remove-CsClsScenario** entfernt das angegebene Szenario, aber die Spuren, die erfasst wurden in den Protokollen für die Sie für die Suche weiterhin verfügbar sind.
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>So laden und entladen Sie das Cmdlet „Edit-CsClsScenario“ mithilfe des Moduls „ClsScenarioEdit.psm1“

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
    > [!IMPORTANT]
    > Das Modul „ClsScenarioEdit.psm1“ wird als separater Webdownload zur Verfügung gestellt. Das Modul ist Bestandteil der Skype für Business Server 2015 Debugging Tools. Die Debugtools werden standardmäßig im Ordner „C:\Programme\Skype for Business Server 2015\Debugging Tools“ installiert. 
  
2. Geben Sie von der Windows PowerShell Folgendes ein:
    
   ```
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > Laden des Moduls gibt Sie an der Windows PowerShell-Eingabeaufforderung zurück. Um zu bestätigen, dass das Modul geladen ist und Edit-CsClsScenario verfügbar ist, geben Sie ein `Get-Help Edit-CsClsScenario`. Daraufhin sollte die grundlegende Kurzfassung der Syntax für „EditCsClsScenario“ angezeigt werden. 
  
3. Geben Sie zum Entladen des Moduls Folgendes ein:
    
   ```
   Remove-Module ClsController
   ```

    > [!TIP]
    > Erfolgreiche Entladen des Moduls gibt Sie an der Windows PowerShell-Eingabeaufforderung. Um zu bestätigen, dass das Modul entladen wird, geben Sie ein `Get-Help Edit-CsClsScenario`. Windows PowerShell versucht, suchen die Hilfe für das Cmdlet und ein Fehler auftritt. 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>So entfernen Sie einen vorhandenen Anbieter mithilfe des Edit-ClsController-Moduls aus einem Szenario

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Geben Sie von der Windows PowerShell Folgendes ein:
    
   ```
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > Laden des Moduls gibt Sie an der Windows PowerShell-Eingabeaufforderung zurück. Um zu bestätigen, dass das Modul geladen ist und Edit-CsClsScenario verfügbar ist, geben Sie ein `Get-Help Edit-CsClsScenario`. Daraufhin sollte die grundlegende Kurzfassung der Syntax für „EditCsClsScenario“ angezeigt werden. 
  
3. Geben Sie Folgendes ein, um einen Anbieter aus dem Szenario „AlwaysOn“ zu entfernen:
    
   ```
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   Beispiel:
    
   ```
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   Bei den Parametern „ScenarioName“ und „ProviderName“ handelt es sich um Positionsparameter (d. h., dass sie in der erwarteten Position in der Eingabeaufforderung definiert werden müssen). Der Parametername muss nicht explizit definiert werden, sofern der Szenarioname an zweiter Position und der Anbieter an dritter Position steht (in Bezug auf den Namen des Cmdlets, der an erster Position steht):
    
   ```
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   Die positionelle Platzieren der Parameterwerte bezieht sich nur auf - Szenario und -Anbieter. Alle anderen Parameter müssen explizit definiert werden.
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>So fügen Sie ein Szenario mit dem Modul „Edit-ClsController“ hinzu

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Geben Sie Folgendes ein, um einen Anbieter zum Szenario „AlwaysOn“ hinzuzufügen:
    
   ```
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    Beispiel:
    
   ```
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    Mögliche Typen für „-Loglevel“ sind „Fatal“, „Error“, „Warning“, „Info“, „Verbose“, „Debug“ oder „All“. -Flags kann eines der Flags, die der Anbieter unterstützt werden, beispielsweise TF_COMPONENT, TF_DIAG. -Flags können auch sein, der alle Wert
    
   Das vorherige Beispiel kann auch mithilfe der Positionsfunktion des Cmdlets eingegeben werden. So würden Sie beispielsweise Folgendes eingeben, um „ChatServer“ zum Szenario „AlwaysOn“ hinzuzufügen:
    
   ```
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```