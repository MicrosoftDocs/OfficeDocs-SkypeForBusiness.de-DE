---
title: Manuelles Löschen der Datenbanken für das Aufzeichnen von Anrufen und der Qualität von Erfahrungen
description: Manuelles Löschen der Datenbanken für das Aufzeichnen von Anrufen und der Qualität von Experience
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
ms.openlocfilehash: 4c7903431d28bf1a829991ce35c2ee7351168b4a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556561"
---
# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a>Manuelles Löschen der Datenbanken für das Aufzeichnen von Anrufen und der Qualität von Experience in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-07-07_

Administratoren können die KDS-Datenbanken (Call Detail Recording) und/oder die QoE-Datenbank (Quality of Experience) so konfigurieren, dass alte Datensätze automatisch aus der Datenbank bereinigt werden; Dies tritt auf, wenn die Bereinigung für die angegebene Datenbank (CDR oder QoE) aktiviert wurde und wenn Datensätze vorhanden sind, die sich in der Datenbank länger als die angegebene Zeitspanne befinden. Beispielsweise können Administratoren jeden Tag um 1:00 Uhr das System so konfigurieren, dass QoE-Datensätze, die älter als 60 Tage sind, aus der QoE-Datenbank gelöscht werden.

Zusätzlich zu dieser automatischen Bereinigung wurden zwei neue Cmdlets hinzugefügt, Invoke-CsCdrDatabasePurge und Invoke-CsQoEDatbasePurge--Microsoft lync Server 2013. Diese Cmdlets ermöglichen Administratoren das manuelle Löschen von Datensätzen aus der KDS-und der QoE-Datenbank zu jedem beliebigen Zeitpunkt. Wenn Sie beispielsweise alle Datensätze, die älter als 10 Tage sind, aus der KDS-Datenbank manuell löschen möchten, können Sie einen Befehl wie den folgenden verwenden:

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

Im vorstehenden Befehl werden sowohl Anruf Detaildatensätze als auch Diagnosedatensätze, die älter als 10 Tage sind, aus der Überwachungsdatenbank auf ATL-SQL-001.litwareinc.com gelöscht. (Anruf Detaildatensätze sind Benutzer/Sitzungsberichte. Bei Diagnosedatensätzen handelt es sich um Diagnoseprotokolle, die von Clientanwendungen wie lync 2013 hochgeladen werden.)

Wie oben gezeigt, müssen Sie beim Ausführen des Cmdlets Invoke-CsCdrDatabasePurge sowohl den Parameter PurgeCallDetaiDataOlderThanDays als auch den Parameter PurgeDiagnosticDataOlderThanDays einfügen. Diese Parameter müssen jedoch nicht auf denselben Wert festgelegt werden. Sie können beispielsweise festlegen, dass Anrufdetaildatensätze, die älter sind als 10 Tage, gelöscht werden, und konfigurieren, dass alle Diagnosedatensätze in der Datenbank bleiben. Legen Sie dazu PurgeCallDetailDataOlderThanDays auf 10 und PurgeDiagnosticDataOlderThanDays auf 0 fest. Beispiel:

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

Wenn Sie das Cmdlet Invoke-CsCdrDatabasePurge ausführen, sehen Sie standardmäßig für jede Datenbanktabelle, die gelöscht werden muss, eine Eingabeauforderung ähnlich wie die folgende:

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

Sie müssen entweder J (für Ja) oder A (für Ja zu allen Optionen) eingeben, bevor der Löschvorgang in der Datenbank tatsächlich beginnt. Wenn Sie diese Bestätigungsaufforderungen lieber unterdrücken möchten, fügen Sie am Ende des Aufrufs von Invoke-CsCdrDatabasePurge die folgenden Parameter hinzu:

    -Confirm:$False

Beispiel:

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

Dies bewirkt, dass keine Bestätigungsaufforderungen angezeigt werden und der Löschvorgang in der Datenbank sofort durchgeführt wird.

Verwenden Sie das Cmdlet Invoke-CsQoEDatabasePurge, um Datensätze in der QoE-Datenbank zu löschen, und geben Sie das Alter zu der löschenden Datensätze (in Tagen) an:

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

