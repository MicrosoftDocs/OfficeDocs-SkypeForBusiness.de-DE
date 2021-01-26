---
title: Installieren von Überwachungsberichten in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6f417569-b100-442c-ad48-fdd794626cf7
description: 'Zusammenfassung: Erfahren Sie, wie Sie einen Dienst installieren, der Überwachungsberichte in Skype for Business Server generiert.'
ms.openlocfilehash: 10a98bea4af3511c50a0b2b814f8b44911f3742f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802255"
---
# <a name="install-monitoring-reports-in-skype-for-business-server"></a>Installieren von Überwachungsberichten in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie einen Dienst installieren, der Überwachungsberichte in Skype for Business Server generiert.
  
Skype for Business Server Monitoring Reports bieten Ihnen eine Vielzahl von Informationen zur Qualität und Menge der Kommunikationssitzungen, die in Ihrer Organisation stattfinden. 
  
## <a name="install-monitoring-reports"></a>Installieren von Überwachungsberichten

Überwachungsberichte werden bei der Installation von Skype for Business Server nicht automatisch installiert. Stattdessen müssen Sie Überwachungsberichte separat installieren, und das erst, nachdem Skype for Business Server auf dem Computer installiert wurde.
  
> [!NOTE]
> Es empfiehlt sich, die Überwachungsberichte auf demselben Computer zu intstallieren, auf dem auch die Überwachungsdatenbank installiert ist. Somit wird die Zuweisung von Zugriffsberechtigungen für die Berichte vereinfacht: wenn die Überwachungsberichte auf dem Computer installiert sind, der auch als Host für den Überwachungsspeicher fungiert, müssen Sie keine Berechtigungen zuweisen, die einer Datenbank auf dem Computer gestatten, mit Reporting Services zu interagieren, wenn diese auf einem zweiten Computer ausgeführt werden. 
  
Skype for Business Server Monitoring Reports umfassen über 30 Berichte, die detaillierte Informationen zu Konferenzen, Peer-zu-Peer-Chatsitzungen, Benutzerregistrierungen, der Reaktiongruppenanwendung und vielem mehr enthalten. Für die Version 2013 umfassen Skype for Business Server Monitoring Reports eine Reihe von Verbesserungen:
  
- **Neue Berichte zur Sprachqualität**. Diese neuen Berichte enthalten den Bericht über die Medienqualität [in Skype for Business Server,](../../manage/health-and-monitoring/comparison.md)in dem die Qualität zwischen verschiedenen Anruftypen verglichen wird (z. B. zwischen kabelgebundenen anrufen und Funkanrufen). und den Bericht über Zeitpunkt des Konferenzanrufs [in Skype for Business Server,](../../manage/health-and-monitoring/join-time-report.md)der Informationen über den Zeitraum enthält, der für den Beitritt von Benutzern zu einer Konferenz erforderlich ist. 
    
- **Verbesserte Berichte zur Analyse und Problembehebung bei Video- und Anwendungsfreigabesitzungen.** Der Zusammenfassende Bericht über [Medienqualität in Skype for Business Server](../../manage/health-and-monitoring/summary.md) bietet eine Möglichkeit zum Analysieren von Video- und Anwendungsfreigabeanrufen, während der Bericht über Serverleistung in Skype for Business [Server](../../manage/health-and-monitoring/server-performance.md) die Leistung der Server, die diese Anrufe generieren, auf einzelheiten. Video- und Anwendungsfreigabemetriken werden jetzt auch im Detailbericht über [Peer-zu-Peer-Sitzungen in Skype for Business Server](../../manage/health-and-monitoring/peer-to-peer-session-detail-report.md) und im Detaillierten Konferenzbericht in Skype for Business Server [gemeldet.](../../manage/health-and-monitoring/detail-report.md)
    
- **Verbesserte Berichtsleistung**. Dies umfasst kürzere Reaktions- und Datenabrufzeiten, also auch eine schnellere und einfachere Navigation in den Berichten.
    
Weitere Informationen erhalten Sie in der Dokumentation zu den Überwachungsberichten.
  
> [!NOTE]
> In Skype for Business Server ist ein weiterer Bericht – der Unterbericht über QoE-Anrufdetails – enthalten. Dieser Bericht dient jedoch in erster Linie der internen Verwendung und ist nicht für den direkten Zugriff vorgesehen. 
  
Es gibt zwei Möglichkeiten zum Installieren von Skype for Business Server-Überwachungsberichten: Sie können den Skype for Business Server-Bereitstellungs-Assistenten oder ein Windows PowerShell-Skript verwenden, das in den Skype for Business Server-Installationsdateien enthalten ist. Unabhängig davon, für welche Installationsmethode Sie sich entscheiden, müssen Sie zunächst Folgendes sicherstellen:
  
- Sie sind dazu berechtigt, einem Benutzerkonto in der Überwachungsdatenbank eine Datenbankrolle hinzuzufügen.
    
- Sie haben die Rolle "Content Manager" in SQL Server Reporting Services. Diese Rolle berechtigt Sie dazu, Berichte in SQL Server Reporting Services bereitzustellen.
    
Führen Sie folgende Schritte durch, um die Überwachungsberichte mithilfe des Bereitstellungs-Assistenten zu installieren:
  
1. Klicken **Sie auf "Start",** **"Alle Programme",** **"Skype for Business Server"** und dann auf **"Skype for Business Server-Bereitstellungs-Assistent".**
    
2. Im Bereitstellungs-Assistenten klicken Sie auf **Überwachungsberichte bereitstellen**, um den Assistenten für die Bereitstellung der Überwachungsberichte zu starten.
    
3. Stellen Sie im Assistenten für die Bereitstellung der Überwachungsberichte auf der Seite **Überwachungsdatenbank angeben** sicher, dass der vollqualifizierte Domänenname des als Host für Ihren Überwachungsspeicher fungierenden Computers in der Dropdownliste **Überwachungsdatenbank** angezeigt wird. (Sollten Sie über mehrere Überwachungsspeicher verfügen, müssen Sie den entsprechenden Server in der Dropdownliste auswählen.) Stellen Sie sicher, dass die richtige SQL-Serverinstanz im Feld **SQL Server Reporting Services-Instanz (SSRS)** angezeigt wird (z. B. **atl-sql-001.litwareinc.com/archinst**) und klicken Sie anschließend auf **Weiter**.
    
4. Geben Sie auf der Seite **Angeben von Anmeldeinformationen** in das Feld **Benutzername** den Domänennamen und Benutzernamen des Kontos ein, das für den Zugriff auf die Überwachungsberichte verwendet werden soll (z. B. **litwareinc\kenmyer**). Wenn Sie dieses Format (Domäne\Benutzername) nicht verwenden, tritt ein Fehler auf.
    
    Geben Sie das Kennwort in das Feld **Kennwort** ein, und klicken Sie auf **Weiter**. Beachten Sie, dass für dieses Konto keine besonderen Rechte erforderlich sind. Dem Konto werden nach Abschluss des Setups automatisch die erforderlichen Anmelde- und Datenbankberechtigungen erteilt.
    
5. Geben Sie auf der Seite **Gruppe mit Lesezugriff angeben** den Namen einer Sicherheitsgruppe an, der der Lesezugriff auf die SQL Server Reporting Services im Benutzergruppenfeld gewährt wird. Wenn Sie beispielsweise einen Lesezugriff auf die Berichte für Administratoren erteilen möchten, geben Sie **RTCUniversalReadOnlyAdmins** ein. Klicken Sie auf **Weiter**.
    
6. Klicken Sie auf der Seite **Befehle ausführen** auf **Fertig stellen**.
    
Überwachungsberichte können auch über die Skype for Business DeployReports.ps1 installiert werden, indem Sie das Skript DeployReports.ps1; Dieses Windows PowerShell finden Sie im Ordner \<install location\> "\Skype for Business Server 2015\Deployment\Setup". Um die Überwachungsdienste mithilfe von "DeployReports.ps1" zu installieren, geben Sie einen ähnlichen Befehl wie den folgenden an der Verwaltungsshell-Eingabeaufforderung ein:
  
```powershell
C:\Program Files\Skype for Business Server 2015\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"
```

Die im vorstehenden Befehl verwendeten Parameter werden in der folgenden Tabelle beschrieben:
  
|**Parametername**|**Erforderlich**|**Beschreibung**|
|:-----|:-----|:-----|
|storedUserName  <br/> |Ja  <br/> |Benutzerkonto, das für den Zugriff auf den Überwachungsspeicher verwendet wird. Zum Beispiel  <br/> ```-storedUserName "litwareinc\kenmyer"``` Dieses Konto muss über die zuvor angegebenen Berechtigungen SQL Server und SQL Server Reporting Services verfügen, da das Skript nicht ausgeführt werden kann.  <br/> |
|storedPassword  <br/> |Ja  <br/> |Kennwort für das Benutzerkonto, das für den Zugriff auf den Überwachungsspeicher verwendet wird.  <br/> |
|readOnlyGroupName  <br/> |Nein  <br/> |Domäne oder lokale Sicherheitsgruppe, deren Mitglieder den Lesezugriff für die Überwachungsberichte erhalten. Beachten Sie, dass das Skript fehlschlägt, wenn die angegebene Gruppe nicht vorhanden ist. Falls Sie diese Berechtigungen später wieder entziehen möchten oder wenn Sie sich dafür entscheiden, anderen Benutzern oder Gruppen Zugriffsberechtigungen zu erteilen, können Sie dies mithilfe des Berichts-Managers der SQL Service Reporting Services tun.  <br/> |
|reportSqlServerInstance  <br/> |Nein  <br/> |SQL Server-Instanz, die als Host für den Berichtsdienst fungiert. Die Berichtsinstanz muss unter Verwendung des vollqualifizierten Domänennamens des Berichtsservers angegeben werden. Beispiel:<br/> ```-reportServerSqlInstance atl-sql-001.litwareinc.com``` Wenn dieser Parameter nicht angegeben wird, geht das Skript davon aus, dass die Berichterstellungsdienste von derselben Instanz gehostet werden SQL Server die die Überwachungsdatenbank hostet.  <br/> |
|monitoringDatabaseId  <br/> |Nein  <br/> |Dienstidentität für die Überwachungsdatenbank. Sie können die Identitäten für Ihre Überwachungsdatenbanken durch Ausführung des folgenden Befehls zurückgeben:<br/> ```Get-CsService -MonitoringDatabase```|
   
Nachdem die Überwachungsberichte installiert wurden, müssen Sie das cmdlet New-CsReportingConfiguration verwenden, um die URL zu konfigurieren, die für den Zugriff auf diese Berichte verwendet wird. Diese Aufgabe kann über die Skype for Business Server-Verwaltungsshell ausgeführt werden, indem Sie den folgenden Windows PowerShell ausführen. Beachten Sie, dass es empfohlen, aber nicht erforderlich ist, dass Sie beim Konfigurieren der Berichts-URL das HTTPS-Protokoll verwenden:
  
```powershell
New-CsReportingConfiguration -Identity 'service:MonitoringDatabase:atl-sql-001.litwareinc.com' -ReportingURL 'https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST'
```

Im vorangehenden Befehl sollte die ReportingUrl-Eigenschaft auf die von SQL Server 2008 R2 Reporting Services verwendete Berichts-Manager-URL festgelegt sein. Führen Sie zur Ermittlung der Berichts-Manager-URL folgende Schritte auf dem Computer durch, auf dem SQL Server Reporting Services installiert wurde:
  
1. Klicken Sie auf "Start", "Alle Programme", "Microsoft SQL Server 2008 R2", "Konfigurationstools" und dann auf "Konfigurations-Manager für Reporting Services".
    
2. Vergewissern Sie sich, dass im Dialogfeld "Konfigurationsverbindung für Reporting Services" der Name des Reporting Services-Computers im Feld "Servername" angezeigt wird. Wählen Sie die SQL Server-Instanz in der Dropdownliste "Berichtsserverinstanz" aus, und klicken Sie dann auf "Verbinden".
    
3. Klicken Sie unter "Konfigurations-Manager für Reporting Services" auf  "Berichts-Manager-URL". Im  Bereich "Berichts-Manager-URL"sollten mehrere URLs angezeigt werden. Sie können jede dieser URLs als URL für die Berichtsfunktion verwenden. Es sei jedoch nochmals darauf hingewiesen, dass für die ReportingUrl das HTTPS-Protokoll empfohlen wird.
    
Wenn Sie eine Spiegeldatenbank für die Überwachungsdatenbank eingerichtet haben, müssen Sie auch die Überwachungsberichte der Spiegeldatenbank zuordnen. Weitere Informationen finden Sie im Artikel ["Zuordnen von Überwachungsberichten](monitoring-reports-with-a-mirror-database.md) zu einer Spiegeldatenbank in Skype for Business Server".
  

