---
title: Verwenden von "Start" für den zentralisierten Protokollierungsdienst zum Aufzeichnen von Protokollen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5033b4a8dfd8121e2f0b5926623a55358188935e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a>Verwenden von "Start" für den zentralisierten Protokollierungsdienst zum Aufzeichnen von Protokollen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Wenn Sie Ablaufverfolgungsprotokolle mithilfe des zentralen Protokollierungsdiensts erfassen möchten, geben Sie einen Befehl aus, um mit der Protokollierung an einem oder mehreren Computern und Pools zu beginnen. Sie geben auch Parameter an, die definieren, welche Computer oder Pools, welche Szenarien ausgeführt werden sollen (beispielsweise AlwaysOn, ein anderes vordefiniertes Szenario oder ein von Ihnen erstelltes Szenario), welche lync Server-Komponenten (beispielsweise S4, SipStack) nachverfolgt werden sollen.

Wenn Sie die richtigen Informationen erfassen möchten, müssen Sie sicherstellen, dass Sie das richtige Szenario verwenden, um Informationen zu sammeln, die für das Problem relevant sind. Im zentralisierten Protokollierungsdienst ist ein Szenario das Konzept des Aktivierens der Protokollierung auf der Grundlage einer Sammlung von Server Komponenten, Protokollierungsebenen und Flags, was wesentlich effizienter und nützlicher ist, als diese Elemente auf pro-Server-Basis zu definieren. Sie definieren und spezifizieren ein Szenario, das ausgeführt werden soll, und das Szenario wird konsistent über alle Server und Pools im Bereich der Infrastruktur ausgeführt.

Das Standardszenario heißt **AlwaysOn**. Wie der Name bereits andeutet, soll dieses Szenario ständig ausgeführt werden. Das Szenario AlwaysOn erfasst Informationen auf der Ebene „Info“ (zum Protokolliergrad „Info“ zählen zusätzlich zu den Infomeldungen Meldungen der Ebenen „Schwerwiegend“, „Fehler“ und „Warnung“) für viele der häufigsten Serverkomponenten. AlwaysOn erfasst Informationen vor und nach einem Problem sowie während eines Problems. Daher unterscheidet es sich gravierend vom typischen Verhalten früherer Protokollierungstools wie OCSLogger. OCSLogger wurde ausgeführt, nachdem das Problem bereits aufgetreten war. Dadurch wurde die Problembehandlung erschwert, da die erfassten Daten nicht proaktiv, sondern rückwirkend waren. Falls AlwaysOn nicht die gewünschten Informationen zum Ermitteln der fehlerhaften Komponente und keine Vorgehensweise zur Behebung enthält (was aufgrund des Umfangs der Anbieter in AlwaysOn unwahrscheinlich ist), erhalten Sie immerhin angemessene Informationen, mit denen die erforderlichen Schritte (z. B. Erstellen eines neuen Szenarios, Erfassen weiterer Informationen, Ausführen einer anderen Suche zum Sammeln genauerer Einzelheiten usw.) ermittelt werden können.

Der zentralisierte Protokollierungsdienst bietet zwei Möglichkeiten zum Ausgeben von Befehlen. Eine Reihe von Themen wurde direkt auf die Verwendung von Windows PowerShell über die lync Server-Verwaltungsshell ausgerichtet. Die Möglichkeit, eine Reihe von komplexen Konfigurationen und Befehlen zu verwenden, begünstigt Windows PowerShell für die Verwendung zentralisierter Protokollierungsdienste. Da Windows PowerShell über die lync Server-Verwaltungsshell nahezu allgegenwärtig für alle Funktionen in lync Server ist, werden nur die Windows PowerShell-Befehle besprochen.

<div>


> [!NOTE]
> Wenn Sie sich entschließen, den in der Befehlszeile verfügbaren Befehl für begrenzte Befehle zu verwenden, können Sie Hilfe zu <CODE>ClsController.exe</CODE>CLSController. exe erhalten, indem Sie eine Eingabe vornehmen. Standardmäßig wird <STRONG>ClsController. exe</STRONG> im Verzeichnis c:\Programme\Microsoft lync Server 2013 \ ClsAgent installiert.



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>So führen Sie Start-CsClsLogging mit Windows PowerShell mithilfe von einfachen Befehlen aus

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Starten Sie ein Protokollierungsszenario mit dem zentralen Protokollierungsdienst, indem Sie Folgendes eingeben:
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    Geben Sie beispielsweise zum Starten des Szenarios **AlwaysOn** Folgendes ein:
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > Für das Szenario AlwaysOn ist keine Standarddauer festgelegt. Das Szenario wird so lange ausgeführt, bis Sie es mit dem Cmdlet <STRONG>Stop-CsClsLogging</STRONG> explizit beenden. Ausführliche Informationen finden Sie unter <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>. Für alle anderen Szenarien gilt eine Standarddauer von 4 Stunden.

    
    </div>

3.  Drücken Sie zum Ausführen des Befehls die EINGABETASTE.
    
    <div>
    

    > [!NOTE]
    > Es kann einen kurzen Moment dauern (30 bis 60 Sekunden), bis der Befehl ausgeführt und der Status von den Computern in Ihrer Bereitstellung abgerufen wird.

    
    </div>
    
    ![Ausführen von Start-CsClsLogging.] (images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Ausführen von Start-CsClsLogging.")

4.  Um ein weiteres Szenario zu starten, verwenden Sie das Cmdlet **Start-CsClsLogging** mit dem Namen des zusätzlichen Szenarios (z. B. des Szenarios **Authentifizierung**) wie folgt:
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > Sie können jederzeit insgesamt zwei Szenarien auf einem beliebigen Computer ausführen. Wenn der Befehl einen globalen Gültigkeitsbereich hat, werden die Szenarien auf allen Computern in Ihrer Bereitstellung ausgeführt. Wenn Sie ein drittes Szenario starten möchten, müssen Sie die Protokollierung für den Computer, Pool, Standort oder globalen Gültigkeitsbereich beenden, für den das neue Szenario ausgeführt werden soll. Wenn Sie einen globalen Gültigkeitsbereich gestartet, können Sie die Protokollierung für mindestens ein Szenario für mindestens einen Computer oder Pool beenden. Ausführliche Informationen zum Verwalten der ausgeführten Szenarien finden Sie unter <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Verwenden von Stop für den zentralisierten Protokollierungsdienst in lync Server 2013</A> und <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">CsClsLogging</A>.

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>So führen Sie Start-CsClsLogging mit Windows PowerShell mithilfe von erweiterten Befehlen aus

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Zur Verwaltung der Protokollierungsbefehle stehen zusätzliche Parameter zur Verfügung. Mit „–Duration“ können Sie die Dauer der Ausführung des Szenarios festlegen. Darüber hinaus können Sie „–Computers“, eine kommagetrennte Liste der Computer-FQDNs (Fully Qualified Domain Names, vollqualifizierte Domänennamen), oder „–Pools“, eine kommagetrennte Liste der FQDNs aller Pools, für die die Protokollierung ausgeführt werden soll, definieren.
    
    Sie starten eine Protokollierungssitzung für das Szenario  *UserReplicator* im Pool „pool01.contoso.net“. Außerdem legen Sie als Dauer der Protokollierungssitzung 8 Stunden fest. Geben Sie hierzu Folgendes ein:
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    Bei erfolgreicher Ausführung dieses Szenarios wird in etwa folgendes Ergebnis zurückgegeben:
    
    ![Ausführen von Start-CsClsLogging.] (images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Ausführen von Start-CsClsLogging.")
    
    Beachten Sie, dass in diesem Beispiel die Szenarien „AlwaysOn“" und „UserReplicator“ ausgeführt werden.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Übersicht über den zentralisierten Protokollierungsdienst in lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

