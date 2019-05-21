---
title: Starten oder Beenden der CLS-Protokollerfassung in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie in Skype for Business Server 2015 eine zentralisierte Protokollierungsdienst-protokollaufnahme Sitzung starten oder beenden.'
ms.openlocfilehash: 49c36620cd58bf113ad1ce7823fcc438d88d8724
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274387"
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a>Starten oder Beenden der CLS-Protokollerfassung in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie eine zentralisierte Protokollierungsdienst-protokollaufnahme Sitzung in Skype for Business Server 2015 starten oder beenden.
  
Wenn Sie Ablaufverfolgungsprotokolle mithilfe des zentralen Protokollierungsdiensts erfassen möchten, geben Sie einen Befehl aus, um mit der Protokollierung an einem oder mehreren Computern und Pools zu beginnen. Sie geben auch Parameter an, die definieren, welche Computer oder Pools, welche Szenarien ausgeführt werden sollen (beispielsweise AlwaysOn, ein anderes vordefiniertes Szenario oder ein von Ihnen erstelltes Szenario), welche Skype for Business Server-Komponenten (beispielsweise S4, SipStack) nachverfolgt werden sollen.
  
Wenn Sie die richtigen Informationen erfassen möchten, müssen Sie sicherstellen, dass Sie das richtige Szenario verwenden, um Informationen zu sammeln, die für das Problem relevant sind. Im zentralisierten Protokollierungsdienst ist ein Szenario das Konzept des Aktivierens der Protokollierung auf der Grundlage einer Sammlung von Server Komponenten, Protokollierungsebenen und Flags, was wesentlich effizienter und nützlicher ist, als diese Elemente auf pro-Server-Basis zu definieren. Sie definieren und spezifizieren ein Szenario, das ausgeführt werden soll, und das Szenario wird konsistent über alle Server und Pools im Bereich der Infrastruktur ausgeführt.
  
Das Standardszenario heißt **AlwaysOn**. Wie der Name bereits andeutet, soll dieses Szenario ständig ausgeführt werden. Das Szenario AlwaysOn erfasst Informationen auf der Ebene „Info“ (zum Protokolliergrad „Info“ zählen zusätzlich zu den Infomeldungen Meldungen der Ebenen „Schwerwiegend“, „Fehler“ und „Warnung“) für viele der häufigsten Serverkomponenten. AlwaysOn erfasst Informationen vor und nach einem Problem sowie während eines Problems. Daher unterscheidet es sich gravierend vom typischen Verhalten früherer Protokollierungstools wie OCSLogger. OCSLogger wurde ausgeführt, nachdem das Problem bereits aufgetreten war. Dadurch wurde die Problembehandlung erschwert, da die erfassten Daten nicht proaktiv, sondern rückwirkend waren. Falls AlwaysOn nicht die gewünschten Informationen zum Ermitteln der fehlerhaften Komponente und keine Vorgehensweise zur Behebung enthält (was aufgrund des Umfangs der Anbieter in AlwaysOn unwahrscheinlich ist), erhalten Sie immerhin angemessene Informationen, mit denen die erforderlichen Schritte (z. B. Erstellen eines neuen Szenarios, Erfassen weiterer Informationen, Ausführen einer anderen Suche zum Sammeln genauerer Einzelheiten usw.) ermittelt werden können.
  
Der zentralisierte Protokollierungsdienst bietet zwei Möglichkeiten zum Ausgeben von Befehlen. Eine Reihe von Themen wurde direkt auf die Verwendung von Windows PowerShell über die Skype for Business Server-Verwaltungsshell ausgerichtet. Die Möglichkeit, eine Reihe von komplexen Konfigurationen und Befehlen zu verwenden, begünstigt Windows PowerShell für die Verwendung zentralisierter Protokollierungsdienste. Da Windows PowerShell über die Skype for Business Server-Verwaltungsshell nahezu allgegenwärtig für alle Funktionen in Skype for Business Server ist, werden nur die Windows PowerShell-Befehle besprochen. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>So führen Sie Start-CsClsLogging mit Windows PowerShell mithilfe von einfachen Befehlen aus

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Starten Sie ein Protokollierungsszenario mit dem zentralen Protokollierungsdienst, indem Sie Folgendes eingeben:
    
   ```
   Start-CsClsLogging -Scenario <name of scenario>
   ```

    Geben Sie beispielsweise zum Starten des Szenarios **AlwaysOn** Folgendes ein:
    
   ```
   Start-CsClsLogging -Scenario AlwaysOn
   ```

    > [!NOTE]
    > Für das Szenario AlwaysOn ist keine Standarddauer festgelegt. Das Szenario wird so lange ausgeführt, bis Sie es mit dem Cmdlet **Stop-CsClsLogging** explizit beenden. Ausführliche Informationen finden Sie unter [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps). Für alle anderen Szenarien gilt eine Standarddauer von 4 Stunden. 
  
3. Drücken Sie zum Ausführen des Befehls die EINGABETASTE. 
    
    > [!NOTE]
    > Es kann einen kurzen Moment dauern (30 bis 60 Sekunden), bis der Befehl ausgeführt und der Status von den Computern in Ihrer Bereitstellung abgerufen wird. 
  
     ![Ausführen von Start-CsClsLogging.](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. Um ein weiteres Szenario zu starten, verwenden Sie das Cmdlet **Start-CsClsLogging** mit dem Namen des zusätzlichen Szenarios (z. B. des Szenarios **Authentifizierung**) wie folgt:
    
   ```
   Start-CsClsLogging -Scenario Authentication
   ```

    > [!IMPORTANT]
    > Sie können jederzeit insgesamt zwei Szenarien auf einem beliebigen Computer ausführen. Wenn der Befehl einen globalen Gültigkeitsbereich hat, werden die Szenarien auf allen Computern in Ihrer Bereitstellung ausgeführt. Wenn Sie ein drittes Szenario starten möchten, müssen Sie die Protokollierung für den Computer, Pool, Standort oder globalen Gültigkeitsbereich beenden, für den das neue Szenario ausgeführt werden soll. Wenn Sie einen globalen Gültigkeitsbereich gestartet, können Sie die Protokollierung für mindestens ein Szenario für mindestens einen Computer oder Pool beenden. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>So führen Sie Start-CsClsLogging mit Windows PowerShell mithilfe von erweiterten Befehlen aus

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Zur Verwaltung der Protokollierungsbefehle stehen zusätzliche Parameter zur Verfügung. Sie können-Duration verwenden, um die Zeitdauer anzupassen, für die das Szenario ausgeführt werden soll. Sie können auch-Computer, eine Liste der vollqualifizierten Domänennamen (FQDNs), die durch ein Komma getrennt sind, oder-Pools, eine durch Kommas getrennte Liste der FQDNs für Pools definieren, für die Sie die Anmeldung ausführen möchten.
    
    Sie starten eine Protokollierungssitzung für das Szenario  UserReplicator im Pool „pool01.contoso.net“. Außerdem legen Sie als Dauer der Protokollierungssitzung 8 Stunden fest. Geben Sie hierzu Folgendes ein:
    
   ```
   Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
   ```

    Bei erfolgreicher Ausführung dieses Szenarios wird in etwa folgendes Ergebnis zurückgegeben:
    
     ![Ausführen von Start-CsClsLogging.](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
Beachten Sie, dass in diesem Beispiel die Szenarien „AlwaysOn“" und „UserReplicator“ ausgeführt werden. 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a>Beenden der Protokollerfassung durch den zentralisierten Protokollierungsdienst
<a name="stop"> </a>

Eine aktuell ausgeführte Protokollierungssitzung können Sie mit dem Cmdlet „Stop-CsClsLogging“ anhalten. Im Allgemeinen gibt es nicht viele Situationen, in denen Sie eine Protokollierungssitzung beenden müssten. Beispielsweise können Sie Protokolle durchsuchen und Konfigurationen ändern, ohne die Protokollierung zuvor anzuhalten. Wenn Sie zwei Szenarien ausführen, z. B. „AlwaysOn“ und „UserReplicator“, und Informationen zur Authentifizierung sammeln müssen, müssen Sie eines der anderen Szenarien anhalten (auf globaler Ebene oder auf Standort-, Pool- oder Computerebene), bevor Sie die Ausführung des Authentifizierungsszenarios starten können. Ausführliche Informationen finden Sie unter [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps).
  
> [!NOTE]
> Beim Festlegen der Szenarien, die in einer Bereitstellung, in einem Pool oder auf einem Computer ausgeführt werden können, müssen Sie unbedingt beachten, dass **pro Computer** nur zwei Szenarien ausgeführt werden können: „AlwaysOn“ und ein benutzerdefiniertes Szenario. Wenn Sie in einem Pool Aktivitäten protokollieren, sollten Sie den Pool als einzelne Entität behandeln. In den meisten Fällen ist das Ausführen verschiedener Szenarien auf jedem Computer in einem Pool nicht sinnvoll. Sinnvoll ist es dagegen, sich mit dem Problem zu befassen, zu dem Sie Daten sammeln, und zu ermitteln, welches Szenario auf einem bestimmten Computer in der gesamten Bereitstellung am hilfreichsten ist. Wenn Sie beispielsweise das UserReplicator-Szenario in Frage stellen, gibt es bei der Ausführung von UserReplicator auf einem Edgeserver oder Edge-Pool nur sehr wenig Wert. 
  
Nachdem Sie das Problem und den Umfang der Auswirkungen analysiert haben, sollten Sie sorgfältig auswählen, welche Szenarien auf welchen Computern und in welchen Pools ausgeführt werden sollen. Während das „AlwaysOn“ für einen weiten Bereich von Anwendungen mit weitem Bereich sinnvoll ist, da dabei Informationen zu einer Vielzahl von Anbietern gesammelt werden, haben bestimmte Szenarien nur Anwendungswert auf bestimmten Computern bzw. in bestimmten Pools. Seien Sie außerdem vorsichtig beim willkürlichen Starten einer Protokollierungssitzung, ohne den Wert eines bestimmten Szenarios zu kennen. Wenn Sie das falsche Szenario verwenden – oder ein für die Aufgabe zwar geeignetes Szenario verwenden, jedoch auf der falschen Ebene (global, Standort, Pool oder Computer) –, erhalten Sie fragwürdige und wenig nützliche Daten, so als ob Sie das Szenario überhaupt nicht ausgeführt hätten.
  
Um die Funktionen für den zentralisierten Protokollierungsdienst mithilfe der Skype for Business Server-Verwaltungsshell zu steuern, müssen Sie Mitglied der CsAdministrator-oder CsServerAdministrator-Sicherheitsgruppe (Role-Based Access Control, RBAC) oder einer benutzerdefinierten RBAC-Rolle sein. , die eine dieser beiden Gruppen enthält. Führen Sie den folgenden Befehl aus der Skype for Business Server-Verwaltungsshell oder der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Beispiel:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Sie Fragen sich vielleicht: wo werden die Protokolle gespeichert, nachdem Sie die Protokollierung aktiviert haben? Da Sie auf die in den Protokollen gespeicherten Informationen mithilfe von Verwaltungsshell-Abfragen zugreifen, die an die CLS-Agents gesendet wurden, und Sie die Ergebnisse in mehreren möglichen Dateiformaten ausgeben können, ist es für jeden Server wichtig, dass der CLS-Agent seine Einträge speichert.  Die Protokolldateien können an einem von Ihnen angegebenen Ort gespeichert und mit einer Reihe von Tools wie " **Snooper. exe** " und einem Tool, mit dem eine Textdatei wie **Notepad. exe**gelesen werden kann, gelesen und analysiert werden. Snooper. exe ist Teil der Skype for Business Server 2015 Debug-Tools und steht als [Web-Download](https://go.microsoft.com/fwlink/p/?LinkId=285257)zur Verfügung.

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>So beenden Sie eine derzeit ausgeführte zentralisierte Protokollierungsdienst Sitzung

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Fragen Sie den zentralisierten Protokollierungsdienst ab, um herauszufinden, welche Szenarien zurzeit ausgeführt werden, indem Sie Folgendes eingeben:
    
   ```
   Show-CsClsLogging
   ```

   ![Windows PowerShell-Konsole nach dem Aufruf von Show-CSCL](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
   Das Ergebnis von „Show-CsClsLogging“ ist eine Zusammenfassung der ausgeführten Szenarien und der Ebenen, auf denen Sie ausgeführt werden. Ausführliche Informationen finden Sie unter [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps).
    
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
    > Protokolle, die während dieser Protokollierungssitzung mit dem Szenario „UserReplicator“ erstellt wurden, werden nicht gelöscht. Die Protokollierung steht Ihnen noch zur Verfügung, um Suchen mit dem Befehl „Search-CsClsLogging“ auszuführen. Ausführliche Informationen finden Sie unter [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps). 
  
Das Cmdlet „Stop-CsClsLogging“ fungiert als Begleitbefehl zu „Start-CsClsLogging“, beendet die Protokollierungssitzung entsprechend der Definition im aktuellen Szenario und behält die von der Protokollierungssitzung erstellten Protokolle bei. Sie können jederzeit zwei Szenarien auf einem bestimmten Computer ausführen. Das Anhalten eines Szenarios, um mithilfe eines anderen Szenarios Informationen zu sammeln, ist eine gängige Aufgabe, die Sie meistens auch bei großer Arbeitsauslastung während der Fehlerbehebung anwenden können.
## <a name="see-also"></a>Siehe auch
<a name="stop"> </a>

[Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md)
