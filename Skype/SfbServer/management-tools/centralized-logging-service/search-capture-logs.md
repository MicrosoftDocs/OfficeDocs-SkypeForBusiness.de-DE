---
title: Suche nach vom zentralisierten Protokollierungsdienst in Skype for Business Server 2015 erstellten Erfassungsprotokollen
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 'Zusammenfassung: Informationen Sie zum Suchen und Lesen von Erfassungsprotokollen in Skype Centralized Logging Service für Business Server 2015.'
ms.openlocfilehash: 4016aeaac5b693ceef620dad66031254f208bfbf
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20969018"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Suche nach vom zentralisierten Protokollierungsdienst in Skype for Business Server 2015 erstellten Erfassungsprotokollen
 
**Zusammenfassung:** Informationen Sie zum Suchen und Lesen von Erfassungsprotokollen in Skype Centralized Logging Service für Business Server 2015.
  
Die Suchfunktionen in der zentralisierte Protokollierungsdienst sind nützlich und leistungsfähig aus den folgenden Gründen: 
  
- Ihre Suchanfragen und die Ergebnisse werden basierend auf den festgelegten Kriterien auf einem Computer, in einem Pool, an einem Standort oder auf globaler Ebene ausgeführt.
    
- Ihre Suchanfragen können breit angelegt sein und anschließend auf genauere Kriterien wie Uhrzeit, Komponente oder Computer eingeschränkt werden. Sie suchen gegen die gleichen Protokolle und müssen nicht ausführen eine protokollierungssitzung erneut Wenn sich die Suchkriterien ändern.
    
- Die Ergebnisse Ihrer Suche werden auf allen Computern und in allen Pools im Bereich erfasst und in einer einzelnen Ausgabedatei gesammelt, die alle Ergebnisse der Suchkriterien enthält (beschränkt auf ausgeführte Szenarien und auf die von den Szenarien erfassten Daten). Sie verwenden zum Lesen der Ausgabedatei und der Ablaufverfolgungsmeldungen in Ihrer Bereitstellung bekannte Tools wie **Snooper** oder **Notepad**.
    
Der CLS-Agent auf den einzelnen Computern erstellt die Protokolle auf Basis der Szenarien (zwei Szenarien pro Computer können jeweils zu einem bestimmten Zeitpunkt ausgeführt werden). Die Protokolle und ihre zugehörigen Index- und Cachedateien werden vom CLS-Agent verwaltet. Wenn Sie eine Suche definieren und ausführen, weist der Suchbefehl den CLS-Agent an, welche Informationen abgerufen werden sollen. Der CLS-Agent führt die Abfrage für die Protokolldateien, Cachedateien und Indexdateien aus und gibt die Ergebnisse der Suche an den CLS-Controller zurück. Der CLS-Controller empfängt die Suchergebnisse von allen Computern und Pools im Bereich der Suche. Der CLS-Controller aggregiert (kombiniert) anschließend die Protokolle und ordnet sie nach Zeitunterschied an (angefangen beim ältesten Eintrag bis hin zum neuesten Eintrag).
  
Nach jedem Suchvorgang mit dem Cmdlet **"Sync-csclslogging"** wird ausgeführt, und es leert den Cache zur Bestimmung von Suchvorgänge (nicht mit der Cachedateien, die CLSAgent verwaltet verwechselt werden). Der Cache wird geleert wird sichergestellt, dass eine Neuinstallation Protokoll- und Trace Capture Dateipuffer an die CLSController für den nächsten Suchvorgang vorhanden ist.
  
Wenn Sie den größten Nutzen aus der zentralisierte Protokollierungsdienst erhalten möchten, benötigen Sie einen umfassenden Überblick über die zum Konfigurieren der Suche zum Zurückgeben von nur Ablaufverfolgungsmeldungen aus den Protokollen Computer und Pools, die für das Problem relevant sind, die Sie suchen. Probleme
  
Um die Suchfunktionen Centralized Logging Service mithilfe der Skype für Business Server-Verwaltungsshell ausgeführt werden soll, müssen Sie Mitglied der Administratorrolle CsAdministrator oder der Sicherheitsgruppen CsServerAdministrator rollenbasierten Zugriffssteuerung (RBAC) oder eine benutzerdefinierte RBAC-Rolle sein. einer dieser beiden Gruppen enthält. Um eine Liste aller RBAC-Rollen, die mit diesem Cmdlet zugewiesen wurde (auch alle benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben), führen Sie den folgenden Befehl aus der Skype für Business Server-Verwaltungsshell oder der Windows PowerShell-Eingabeaufforderung ein:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Beispiel:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Der Rest dieses Artikels befasst sich mit dem Definieren einer Suche zur Optimierung der Problembehandlung.
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>So führen eine einfache Suche mithilfe der zentralisierte Protokollierungsdienst

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Stellen Sie sicher, dass das Szenario „AlwaysOn“ in Ihrer Bereitstellung auf globaler Ebene ausgeführt wird, und geben Sie dann Folgendes an der Eingabeaufforderung ein:
    
  ```
  Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
  ```

> [!NOTE]
> Standardmäßig werden von „Search-CsClsLogging“ die Ergebnisse der Suche an die Konsole gesendet. Wenn Sie die Suchergebnisse in eine Datei speichern möchten, verwenden Sie - OutputFilePath _ \<Zeichenfolge vollständig qualifizierte Pfad\>_. Um den OutputFilePath - Parameter zu definieren, geben Sie einen Pfad und einen Dateinamen als Teil des Parameters in ein Zeichenfolgenformat in Anführungszeichen eingeschlossen (z. b; C:\LogFiles\SearchOutput.txt). In diesen Beispiel müssen Sie sicherstellen, dass das Verzeichnis „C:\LogFiles“ vorhanden ist und Sie über Lese- und Schreibberechtigungen (NTFS-Berechtigungen) für Dateien in diesem Ordner verfügen. An die Ausgabe werden immer Daten angefügt, sie wird nicht überschrieben. Wenn Sie separate Dateien benötigen, geben Sie unterschiedliche Dateinamen für die einzelnen Suchvorgänge an. 
  
Beispiel:
    
  ```
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>Eine einfache Suche auf einem Computer oder Pool So führen Sie mithilfe der zentralisierte Protokollierungsdienst

1. Um die Suche auf einen bestimmten Pool oder Computer beschränken möchten, verwenden Sie den Parameter Computer mit dem Computer durch einen vollqualifizierten Computernamen definiert, in Anführungszeichen eingeschlossen und durch ein Komma getrennt:
    
  ```
  Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
  ```

Beispiel:
    
  ```
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. Geben Sie zum Suchen auf mehreren Computern mehrere Computernamen in Anführungszeichen und durch Komma getrennt ein:
    
  ```
  Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

3. Wenn Sie suchen ein gesamtes Pools anstelle von einem einzelnen Computer müssen, ändern Sie den Computer Parameter - zu - Pools und entfernen Sie den Namen des Computers zu ersetzen mit den Pool oder Pools in Anführungszeichen durch Kommas getrennt.
    
    Beispiel:
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. Wenn Sie die Search-Befehle verwenden, kann Pools jedes Pools in Ihrer Bereitstellung, wie Front-End-Pools, Edge-Pools, Persistent Chat Server-Pools oder andere Personen, die als Pool in Ihrer Bereitstellung definiert sind.
    
    Beispiel:
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-a-search-by-using-time-parameters"></a>So führen Sie eine Suche mithilfe von Zeitparametern aus

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Standardmäßig liegt die Startzeit für die zeitspezifischen Parameter einer Suche 25 Minuten vor bis fünf Minuten nach der Zeit, zu der die Suche gestartet wird. Mit anderen Worten: Wenn die Suche um 16:00 Uhr gestartet wird, wird als Startzeit der Suche 15:35 Uhr bis 16:05 Uhr angezeigt. Wenn Sie 60 Minuten oder 3 Stunden vor der aktuellen Zeit zu suchen, verwenden Sie den Parameter StartTime - und legen Sie die Zeichenfolge für Datum und Uhrzeit an, dass der Zeit müssen möchten Sie die Suche beginnen. 
    
    Definieren Sie einen Bereich für Datum und Uhrzeit mit - Werte von StartTime und EndTime-, können Sie beispielsweise eine Suche zwischen 8 und 9 Uhr 11/20/2012 auf dem Pool definieren. Sie können den Ausgabepfad angeben, sodass die Ergebnisse folgendermaßen in eine Datei namens „c:\logfile.txt“ geschrieben werden:
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

> [!NOTE]
> Die angegebene Uhrzeit- und Datumszeichenfolge kann „Datum Uhrzeit“ oder „Uhrzeit Datum“ lauten. "Der Befehl wird die Zeichenfolge zu analysieren und verwenden Sie die entsprechenden Werte für Datum und Uhrzeit sowie die Gebietsschema und der Kultur Einstellungen auf dem Computer, den, dem Sie aus-Cmdlet ausgeführt werden. 
  
3. Wenn Sie Protokolle beginnend bei 11:00:00 Uhr am 11/20/2012 abrufen möchten, definieren Sie die StartTime. Der Standardbereich Zeit für die Suche ist 30 Minuten, es sei denn, Sie bestimmte - EndTime definieren. Die Suche gibt Protokolle der festgelegten Computer oder Pools aus dem Zeitraum von 11:00 Uhr bis 11:30 Uhr zurück.
    
Beispiel:
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. Zum Durchführen einer Suche von Protokollen innerhalb einer bestimmten Zeitspanne, definieren Sie einen StartTime - und - EndTime. Sie benötigen Protokolle für den Zeitraum zwischen 13 und 14:45 Uhr auf dem Computer „edge01.contoso.net“. 
    
Beispiel:
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>So führen Sie mithilfe weiterer Kriterien und Abgleichungsoptionen eine erweiterte Suche aus

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Geben Sie zum Ausführen eines Befehls zum Erfassen von Ablaufverfolgungen für bestimmte Komponenten Folgendes ein:
    
  ```
  Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
  ```

Beispiel:
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

Die Suche gibt alle Protokolleinträge zurück, die Ablaufverfolgungskomponenten für SIPStack, S4 und UserServices für alle Computer und Pools in Ihrer Bereitstellung in den letzten 30 Minuten enthalten.
    
3. Um die Suche mit denselben Komponenten auf nur den Front-End-Pool mit dem Namen pool01.contoso.net einzuschränken, geben Sie Folgendes ein:
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. Die Standardsuchlogik für Befehle mit mehreren Parametern besteht darin, das logische „Oder“ mit den einzelnen definierten Parametern zu verwenden. Sie können dieses Verhalten ändern, indem Sie den **MatchAll -** Parameter angeben. Geben Sie dazu Folgendes ein:
    
  ```
  Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

5. Wenn Ihre Szenarien für eine ständige Ausführung festgelegt sind (wie AlwaysOn) oder wenn Sie ein langfristiges Szenario festgelegt haben, werden Protokolle möglicherweise vom lokalen Computer auf die Dateifreigabe verschoben. Sie legen die Dateifreigabe  mithilfe des Parameters „CacheFileNetworkFolder“ fest, um mithilfe von „New-CsClsConfiguration“ eine neue Konfiguration zu erstellen oder mithilfe von „Set-CsClsConfiguration“ eine vorhandene Konfiguration zu ändern. Wenn die Dateifreigabe in der Auflistung der zu durchsuchenden Protokolle nicht durchsucht werden soll, verwenden Sie den Parameter „SkipNetworkLogs“ folgendermaßen:
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a>Lesen von Erfassungsprotokollen aus dem zentralisierten Protokollierungsdienst

Sie Nutzung der echte Vorteile Centralized Logging Service, nachdem Sie führen Sie die Suche, und Sie eine Datei haben, mit denen Sie eine gemeldete Problem nachzuverfolgen. Es gibt eine Reihe von Methoden, um die Datei gelesen werden kann. Die Ausgabedatei befindet sich in einer standard-Text-Format und können Notepad.exe oder andere Programme, mit denen Sie öffnen und eine Textdatei lesen. Für größere Dateien und komplexer Probleme können Sie ein Tool wie Snooper.exe, die zum Lesen und analysieren die Protokollierungsausgabe aus der zentralisierte Protokollierungsdienst entwickelt wurde. Snooper gehört zum Lieferumfang der Debugtools, die als separater Download verfügbar sind. Sie können hier die Debugtools herunterladen: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257). Wenn Sie die Debugtools installieren, werden nicht Short schneidet und Menüelemente erstellt. Nach der Installation der Debugtools öffnen Sie Windows Explorer, ein Befehlszeilenfenster oder Skype für Business Server-Verwaltungsshell, und wechseln Sie zum Verzeichnis (Standardspeicherort) C:\Program Files\Skype für Business Server 2015\Debugging Tools. Doppelklicken Sie auf Snooper.exe oder geben Sie Snooper.exe, und drücken Sie die EINGABETASTE, wenn Sie die Befehlszeile oder Skype für Business Server-Verwaltungsshell verwenden.
  
> [!IMPORTANT]
> In diesem Thema sollen keine Problembehandlungstechniken beschrieben und behandelt werden. Die Problembehandlung und die damit verbundenen Prozesse sind ein komplexes Thema. Ausführliche Informationen zu Grundlegende Problembehandlung und Problembehandlung bei Problemen mit spezifischen arbeitsauslastungen, finden Sie unter Microsoft Lync Server 2010 Resource Kit dieses Buch unter [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003). Die Prozesse und Verfahren gelten weiterhin für Skype für Business Server 2015. 
  
### <a name="to-open-a-log-file-in-snooper"></a>So öffnen Sie eine Protokolldatei in Snooper

1. Zum Öffnen von Protokolldateien mithilfe von Snooper benötigen Sie Lesezugriff für die Protokolldateien. Für den Zugriff auf die Protokolldateien mithilfe von Snooper müssen Sie ein Mitglied der rollenbasierten Zugriffssteuerungs-Sicherheitsgruppe „CsAdministrator“ oder „CsServerAdministrator“ oder einer benutzerdefinierten rollenbasierten Zugriffssteuerungsrolle sein, die eine dieser beiden Gruppen enthält. 
    
2. Nach der Installation der Debugtools („LyncDebugTools.msi“) wechseln Sie in Windows Explorer oder in der Befehlszeile zum Verzeichnis, in dem „Snooper.exe“ gespeichert ist. Standardmäßig befinden sich die Debugtools in c:\Programme\Microsoft Files\Skype für Business Server 2015\Debugging Tools. Führen Sie „Snooper.exe“ mittels Doppelklick aus.
    
3. Nachdem Snooper geöffnet wurde, klicken Sie mit der rechten Maustaste auf **File** (Datei), klicken Sie auf **OpenFile** (Datei öffnen), suchen Sie nach Ihren Protokolldateien, wählen Sie eine Datei im Dialogfeld **Open** (Öffnen) aus und klicken Sie dann auf **Open** (Öffnen).
    
4. **Die Protokolldatei Ablaufverfolgungsmeldungen** werden angezeigt auf die **Trace** Registerkarte, klicken Sie auf der Registerkarte **Nachrichten** Nachrichteninhalt die erfassten ablaufverfolgungen anzeigen.
    
### <a name="to-display-a-call-flow-diagram"></a>So zeigen Sie ein Anrufflussdiagramm an

1. Zum Öffnen von Protokolldateien mithilfe von Snooper benötigen Sie Lesezugriff für die Protokolldateien. Für den Zugriff auf die Protokolldateien mithilfe von Snooper müssen Sie ein Mitglied der rollenbasierten Zugriffssteuerungs-Sicherheitsgruppe „CsAdministrator“ oder „CsServerAdministrator“ oder einer benutzerdefinierten rollenbasierten Zugriffssteuerungsrolle sein, die eine dieser beiden Gruppen enthält.
    
2. Öffnen Sie eine Protokolldatei und klicken Sie auf die Registerkarte **Messages** (Nachrichten), wählen Sie eine Unterhaltung in der Nachrichtenansicht aus oder wählen Sie eine Ablaufverfolgungskomponente auf der Registerkarte **Trace** (Ablaufverfolgung) aus.
    
3. Klicken Sie auf **Call Flow** (Anruffluss).
    
> [!NOTE]
> Wenn Sie auf eine Nachricht oder Trace, die nicht Teil einer Anruffluss ist, das Diagramm wird nicht angezeigt, und eine Statusmeldung am unteren Rand Snooper Auskunft über die "Diese Nachricht nicht Callfow werden" wird angezeigt. Wählen Sie aus einer anderen Nachricht oder Trace und der Anruffluss wird angezeigt, wenn die Nachricht oder Trace Bestandteil einer Anruffluss ist. 
  
4. Navigieren Sie in den Nachrichten oder Ablaufverfolgungszeilen und überprüfen Sie, ob das Anrufflussdiagramm aktualisiert oder geändert und ein neues Diagramm angezeigt wird.
    
5. Zeigen Sie auf Elemente, um Informationen zu Anrufnachrichten, Endpunkten und sonstigen Komponenten anzuzeigen.