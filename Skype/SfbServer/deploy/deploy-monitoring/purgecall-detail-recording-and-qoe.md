---
title: Manuelles Löschen der Aufzeichnung von Anrufdetailaufzeichnungen und der Quality of Experience-Datenbanken in Skype for Business Server
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
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: 'Zusammenfassung: Informationen zum manuellen Löschen von Datensätzen aus dem CDR und den von Skype for Business Server verwendeten QoE-Datenbanken.'
ms.openlocfilehash: 2d36af2d06b6d6951e436ea456d4036478278600
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802145"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a>Manuelles Löschen der Aufzeichnung von Anrufdetailaufzeichnungen und der Quality of Experience-Datenbanken in Skype for Business Server
 
**Zusammenfassung:** Informationen zum manuellen Löschen von Datensätzen aus dem CDR und den von Skype for Business Server verwendeten QoE-Datenbanken.
  
Die CdR- und die QoE-Datenbank können manuell oder automatisch gelöscht werden. Das Löschen von Datensätzen kann wichtig sein, damit die Daten nicht veraltet sind oder wenn Berichte von einer Ausgangsbasis zurückgesetzt werden müssen.
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>Manuelles Löschen von Datensätzen aus CDR- und QoE-Datenbanken

Administratoren können die #A0 (Call Detail Recording, Aufzeichnung von Anrufdetails) und/oder die #A1 (Quality of Experience) so konfigurieren, dass alte Datensätze automatisch aus der Datenbank gelöscht werden. Dies tritt auf, wenn das Löschen für die angegebene Datenbank (CDR oder QoE) aktiviert wurde und datensätze vorhanden sind, die länger als die angegebene Zeit in der Datenbank sind. Beispielsweise können Administratoren täglich um 1:00 Uhr das System so konfigurieren, dass QoE-Einträge, die länger als 60 Tage alt sind, aus der QoE-Datenbank gelöscht werden.
  
Zusätzlich zu dieser automatischen Bereinigung wurden zwei neue Cmdlets &#x2014; Invoke-CsCdrDatabasePurge und Invoke-CsQoEDatbasePurge &#x2014; Skype for Business Server hinzugefügt. Mit diesen Cmdlets können Administratoren Datensätze jederzeit manuell aus der CDR- und der QoE-Datenbank löschen. Um beispielsweise alle Datensätze, die mehr als 10 Tage alt sind, manuell aus der Datenbank für die Aufzeichnung von Aufzeichnungen von Aufzeichnungen zu löschen, können Sie einen Befehl wie den folgenden verwenden:
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

Im vorstehenden Befehl werden sowohl Anrufdetaildatensätze als auch Diagnosedatensätze, die älter als 10 Tage sind, aus der Überwachungsdatenbank auf dem atl-sql-001.litwareinc.com. (Anrufdetaildatensätze sind Benutzer-/Sitzungsberichte. Diagnosedatensätze sind Diagnoseprotokolle, die von Clientanwendungen wie Skype for Business Server hochgeladen werden.)
  
Wie oben gezeigt, müssen Sie beim Ausführen des Cmdlets Invoke-CsCdrDatabasePurge sowohl den Parameter PurgeCallDetaiDataOlderThanDays als auch den Parameter PurgeDiagnosticDataOlderThanDays einfügen. Diese Parameter müssen jedoch nicht auf denselben Wert festgelegt werden. Sie können beispielsweise festlegen, dass Anrufdetaildatensätze, die älter sind als 10 Tage, gelöscht werden, und konfigurieren, dass alle Diagnosedatensätze in der Datenbank bleiben. Legen Sie dazu "PurgeCallDetailDataOlderThanDays" auf 10 und "PurgeDiagnosticDataOlderThanDays" auf 0 fest. Beispiel:
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

Wenn Sie das Cmdlet Invoke-CsCdrDatabasePurge ausführen, sehen Sie standardmäßig für jede Datenbanktabelle, die gelöscht werden muss, eine Eingabeauforderung ähnlich wie die folgende:
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

Sie müssen entweder J (für Ja) oder A (für Ja zu allen Optionen) eingeben, bevor der Löschvorgang in der Datenbank tatsächlich beginnt. Wenn Sie diese Bestätigungsaufforderungen lieber unterdrücken möchten, fügen Sie am Ende des Aufrufs von Invoke-CsCdrDatabasePurge die folgenden Parameter hinzu:
  
```powershell
-Confirm:$False
```

Beispiel:
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

Dies bewirkt, dass keine Bestätigungsaufforderungen angezeigt werden und der Löschvorgang in der Datenbank sofort durchgeführt wird.
  
Verwenden Sie das Cmdlet Invoke-CsQoEDatabasePurge, um Datensätze in der QoE-Datenbank zu löschen, und geben Sie das Alter zu der löschenden Datensätze (in Tagen) an:
  
```powershell
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


