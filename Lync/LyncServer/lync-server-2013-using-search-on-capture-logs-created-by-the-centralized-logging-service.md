---
title: Verwenden der Suche in den vom zentralisierten Protokollierungsdienst erstellten Aufnahme Protokollen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using search on capture logs created by the Centralized Logging Service
ms:assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687982(v=OCS.15)
ms:contentKeyID: 49733571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edfc176934479aef04d6850a8ebbae3b38a553a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-search-on-capture-logs-created-by-the-centralized-logging-service-in-lync-server-2013"></a>Verwenden der Suche in Aufzeichnungs Protokollen, die vom zentralisierten Protokollierungsdienst in lync Server 2013 erstellt wurden

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Die Suchfeatures im zentralisierten Protokollierungsdienst sind aus folgenden Gründen nützlich und leistungsfähig:

  - Ihre Suchanfragen und die Ergebnisse werden basierend auf den festgelegten Kriterien auf einem Computer, in einem Pool, an einem Standort oder auf globaler Ebene ausgeführt.

  - Ihre Suchanfragen können breit angelegt sein und anschließend auf genauere Kriterien wie Uhrzeit, Komponente oder Computer eingeschränkt werden. Sie suchen mit denselben Protokollen und müssen nicht erneut eine Protokollierungssitzung ausführen, wenn sich die Suchkriterien ändern.

  - Die Ergebnisse Ihrer Suche werden auf allen Computern und in allen Pools im Bereich erfasst und in einer einzelnen Ausgabedatei gesammelt, die alle Ergebnisse der Suchkriterien enthält (beschränkt auf ausgeführte Szenarien und auf die von den Szenarien erfassten Daten). Sie verwenden zum Lesen der Ausgabedatei und der Ablaufverfolgungsmeldungen in Ihrer Bereitstellung bekannte Tools wie **Snooper** oder **Notepad**.

Der CLS-Agent auf den einzelnen Computern erstellt die Protokolle auf Basis der Szenarien (zwei Szenarien pro Computer können jeweils zu einem bestimmten Zeitpunkt ausgeführt werden). Die Protokolle und ihre zugehörigen Index- und Cachedateien werden vom CLS-Agent verwaltet. Wenn Sie eine Suche definieren und ausführen, weist der Suchbefehl den CLS-Agent an, welche Informationen abgerufen werden sollen. Der CLS-Agent führt die Abfrage für die Protokolldateien, Cachedateien und Indexdateien aus und gibt die Ergebnisse der Suche an den CLS-Controller zurück. Der CLS-Controller empfängt die Suchergebnisse von allen Computern und Pools im Bereich der Suche. Der CLS-Controller aggregiert (kombiniert) anschließend die Protokolle und ordnet sie nach Zeitunterschied an (angefangen beim ältesten Eintrag bis hin zum neuesten Eintrag).

Nach jeder Suche wird das Cmdlet **Sync-CsClsLogging** ausgeführt, und es wird der von Suchvorgängen verwendete Cache geleert (nicht zu verwechseln mit den Cachedateien, die vom CLSAgent verwaltet werden). Durch das Leeren des Caches können Sie sicherstellen, dass im CLSController für den nächsten Suchvorgang ein sauberer Protokoll-und Ablaufverfolgungsdatei-Aufnahmepuffer vorhanden ist.

Um den größten Nutzen aus dem zentralisierten Protokollierungsdienst zu ziehen, benötigen Sie ein gutes Verständnis dafür, wie Sie die Suche so konfigurieren, dass nur nach Verfolgungs Nachrichten von den Computern und Pool Protokollen zurückgegeben werden, die für das von Ihnen recherchierte Problem relevant sind. Fragen

Wenn Sie die Suchfunktionen des zentralen Protokollierungsdiensts mithilfe der lync Server-Verwaltungsshell ausführen möchten, müssen Sie Mitglied der CsAdministrator-oder CsServerAdministrator-Sicherheitsgruppe (Role-Based Access Control, RBAC) oder einer benutzerdefinierten RBAC-Rolle sein, die eine dieser beiden Gruppen. Führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell oder in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Beispiel:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

Der Rest dieses Artikels befasst sich mit dem Definieren einer Suche zur Optimierung der Problembehandlung.

<div>

## <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>So führen Sie eine einfache Suche mit dem zentralen Protokollierungsdienst aus

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Stellen Sie sicher, dass das Szenario „AlwaysOn“ in Ihrer Bereitstellung auf globaler Ebene ausgeführt wird, und geben Sie dann Folgendes an der Eingabeaufforderung ein:
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    <div>
    

    > [!NOTE]
    > Standardmäßig werden von „Search-CsClsLogging“ die Ergebnisse der Suche an die Konsole gesendet. Wenn Sie die Suchergebnisse in einer Datei speichern möchten, verwenden Sie den voll &lt;qualifizierten Dateipfad-OutputFilePath-&gt;Zeichenfolge. Um den Parameter „–OutputFilePath“ zu definieren, geben Sie einen Pfad und einen Dateinamen als Teil des Parameters in Form einer Zeichenfolge zwischen Anführungszeichen ein, z. B. „C:\LogFiles\SearchOutput.txt“. In diesen Beispiel müssen Sie sicherstellen, dass das Verzeichnis „C:\LogFiles“ vorhanden ist und Sie über Lese- und Schreibberechtigungen (NTFS-Berechtigungen) für Dateien in diesem Ordner verfügen. An die Ausgabe werden immer Daten angefügt, sie wird nicht überschrieben. Wenn Sie separate Dateien benötigen, geben Sie unterschiedliche Dateinamen für die einzelnen Suchvorgänge an.

    
    </div>
    
    Beispiel:
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>So führen Sie eine einfache Suche in einem Pool oder Computer mithilfe des zentralen Protokollierungsdiensts aus

1.  Um die Suche auf einen bestimmten Pool oder Computer zu beschränken, verwenden Sie den Parameter „–Computers“ mit dem Computer, der durch einen vollqualifizierten Computernamen angegeben ist. Er wird folgendermaßen in Anführungszeichen gesetzt und durch Komma getrennt:
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    Beispiel:
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  Geben Sie zum Suchen auf mehreren Computern mehrere Computernamen in Anführungszeichen und durch Komma getrennt ein:
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  Wenn Sie einen gesamten Pool anstelle eines einzelnen Computers durchsuchen müssen, ändern Sie den Parameter „–Computers“ in „–Pools“, entfernen Sie den Computernamen und ersetzen Sie ihn durch die Poolnamen (in Anführungszeichen und durch Komma getrennt).
    
    Beispiel:
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  Bei Verwendung der Suchbefehle können Pools in Ihrer Bereitstellung ein beliebiger Pool sein, beispielsweise Front-End-Pools, Edge-Pools, persistent Chat-Server Pools oder andere, die in Ihrer Bereitstellung als Pool definiert sind.
    
    Beispiel:
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-search-by-using-time-parameters"></a>So führen Sie eine Suche mithilfe von Zeitparametern aus

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Standardmäßig beträgt die Anfangszeit für die zeitspezifischen Parameter einer Suche 30 Minuten vor dem Zeitpunkt, zu dem Sie die Suche initiieren. Anders ausgedrückt: Wenn Sie Ihre Suche um 4:00:00 Uhr initiieren, werden die Protokolle nach den Computern und Pools durchsucht, die Sie von 3:30:00 Uhr bis 4:00:00 Uhr definieren. Wenn eine Suche 60 Minuten oder 3 Stunden vor der aktuellen Uhrzeit ausgeführt werden soll, verwenden Sie den Parameter „–StartTime“ und legen Sie die Zeichenfolge für Datum und Uhrzeit fest, um die Uhrzeit für den Beginn der Suche anzugeben.
    
    Beispiel: Wenn Sie mit „–StartTime“ und „–EndTime“ einen Uhrzeit- und Datumsbereich festlegen, können Sie eine Suche in Ihrem Pool für den Zeitraum zwischen 8 und 9 Uhr am am 20.11.2012 festlegen. Sie können den Ausgabepfad so einstellen, dass die Ergebnisse in eine Datei mit dem\\Namen c: Logfile. txt wie folgt geschrieben werden:
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <div>
    

    > [!NOTE]
    > Die angegebene Uhrzeit- und Datumszeichenfolge kann „Datum Uhrzeit“ oder „Uhrzeit Datum“ lauten. "Mit dem Befehl wird die Zeichenfolge analysiert und die entsprechenden Werte für Datum und Uhrzeit verwendet.

    
    </div>

3.  Wenn Sie mit dem Abrufen von Protokollen am 20.11.2012 um 11:00 Uhr beginnen möchten, legen Sie dies als „–StartTime“ fest. Der Standardzeitraum für die Suche beträgt 30 Minuten, es sei denn, Sie legen einen bestimmten Wert für „–EndTime“ fest. Die Suche gibt Protokolle der festgelegten Computer oder Pools aus dem Zeitraum von 11:00 Uhr bis 11:30 Uhr zurück.
    
    Beispiel:
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  Legen Sie zum Ausführen einer Suche nach Protokollen in einem bestimmten Zeitraum „–StartTime“ und „–EndTime“ fest. Sie benötigen Protokolle für den Zeitraum zwischen 13 und 14:45 Uhr auf dem Computer „edge01.contoso.net“.
    
    Beispiel:
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>So führen Sie mithilfe weiterer Kriterien und Abgleichungsoptionen eine erweiterte Suche aus

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Geben Sie zum Ausführen eines Befehls zum Erfassen von Ablaufverfolgungen für bestimmte Komponenten Folgendes ein:
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    Beispiel:
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    Die Suche gibt alle Protokolleinträge zurück, die Ablaufverfolgungskomponenten für SIPStack, S4 und UserServices für alle Computer und Pools in Ihrer Bereitstellung in den letzten 30 Minuten enthalten.

3.  Wenn Sie die Suche auf die gleichen Komponenten nur auf Ihren Front-End-Pool mit dem Namen pool01.contoso.net beschränken möchten, geben Sie Folgendes ein:
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  Die Standardsuchlogik für Befehle mit mehreren Parametern besteht darin, das logische „Oder“ mit den einzelnen definierten Parametern zu verwenden. Sie können dieses Verhalten durch Angabe des Parameters **–MatchAll** ändern. Geben Sie dazu Folgendes ein:
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  Wenn Ihre Szenarien für eine ständige Ausführung festgelegt sind (wie AlwaysOn) oder wenn Sie ein langfristiges Szenario festgelegt haben, werden Protokolle möglicherweise vom lokalen Computer auf die Dateifreigabe verschoben. Sie legen die Dateifreigabe  mithilfe des Parameters „CacheFileNetworkFolder“ fest, um mithilfe von „New-CsClsConfiguration“ eine neue Konfiguration zu erstellen oder mithilfe von „Set-CsClsConfiguration“ eine vorhandene Konfiguration zu ändern. Wenn die Dateifreigabe in der Auflistung der zu durchsuchenden Protokolle nicht durchsucht werden soll, verwenden Sie den Parameter „SkipNetworkLogs“ folgendermaßen:
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

</div>

<span> </span>

</div>

</div>

</div>

