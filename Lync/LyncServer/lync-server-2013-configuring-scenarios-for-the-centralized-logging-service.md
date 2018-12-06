---
title: Konfigurieren von Szenarien für den zentralisierten Protokollierungsdienst
TOCTitle: Konfigurieren von Szenarien für den zentralisierten Protokollierungsdienst
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49890783
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Szenarien für den zentralisierten Protokollierungsdienst

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Szenarien definieren den Geltungsbereich (global, standortweit, poolweit oder computerbezogen) für den Zentraler Protokollierungsdienst und welche Dienstanbieter dafür verwendet werden. Mithilfe von Szenarien können Sie die Ablaufverfolgung für Dienstanbieter aktivieren oder deaktivieren (z. B. bzgl. S4, SIPStack, IM und Anwesenheit). Durch das Konfigurieren eines Szenarios können Sie alle Dienstanbieter für eine bestimmte logische Sammlung gruppieren, die sich mit einem bestimmten Problemzustand befassen. Sollten Sie feststellen, dass ein Szenario besser auf Ihre Problembehandlungs- und Protokollierungsbedürfnisse abgestimmt werden muss, erhalten Sie in den Debugtools von Lync Server 2013 ein Windows PowerShell-Modul namens *ClsController.psm1*, das die Funktion *Edit-CsClsScenario* enthält. Das Modul soll dazu dienen, die Eigenschaften des betreffenden Szenarios zu bearbeiten. Beispiele für die Funktionsweise des Moduls erhalten Sie in diesem Thema. Die Lync Server 2013-Debugtools werden unter dem folgenden Link heruntergeladen: [http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)


> [!IMPORTANT]
> Sie können für einen bestimmten Geltungsbereich – Standort, global, Pool oder Computer – maximal zwei Szenarien gleichzeitig ausführen. Verwenden Sie Windows PowerShell und <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A>, um festzustellen, welche Szenarien derzeit ausgeführt werden. Mithilfe von Windows PowerShell und <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsScenario">Set-CsClsScenario</A> können Sie dynamisch ändern, welche Szenarien ausgeführt werden. Sie können im Laufe einer Protokollierungssitzung ändern, welche Szenarien ausgeführt werden, um somit anzupassen bzw. genau abzustimmen, welche Daten von welchen Dienstanbietern erfassst werden sollen.



Um die Funktionen des Zentraler Protokollierungsdienst über die Lync Server-Verwaltungsshell auszuführen, müssen Sie ein Mitglied der Sicherheitsgruppen "CsAdministrator" oder "CsServerAdministrator" für rollenbasierten Zugriffssteuerungsrollen (RBAC, Role-Based Access Control) oder einer benutzerdefinierten rollenbasierten Zugriffssteuerungsrolle sein, die eine dieser beiden Gruppen enthält. Geben Sie den folgenden Befehl an der Lync Server-Verwaltungsshell- oder der Windows PowerShell-Eingabeaufforderung ein, um eine Liste aller rollenbasierten Zugriffssteuerungsrollen zurückzugeben, die diesem Cmdlet zugewiesen wurden (einschließlich der benutzerdefinierten rollenbasierten Zugriffssteuerungsrollen, die Sie selbst erstellt haben):

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Beispiel:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

Nachfolgend wird beschrieben, wie Sie ein Szenario ändern, wie Sie abrufen, welche Szenarien ausgeführt werden, wie Sie ein Szenario entfernen und wie Sie die Inhalte eines Szenarios auf eine optimale Problembehandlung abstimmen können. Es gibt zwei Möglichkeiten für die Ausgabe von Zentraler Protokollierungsdienst-Befehlen. Sie können die Datei "CLSController.exe" verwenden, die sich standardmäßig im Verzeichnis "C:\\Programme\\Gemeinsame Dateien\\Microsoft Lync Server 2013\\CLSAgent" befindet. Oder Sie verwenden die Lync Server-Verwaltungsshell für die Ausgabe von Windows PowerShell-Befehlen. Der entscheidende Unterschied liegt darin, dass Sie bei Verwendung der Datei "CLSController.exe" an der Befehlszeile eine begrenzte Auswahl an Szenarien zur Verfügung haben. Bei der Verwendung von Windows PowerShell können Sie neue Szenarien für Ihre Protokollierungssitzungen definieren.

Wie bereits einführend im Abschnitt [Übersicht über den zentralisierten Protokollierungsdienst](lync-server-2013-overview-of-the-centralized-logging-service.md) beschrieben, weist ein Szenario die folgenden Elemente auf:

  - **Anbieter**   Wenn Sie mit OCSLogger vertraut sind, sind Ihnen Anbieter als die Komponenten bekannt, die Sie angeben, um in OCSLogger anzugeben, wovon das Ablaufverfolgungsmodul Protokolle erfassen soll. Die Anbieter entsprechen den Komponenten in OCSLogger und haben in vielen Fällen auch dieselben Namen. Sollten Sie nicht mit OCSLogger vertraut sein, so können Anbieter als serverrollenspezifische Komponenten definiert werden, aus denen der Zentraler Protokollierungsdienst Protokolle erfassen kann. Ausführliche Informationen zum Konfigurieren von Anbietern, erhalten Sie im Abschnitt [Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst](lync-server-2013-configuring-providers-for-centralized-logging-service.md).

  - **Identität**   Der Parameter "–Identity" legt den Geltungsbereich und Namen des Szenarios fest. So können Sie beispielsweise den Geltungsbereich "global" festlegen und das Szenario "LyssServiceScenario" nennen. Durch die Kombination aus diesen beiden Festlegungen definieren Sie den Parameter "Identitiy" (z. B. "global/LyssServiceScenario").
    
    Optional können Sie auch die Parameter "–Name" und "–Parent" verwenden. Sie definieren den Parameter "Name", um das Szenario eindeutig zu identifizieren. Wenn Sie "Name" verwenden, müssen Sie auch "Parent" verwenden, um das Szenario entweder einem globalen oder einem standortweiten Geltungsbereich hinzuzufügen.
    

    > [!IMPORTANT]
    > Falls Sie die Parameter "Name" und "Parent" verwenden, können Sie den Parameter <STRONG>–Identity</STRONG> nicht verwenden.



## So erstellen Sie ein neues Szenario mit dem Cmdlet "New-CsClsScenario"

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Verwenden Sie für die Erstellung eines neuen Szenarios für eine Protokollierungssitzung [New-CsClsProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsProvider), und definieren Sie den Namen für das Szenario (d. h. dessen eindeutige Identifizierung). Wählen Sie als Typ für das Protokollierungsformat entweder WPP (Windows-Präprozessorformat für die Softwareablaufverfolgung, Standard), EventLog (Windows-Ereignisprotokoll-Format) oder IISLog (Datei im ASCII-Format basierend auf dem IIS-Protokolldatei-Format). Definieren Sie anschließend den Protokolliergrad (gemäß der Definition im entsprechenden Abschnitt in diesem Thema) und die Flags (gemäß der Definition im entsprechenden Abschnitt in diesem Thema).
    
    Für dieses Beispielszenario verwenden wir LyssProvider als Beispiel für die Anbietervariable.
    
    Geben Sie zum Erstellen eines Szenarios mit den definierten Optionen Folgendes ein:
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    Beispiel:
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    Alternatives Format unter Verwendung von "–Name" und "–Parent":
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

## So erstellen Sie ein neues Szenario mit mehreren Anbietern mit dem Cmdlet "New-CsClsScenario"

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Für jeweils einen Geltungsbereich können Sie nur zwei Szenarien erstellen. Sie sind jedoch nicht auf eine feste Anzahl von Anbietern beschränkt. In diesem Beispiel wird davon ausgegangen, dass drei Anbieter erstellt wurden, die Sie allesamt dem Szenario zuweisen möchten, das Sie soeben erstellen. Die Variablennamen der Anbieter lauten LyssProvider, ABServerProvider und SIPStackProvider. Geben Sie Folgendes an einer Lync Server-Verwaltungsshell- oder Windows PowerShell-Eingabeaufforderung ein, um mehrere Anbieter zu definieren und einem Szenario zuzuweisen:
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    

    > [!NOTE]
    > Bekanntermaßen wird in der Windows PowerShell die Konvention für die Erstellung einer Hashtabelle unter Verwendung von <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> als <EM>Splatten</EM> bezeichnet. Ausführliche Informationen zum Splatten in Windows PowerShell erhalten Sie unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=267760%26clcid=0x407">http://go.microsoft.com/fwlink/?linkid=267760&amp;clcid=0x407</A>.



## So ändern Sie ein vorhandenes Szenario mit dem Cmdlet "Set-CsClsScenario"

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

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

## So entfernen Sie ein vorhandenes Szenario mit dem Cmdlet "Remove-CsClsScenario"

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Wenn Sie ein Szenario entfernen möchten, das zuvor definiert wurde, geben Sie Folgendes ein:
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    Beispiel für das Entfernen des Szenarios "site:Redmond/LyssServiceScenario":
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

Das Cmdlet **Remove-CsClsScenario** entfernt das angegebene Szenario, die bereits erfassten Ablaufverfolgungen sind jedoch nach wie vor in den Protokollen verfügbar und können gesucht werden.

## So laden und entladen Sie das Cmdlet "Edit-CsClsScenario" mithilfe des ClsController.psm1-Moduls

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.
    

    > [!IMPORTANT]
    > Das ClsController.psm1-Modul wird als separater Webdownload zur Verfügung gestellt. Das Modul ist Bestandteil der Lync Server 2013-Debuggingtools. Die Debuggingtools werden standardmäßig im Ordner "C:\Programme\Lync Server 2013\Debugging Tools" installiert.



2.  Geben Sie über die Windows PowerShell Folgendes ein:
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    

    > [!TIP]
    > Nachdem das Modul erfolgreich geladen wurde, gelangen Sie wieder zur Windows PowerShell-Eingabeaufforderung. Zur Bestätigung, dass das Modul geladen wurde und dass "Edit-CsClsScenario" verfügbar ist, geben Sie <CODE>Get-Help Edit-CsClsScenario</CODE> ein. Daraufhin sollte die grundlegende Kurzfassung der Syntax für EditCsClsScenario angezeigt werden.



3.  Geben Sie zum Entladen der Module Folgendes ein:
    
        Remove-Module ClsController
    

    > [!TIP]
    > Nachdem das Modul erfolgreich entladen wurde, gelangen Sie wieder zur Windows PowerShell-Eingabeaufforderung. Geben Sie <CODE>Get-Help Edit-CsClsScenario</CODE> ein, um zu bestätigen, dass das Modul entladen wurde. Windows PowerShell sucht daraufhin erfolglos die Hilfe für das Cmdlet.



## So entfernen Sie einen vorhandenen Anbieter mithilfe des Edit-ClsController-Moduls aus einem Szenario

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Geben Sie Folgendes ein, um einen Anbieter aus dem AlwaysOn-Szenario zu entfernen:
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    Beispiel:
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    Bei den Parametern "ScenarioName" und "ProviderName" handelt es sich um Positionsparameter (d. h., dass sie in der erwarteten Position in der Eingabeaufforderung definiert werden müssen). Der Parametername muss nicht explizit definiert werden, sofern der Szenarioname an zweiter Position und der Anbieter an dritter Position steht (in Bezug auf den Namen des Cmdlets, der an erster Position steht):
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    Die Platzierung der Parameterwerte an einer bestimmten Position gilt nur für "–Scenario" und "–Provider". Alle anderen Parameter müssen explizit definiert werden.

## So fügen Sie ein Szenario mit dem Edit-ClsController-Modul hinzu

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Geben Sie Folgendes ein, um einen Anbieter zum AlwaysOn-Szenario hinzuzufügen:
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    Beispiel:
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    Mögliche Typen für "-Loglevel" sind "Fatal", "Error", "Warning", "Info", "Verbose", "Debug" oder "All". Für "–Flags" sind sämtliche Flags möglich, die vom Anbieter unterstützt werden, beispielsweise TF\_COMPONENT, TF\_DIAG. Der Wert ALL ist für "–Flags" ebenfalls möglich.
    
    Das vorherige Beispiel kann auch mithilfe des Positionsfeatures des Cmdlets eingegeben werden. So würden Sie beispielsweise Folgendes eingeben, um "ChatServer" zum AlwaysOn-Szenario hinzuzufügen:
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

