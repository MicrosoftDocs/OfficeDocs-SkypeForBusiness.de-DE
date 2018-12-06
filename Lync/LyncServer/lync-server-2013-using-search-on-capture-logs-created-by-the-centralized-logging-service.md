---
title: Verwenden der Suche in Erfassungsprotokollen, die vom zentralisierten Protokollierungsdienst erstellt wurden
TOCTitle: Verwenden der Suche in Erfassungsprotokollen, die vom zentralisierten Protokollierungsdienst erstellt wurden
ms:assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ687982(v=OCS.15)
ms:contentKeyID: 49890645
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwenden der Suche in Erfassungsprotokollen, die vom zentralisierten Protokollierungsdienst erstellt wurden

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Die Suchfunktionen im zentralisierten Protokollierungsdienst sind aus folgenden Gründen nützlich und leistungsfähig:

  - Ihre Suchanfragen und die Ergebnisse werden basierend auf den festgelegten Kriterien auf einem Computer, in einem Pool, an einem Standort oder auf globaler Ebene ausgeführt.

  - Ihre Suchanfragen können breit angelegt sein und anschließend auf genauere Kriterien wie Uhrzeit, Komponente oder Computer eingeschränkt werden. Sie suchen mit denselben Protokollen und müssen nicht erneut eine Protokollierungssitzung ausführen, wenn sich die Suchkriterien ändern.

  - Die Ergebnisse Ihrer Suche werden auf allen Computern und in allen Pools im Bereich erfasst und in einer einzelnen Ausgabedatei gesammelt und aggregiert, die alle Ergebnisse der Suchkriterien enthält (beschränkt auf ausgeführte Szenarien und auf die von den Szenarien erfassten Daten). Sie verwenden zum Lesen der Ausgabedatei und der Ablaufverfolgungsmeldungen in Ihrer Bereitstellung bekannte Tools wie **Snooper** oder **Editor**.

Der CLS-Agent auf den einzelnen Computern erstellt die Protokolle auf Basis der Szenarien (zwei Szenarien pro Computer können jeweils zu einem bestimmten Zeitpunkt ausgeführt werden). Die Protokolle und ihre zugehörigen Index- und Cachedateien werden vom CLS-Agent verwaltet. Wenn Sie eine Suche definieren und ausführen, weist der Suchbefehl den CLS-Agent an, welche Informationen abgerufen werden sollen. Der CLS-Agent führt die Abfrage für die Protokolldateien, Cachedateien und Indexdateien aus und gibt die Ergebnisse der Suche an den CLS-Controller zurück. Der CLS-Controller empfängt die Suchergebnisse von allen Computern und Pools im Bereich der Suche. Der CLS-Controller aggregiert (kombiniert) anschließend die Protokolle und ordnet sie nach Zeitunterschied an (angefangen beim ältesten Eintrag bis hin zum neuesten Eintrag).

Nach der Suche wird das Cmdlet **Sync-CsClsLogging** ausgeführt. Der von den Suchvorgängen verwendete Cache (nicht zu verwechseln mit den vom CLS-Agent verwalteten Cachedateien) wird geleert. Durch das Leeren des Cache wird sichergestellt, dass im CLS-Controller ein sauberer Sammlungspuffer für Protokoll- und Ablaufverfolgungsdateien für den nächsten Suchvorgang zur Verfügung steht.

Damit Sie den zentralisierten Protokollierungsdienst optimal nutzen können, sollten Sie mit der Vorgehensweise zum Konfigurieren von Suchvorgängen vertraut sein, damit nur Ablaufverfolgungsmeldungen aus Computer- und Poolprotokollen zurückgegeben werden, die für das entsprechende Problem relevant sind.

Zum Ausführen der Suchfunktionen des zentralisierten Protokollierungsdiensts mithilfe der Lync Server-Verwaltungsshell müssen Sie Mitglied der rollenbasierten Zugriffssteuerungs-Sicherheitsgruppe "CsAdministrator" oder "CsServerAdministrator" oder einer benutzerdefinierten RBAC-Rolle sein, die eine dieser beiden Gruppen umfasst. Um eine Liste mit allen RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller von Ihnen erstellten, benutzerdefinierten RBAC-Rollen), führen Sie in der Lync Server-Verwaltungsshell oder die Windows PowerShell-Aufforderung aus:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Beispiel:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

Der Rest dieses Artikels befasst sich mit dem Definieren einer Suche zur Optimierung der Problembehandlung.

## So führen Sie mithilfe des Zentraler Protokollierungsdiensts eine einfache Suche durch

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Stellen Sie sicher, dass das AlwaysOn-Szenario in Ihrer Bereitstellung auf globaler Ebene ausgeführt wird, und geben Sie dann Folgendes an der Eingabeaufforderung ein:
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    

    > [!NOTE]
    > Standardmäßig werden von "Search-CsClsLogging" die Ergebnisse der Suche an die Konsole gesendet. Wenn Sie die Suchergebnisse in einer Datei speichern möchten, verwenden Sie dazu "–OutputFilePath <EM>&lt;Vollqualifizierter Dateipfad&gt;</EM>. Um den Parameter "–OutputFilePath" zu definieren, geben Sie einen Pfad und einen Dateinamen als Teil des Parameters in Form einer Zeichenfolge zwischen Anführungszeichen ein, z.&nbsp;B. "C:\LogFiles\SearchOutput.txt". In diesen Beispiel müssen Sie sicherstellen, dass das Verzeichnis "C:\LogFiles" vorhanden ist und Sie über Lese- und Schreibberechtigungen (NTFS-Berechtigungen) für Dateien in diesem Ordner verfügen. An die Ausgabe werden immer Daten angefügt, sie wird nicht überschrieben. Wenn Sie separate Dateien benötigen, geben Sie unterschiedliche Dateinamen für die einzelnen Suchvorgänge an.

    
    Beispiel:
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

## So führen Sie mithilfe des zentralisierten Protokollierungsdiensts eine einfache Suche für einen Pool oder auf einem Computer durch

1.  Um die Suche auf einen bestimmten Pool oder Computer einzuschränken, verwenden Sie den Parameter "–Computers" mit dem Computer, der durch einen vollqualifizierten Computernamen angegeben ist. Er wird folgendermaßen in Anführungszeichen gesetzt und durch Komma getrennt:
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    Beispiel:
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  Geben Sie zum Suchen auf mehreren Computern mehrere Computernamen in Anführungszeichen und durch Komma getrennt ein:
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  Wenn Sie einen gesamten Pool anstelle eines einzelnen Computers durchsuchen müssen, ändern Sie den Parameter "–Computers" in "–Pools", entfernen Sie den Computernamen, und ersetzen Sie ihn mit den Pools (versehen mit Anführungszeichen und durch Komma getrennt).
    
    Beispiel:
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  Bei Verwendung der Suchbefehle können beliebige Pools in Ihrer Bereitstellung verwendet werden, z. B. Front-End-Pools, Edgepools, Serverpools für beständigen Chat oder andere Elemente, die als Pools in Ihrer Bereitstellung definiert sind.
    
    Beispiel:
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

## So führen Sie eine Suche mithilfe der Zeitparameter aus

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Standardmäßig liegt die Startzeit für die zeitspezifischen Parameter einer Suche 30 Minuten vor der Zeit, zu der die Suche gestartet wird. Anders ausgedrückt: Wenn Sie die Suche um 16:00 Uhr starten, werden die Protokolle für die festgelegten Computer und Pools zwischen 15:30 und 16:00 Uhr durchsucht. Wenn 60 Minuten oder 3 Stunden vor der aktuellen Uhrzeit eine Suche ausgeführt werden soll, verwenden Sie den Parameter "–StartTime", und legen Sie die Zeichenfolge für Datum und Uhrzeit fest, um die Uhrzeit für den Beginn der Suche anzugeben.
    
    Beispiel: Wenn Sie mit "–StartTime" und "–EndTime" einen Uhrzeit- und Datumsbereich festlegen, können Sie eine Suche für den 20.11.2012 für den Zeitraum zwischen 8 und 9 Uhr für Ihren Pool definieren. Sie können den Ausgabepfad angeben, sodass die Ergebnisse folgendermaßen in eine Datei namens "c:\\logfile.txt" geschrieben werden:
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    

    > [!NOTE]
    > Die angegebene Uhrzeit- und Datumszeichenfolge kann "Datum Uhrzeit" oder "Uhrzeit Datum" lauten. Der Befehl analysiert die Zeichenfolge und verwendet die entsprechenden Werte für Datum und Uhrzeit.



3.  Wenn Sie mit dem Abrufen von Protokollen am 20.11.2012 um 11:00 Uhr beginnen möchten, legen Sie "–StartTime" fest. Der Standardzeitraum für die Suche ist 30 Minuten, es sei denn, Sie legen einen bestimmten Wert für "–EndTime" fest. Die Suche gibt Protokolle der festgelegten Computer oder Pools aus dem Zeitraum zwischen 11:00 Uhr bis 11:30 Uhr zurück.
    
    Beispiel:
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  Legen Sie zum Ausführen einer Suche nach Protokollen in einem bestimmten Zeitraum "–StartTime" und "–EndTime" fest. Sie benötigen Protokolle für den Zeitraum zwischen 13 und 14:45 Uhr auf dem Computer "edge01.contoso.net".
    
    Beispiel:
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

## So führen Sie mithilfe weiterer Kriterien und Abgleichungsoptionen eine erweiterte Suche aus

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Geben Sie zum Ausführen eines Befehls zum Erfassen von Ablaufverfolgungen für bestimmte Komponenten Folgendes ein:
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    Beispiel:
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    Die Suche gibt alle Protokolleinträge zurück, die Ablaufverfolgungskomponenten für SIPStack, S4 und UserServices für alle Computer und Pools in Ihrer Bereitstellung in den letzten 30 Minuten enthalten.

3.  Um die Suche mit denselben Komponenten auf Ihren Front-End-Pool mit dem Namen "pool01.contoso.net" einzuschränken, geben Sie Folgendes ein:
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  Die Standardsuchlogik für Befehle mit mehreren Parametern besteht darin, das logische "Oder" mit den einzelnen definierten Parametern zu verwenden. Sie können dieses Verhalten durch Angabe des Parameters **–MatchAll** ändern. Geben Sie dazu Folgendes ein:
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  Wenn Ihre Szenarien für die ständige Ausführung festgelegt sind (wie AlwaysOn) oder wenn Sie ein langwieriges Szenario festgelegt haben, werden Protokolle möglicherweise vom lokalen Computer auf die Dateifreigabe verschoben. Sie legen die Dateifreigabe mithilfe des Parameters "CacheFileNetworkFolder" fest, um mithilfe von "New-CsClsConfiguration" eine neue Konfiguration zu erstellen oder mithilfe von "Set-CsClsConfiguration" eine vorhandene Konfiguration zu ändern. Soll die Suche die Dateifreigabe in der Auflistung der zu durchsuchenden Protokolle nicht durchsuchen, verwenden Sie den Parameter "SkipNetworkLogs" folgendermaßen:
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

