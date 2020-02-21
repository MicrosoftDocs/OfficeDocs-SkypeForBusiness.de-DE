---
title: Verwenden von Start für den zentralisierten Protokollierungsdienst zum Erfassen von Protokollen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04614e970064f765e24b86b6e875d1fb284b3fbc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a>Verwenden von Start für den zentralisierten Protokollierungsdienst zum Erfassen von Protokollen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Zum Erfassen von Ablaufverfolgungsprotokollen mit dem zentralisierten Protokollierungsdienst geben Sie einen Befehl ein, um mit der Protokollierung für einen oder mehrere Computer und Pools zu beginnen. Sie können auch Parameter ausgeben, die definieren, welche Computer oder Pools, welche Szenarien ausgeführt werden sollen (beispielsweise AlwaysOn, ein anderes vordefiniertes Szenario oder ein Szenario, das Sie erstellt haben), welche lync Server Komponenten (beispielsweise S4, SipStack) zur Ablaufverfolgung.

Um die richtigen Informationen zu erfassen, müssen Sie sicherstellen, dass Sie das richtige Szenario verwenden, um Informationen zu sammeln, die für das Problem relevant sind. Im zentralisierten Protokollierungsdienst ist ein Szenario das Konzept der Aktivierung der Protokollierung basierend auf einer Auflistung von Server Komponenten, Protokollierungsebenen und Flags, die wesentlich effizienter und nützlicher ist, als diese Elemente auf einer pro-Server-Basis zu definieren. Sie definieren und geben ein Szenario an, das ausgeführt werden soll, und das Szenario wird konsistent auf allen Servern und Pools im Bereich der Infrastruktur ausgeführt.

Das Standardszenario heißt **AlwaysOn**. AlwaysOn soll dazu dienen, das Szenario ständig auszuführen, wie der Name des Szenarios bereits impliziert. Das Szenario AlwaysOn erfasst Informationen auf der Ebene "Info" (zum Protokolliergrad "Info" zählen zusätzlich zu den Infomeldungen Meldungen der Ebenen "Schwerwiegend", "Fehler" und "Warnung") für viele der häufigsten Serverkomponenten. Von AlwaysOn werden Informationen vor und nach einem Problem sowie während eines Problems erfasst. Daher unterscheidet es sich gravierend vom typischen Verhalten früherer Protokollierungstools wie OCSLogger. OCSLogger wurde ausgeführt, nachdem das Problem bereits aufgetreten war. Dadurch wurde die Problembehandlung erschwert, da die erfassten Daten nicht proaktiv, sondern rückwirkend waren. Falls AlwaysOn nicht die gewünschten Informationen zum Ermitteln der fehlerhaften Komponente und keine Vorgehensweise zur Behebung enthält (was aufgrund des Umfangs der Anbieter in AlwaysOn unwahrscheinlich ist), erhalten Sie immerhin angemessene Informationen, mit denen die erforderlichen Schritte (z. B. Erstellen eines neuen Szenarios, Erfassen weiterer Informationen, Ausführen einer anderen Suche zum Sammeln genauerer Einzelheiten usw.) ermittelt werden können.

Der zentralisierte Protokollierungsdienst bietet zwei Möglichkeiten zum Ausgeben von Befehlen. Eine Reihe von Themen wurde direkt auf die Verwendung von Windows PowerShell über die lync Server-Verwaltungsshell ausgerichtet. Die Möglichkeit, eine Reihe komplexer Konfigurationen und Befehle zu verwenden, begünstigt Windows PowerShell für die Verwendung von zentralisiertem Protokollierungsdienst. Da Windows PowerShell über das lync Server-Verwaltungsshell für alle Funktionen in lync Server fast allgegenwärtig ist, werden nur die Windows PowerShell-Befehle besprochen.

<div>


> [!NOTE]
> Wenn Sie sich für die Verwendung des begrenzten Befehlssatzes entscheiden, der über die Befehlszeile verfügbar ist, können Sie Hilfe zu CLSController <CODE>ClsController.exe</CODE>. exe erhalten, indem Sie die EINGABETASTE eingeben. Standardmäßig wird <STRONG>ClsController. exe</STRONG> im Verzeichnis C:\Program Files\Microsoft lync Server 2013 \ ClsAgent installiert.



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>So führen Sie Start-CsClsLogging mit Windows PowerShell mit grundlegenden Befehlen aus

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Starten Sie ein Protokollierungsszenario mit dem zentralisierten Protokollierungsdienst, indem Sie Folgendes eingeben:
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    Geben Sie beispielsweise zum Starten des Szenarios **AlwaysOn** Folgendes ein:
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > Für das AlwaysOn-Szenario ist keine Standarddauer festgelegt. Das Szenario wird so lange ausgeführt, bis Sie es mit dem Cmdlet <STRONG>Stop-CsClsLogging</STRONG> explizit beenden. Ausführliche Informationen finden Sie unter <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>. Für alle anderen Szenarios gilt eine Standarddauer von 4 Stunden.

    
    </div>

3.  Drücken Sie zum Ausführen des Befehls die EINGABETASTE.
    
    <div>
    

    > [!NOTE]
    > Es kann einen kurzen Moment dauern (30 bis 60 Sekunden), bis der Befehl ausgeführt und der Status von den Computern in Ihrer Bereitstellung abgerufen wird.

    
    </div>
    
    ![Start-CsClsLogging wird gestartet.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Start-CsClsLogging wird gestartet.")

4.  Um ein weiteres Szenario zu starten, verwenden Sie das Cmdlet **Start-CsClsLogging** mit dem Namen des zusätzlichen Szenarios (z. B. des Szenarios **Authentifizierung**) wie folgt:
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > Sie können jederzeit insgesamt zwei Szenarien auf einem beliebigen Computer ausführen. Hat der Befehl einen globalen Gültigkeitsbereich, werden die Szenarien auf allen Computern in Ihrer Bereitstellung ausgeführt. Wenn Sie ein drittes Szenario starten möchten, müssen Sie die Protokollierung für den Computer, Pool, Standort oder globalen Gültigkeitsbereich beenden, für den das neue Szenario ausgeführt werden soll. Haben Sie einen globalen Gültigkeitsbereich gestartet, können Sie die Protokollierung für mindestens ein Szenario für mindestens einen Computer oder Pool beenden. Ausführliche Informationen zum Verwalten der ausgeführten Szenarien finden Sie unter <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">using Stop for the zentralisiert Logging Service in lync Server 2013</A> and <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>So führen Sie Start-CsClsLogging mit Windows PowerShell mit erweiterten Befehlen aus

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Zur Verwaltung der Protokollierungsbefehle stehen zusätzliche Parameter zur Verfügung. Mit –Duration können Sie die Dauer der Ausführung des Szenarios festlegen. Darüber hinaus können Sie –Computers, eine Liste der durch Komma getrennten Computer-FQDNs (Fully Qualified Domain Names, vollqualifizierte Domänennamen), oder –Pools, eine durch Komma getrennte Liste der FQDNs aller Pools, für die die Protokollierung ausgeführt werden soll, definieren.
    
    Sie starten eine Protokollierungssitzung für das *UserReplicator* -Szenario im Pool "pool01.contoso.net". Außerdem legen Sie für die Dauer der Protokollierungssitzung 8 Stunden fest. Geben Sie hierzu Folgendes ein:
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    Bei erfolgreicher Ausführung dieses Szenarios wird in etwa folgendes Ergebnis zurückgegeben:
    
    ![Start-CsClsLogging wird gestartet.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Start-CsClsLogging wird gestartet.")
    
    Beachten Sie, dass in diesem Beispiel die Szenarien "AlwaysOn" und "UserReplicator" ausgeführt werden.

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

