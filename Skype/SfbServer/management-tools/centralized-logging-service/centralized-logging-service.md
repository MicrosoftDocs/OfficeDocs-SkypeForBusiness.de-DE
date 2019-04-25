---
title: Zentralisierter Protokollierungsdienst in Skype for Business 2015
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
description: 'Zusammenfassung: Informationen Sie zu den Komponenten und Konfigurationseinstellungen für die zentralisierte Protokollierungsdienst in Skype für Business Server 2015.'
ms.openlocfilehash: 6f1766e97c318a11095aa2f064cd09a0785c1562
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217590"
---
# <a name="centralized-logging-service-in-skype-for-business-2015"></a>Zentralisierter Protokollierungsdienst in Skype for Business 2015
 
**Zusammenfassung:** Informationen Sie zu den Komponenten und Konfigurationseinstellungen für die zentralisierte Protokollierungsdienst in Skype für Business Server 2015.
  
Der zentralisierte Protokollierungsdienst können: 
  
- Starten Sie oder beenden Sie die Protokollierung für einen oder mehrere Computer und Pools mit einem einzigen Befehl von einem zentralen Ort.
    
- Suche protokolliert für einen oder mehrere Computer und Pools. Sie können die Suche zum Zurückgeben von aller Protokolle auf allen Computern Anpassung und kürzeren Ergebnisse zurückzugeben.
    
- Konfigurieren Sie die Protokollierungssitzungen wie folgt:
    
  - Definieren Sie ein **Szenario** oder verwenden Sie ein Standardszenario. Ein Szenario in Centralized Logging Service besteht des Bereichs (global oder Standort), Name eines Szenarios, um den Zweck der Browser und eine oder mehrere Anbieter zu identifizieren. Sie können das Standardszenario und eine definierte Szenario auf einem Computer zu einem bestimmten Zeitpunkt ausführen.
    
  - Sie können einen vorhandenen Anbieter verwenden oder einen neuen Anbieter erstellen. Aprovider definiert, was die protokollierungssitzung erfasst, welche Detailebene, welche Komponenten zu verfolgen und welche Flags angewendet werden.
    
    > [!TIP]
    >  Wenn Sie mit OCSLogger vertraut sind, bezieht sich die Termproviders auf die Auflistung der **Komponenten** (beispielsweise S4, SIPStack), eine **logging Type** (beispielsweise WPP, EventLog oder IIS Logfile), eine **Protokollierungsstufe** (beispielsweise alle, ausführliches, Debuggen) , und die **Kennzeichen** (z. B. TF_COMPONENT, TF_DIAG). Diese Elemente werden im-Anbieter (Windows PowerShell-Variable) definiert und dem Befehl Centralized Logging Service übergeben.
  
  - Konfigurieren von Protokollen für bestimmte Computer und Pools.
    
  - Definieren Sie den Bereich der Protokollierungssitzung unter Verwendung der Optionen **Standort** (Ausführung der Protokollierungsaufzeichnung erfolgt nur auf Computern an diesem Standort) bzw. **Global** (Ausführung der Protokollierungsaufzeichnung erfolgt auf allen Computern in der Bereitstellung).
    
Der zentralisierte Protokollierungsdienst ist ein leistungsstarkes Tool zur Problembehandlung bei Problemen große oder kleine, von Ursachenanalyse zu Leistungsproblemen. Alle Beispiele der Skype für Business Server-Verwaltungsshell verwenden. Hilfe für das Befehlszeilentool durch das Tool selbst bereitgestellt, aber es ist eine begrenzte Auswahl von Funktionen, die Sie über die Befehlszeile ausführen können. Skype für Business Server-Verwaltungsshell verwenden, haben Sie Zugriff auf einen größeren und umfassender konfigurierbar Satz von Features, damit die erste Wahl immer sein sollte. 
  
## <a name="logging-service-components"></a>Komponenten des Protokollierungsdiensts

 Der zentralisierte Protokollierungsdienst führt auf allen Servern in Ihrer Bereitstellung und besteht aus den folgenden Agents und Dienste:
  
- Zentralisierte Protokollierung-Agent-Dienst ClsAgent ausgeführt auf jedem Computer mit Skype für Business Server bereitgestellt wird. Sie hört ( **50001 50003 TCP**-Ports) für Steuerbefehle zwischen ClsController über WCF und Antworten an den Controller sendet. Er verwaltet Log-Sitzungen (Starten/Beenden/aktualisieren) und durchsucht Protokolle. Außerdem führt Wartungsaufgaben Vorgänge wie das Protokoll Archivierung und löscht ein. 
    
- Zentralisierte Protokollierung Service-Controller-Cmdlets die Skype für Business Server-Verwaltungsshell starten, anhalten, Flush und Suche Befehle an die ClsAgent gesendet. Wenn Search-Befehle gesendet werden, sind diese Protokolle an die ClsControllerLib.dll zurückgegeben und aggregiert. Der Controller Befehle an den Agent sendet, erhält den Status der Befehle und wie es von allen Agents auf einem beliebigen Computer in den Suchbereich zurückgegeben und die Protokolldaten in einen sinnvollen und sortierte Ausgabe Satz aggregiert die Suche Protokolldateidaten verwaltet. Die Informationen in den folgenden Themen konzentriert sich auf die Skype für Business Server-Verwaltungsshell verwenden.
    
**Kommunikation zwischen ClsController und ClsAgent**

![Beziehung zwischen CLSController und CLSAgent.](../../media/Ops_CLS_Architecture.jpg)
  
Sie Befehle mithilfe der Windows Server-Befehlszeilenschnittstelle oder die Skype für die Business Server-Verwaltungsshell. Die Befehle werden auf dem Computer ausgeführt, bei dem Sie angemeldet sind, und an den lokalen ClsAgent oder an die anderen Computer und Pools in Ihrer Bereitstellung gesendet.
  
ClsAgent verwaltet eine Indexdatei aller .CACHE-Dateien, die auf dem lokalen Computer vorhanden sind. ClsAgent ordnet diese so zu, dass sie, entsprechend der Definition der Option „CacheFileLocalFolders“, gleichmäßig auf Volumes verteilt sind und nie mehr als 80 % eines Volumes belegen (der lokale Cachespeicherort und der Prozentsatz sind mit dem Cmdlet **Set-CsClsConfiguration** konfigurierbar). ClsAgent ist außerdem für die Cacheablaufzeiten alter gecachter Ereignisablaufprotokolldateien (ETL-Dateien) vom lokalen Computer zuständig. Nach zwei Wochen (der Zeitrahmen kann mit dem Cmdlet**Set-CsClsConfiguration** konfiguriert werden) werden diese Dateien in eine Dateifreigabe kopiert und vom lokalen Computer gelöscht. Ausführliche Informationen finden Sie unter [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps). Wenn eine Suchanfrage empfangen wird, werden die Suchkriterien verwendet, um die gecachten ETL-Dateien auszuwählen und die Suche anhand der Werte in dem vom Agent geführten Index durchzuführen.
  
> [!NOTE]
> Dateien, die vom lokalen Computer in die Dateifreigabe verschoben wurden, können von ClsAgent durchsucht werden. Sobald ClsAgent die Dateien in die Dateifreigabe verschiebt, werden die Cacheablaufzeiten und das Entfernen von Dateien nicht mehr durch ClsAgent verwaltet. Sie sollten daher eine administrative Aufgabe definieren, die die Größe der Dateien in der Dateifreigabe überwacht und diese Dateien löscht oder archiviert. 
  
Die resultierende Protokolldateien gelesen werden und analysiert mithilfe einer Vielzahl von Tools, einschließlich **Snooper.exe** und ein beliebiges Tool, das eine Textdatei, wie etwa **Notepad.exe**lesen kann. Snooper.exe ist Teil der Skype für Business Server 2015-Tools zum Debuggen und steht als [Web herunterladen](https://go.microsoft.com/fwlink/p/?LinkId=285257).
  
Wie OCSLogger der zentralisierte Protokollierungsdienst enthält mehrere Komponenten gegen verfolgen und bietet Optionen Flags, wie TF_COMPONENT und TF_DIAG auswählen. Zentralisierte Protokollierungsdienst behält auch die Ebene Protokollierungsoptionen OCSLogger.
  
Der wichtigste Vorteil der Skype für Business Server-Verwaltungsshell über das Command-Line ClsController ist, konfigurieren und die neue Szenarien für den Einsatz von ausgewählten Anbieter, die das Problem Speicherplatz, benutzerdefinierte Flags und Protokolliergrade abzielen definieren. Die für ClsController verfügbaren Szenarien sind auf die für das Programm definierten Szenarien beschränkt.
  
In früheren Versionen war OCSLogger.exe verfügbar, um Administratoren und Supportmitarbeitern das Erfassen von Nachverfolgungsdateien von Computern in der Bereitstellung zu ermöglichen. OCSLogger hatte bei all seinen Stärken einen Nachteil. Sie konnten damit nur jeweils auf einem Computer Protokolle erfassen. Sie konnten sich bei mehreren Computern anmelden, indem Sie separate Kopien von OCSLogger verwendeten, Sie erhielten jedoch mehrere Protokolle und es gab kein einfaches Verfahren, um die Ergebnisse zusammenzufassen.
  
Wenn ein Benutzer eine Protokollsuche anfordert, ermittelt der ClsController, an welche Computer die Anfrage gesendet werden muss (dies basiert auf den ausgewählten Szenarien). Er bestimmt außerdem, ob die Suche an die Dateifreigabe gesendet werden muss, in der sich die gespeicherten ETL-Dateien befinden. Wenn die Suchergebnisse an den ClsController zurückgegeben werden, fasst der Controller die Ergebnisse zu einem einzigen, zeitlich geordneten Ergebnissatz zusammen, der dem Benutzer angezeigt wird. Benutzer können die Suchergebnisse für weitere Analysen auf ihrem lokalen Computer speichern.
  
Wenn Sie eine Protokollierungssitzung starten, legen Sie Szenarien fest, die sich auf das Problem beziehen, das Sie beheben möchten. Sie können jederzeit zwei Szenarien gleichzeitig ausführen. Eines dieser beiden Szenarien sollte das Szenario „AlwaysOn“ sein. Dieses sollte in Ihrer Bereitstellung immer ausgeführt werden und Informationen von allen Computern, Pools und Komponenten erfassen.
  
> [!IMPORTANT]
> Standardmäßig wird das AlwaysOn-Szenario in Ihrer Bereitstellung nicht ausgeführt. Das Szenario muss explizit gestartet werden. Nach dem Start weiterhin ausgeführt, bis Sie explizit beendet und ausgeführt werden Neustarts der Computer beibehalten. Informationen zum Starten und Beenden von Szenarien finden Sie unter [Starten oder Beenden von CLS Log-Erfassung in Skype für Business Server 2015](start-or-stop-log-capture.md). 
  
Wenn ein Problem auftritt, können Sie ein zweites Szenario starten, das sich auf dieses Problem bezieht. Reproduzieren Sie das Problem und beenden Sie dann die Protokollierung für das zweite Szenario. Beginnen Sie mit der Protokollsuche für das Problem. Die zusammengefassten Protokolle ergeben eine Protokolldatei, die Nachverfolgungsmeldungen von allen Computern des Standort- oder des globalen Bereichs Ihrer Bereitstellung enthält. Wenn die Suche mehr Daten zurückgibt, als Sie analysieren können (meist aufgrund von Störabstände, bei denen das Rauschen zu hoch ist), führen Sie eine weitere Suche mit enger gesteckten Parametern durch. An diesem Punkt können Sie gegebenenfalls auftretende Muster feststellen, die Ihnen helfen, das Problem genauer einzugrenzen. Letztlich finden Sie nach diversen verfeinerten Suchen Daten, die für das Problem relevant sind und die Hauptursache deutlich machen.
  
> [!TIP]
> Wenn ein Problemszenario in Skype für Business Server angezeigt, beginnen Sie, Fragen Sie sich "Was ich bereits über das Problem wissen?" Wenn Sie die Problem Grenzen quantifiziert, können einen Großteil der betrieblichen Entitäten in Skype für Business Server ausgeschlossen werden. 
  
Stellen Sie sich ein Beispielszenario vor, in dem Sie wissen, dass Benutzer bei der Suche nach einem Kontakt keine aktuellen Ergebnisse erhalten. Es ist nicht sinnvoll suchen Sie nach Problemen in die Media-Komponenten, Enterprise-VoIP, Konferenzen und eine Reihe von anderen Komponenten. Was Sie nicht wissen, ist, wo das Problem tatsächlich auftritt: auf dem Client oder auf dem Server? Kontakte werden aus Active Directory mithilfe der Benutzerreplikationsdienst erfasst und an den Client über den Adressbuchserver (ABServer) geliefert. Die Ausführung von ABServer Ruft die Updates aus der RTC-Datenbank (wobei geschrieben haben Benutzerreplikationsdienst sie) und sammelt in Offlineadressbuch-Dateien, standardmäßig - 1:30 Uhr. Die Skype für Business Server-Clients rufen Sie das neue Adressbuch nach einem zufälligen Zeitplan ab. Da Sie kennen die Funktionsweise des Prozesses vertraut, können Sie auf ein Problem im Zusammenhang mit Daten aus Active Directory der Benutzerreplikationsdienst die Ausführung von ABServer nicht abrufen und Erstellen der Offlineadressbuch-Dateien oder die Clients nicht erfasst wird die Suche für die mögliche Ursache reduzieren. Herunterladen der Adressbuchdatei.
  
## <a name="current-configuration"></a>Aktuelle Konfiguration

Der zentralisierte Protokollierungsdienst wird so konfiguriert, dass definieren, was der Protokollierungsdienst zu sammeln, wie es sammelt, wobei aus erfasst und was sind die Parameter vorgesehen. Sie definieren diese Einstellungen global (d. h. für die gesamte Bereitstellung) oder für einen Standort (also einen benannten Standort in Ihrer Bereitstellung). Für jede Protokollierung, die Sie definieren, werden die Einstellungen verwendet, die jeweils für die von Ihnen für Befehle zum Starten, Beenden, Leeren und Durchsuchen von Protokollen verwendete Identität geeignet sind.
  
### <a name="to-display-the-current-centralized-logging-service-configuration"></a>Um die aktuelle Konfiguration der zentralisierte Protokollierungsdienst anzuzeigen.

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
   ```
   Get-CsClsConfiguration
   ```

    > [!TIP]
    > Sie können beschränken oder Erweitern Sie den Bereich der Konfigurationseinstellungen, die durch die Definition zurückgegeben werden `-Identity` und einen Bereich, z. B. "Site: Redmond", um nur die CsClsConfiguration für den Standort "Redmond" zurückzugeben. Wenn Sie Details zu einem bestimmten Teil der Konfiguration möchten, können Sie die Ausgabe in eine andere Windows PowerShell-Cmdlet umleiten. Angenommen, um Details zu den in der Konfiguration für den Standort "Redmond" definierten Szenarien erhalten möchten, geben Sie Folgendes ein:`Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandProperty Scenarios`
  
     ![Beispielausgabe von "Get-csclsconfiguration".](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
    Das Ergebnis des Cmdlets zeigt die aktuelle Konfiguration des Centralized Logging Service.
    
|**Konfigurationseinstellung**|**Beschreibung**|
|:-----|:-----|
|**Identity** <br/> |Identifiziert den Bereich und den Namen dieser Konfiguration. Es gibt nur eine globale Konfiguration sowie eine Konfiguration pro Standort.  <br/> |
|**Scenarios** <br/> |Auflistung aller Szenarien, die für diese Konfiguration definiert sind.  <br/> |
|**SearchTerms** <br/> |Definierte Suchbegriffe für die Konfiguration. Office 365, nicht lokalen Bereitstellungen.  <br/> |
|**SecurityGroups** <br/> |Definierte Sicherheitsgruppen, die steuern, welche Mitglieder von Sicherheitsgruppen Computer basierend auf dem Standort, an dem sie sich befinden, anzeigen können. In diesem Kontext-Website ist die Website gemäß Definition im Topologie-Generator.  <br/> |
|**Regions** <br/> |Definierte Regionen werden verwendet, um Sicherheitsgruppen zu einer Region zusammenzufassen, beispielsweise EMEA.  <br/> |
|**EtlFileRolloverSizeMB** <br/> |Dieser Parameter gibt die maximale Größe der Protokolldatei vor der Erstellung einer neuen ETL-Datei (Event Trace Log, Ereignis-Ablaufverfolgungsprotokoll) an. Wenn die definierte Größe erreicht ist, wird eine neue Protokolldatei erstellt, auch wenn die in EtlFileRolloverMinutes festgelegte maximale Zeit noch nicht erreicht wurde.  <br/> |
|**EtlFileRolloverMinutes** <br/> |Die definierte maximale Zeitspanne in Minuten, die für ein Protokoll verstreichen kann, bevor eine neue ETL-Datei erstellt wird. Wenn der Timer abläuft, wird eine neue Protokolldatei erstellt, auch wenn die in EtlFileRolloverSizeMB festgelegte maximale Größe noch nicht erreicht wurde.  <br/> |
|**TmfFileSearchPath** <br/> |Speicherort, an dem nach den Formatdateien für Ablaufverfolgungsmeldungen gesucht wird.  <br/> |
|**CacheFileLocalFolders** <br/> |Definierter Pfad zu dem Speicherort, an dem Cachedateien auf Computer geschrieben werden. CLSAgent schreibt die Cachedatei und wird im Kontext des Netzwerkdiensts ausgeführt. In diesem Fall wird %TEMP% zu %WINDIR%\ServiceProfiles\NetworkService\AppData\Local erweitert. Standardmäßig werden Cache- und Protokolldateien in dasselbe Verzeichnis geschrieben.  <br/> |
|**CacheFileNetworkFolder** <br/> |Sie können einen UNC-Pfad (Universal Naming Convention) definieren, um die Cachedateien während Protokollierungsvorgängen zu empfangen.  <br/> |
|**CacheFileLocalRetentionPeriod** <br/> |Definiert als die Höchstdauer in Tagen, für die Cachedateien beibehalten werden.  <br/> |
|**CacheFileMaxDiskUsage** <br/> |Definiert als der prozentuale Anteil des Speicherplatzes, der von den Cachedateien verwendet werden kann.  <br/> |
|**ComponentThrottleLimit** <br/> |Definiert als die Höchstzahl an Ablaufverfolgungen pro Sekunde, die eine Komponente erzeugen kann, bevor der automatische Drosselbegrenzer ausgelöst wird.  <br/> |
|**ComponentThrottleSample** <br/> |Anzahl der möglichen Überschreitungen von ComponentThrottleLimit in 60 Sekunden.  <br/> |
|**MinimumClsAgentServiceVersion** <br/> |Die mindestens erforderliche Version des CLSAgent, die ausgeführt werden kann. Dieses Element ist für Office 365 vorgesehen.  <br/> |
   

