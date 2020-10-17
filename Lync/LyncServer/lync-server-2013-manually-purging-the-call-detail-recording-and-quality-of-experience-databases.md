---
title: Manuelles Löschen der Datenbanken für das Aufzeichnen von Anrufen und der Qualität von Erfahrungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manually purging the call detail recording and Quality of Experience databases
ms:assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204812(v=OCS.15)
ms:contentKeyID: 48183859
ms.date: 07/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b34b3a0dd79651ef288740243313d58482959e4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524782"
---
# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a><span data-ttu-id="4efe4-102">Manuelles Löschen der Datenbanken für das Aufzeichnen von Anrufen und der Qualität von Experience in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4efe4-102">Manually purging the call detail recording and Quality of Experience databases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4efe4-103">_**Letztes Änderungsstand des Themas:** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="4efe4-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="4efe4-104">Administratoren können die KDS-Datenbanken (Call Detail Recording) und/oder die QoE-Datenbank (Quality of Experience) so konfigurieren, dass alte Datensätze automatisch aus der Datenbank bereinigt werden; Dies tritt auf, wenn die Bereinigung für die angegebene Datenbank (CDR oder QoE) aktiviert wurde und wenn Datensätze vorhanden sind, die sich in der Datenbank länger als die angegebene Zeitspanne befinden.</span><span class="sxs-lookup"><span data-stu-id="4efe4-104">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time.</span></span> <span data-ttu-id="4efe4-105">Beispielsweise können Administratoren jeden Tag um 1:00 Uhr das System so konfigurieren, dass QoE-Datensätze, die älter als 60 Tage sind, aus der QoE-Datenbank gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="4efe4-105">For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>

<span data-ttu-id="4efe4-106">Zusätzlich zu dieser automatischen Bereinigung wurden zwei neue Cmdlets hinzugefügt, Invoke-CsCdrDatabasePurge und Invoke-CsQoEDatbasePurge--Microsoft lync Server 2013. Diese Cmdlets ermöglichen Administratoren das manuelle Löschen von Datensätzen aus der KDS-und der QoE-Datenbank zu jedem beliebigen Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="4efe4-106">In addition to that automatic purging, two new cmdlets -- Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge -- have been added to Microsoft Lync Server 2013; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="4efe4-107">Wenn Sie beispielsweise alle Datensätze, die älter als 10 Tage sind, aus der KDS-Datenbank manuell löschen möchten, können Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="4efe4-107">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

<span data-ttu-id="4efe4-108">Im vorstehenden Befehl werden sowohl Anruf Detaildatensätze als auch Diagnosedatensätze, die älter als 10 Tage sind, aus der Überwachungsdatenbank auf ATL-SQL-001.litwareinc.com gelöscht.</span><span class="sxs-lookup"><span data-stu-id="4efe4-108">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="4efe4-109">(Anruf Detaildatensätze sind Benutzer/Sitzungsberichte.</span><span class="sxs-lookup"><span data-stu-id="4efe4-109">(Call detail records are user/session reports.</span></span> <span data-ttu-id="4efe4-110">Bei Diagnosedatensätzen handelt es sich um Diagnoseprotokolle, die von Clientanwendungen wie lync 2013 hochgeladen werden.)</span><span class="sxs-lookup"><span data-stu-id="4efe4-110">Diagnostic data records are diagnostic logs uploaded by client applications such as Lync 2013.)</span></span>

<span data-ttu-id="4efe4-111">Wie oben gezeigt, müssen Sie beim Ausführen des Cmdlets Invoke-CsCdrDatabasePurge sowohl den Parameter PurgeCallDetaiDataOlderThanDays als auch den Parameter PurgeDiagnosticDataOlderThanDays einfügen.</span><span class="sxs-lookup"><span data-stu-id="4efe4-111">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="4efe4-112">Diese Parameter müssen jedoch nicht auf denselben Wert festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4efe4-112">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="4efe4-113">Sie können beispielsweise festlegen, dass Anrufdetaildatensätze, die älter sind als 10 Tage, gelöscht werden, und konfigurieren, dass alle Diagnosedatensätze in der Datenbank bleiben.</span><span class="sxs-lookup"><span data-stu-id="4efe4-113">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="4efe4-114">Legen Sie dazu PurgeCallDetailDataOlderThanDays auf 10 und PurgeDiagnosticDataOlderThanDays auf 0 fest.</span><span class="sxs-lookup"><span data-stu-id="4efe4-114">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="4efe4-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4efe4-115">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

<span data-ttu-id="4efe4-116">Wenn Sie das Cmdlet Invoke-CsCdrDatabasePurge ausführen, sehen Sie standardmäßig für jede Datenbanktabelle, die gelöscht werden muss, eine Eingabeauforderung ähnlich wie die folgende:</span><span class="sxs-lookup"><span data-stu-id="4efe4-116">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

<span data-ttu-id="4efe4-p105">Sie müssen entweder J (für Ja) oder A (für Ja zu allen Optionen) eingeben, bevor der Löschvorgang in der Datenbank tatsächlich beginnt. Wenn Sie diese Bestätigungsaufforderungen lieber unterdrücken möchten, fügen Sie am Ende des Aufrufs von Invoke-CsCdrDatabasePurge die folgenden Parameter hinzu:</span><span class="sxs-lookup"><span data-stu-id="4efe4-p105">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place. If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>

    -Confirm:$False

<span data-ttu-id="4efe4-119">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4efe4-119">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

<span data-ttu-id="4efe4-120">Dies bewirkt, dass keine Bestätigungsaufforderungen angezeigt werden und der Löschvorgang in der Datenbank sofort durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4efe4-120">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>

<span data-ttu-id="4efe4-121">Verwenden Sie das Cmdlet Invoke-CsQoEDatabasePurge, um Datensätze in der QoE-Datenbank zu löschen, und geben Sie das Alter zu der löschenden Datensätze (in Tagen) an:</span><span class="sxs-lookup"><span data-stu-id="4efe4-121">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

