---
title: Verwalten der Konfiguration von Computer-, Standort-und globalen zentralisierten Protokollierungs Diensten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing computer, site and global Centralized Logging Service configuration
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49733738
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 868005d0a719bc8bc021f1a0b82260037c1f6ea6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a>Verwalten der Konfiguration von Computer-, Standort-und globalen zentralisierten Protokollierungs Diensten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-04_

Der zentralisierte Protokollierungsdienst kann in einem Bereich ausgeführt werden, der einen einzelnen Computer, einen Pool von Computern, einen Standortbereich (also einen definierten Standort wie den Standort "Redmond", der eine Sammlung von Computern und Pools in Ihrer Bereitstellung enthält) oder auf globaler Ebene (also , alle Computer und Pools in Ihrer Bereitstellung).

Um den Bereich für den zentralisierten Protokollierungsdienst mithilfe der lync Server-Verwaltungsshell zu konfigurieren, müssen Sie Mitglied der rollenbasierten Sicherheitsgruppen "CsAdministrator" oder "CsServerAdministrator" oder einer benutzerdefinierten RBAC-Rolle sein, die Folgendes enthält: eine dieser beiden Gruppen. Um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben), führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell oder der Windows PowerShell-Eingabeaufforderung aus:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

Zum Beispiel:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> Windows PowerShell bietet Ihnen weitere Optionen und zusätzliche Konfigurationsoptionen, die mit CLSController. exe nicht verfügbar sind. CLSController bietet ein schnelles, präzises Verfahren zum Ausführen von Befehlen, ist aber auf den für den CLSController verfügbaren Befehlssatz beschränkt. Windows PowerShell ist nicht auf den Befehl limitiert, der für den Befehlsprozessor des CLSController verfügbar ist, und bietet eine breitere Palette von Befehlen und eine Vielzahl von Optionen. Beispiel: CLSController.exe bietet Ihnen Optionen für "–computers" und "–pools". Mit Windows PowerShell können Sie in den meisten Befehlen Computer oder Pools angeben, und wenn Sie neue Szenarien definieren (CLSController verfügt über eine begrenzte Anzahl von Szenarien, die nicht vom Benutzer geändert werden können), können Sie eine Website oder einen globalen Bereich definieren. Dieses leistungsstarke Feature von Windows PowerShell ermöglicht Ihnen, ein Szenario als Standort oder globaler Bereich zu definieren, die tatsächliche Protokollierung jedoch auf einen Computer oder einen Pool zu beschränken.<BR>Es gibt grundlegende Unterschiede zwischen den Befehlszeilenbefehlen, die Sie in Windows PowerShell oder CLSController ausführen können. Windows PowerShell bietet eine umfassende Methode zum Konfigurieren und Definieren von Szenarien sowie zur sinnvollen Wiederverwendung dieser Szenarien für Ihre Problembehandlungsszenarien. Während der CLSController eine schnelle und effiziente Möglichkeit bietet, Befehle einzugeben und Ergebnisse zu erhalten, ist der Befehlssatz für den CLSController auf die begrenzte Anzahl der über die Befehlszeile verfügbaren Befehle beschränkt. Im Gegensatz zu den Windows PowerShell-Cmdlets können CLSController keine neuen Szenarien definieren, den Bereich an einer Website oder auf globaler Ebene verwalten und viele andere Einschränkungen eines begrenzten Befehlssatzes, der nicht dynamisch konfiguriert werden kann. Während CLSController eine Möglichkeit zur schnellen Ausführung bietet, bietet Windows PowerShell eine Möglichkeit, die Funktionalität des zentralisierten Protokollierungsdiensts über das hinaus zu erweitern, was mit CLSController möglich ist.



</div>

Ein einzelner Computerbereich kann während der Ausführung eines [Search-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15))-, [Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15))-, [Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15))-, [Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15))-, [Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15)) -und [Update-CsClsLogging-](https://technet.microsoft.com/library/JJ619170(v=OCS.15)) Befehls mithilfe des Parameters – Computers definiert werden. Der Parameter "–Computers" akzeptiert eine kommagetrennte Liste vollqualifizierter Domänennamen (FQDNs) für den Zielcomputer.

<div>


> [!TIP]
> Sie können ebenso "–Pools" angeben und eine kommagetrennte Liste mit Pools übergeben, in denen die Protokollierungsbefehle ausgeführt werden sollen.



</div>

Website-und globale Bereiche werden in den Cmdlets **New-**, **Sets-** und **Remove-** zentralisierter Protokollierungsdienst definiert. Die folgenden Beispiele zeigen, wie ein Standortbereich und ein globaler Bereich festgelegt werden.

<div>


> [!IMPORTANT]
> Die angezeigten Befehle enthalten möglicherweise Parameter und Konzepte, die in anderen Abschnitten behandelt werden. Die Beispielbefehle sollen die Verwendung des Parameters <STRONG>– Identity</STRONG> veranschaulichen, um den Bereich zu definieren, und die anderen Parameter werden zur Vollständigkeit und zur Angabe des Bereichs hinzugefügt. Ausführliche Informationen zu den Cmdlets für das Cmdlet " <STRONG>csclsconfiguration"</STRONG> "finden Sie unter <A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">Festlegen von csclsconfiguration"</A> in der Betriebsdokumentation.



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>So rufen Sie die aktuelle Konfiguration des zentralisierten Protokollierungsdiensts ab

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
        Get-CsClsConfiguration

Verwenden Sie die Cmdlets **New-CsClsConfiguration** und **Set-CsClsConfiguration**, um eine neue Konfiguration zu erstellen oder eine vorhandene Konfiguration zu aktualisieren.

Wenn Sie **Get-csclsconfiguration "** ausführen, werden Informationen angezeigt, die dem folgenden Screenshot ähneln, in dem die Bereitstellung derzeit die standardmäßige globale Konfiguration aufweist, jedoch keine Websitekonfigurationen definiert sind:

![Beispielausgabe von Get-csclsconfiguration ".](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Beispielausgabe von Get-csclsconfiguration ".")

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>So rufen Sie die aktuelle Konfiguration des zentralisierten Protokollierungsdiensts aus dem lokalen Computerspeicher ab

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
        Get-CsClsConfiguration -LocalStore

Wenn Sie das erste Beispiel verwenden, in dem **Get-csclsconfiguration "** keine Parameter angibt, verweist der Befehl auf den zentralen Verwaltungsspeicher für die Daten. Wenn Sie den Parameter-localstore angeben, verweist der Befehl auf den Computer localstore anstelle des zentralen Verwaltungsspeichers.

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>So rufen Sie eine Liste der aktuell definierten Szenarien ab

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    Um z. B. die für den globalen Bereich definierten Szenarien abzurufen:
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

Das Cmdlet **Get-CsClsConfiguration** zeigt immer die Szenarien an, die Teil der Konfiguration eines vorgegebenen Bereichs sind. In den meisten Fällen werden nicht alle Szenarien angezeigt, und es wird gekürzt. Der hier verwendete Befehl erstellt eine Liste aller Szenarien mit Teilinformationen darüber, welche Anbieter, Einstellungen und Flags verwendet werden.

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>So aktualisieren Sie einen globalen Bereich für den zentralisierten Protokollierungsdienst mithilfe von Windows PowerShell

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    Beispiel:
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

Der Befehl teilt dem CLSAgent auf allen Computern und in allen Pools der Bereitstellung mit, die Größe des Rollover-Werts für die Tracing-Datei auf 40 MB festzulegen. Dieser Befehl wirkt sich auf alle Computer und Pools an allen Standorten aus und ändert deren konfigurierten Rollover-Wert in 40 MB.

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>So aktualisieren Sie einen Website Bereich für den zentralisierten Protokollierungsdienst mithilfe von Windows PowerShell

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    Beispiel:
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > Wie im Beispiel gezeigt, ist der Standardspeicherort der Protokolldateien "%TEMP%\Tracing". Da es jedoch der CLSAgent ist, der die Datei tatsächlich schreibt, und da der CSLAgent als Netzwerkdienst ausgeführt wird, wird die Variable %TEMP% zu "%WINDIR%\ServiceProfiles\NetworkService\AppData\Local" erweitert.

    
    </div>

Der Befehl teilt dem CLSAgent auf allen Computern und in allen Pools am Standort Redmond mit, die Größe des Rollover-Werts für die Tracing-Datei auf 40 MB festzulegen. Computer und Pools an anderen Standorten sind von dem Befehl nicht betroffen und verwenden weiterhin den aktuell konfigurierten Rollover-Wert für die Tracing-Datei - der entweder durch den Standardwert (20 MB) oder bei der Anmeldung definiert wird.

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a>So erstellen Sie eine neue Konfiguration für den zentralisierten Protokollierungsdienst

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > "New-CsClsConfiguration" bietet Zugriff auf eine Vielzahl optionaler Konfigurationseinstellungen. Ausführliche Informationen zu den Konfigurationsoptionen finden Sie unter <A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">Get-csclsconfiguration "</A> und <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Grundlegendes zu den Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in lync Server 2013</A>.

    
    </div>
    
    Wenn Sie z. B. eine neue Konfiguration erstellen möchten, die einen Netzwerkordner für Cachedateien, den Rollover-Zeitraum für die Protokolldateien und die Rollover-Größe für die Protokolldateien definiert, können Sie folgenden Befehl eingeben:
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

Sie sollten die Erstellung neuer Konfigurationen und die Definition neuer Eigenschaften für den zentralisierten Protokollierungsdienst sorgfältig planen. Gehen Sie vorsichtig vor, wenn Sie Änderungen durchführen, und stellen Sie sicher, dass Ihnen die Auswirkungen auf die Möglichkeit, Problemszenarien richtig zu protokollieren, bewusst sind. Änderungen an der Konfiguration sollten Sie durchführen, um Ihre Möglichkeiten zur Verwaltung der Protokolle mit einer Größe und einem Rollover-Zeitraum so zu verbessern, dass Sie Probleme bei ihrem Auftreten lösen können.

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>So entfernen Sie eine vorhandene Konfiguration für den zentralisierten Protokollierungsdienst

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    Wenn Sie beispielsweise eine von Ihnen erstellte Konfiguration für den zentralisierten Protokollierungsdienst entfernen möchten, um die rolloverzeit der Protokolldatei zu verbessern, vergrößern Sie die Größe der Rollover-Protokolldatei, und legen Sie den Speicherort des Protokolldatei Caches wie folgt auf eine Netzwerkfreigabe fest:
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > Dies ist die neue Konfiguration, die im Verfahren "So erstellen Sie eine neue Konfiguration für den zentralisierten Protokollierungsdienst" erstellt wurde.

    
    </div>

Wenn Sie eine Konfiguration auf Standortebene löschen, verwendet der Standort anschließend die globalen Einstellungen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Übersicht über den zentralisierten Protokollierungsdienst in lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Verwalten der Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in lync Server 2013](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
[Gruppe-csclsconfiguration "](https://technet.microsoft.com/library/JJ619182(v=OCS.15))  
[Get-csclsconfiguration "](https://technet.microsoft.com/library/JJ619179(v=OCS.15))  
[New-csclsconfiguration "](https://technet.microsoft.com/library/JJ619177(v=OCS.15))  
[Remove-csclsconfiguration "](https://technet.microsoft.com/library/JJ619191(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

