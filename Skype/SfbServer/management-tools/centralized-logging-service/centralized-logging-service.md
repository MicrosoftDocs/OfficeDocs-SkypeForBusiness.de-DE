---
title: Zentraler Protokollierungsdienst in Skype for Business 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
description: 'Zusammenfassung: Informationen zu den Dienstkomponenten und Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015.'
ms.openlocfilehash: 7cc49d258011334d7c72bca3f55d5f83ae5d06af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098871"
---
# <a name="centralized-logging-service-in-skype-for-business-2015"></a>Zentraler Protokollierungsdienst in Skype for Business 2015
 
**Zusammenfassung:** Erfahren Sie mehr über die Dienstkomponenten und Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015.
  
Der zentralisierte Protokollierungsdienst kann: 
  
- Starten oder beenden Sie die Protokollierung auf einem oder mehreren Computern und Pools mit einem einzelnen Befehl von einem zentralen Speicherort aus.
    
- Suchprotokolle auf einem oder mehreren Computern und Pools. Sie können die Suche so anpassen, dass alle Protokolle auf allen Computern oder präzisere Ergebnisse zurückgeben.
    
- Konfigurieren Sie die Protokollierungssitzungen wie folgt:
    
  - Definieren Sie ein **Szenario**, oder verwenden Sie ein Standardszenario. Ein Szenario im zentralisierten Protokollierungsdienst besteht aus Bereich (global oder Standort), einem Szenarionamen zum Identifizieren des Zwecks des Szenarios und einem oder mehreren Anbietern. Sie können das Standardszenario und ein definiertes Szenario jederzeit auf einem Computer ausführen.
    
  - Sie können einen vorhandenen Anbieter verwenden oder einen neuen Anbieter erstellen. Aprovider definiert, was die Protokollierungssitzung erfasst, welche Detailebene, welche Komponenten nachverfolgt werden sollen und welche Kennzeichen angewendet werden.
    
    > [!TIP]
    >  Wenn Sie mit OCSLogger vertraut sind, beziehen sich  die Ausdrucksprovider auf die Auflistung von Komponenten (z. B. S4, SIPStack), einen Protokollierungstyp **(z.** B. WPP, EventLog oder IIS-Protokolldatei), eine Ablaufverfolgungsebene **(z.** B. Alle, ausführlich, Debuggen) und Flags **(z.** B. TF_COMPONENT, TF_DIAG). Diese Elemente werden im Anbieter (eine Windows PowerShell) definiert und an den Befehl Zentralisierter Protokollierungsdienst übergeben.
  
  - Konfigurieren von Protokollen für bestimmte Computer und Pools
    
  - Definieren Sie den Bereich für die Protokollierungssitzung über die Optionen **Site** (zum Ausführen von Protokollierungsaufzeichnungen nur auf Computern an diesem Standort) oder **global** (zum Ausführen von Protokollierungsaufzeichnungen auf allen Computern in der Bereitstellung).
    
Der zentralisierte Protokollierungsdienst ist ein leistungsstarkes Problembehandlungstool für große oder kleine Probleme, von der Analyse der Stammursache bis zu Leistungsproblemen. Alle Beispiele werden mithilfe der Skype for Business Server-Verwaltungsshell gezeigt. Hilfe für das Befehlszeilentool wird über das Tool selbst bereitgestellt, es gibt jedoch eine begrenzte Anzahl von Funktionen, die Sie über die Befehlszeile ausführen können. Durch die Verwendung der Skype for Business Server-Verwaltungsshell haben Sie Zugriff auf einen viel größeren und viel konfigurierbareren Satz von Features, sodass dies immer Ihre erste Wahl sein sollte. 
  
## <a name="logging-service-components"></a>Protokollierungsdienstkomponenten

 Der zentralisierte Protokollierungsdienst wird auf allen Servern in Ihrer Bereitstellung ausgeführt und besteht aus den folgenden Agents und Diensten:
  
- Centralized Logging Service Agent ClsAgent wird auf jedem Computer ausgeführt, auf dem Skype for Business Server bereitgestellt ist. Es lauscht ( auf Ports **TCP 50001-50003**) auf Befehle von ClsController über WCF und sendet Antworten zurück an den Controller. Es verwaltet Protokollsitzungen (Start/Stopp/Update) und durchsucht Protokolle. Es führt auch Housekeeping-Vorgänge wie Protokollarchivierung und -bereinigungen durch. 
    
- Cmdlets des zentralen Protokollierungsdienstcontrollers Die Skype for Business Server-Verwaltungsshell sendet Die Befehle Start, Stop, Flush und Search an den ClsAgent. Wenn Suchbefehle gesendet werden, werden die resultierenden Protokolle an die ClsControllerLib.dll und aggregiert. Der Controller sendet Befehle an den Agent, empfängt den Status dieser Befehle und verwaltet die Suchprotokolldateidaten, wie sie von allen Agents auf einem beliebigen Computer im Suchbereich zurückgegeben werden, und aggregiert die Protokolldaten in einem aussagekräftigen und geordneten Ausgabesatz. Die Informationen in den folgenden Themen konzentrieren sich auf die Verwendung der Skype for Business Server-Verwaltungsshell.
    
**Kommunikation zwischen ClsController und ClsAgent**

![Beziehung zwischen CLSController und CLSAgent.](../../media/Ops_CLS_Architecture.jpg)
  
Sie geben Befehle über die Windows Server-Befehlszeilenschnittstelle oder die Skype for Business Server-Verwaltungsshell aus. Die Befehle werden auf dem Computer ausgeführt, bei dem Sie angemeldet sind, und an den lokalen ClsAgent oder an die anderen Computer und Pools in Ihrer Bereitstellung gesendet.
  
ClsAgent verwaltet eine Indexdatei aller .CACHE-Dateien, die auf dem lokalen Computer vorhanden sind. ClsAgent ordnet diese so zu, dass sie, entsprechend der Definition der Option "CacheFileLocalFolders", gleichmäßig auf Volumes verteilt sind und nie mehr als 80 % eines Volumes belegen (der lokale Cachespeicherort und der Prozentsatz sind mit dem **Set-CsClsConfiguration**-Cmdlet konfigurierbar). ClsAgent ist außerdem für die Cacheablaufzeiten alter gecachter Ereignisablaufprotokolldateien (.etl) vom lokalen Computer zuständig. Nach zwei Wochen (der Zeitrahmen kann mit dem **Set-CsClsConfiguration**-Cmdlet konfiguriert werden) werden diese Dateien in eine Dateifeigabe kopiert und vom lokalen Computer gelöscht. Ausführliche Informationen finden Sie unter [Set-CsClsConfiguration](/powershell/module/skype/set-csclsconfiguration?view=skype-ps). Wenn eine Suchanfrage empfangen wird, werden die Suchkriterien verwendet, um die gecachten .etl-Dateien auszuwählen und die Suche anhand der Werte in dem vom Agent geführten Index durchzuführen.
  
> [!NOTE]
> Dateien, die vom lokalen Computer in die Dateifreigabe verschoben wurden, können durch ClsAgent durchsucht werden. Sobald ClsAgent die Dateien in die Dateifreigabe verschiebt, werden die Cacheablaufzeiten und das Entfernen von Dateien nicht mehr durch ClsAgent verwaltet. Sie sollten daher eine administrative Aufgabe definieren, die die Größe der Dateien in der Dateifreigabe überwacht und diese löscht oder archiviert. 
  
Die resultierenden Protokolldateien können mit einer Vielzahl von Tools gelesen und analysiert werden, einschließlich **Snooper.exe** und jedem Tool, das eine Textdatei lesen **kann,** z. B.Notepad.exe. Snooper.exe ist Teil der Skype for Business Server 2015-Debugtools und steht als [Webdownload zur Verfügung.](https://go.microsoft.com/fwlink/p/?LinkId=285257)
  
Wie OCSLogger verfügt der zentralisierte Protokollierungsdienst über mehrere Komponenten, die nachverfolgt werden müssen, und bietet Optionen zum Auswählen von Flags, z. B. TF_COMPONENT und TF_DIAG. Der zentralisierte Protokollierungsdienst behält auch die Protokollierungsebenenoptionen von OCSLogger bei.
  
Der wichtigste Vorteil bei der Verwendung der Skype for Business Server-Verwaltungsshell gegenüber dem Befehlszeilen-ClsController ist, dass Sie neue Szenarien mithilfe ausgewählter Anbieter konfigurieren und definieren können, die auf den Problembereich, benutzerdefinierte Flags und Protokollierungsebenen zielen. Die für ClsController verfügbaren Szenarien sind auf die für das Programm definierten Szenarien beschränkt.
  
In früheren Versionen war OCSLogger.exe verfügbar, um Administratoren und Supportmitarbeitern das Erfassen von Nachverfolgungsdateien von Computern in der Bereitstellung zu ermöglichen. OCSLogger hatte bei all seinen Stärken einen Nachteil. Sie konnten damit nur jeweils auf einem Computer Protokolle erfassen. Sie konnten sich bei mehreren Computern anmelden, indem Sie separate Kopien von OCSLogger verwendeten, Sie erhielten aber mehrere Protokolle und hatten kein einfaches Verfahren, die Ergebnisse zusammenzufassen.
  
Wenn ein Benutzer eine Protokollsuche anfordert, ermittelt der ClsController, an welche Computer die Anfrage gesendet werden muss (dies basiert auf den ausgewählten Szenarien). Er bestimmt außerdem, ob die Suche an die Dateifreigabe gesendet werden muss, in der sich die gespeicherten .etl-Dateien befinden. Wenn die Suchergebnisse an den ClsController zurückgegeben werden, fasst der Controller die Ergebnisse zu einem einzigen, zeitlich geordneten Ergebnissatz zusammen, der an dem Benutzer angezeigt wird. Benutzer können die Suchergebnisse für weitere Analysen auf ihrem lokalen Computer speichern.
  
Wenn Sie eine Protokollierungssitzung starten, legen Sie Szenarien fest, die sich auf das Problem beziehen, das Sie beheben möchten. Sie können jederzeit zwei Szenarien gleichzeitig ausführen. Eines dieser beiden Szenarien sollte das Szenario "AlwaysOn" sein. Dieses sollte in Ihrer Bereitstellung immer ausgeführt werden und Informationen von allen Computern, Pools und Komponenten erfassen.
  
> [!IMPORTANT]
> Standardmäßig wird das AlwaysOn-Szenario in Ihrer Bereitstellung nicht ausgeführt. Sie müssen das Szenario explizit starten. Nachdem sie gestartet wurde, wird sie weiterhin ausgeführt, bis sie explizit beendet wurde, und der Ausführungsstatus wird durch Neustarts der Computer beibehalten. Weitere Informationen zum Starten und Beenden von Szenarien finden Sie unter [Start or stop CLS log capture in Skype for Business Server 2015](start-or-stop-log-capture.md). 
  
Wenn ein Problem auftritt, können Sie ein zweites Szenario starten, das sich auf das Problem bezieht. Reproduzieren Sie das Problem, und beenden Sie dann die Protokollierung für das zweite Szenario. Beginnen Sie für das Problem mit der Protokollsuche. Die zusammengefassten Protokolle ergeben eine Protokolldatei, die Nachverfolgungsmeldungen von allen Computern des Standort- oder des globalen Bereichs Ihrer Bereitstellung enthält. Wenn die Suche mehr Daten zurückgibt, als Sie analysieren können (meist Störabstände, bei denen das Rauschen zu hoch ist), führen Sie eine weitere Suche mit enger gesteckten Parametern durch. An diesem Punkt können Sie gegebenenfalls auftretende Muster feststellen, die Ihnen helfen, das Problem genauer einzugrenzen. Letztlich finden Sie nach diversen verfeinerten Suchen Daten, die für das Problem relevant sind und die Hauptursache deutlich machen.
  
> [!TIP]
> Wenn ein Problemszenario in Skype for Business Server vorgestellt wird, fragen Sie sich zunächst: "Was weiß ich bereits über das Problem?" Wenn Sie die Problemgrenzen quantifizieren, können Sie einen Großteil der operativen Entitäten in Skype for Business Server eliminieren. 
  
Stellen Sie sich ein Beispielszenario vor, in dem Sie wissen, dass Benutzer bei der Suche nach einem Kontakt keine aktuellen Ergebnisse erhalten. Es macht keinen Sinn, nach Problemen in den Medienkomponenten, Enterprise-VoIP, Konferenzen und einer Reihe anderer Komponenten zu suchen. Was Sie nicht wissen, ist, wo das Problem tatsächlich auftritt: auf dem Client oder auf dem Server? Kontakte werden vom Benutzerreplikatetor aus Active Directory gesammelt und über den Adressbuchserver (Address Book Server, ABServer) an den Client übermittelt. Der ABServer ruft seine Updates aus der RTC-Datenbank ab (in der der Benutzerreplikatetor sie geschrieben hat) und sammelt sie standardmäßig - 1:30 Uhr - in Adressbuchdateien. Die Skype for Business Server-Clients rufen das neue Adressbuch nach einem randomisierten Zeitplan ab. Da Sie wissen, wie der Prozess funktioniert, können Sie die Suche nach der potenziellen Ursache für ein Problem im Zusammenhang mit daten, die vom Benutzerreplikatetor aus Active Directory gesammelt werden, den ABServer, der die Adressbuchdateien nicht abruft und erstellt, oder die Clients, die die Adressbuchdatei nicht herunterladen, reduzieren.
  
## <a name="current-configuration"></a>Aktuelle Konfiguration

Der zentralisierte Protokollierungsdienst ist so konfiguriert, dass er definiert, was der Protokollierungsdienst erfassen soll, wie er gesammelt wird, woher er gesammelt wird und welche Protokolleinstellungen es gibt. Sie definieren diese Einstellungen global (d. h. für die gesamte Bereitstellung) oder für einen Standort (d. h. einen benannten Standort in Ihrer Bereitstellung). Für jede Protokollierung, die Sie definieren, werden die Einstellungen verwendet, die jeweils für die von Ihnen für Befehle zum Starten, Beenden, Leeren und Durchsuchen von Protokollen verwendete Identität geeignet sind.
  
### <a name="to-display-the-current-centralized-logging-service-configuration"></a>So zeigen Sie die aktuelle Konfiguration des zentralisierten Protokollierungsdiensts an

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
2. Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
   ```PowerShell
   Get-CsClsConfiguration
   ```

    > [!TIP]
    > Sie können den Bereich der zurückgegebenen Konfigurationseinstellungen ein- oder erweitern, indem Sie einen Bereich definieren, z. B.  `-Identity` "Site:Redmond", um nur die CsClsConfiguration für den Standort "Redmond" zurückzukehren. Wenn Sie Details zu einem bestimmten Teil der Konfiguration wünschen, können Sie die Ausgabe an ein anderes cmdlet Windows PowerShell umleitungen. Geben Sie beispielsweise ein, um Details zu den szenarien zu erhalten, die in der Konfiguration für den Standort "Redmond" definiert sind: `Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandProperty Scenarios`
  
     ![Beispielausgabe von Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
    Das Ergebnis des Cmdlets zeigt die aktuelle Konfiguration des zentralisierten Protokollierungsdiensts an.
    
|**Konfigurationseinstellung**|**Beschreibung**|
|:-----|:-----|
|**Identity** <br/> |Identifiziert den Bereich und den Namen dieser Konfiguration. Es gibt nur eine globale Konfiguration sowie eine Konfiguration pro Standort.  <br/> |
|**Scenarios** <br/> |Auflistung aller Szenarien, die für diese Konfiguration definiert sind.  <br/> |
|**SearchTerms** <br/> |Definierte Suchbegriffe für die Konfiguration. Microsoft 365 oder Office 365, keine lokalen Bereitstellungen.  <br/> |
|**SecurityGroups** <br/> |Definierte Sicherheitsgruppen, die steuern, wer (welche Mitglieder der Sicherheitsgruppen) Computer basierend auf dem Standort, an dem sie sich befinden, anzeigen können. Site ist in diesem Kontext die Im Topologie-Generator definierte Website.  <br/> |
|**Regionen** <br/> |Definierte Regionen werden verwendet, um Sicherheitsgruppen zu einer Region zusammenzufassen, beispielsweise EMEA.  <br/> |
|**EtlFileRolloverSizeMB** <br/> |Der Parameter gibt die maximale Größe der Protokolldatei vor der Erstellung einer neuen ETL-Datei (Event Trace Log, Ereignis-Ablaufverfolgungsprotokoll) an. Wenn die definierte Größe erreicht ist, wird eine neue Protokolldatei erstellt, auch wenn die in EtlFileRolloverMinutes festgelegte maximale Zeit noch nicht erreicht wurde.  <br/> |
|**EtlFileRolloverMinutes** <br/> |Die definierte maximale Zeitspanne in Minuten, die für ein Protokoll verstreichen kann, bevor eine neue ETL-Datei erstellt wird. Wenn der Timer abläuft, wird eine neue Protokolldatei erstellt, auch wenn die in EtlFileRolloverSizeMB festgelegte maximale Größe noch nicht erreicht wurde.  <br/> |
|**TmfFileSearchPath** <br/> |Speicherort, an dem nach den Formatdateien für Ablaufverfolgungsmeldungen gesucht wird.  <br/> |
|**CacheFileLocalFolders** <br/> |Definierter Pfad zu dem Speicherort, an dem Cachedateien auf Computer geschrieben werden. CLSAgent schreibt die Cachedatei und wird im Kontext des Netzwerkdiensts ausgeführt. In diesem Fall wird %TEMP% zu %WINDIR%\ServiceProfiles\NetworkService\AppData\Local erweitert. Standardmäßig werden Cache- und Protokolldateien in dasselbe Verzeichnis geschrieben.  <br/> |
|**CacheFileNetworkFolder** <br/> |Sie können einen UNC-Pfad (Universal Naming Convention) definieren, um die Cachedateien während Protokollierungsvorgängen zu empfangen.  <br/> |
|**CacheFileLocalRetentionPeriod** <br/> |Definiert als die Höchstdauer in Tagen, für die Cachedateien beibehalten werden.  <br/> |
|**CacheFileMaxDiskUsage** <br/> |Definiert als der prozentuale Anteil des Speicherplatzes, der von den Cachedateien verwendet werden kann.  <br/> |
|**ComponentThrottleLimit** <br/> |Definiert als die Höchstzahl an Ablaufverfolgungen pro Sekunde, die eine Komponente erzeugen kann, bevor der automatische Drosselbegrenzer ausgelöst wird.  <br/> |
|**ComponentThrottleSample** <br/> |Anzahl der möglichen Überschreitungen von ComponentThrottleLimit in 60 Sekunden.  <br/> |
|**MinimumClsAgentServiceVersion** <br/> |Die mindestens erforderliche Version des CLSAgent, die ausgeführt werden kann. Dieses Element ist für Microsoft 365 oder Office 365 vorgesehen.  <br/> |
