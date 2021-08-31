---
title: Starten oder Beenden der CLS-Protokollerfassung in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: 'Zusammenfassung: Erfahren Sie, wie Sie eine Protokollerfassungssitzung des zentralisierten Protokollierungsdiensts in Skype for Business Server 2015 starten oder beenden.'
ms.openlocfilehash: 5ed9630f21e409c240871c981db6346d2d2d9599
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726954"
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a>Starten oder Beenden der CLS-Protokollerfassung in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie in Skype for Business Server 2015 eine Protokollerfassungssitzung für den zentralisierten Protokollierungsdienst starten oder beenden.
  
Um Ablaufverfolgungsprotokolle mithilfe des zentralisierten Protokollierungsdiensts zu erfassen, geben Sie einen Befehl aus, um mit der Protokollierung auf einem oder mehreren Computern und Pools zu beginnen. Außerdem geben Sie Parameter aus, die definieren, welche Computer oder Pools ausgeführt werden sollen (z. B. AlwaysOn, ein anderes vordefiniertes Szenario oder ein erstelltes Szenario), Skype for Business Server welche Komponenten (z. B. S4, SipStack) nachverfolgt werden sollen.
  
Um die richtigen Informationen zu erfassen, müssen Sie sicherstellen, dass Sie das richtige Szenario verwenden, um Informationen zu sammeln, die für das Problem relevant sind. Im zentralisierten Protokollierungsdienst besteht ein Szenario darin, die Protokollierung basierend auf einer Sammlung von Serverkomponenten, Protokollierungsebenen und Flags zu aktivieren, was viel effizienter und nützlicher ist, als diese Elemente pro Server zu definieren. Sie definieren und geben ein Szenario an, das ausgeführt werden soll, und das Szenario wird konsistent auf allen Servern und Pools im Bereich der Infrastruktur ausgeführt.
  
Das Standardszenario heißt **AlwaysOn**. AlwaysOn soll dazu dienen, das Szenario ständig auszuführen, wie der Name des Szenarios bereits impliziert. Das Szenario AlwaysOn erfasst Informationen auf der Ebene "Info" (zum Protokolliergrad "Info" zählen zusätzlich zu den Infomeldungen Meldungen der Ebenen "Schwerwiegend", "Fehler" und "Warnung") für viele der häufigsten Serverkomponenten. Von AlwaysOn werden Informationen vor und nach einem Problem sowie während eines Problems erfasst. Daher unterscheidet es sich gravierend vom typischen Verhalten früherer Protokollierungstools wie OCSLogger. OCSLogger wurde ausgeführt, nachdem das Problem bereits aufgetreten war. Dadurch wurde die Problembehandlung erschwert, da die erfassten Daten nicht proaktiv, sondern rückwirkend waren. Falls AlwaysOn nicht die gewünschten Informationen zum Ermitteln der fehlerhaften Komponente und keine Vorgehensweise zur Behebung enthält (was aufgrund des Umfangs der Anbieter in AlwaysOn unwahrscheinlich ist), erhalten Sie immerhin angemessene Informationen, mit denen die erforderlichen Schritte (z. B. Erstellen eines neuen Szenarios, Erfassen weiterer Informationen, Ausführen einer anderen Suche zum Sammeln genauerer Einzelheiten usw.) ermittelt werden können.
  
Der zentralisierte Protokollierungsdienst bietet zwei Möglichkeiten zum Ausgeben von Befehlen. Eine Reihe von Themen konzentriert sich auf die Verwendung von Windows PowerShell über die Skype for Business Server-Verwaltungsshell. Die Möglichkeit, eine Reihe komplexer Konfigurationen und Befehle zu verwenden, bevorzugt Windows PowerShell für die Verwendung des zentralisierten Protokollierungsdiensts. Da Windows PowerShell über die Skype for Business Server Verwaltungsshell nahezu für alle Funktionen in Skype for Business Server vorhanden ist, werden nur die Windows PowerShell Befehle behandelt. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>So führen Sie Start-CsClsLogging mit Windows PowerShell mit einfachen Befehlen aus

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell.**
    
2. Starten Sie ein Protokollierungsszenario mit dem zentralisierten Protokollierungsdienst, indem Sie Folgendes eingeben:
    
   ```PowerShell
   Start-CsClsLogging -Scenario <name of scenario>
   ```

    Geben Sie beispielsweise zum Starten des Szenarios **AlwaysOn** Folgendes ein:
    
   ```PowerShell
   Start-CsClsLogging -Scenario AlwaysOn
   ```

    > [!NOTE]
    > Für das AlwaysOn-Szenario ist keine Standarddauer festgelegt. Das Szenario wird so lange ausgeführt, bis Sie es mit dem Cmdlet **Stop-CsClsLogging** explizit beenden. Ausführliche Informationen finden Sie unter [Stop-CsClsLogging](/powershell/module/skype/stop-csclslogging?view=skype-ps). Für alle anderen Szenarios gilt eine Standarddauer von 4 Stunden. 
  
3. Drücken Sie zum Ausführen des Befehls die EINGABETASTE. 
    
    > [!NOTE]
    > Es kann einen kurzen Moment dauern (30 bis 60 Sekunden), bis der Befehl ausgeführt und der Status von den Computern in Ihrer Bereitstellung abgerufen wird. 
  
     ![Ausführen von Start-CsClsLogging.](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. Um ein weiteres Szenario zu starten, verwenden Sie das Cmdlet **Start-CsClsLogging** mit dem Namen des zusätzlichen Szenarios (z. B. des Szenarios **Authentifizierung**) wie folgt:
    
   ```PowerShell
   Start-CsClsLogging -Scenario Authentication
   ```

    > [!IMPORTANT]
    > Sie können jederzeit insgesamt zwei Szenarien auf einem beliebigen Computer ausführen. Hat der Befehl einen globalen Gültigkeitsbereich, werden die Szenarien auf allen Computern in Ihrer Bereitstellung ausgeführt. Wenn Sie ein drittes Szenario starten möchten, müssen Sie die Protokollierung für den Computer, Pool, Standort oder globalen Gültigkeitsbereich beenden, für den das neue Szenario ausgeführt werden soll. Haben Sie einen globalen Gültigkeitsbereich gestartet, können Sie die Protokollierung für mindestens ein Szenario für mindestens einen Computer oder Pool beenden. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>So führen Sie Start-CsClsLogging mit Windows PowerShell mithilfe erweiterter Befehle aus

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell.**
    
2. Zur Verwaltung der Protokollierungsbefehle stehen zusätzliche Parameter zur Verfügung. Sie können "-Duration" verwenden, um die Zeitdauer für die Ausführung des Szenarios anzupassen. Sie können auch "-Computers", eine Durch Komma getrennte Liste der vollqualifizierten Domänennamen (Fully Qualified Domain Names, FQDNs) des Computers oder "-Pools", eine durch Kommas getrennte Liste der FQDNs für Pools definieren, auf denen Sie die Protokollierung ausführen möchten.
    
    Sie starten eine Protokollierungssitzung für das UserReplicator-Szenario im Pool "pool01.contoso.net". Außerdem legen Sie für die Dauer der Protokollierungssitzung 8 Stunden fest. Geben Sie hierzu Folgendes ein:
    
   ```PowerShell
   Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
   ```

    Bei erfolgreicher Ausführung dieses Szenarios wird in etwa folgendes Ergebnis zurückgegeben:
    
     ![Ausführen von Start-CsClsLogging.](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
Beachten Sie, dass in diesem Beispiel die Szenarien "AlwaysOn" und "UserReplicator" ausgeführt werden. 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a>Beenden der Protokollerfassung des zentralisierten Protokollierungsdiensts
<a name="stop"> </a>

Eine derzeit ausgeführte Protokollierungssitzung können Sie mit dem Cmdlet "Stop-CsClsLogging" anhalten. Im Allgemeinen gibt es nicht viele Situationen, in denen Sie eine Protokollierungssitzung beenden müssen. Beispielsweise können Sie Protokolle durchsuchen und Konfigurationen ändern, ohne die Protokollierung zuvor anzuhalten. Wenn Sie zwei Szenarien ausführen, z. B. "AlwaysOn" und "UserReplicator" und Informationen zur Authentifizierung sammeln müssen, so müssen Sie eines der anderen Szenarien anhalten (auf globaler Ebene oder auf Standort-, Pool- oder Computerebene), bevor Sie die Ausführung des Authentifizierungsszenarios starten können. Ausführliche Informationen finden Sie unter [Stop-CsClsLogging](/powershell/module/skype/stop-csclslogging?view=skype-ps).
  
> [!NOTE]
> Wenn Sie ermitteln, welche Szenarien Sie in einer bestimmten Bereitstellung, einem Pool oder einem bestimmten Computer ausführen können, müssen Sie bedenken, dass Sie auf die Ausführung von zwei Szenarien **pro Computer** beschränkt sind: AlwaysOn und ein benutzerdefiniertes Szenario. Wenn Sie in einem Pool Aktivitäten protokollieren, sollten Sie den Pool als einzelne Entität behandeln. In den meisten Fällen wäre das Ausführen verschiedener Szenarien auf jedem Computer in einem Pool nicht sinnvoll. Sinnvoll ist es dagegen, sich mit dem Problem zu befassen, zu dem Sie Daten sammeln und zu ermitteln, welches Szenario auf einem bestimmten Computer in der gesamten Bereitstellung am sinnvollsten ist. Wenn Sie z. B. das Szenario "UserReplicator" in Betracht ziehen, wäre die Ausführung von UserReplicator auf einem Edgeserver oder Edgepool sehr wenig sinnvoll. 
  
Nachdem Sie das Problem und den Umfang der Auswirkungen analysiert haben, sollten Sie sorgfältig auswählen, welche Szenarien auf welchen Computern und in welchen Pools ausgeführt werden sollen. Während das AlwaysOn-Szenario für eine Anwendung mit weitem Bereich sinnvoll ist, da dabei Informationen zu einer Vielfalt von Anbietern gesammelt werden, haben bestimmte Szenarien nur Anwendungswert auf bestimmten Computern bzw. in bestimmten Pools. Seien Sie außerdem vorsichtig beim willkürlichen Starten einer Protokollierungssitzung, ohne den Wert eines bestimmten Szenarios zu kennen. Wenn Sie das falsche Szenario verwenden – oder ein für die Aufgabe zwar geeignetes Szenario verwenden, jedoch auf der falschen Ebene (global, Standort, Pool oder Computer) anwenden – erhalten Sie fragwürdige und wenig nützliche Daten, so als ob Sie das Szenario überhaupt nicht ausgeführt hätten.
  
Um die Funktionen des zentralisierten Protokollierungsdiensts mithilfe der Skype for Business Server Verwaltungsshell zu steuern, müssen Sie Entweder Mitglied der Rollenbasierten Zugriffssteuerungsgruppen (Role-Based Access Control, RBAC) "CsAdministrator" oder "CsServerAdministrator" oder einer benutzerdefinierten RBAC-Rolle sein, die eine dieser beiden Gruppen enthält. Um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben), führen Sie den folgenden Befehl über die Skype for Business Server Verwaltungsshell oder die Windows PowerShell Eingabeaufforderung aus:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Beispiel:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Sie fragen sich vielleicht: Wo werden die Protokolle aufbewahrt, nachdem Sie die Protokollierung aktiviert haben? Da Sie mithilfe von Verwaltungsshellabfragen, die an die CLS-Agents gesendet werden, auf die in den Protokollen gespeicherten Informationen zugreifen, können Sie die Ergebnisse in mehrere dateiformate ausgeben, wobei auf jedem Server ein CLS-Agent seine Datensätze aufbewahrt, was eigentlich nicht wichtig ist.  Die Protokolldateien können an einem Speicherort gespeichert werden, den Sie mithilfe einer Vielzahl von Tools angeben und lesen und analysieren, einschließlich **Snooper.exe** und jedes Tool, das eine Textdatei lesen kann, z. **B.Notepad.exe.** Snooper.exe ist Teil der Skype for Business Server 2015-Debugtools und steht als [Webdownload](https://go.microsoft.com/fwlink/p/?LinkId=285257)zur Verfügung.

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>So beenden Sie eine derzeit ausgeführte sitzung des zentralisierten Protokollierungsdiensts

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell.**
    
2. Fragen Sie den zentralisierten Protokollierungsdienst ab, um herauszufinden, welche Szenarien derzeit ausgeführt werden, indem Sie Folgendes eingeben:
    
   ```PowerShell
   Show-CsClsLogging
   ```

   ![Windows PowerShell Konsole nach dem Aufrufen von Show-CsCl.](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
   Das Ergebnis von "Show-CsClsLogging" ist eine Zusammenfassung der ausgeführten Szenarien und der Ebenen, auf denen Sie ausgeführt werden. Ausführliche Informationen finden Sie unter [Show-CsClsLogging](/powershell/module/skype/show-csclslogging?view=skype-ps).
    
3. Zum Anhalten einer derzeit ausgeführten Protokollierungssitzung mit einem bestimmten Szenario, geben Sie Folgendes ein:
    
   ```PowerShell
   Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
   ```
   Beispiel:
    
   ```PowerShell
   Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
   ```

   Mit diesem Befehl wird die Protokollierung mit dem UserReplicatior-Szenario in "pool01.contoso.net" angehalten.
    
    > [!NOTE]
    > Protokolle, die während dieser Protokollierungssitzung mit dem UserReplicator-Szenario erstellt wurden, werden nicht gelöscht. Die Protokollierung steht Ihnen noch zur Verfügung, um Suchen mit dem Befehl "Search-CsClsLogging" auszuführen. Ausführliche Informationen finden Sie unter [Search-CsClsLogging](/powershell/module/skype/search-csclslogging?view=skype-ps). 
  
Das Cmdlet "Stop-CsClsLogging" fungiert als Begleitbefehl zu "Start-CsClsLogging", beendet definiert nach Szenarien die Protokollierungssitzung und behält die von der Protokollierungssitzung erstellten Protokolle bei. Sie können jederzeit zwei Szenarien auf einem bestimmten Computer ausführen. Das Anhalten eines Szenarios, um mithilfe eines anderen Szenarios Informationen zu sammeln ist eine gängige Aufgabe, die Sie während der Fehlerbehebung bei der Arbeitsauslastung meist anwenden können.
## <a name="see-also"></a>Siehe auch
<a name="stop"> </a>

[Zentralisierter Protokollierungsdienst in Skype for Business 2015](centralized-logging-service.md)