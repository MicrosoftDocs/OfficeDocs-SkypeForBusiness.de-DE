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
ms.openlocfilehash: 6a39bcd23516970edf1c4694a8eff1ecb682eda1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-scenarios-for-the-centralized-logging-service-in-lync-server-2013"></a>Konfigurieren von Szenarien für den zentralisierten Protokollierungsdienst in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-05_

Szenarien definieren den Bereich (Global, Standort, Pool oder Computer) und welche Anbieter im zentralisierten Protokollierungsdienst verwendet werden sollen. Mithilfe von Szenarios können Sie die Ablaufverfolgung für Anbieter aktivieren oder deaktivieren (beispielsweise S4, SIPStack, Chat und Anwesenheit). Durch Konfigurieren eines Szenarios können Sie alle Anbieter für eine bestimmte logische Auflistung gruppieren, die eine bestimmte Problem Bedingung behandeln. Wenn Sie feststellen, dass ein Szenario geändert werden muss, um die Anforderungen an die Problembehandlung und Protokollierung zu erfüllen, bietet Ihnen die lync Server 2013 Debug-Tools ein Windows PowerShell Modul mit dem Namen *ClsController. psm1* , das eine Funktion mit dem Namen *Edit-CsClsScenario*enthält. Der Zweck des Moduls besteht darin, die Eigenschaften des benannten Szenarios zu bearbeiten. Beispiele zur Funktionsweise dieses Moduls finden Sie in diesem Thema. Die lync Server 2013 Debug-Tools werden unter folgendem Link heruntergeladen:[http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)

<div>


> [!IMPORTANT]  
> Für einen bestimmten Bereich – Standort, Global, Pool oder Computer – können Sie zu einem beliebigen Zeitpunkt maximal zwei Szenarien ausführen. Verwenden Sie Windows PowerShell und <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A>, um zu ermitteln, welche Szenarien derzeit aktiv sind. Mithilfe von Windows PowerShell und <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">CsClsScenario</A>können Sie dynamisch ändern, welche Szenarien gerade durchführen. Sie können ändern, welche Szenarien während einer Protokollierungssitzung durchführen, um die Daten, die Sie sammeln, anzupassen oder zu verfeinern, und von welchen Anbietern.



</div>

Zum Ausführen der Funktionen für den zentralisierten Protokollierungsdienst mit dem lync Server-Verwaltungsshell müssen Sie Mitglied der rollenbasierten Sicherheitsgruppen "CsAdministrator" oder "CsServerAdministrator" oder einer benutzerdefinierten RBAC-Rolle sein, die entweder dieser beiden Gruppen. Um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde, einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben, führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell oder der Windows PowerShell-Eingabeaufforderung aus:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Beispiel:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

Nachfolgend wird beschrieben, wie Sie ein Szenario ändern, wie Sie abrufen, welche Szenarien ausgeführt werden, wie Sie ein Szenario entfernen und wie Sie die Inhalte eines Szenarios auf eine optimale Problembehandlung abstimmen können. Es gibt zwei Möglichkeiten zum Ausgeben von Befehlen für den zentralisierten Protokollierungsdienst. Sie können\\die CLSController. exe verwenden, die sich standardmäßig im Verzeichnis C: Program Files\\Common Files\\Microsoft lync Server 2013\\CLSAgent befindet. Sie können auch die lync Server-Verwaltungsshell verwenden, um Windows PowerShell Befehle auszugeben. Der entscheidende Unterschied liegt darin, dass Sie bei Verwendung der Datei "CLSController.exe" an der Befehlszeile eine begrenzte Auswahl an Szenarien zur Verfügung haben. Wenn Sie Windows PowerShell verwenden, können Sie neue Szenarien für die Verwendung in ihren Protokollierungssitzungen definieren.

Wie in der [Übersicht über den zentralisierten Protokollierungsdienst in lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)vorgestellt, sind die Elemente eines Szenarios wie folgt dargestellt:

  - **Anbieter**   Wenn Sie mit OCSLogger vertraut sind, handelt es sich bei Anbietern um die Komponenten, die Sie OCSLogger mitteilen, welche Protokolle von dem Ablaufverfolgungsmodul erfasst werden sollen. Die Anbieter entsprechen den Komponenten in OCSLogger und haben in vielen Fällen auch dieselben Namen. Wenn Sie mit OCSLogger nicht vertraut sind, handelt es sich bei Anbietern um Serverrollen spezifische Komponenten, von denen der zentralisierte Protokollierungsdienst Protokolle erfassen kann. Ausführliche Informationen zur Konfiguration von Anbietern finden Sie unter [Configuring Providers for zentralisiert Logging Service in lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).

  - **Identity**   der Parameter – Identity legt den Bereich und den Namen des Szenarios fest. So können Sie beispielsweise den Geltungsbereich "global" festlegen und das Szenario "LyssServiceScenario" nennen. Durch die Kombination aus diesen beiden Festlegungen definieren Sie den Parameter "Identitiy" (z. B. "global/LyssServiceScenario").
    
    Optional können Sie auch die Parameter "–Name" und "–Parent" verwenden. Sie definieren den Parameter "Name", um das Szenario eindeutig zu identifizieren. Wenn Sie "Name" verwenden, müssen Sie auch "Parent" verwenden, um das Szenario entweder einem globalen oder einem standortweiten Geltungsbereich hinzuzufügen.
    
    <div>
    

    > [!IMPORTANT]  
    > Falls Sie die Parameter "Name" und "Parent" verwenden, können Sie den Parameter <STRONG>–Identity</STRONG> nicht verwenden.

    
    </div>

<div>

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>So erstellen Sie ein neues Szenario mit dem Cmdlet "New-CsClsScenario"

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Verwenden Sie für die Erstellung eines neuen Szenarios für eine Protokollierungssitzung [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider), und definieren Sie den Namen für das Szenario (d. h. dessen eindeutige Identifizierung). Wählen Sie als Typ für das Protokollierungsformat entweder WPP (Windows-Präprozessorformat für die Softwareablaufverfolgung, Standard), EventLog (Windows-Ereignisprotokoll-Format) oder IISLog (Datei im ASCII-Format basierend auf dem IIS-Protokolldatei-Format). Definieren Sie anschließend den Protokolliergrad (gemäß der Definition im entsprechenden Abschnitt in diesem Thema) und die Flags (gemäß der Definition im entsprechenden Abschnitt in diesem Thema).
    
    Für dieses Beispielszenario verwenden wir LyssProvider als Beispiel für die Anbietervariable.
    
    Geben Sie zum Erstellen eines Szenarios mit den definierten Optionen Folgendes ein:
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    Beispiel:
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    Alternatives Format unter Verwendung von "–Name" und "–Parent":
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

</div>

<div>

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>So erstellen Sie ein neues Szenario mit mehreren Anbietern mit dem Cmdlet "New-CsClsScenario"

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Für jeweils einen Geltungsbereich können Sie nur zwei Szenarien erstellen. Sie sind jedoch nicht auf eine feste Anzahl von Anbietern beschränkt. In diesem Beispiel wird davon ausgegangen, dass drei Anbieter erstellt wurden, die Sie allesamt dem Szenario zuweisen möchten, das Sie soeben erstellen. Die Variablennamen der Anbieter lauten LyssProvider, ABServerProvider und SIPStackProvider. Geben Sie zum Definieren und zuweisen mehrerer Anbieter zu einem Szenario an einer lync Server-Verwaltungsshell-oder Windows PowerShell-Eingabeaufforderung Folgendes ein:
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    <div>
    

    > [!NOTE]  
    > Wie in Windows PowerShell bekannt, wird die Konvention zum Erstellen einer Hashtabelle mit Werten verwendet <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> als <EM>splatting</EM>bezeichnet. Ausführliche Informationen zu splatting in Windows PowerShell finden Sie <A href="http://go.microsoft.com/fwlink/p/?linkid=267760">http://go.microsoft.com/fwlink/p/?LinkId=267760</A>unter.

    
    </div>

</div>

<div>

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>So ändern Sie ein vorhandenes Szenario mit dem Cmdlet "Set-CsClsScenario"

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Es gilt eine Beschränkung auf zwei Szenarien pro Geltungsbereich. Sie können jederzeit ändern, welche Szenarien ausgeführt werden, auch wenn gerade eine Protokollerfassungssitzung läuft. Falls Sie die ausgeführten Szenarien neu definieren, verwendet die aktuelle Protokollierungssitzung ab diesem Zeitpunkt das entfernte Szenario nicht mehr, sondern stattdessen das neue Szenario. Die Protokollinformationen, die im Rahmen des entfernten Szenarios erfasst wurden, verbleiben jedoch in den erfassten Protokollen. Gehen Sie wie folgt vor, um ein neues Szenarios zu definieren (hierbei wird angenommen, dass ein bereits definierter Anbieter namens "S4Provider" hinzugefügt wurde):
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    Beispiel:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    Falls Sie Anbieter ersetzen möchten, definieren Sie einen einzelnen Anbieter oder eine durch Kommas getrennte Liste mit Anbietern, um die aktuelle Gruppe zu ersetzten. Für den Fall, dass Sie nur einen von vielen Anbietern ersetzen möchten, fügen Sie die aktuellen Anbieter zu den neuen Anbietern hinzu, um eine neue Gruppe von Anbietern zu erstellen, die sowohl die neuen als auch die zuvor vorhandenen Anbieter enthält. Geben Sie Folgendes ein, um sämtliche Anbieter durch eine neue Gruppe zu ersetzen:
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    Beispiel, bei dem die aktuelle aus "$LyssProvider", "$ABServerProvider" und "$SIPStackProvider" bestehende Gruppe durch "$LyssServiceProvider" ersetzt wird:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    Geben Sie Folgendes ein, um lediglich den Anbieter "$LyssProvider" aus der aktuellen Gruppe mit "$LyssProvider", "$ABServerProvider" und "$SIPStackProvider" durch den Anbieter "$LyssServiceProvider" zu ersetzen:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

</div>

<div>

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>So entfernen Sie ein vorhandenes Szenario mit dem Cmdlet "Remove-CsClsScenario"

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Wenn Sie ein Szenario entfernen möchten, das zuvor definiert wurde, geben Sie Folgendes ein:
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    Beispiel für das Entfernen des Szenarios "site:Redmond/LyssServiceScenario":
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

Das Cmdlet **Remove-CsClsScenario** entfernt das angegebene Szenario, die bereits erfassten Ablaufverfolgungen sind jedoch nach wie vor in den Protokollen verfügbar und können gesucht werden.

</div>

<div>

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clscontrollerpsm1-module"></a>So laden und entladen Sie das Cmdlet "Edit-CsClsScenario" mithilfe des ClsController.psm1-Moduls

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.
    
    <div>
    

    > [!IMPORTANT]  
    > Das ClsController.psm1-Modul wird als separater Webdownload zur Verfügung gestellt. Das Modul ist Teil der lync Server 2013 Debugging-Tools. Die Debuggingtools werden standardmäßig im Ordner "C:\Programme\Lync Server 2013\Debugging Tools" installiert.

    
    </div>

2.  Geben Sie im Windows PowerShell Folgendes ein:
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    <div>
    

    > [!TIP]  
    > Durch erfolgreiches Laden des Moduls kehren Sie zur Windows PowerShell-Eingabeaufforderung zurück. Geben <CODE>Get-Help Edit-CsClsScenario</CODE>Sie ein, um zu bestätigen, dass das Modul geladen wurde und dass Edit-CsClsScenario verfügbar ist. Daraufhin sollte die grundlegende Kurzfassung der Syntax für  EditCsClsScenario angezeigt werden.

    
    </div>

3.  Geben Sie zum Entladen der Module Folgendes ein:
    
        Remove-Module ClsController
    
    <div>
    

    > [!TIP]  
    > Bei erfolgreicher Entladung des Moduls kehren Sie zur Windows PowerShell Eingabeaufforderung zurück. Geben <CODE>Get-Help Edit-CsClsScenario</CODE>Sie ein, um zu bestätigen, dass das Modul entladen wurde. Windows PowerShell versuchen, die Hilfe für das Cmdlet zu finden, und es tritt ein Fehler auf.

    
    </div>

</div>

<div>

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>So entfernen Sie einen vorhandenen Anbieter mithilfe des Edit-ClsController-Moduls aus einem Szenario

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Geben Sie Folgendes ein, um einen Anbieter aus dem AlwaysOn-Szenario zu entfernen:
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    Beispiel:
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    Bei den Parametern "ScenarioName" und "ProviderName" handelt es sich um Positionsparameter (d. h., dass sie in der erwarteten Position in der Eingabeaufforderung definiert werden müssen). Der Parametername muss nicht explizit definiert werden, sofern der Szenarioname an zweiter Position und der Anbieter an dritter Position steht (in Bezug auf den Namen des Cmdlets, der an erster Position steht):
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    Die Platzierung der Parameterwerte an einer bestimmten Position gilt nur für  "–Scenario" und "–Provider". Alle anderen Parameter müssen explizit definiert werden.

</div>

<div>

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>So fügen Sie ein Szenario mit dem Edit-ClsController-Modul hinzu

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Geben Sie Folgendes ein, um einen Anbieter zum AlwaysOn-Szenario hinzuzufügen:
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    Beispiel:
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    \-LogLevel kann vom Typ "Fatal", "Error", "Warning", "Info", "Verbose", "Debug" oder "All" sein. – Flags können alle Flags sein, die vom Anbieter unterstützt werden, wie TF\_Component, TF\_diag. Der Wert ALL ist für "–Flags" ebenfalls möglich.
    
    Das vorherige Beispiel kann auch mithilfe des Positionsfeatures des Cmdlets eingegeben werden. So würden Sie beispielsweise Folgendes eingeben, um "ChatServer" zum AlwaysOn-Szenario hinzuzufügen:
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

</div>

</div>

<span> </span>

</div>

</div>

</div>

