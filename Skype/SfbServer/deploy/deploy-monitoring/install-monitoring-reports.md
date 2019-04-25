---
title: Installieren von Überwachungsberichten in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f417569-b100-442c-ad48-fdd794626cf7
description: 'Zusammenfassung: Erfahren Sie, wie einen Dienst installiert, der Monitoring Server-Berichte in Skype für Business Server generiert wird.'
ms.openlocfilehash: ee500d3440e4211bc42566a7cbdd47ee2cd4cc0e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225504"
---
# <a name="install-monitoring-reports-in-skype-for-business-server"></a>Installieren von Überwachungsberichten in Skype für Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie einen Dienst zu installieren, der Monitoring Server-Berichte in Skype für Business Server generiert.
  
Skype für Business Server Monitoring Reports liefern Ihnen eine Fülle von Informationen über die Qualität und die Menge der kommunikationssitzungen, die in Ihrer Organisation stattfinden. 
  
## <a name="install-monitoring-reports"></a>Installieren von Überwachungsberichten

Monitoring-Berichten werden nicht automatisch installiert, bei der Installation von Skype für Business Server; Stattdessen müssen Sie Überwachungsberichte separat installieren, und nur nach Skype für Business Server auf dem Computer installiert wurde.
  
> [!NOTE]
> Es empfiehlt sich, die Überwachungsberichte auf demselben Computer zu installieren, auf dem auch die Überwachungsdatenbank installiert ist. Somit wird die Zuweisung von Zugriffsberechtigungen für die Berichte vereinfacht: wenn die Überwachungsberichte auf dem Computer installiert sind, der auch als Host für den Überwachungsspeicher fungiert, müssen Sie keine Berechtigungen zuweisen, die einer Datenbank auf dem Computer gestatten, mit Reporting Services zu interagieren, wenn diese auf einem zweiten Computer ausgeführt werden. 
  
Skype für Business Server-Überwachungsberichte enthalten über 30 Berichte bieten ausführliche Informationen zu Konferenzen, Peer-zu-Peer-Sofortnachrichtensitzungen, Benutzer Registrierungen, die reaktionsgruppenanwendung und vieles mehr. Für die Version 2013 Skype für Business Server-Überwachungsberichte eine Reihe von Verbesserungen umfassen:
  
- **Neue Berichte zur Sprachqualität**. Diese neuen Berichte umfassen [Media Quality Comparison Report in Skype für Business Server](../../manage/health-and-monitoring/comparison.md), der zwischen zwei verschiedene Arten von Anrufen (beispielsweise zwischen verkabelten Anrufe und drahtlosen Anrufe); vergleicht und erfordert einen [Konferenzbeitrittszeit in Skype für Business Server](../../manage/health-and-monitoring/join-time-report.md), die Informationen über die Zeitspanne für Benutzer an einer Konferenz teilzunehmen. 
    
- **Verbesserte Berichte zur Analyse und Problembehandlung bei Video- und Anwendungsfreigabesitzungen.** [Media Quality Summary Report in Skype für Business Server](../../manage/health-and-monitoring/summary.md) bietet eine Möglichkeit zum Analysieren von Video und die Anwendungsfreigabe Anrufe, während der [Server Performance Report in Skype für Business Server](../../manage/health-and-monitoring/server-performance.md) die Leistung von Servern, die diese generieren details Anrufe. Video und anwendungsfreigabemetriken werden jetzt auch mithilfe der [Peer-zu-Peer-Sitzungsbericht in Skype für Business Server](../../manage/health-and-monitoring/peer-to-peer-session-detail-report.md) und den [Detaillierten Konferenzbericht in Skype für Business Server](../../manage/health-and-monitoring/detail-report.md)gemeldet.
    
- **Verbesserte Berichtsleistung**. Dazu gehören kürzere Reaktions- und Datenabrufzeiten sowie eine schnellere und einfachere Navigation durch die Berichte.
    
Weitere Informationen erhalten Sie in der Dokumentation zu den Überwachungsberichten.
  
> [!NOTE]
> Einen anderen Bericht - QoE Call Detail Unterbericht - in Skype für Business Server enthalten ist. Dieser Bericht dient jedoch in erster Linie internen Zwecken und soll nicht direkt aufgerufen werden. 
  
Es gibt zwei Methoden, Skype für Business Server-Überwachungsberichte zu installieren: können die Skype für Business Server-Bereitstellungs-Assistenten oder ein Windows PowerShell-Skripts mit der Skype für Business Server-Installationsdateien enthalten können. Unabhängig von der Installationsmethode, für die Sie sich entscheiden, müssen Sie zunächst Folgendes sicherstellen:
  
- Sie sind dazu berechtigt, einem Benutzerkonto in der Überwachungsdatenbank eine Datenbankrolle hinzuzufügen.
    
- Sie haben die Rolle „Content Manager“ in SQL Server Reporting Services. Diese Rolle berechtigt Sie dazu, Berichte in SQL Server Reporting Services bereitzustellen.
    
Führen Sie folgende Schritte durch, um die Überwachungsberichte mithilfe des Bereitstellungs-Assistenten zu installieren:
  
1. Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server**und klicken Sie dann auf **Skype für Business Server-Bereitstellungs-Assistenten**.
    
2. Klicken Sie im Bereitstellungs-Assistenten auf **Überwachungsberichte bereitstellen**, um den Assistenten für die Bereitstellung der Überwachungsberichte zu starten.
    
3. Stellen Sie im Assistenten für die Bereitstellung der Überwachungsberichte auf der Seite **Überwachungsdatenbank angeben** sicher, dass der vollqualifizierte Domänenname des als Host für Ihren Überwachungsspeicher fungierenden Computers in der Dropdownliste **Überwachungsdatenbank** angezeigt wird. (Sollten Sie über mehrere Überwachungsspeicher verfügen, müssen Sie den entsprechenden Server in der Dropdownliste auswählen.) Stellen Sie sicher, dass die richtige SQL-Serverinstanz im Feld **SQL Server Reporting Services-Instanz (SSRS)** angezeigt wird (z. B. **atl-sql-001.litwareinc.com/archinst**) und klicken Sie anschließend auf **Weiter**.
    
4. Geben Sie auf der Seite **Angeben von Anmeldeinformationen** in das Feld **Benutzername** den Domänennamen und Benutzernamen des Kontos ein, das für den Zugriff auf die Überwachungsberichte verwendet werden soll (z. B. **litwareinc\jansachweh**). Wenn Sie nicht dieses Format (Domäne\Benutzername) verwenden, tritt ein Fehler auf.
    
    Geben Sie das Kennwort des Benutzerkontos in das Feld **Kennwort** ein und klicken Sie auf **Weiter**. Für dieses Konto sind keine speziellen Rechte erforderlich. Dem Konto werden die erforderlichen Anmelde- und Datenbankberechtigungen automatisch erteilt, wenn die Einrichtung abgeschlossen wird.
    
5. Geben Sie auf der Seite **Gruppe mit Lesezugriff angeben** den Namen einer Sicherheitsgruppe an, der der Lesezugriff auf die SQL Server Reporting Services im Benutzergruppenfeld gewährt wird. Wenn Sie beispielsweise einen Lesezugriff auf die Berichte für Administratoren erteilen möchten, geben Sie **RTCUniversalReadOnlyAdmins** ein. Klicken Sie auf **Weiter**.
    
6. Klicken Sie auf der Seite **Befehle ausführen** auf **Fertigstellen**.
    
Monitoring-Berichte kann auch von der Skype für Business Server-Verwaltungsshell installiert werden durch Ausführen des Skripts DeployReports.ps1; in Windows PowerShell-Skripts finden Sie der \<Installationsspeicherort\>\Skype für Business Server 2015\Deployment\Setup Ordner. Um Überwachungsberichte mithilfe von DeployReports.ps1 zu installieren, geben Sie einen Befehl ähnlich dem folgenden an der Eingabeaufforderung-Verwaltungsshell aus:
  
```
C:\Program Files\Skype for Business Server 2015\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"
```

Die im vorstehenden Befehl verwendeten Parameter werden in der folgenden Tabelle beschrieben:
  
|**Parametername**|**Erforderlich**|**Beschreibung**|
|:-----|:-----|:-----|
|storedUserName  <br/> |Ja  <br/> |Benutzerkonto, das für den Zugriff auf den Überwachungsspeicher verwendet wird. Zum Beispiel  <br/> ```-storedUserName "litwareinc\kenmyer"```Dieses Konto muss die zuvor angegebene SQL Server und SQL Server Reporting Services-Berechtigungen verfügen, oder das Skript nicht fehlschlägt.  <br/> |
|storedPassword  <br/> |Ja  <br/> |Kennwort für das Benutzerkonto, das für den Zugriff auf den Überwachungsspeicher verwendet wird.  <br/> |
|readOnlyGroupName  <br/> |Nein  <br/> |Domäne oder lokale Sicherheitsgruppe, deren Mitglieder den Lesezugriff für die Überwachungsberichte erhalten. Beachten Sie, dass das Skript fehlschlägt, wenn die angegebene Gruppe nicht vorhanden ist. Falls Sie diese Berechtigungen später wieder entziehen möchten oder sich dafür entscheiden, anderen Benutzern oder Gruppen Zugriffsberechtigungen zu erteilen, können Sie dies mithilfe des Berichts-Managers der SQL Service Reporting Services tun.  <br/> |
|reportSqlServerInstance  <br/> |Nein  <br/> |SQL Server-Instanz, die als Host für den Berichtsdienst fungiert. Die Berichtsinstanz muss unter Verwendung des vollqualifizierten Domänennamens des Berichtsservers angegeben werden. Beispiel:<br/> ```-reportServerSqlInstance atl-sql-001.litwareinc.com```Wenn dieser Parameter nicht angegeben ist wird das Skript wird davon ausgegangen, dass die reporting Services von derselben SQL Server-Instanz gehostet werden, die die Überwachungsdatenbank gehostet wird.  <br/> |
|monitoringDatabaseId  <br/> |Nein  <br/> |Dienstidentität für die Überwachungsdatenbank. Sie können die Identitäten für Ihre Überwachungsdatenbanken durch Ausführung des folgenden Befehls zurückgeben:<br/> ```Get-CsService -MonitoringDatabase```|
   
Verwenden Sie, nachdem die Überwachungsberichte installiert wurden, das New-CsReportingConfiguration-Cmdlet, um die URL für den Zugriff auf die Berichte zu konfigurieren. Für diese Aufgabe kann aus der Skype für Business Server-Verwaltungsshell durchgeführt werden durch den folgenden Windows PowerShell-Befehl ausführen. Beachten Sie, dass es zwar ratsam, aber nicht erforderlich ist, das HTTPS-Protokoll für die Konfiguration der Berichts-URL zu verwenden:
  
```
New-CsReportingConfiguration -Identity 'service:MonitoringDatabase:atl-sql-001.litwareinc.com' -ReportingURL 'https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST'
```

Im vorangehenden Befehl sollte die ReportingUrl-Eigenschaft auf die von SQL Server 2008 R2 Reporting Services verwendete Berichts-Manager-URL festgelegt sein. Führen Sie zur Ermittlung der Berichts-Manager-URL folgende Schritte auf dem Computer durch, auf dem SQL Server Reporting Services installiert wurde:
  
1. Klicken Sie auf „Start“, „Alle Programme“, „Microsoft SQL Server 2008 R2“, „Konfigurationstools“ und dann auf „Konfigurations-Manager für Reporting Services“.
    
2. Vergewissern Sie sich, dass im Dialogfeld „Konfigurationsverbindung für Reporting Services“ der Name des Reporting Services-Computers im Feld „Servername“ angezeigt wird. Wählen Sie die SQL Server-Instanz in der Dropdownliste „Berichtsserverinstanz“ aus und klicken Sie dann auf „Verbinden“.
    
3. Klicken Sie unter „Konfigurations-Manager für Reporting Services“ auf „Berichts-Manager-URL“. Im Bereich „Berichts-Manager-URL“ sollten mehrere URLs angezeigt werden. Sie können jede dieser URLs als URL für die Berichtsfunktion verwenden. Es sei jedoch nochmals darauf hingewiesen, dass für die ReportingUrl das HTTPS-Protokoll empfohlen wird.
    
Wenn Sie eine Spiegeldatenbank für Ihre Überwachungsdatenbank eingerichtet haben, müssen Sie auch die Überwachungsberichte mit der Spiegeldatenbank verknüpfen. Finden Sie im Artikel [Überwachungsberichte mit einer Spiegeldatenbank in Skype für Business Server zuordnen](monitoring-reports-with-a-mirror-database.md) ausführliche.
  

