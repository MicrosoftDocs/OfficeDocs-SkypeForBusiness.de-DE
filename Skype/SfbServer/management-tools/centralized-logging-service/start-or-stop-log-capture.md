---
title: Starten oder Beenden der CLS-Protokollerfassung in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: 'Zusammenfassung: Informationen Sie zum Starten oder Beenden einer Centralized Logging Service Log Capture-Sitzung in Skype für Business Server 2015.'
ms.openlocfilehash: c0b65fddcb5036cf41866ce79d82ae0bc49a79e3
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373764"
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a>Starten oder Beenden der CLS-Protokollerfassung in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zum Starten oder Beenden einer Centralized Logging Service Log Capture-Sitzung in Skype für Business Server 2015.
  
Zum Erfassen von Ablaufverfolgungsprotokollen mithilfe der zentralisierte Protokollierungsdienst stellen Sie einen Befehl aus, um mit der Protokollierung für einen oder mehrere Computer und Pools beginnen. Problem Sie auch Parameter, die definieren, welche Computer oder Pools, welche Szenarien zum Ausführen (z. B., AlwaysOn, einem anderen vordefinierten Szenario oder einem Szenario, die Sie erstellt haben), welche Skype für Business Server-Komponenten (beispielsweise S4, SipStack) zu verfolgen.
  
Um die richtigen Informationen zu erfassen, müssen Sie sicherstellen, dass Sie des richtigen Szenarios verwenden, um Informationen zu sammeln, die für das Problem relevant ist. In der zentralisierte Protokollierungsdienst ist ein Szenario für das Konzept der Aktivieren der Protokollierung basierend auf eine Auflistung von Server-Komponenten, Protokollierungsebenen und Kennzeichen, das ist wesentlich effizienter und zum Definieren dieser Elemente auf pro Server als hilfreich. Sie definieren, und geben Sie ein Szenario ausführen und das Szenario konsistent in allen Servern und Pools in den Bereich der Infrastruktur ausgeführt wird.
  
Das Standardszenario heißt **AlwaysOn**. Wie der Name bereits andeutet, soll dieses Szenario ständig ausgeführt werden. Das Szenario AlwaysOn erfasst Informationen auf der Ebene „Info“ (zum Protokolliergrad „Info“ zählen zusätzlich zu den Infomeldungen Meldungen der Ebenen „Schwerwiegend“, „Fehler“ und „Warnung“) für viele der häufigsten Serverkomponenten. AlwaysOn erfasst Informationen vor und nach einem Problem sowie während eines Problems. Daher unterscheidet es sich gravierend vom typischen Verhalten früherer Protokollierungstools wie OCSLogger. OCSLogger wurde ausgeführt, nachdem das Problem bereits aufgetreten war. Dadurch wurde die Problembehandlung erschwert, da die erfassten Daten nicht proaktiv, sondern rückwirkend waren. Falls AlwaysOn nicht die gewünschten Informationen zum Ermitteln der fehlerhaften Komponente und keine Vorgehensweise zur Behebung enthält (was aufgrund des Umfangs der Anbieter in AlwaysOn unwahrscheinlich ist), erhalten Sie immerhin angemessene Informationen, mit denen die erforderlichen Schritte (z. B. Erstellen eines neuen Szenarios, Erfassen weiterer Informationen, Ausführen einer anderen Suche zum Sammeln genauerer Einzelheiten usw.) ermittelt werden können.
  
Der zentralisierte Protokollierungsdienst bietet zwei Möglichkeiten zum Problem Befehle. Eine Anzahl von Themen haben herum konzentriert sich wurde mithilfe von Windows PowerShell über die Skype für Business Server-Verwaltungsshell. Die Möglichkeit, eine Reihe von komplexen Konfigurationen und Befehle mit bevorzugt Windows PowerShell für die Verwendung von Centralized Logging Service. Da Windows PowerShell über die Skype für Business Server-Verwaltungsshell nahezu universell für alle Funktionen in Skype für Business Server ist, werden nur die Windows PowerShell-Befehle erläutert. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>So führen Sie "Start-csclslogging" mit Windows PowerShell mithilfe grundlegender Befehle aus

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Starten Sie ein protokollierungsszenario mit Centralized Logging Service, indem Sie Folgendes eingeben:
    
   ```
   Start-CsClsLogging -Scenario <name of scenario>
   ```

    Geben Sie beispielsweise zum Starten des Szenarios **AlwaysOn** Folgendes ein:
    
   ```
   Start-CsClsLogging -Scenario AlwaysOn
   ```

    > [!NOTE]
    > Für das Szenario AlwaysOn ist keine Standarddauer festgelegt. In diesem Szenario wird ausgeführt, bis Sie explizit mit dem Cmdlet **"Stop-csclslogging"** beenden. Weitere Informationen hierzu finden Sie unter ["Stop-csclslogging"](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps). Für alle anderen Szenarien gilt eine Standarddauer von 4 Stunden. 
  
3. Drücken Sie zum Ausführen des Befehls die EINGABETASTE. 
    
    > [!NOTE]
    > Es kann einen kurzen Moment dauern (30 bis 60 Sekunden), bis der Befehl ausgeführt und der Status von den Computern in Ihrer Bereitstellung abgerufen wird. 
  
     ![Ausführen von Start-CsClsLogging](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. Verwenden Sie zum Starten von einem anderen Szenario mit dem Cmdlet **"Start-csclslogging"** mit dem Namen des zusätzliche Szenarios wie folgt (beispielsweise das Szenario **Authentifizierung**) ausführen:
    
   ```
   Start-CsClsLogging -Scenario Authentication
   ```

    > [!IMPORTANT]
    > Sie können jederzeit insgesamt zwei Szenarien auf einem beliebigen Computer ausführen. Wenn der Befehl einen globalen Gültigkeitsbereich hat, werden die Szenarien auf allen Computern in Ihrer Bereitstellung ausgeführt. Wenn Sie ein drittes Szenario starten möchten, müssen Sie die Protokollierung für den Computer, Pool, Standort oder globalen Gültigkeitsbereich beenden, für den das neue Szenario ausgeführt werden soll. Wenn Sie einen globalen Gültigkeitsbereich gestartet, können Sie die Protokollierung für mindestens ein Szenario für mindestens einen Computer oder Pool beenden. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>So führen Sie "Start-csclslogging" mit Windows PowerShell mithilfe erweiterter Befehle aus

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Zur Verwaltung der Protokollierungsbefehle stehen zusätzliche Parameter zur Verfügung. Sie können - Dauer, passen Sie die Dauer für das Szenario ausgeführt. Auch können Sie definieren - Computer, eine Liste der Computer vollqualifizierten Domänennamen (FQDNs) durch ein Komma getrennt oder - Pools, eine durch Trennzeichen getrennte Liste mit FQDNs für Pools, die Sie auf Protokollierung ausführen möchten.
    
    Sie starten eine Protokollierungssitzung für das Szenario  UserReplicator im Pool „pool01.contoso.net“. Außerdem legen Sie als Dauer der Protokollierungssitzung 8 Stunden fest. Geben Sie hierzu Folgendes ein:
    
   ```
   Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
   ```

    Bei erfolgreicher Ausführung dieses Szenarios wird in etwa folgendes Ergebnis zurückgegeben:
    
     ![Ausführen von Start-CsClsLogging](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
Beachten Sie, dass in diesem Beispiel die Szenarien „AlwaysOn“" und „UserReplicator“ ausgeführt werden. 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a>Beenden der Protokollerfassung durch den zentralisierten Protokollierungsdienst
<a name="stop"> </a>

Eine aktuell ausgeführte Protokollierungssitzung können Sie mit dem Cmdlet „Stop-CsClsLogging“ anhalten. In der Regel keine viele Situationen, in denen Sie eine protokollierungssitzung anzuhalten müssen, vorhanden sind. Beispielsweise können Sie Protokolle durchsuchen und Konfigurationen ändern, ohne die Protokollierung zuvor anzuhalten. Wenn Sie zwei Szenarien ausführen, z. B. „AlwaysOn“ und „UserReplicator“, und Informationen zur Authentifizierung sammeln müssen, müssen Sie eines der anderen Szenarien anhalten (auf globaler Ebene oder auf Standort-, Pool- oder Computerebene), bevor Sie die Ausführung des Authentifizierungsszenarios starten können. Weitere Informationen hierzu finden Sie unter ["Stop-csclslogging"](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps).
  
> [!NOTE]
> Beim Festlegen der Szenarien, die in einer Bereitstellung, in einem Pool oder auf einem Computer ausgeführt werden können, müssen Sie unbedingt beachten, dass **pro Computer** nur zwei Szenarien ausgeführt werden können: „AlwaysOn“ und ein benutzerdefiniertes Szenario. Wenn Sie in einem Pool Aktivitäten protokollieren, sollten Sie den Pool als einzelne Entität behandeln. In den meisten Fällen ist das Ausführen verschiedener Szenarien auf jedem Computer in einem Pool nicht sinnvoll. Sinnvoll ist es dagegen, sich mit dem Problem zu befassen, zu dem Sie Daten sammeln, und zu ermitteln, welches Szenario auf einem bestimmten Computer in der gesamten Bereitstellung am hilfreichsten ist. Beispielsweise, wenn Sie das UserReplicator Szenario in Betracht ziehen, wäre es eine sehr geringe Wert in UserReplicator auf einem Edge-Server oder Edge-Pool ausgeführt. 
  
Nachdem Sie das Problem und den Umfang der Auswirkungen analysiert haben, sollten Sie sorgfältig auswählen, welche Szenarien auf welchen Computern und in welchen Pools ausgeführt werden sollen. Während das „AlwaysOn“ für einen weiten Bereich von Anwendungen mit weitem Bereich sinnvoll ist, da dabei Informationen zu einer Vielzahl von Anbietern gesammelt werden, haben bestimmte Szenarien nur Anwendungswert auf bestimmten Computern bzw. in bestimmten Pools. Seien Sie außerdem vorsichtig beim willkürlichen Starten einer Protokollierungssitzung, ohne den Wert eines bestimmten Szenarios zu kennen. Wenn Sie das falsche Szenario verwenden – oder ein für die Aufgabe zwar geeignetes Szenario verwenden, jedoch auf der falschen Ebene (global, Standort, Pool oder Computer) –, erhalten Sie fragwürdige und wenig nützliche Daten, so als ob Sie das Szenario überhaupt nicht ausgeführt hätten.
  
Um die Centralized Logging Service-Funktionen steuern, indem Sie die Skype für Business Server-Verwaltungsshell verwenden, müssen Sie Mitglied der Administratorrolle CsAdministrator oder der Sicherheitsgruppen CsServerAdministrator rollenbasierten Zugriffssteuerung (RBAC) oder eine benutzerdefinierte RBAC-Rolle sein. einer dieser beiden Gruppen enthält. Um eine Liste aller RBAC-Rollen, die mit diesem Cmdlet zugewiesen wurde (auch alle benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben), führen Sie den folgenden Befehl aus der Skype für Business Server-Verwaltungsshell oder der Windows PowerShell-Eingabeaufforderung ein:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Beispiel:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>So beenden Sie eine derzeit ausgeführte Centralized Logging Service-Sitzung

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Abfragen der zentralisierte Protokollierungsdienst um zu ermitteln, welche Szenarien derzeit ausgeführt werden, indem Sie Folgendes eingeben:
    
   ```
   Show-CsClsLogging
   ```

   ![Windows PowerShell-Konsole nach Aufrufen von Show-CsCl](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
   Das Ergebnis von „Show-CsClsLogging“ ist eine Zusammenfassung der ausgeführten Szenarien und der Ebenen, auf denen Sie ausgeführt werden. Weitere Informationen hierzu finden Sie unter ["Show-csclslogging"](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps).
    
3. Geben Sie zum Anhalten einer aktuell ausgeführten Protokollierungssitzung mit einem bestimmten Szenario Folgendes ein:
    
   ```
   Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
   ```
   Beispiel:
    
   ```
   Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
   ```

   Mit diesem Befehl wird die Protokollierung mit dem Szenario „UserReplicator“ in „pool01.contoso.net“ angehalten.
    
    > [!NOTE]
    > Protokolle, die während dieser Protokollierungssitzung mit dem Szenario „UserReplicator“ erstellt wurden, werden nicht gelöscht. Die Protokollierung steht Ihnen noch zur Verfügung, um Suchen mit dem Befehl „Search-CsClsLogging“ auszuführen. Weitere Informationen hierzu finden Sie unter ["Search-csclslogging"](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps). 
  
Das Cmdlet „Stop-CsClsLogging“ fungiert als Begleitbefehl zu „Start-CsClsLogging“, beendet die Protokollierungssitzung entsprechend der Definition im aktuellen Szenario und behält die von der Protokollierungssitzung erstellten Protokolle bei. Sie können jederzeit zwei Szenarien auf einem bestimmten Computer ausführen. Das Anhalten eines Szenarios, um mithilfe eines anderen Szenarios Informationen zu sammeln, ist eine gängige Aufgabe, die Sie meistens auch bei großer Arbeitsauslastung während der Fehlerbehebung anwenden können.
## <a name="see-also"></a>Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.
<a name="stop"> </a>

[Zentralisierter Protokollierungsdienst in Skype for Business 2015](centralized-logging-service.md)