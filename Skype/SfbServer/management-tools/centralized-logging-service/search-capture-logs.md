---
title: Suche nach vom zentralisierten Protokollierungsdienst in Skype for Business Server 2015 erstellten Erfassungsprotokollen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie in Skype for Business Server 2015 die Protokolle für zentralisierte Protokollierungsdienste durchsuchen und lesen können.'
ms.openlocfilehash: 563f2c5e08da0830c3bd03e562d0d94052fa359b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991450"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Suche nach vom zentralisierten Protokollierungsdienst in Skype for Business Server 2015 erstellten Erfassungsprotokollen
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie in Skype for Business Server 2015 die Protokolle für zentralisierte Protokollierungsdienste durchsuchen und lesen können.
  
Die Suchfeatures im zentralisierten Protokollierungsdienst sind aus folgenden Gründen nützlich und leistungsfähig: 
  
- Ihre Suchanfragen und die Ergebnisse werden basierend auf den festgelegten Kriterien auf einem Computer, in einem Pool, an einem Standort oder auf globaler Ebene ausgeführt.
    
- Ihre Suchanfragen können breit angelegt sein und anschließend auf genauere Kriterien wie Uhrzeit, Komponente oder Computer eingeschränkt werden. Sie suchen nach denselben Protokollen und müssen keine Protokollierungssitzung erneut ausführen, wenn sich die Suchkriterien ändern.
    
- Die Ergebnisse Ihrer Suche werden auf allen Computern und in allen Pools im Bereich erfasst und in einer einzelnen Ausgabedatei gesammelt, die alle Ergebnisse der Suchkriterien enthält (beschränkt auf ausgeführte Szenarien und auf die von den Szenarien erfassten Daten). Sie verwenden zum Lesen der Ausgabedatei und der Ablaufverfolgungsmeldungen in Ihrer Bereitstellung bekannte Tools wie **Snooper** oder **Notepad**.
    
Der CLS-Agent auf den einzelnen Computern erstellt die Protokolle auf Basis der Szenarien (zwei Szenarien pro Computer können jeweils zu einem bestimmten Zeitpunkt ausgeführt werden). Die Protokolle und ihre zugehörigen Index- und Cachedateien werden vom CLS-Agent verwaltet. Wenn Sie eine Suche definieren und ausführen, weist der Suchbefehl den CLS-Agent an, welche Informationen abgerufen werden sollen. Der CLS-Agent führt die Abfrage für die Protokolldateien, Cachedateien und Indexdateien aus und gibt die Ergebnisse der Suche an den CLS-Controller zurück. Der CLS-Controller empfängt die Suchergebnisse von allen Computern und Pools im Bereich der Suche. Der CLS-Controller aggregiert (kombiniert) anschließend die Protokolle und ordnet sie nach Zeitunterschied an (angefangen beim ältesten Eintrag bis hin zum neuesten Eintrag).
  
Nach jeder Suche wird das Cmdlet **Sync-CsClsLogging** ausgeführt, und es wird der von Suchvorgängen verwendete Cache geleert (nicht zu verwechseln mit den Cachedateien, die vom CLSAgent verwaltet werden). Durch das Leeren des Caches können Sie sicherstellen, dass im CLSController für den nächsten Suchvorgang ein sauberer Protokoll-und Ablaufverfolgungsdatei-Aufnahmepuffer vorhanden ist.
  
Um den größten Nutzen aus dem zentralisierten Protokollierungsdienst zu ziehen, benötigen Sie ein gutes Verständnis dafür, wie Sie die Suche so konfigurieren, dass nur nach Verfolgungs Nachrichten von den Computern und Pool Protokollen zurückgegeben werden, die für das von Ihnen recherchierte Problem relevant sind. Fragen
  
Wenn Sie die Suchfunktionen für den zentralisierten Protokollierungsdienst mithilfe der Skype for Business Server-Verwaltungsshell ausführen möchten, müssen Sie Mitglied der CsAdministrator-oder CsServerAdministrator-Sicherheitsgruppe (Role-Based Access Control, RBAC) oder einer benutzerdefinierten RBAC-Rolle sein. , die eine dieser beiden Gruppen enthält. Führen Sie den folgenden Befehl aus der Skype for Business Server-Verwaltungsshell oder der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Beispiel:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Der Rest dieses Artikels befasst sich mit dem Definieren einer Suche zur Optimierung der Problembehandlung.
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>So führen Sie eine einfache Suche mit dem zentralen Protokollierungsdienst aus

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Stellen Sie sicher, dass das Szenario „AlwaysOn“ in Ihrer Bereitstellung auf globaler Ebene ausgeführt wird, und geben Sie dann Folgendes an der Eingabeaufforderung ein:
    
   ```PowerShell
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> Standardmäßig werden von „Search-CsClsLogging“ die Ergebnisse der Suche an die Konsole gesendet. Wenn Sie die Suchergebnisse in einer Datei speichern möchten, verwenden Sie-OutputFilePath _ \<Zeichenfolge vollqualifizierter\>Dateipfad_. Um den Parameter-OutputFilePath zu definieren, geben Sie einen Pfad und einen Dateinamen als Teil des Parameters in einem in Anführungszeichen eingeschlossenen Zeichenfolgenformat an (beispielsweise; C:\LogFiles\SearchOutput.txt). In diesen Beispiel müssen Sie sicherstellen, dass das Verzeichnis „C:\LogFiles“ vorhanden ist und Sie über Lese- und Schreibberechtigungen (NTFS-Berechtigungen) für Dateien in diesem Ordner verfügen. An die Ausgabe werden immer Daten angefügt, sie wird nicht überschrieben. Wenn Sie separate Dateien benötigen, geben Sie unterschiedliche Dateinamen für die einzelnen Suchvorgänge an. 
  
Beispiel:
    
  ```PowerShell
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>So führen Sie eine einfache Suche in einem Pool oder Computer mithilfe des zentralen Protokollierungsdiensts aus

1. Wenn Sie die Suche auf einen bestimmten Pool oder Computer einschränken möchten, verwenden Sie den-Computers-Parameter mit dem Computer, der durch einen vollqualifizierten Computernamen definiert ist, in Anführungszeichen eingeschlossen und wie folgt durch ein Komma getrennt:
    
   ```PowerShell
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

Beispiel:
    
  ```PowerShell
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. Geben Sie zum Suchen auf mehreren Computern mehrere Computernamen in Anführungszeichen und durch Komma getrennt ein:
    
   ```PowerShell
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. Wenn Sie einen gesamten Pool anstelle eines einzelnen Computers durchsuchen müssen, ändern Sie den Parameter-Computer in-Pools, entfernen Sie den Computernamen, und ersetzen Sie ihn durch den Pool oder die Pools in Anführungszeichen durch Kommas getrennt.
    
    Beispiel:
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. Bei Verwendung der Suchbefehle können Pools in Ihrer Bereitstellung ein beliebiger Pool sein, beispielsweise Front-End-Pools, Edge-Pools, persistent Chat-Server Pools oder andere, die in Ihrer Bereitstellung als Pool definiert sind.
    
    Beispiel:
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a>So führen Sie eine Suche mithilfe von Zeitparametern aus

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Standardmäßig liegt die Startzeit für die zeitspezifischen Parameter einer Suche 25 Minuten vor bis fünf Minuten nach der Zeit, zu der die Suche gestartet wird. Mit anderen Worten: Wenn die Suche um 16:00 Uhr gestartet wird, wird als Startzeit der Suche 15:35 Uhr bis 16:05 Uhr angezeigt. Wenn Sie 60 Minuten oder 3 Stunden vor der aktuellen Uhrzeit suchen müssen, verwenden Sie den-startTime-Parameter, und legen Sie die Datums-und Uhrzeitzeichenfolge fest, um die Uhrzeit anzugeben, zu der die Suche beginnen soll. 
    
    Wenn Sie beispielsweise-StartTime und-EndTime verwenden, um einen Zeit-und Datumsbereich zu definieren, können Sie eine Suche zwischen 8 und 9 Uhr auf 11/20/2012 im Pool definieren. Sie können den Ausgabepfad angeben, sodass die Ergebnisse folgendermaßen in eine Datei namens „c:\logfile.txt“ geschrieben werden:
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> Die angegebene Uhrzeit- und Datumszeichenfolge kann „Datum Uhrzeit“ oder „Uhrzeit Datum“ lauten. "Der Befehl analysiert die Zeichenfolge und verwendet die entsprechenden Werte für Datum und Uhrzeit sowie ihre Gebietsschema-und Kultureinstellungen auf dem Computer, aus dem Sie das Cmdlet ausführen. 
  
3. Wenn Sie die Protokolle ab 11:00:00 am 11/20/2012 abrufen möchten, definieren Sie die Startzeit. Der standardmäßige Zeitbereich für die Suche beträgt 30 Minuten, es sei denn, Sie definieren einen bestimmten-EndTime. Die Suche gibt Protokolle der festgelegten Computer oder Pools aus dem Zeitraum von 11:00 Uhr bis 11:30 Uhr zurück.
    
Beispiel:
    
  ```PowerShell
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. Wenn Sie eine Suche nach Protokollen innerhalb eines bestimmten Zeitraums durchführen möchten, definieren Sie a-StartTime und a-EndTime. Sie benötigen Protokolle für den Zeitraum zwischen 13 und 14:45 Uhr auf dem Computer „edge01.contoso.net“. 
    
Beispiel:
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>So führen Sie mithilfe weiterer Kriterien und Abgleichungsoptionen eine erweiterte Suche aus

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Geben Sie zum Ausführen eines Befehls zum Erfassen von Ablaufverfolgungen für bestimmte Komponenten Folgendes ein:
    
   ```PowerShell
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

Beispiel:
    
  ```PowerShell
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

Die Suche gibt alle Protokolleinträge zurück, die Ablaufverfolgungskomponenten für SIPStack, S4 und UserServices für alle Computer und Pools in Ihrer Bereitstellung in den letzten 30 Minuten enthalten.
    
3. Wenn Sie die Suche auf die gleichen Komponenten nur auf Ihren Front-End-Pool mit dem Namen pool01.contoso.net beschränken möchten, geben Sie Folgendes ein:
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. Die Standardsuchlogik für Befehle mit mehreren Parametern besteht darin, das logische „Oder“ mit den einzelnen definierten Parametern zu verwenden. Sie können dieses Verhalten ändern, indem Sie den Parameter **-MatchAll** angeben. Geben Sie dazu Folgendes ein:
    
   ```PowerShell
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. Wenn Ihre Szenarien für eine ständige Ausführung festgelegt sind (wie AlwaysOn) oder wenn Sie ein langfristiges Szenario festgelegt haben, werden Protokolle möglicherweise vom lokalen Computer auf die Dateifreigabe verschoben. Sie legen die Dateifreigabe  mithilfe des Parameters „CacheFileNetworkFolder“ fest, um mithilfe von „New-CsClsConfiguration“ eine neue Konfiguration zu erstellen oder mithilfe von „Set-CsClsConfiguration“ eine vorhandene Konfiguration zu ändern. Wenn die Dateifreigabe in der Auflistung der zu durchsuchenden Protokolle nicht durchsucht werden soll, verwenden Sie den Parameter „SkipNetworkLogs“ folgendermaßen:
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a>Lesen von Erfassungsprotokollen aus dem zentralisierten Protokollierungsdienst

Sie erkennen den wirklichen Vorteil des zentralen Protokollierungsdiensts, nachdem Sie die Suche ausgeführt haben, und Sie verfügen über eine Datei, mit der Sie ein gemeldetes Problem nachvollziehen können. Es gibt eine Reihe von Möglichkeiten, wie Sie die Datei lesen können. Die Ausgabedatei befindet sich in einem Standardtextformat, und Sie können Notepad. exe oder alle anderen Programme verwenden, die es Ihnen ermöglichen, eine Textdatei zu öffnen und zu lesen. Für größere Dateien und komplexere Probleme können Sie ein Tool wie Snooper. exe verwenden, das zum Lesen und Analysieren der Protokollierungsausgabe vom zentralen Protokollierungsdienst entwickelt wurde. Snooper ist im Lieferumfang der Debug-Tools enthalten, die als separater Download zur Verfügung stehen. Sie können die Debug-Tools hier herunter [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257)laden:. Wenn Sie die Debug-Tools installieren, werden keine kurzen Schnitte und Menüelemente erstellt. Nachdem Sie die Debug-Tools installiert haben, öffnen Sie den Windows-Explorer, ein Befehlszeilenfenster oder die Skype for Business Server-Verwaltungsshell, und wechseln Sie zum Verzeichnis (Standardspeicherort) C:\Program Files\Skype for Business Server 2015 \ Debugging Tools. Doppelklicken Sie auf Snooper. exe, oder geben Sie Snooper. exe ein, und drücken Sie dann die EINGABETASTE, wenn Sie die Befehlszeile oder die Skype for Business Server-Verwaltungsshell verwenden.
  
> [!IMPORTANT]
> In diesem Thema sollen keine Problembehandlungstechniken beschrieben und behandelt werden. Die Problembehandlung und die damit verbundenen Prozesse sind ein komplexes Thema. Details zu den Grundlagen der Problembehandlung und zur Problembehandlung bei bestimmten Arbeitslasten finden Sie im Microsoft lync [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003)Server 2010 Resource Kit-Handbuch unter. Die Prozesse und Verfahren gelten weiterhin für Skype for Business Server 2015. 
  
### <a name="to-open-a-log-file-in-snooper"></a>So öffnen Sie eine Protokolldatei in Snooper

1. Zum Öffnen von Protokolldateien mithilfe von Snooper benötigen Sie Lesezugriff für die Protokolldateien. Für den Zugriff auf die Protokolldateien mithilfe von Snooper müssen Sie ein Mitglied der rollenbasierten Zugriffssteuerungs-Sicherheitsgruppe „CsAdministrator“ oder „CsServerAdministrator“ oder einer benutzerdefinierten rollenbasierten Zugriffssteuerungsrolle sein, die eine dieser beiden Gruppen enthält. 
    
2. Nach der Installation der Debugtools („LyncDebugTools.msi“) wechseln Sie in Windows Explorer oder in der Befehlszeile zum Verzeichnis, in dem „Snooper.exe“ gespeichert ist. Standardmäßig befinden sich die Debug-Tools unter C:\Program Files\Skype for Business Server 2015 \ Debugging Tools. Führen Sie „Snooper.exe“ mittels Doppelklick aus.
    
3. Nachdem Snooper geöffnet wurde, klicken Sie mit der rechten Maustaste auf **File** (Datei), klicken Sie auf **OpenFile** (Datei öffnen), suchen Sie nach Ihren Protokolldateien, wählen Sie eine Datei im Dialogfeld **Open** (Öffnen) aus und klicken Sie dann auf **Open** (Öffnen).
    
4. Die **Ablauf Verfolgungs** Meldungen der Protokolldatei werden auf der Registerkarte **Ablaufverfolgung** angezeigt. Klicken Sie auf die Registerkarte **Nachrichten** , um den Nachrichteninhalt der gesammelten Ablaufverfolgungen anzuzeigen.
    
### <a name="to-display-a-call-flow-diagram"></a>So zeigen Sie ein Anrufflussdiagramm an

1. Zum Öffnen von Protokolldateien mithilfe von Snooper benötigen Sie Lesezugriff für die Protokolldateien. Für den Zugriff auf die Protokolldateien mithilfe von Snooper müssen Sie ein Mitglied der rollenbasierten Zugriffssteuerungs-Sicherheitsgruppe „CsAdministrator“ oder „CsServerAdministrator“ oder einer benutzerdefinierten rollenbasierten Zugriffssteuerungsrolle sein, die eine dieser beiden Gruppen enthält.
    
2. Öffnen Sie eine Protokolldatei und klicken Sie auf die Registerkarte **Messages** (Nachrichten), wählen Sie eine Unterhaltung in der Nachrichtenansicht aus oder wählen Sie eine Ablaufverfolgungskomponente auf der Registerkarte **Trace** (Ablaufverfolgung) aus.
    
3. Klicken Sie auf **Call Flow** (Anruffluss).
    
> [!NOTE]
> Wenn Sie auf eine Nachricht oder eine Ablaufverfolgung klicken, die nicht Teil eines Anrufflusses ist, wird das Diagramm nicht angezeigt, und unten in Snooper wird eine Statusmeldung angezeigt, die besagt, dass "diese Nachricht nicht für callfow geeignet ist". Wählen Sie eine andere Nachricht oder Ablaufverfolgung aus, und der Anruffluss wird angezeigt, wenn die Nachricht oder Ablaufverfolgung Teil eines Anrufflusses ist. 
  
4. Navigieren Sie in den Nachrichten oder Ablaufverfolgungszeilen und überprüfen Sie, ob das Anrufflussdiagramm aktualisiert oder geändert und ein neues Diagramm angezeigt wird.
    
5. Zeigen Sie auf Elemente, um Informationen zu Anrufnachrichten, Endpunkten und sonstigen Komponenten anzuzeigen.
