---
title: Manuelles Bereinigen der KDS- und QoE-Datenbanken
TOCTitle: Manuelles Bereinigen der KDS- und QoE-Datenbanken
ms:assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204812(v=OCS.15)
ms:contentKeyID: 49293718
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Manuelles Bereinigen der KDS- und QoE-Datenbanken

 

_**Letztes Änderungsdatum des Themas:** 2014-07-07_

Wie im vorherigen Abschnitt angegeben, können Administratoren die Datenbank für die Aufzeichnung von Kommunikationsdatensätzen (KDS) und/oder die QoE-Datenbanken (Quality of Experience) so konfigurieren, dass alte Datensätze automatisch aus der Datenbank gelöscht werden. Dies ist der Fall, wenn der Löschvorgang für die angegebene Datenbank (KDS oder QoE) aktiviert wurde und wenn Datensätze vorhanden sind, die länger als der angegebene Zeitraum in der Datenbank vorhanden waren. Administratoren können das System beispielsweise so konfigurieren, dass täglich um 1:00 Uhr QoE-Datensätze, die älter als 60 Tage sind, aus der QoE-Datenbank gelöscht werden.

Zusätzlich zu diesem automatischen Löschvorgang wurden zwei neue Cmdlets zu Microsoft Lync Server 2013 hinzugefügt: **Invoke-CsCdrDatabasePurge** und **Invoke-CsQoEDatbasePurge**. Mit diesen Cmdlets können Administratoren Datensätze jederzeit aus den KDS- und QoE-Datenbanken löschen. Um beispielsweise alle Datensätze, die älter als 10 Tage sind, aus der KDS-Datenbank zu entfernen, können Sie einen ähnlichen Befehl wie den folgenden verwenden:

    Invoke-CsCdrDatabasePurge -Identity MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

Im vorherigen Befehl werden sowohl Anrufdetaildatensätze als auch Diagnosedatensätze, die älter als 10 Tage sind, aus der Überwachungsdatenbank unter **atl-sql-001.litwareinc.com** entfernt. (Anrufdetaildatensätze sind Benutzer-/Sitzungsberichte. Diagnosedatensätze sind Diagnoseprotokolle, die von Clientanwendungen wie Lync 2013 hochgeladen werden.)

Wie oben gezeigt, müssen Sie beim Ausführen des Cmdlets **Invoke-CsCdrDatabasePurge** sowohl den Parameter **PurgeCallDetaiDataOlderThanDays** als auch den Parameter **PurgeDiagnosticDataOlderThanDays** einfügen. Diese Parameter müssen jedoch nicht auf denselben Wert festgelegt werden. Sie können beispielsweise festlegen, dass Anrufdetaildatensätze, die älter sind als 10 Tage, gelöscht werden, und konfigurieren, dass alle Diagnosedatensätze in der Datenbank bleiben. Legen Sie hierzu **PurgeCallDetailDataOlderThanDays** auf den Wert **10** und **PurgeDiagnosticDataOlderThanDays** auf den Wert **0** fest. Beispiel:

    Invoke-CsCdrDatabasePurge -Identity MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

Wenn Sie das Cmdlet **Invoke-CsCdrDatabasePurge** ausführen, sehen Sie standardmäßig für jede Datenbanktabelle, die gelöscht werden muss, eine Eingabeauforderung ähnlich wie die folgende:

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

Sie müssen entweder J (für Ja) oder A (für Ja zu allen Optionen) eingeben, bevor der Löschvorgang in der Datenbank tatsächlich beginnt. Wenn Sie diese Bestätigungsaufforderungen lieber unterdrücken möchten, fügen Sie am Ende des Aufrufs von **Invoke-CsCdrDatabasePurge** die folgenden Parameter hinzu:

    -Confirm:$False

Beispiel:

    Invoke-CsCdrDatabasePurge -Identity MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

Dies bewirkt, dass keine Bestätigungsaufforderungen angezeigt werden und der Löschvorgang in der Datenbank sofort durchgeführt wird.

Verwenden Sie das Cmdlet **Invoke-CsQoEDatabasePurge**, um Datensätze in der QoE-Datenbank zu löschen, und geben Sie das Alter zu der löschenden Datensätze (in Tagen) an:

    Invoke-CsQoEDatabasePurge -Identity MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

