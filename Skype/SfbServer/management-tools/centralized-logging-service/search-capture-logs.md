---
title: Sucherfassungsprotokolle, die vom zentralisierten Protokollierungsdienst in Skype for Business Server 2015 erstellt wurden
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 'Zusammenfassung: Erfahren Sie, wie Sie aufzeichnungsprotokolle des zentralisierten Protokollierungsdiensts in Skype for Business Server 2015 durchsuchen und lesen.'
ms.openlocfilehash: a65fac6ffc96088cd1e544ed17914128d040e2b6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60831919"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Sucherfassungsprotokolle, die vom zentralisierten Protokollierungsdienst in Skype for Business Server 2015 erstellt wurden
 
**Zusammenfassung:** Erfahren Sie, wie Sie aufzeichnungsprotokolle des zentralisierten Protokollierungsdiensts in Skype for Business Server 2015 suchen und lesen.
  
Die Suchfunktionen im zentralisierten Protokollierungsdienst sind aus den folgenden Gründen nützlich und leistungsfähig: 
  
- Ihre Suchanfragen und die Ergebnisse werden basierend auf den festgelegten Kriterien auf einem Computer, in einem Pool, an einem Standort oder auf globaler Ebene ausgeführt.
    
- Ihre Suchanfragen können breit angelegt sein und anschließend auf genauere Kriterien wie Uhrzeit, Komponente oder Computer eingeschränkt werden. Sie suchen nach denselben Protokollen und müssen keine Protokollierungssitzung erneut ausführen, wenn sich die Suchkriterien ändern.
    
- Die Ergebnisse Ihrer Suche werden auf allen Computern und in allen Pools im Bereich erfasst und in einer einzelnen Ausgabedatei gesammelt und aggregiert, die alle Ergebnisse der Suchkriterien enthält (beschränkt auf ausgeführte Szenarien und auf die von den Szenarien erfassten Daten). Sie verwenden zum Lesen der Ausgabedatei und der Ablaufverfolgungsmeldungen in Ihrer Bereitstellung bekannte Tools wie **Snooper** oder **Editor**.
    
Der CLS-Agent auf den einzelnen Computern erstellt die Protokolle auf Basis der Szenarien (zwei Szenarien pro Computer können jeweils zu einem bestimmten Zeitpunkt ausgeführt werden). Die Protokolle und ihre zugehörigen Index- und Cachedateien werden vom CLS-Agent verwaltet. Wenn Sie eine Suche definieren und ausführen, weist der Suchbefehl den CLS-Agent an, welche Informationen abgerufen werden sollen. Der CLS-Agent führt die Abfrage für die Protokolldateien, Cachedateien und Indexdateien aus und gibt die Ergebnisse der Suche an den CLS-Controller zurück. Der CLS-Controller empfängt die Suchergebnisse von allen Computern und Pools im Bereich der Suche. Der CLS-Controller aggregiert (kombiniert) anschließend die Protokolle und ordnet sie nach Zeitunterschied an (angefangen beim ältesten Eintrag bis hin zum neuesten Eintrag).
  
Nach der Suche wird das Cmdlet **Sync-CsClsLogging** ausgeführt. Der von den Suchvorgängen verwendete Cache (nicht zu verwechseln mit den vom CLS-Agent verwalteten Cachedateien) wird geleert. Durch das Leeren des Cache wird sichergestellt, dass im CLS-Controller ein sauberer Sammlungspuffer für Protokoll- und Ablaufverfolgungsdateien für den nächsten Suchvorgang zur Verfügung steht.
  
Um den größten Nutzen aus dem zentralisierten Protokollierungsdienst zu ziehen, benötigen Sie ein gutes Verständnis dafür, wie Sie die Suche so konfigurieren, dass nur Ablaufverfolgungsnachrichten von den Computer- und Poolprotokollen zurückgegeben werden, die für das von Ihnen untersuchte Problem relevant sind. Probleme
  
Um die Suchfunktionen des zentralisierten Protokollierungsdiensts mithilfe der Skype for Business Server Verwaltungsshell auszuführen, müssen Sie Mitglied der Rollenbasierten Zugriffssteuerungsgruppen (Role-Based Access Control, RBAC) "CsAdministrator" oder "CsServerAdministrator" oder einer benutzerdefinierten RBAC-Rolle sein, die eine dieser beiden Gruppen enthält. Um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben), führen Sie den folgenden Befehl über die Skype for Business Server Verwaltungsshell oder die Windows PowerShell Eingabeaufforderung aus:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Beispiel:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Der Rest dieses Artikels befasst sich mit dem Definieren einer Suche zur Optimierung der Problembehandlung.
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>So führen Sie eine einfache Suche mithilfe des zentralisierten Protokollierungsdiensts aus

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell.**
    
2. Stellen Sie sicher, dass das AlwaysOn-Szenario in Ihrer Bereitstellung auf globaler Ebene ausgeführt wird, und geben Sie dann Folgendes an der Eingabeaufforderung ein:
    
   ```PowerShell
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> Standardmäßig werden von "Search-CsClsLogging" die Ergebnisse der Suche an die Konsole gesendet. Wenn Sie die Suchergebnisse in einer Datei speichern möchten, verwenden Sie -OutputFilePath  _\<string fully qualified file path\>_ . Geben Sie zum Definieren des Parameters "-OutputFilePath" einen Pfad und einen Dateinamen als Teil des Parameters in einem Zeichenfolgenformat an, das in Anführungszeichen eingeschlossen ist (z. B. C:\LogFiles\SearchOutput.txt). In diesen Beispiel müssen Sie sicherstellen, dass das Verzeichnis "C:\LogFiles" vorhanden ist und Sie über Lese- und Schreibberechtigungen  (NTFS-Berechtigungen) für Dateien in diesem Ordner verfügen. An die Ausgabe werden immer Daten angefügt, sie wird nicht überschrieben. Wenn Sie separate Dateien benötigen, geben Sie unterschiedliche Dateinamen für die einzelnen Suchvorgänge an. 
  
Beispiel:
    
  ```PowerShell
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>So führen Sie eine einfache Suche auf einem Pool oder Computer mithilfe des zentralisierten Protokollierungsdiensts aus

1. Um die Suche auf einen bestimmten Pool oder Computer zu beschränken, verwenden Sie den Parameter "-Computers" mit dem Computer, der durch einen vollqualifizierten Computernamen definiert ist, in Anführungszeichen eingeschlossen und durch ein Komma getrennt wie folgt:
    
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

3. Wenn Sie einen gesamten Pool anstelle eines einzelnen Computers durchsuchen müssen, ändern Sie den Parameter "-Computers" in "-Pools", entfernen Sie den Computernamen, und ersetzen Sie ihn durch den Pool oder die Pools in Anführungszeichen, die durch Kommas getrennt sind.
    
    Beispiel:
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. Bei Verwendung der Suchbefehle können Pools ein beliebiger Pool in Ihrer Bereitstellung sein, z. B. Front-End-Pools, Edgepools, Serverpools für beständigen Chat oder andere, die in Ihrer Bereitstellung als Pool definiert sind.
    
    Beispiel:
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a>So führen Sie eine Suche mithilfe der Zeitparameter aus

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell.**
    
2. Standardmäßig beträgt die Anfangszeit für die zeitspezifischen Parameter einer Suche 25 Minuten vor fünf Minuten nach dem Zeitpunkt, zu dem Sie die Suche starten. Wenn wir also um 16:00:00 Uhr suchen, wird die Startzeit der Suche als 15:35:00 Uhr bis 16:05:00 Uhr angezeigt. Wenn Sie 60 Minuten oder 3 Stunden vor der aktuellen Zeit suchen müssen, verwenden Sie den Parameter "-StartTime", und legen Sie die Datums- und Uhrzeitzeichenfolge fest, um die Uhrzeit anzugeben, zu der die Suche beginnen soll. 
    
    Wenn Sie z. B. "-StartTime" und "-EndTime" zum Definieren eines Uhrzeit- und Datumsbereichs verwenden, können Sie eine Suche zwischen 08:00 Uhr und 9:00 Uhr am 20.11.2012 in Ihrem Pool definieren. Sie können den Ausgabepfad angeben, sodass die Ergebnisse folgendermaßen in eine Datei namens "c:\logfile.txt" geschrieben werden:
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> Die angegebene Uhrzeit- und Datumszeichenfolge kann "Datumszeit" oder "Uhrzeitdatum" sein. " The command will parse the string and use the appropriate values for date and time and your locale and culture settings on the machine you are running cmdlet from. 
  
3. Wenn Sie Protokolle abrufen möchten, die am 20.11.2012 um 11:00:00 Uhr beginnen, definieren Sie "-StartTime". Der Standardzeitbereich für die Suche beträgt 30 Minuten, es sei denn, Sie definieren eine bestimmte -EndTime. Die Suche gibt Protokolle der festgelegten Computer oder Pools aus dem Zeitraum zwischen 11:00 Uhr bis 11:30 Uhr zurück.
    
Beispiel:
    
  ```PowerShell
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. Um eine Suche von Protokollen innerhalb eines bestimmten Zeitraums durchzuführen, definieren Sie "-StartTime" und "-EndTime". Sie benötigen Protokolle für den Zeitraum zwischen 13 und 14:45 Uhr auf dem Computer "edge01.contoso.net". 
    
Beispiel:
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>So führen Sie mithilfe weiterer Kriterien und Abgleichungsoptionen eine erweiterte Suche aus

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell.**
    
2. Geben Sie zum Ausführen eines Befehls zum Erfassen von Ablaufverfolgungen für bestimmte Komponenten Folgendes ein:
    
   ```PowerShell
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

Beispiel:
    
  ```PowerShell
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

Die Suche gibt alle Protokolleinträge zurück, die Ablaufverfolgungskomponenten für SIPStack, S4 und UserServices für alle Computer und Pools in Ihrer Bereitstellung in den letzten 30 Minuten enthalten.
    
3. Geben Sie Folgendes ein, um die Suche mit denselben Komponenten auf ihren Front-End-Pool mit dem Namen pool01.contoso.net zu beschränken:
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. Die Standardsuchlogik für Befehle mit mehreren Parametern besteht darin, das logische "Oder" mit den einzelnen definierten Parametern zu verwenden. Sie können dieses Verhalten ändern, indem Sie den Parameter **"-MatchAll"** angeben. Geben Sie dazu Folgendes ein:
    
   ```PowerShell
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. Wenn Ihre Szenarien für die ständige Ausführung festgelegt sind (wie AlwaysOn) oder wenn Sie ein langwieriges Szenario festgelegt haben, werden Protokolle möglicherweise vom lokalen Computer auf die Dateifreigabe verschoben. Sie legen die Dateifreigabe  mithilfe des Parameters "CacheFileNetworkFolder" fest, um mithilfe von "New-CsClsConfiguration" eine neue Konfiguration zu erstellen oder mithilfe von "Set-CsClsConfiguration" eine vorhandene Konfiguration zu ändern. Soll die Suche die Dateifreigabe in der Auflistung der zu durchsuchenden Protokolle nicht durchsuchen, verwenden Sie den Parameter "SkipNetworkLogs" folgendermaßen:
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a>Lesen von Erfassungsprotokollen aus dem zentralisierten Protokollierungsdienst

Sie erkennen den tatsächlichen Vorteil des zentralisierten Protokollierungsdiensts, nachdem Sie die Suche ausgeführt haben, und Sie haben eine Datei, die Sie verwenden können, um ein gemeldetes Problem nachzuverfolgen. Es gibt eine Reihe von Möglichkeiten, die Datei zu lesen. Die Ausgabedatei weist ein Standardtextformat auf, und Sie können Notepad.exe oder andere Programme verwenden, mit denen Sie eine Textdatei öffnen und lesen können. Bei größeren Dateien und komplexeren Problemen können Sie ein Tool wie Snooper.exe verwenden, mit dem die Protokollierungsausgabe des zentralisierten Protokollierungsdiensts gelesen und analysiert werden kann. Snooper ist in den Debugtools enthalten, die als separater Download verfügbar sind. Sie können die Debugtools hier herunterladen: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257) . Wenn Sie die Debugtools installieren, werden keine Abkürzungen und Menüelemente erstellt. Öffnen Sie nach der Installation der Debugtools Windows Explorer, ein Befehlszeilenfenster oder Skype for Business Server Verwaltungsshell, und wechseln Sie zum Verzeichnis (Standardspeicherort) C:\Program Files\Skype for Business Server 2015\Debugging Tools. Doppelklicken Sie auf Snooper.exe oder geben Sie Snooper.exe ein, und drücken Sie dann die EINGABETASTE, wenn Sie die Befehlszeile oder Skype for Business Server Verwaltungsshell verwenden.
  
> [!IMPORTANT]
> In diesem Thema geht es nicht um Ausführliches und Behandeln von Problembehandlungstechniken. Die Problembehandlung und die Damit umgehenden Prozesse sind ein komplexes Thema. Ausführliche Informationen zur Problembehandlung von Grundlagen und zur Problembehandlung bestimmter Workloads finden Sie im Microsoft Lync Server 2010 Resource Kit-Buch unter [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003) . Die Prozesse und Verfahren gelten weiterhin für Skype for Business Server 2015. 
  
### <a name="to-open-a-log-file-in-snooper"></a>So öffnen Sie eine Protokolldatei in Snooper

1. Um Snooper zu verwenden und Protokolldateien zu öffnen, benötigen Sie Lesezugriff auf die Protokolldateien. Um Snooper zu verwenden und auf die Protokolldateien zuzugreifen, müssen Sie Mitglied der Sicherheitsgruppe "CsAdministrator" oder "CsServerAdministrator" mit rollenbasierter Zugriffssteuerung (Role-Based Access Control, RBAC) oder einer benutzerdefinierten RBAC-Rolle sein, die eine dieser beiden Gruppen enthält. 
    
2. Ändern Sie nach der Installation der Debugtools (LyncDebugTools.msi) das Verzeichnis an den Speicherort von Snooper.exe mit Windows Explorer oder über die Befehlszeile. Standardmäßig befinden sich die Debugtools unter "C:\Programme\Skype for Business Server 2015\Debugtools". Doppelklicken Oder führen Sie Snooper.exe aus.
    
3. Klicken Sie nach dem Öffnen von Snooper mit der rechten Maustaste auf **"Datei",** klicken Sie auf **"OpenFile",** suchen Sie ihre Protokolldateien, wählen Sie eine Datei im Dialogfeld **"Öffnen"** aus, und klicken Sie dann auf **"Öffnen".**
    
4. Die **Ablaufverfolgungsmeldungen** der Protokolldatei werden auf der Registerkarte **"Ablaufverfolgung"** angezeigt. Klicken Sie auf die Registerkarte **"Nachrichten",** um den Nachrichteninhalt der erfassten Ablaufverfolgungen anzuzeigen.
    
### <a name="to-display-a-call-flow-diagram"></a>So zeigen Sie ein Anrufflussdiagramm an

1. Um Snooper zu verwenden und Protokolldateien zu öffnen, benötigen Sie Lesezugriff auf die Protokolldateien. Um Snooper zu verwenden und auf die Protokolldateien zuzugreifen, müssen Sie Mitglied der Rollenbasierten Zugriffssteuerungsgruppen (Role-Based Access Control, RBAC) "CsAdministrator" oder "CsServerAdministrator" oder einer benutzerdefinierten RBAC-Rolle sein, die eine dieser beiden Gruppen enthält.
    
2. Öffnen Sie eine Protokolldatei, und klicken Sie auf die Registerkarte **Nachrichten,** wählen Sie eine Unterhaltung in der Nachrichtenansicht aus, oder wählen Sie eine Ablaufverfolgungskomponente auf der Registerkarte **"Ablaufverfolgung"** aus.
    
3. Klicken Sie auf **Anruf Flow**.
    
> [!NOTE]
> Wenn Sie auf eine Nachricht oder Ablaufverfolgung klicken, die nicht Teil eines Anrufflusses ist, wird das Diagramm nicht angezeigt, und unten in Snooper wird eine Statusmeldung mit der Meldung "Diese Nachricht ist nicht für callfow berechtigt" angezeigt. Wählen Sie eine andere Nachricht oder Ablaufverfolgung aus, und der Anruffluss wird angezeigt, wenn die Nachricht oder Ablaufverfolgung Teil eines Anrufflusses ist. 
  
4. Navigieren Sie durch die Nachrichten oder ablaufverfolgungslinien, und notieren Sie, ob das Anrufflussdiagramm aktualisiert oder geändert wird, um ein neues Diagramm anzuzeigen.
    
5. Zeigen Sie auf Elemente, um Informationen zu Anrufnachrichten, Endpunkten und anderen Komponenten abzurufen.
