---
title: Manuelles Löschen der KDS- und QoE-Datenbanken in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: 'Zusammenfassung: Erfahren Sie, wie Manuelles Löschen von Datensätzen KDS und die QoE-Datenbank von Skype für Business Server 2015 verwendet wird.'
ms.openlocfilehash: 1451187112e636e58fbcd32061ce1e8bec1b7b9a
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568532"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server-2015"></a>Manuelles Löschen der KDS- und QoE-Datenbanken in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Manuelles Löschen von Datensätzen KDS und die QoE-Datenbank von Skype für Business Server 2015 verwendet wird.
  
Die KDS- und die QoE-Datenbank können manuell oder automatisch von Datensätzen bereinigt werden. Die Bereinigung von Einträgen kann wichtig sein, wenn Daten nicht verfallen sollen oder wenn Berichte von einer Ausgangsbasis aus zurückgesetzt werden müssen.
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>Manuelles Bereinigen von Datensätzen aus KDS- und QoE-Datenbanken

Administratoren können die Datenbank für die Aufzeichnung von Kommunikationsdatensätzen (KDS) und/oder die QoE-Datenbanken (Quality of Experience) so konfigurieren, dass alte Datensätze automatisch aus der Datenbank gelöscht werden. Dies ist der Fall, wenn der Löschvorgang für die angegebene Datenbank (KDS oder QoE) aktiviert wurde und wenn Datensätze vorhanden sind, die länger als der angegebene Zeitraum in der Datenbank vorhanden waren. Administratoren können das System beispielsweise so konfigurieren, dass täglich um 1:00 Uhr QoE-Datensätze, die älter als 60 Tage sind, aus der QoE-Datenbank gelöscht werden.
  
Zusätzlich zu, dass automatische Löschung, zwei neue Cmdlets & #x 2014; Rufen Sie CsCdrDatabasePurge und Aufrufen CsQoEDatbasePurge & #x 2014; Skype wurden für Business Server 2015 hinzugefügt; Diese Cmdlets ermöglichen Administratoren die Datensätze aus der KDS und QoE-Datenbanken können Sie jederzeit manuell zu löschen. Beispielsweise um Manuelles Löschen aller Datensätze von mehr als 10 Tage alt sind, aus der CDR-Datenbank einen ähnlichen Befehl wie können Sie:
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

Im vorherigen Befehl werden sowohl Anrufdetaildatensätze als auch Diagnosedatensätze, die älter als 10 Tage sind, aus der Überwachungsdatenbank unter atl-sql-001.litwareinc.com entfernt. (Anrufdetaildatensätze sind Benutzer-/Sitzungsberichte. Diagnosedaten Datensätze werden Diagnoseprotokolle hochgeladen von Clientanwendungen wie Skype für Business Server 2015.)
  
Wie oben gezeigt, müssen Sie beim Ausführen des Cmdlets Invoke-CsCdrDatabasePurge sowohl den Parameter PurgeCallDetaiDataOlderThanDays als auch den Parameter PurgeDiagnosticDataOlderThanDays einfügen. Diese Parameter müssen jedoch nicht auf denselben Wert festgelegt werden. Sie können beispielsweise festlegen, dass Anrufdetaildatensätze, die älter sind als 10 Tage, gelöscht werden und konfigurieren, dass alle Diagnosedatensätze in der Datenbank bleiben. Klicken Sie dazu "purgecalldetaildataolderthandays" auf 10 und PurgeDiagnosticDataOlderThanDays auf 0 festgelegt. Beispiel:
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

Wenn Sie das Cmdlet Invoke-CsCdrDatabasePurge ausführen, sehen Sie standardmäßig für jede Datenbanktabelle, die gelöscht werden muss, eine Eingabeaufforderung ähnlich wie die folgende:
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

Sie müssen entweder J (für Ja) oder A (für Ja zu allen Optionen) eingeben, bevor der Löschvorgang in der Datenbank tatsächlich beginnt. Wenn Sie diese Bestätigungsaufforderungen lieber unterdrücken möchten, fügen Sie am Ende des Aufrufs von Invoke-CsCdrDatabasePurge die folgenden Parameter hinzu:
  
```
-Confirm:$False
```

Beispiel:
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

Dies bewirkt, dass keine Bestätigungsaufforderungen angezeigt werden und der Löschvorgang in der Datenbank sofort durchgeführt wird.
  
Verwenden Sie das Cmdlet Invoke-CsQoEDatabasePurge, um Datensätze in der QoE-Datenbank zu löschen und geben Sie das Alter der zu löschenden Datensätze (in Tagen) an:
  
```
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


