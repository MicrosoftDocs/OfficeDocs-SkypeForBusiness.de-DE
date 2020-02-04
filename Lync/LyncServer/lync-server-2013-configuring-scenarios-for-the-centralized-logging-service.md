---
title: 'Lync Server 2013: Konfigurieren von Szenarien für den zentralisierten Protokollierungsdienst'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring scenarios for the Centralized Logging Service
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49733682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd3933ff81fad6947fcc4ab1ff7a7dc9ad136c39
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-scenarios-for-the-centralized-logging-service-in-lync-server-2013"></a>Konfigurieren von Szenarien für den zentralisierten Protokollierungsdienst in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-05_

Szenarien definieren den Bereich (Global, Site, Pool oder Computer) und welche Anbieter im zentralisierten Protokollierungsdienst zu verwenden sind. Mithilfe von Szenarien können Sie die Ablaufverfolgung für Dienstanbieter aktivieren oder deaktivieren (z. B. bezüglich S4, SIPStack, IM und Anwesenheit). Durch das Konfigurieren eines Szenarios können Sie alle Dienstanbieter für eine bestimmte logische Sammlung gruppieren, die sich mit einem bestimmten Problemzustand befassen. Wenn Sie feststellen, dass ein Szenario geändert werden muss, um die Anforderungen zur Problembehandlung und Protokollierung zu erfüllen, bietet Ihnen die lync Server 2013-Debug-Tools ein Windows PowerShell-Modul mit dem Namen *ClsController. psm1* , das eine Funktion mit dem Namen *Edit-CsClsScenario*enthält. Dieses Modul soll dazu dienen, die Eigenschaften des betreffenden Szenarios zu bearbeiten. Beispiele für die Funktionsweise des Moduls erhalten Sie in diesem Thema. Die lync Server 2013-Debug-Tools werden über den folgenden Link heruntergeladen:[http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)

<div>


> [!IMPORTANT]  
> Für einen bestimmten Bereich – Website, Global, Pool oder Computer – können Sie maximal zwei Szenarien zu einem bestimmten Zeitpunkt ausführen. Um zu ermitteln, welche Szenarien zurzeit ausgeführt werden, verwenden Sie Windows PowerShell und <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A>. Mithilfe von Windows PowerShell und der <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">CsClsScenario</A>können Sie dynamisch ändern, welche Szenarien ausgeführt werden. Sie können ändern, welche Szenarien während einer Protokollierungssitzung ausgeführt werden, um die Daten, die Sie sammeln, und von welchen Anbietern anzupassen oder zu verfeinern.



</div>

Wenn Sie die Funktionen für den zentralisierten Protokollierungsdienst mithilfe der lync Server-Verwaltungsshell ausführen möchten, müssen Sie ein Mitglied der CsAdministrator-oder CsServerAdministrator-Sicherheitsgruppe (Role-Based Access Control, RBAC) oder eine benutzerdefinierte RBAC-Rolle sein, die entweder dieser beiden Gruppen. Führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell oder in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde, einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Beispiel:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

Nachfolgend wird beschrieben, wie Sie ein Szenario definieren, ein Szenario ändern, wie Sie abrufen, welche Szenarien ausgeführt werden, wie Sie ein Szenario entfernen und wie Sie die Inhalte eines Szenarios auf eine optimale Problembehandlung abstimmen können. Es gibt zwei Möglichkeiten zum Ausgeben von Befehlen für zentralisierte Protokollierungsdienste. Sie können\\die CLSController. exe verwenden, die sich standardmäßig im Verzeichnis C: Programmdateien\\allgemeine Dateien\\Microsoft lync Server 2013\\CLSAgent befindet. Oder Sie können die lync Server-Verwaltungsshell zum Ausgeben von Windows PowerShell-Befehlen verwenden. Der wichtige Unterschied besteht darin, dass bei der Verwendung von CLSController. exe in der Befehlszeile eine begrenzte Auswahl von Szenarien verfügbar ist. Wenn Sie Windows PowerShell verwenden, können Sie neue Szenarien für die Verwendung in ihren Protokollierungssitzungen definieren.

Wie in der [Übersicht über den zentralisierten Protokollierungsdienst in lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)eingeführt, sind die Elemente eines Szenarios:

  - **Anbieter**   Wenn Sie mit OCSLogger vertraut sind, sind Anbieter die Komponenten, die Sie angeben, um OCSLogger zu informieren, von welchem das Ablaufverfolgungsmodul Protokolle sammeln soll. Die Anbieter sind die gleichen Komponenten und haben in vielen Fällen denselben Namen wie die Komponenten in OCSLogger. Wenn Sie mit OCSLogger nicht vertraut sind, sind Anbieterserver rollenspezifische Komponenten, von denen der zentralisierte Protokollierungsdienst Protokolle sammeln kann. Details zur Konfiguration von Anbietern finden Sie unter [Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst in lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).

  - **Identity**   the Parameter – Identity legt den Bereich und den Namen des Szenarios fest. So können Sie beispielsweise einen Bereich von "Global" festlegen und das Szenario mit "LyssServiceScenario" identifizieren. Wenn Sie die beiden kombinieren, definieren Sie die Identität (beispielsweise "Global/LyssServiceScenario").
    
    Optional können Sie auch die Parameter „–Name“ und „–Parent“ verwenden. Sie definieren den Parameter „Name“, um das Szenario eindeutig zu identifizieren. Wenn Sie „Name“ verwenden, müssen Sie auch „Parent“ verwenden, um das Szenario entweder einem globalen oder einem standortweiten Geltungsbereich hinzuzufügen.
    
    <div>
    

    > [!IMPORTANT]  
    > Falls Sie die Parameter „Name“ und „Parent“ verwenden, können Sie den Parameter <STRONG>–Identity</STRONG> nicht verwenden.

    
    </div>

<div>

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>So erstellen Sie ein neues Szenario mit dem Cmdlet „New-CsClsScenario“

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Verwenden Sie für die Erstellung eines neuen Szenarios für eine Protokollierungssitzung [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) und definieren Sie den Namen für das Szenario (d. h. dessen eindeutige Identifikation). Wählen Sie als Typ für das Protokollierungsformat entweder WPP (Windows-Präprozessorformat für die Softwareablaufverfolgung, Standard), EventLog (Windows-Ereignisprotokoll-Format) oder IISLog (Datei im ASCII-Format basierend auf dem IIS-Protokolldatei-Format). Definieren Sie anschließend den Protokolliergrad (gemäß der Definition im entsprechenden Abschnitt in diesem Thema) und die Flags (gemäß der Definition im entsprechenden Abschnitt in diesem Thema).
    
    Für dieses Beispielszenario verwenden wir LyssProvider als Beispiel für die Anbietervariable.
    
    Geben Sie zum Erstellen eines Szenarios mit den definierten Optionen Folgendes ein:
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    Beispiel:
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    Alternatives Format unter Verwendung von „–Name“ und „–Parent“:
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

</div>

<div>

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>So erstellen Sie ein neues Szenario mit mehreren Anbietern mithilfe des Cmdlets „New-CsClsScenario“

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Für jeweils einen Geltungsbereich können Sie nur zwei Szenarien erstellen. Sie sind jedoch nicht auf eine feste Anzahl von Anbietern beschränkt. In diesem Beispiel wird davon ausgegangen, dass drei Anbieter erstellt wurden, die Sie allesamt dem Szenario zuweisen möchten, das Sie soeben erstellen. Die Variablennamen der Anbieter lauten „LyssProvider“, „ABServerProvider“ und „SIPStackProvider“. Wenn Sie einem Szenario mehrere Anbieter definieren und zuweisen möchten, geben Sie Folgendes an einer lync Server-Verwaltungsshell oder Windows PowerShell-Eingabeaufforderung ein:
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    <div>
    

    > [!NOTE]  
    > Wie es in Windows PowerShell bekannt ist, wird die Konvention zum Erstellen einer Hashtabelle mit Werten <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> unter dem Namen <EM>splatting</EM>. Ausführliche Informationen zu splatting in Windows PowerShell finden Sie <A href="http://go.microsoft.com/fwlink/p/?linkid=267760">http://go.microsoft.com/fwlink/p/?LinkId=267760</A>unter.

    
    </div>

</div>

<div>

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>So ändern Sie ein vorhandenes Szenario mithilfe des Cmdlets „Set-CsClsScenario“

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Es gilt eine Beschränkung auf zwei Szenarien pro Geltungsbereich. Sie können jederzeit ändern, welche Szenarien ausgeführt werden, auch wenn gerade eine Protokollerfassungssitzung läuft. Falls Sie die ausgeführten Szenarien neu definieren, verwendet die aktuelle Protokollierungssitzung ab diesem Zeitpunkt nicht mehr das entfernte Szenario, sondern stattdessen das neue Szenario. Die Protokollinformationen, die im Rahmen des entfernten Szenarios erfasst wurden, verbleiben jedoch in den erfassten Protokollen. Gehen Sie wie folgt vor, um ein neues Szenarios zu definieren (hierbei wird angenommen, dass ein bereits definierter Anbieter namens „S4Provider“ hinzugefügt wurde):
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    Beispiel:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    Falls Sie Anbieter ersetzen möchten, definieren Sie einen einzelnen Anbieter oder eine kommagetrennte Liste mit Anbietern, um die aktuelle Gruppe zu ersetzen. Für den Fall, dass Sie nur einen von vielen Anbietern ersetzen möchten, fügen Sie die aktuellen Anbieter zu den neuen Anbietern hinzu, um eine neue Gruppe von Anbietern zu erstellen, die sowohl die neuen als auch die zuvor vorhandenen Anbieter enthält. Geben Sie Folgendes ein, um sämtliche Anbieter durch eine neue Gruppe zu ersetzen:
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    Beispiel, bei dem die aktuelle aus „$LyssProvider“, „$ABServerProvider“ und „$SIPStackProvider“ bestehende Gruppe durch „$LyssServiceProvider“ ersetzt wird:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    Geben Sie Folgendes ein, um lediglich den Anbieter „$LyssProvider“ aus der aktuellen Gruppe mit „$LyssProvider“, „$ABServerProvider“ und „$SIPStackProvider“ durch den Anbieter „$LyssServiceProvider“ zu ersetzen:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

</div>

<div>

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>So entfernen Sie ein vorhandenes Szenario mithilfe des Cmdlets „Remove-CsClsScenario“

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Wenn Sie ein Szenario entfernen möchten, das zuvor definiert wurde, geben Sie Folgendes ein:
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    Beispiel für das Entfernen des Szenarios „site:Redmond/LyssServiceScenario“:
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

Das Cmdlet **Remove-CsClsScenario** entfernt das angegebene Szenario. Die bereits erfassten Ablaufverfolgungen sind jedoch nach wie vor in den Protokollen verfügbar und können gesucht werden.

</div>

<div>

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clscontrollerpsm1-module"></a>So laden und Entladen Sie das Cmdlet "Edit-CsClsScenario" mit dem ClsController. psm1-Modul

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.
    
    <div>
    

    > [!IMPORTANT]  
    > Das ClsController. psm1-Modul wird als separater Webdownload bereitgestellt. Das Modul gehört zu den lync Server 2013-Debugging-Tools. Standardmäßig werden die Debug-Tools im Verzeichnis C:\Program Files\Lync Server 2013 \ Debugging Tools installiert.

    
    </div>

2.  Geben Sie in der Windows PowerShell Folgendes ein:
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    <div>
    

    > [!TIP]  
    > Durch erfolgreiches Laden des Moduls kehren Sie zur Windows PowerShell-Eingabeaufforderung zurück. Um zu überprüfen, ob das Modul geladen wurde und dass Edit-CsClsScenario verfügbar <CODE>Get-Help Edit-CsClsScenario</CODE>ist, geben Sie. Daraufhin sollte die grundlegende Kurzfassung der Syntax für „EditCsClsScenario“ angezeigt werden.

    
    </div>

3.  Geben Sie zum Entladen des Moduls Folgendes ein:
    
        Remove-Module ClsController
    
    <div>
    

    > [!TIP]  
    > Durch erfolgreiches Entladen des Moduls kehren Sie zur Windows PowerShell-Eingabeaufforderung zurück. Um zu bestätigen, dass das Modul entladen wird, geben <CODE>Get-Help Edit-CsClsScenario</CODE>Sie. Windows PowerShell versucht, die Hilfe für das Cmdlet zu finden, und es wird ein Fehler ausgeführt.

    
    </div>

</div>

<div>

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>So entfernen Sie einen vorhandenen Anbieter mithilfe des Edit-ClsController-Moduls aus einem Szenario

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Geben Sie Folgendes ein, um einen Anbieter aus dem Szenario „AlwaysOn“ zu entfernen:
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    Beispiel:
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    Bei den Parametern „ScenarioName“ und „ProviderName“ handelt es sich um Positionsparameter (d. h., dass sie in der erwarteten Position in der Eingabeaufforderung definiert werden müssen). Der Parametername muss nicht explizit definiert werden, sofern der Szenarioname an zweiter Position und der Anbieter an dritter Position steht (in Bezug auf den Namen des Cmdlets, der an erster Position steht):
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    Die Platzierung der Parameterwerte an einer bestimmten Position gilt nur für  „–Scenario“ und „–Provider“. Alle anderen Parameter müssen explizit definiert werden.

</div>

<div>

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>So fügen Sie ein Szenario mit dem Modul „Edit-ClsController“ hinzu

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Geben Sie Folgendes ein, um einen Anbieter zum Szenario „AlwaysOn“ hinzuzufügen:
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    Beispiel:
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    \-LogLevel kann vom Typ fatal, Error, Warning, Info, Verbose, Debug oder all sein. – Flags können beliebige der vom Anbieter unterstützten Flags sein, wie TF\_-Komponente, TF\_diag. Der Wert ALL ist für „–Flags“ ebenfalls möglich.
    
    Das vorherige Beispiel kann auch mithilfe der Positionsfunktion des Cmdlets eingegeben werden. So würden Sie beispielsweise Folgendes eingeben, um „ChatServer“ zum Szenario „AlwaysOn“ hinzuzufügen:
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

</div>

</div>

<span> </span>

</div>

</div>

</div>

