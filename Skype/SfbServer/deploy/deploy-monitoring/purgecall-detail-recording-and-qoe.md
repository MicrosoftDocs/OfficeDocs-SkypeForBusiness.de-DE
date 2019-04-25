---
title: Manuelles Löschen der KDS- und Quality of Experience-Datenbanken in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: 'Zusammenfassung: Erfahren Sie, wie Manuelles Löschen von Datensätzen KDS und die QoE-Datenbank von Skype für Business Server verwendet wird.'
ms.openlocfilehash: 55582d28541e798e8ab1c488fb6eeed266bd29b9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225469"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a><span data-ttu-id="ecb41-103">Manuelles Löschen der KDS- und Quality of Experience-Datenbanken in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="ecb41-103">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>
 
<span data-ttu-id="ecb41-104">**Zusammenfassung:** Erfahren Sie, wie Manuelles Löschen von Datensätzen KDS und die QoE-Datenbank von Skype für Business Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ecb41-104">**Summary:** Learn how to manually purge records from the CDR and the QoE databases used by Skype for Business Server.</span></span>
  
<span data-ttu-id="ecb41-p101">Die KDS- und die QoE-Datenbank können manuell oder automatisch von Datensätzen bereinigt werden. Die Bereinigung von Einträgen kann wichtig sein, wenn Daten nicht verfallen sollen oder wenn Berichte von einer Ausgangsbasis aus zurückgesetzt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ecb41-p101">The CDR and QoE databases can be manually or automatically purged of records. Purging records can be important so that data doesn't become stale or when needing to reset reports from a starting baseline.</span></span>
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a><span data-ttu-id="ecb41-107">Manuelles Bereinigen von Datensätzen aus KDS- und QoE-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="ecb41-107">Manually purge records from CDR and QoE databases</span></span>

<span data-ttu-id="ecb41-p102">Administratoren können die Datenbank für die Aufzeichnung von Kommunikationsdatensätzen (KDS) und/oder die QoE-Datenbanken (Quality of Experience) so konfigurieren, dass alte Datensätze automatisch aus der Datenbank gelöscht werden. Dies ist der Fall, wenn der Löschvorgang für die angegebene Datenbank (KDS oder QoE) aktiviert wurde und wenn Datensätze vorhanden sind, die länger als der angegebene Zeitraum in der Datenbank vorhanden waren. Administratoren können das System beispielsweise so konfigurieren, dass täglich um 1:00 Uhr QoE-Datensätze, die älter als 60 Tage sind, aus der QoE-Datenbank gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="ecb41-p102">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time. For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>
  
<span data-ttu-id="ecb41-110">Zusätzlich zu den automatische Löschung; zwei neue Cmdlets & #x 2014 Rufen Sie CsCdrDatabasePurge und Aufrufen CsQoEDatbasePurge & #x 2014; Skype wurden für Business Server hinzugefügt; Diese Cmdlets ermöglichen Administratoren die Datensätze aus der KDS und QoE-Datenbanken können Sie jederzeit manuell zu löschen.</span><span class="sxs-lookup"><span data-stu-id="ecb41-110">In addition to that automatic purging, two new cmdlets &#x2014; Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge &#x2014; have been added to Skype for Business Server; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="ecb41-111">Beispielsweise um Manuelles Löschen aller Datensätze von mehr als 10 Tage alt sind, aus der CDR-Datenbank einen ähnlichen Befehl wie können Sie:</span><span class="sxs-lookup"><span data-stu-id="ecb41-111">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

<span data-ttu-id="ecb41-112">Im vorherigen Befehl werden sowohl Anrufdetaildatensätze als auch Diagnosedatensätze, die älter als 10 Tage sind, aus der Überwachungsdatenbank unter atl-sql-001.litwareinc.com entfernt.</span><span class="sxs-lookup"><span data-stu-id="ecb41-112">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="ecb41-113">(Anrufdetaildatensätze sind Benutzer-/Sitzungsberichte.</span><span class="sxs-lookup"><span data-stu-id="ecb41-113">(Call detail records are user/session reports.</span></span> <span data-ttu-id="ecb41-114">Diagnosedaten Datensätze werden Diagnoseprotokolle von Clientanwendungen wie Skype für Business Server hochgeladen wurden.)</span><span class="sxs-lookup"><span data-stu-id="ecb41-114">Diagnostic data records are diagnostic logs uploaded by client applications such as Skype for Business Server.)</span></span>
  
<span data-ttu-id="ecb41-115">Wie oben gezeigt, müssen Sie beim Ausführen des Cmdlets Invoke-CsCdrDatabasePurge sowohl den Parameter PurgeCallDetaiDataOlderThanDays als auch den Parameter PurgeDiagnosticDataOlderThanDays einfügen.</span><span class="sxs-lookup"><span data-stu-id="ecb41-115">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="ecb41-116">Diese Parameter müssen jedoch nicht auf denselben Wert festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="ecb41-116">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="ecb41-117">Sie können beispielsweise festlegen, dass Anrufdetaildatensätze, die älter sind als 10 Tage, gelöscht werden und konfigurieren, dass alle Diagnosedatensätze in der Datenbank bleiben.</span><span class="sxs-lookup"><span data-stu-id="ecb41-117">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="ecb41-118">Klicken Sie dazu "purgecalldetaildataolderthandays" auf 10 und PurgeDiagnosticDataOlderThanDays auf 0 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ecb41-118">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="ecb41-119">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ecb41-119">For example:</span></span>
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

<span data-ttu-id="ecb41-120">Wenn Sie das Cmdlet Invoke-CsCdrDatabasePurge ausführen, sehen Sie standardmäßig für jede Datenbanktabelle, die gelöscht werden muss, eine Eingabeaufforderung ähnlich wie die folgende:</span><span class="sxs-lookup"><span data-stu-id="ecb41-120">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

<span data-ttu-id="ecb41-p106">Sie müssen entweder J (für Ja) oder A (für Ja zu allen Optionen) eingeben, bevor der Löschvorgang in der Datenbank tatsächlich beginnt. Wenn Sie diese Bestätigungsaufforderungen lieber unterdrücken möchten, fügen Sie am Ende des Aufrufs von Invoke-CsCdrDatabasePurge die folgenden Parameter hinzu:</span><span class="sxs-lookup"><span data-stu-id="ecb41-p106">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place. If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>
  
```
-Confirm:$False
```

<span data-ttu-id="ecb41-123">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ecb41-123">For example:</span></span>
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

<span data-ttu-id="ecb41-124">Dies bewirkt, dass keine Bestätigungsaufforderungen angezeigt werden und der Löschvorgang in der Datenbank sofort durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ecb41-124">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>
  
<span data-ttu-id="ecb41-125">Verwenden Sie das Cmdlet Invoke-CsQoEDatabasePurge, um Datensätze in der QoE-Datenbank zu löschen und geben Sie das Alter der zu löschenden Datensätze (in Tagen) an:</span><span class="sxs-lookup"><span data-stu-id="ecb41-125">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>
  
```
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


