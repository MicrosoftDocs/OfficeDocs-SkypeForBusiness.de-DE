---
title: Konfigurieren von Szenarien für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 'Zusammenfassung: Informationen zum Erstellen, Ändern und Entfernen von Szenarien für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015.'
ms.openlocfilehash: 6ec6764ce3717f38fead9e88c570895f1676310f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098841"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Konfigurieren von Szenarien für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie Szenarien für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015 erstellen, ändern und entfernen.
  
Szenarien definieren den Bereich (d. h. global, Standort, Pool oder Computer) und welche Anbieter im zentralisierten Protokollierungsdienst verwendet werden sollen. Mithilfe von Szenarien aktivieren oder deaktivieren Sie die Ablaufverfolgung für Anbieter (z. B. S4, SIPStack, Im- und Anwesenheit). Durch konfigurieren eines Szenarios können Sie alle Anbieter für eine bestimmte logische Auflistung gruppieren, die eine bestimmte Problembedingung beheben. Wenn Sie feststellen, dass ein Szenario entsprechend Ihren Problembehandlungs- und Protokollierungsanforderungen geändert werden muss, stellen die Skype for Business Server 2015-Debugtools ein Windows PowerShell-Modul namens ClsScenarioEdit.psm1 bereit, das eine Funktion namensEdit-CsClsScenario enthält. Der Zweck des Moduls besteht in der Bearbeitung der Eigenschaften des benannten Szenarios. Beispiele für die Funktionsweise dieses Moduls finden Sie in diesem Thema. Laden Sie die Skype for Business Server 2015 [Debugging Tools herunter,](https://go.microsoft.com/fwlink/p/?LinkId=285257) bevor Sie weitere Informationen erhalten.
  
> [!IMPORTANT]
> Für einen bestimmten Bereich – Standort, global, Pool oder Computer – können Sie maximal zwei Szenarien zu einem bestimmten Zeitpunkt ausführen. Um zu bestimmen, welche Szenarien derzeit ausgeführt werden, verwenden Sie Windows PowerShell [und Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps). Mithilfe von Windows PowerShell [und Set-CsClsScenario](/powershell/module/skype/set-csclsscenario?view=skype-ps)können Sie dynamisch ändern, welche Szenarien ausgeführt werden. Sie können ändern, welche Szenarien während einer Protokollierungssitzung ausgeführt werden, um die gesammelten Daten und von welchen Anbietern anzupassen oder zu verfeinern. 
  
Zum Ausführen der Funktionen des zentralisierten Protokollierungsdiensts mithilfe der Skype for Business Server-Verwaltungsshell müssen Sie Mitglied der Sicherheitsgruppen "CsAdministrator" oder "CsServerAdministrator" (Role-Based Access Control, RBAC) oder einer benutzerdefinierten Rollensteuerungsrolle sein, die eine dieser beiden Gruppen enthält. Führen Sie den folgenden Befehl in der Skype for Business Server Management Windows PowerShell Shell oder an der Eingabeaufforderung aus, um eine Liste aller rollenspezifischen Verwaltungsrollen zurückzukehren, die diesem Cmdlet zugewiesen wurden, einschließlich der benutzerdefinierten rollenspezifischen Rollen, die Sie selbst erstellt haben:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Beispiel:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Nachfolgend wird beschrieben, wie Sie ein Szenario ändern, wie Sie abrufen, welche Szenarien ausgeführt werden, wie Sie ein Szenario entfernen und wie Sie die Inhalte eines Szenarios auf eine optimale Problembehandlung abstimmen können. Sie können die Skype for Business Server-Verwaltungsshell verwenden, um Windows PowerShell aus. Wenn Sie Windows PowerShell, können Sie neue Szenarien für die Verwendung in Ihren Protokollierungssitzungen definieren.
  
Wie in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md)eingeführt, sind die Elemente eines Szenarios:
  
- **Anbieter** Wenn Sie mit OCSLogger vertraut sind, sind Anbieter die Komponenten, von der Sie OCSLogger mitteilen möchten, wofür das Ablaufverfolgungsmodul Protokolle sammeln soll. Die Anbieter entsprechen den Komponenten in OCSLogger und haben in vielen Fällen auch dieselben Namen. Wenn Sie mit OCSLogger nicht vertraut sind, sind Anbieter serverrollespezifische Komponenten, von deren Protokollierungsdienst Protokolle erfassen kann. Weitere Informationen zur Konfiguration von Anbietern finden Sie unter [Configure providers for Centralized Logging Service in Skype for Business Server 2015](configure-providers.md).
    
- **Identität** Der Parameter -Identity legt den Bereich und den Namen des Szenarios fest. Sie könnten beispielsweise einen Bereich von "global" festlegen und das Szenario mit "LyssServiceScenario" identifizieren. Wenn Sie beides kombinieren, definieren Sie die Identität (z. B. "global/LyssServiceScenario").
    
    Optional können Sie die Parameter -Name und -Parent verwenden. Sie definieren den Parameter "Name", um das Szenario eindeutig zu identifizieren. Wenn Sie "Name" verwenden, müssen Sie auch "Parent" verwenden, um das Szenario entweder einem globalen oder einem standortweiten Geltungsbereich hinzuzufügen. 
    
    > [!IMPORTANT]
    > Wenn Sie die Parameter Name und Parent verwenden, können Sie den **Parameter -Identity nicht** verwenden.
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>So erstellen Sie ein neues Szenario mit dem Cmdlet "New-CsClsScenario"

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
2. Verwenden Sie für die Erstellung eines neuen Szenarios für eine Protokollierungssitzung [New-CsClsProvider](/powershell/module/skype/new-csclsprovider?view=skype-ps), und definieren Sie den Namen für das Szenario (d. h. dessen eindeutige Identifizierung). Wählen Sie als Typ für das Protokollierungsformat entweder WPP (Windows-Präprozessorformat für die Softwareablaufverfolgung, Standard), EventLog (Windows-Ereignisprotokoll-Format) oder IISLog (Datei im ASCII-Format basierend auf dem IIS-Protokolldatei-Format). Definieren Sie anschließend den Protokolliergrad (gemäß der Definition im entsprechenden Abschnitt in diesem Thema) und die Flags (gemäß der Definition im entsprechenden Abschnitt in diesem Thema).
    
    Für dieses Beispielszenario verwenden wir LyssProvider als Beispiel für die Anbietervariable.
    
    Geben Sie zum Erstellen eines Szenarios mit den definierten Optionen Folgendes ein:
    
   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    Beispiel:
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    Das alternative Format mit -Name und -Parent:
    
   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>So erstellen Sie ein neues Szenario mit mehreren Anbietern mit dem Cmdlet "New-CsClsScenario"

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
2. Für jeweils einen Geltungsbereich können Sie nur zwei Szenarien erstellen. Sie sind jedoch nicht auf eine feste Anzahl von Anbietern beschränkt. In diesem Beispiel wird davon ausgegangen, dass drei Anbieter erstellt wurden, die Sie allesamt dem Szenario zuweisen möchten, das Sie soeben erstellen. Die Variablennamen der Anbieter lauten LyssProvider, ABServerProvider und SIPStackProvider. Geben Sie zum Definieren und Zuweisen mehrerer Anbieter zu einem Szenario folgendes an einer Skype for Business Server-Verwaltungsshell ein oder Windows PowerShell Eingabeaufforderung:
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > Wie in der Windows PowerShell bekannt, wird die Konvention zum Erstellen einer Hashtabelle mit Werten  `@{<variable>=<value1>, <value2>, <value>…}` alsPlatting bezeichnet. Weitere Informationen zumPlatting in Windows PowerShell finden Sie unter [https://go.microsoft.com/fwlink/p/?LinkId=267760](/previous-versions/technet-magazine/gg675931(v=msdn.10)) . 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>So ändern Sie ein vorhandenes Szenario mit dem Cmdlet "Set-CsClsScenario"

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
2. Es gilt eine Beschränkung auf zwei Szenarien pro Geltungsbereich. Sie können jederzeit ändern, welche Szenarien ausgeführt werden, auch wenn gerade eine Protokollerfassungssitzung läuft. Falls Sie die ausgeführten Szenarien neu definieren, verwendet die aktuelle Protokollierungssitzung ab diesem Zeitpunkt das entfernte Szenario nicht mehr, sondern stattdessen das neue Szenario. Die Protokollinformationen, die im Rahmen des entfernten Szenarios erfasst wurden, verbleiben jedoch in den erfassten Protokollen. Gehen Sie zum Definieren eines neuen Szenarios wie folgt vor (d. h. unter der Annahme, dass ein bereits definierter Anbieter namens "S4Provider" hinzu kommt):
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    Beispiel:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    Falls Sie Anbieter ersetzen möchten, definieren Sie einen einzelnen Anbieter oder eine durch Kommas getrennte Liste mit Anbietern, um die aktuelle Gruppe zu ersetzten. Für den Fall, dass Sie nur einen von vielen Anbietern ersetzen möchten, fügen Sie die aktuellen Anbieter zu den neuen Anbietern hinzu, um eine neue Gruppe von Anbietern zu erstellen, die sowohl die neuen als auch die zuvor vorhandenen Anbieter enthält. Geben Sie Folgendes ein, um sämtliche Anbieter durch eine neue Gruppe zu ersetzen:
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    Beispiel, bei dem die aktuelle aus "$LyssProvider", "$ABServerProvider" und "$SIPStackProvider" bestehende Gruppe durch "$LyssServiceProvider" ersetzt wird:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    Geben Sie Folgendes ein, um lediglich den Anbieter "$LyssProvider" aus der aktuellen Gruppe mit "$LyssProvider", "$ABServerProvider" und "$SIPStackProvider" durch den Anbieter "$LyssServiceProvider" zu ersetzen:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>So entfernen Sie ein vorhandenes Szenario mit dem Cmdlet "Remove-CsClsScenario"

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
2. Wenn Sie ein Szenario entfernen möchten, das zuvor definiert wurde, geben Sie Folgendes ein:
    
   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    Beispiel für das Entfernen des Szenarios "site:Redmond/LyssServiceScenario":
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

Das Cmdlet **Remove-CsClsScenario** entfernt das angegebene Szenario, die bereits erfassten Ablaufverfolgungen sind jedoch nach wie vor in den Protokollen verfügbar und können gesucht werden.
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>So laden und entladen Edit-CsClsScenario cmdlet mithilfe des ClsScenarioEdit.psm1-Moduls

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
    > [!IMPORTANT]
    > Das Modul ClsScenarioEdit.psm1 wird als separater Webdownload bereitgestellt. Das Modul ist Teil der Skype for Business Server 2015-Debuggingtools. Standardmäßig werden die Debugtools im Verzeichnis C:\Programme\Skype for Business Server 2015\Debugging Tools installiert. 
  
2. Geben Sie im Windows PowerShell ein:
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > Das erfolgreiche Laden des Moduls gibt Sie an die eingabeaufforderung Windows PowerShell zurück. Geben Sie ein, um zu bestätigen, dass das Modul geladen ist und Edit-CsClsScenario verfügbar  `Get-Help Edit-CsClsScenario` ist. Daraufhin sollte die grundlegende Kurzfassung der Syntax für  EditCsClsScenario angezeigt werden. 
  
3. Geben Sie zum Entladen der Module Folgendes ein:
    
   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > Das erfolgreiche Entladen des Moduls gibt Sie an die Eingabeaufforderung Windows PowerShell zurück. Geben Sie ein, um zu bestätigen, dass das Modul entladen  `Get-Help Edit-CsClsScenario` ist. Windows PowerShell versucht, die Hilfe für das Cmdlet zu finden, und fehlert. 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>So entfernen Sie einen vorhandenen Anbieter mithilfe des Edit-ClsController-Moduls aus einem Szenario

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
2. Geben Sie im Windows PowerShell ein:
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > Das erfolgreiche Laden des Moduls gibt Sie an die eingabeaufforderung Windows PowerShell zurück. Geben Sie ein, um zu bestätigen, dass das Modul geladen ist und Edit-CsClsScenario verfügbar  `Get-Help Edit-CsClsScenario` ist. Daraufhin sollte die grundlegende Kurzfassung der Syntax für  EditCsClsScenario angezeigt werden. 
  
3. Geben Sie Folgendes ein, um einen Anbieter aus dem AlwaysOn-Szenario zu entfernen:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   Beispiel:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   Bei den Parametern "ScenarioName" und "ProviderName" handelt es sich um Positionsparameter (d. h., dass sie in der erwarteten Position in der Eingabeaufforderung definiert werden müssen). Der Parametername muss nicht explizit definiert werden, sofern der Szenarioname an zweiter Position und der Anbieter an dritter Position steht (in Bezug auf den Namen des Cmdlets, der an erster Position steht):
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   Die positionelle Platzierung der Parameterwerte gilt nur für -Scenario und -Provider. Alle anderen Parameter müssen explizit definiert werden.
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>So fügen Sie ein Szenario mit dem Edit-ClsController-Modul hinzu

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
2. Geben Sie Folgendes ein, um einen Anbieter zum AlwaysOn-Szenario hinzuzufügen:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    Beispiel:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    Mögliche Typen für "-Loglevel" sind "Fatal", "Error", "Warning", "Info", "Verbose", "Debug" oder "All". -Flags können alle vom Anbieter unterstützten Flags sein, z. B. TF_COMPONENT, TF_DIAG. -Flags können auch vom Wert ALL sein
    
   Das vorherige Beispiel kann auch mithilfe des Positionsfeatures des Cmdlets eingegeben werden. So würden Sie beispielsweise Folgendes eingeben, um "ChatServer" zum AlwaysOn-Szenario hinzuzufügen:
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```