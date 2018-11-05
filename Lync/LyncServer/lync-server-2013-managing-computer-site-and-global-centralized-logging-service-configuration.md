---
title: Verwalten von Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst auf Computer-, Standort- und globaler Ebene
TOCTitle: Verwalten von Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst auf Computer-, Standort- und globaler Ebene
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49890846
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwalten von Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst auf Computer-, Standort- und globaler Ebene

 

_**Letztes Änderungsdatum des Themas:** 2014-02-04_

Der Zentraler Protokollierungsdienst kann in einem Bereich ausgeführt werden, der einen einzelnen Computer oder einen Pool von Computern umfasst, in einem Standortbereich (dies ist ein definierter Standort, wie der Standort Redmond, der eine Sammlung von Computern und Pools in Ihrer Bereitstellung enthält) oder in einem globalen Bereich (dieser umfasst alle Computer und Pools in Ihrer Bereitstellung).

Für die Konfiguration des Zentraler Protokollierungsdienst-Bereichs mit der Lync Server-Verwaltungsshell, müssen Sie Mitglied der RBAC-Sicherheitsgruppen "CsAdministrator" oder "CsServerAdministrator" oder einer benutzerdefinierten RBAC-Rolle sein, die eine dieser beiden Gruppen enthält. Für eine Liste aller RBAC-Rollen (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben), denen dieses Cmdlet zugewiesen wurde, führen Sie den folgenden Befehl über die Befehlszeile der Lync Server-Verwaltungsshell oder der Windows PowerShell aus:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

Beispiel:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}


> [!NOTE]
> Windows PowerShell bietet Ihnen mehr Optionen und zusätzliche Konfigurationsoptionen, die mit CLSController.exe nicht verfügbar sind. CLSController bietet ein schnelles, präzises Verfahren zum Ausführen von Befehlen, ist aber auf den für den CLSController verfügbaren Befehlssatz beschränkt. Windows PowerShell ist nicht auf die Befehle beschränkt, die für den Befehlsprozessor des CLSControllers verfügbar sind, und bietet einen größeren Befehlssatz und mehr Optionen. Beispiel: CLSController.exe bietet Ihnen Optionen für "–computers" und "–pools". Mit der Windows PowerShell können Sie in den meisten Befehlen Computer oder Pools angeben, und wenn Sie neue Szenarien definieren (CLSController besitzt eine begrenzte Anzahl Szenarien, die nicht durch den Benutzer geändert werden können), können Sie einen Standort- oder einen globalen Bereich definieren. Diese leistungsstarke Funktion der Windows PowerShell erlaubt Ihnen die Definition eines Szenarios im Standort- oder im globalen Bereich, während die tatsächliche Protokollierung auf einen Computer oder Pool beschränkt wird.<BR>Zwischen den Eingabezeilenbefehlen, die in der Windows PowerShell oder im CLSController ausgeführt werden können, bestehen fundamentale Unterschiede. Die Windows PowerShell bietet reichhaltige Verfahren für die Konfiguration und Definition von Szenarien sowie zur sinnvollen Wiederverwendung dieser Szenarien in Ihren Fehlerbehebungsszenarien. Während der CLSController eine schnelle und effiziente Möglichkeit bietet, Befehle einzugeben und Ergebnisse zu erhalten, ist der Befehlssatz für den CLSController auf die begrenzte Anzahl der über die Befehlszeile verfügbaren Befehle beschränkt. Anders als Windows PowerShell-Cmdlets kann der CLSController keine neuen Szenarien definieren oder den Bereich auf Standort- oder globaler Ebene verwalten und ist durch einen begrenzten Befehlssatz eingeschränkt, der nicht dynamisch konfiguriert werden kann. Während der CLSController eine schnelle Ausführung ermöglicht, bietet die Windows PowerShell die Möglichkeit, die Funktion des Zentraler Protokollierungsdiensts über die Grenzen des CLSControllers hinaus zu erweitern.



Bei der Ausführung der Befehle [Search-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Search-CsClsLogging), [Show-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Show-CsClsLogging), [Start-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Start-CsClsLogging), [Stop-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Stop-CsClsLogging), [Sync-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Sync-CsClsLogging) und [Update-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Update-CsClsLogging) kann mit dem Parameter "–Computers" ein einzelner Computerbereich definiert werden. Der Parameter "–Computers" akzeptiert eine kommagetrennte Liste vollqualifizierter Domänennamen (FQDNs) für den Zielcomputer.


> [!TIP]
> Sie können ebenso "–Pools" angeben und eine kommagetrennte Liste mit Pools übergeben, in denen die Protokollierungsbefehle ausgeführt werden sollen.



Standort- und globale Bereiche werden in den Cmdlets **New-**, **Set-** und **Remove-**Zentraler Protokollierungsdienst definiert. Die folgenden Beispiele zeigen, wie ein Standortbereich und ein globaler Bereich festgelegt werden.


> [!IMPORTANT]
> Die aufgeführten Befehle enthalten möglicherweise Parameter und Konzepte, die in anderen Abschnitten behandelt werden. Die Beispielbefehle sollen die Verwendung des Parameters <STRONG>–Identity</STRONG> für die Definition eines Bereichs zeigen. Die anderen Parameter sind der Vollständigkeit halber und zur Angabe des Bereichs enthalten. Ausführliche Informationen zu den <STRONG>Set-CsClsConfiguration</STRONG>-Cmdlets finden Sie in der Dokumentation zu <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsConfiguration">Set-CsClsConfiguration</A>.



## So rufen Sie die aktuelle Konfiguration des Zentraler Protokollierungsdiensts ab

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
        Get-CsClsConfiguration

Verwenden Sie die Cmdlets **New-CsClsConfiguration** und **Set-CsClsConfiguration**, um eine neue Konfiguration zu erstellen oder eine vorhandene Konfiguration zu aktualisieren.

Wenn Sie **Get-CsClsConfiguration** ausführen, werden Informationen wie auf dem folgenden Screenshot angezeigt, auf dem die Bereitstellung aktuell die standardmäßige Global-Konfiguration hat, aber keine Standortkonfigurationen definiert sind:

![Beispielausgabe von Get-CsClsConfiguration](images/JJ688138.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Beispielausgabe von Get-CsClsConfiguration")

## So rufen Sie die aktuelle Konfiguration des Zentraler Protokollierungsdiensts aus dem lokalen Speicher des Computers ab

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
        Get-CsClsConfiguration -LocalStore

Wenn Sie das erste Beispiel verwenden, in dem **Get-CsClsConfiguration** keine Parameter festlegt, referenziert der Befehl den zentralen Verwaltungsspeicher für die Daten. Wenn Sie den Parameter "–LocalStore" angeben, referenziert der Befehl den LocalStore des Computers und nicht den zentralen Verwaltungsspeicher.

## So rufen Sie eine Liste der aktuell definierten Szenarien ab

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    Um z. B. die für den globalen Bereich definierten Szenarien abzurufen:
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

Das Cmdlet **Get-CsClsConfiguration** zeigt immer die Szenarien an, die Teil der Konfiguration eines vorgegebenen Bereichs sind. In den meisten Fällen werden nicht alle Szenarien angezeigt, und es wird gekürzt. Der hier verwendete Befehl erstellt eine Liste aller Szenarien mit Teilinformationen darüber, welche Anbieter, Einstellungen und Flags verwendet werden.

## So aktualisieren Sie einen globalen Bereich für den Zentraler Protokollierungsdienst mithilfe der Windows PowerShell

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    Beispiel:
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

Der Befehl teilt dem CLSAgent auf allen Computern und in allen Pools der Bereitstellung mit, die Größe des Rollover-Werts für die Tracing-Datei auf 40 MB festzulegen. Dieser Befehl wirkt sich auf alle Computer und Pools an allen Standorten aus und ändert deren konfigurierten Rollover-Wert in 40 MB.

## So aktualisieren Sie einen Standortbereich für den Zentraler Protokollierungsdienst mithilfe der Windows PowerShell

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    Beispiel:
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    

    > [!NOTE]
    > Wie im Beispiel gezeigt, ist der Standardspeicherort der Protokolldateien "%TEMP%\Tracing". Da es jedoch der CLSAgent ist, der die Datei tatsächlich schreibt, und da der CSLAgent als Netzwerkdienst ausgeführt wird, wird die Variable %TEMP% zu "%WINDIR%\ServiceProfiles\NetworkService\AppData\Local" erweitert.



Der Befehl teilt dem CLSAgent auf allen Computern und in allen Pools am Standort Redmond mit, die Größe des Rollover-Werts für die Tracing-Datei auf 40 MB festzulegen. Computer und Pools an anderen Standorten sind von dem Befehl nicht betroffen und verwenden weiterhin den aktuell konfigurierten Rollover-Wert für die Tracing-Datei - der entweder durch den Standardwert (20 MB) oder bei der Anmeldung definiert wird.

## So erstellen Sie eine neue Konfiguration des Zentraler Protokollierungsdiensts

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    

    > [!NOTE]
    > "New-CsClsConfiguration" bietet Zugriff auf eine Vielzahl optionaler Konfigurationseinstellungen. Detaillierte Informationen zu den Konfigurationsoptionen finden Sie unter <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsConfiguration">Get-CsClsConfiguration</A> und <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Grundlegendes zu Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst</A>.

    
    Wenn Sie z. B. eine neue Konfiguration erstellen möchten, die einen Netzwerkordner für Cachedateien, den Rollover-Zeitraum für die Protokolldateien und die Rollover-Größe für die Protokolldateien definiert, können Sie folgenden Befehl eingeben:
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

Das Erstellen neuer Konfigurationen und die Definition neuer Eigenschaften für den Zentraler Protokollierungsdienst sollten Sie sorgfältig planen. Gehen Sie vorsichtig vor, wenn Sie Änderungen durchführen, und stellen Sie sicher, dass Ihnen die Auswirkungen auf die Möglichkeit, Problemszenarien richtig zu protokollieren, bewusst sind. Änderungen an der Konfiguration sollten Sie durchführen, um Ihre Möglichkeiten zur Verwaltung der Protokolle mit einer Größe und einem Rollover-Zeitraum so zu verbessern, dass Sie Probleme bei ihrem Auftreten lösen können.

## So löschen Sie eine vorhandene Konfiguration des Zentraler Protokollierungsdiensts

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    Um z. B. eine Zentraler Protokollierungsdienst-Konfiguration zu löschen, die Sie erstellt haben, um die Rollover-Zeit der Protokolldatei zu verlängern, erhöhen Sie wie folgt die Rollover-Größe der Protokolldatei, und legen Sie für den Cachespeicherort der Protokolldatei eine Netzwerkfreigabe fest:
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    

    > [!NOTE]
    > Dies ist die neue Konfiguration, die im Verfahren "So erstellen Sie eine neue Konfiguration des Zentraler Protokollierungsdiensts" erstellt wurde.



Wenn Sie eine Konfiguration auf Standortebene löschen, verwendet der Standort anschließend die globalen Einstellungen.

## Siehe auch

#### Konzepte

[Übersicht über den zentralisierten Protokollierungsdienst](lync-server-2013-overview-of-the-centralized-logging-service.md)  

#### Weitere Ressourcen

[Verwalten der Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst mithilfe von PowerShell](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
[Set-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsConfiguration)  
[Get-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsConfiguration)  
[New-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsConfiguration)  
[Remove-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsConfiguration)

