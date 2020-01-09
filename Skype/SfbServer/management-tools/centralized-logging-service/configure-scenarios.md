---
title: Konfigurieren von Szenarien für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Szenarien für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015 erstellen, ändern und entfernen.'
ms.openlocfilehash: 9a6ce9a760255275c3ad265cdd6c58fa964f8e43
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991600"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Konfigurieren von Szenarien für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie Szenarien für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015 erstellen, ändern und entfernen können.
  
Szenarien definieren den Bereich (Global, Site, Pool oder Computer) und welche Anbieter im zentralisierten Protokollierungsdienst zu verwenden sind. Mithilfe von Szenarien können Sie die Ablaufverfolgung für Dienstanbieter aktivieren oder deaktivieren (z. B. bezüglich S4, SIPStack, IM und Anwesenheit). Durch das Konfigurieren eines Szenarios können Sie alle Dienstanbieter für eine bestimmte logische Sammlung gruppieren, die sich mit einem bestimmten Problemzustand befassen. Wenn Sie feststellen, dass ein Szenario geändert werden muss, um die Anforderungen zur Problembehandlung und Protokollierung zu erfüllen, bietet Ihnen Skype for Business Server 2015 Debug Tools ein Windows PowerShell-Modul mit dem Namen "ClsScenarioEdit. psm1", das eine Funktion namedEdit-CsClsScenario enthält. Dieses Modul soll dazu dienen, die Eigenschaften des betreffenden Szenarios zu bearbeiten. Beispiele für die Funktionsweise des Moduls erhalten Sie in diesem Thema. Laden Sie die [Debug-Tools](https://go.microsoft.com/fwlink/p/?LinkId=285257) von Skype for Business Server 2015 herunter, bevor Sie fortfahren.
  
> [!IMPORTANT]
> Für einen bestimmten Bereich – Website, Global, Pool oder Computer – können Sie maximal zwei Szenarien zu einem bestimmten Zeitpunkt ausführen. Um zu ermitteln, welche Szenarien zurzeit ausgeführt werden, verwenden Sie Windows PowerShell und [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps). Mithilfe von Windows PowerShell und der [CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)können Sie dynamisch ändern, welche Szenarien ausgeführt werden. Sie können ändern, welche Szenarien während einer Protokollierungssitzung ausgeführt werden, um die Daten, die Sie sammeln, und von welchen Anbietern anzupassen oder zu verfeinern. 
  
Wenn Sie die Funktionen für den zentralisierten Protokollierungsdienst mithilfe der Skype for Business Server-Verwaltungsshell ausführen möchten, müssen Sie Mitglied der CsAdministrator-oder CsServerAdministrator-Sicherheitsgruppe (Role-Based Access Control, RBAC) oder einer benutzerdefinierten RBAC-Rolle sein, die enthält eine dieser beiden Gruppen. Führen Sie den folgenden Befehl aus der Skype for Business Server-Verwaltungsshell oder der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde, einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Beispiel:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Nachfolgend wird beschrieben, wie Sie ein Szenario definieren, ein Szenario ändern, wie Sie abrufen, welche Szenarien ausgeführt werden, wie Sie ein Szenario entfernen und wie Sie die Inhalte eines Szenarios auf eine optimale Problembehandlung abstimmen können. Sie können die Skype for Business Server-Verwaltungsshell zum Ausgeben von Windows PowerShell-Befehlen verwenden. Wenn Sie Windows PowerShell verwenden, können Sie neue Szenarien für die Verwendung in ihren Protokollierungssitzungen definieren.
  
Wie im [zentralisierten Protokollierungsdienst in Skype for Business 2015](centralized-logging-service.md)eingeführt, sind die Elemente eines Szenarios:
  
- **Anbieter** Wenn Sie mit OCSLogger vertraut sind, sind Anbieter die Komponenten, die Sie angeben, um OCSLogger zu informieren, von welchem das Ablaufverfolgungsmodul Protokolle sammeln soll. Die Anbieter sind die gleichen Komponenten und haben in vielen Fällen denselben Namen wie die Komponenten in OCSLogger. Wenn Sie mit OCSLogger nicht vertraut sind, sind Anbieterserver rollenspezifische Komponenten, von denen der zentralisierte Protokollierungsdienst Protokolle sammeln kann. Details zur Konfiguration von Anbietern finden Sie unter [Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015](configure-providers.md).
    
- **Identität** Die Parameter-Identity legt den Bereich und den Namen des Szenarios fest. So können Sie beispielsweise einen Bereich von "Global" festlegen und das Szenario mit "LyssServiceScenario" identifizieren. Wenn Sie die beiden kombinieren, definieren Sie die Identität (beispielsweise "Global/LyssServiceScenario").
    
    Optional können Sie die Parameter-Name und-Parent verwenden. Sie definieren den Parameter „Name“, um das Szenario eindeutig zu identifizieren. Wenn Sie „Name“ verwenden, müssen Sie auch „Parent“ verwenden, um das Szenario entweder einem globalen oder einem standortweiten Geltungsbereich hinzuzufügen. 
    
    > [!IMPORTANT]
    > Wenn Sie den Parameter Name und Parent verwenden, können Sie den Parameter **-Identity** nicht verwenden.
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>So erstellen Sie ein neues Szenario mit dem Cmdlet „New-CsClsScenario“

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Verwenden Sie für die Erstellung eines neuen Szenarios für eine Protokollierungssitzung [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) und definieren Sie den Namen für das Szenario (d. h. dessen eindeutige Identifikation). Wählen Sie als Typ für das Protokollierungsformat entweder WPP (Windows-Präprozessorformat für die Softwareablaufverfolgung, Standard), EventLog (Windows-Ereignisprotokoll-Format) oder IISLog (Datei im ASCII-Format basierend auf dem IIS-Protokolldatei-Format). Definieren Sie anschließend den Protokolliergrad (gemäß der Definition im entsprechenden Abschnitt in diesem Thema) und die Flags (gemäß der Definition im entsprechenden Abschnitt in diesem Thema).
    
    Für dieses Beispielszenario verwenden wir LyssProvider als Beispiel für die Anbietervariable.
    
    Geben Sie zum Erstellen eines Szenarios mit den definierten Optionen Folgendes ein:
    
   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    Beispiel:
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    Das alternative Format using-Name und-Parent:
    
   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>So erstellen Sie ein neues Szenario mit mehreren Anbietern mithilfe des Cmdlets „New-CsClsScenario“

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Für jeweils einen Geltungsbereich können Sie nur zwei Szenarien erstellen. Sie sind jedoch nicht auf eine feste Anzahl von Anbietern beschränkt. In diesem Beispiel wird davon ausgegangen, dass drei Anbieter erstellt wurden, die Sie allesamt dem Szenario zuweisen möchten, das Sie soeben erstellen. Die Variablennamen der Anbieter lauten „LyssProvider“, „ABServerProvider“ und „SIPStackProvider“. Wenn Sie einem Szenario mehrere Anbieter definieren und zuweisen möchten, geben Sie Folgendes in einer Skype for Business Server-Verwaltungsshell oder Windows PowerShell-Eingabeaufforderung ein:
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > Wie es in Windows PowerShell bekannt ist, ist die Konvention zum Erstellen einer Hashtabelle mit Werten `@{<variable>=<value1>, <value2>, <value>…}` , die assplatting verwendet, bekannt. Ausführliche Informationen zu splatting in Windows PowerShell finden Sie [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760)unter. 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>So ändern Sie ein vorhandenes Szenario mithilfe des Cmdlets „Set-CsClsScenario“

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Es gilt eine Beschränkung auf zwei Szenarien pro Geltungsbereich. Sie können jederzeit ändern, welche Szenarien ausgeführt werden, auch wenn gerade eine Protokollerfassungssitzung läuft. Falls Sie die ausgeführten Szenarien neu definieren, verwendet die aktuelle Protokollierungssitzung ab diesem Zeitpunkt nicht mehr das entfernte Szenario, sondern stattdessen das neue Szenario. Die Protokollinformationen, die im Rahmen des entfernten Szenarios erfasst wurden, verbleiben jedoch in den erfassten Protokollen. Wenn Sie ein neues Szenario definieren möchten, gehen Sie folgendermaßen vor (vorausgesetzt, es wird ein bereits definierter Anbieter mit dem Namen "S4Provider" hinzugefügt):
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    Beispiel:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    Falls Sie Anbieter ersetzen möchten, definieren Sie einen einzelnen Anbieter oder eine kommagetrennte Liste mit Anbietern, um die aktuelle Gruppe zu ersetzen. Für den Fall, dass Sie nur einen von vielen Anbietern ersetzen möchten, fügen Sie die aktuellen Anbieter zu den neuen Anbietern hinzu, um eine neue Gruppe von Anbietern zu erstellen, die sowohl die neuen als auch die zuvor vorhandenen Anbieter enthält. Geben Sie Folgendes ein, um sämtliche Anbieter durch eine neue Gruppe zu ersetzen:
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    Beispiel, bei dem die aktuelle aus „$LyssProvider“, „$ABServerProvider“ und „$SIPStackProvider“ bestehende Gruppe durch „$LyssServiceProvider“ ersetzt wird:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    Geben Sie Folgendes ein, um lediglich den Anbieter „$LyssProvider“ aus der aktuellen Gruppe mit „$LyssProvider“, „$ABServerProvider“ und „$SIPStackProvider“ durch den Anbieter „$LyssServiceProvider“ zu ersetzen:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>So entfernen Sie ein vorhandenes Szenario mithilfe des Cmdlets „Remove-CsClsScenario“

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Wenn Sie ein Szenario entfernen möchten, das zuvor definiert wurde, geben Sie Folgendes ein:
    
   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    Beispiel für das Entfernen des Szenarios „site:Redmond/LyssServiceScenario“:
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

Das Cmdlet **Remove-CsClsScenario** entfernt das angegebene Szenario. Die bereits erfassten Ablaufverfolgungen sind jedoch nach wie vor in den Protokollen verfügbar und können gesucht werden.
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>So laden und entladen Sie das Cmdlet „Edit-CsClsScenario“ mithilfe des Moduls „ClsScenarioEdit.psm1“

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
    > [!IMPORTANT]
    > Das Modul „ClsScenarioEdit.psm1“ wird als separater Webdownload zur Verfügung gestellt. Das Modul ist Teil der Debug-Tools für Skype for Business Server 2015. Die Debugtools werden standardmäßig im Ordner „C:\Programme\Skype for Business Server 2015\Debugging Tools“ installiert. 
  
2. Geben Sie in der Windows PowerShell Folgendes ein:
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > Durch erfolgreiches Laden des Moduls kehren Sie zur Windows PowerShell-Eingabeaufforderung zurück. Um zu überprüfen, ob das Modul geladen wurde und dass Edit-CsClsScenario verfügbar `Get-Help Edit-CsClsScenario`ist, geben Sie. Daraufhin sollte die grundlegende Kurzfassung der Syntax für „EditCsClsScenario“ angezeigt werden. 
  
3. Geben Sie zum Entladen des Moduls Folgendes ein:
    
   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > Durch erfolgreiches Entladen des Moduls kehren Sie zur Windows PowerShell-Eingabeaufforderung zurück. Um zu bestätigen, dass das Modul entladen wird, geben `Get-Help Edit-CsClsScenario`Sie. Windows PowerShell versucht, die Hilfe für das Cmdlet zu finden, und es wird ein Fehler ausgeführt. 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>So entfernen Sie einen vorhandenen Anbieter mithilfe des Edit-ClsController-Moduls aus einem Szenario

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Geben Sie in der Windows PowerShell Folgendes ein:
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > Durch erfolgreiches Laden des Moduls kehren Sie zur Windows PowerShell-Eingabeaufforderung zurück. Um zu überprüfen, ob das Modul geladen wurde und dass Edit-CsClsScenario verfügbar `Get-Help Edit-CsClsScenario`ist, geben Sie. Daraufhin sollte die grundlegende Kurzfassung der Syntax für „EditCsClsScenario“ angezeigt werden. 
  
3. Geben Sie Folgendes ein, um einen Anbieter aus dem Szenario „AlwaysOn“ zu entfernen:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   Beispiel:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   Bei den Parametern „ScenarioName“ und „ProviderName“ handelt es sich um Positionsparameter (d. h., dass sie in der erwarteten Position in der Eingabeaufforderung definiert werden müssen). Der Parametername muss nicht explizit definiert werden, sofern der Szenarioname an zweiter Position und der Anbieter an dritter Position steht (in Bezug auf den Namen des Cmdlets, der an erster Position steht):
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   Die Positions Platzierung der Parameterwerte gilt nur für Scenario und-Provider. Alle anderen Parameter müssen explizit definiert werden.
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>So fügen Sie ein Szenario mit dem Modul „Edit-ClsController“ hinzu

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Geben Sie Folgendes ein, um einen Anbieter zum Szenario „AlwaysOn“ hinzuzufügen:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    Beispiel:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    Mögliche Typen für „-Loglevel“ sind „Fatal“, „Error“, „Warning“, „Info“, „Verbose“, „Debug“ oder „All“. -Flags können beliebige der vom Anbieter unterstützten Flags sein, beispielsweise TF_COMPONENT, TF_DIAG. -Flags können auch vom Wert "alle" sein
    
   Das vorherige Beispiel kann auch mithilfe der Positionsfunktion des Cmdlets eingegeben werden. So würden Sie beispielsweise Folgendes eingeben, um „ChatServer“ zum Szenario „AlwaysOn“ hinzuzufügen:
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
