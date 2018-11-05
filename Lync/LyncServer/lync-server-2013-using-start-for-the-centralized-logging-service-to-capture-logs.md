---
title: Verwenden von "Start", damit der zentralisierte Protokollierungsdienst Protokolle erfasst
TOCTitle: Verwenden von "Start", damit der zentralisierte Protokollierungsdienst Protokolle erfasst
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49890608
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwenden von \"Start\", damit der zentralisierte Protokollierungsdienst Protokolle erfasst

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Zum Erfassen von Ablaufprotokollen mit dem Zentraler Protokollierungsdienst geben Sie einen Befehl aus, um die Protokollierung für mindestens einen Computer und Pool zu starten. Sie geben außerdem Parameter an, die die Computer oder Pools für die Ablaufverfolgung definieren und festlegen, welche Szenarien ausgeführt (z. B. AlwaysOn, ein anderes vordefiniertes Szenario oder ein von Ihnen erstelltes Szenario) und welche Lync Server-Komponenten (z. B. S4, SipStack) nachverfolgt werden sollen.

Damit die richtigen Informationen gesammelt werden, müssen Sie sicherstellen, dass Sie das richtige Szenario zum Erfassen der für das Problem relevanten Informationen verwenden. Im Zentraler Protokollierungsdienst umfasst ein Szenario das Aktivieren der Protokollierung basierend auf einer Reihe von Serverkomponenten und Flags und dem Protokolliergrad. Dies ist effizienter und hilfreicher, als wenn Sie diese Elemente pro Server festlegen müssten. Sie definieren ein auszuführendes Szenario und geben es an. Das Szenario wird konsistent auf allen Servern und Pools im Bereich der Infrastruktur ausgeführt.

Das Standardszenario heißt **AlwaysOn**. AlwaysOn soll dazu dienen, das Szenario ständig auszuführen, wie der Name des Szenarios bereits impliziert. Das Szenario AlwaysOn erfasst Informationen auf der Ebene "Info" (zum Protokolliergrad "Info" zählen zusätzlich zu den Infomeldungen Meldungen der Ebenen "Schwerwiegend", "Fehler" und "Warnung") für viele der häufigsten Serverkomponenten. Von AlwaysOn werden Informationen vor und nach einem Problem sowie während eines Problems erfasst. Daher unterscheidet es sich gravierend vom typischen Verhalten früherer Protokollierungstools wie OCSLogger. OCSLogger wurde ausgeführt, nachdem das Problem bereits aufgetreten war. Dadurch wurde die Problembehandlung erschwert, da die erfassten Daten nicht proaktiv, sondern rückwirkend waren. Falls AlwaysOn nicht die gewünschten Informationen zum Ermitteln der fehlerhaften Komponente und keine Vorgehensweise zur Behebung enthält (was aufgrund des Umfangs der Anbieter in AlwaysOn unwahrscheinlich ist), erhalten Sie immerhin angemessene Informationen, mit denen die erforderlichen Schritte (z. B. Erstellen eines neuen Szenarios, Erfassen weiterer Informationen, Ausführen einer anderen Suche zum Sammeln genauerer Einzelheiten usw.) ermittelt werden können.

Mit dem Zentraler Protokollierungsdienst können Befehle auf zwei Arten ausgegeben werden. Eine Reihe von Themen konzentriert sich voll und ganz auf die Verwendung von Windows PowerShell über die Lync Server-Verwaltungsshell. Die Möglichkeit, zahlreiche komplexe Konfigurationen und Befehle nutzen zu können, spricht für Windows PowerShell zur Verwendung von Zentraler Protokollierungsdienst. Da Windows PowerShell über die Lync Server-Verwaltungsshell beinahe für alle Funktionen in Lync Server verfügbar ist, werden nur die Windows PowerShell-Befehle besprochen.


> [!NOTE]
> Wenn Sie den in der Befehlszeile verfügbaren eingeschränkten Befehlssatz verwenden möchten, erhalten Sie durch Eingabe von <CODE>ClsController.exe</CODE> Hilfe zu "CLSController.exe". <STRONG>ClsController.exe</STRONG> wird standardmäßig in folgendem Verzeichnis installiert: C:\Programme\Microsoft Lync Server 2013\ClsAgent.



## So führen Sie "Start-CsClsLogging" mit Windows PowerShell mithilfe grundlegender Befehle aus

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Starten Sie ein Protokollierungsszenario mit dem Zentraler Protokollierungsdienst, indem Sie Folgendes eingeben:
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    Geben Sie beispielsweise zum Starten des Szenarios **AlwaysOn** Folgendes ein:
    
        Start-CsClsLogging -Scenario AlwaysOn
    

    > [!NOTE]
    > Für das AlwaysOn-Szenario ist keine Standarddauer festgelegt. Das Szenario wird so lange ausgeführt, bis Sie es mit dem Cmdlet <STRONG>Stop-CsClsLogging</STRONG> explizit beenden. Ausführliche Informationen finden Sie unter <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Stop-CsClsLogging">Stop-CsClsLogging</A>. Für alle anderen Szenarios gilt eine Standarddauer von 4&nbsp;Stunden.



3.  Drücken Sie zum Ausführen des Befehls die EINGABETASTE.
    

    > [!NOTE]
    > Es kann einen kurzen Moment dauern (30 bis 60&nbsp;Sekunden), bis der Befehl ausgeführt und der Status von den Computern in Ihrer Bereitstellung abgerufen wird.

    
    ![Ausführen von Start-CsClsLogging](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Ausführen von Start-CsClsLogging")

4.  Um ein weiteres Szenario zu starten, verwenden Sie das Cmdlet **Start-CsClsLogging** mit dem Namen des zusätzlichen Szenarios (z. B. des Szenarios **Authentifizierung**) wie folgt:
    
        Start-CsClsLogging -Scenario Authentication
    

    > [!IMPORTANT]
    > Sie können jederzeit insgesamt zwei&nbsp;Szenarien auf einem beliebigen Computer ausführen. Hat der Befehl einen globalen Gültigkeitsbereich, werden die Szenarien auf allen Computern in Ihrer Bereitstellung ausgeführt. Wenn Sie ein drittes Szenario starten möchten, müssen Sie die Protokollierung für den Computer, Pool, Standort oder globalen Gültigkeitsbereich beenden, für den das neue Szenario ausgeführt werden soll. Haben Sie einen globalen Gültigkeitsbereich gestartet, können Sie die Protokollierung für mindestens ein Szenario für mindestens einen Computer oder Pool beenden. Ausführliche Informationen zur Verwaltung der ausgeführten Szenarien finden Sie unter <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Verwenden von "Stop" für den zentralisierten Protokollierungsdienst</A> und <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Stop-CsClsLogging">Stop-CsClsLogging</A>.



## So führen Sie "Start-CsClsLogging" mit Windows PowerShell mithilfe erweiterter Befehle aus

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Zur Verwaltung der Protokollierungsbefehle stehen zusätzliche Parameter zur Verfügung. Mit "–Duration" können Sie die Dauer der Ausführung des Szenarios festlegen. Darüber hinaus können Sie "–Computers", eine Liste der durch Komma getrennten Computer-FQDNs (Fully Qualified Domain Names, vollqualifizierte Domänennamen), oder "–Pools", eine durch Komma getrennte Liste der FQDNs aller Pools, für die die Protokollierung ausgeführt werden soll, definieren.
    
    Sie starten eine Protokollierungssitzung für das Szenario *UserReplicator* für den Pool "pool01.contoso.net". Außerdem legen Sie für die Dauer der Protokollierungssitzung 8 Stunden fest. Geben Sie hierzu Folgendes ein:
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    Bei erfolgreicher Ausführung dieses Szenarios wird in etwa folgendes Ergebnis zurückgegeben:
    
    ![Ausführen von Start-CsClsLogging](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Ausführen von Start-CsClsLogging")
    
    Beachten Sie, dass in diesem Beispiel die Szenarien "AlwaysOn" und "UserReplicator" ausgeführt werden.

## Siehe auch

#### Konzepte

[Übersicht über den zentralisierten Protokollierungsdienst](lync-server-2013-overview-of-the-centralized-logging-service.md)

