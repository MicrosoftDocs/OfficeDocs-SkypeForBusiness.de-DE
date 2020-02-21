---
title: 'Lync Server 2013: Verwenden von Stop für den zentralisierten Protokollierungsdienst'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Stop for the Centralized Logging Service
ms:assetid: 09ac093e-8f30-4874-84b4-12548ac8c898
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687964(v=OCS.15)
ms:contentKeyID: 49733549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f764bbc93ae327e30fa6ac9daf3128963856460
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a>Verwenden von Stop für den zentralisierten Protokollierungsdienst in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Eine derzeit ausgeführte Protokollierungssitzung können Sie mit dem Cmdlet "Stop-CsClsLogging" anhalten. Eine Protokollierungssitzung muss in Allgemeinen nur in wenigen Situationen angehalten werden. Beispielsweise können Sie Protokolle durchsuchen und Konfigurationen ändern, ohne die Protokollierung zuvor anzuhalten. Wenn Sie zwei Szenarien ausführen, z. B. "AlwaysOn" und "UserReplicator" und Informationen zur Authentifizierung sammeln müssen, so müssen Sie eines der anderen Szenarien anhalten (auf globaler Ebene oder auf Standort-, Pool- oder Computerebene), bevor Sie die Ausführung des Authentifizierungsszenarios starten können. Ausführliche Informationen finden Sie unter [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).

<div>


> [!NOTE]  
> Beim Festlegen der Szenarien, die in einer bestimmten Bereitstellung, einem Pool oder auf einem Computer ausgeführt werden können, denken Sie unbedingt daran, dass <STRONG>pro Computer</STRONG> nur zwei Szenarien ausgeführt werden können. Wenn Sie in einem Pool Aktivitäten protokollieren, sollten Sie den Pool als einzelne Entität behandeln. In den meisten Fällen wäre das Ausführen verschiedener Szenarien auf jedem Computer in einem Pool nicht sinnvoll. Sinnvoll ist es dagegen, sich mit dem Problem zu befassen, zu dem Sie Daten sammeln und zu ermitteln, welches Szenario auf einem bestimmten Computer in der gesamten Bereitstellung am sinnvollsten ist. Wenn Sie beispielsweise das UserReplicator-Szenario in Frage stellen, gäbe es bei der Ausführung von UserReplicator auf einem Edgeserver oder Edgepool nur sehr wenig Wert.<BR>Nachdem Sie das Problem und den Umfang der Auswirkungen analysiert haben, sollten Sie sorgfältig auswählen, welche Szenarien auf welchen Computern und in welchen Pools ausgeführt werden sollen. Während das AlwaysOn-Szenario für eine Anwendung mit weitem Bereich sinnvoll ist, da dabei Informationen zu einer Vielfalt von Anbietern gesammelt werden, haben bestimmte Szenarien nur Anwendungswert auf bestimmten Computern bzw. in bestimmten Pools. Seien Sie außerdem vorsichtig beim willkürlichen Starten einer Protokollierungssitzung, ohne den Wert eines bestimmten Szenarios zu kennen. Wenn Sie das falsche Szenario verwenden – oder ein für die Aufgabe zwar geeignetes Szenario verwenden, jedoch auf der falschen Ebene (global, Standort, Pool oder Computer) anwenden – erhalten Sie fragwürdige und wenig nützliche Daten, so als ob Sie das Szenario überhaupt nicht ausgeführt hätten.



</div>

Zum Steuern der Funktionen für den zentralisierten Protokollierungsdienst mit dem lync Server-Verwaltungsshell müssen Sie Mitglied der rollenbasierten Sicherheitsgruppen für die CsAdministrator oder CsServerAdministrator oder eine benutzerdefinierte RBAC-Rolle sein, die Folgendes enthält: eine dieser beiden Gruppen. Um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben), führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell oder der Windows PowerShell-Eingabeaufforderung aus:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Zum Beispiel:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>So beenden Sie eine derzeit ausgeführten Sitzung für den zentralisierten Protokollierungsdienst

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Fragen Sie den zentralisierten Protokollierungsdienst, um herauszufinden, welche Szenarien derzeit durchführen, indem Sie Folgendes eingeben:
    
        Show-CsClsLogging
    
    ![Windows PowerShell Konsole nach dem Aufruf von Show-CSCL](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Windows PowerShell Konsole nach dem Aufruf von Show-CSCL")
    
    Das Ergebnis von "Show-CsClsLogging" ist eine Zusammenfassung der ausgeführten Szenarien und der Ebenen, auf denen Sie ausgeführt werden. Ausführliche Informationen finden Sie unter [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).

3.  Zum Anhalten einer derzeit ausgeführten Protokollierungssitzung mit einem bestimmten Szenario, geben Sie Folgendes ein:
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    Beispiel:
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    Mit diesem Befehl wird die Protokollierung mit dem UserReplicatior-Szenario in "pool01.contoso.net" angehalten.
    
    <div>
    

    > [!NOTE]  
    > Protokolle, die während dieser Protokollierungssitzung mit dem UserReplicator-Szenario erstellt wurden, werden nicht gelöscht. Die Protokollierung steht Ihnen noch zur Verfügung, um Suchen mit dem Befehl "Search-CsClsLogging" auszuführen. Ausführliche Informationen finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.

    
    </div>

Das Cmdlet "Stop-CsClsLogging" fungiert als Begleitbefehl zu "Start-CsClsLogging", beendet definiert nach Szenarien die Protokollierungssitzung und behält die von der Protokollierungssitzung erstellten Protokolle bei. Sie können jederzeit zwei Szenarien auf einem bestimmten Computer ausführen. Das Anhalten eines Szenarios, um mithilfe eines anderen Szenarios Informationen zu sammeln ist eine gängige Aufgabe, die Sie während der Fehlerbehebung bei der Arbeitsauslastung meist anwenden können.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verwenden von Start für den zentralisierten Protokollierungsdienst zum Erfassen von Protokollen in lync Server 2013](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[Übersicht über den zentralisierten Protokollierungsdienst in lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

