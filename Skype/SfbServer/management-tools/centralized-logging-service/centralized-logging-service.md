---
title: Zentralisierter Protokollierungsdienst in Skype for Business 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
description: 'Zusammenfassung: erfahren Sie mehr über die Dienstkomponenten und Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015.'
ms.openlocfilehash: a02d2a283716dd01572e0cbd8cccf075b29fd9b8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274513"
---
# <a name="centralized-logging-service-in-skype-for-business-2015"></a>Zentralisierter Protokollierungsdienst in Skype for Business 2015
 
**Zusammenfassung:** Informieren Sie sich über die Dienstkomponenten und Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in Skype for Business Server 2015.
  
Der zentralisierte Protokollierungsdienst kann: 
  
- Starten oder Beenden der Protokollierung auf einem oder mehreren Computern und Pools mit einem einzigen Befehl von einem zentralen Ort aus.
    
- Durchsuchen von Protokollen auf einem oder mehreren Computern und Pools Sie können die Suche so anpassen, dass alle Protokolle auf allen Computern zurückgegeben werden, oder Sie können prägnantere Ergebnisse zurückgeben.
    
- Konfigurieren Sie die Protokollierungssitzungen wie folgt:
    
  - Definieren Sie ein **Szenario** oder verwenden Sie ein Standardszenario. Ein Szenario im zentralisierten Protokollierungsdienst besteht aus dem Bereich (Global oder Website), einem Szenarionamen zur Identifizierung des Zwecks des Szenarios und einem oder mehreren Anbietern. Sie können das Standardszenario und ein bestimmtes Szenario zu einem beliebigen Zeitpunkt auf einem Computer ausführen.
    
  - Sie können einen vorhandenen Anbieter verwenden oder einen neuen Anbieter erstellen. Anbieter definiert, was die Protokollierungssitzung sammelt, welche Detailebene, welche Komponenten nachzuverfolgen und welche Flags angewendet werden.
    
    > [!TIP]
    >  Wenn Sie mit OCSLogger vertraut sind, bezieht sich die termproviders auf die Sammlung von **Komponenten** (beispielsweise S4, SIPStack), **** einen Protokollierungs (beispielsweise WPP, EventLog oder IIS-Protokolldatei), eine **Ablaufverfolgungsebene** (beispielsweise all, Verbose, Debug). und **Flags** (beispielsweise TF_COMPONENT, TF_DIAG). Diese Elemente werden im Anbieter (eine Windows PowerShell-Variable) definiert und an den Befehl "zentralisierter Protokollierungsdienst" übergeben.
  
  - Konfigurieren Sie Protokolle für bestimmte Computer und Pools.
    
  - Definieren Sie den Bereich der Protokollierungssitzung unter Verwendung der Optionen **Standort** (Ausführung der Protokollierungsaufzeichnung erfolgt nur auf Computern an diesem Standort) bzw. **Global** (Ausführung der Protokollierungsaufzeichnung erfolgt auf allen Computern in der Bereitstellung).
    
Der zentralisierte Protokollierungsdienst ist ein leistungsfähiges Tool zur Problembehandlung bei großen oder kleinen Problemen, von der Ursachenanalyse bis zu Leistungsproblemen. Alle Beispiele werden mit der Skype for Business Server-Verwaltungsshell angezeigt. Hilfe wird für das Befehlszeilentool über das Tool selbst bereitgestellt, es gibt jedoch eine begrenzte Anzahl von Funktionen, die Sie über die Befehlszeile ausführen können. Wenn Sie die Skype for Business Server-Verwaltungsshell verwenden, haben Sie Zugriff auf eine viel größere und viel mehr konfigurierbare Gruppe von Features, die immer Ihre erste Wahl sein sollten. 
  
## <a name="logging-service-components"></a>Komponenten des Protokollierungsdiensts

 Der zentralisierte Protokollierungsdienst wird auf allen Servern in Ihrer Bereitstellung ausgeführt und besteht aus den folgenden Agents und Diensten:
  
- Der Agent für zentralisierte Protokollierungsdienste-ClsAgent wird auf jedem Computer ausgeführt, auf dem Skype for Business Server bereitgestellt wird. Sie lauscht (auf Ports **TCP 50001-50003**) für Befehle von ClsController über WCF und sendet Antworten an den Controller zurück. Es verwaltet Protokollsitzungen (Start/Stop/Update) und durchsucht Protokolle. Sie führt auch Housekeeping-Operationen wie Protokoll Archivierung und-Säuberungen durch. 
    
- Cmdlets für zentralisierte Protokollierungsdienst Controller die Skype for Business Server-Verwaltungsshell sendet Start-, Stopp-, Flush-und Suchbefehle an die ClsAgent. Wenn Suchbefehle gesendet werden, werden die resultierenden Protokolle an die ClsControllerLib. dll zurückgegeben und aggregiert. Der Controller sendet Befehle an den Agenten, erhält den Status dieser Befehle und verwaltet die Suchprotokoll Datei-Daten, wie Sie von allen Agents auf einem beliebigen Computer im Suchbereich zurückgegeben werden, und fasst die Protokolldaten in einen aussagekräftigen und geordneten Ausgabesatz zusammen. Die Informationen in den folgenden Themen konzentrieren sich auf die Verwendung der Skype for Business Server-Verwaltungsshell.
    
**Kommunikation zwischen ClsController und ClsAgent**

![Beziehung zwischen CLSController und CLSAgent.](../../media/Ops_CLS_Architecture.jpg)
  
Sie können Befehle über die Windows Server-Befehlszeilenschnittstelle oder über die Skype for Business Server-Verwaltungsshell ausgeben. Die Befehle werden auf dem Computer ausgeführt, bei dem Sie angemeldet sind, und an den lokalen ClsAgent oder an die anderen Computer und Pools in Ihrer Bereitstellung gesendet.
  
ClsAgent verwaltet eine Indexdatei aller .CACHE-Dateien, die auf dem lokalen Computer vorhanden sind. ClsAgent ordnet diese so zu, dass sie, entsprechend der Definition der Option „CacheFileLocalFolders“, gleichmäßig auf Volumes verteilt sind und nie mehr als 80 % eines Volumes belegen (der lokale Cachespeicherort und der Prozentsatz sind mit dem Cmdlet **Set-CsClsConfiguration** konfigurierbar). ClsAgent ist außerdem für die Cacheablaufzeiten alter gecachter Ereignisablaufprotokolldateien (ETL-Dateien) vom lokalen Computer zuständig. Nach zwei Wochen (der Zeitrahmen kann mit dem Cmdlet**Set-CsClsConfiguration** konfiguriert werden) werden diese Dateien in eine Dateifreigabe kopiert und vom lokalen Computer gelöscht. Ausführliche Informationen finden Sie unter [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps). Wenn eine Suchanfrage empfangen wird, werden die Suchkriterien verwendet, um die gecachten ETL-Dateien auszuwählen und die Suche anhand der Werte in dem vom Agent geführten Index durchzuführen.
  
> [!NOTE]
> Dateien, die vom lokalen Computer in die Dateifreigabe verschoben wurden, können von ClsAgent durchsucht werden. Sobald ClsAgent die Dateien in die Dateifreigabe verschiebt, werden die Cacheablaufzeiten und das Entfernen von Dateien nicht mehr durch ClsAgent verwaltet. Sie sollten daher eine administrative Aufgabe definieren, die die Größe der Dateien in der Dateifreigabe überwacht und diese Dateien löscht oder archiviert. 
  
Die resultierenden Protokolldateien können mithilfe einer Vielzahl von Tools, einschließlich **Snooper. exe** und jedem Tool, das eine Textdatei wie **Notepad. exe**lesen kann, gelesen und analysiert werden. Snooper. exe ist Teil der Skype for Business Server 2015 Debug-Tools und steht als [Web-Download](https://go.microsoft.com/fwlink/p/?LinkId=285257)zur Verfügung.
  
Wie OCSLogger verfügt der zentralisierte Protokollierungsdienst über mehrere Komponenten, die verfolgt werden können, und bietet Optionen zum Auswählen von Flags wie TF_COMPONENT und TF_DIAG. Der zentralisierte Protokollierungsdienst behält auch die Protokollierungsstufen Optionen von OCSLogger bei.
  
Der wichtigste Vorteil bei der Verwendung der Skype for Business Server-Verwaltungsshell über die Befehlszeilen-ClsController besteht darin, dass Sie neue Szenarien mit ausgewählten Anbietern konfigurieren und definieren können, die auf den Problembereich, benutzerdefinierte Flags und Protokollierungsebenen ausgerichtet sind. Die für ClsController verfügbaren Szenarien sind auf die für das Programm definierten Szenarien beschränkt.
  
In früheren Versionen war OCSLogger.exe verfügbar, um Administratoren und Supportmitarbeitern das Erfassen von Nachverfolgungsdateien von Computern in der Bereitstellung zu ermöglichen. OCSLogger hatte bei all seinen Stärken einen Nachteil. Sie konnten damit nur jeweils auf einem Computer Protokolle erfassen. Sie konnten sich bei mehreren Computern anmelden, indem Sie separate Kopien von OCSLogger verwendeten, Sie erhielten jedoch mehrere Protokolle und es gab kein einfaches Verfahren, um die Ergebnisse zusammenzufassen.
  
Wenn ein Benutzer eine Protokollsuche anfordert, ermittelt der ClsController, an welche Computer die Anfrage gesendet werden muss (dies basiert auf den ausgewählten Szenarien). Er bestimmt außerdem, ob die Suche an die Dateifreigabe gesendet werden muss, in der sich die gespeicherten ETL-Dateien befinden. Wenn die Suchergebnisse an den ClsController zurückgegeben werden, fasst der Controller die Ergebnisse zu einem einzigen, zeitlich geordneten Ergebnissatz zusammen, der dem Benutzer angezeigt wird. Benutzer können die Suchergebnisse für weitere Analysen auf ihrem lokalen Computer speichern.
  
Wenn Sie eine Protokollierungssitzung starten, legen Sie Szenarien fest, die sich auf das Problem beziehen, das Sie beheben möchten. Sie können jederzeit zwei Szenarien gleichzeitig ausführen. Eines dieser beiden Szenarien sollte das Szenario „AlwaysOn“ sein. Dieses sollte in Ihrer Bereitstellung immer ausgeführt werden und Informationen von allen Computern, Pools und Komponenten erfassen.
  
> [!IMPORTANT]
> Standardmäßig wird das AlwaysOn-Szenario nicht in Ihrer Bereitstellung ausgeführt. Sie müssen das Szenario explizit starten. Nachdem der Vorgang gestartet wurde, wird er weiterhin ausgeführt, bis er explizit angehalten wird, und der Ausführungszustand wird durch einen Neustart der Computer beibehalten. Details zum Starten und Beenden von Szenarien finden Sie unter [starten oder Beenden der CLS-Protokollerfassung in Skype for Business Server 2015](start-or-stop-log-capture.md). 
  
Wenn ein Problem auftritt, können Sie ein zweites Szenario starten, das sich auf dieses Problem bezieht. Reproduzieren Sie das Problem und beenden Sie dann die Protokollierung für das zweite Szenario. Beginnen Sie mit der Protokollsuche für das Problem. Die zusammengefassten Protokolle ergeben eine Protokolldatei, die Nachverfolgungsmeldungen von allen Computern des Standort- oder des globalen Bereichs Ihrer Bereitstellung enthält. Wenn die Suche mehr Daten zurückgibt, als Sie analysieren können (meist aufgrund von Störabstände, bei denen das Rauschen zu hoch ist), führen Sie eine weitere Suche mit enger gesteckten Parametern durch. An diesem Punkt können Sie gegebenenfalls auftretende Muster feststellen, die Ihnen helfen, das Problem genauer einzugrenzen. Letztlich finden Sie nach diversen verfeinerten Suchen Daten, die für das Problem relevant sind und die Hauptursache deutlich machen.
  
> [!TIP]
> Wenn Sie mit einem Problemszenario in Skype for Business Server dargestellt werden, Fragen Sie sich zunächst, was ich bereits über das Problem weiß. Wenn Sie die Problem Grenzen quantifizieren, können Sie einen Großteil der operativen Entitäten in Skype for Business Server eliminieren. 
  
Stellen Sie sich ein Beispielszenario vor, in dem Sie wissen, dass Benutzer bei der Suche nach einem Kontakt keine aktuellen Ergebnisse erhalten. Es hat keinen Punkt, nach Problemen in den Medienkomponenten, Enterprise-VoIP, Konferenz und einer Reihe anderer Komponenten zu suchen. Was Sie nicht wissen, ist, wo das Problem tatsächlich auftritt: auf dem Client oder auf dem Server? Kontakte werden vom Benutzerreplikationsdienst aus Active Directory gesammelt und über den Adressbuch Server (AbServer) an den Client übermittelt. Der ABServer erhält seine Updates aus der RTC-Datenbank (wobei der Benutzer-Replikator Sie geschrieben hat) und sammelt sie standardmäßig in Adressbuchdateien (1:30 am). Die Skype for Business Server-Clients rufen das neue Adressbuch in einem randomisierten Zeitplan ab. Da Sie wissen, wie der Prozess funktioniert, können Sie die Suche nach der potenziellen Ursache für ein Problem reduzieren, das mit Daten zusammenhängt, die von Active Directory vom Benutzerreplikationsdienst erfasst werden, die ABServer die Adressbuchdateien nicht abrufen und erstellen, oder die Clients, die nicht Herunterladen der Adressbuchdatei.
  
## <a name="current-configuration"></a>Aktuelle Konfiguration

Der zentralisierte Protokollierungsdienst ist so konfiguriert, dass er definiert, was der Protokollierungsdienst sammeln soll, wie er erfasst, woher er sammelt und welche Protokolleinstellungen vorgenommen werden. Sie definieren diese Einstellungen global (d. h. für die gesamte Bereitstellung) oder für einen Standort (also einen benannten Standort in Ihrer Bereitstellung). Für jede Protokollierung, die Sie definieren, werden die Einstellungen verwendet, die jeweils für die von Ihnen für Befehle zum Starten, Beenden, Leeren und Durchsuchen von Protokollen verwendete Identität geeignet sind.
  
### <a name="to-display-the-current-centralized-logging-service-configuration"></a>So zeigen Sie die aktuelle Konfiguration für den zentralisierten Protokollierungsdienst an

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:
    
   ```
   Get-CsClsConfiguration
   ```

    > [!TIP]
    > Sie können den Umfang der Konfigurationseinstellungen einschränken oder erweitern, die durch definieren `-Identity` und einen Bereich wie "Website: Redmond" zurückgegeben werden, um nur den CsClsConfiguration für die Website Redmond zurückzugeben. Wenn Sie Details zu einem bestimmten Teil der Konfiguration wünschen, können Sie die Ausgabe in ein anderes Windows PowerShell-Cmdlet übertragen. Wenn Sie beispielsweise Details zu den Szenarien erhalten möchten, die in der Konfiguration für die Website "Redmond" definiert sind, geben Sie Folgendes ein:`Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandProperty Scenarios`
  
     ![Beispielausgabe von Get-CsClsConfiguration](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
    Das Ergebnis des Cmdlets zeigt die aktuelle Konfiguration des zentralen Protokollierungsdiensts an.
    
|**Konfigurationseinstellung**|**Beschreibung**|
|:-----|:-----|
|**Identity** <br/> |Identifiziert den Bereich und den Namen dieser Konfiguration. Es gibt nur eine globale Konfiguration sowie eine Konfiguration pro Standort.  <br/> |
|**Scenarios** <br/> |Auflistung aller Szenarien, die für diese Konfiguration definiert sind.  <br/> |
|**SearchTerms** <br/> |Definierte Suchbegriffe für die Konfiguration. Office 365, keine lokalen Bereitstellungen.  <br/> |
|**SecurityGroups** <br/> |Definierte Sicherheitsgruppen, die steuern, welche Mitglieder von Sicherheitsgruppen Computer basierend auf dem Standort, an dem sie sich befinden, anzeigen können. Website ist in diesem Kontext die Website, wie Sie im Topologie-Generator definiert ist.  <br/> |
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
   

