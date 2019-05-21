---
title: Installieren von Überwachungsberichten in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f417569-b100-442c-ad48-fdd794626cf7
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie einen Dienst installieren, in dem Überwachungsberichte in Skype for Business Server generiert werden.'
ms.openlocfilehash: d17f66a5a500dad19677e51c98a465a2eb6ee87b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282366"
---
# <a name="install-monitoring-reports-in-skype-for-business-server"></a>Installieren von Überwachungsberichten in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie einen Dienst installieren, der Überwachungsberichte in Skype for Business Server generiert.
  
Skype for Business Server-Überwachungsberichte bieten Ihnen eine Fülle von Informationen über die Qualität und Quantität der Kommunikationssitzungen, die in Ihrer Organisation stattfinden. 
  
## <a name="install-monitoring-reports"></a>Installieren von Überwachungsberichten

Überwachungsberichte werden bei der Installation von Skype for Business Server nicht automatisch installiert. Stattdessen müssen Sie die Überwachungsberichte separat und erst nach der Installation von Skype for Business Server auf dem Computer installieren.
  
> [!NOTE]
> Es empfiehlt sich, die Überwachungsberichte auf demselben Computer zu installieren, auf dem auch die Überwachungsdatenbank installiert ist. Somit wird die Zuweisung von Zugriffsberechtigungen für die Berichte vereinfacht: wenn die Überwachungsberichte auf dem Computer installiert sind, der auch als Host für den Überwachungsspeicher fungiert, müssen Sie keine Berechtigungen zuweisen, die einer Datenbank auf dem Computer gestatten, mit Reporting Services zu interagieren, wenn diese auf einem zweiten Computer ausgeführt werden. 
  
Skype for Business Server-Überwachungsberichte enthalten mehr als 30 Berichte, die detaillierte Informationen zu Konferenzen, Peer-to-Peer-Chatsitzungen, Benutzerregistrierungen, der reaktionsgruppenanwendung und vielem mehr bieten. Für die 2013-Version bieten die Skype for Business Server-Überwachungsberichte eine Reihe von Verbesserungen:
  
- **Neue Berichte zur Sprachqualität**. Diese neuen Berichte beinhalten den [Bericht zur Medienqualität in Skype for Business Server, in](../../manage/health-and-monitoring/comparison.md)dem die Qualität zwischen verschiedenen Anrufarten verglichen wird (beispielsweise zwischen kabelgebundenen anrufen und WLAN-anrufen). und den [Bericht "Konferenzteilnahme Zeit" in Skype for Business Server](../../manage/health-and-monitoring/join-time-report.md), der Informationen darüber enthält, wie viel Zeit für die Teilnahme von Benutzern an einer Konferenz erforderlich ist. 
    
- **Verbesserte Berichte zur Analyse und Problembehandlung bei Video- und Anwendungsfreigabesitzungen.** der [Bericht zur Zusammenfassung der Medienqualität in Skype for Business Server](../../manage/health-and-monitoring/summary.md) bietet eine Möglichkeit, Video-und Anwendungsfreigabe Aufrufe zu analysieren, während der [Bericht zur Serverleistung in Skype for Business Server](../../manage/health-and-monitoring/server-performance.md) die Leistung der Server beschreibt, die diese generieren. Anrufe. Die Metriken für die Video-und Anwendungsfreigabe werden jetzt auch über den [Bericht Peer-to-Peer-Sitzungsdetails in Skype for Business Server](../../manage/health-and-monitoring/peer-to-peer-session-detail-report.md) und dem [Konferenz Detailbericht in Skype for Business Server](../../manage/health-and-monitoring/detail-report.md)gemeldet.
    
- **Verbesserte Berichtsleistung**. Dazu gehören kürzere Reaktions- und Datenabrufzeiten sowie eine schnellere und einfachere Navigation durch die Berichte.
    
Weitere Informationen erhalten Sie in der Dokumentation zu den Überwachungsberichten.
  
> [!NOTE]
> Es gibt einen anderen Bericht-QoE-Anruf Detail-Unterbericht, der in Skype for Business Server enthalten ist. Dieser Bericht dient jedoch in erster Linie internen Zwecken und soll nicht direkt aufgerufen werden. 
  
Es gibt zwei Möglichkeiten, Skype for Business Server-Überwachungsberichte zu installieren: Sie können den Skype for Business Server-Bereitstellungs-Assistenten verwenden oder ein Windows PowerShell-Skript verwenden, das in den Skype for Business Server-Installationsdateien enthalten ist. Unabhängig von der Installationsmethode, für die Sie sich entscheiden, müssen Sie zunächst Folgendes sicherstellen:
  
- Sie sind dazu berechtigt, einem Benutzerkonto in der Überwachungsdatenbank eine Datenbankrolle hinzuzufügen.
    
- Sie haben die Rolle „Content Manager“ in SQL Server Reporting Services. Diese Rolle berechtigt Sie dazu, Berichte in SQL Server Reporting Services bereitzustellen.
    
Führen Sie folgende Schritte durch, um die Überwachungsberichte mithilfe des Bereitstellungs-Assistenten zu installieren:
  
1. Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server**-Bereitstellungs-Assistent.
    
2. Klicken Sie im Bereitstellungs-Assistenten auf **Überwachungsberichte bereitstellen**, um den Assistenten für die Bereitstellung der Überwachungsberichte zu starten.
    
3. Stellen Sie im Assistenten für die Bereitstellung der Überwachungsberichte auf der Seite **Überwachungsdatenbank angeben** sicher, dass der vollqualifizierte Domänenname des als Host für Ihren Überwachungsspeicher fungierenden Computers in der Dropdownliste **Überwachungsdatenbank** angezeigt wird. (Sollten Sie über mehrere Überwachungsspeicher verfügen, müssen Sie den entsprechenden Server in der Dropdownliste auswählen.) Stellen Sie sicher, dass die richtige SQL-Serverinstanz im Feld **SQL Server Reporting Services-Instanz (SSRS)** angezeigt wird (z. B. **atl-sql-001.litwareinc.com/archinst**) und klicken Sie anschließend auf **Weiter**.
    
4. Geben Sie auf der Seite **Angeben von Anmeldeinformationen** in das Feld **Benutzername** den Domänennamen und Benutzernamen des Kontos ein, das für den Zugriff auf die Überwachungsberichte verwendet werden soll (z. B. **litwareinc\jansachweh**). Wenn Sie nicht dieses Format (Domäne\Benutzername) verwenden, tritt ein Fehler auf.
    
    Geben Sie das Kennwort des Benutzerkontos in das Feld **Kennwort** ein und klicken Sie auf **Weiter**. Für dieses Konto sind keine speziellen Rechte erforderlich. Dem Konto werden die erforderlichen Anmelde- und Datenbankberechtigungen automatisch erteilt, wenn die Einrichtung abgeschlossen wird.
    
5. Geben Sie auf der Seite **Gruppe mit Lesezugriff angeben** den Namen einer Sicherheitsgruppe an, der der Lesezugriff auf die SQL Server Reporting Services im Benutzergruppenfeld gewährt wird. Wenn Sie beispielsweise einen Lesezugriff auf die Berichte für Administratoren erteilen möchten, geben Sie **RTCUniversalReadOnlyAdmins** ein. Klicken Sie auf **Weiter**.
    
6. Klicken Sie auf der Seite **Befehle ausführen** auf **Fertigstellen**.
    
Überwachungsberichte können auch über die Skype for Business Server-Verwaltungsshell installiert werden, indem Sie das Skript DeployReports. ps1 ausführen. Dieses Windows PowerShell-Skript befindet sich im Ordner \<"Installations\>Speicherort \Skype for Business Server 2015 \ Deployment\Setup". Wenn Sie Überwachungsberichte mit DeployReports. ps1 installieren möchten, geben Sie an der Eingabeaufforderung der Verwaltungsshell einen Befehl ähnlich der folgenden ein:
  
```
C:\Program Files\Skype for Business Server 2015\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"
```

Die im vorstehenden Befehl verwendeten Parameter werden in der folgenden Tabelle beschrieben:
  
|**Parametername**|**Erforderlich**|**Beschreibung**|
|:-----|:-----|:-----|
|storedUserName  <br/> |Ja  <br/> |Benutzerkonto, das für den Zugriff auf den Überwachungsspeicher verwendet wird. Zum Beispiel  <br/> ```-storedUserName "litwareinc\kenmyer"```Dieses Konto muss über die zuvor angegebenen SQL Server-und SQL Server Reporting Services-Berechtigungen verfügen, oder das Skript schlägt fehl.  <br/> |
|storedPassword  <br/> |Ja  <br/> |Kennwort für das Benutzerkonto, das für den Zugriff auf den Überwachungsspeicher verwendet wird.  <br/> |
|readOnlyGroupName  <br/> |Nein  <br/> |Domäne oder lokale Sicherheitsgruppe, deren Mitglieder den Lesezugriff für die Überwachungsberichte erhalten. Beachten Sie, dass das Skript fehlschlägt, wenn die angegebene Gruppe nicht vorhanden ist. Falls Sie diese Berechtigungen später wieder entziehen möchten oder sich dafür entscheiden, anderen Benutzern oder Gruppen Zugriffsberechtigungen zu erteilen, können Sie dies mithilfe des Berichts-Managers der SQL Service Reporting Services tun.  <br/> |
|reportSqlServerInstance  <br/> |Nein  <br/> |SQL Server-Instanz, die als Host für den Berichtsdienst fungiert. Die Berichtsinstanz muss unter Verwendung des vollqualifizierten Domänennamens des Berichtsservers angegeben werden. Beispiel:<br/> ```-reportServerSqlInstance atl-sql-001.litwareinc.com```Wenn dieser Parameter nicht enthalten ist, geht das Skript davon aus, dass die Reporting Services von der gleichen SQL Server-Instanz gehostet werden, die die Überwachungsdatenbank hostet.  <br/> |
|monitoringDatabaseId  <br/> |Nein  <br/> |Dienstidentität für die Überwachungsdatenbank. Sie können die Identitäten für Ihre Überwachungsdatenbanken durch Ausführung des folgenden Befehls zurückgeben:<br/> ```Get-CsService -MonitoringDatabase```|
   
Verwenden Sie, nachdem die Überwachungsberichte installiert wurden, das New-CsReportingConfiguration-Cmdlet, um die URL für den Zugriff auf die Berichte zu konfigurieren. Diese Aufgabe kann über die Skype for Business Server-Verwaltungsshell ausgeführt werden, indem Sie den folgenden Windows PowerShell-Befehl ausführen. Beachten Sie, dass es zwar ratsam, aber nicht erforderlich ist, das HTTPS-Protokoll für die Konfiguration der Berichts-URL zu verwenden:
  
```
New-CsReportingConfiguration -Identity 'service:MonitoringDatabase:atl-sql-001.litwareinc.com' -ReportingURL 'https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST'
```

Im vorangehenden Befehl sollte die ReportingUrl-Eigenschaft auf die von SQL Server 2008 R2 Reporting Services verwendete Berichts-Manager-URL festgelegt sein. Führen Sie zur Ermittlung der Berichts-Manager-URL folgende Schritte auf dem Computer durch, auf dem SQL Server Reporting Services installiert wurde:
  
1. Klicken Sie auf „Start“, „Alle Programme“, „Microsoft SQL Server 2008 R2“, „Konfigurationstools“ und dann auf „Konfigurations-Manager für Reporting Services“.
    
2. Vergewissern Sie sich, dass im Dialogfeld „Konfigurationsverbindung für Reporting Services“ der Name des Reporting Services-Computers im Feld „Servername“ angezeigt wird. Wählen Sie die SQL Server-Instanz in der Dropdownliste „Berichtsserverinstanz“ aus und klicken Sie dann auf „Verbinden“.
    
3. Klicken Sie unter „Konfigurations-Manager für Reporting Services“ auf „Berichts-Manager-URL“. Im Bereich „Berichts-Manager-URL“ sollten mehrere URLs angezeigt werden. Sie können jede dieser URLs als URL für die Berichtsfunktion verwenden. Es sei jedoch nochmals darauf hingewiesen, dass für die ReportingUrl das HTTPS-Protokoll empfohlen wird.
    
Wenn Sie eine Spiegeldatenbank für Ihre Überwachungsdatenbank eingerichtet haben, müssen Sie auch die Überwachungsberichte mit der Spiegeldatenbank verknüpfen. Weitere Informationen finden Sie im Artikel [Zuordnen von Überwachungsberichten zu einer Spiegeldatenbank in Skype for Business Server](monitoring-reports-with-a-mirror-database.md) .
  

