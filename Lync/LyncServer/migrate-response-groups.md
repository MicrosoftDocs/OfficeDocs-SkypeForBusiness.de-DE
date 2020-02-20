---
title: Migrieren von Reaktionsgruppen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fb771f448fdb6bb155f80403b5b978a62f714e9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>Migrieren von Reaktionsgruppen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-09-23_

Nachdem die Benutzer in lync Server 2013 Pools verschoben wurden, können Sie Ihre Reaktionsgruppen migrieren. Die Migration von Reaktionsgruppen umfasst das Kopieren von Agentgruppen, Warteschlangen, Workflows, Audiodateien und Kontaktobjekten der verschobenen Reaktionsgruppe aus der Legacy Bereitstellung in den lync Server 2013 Pool. Nachdem Sie Ihre Legacy-Reaktionsgruppen migriert haben, werden Anrufe an die Reaktionsgruppen von der Reaktionsgruppenanwendung im lync Server 2013-Pool verarbeitet. Anrufe für Reaktionsgruppen werden nicht mehr vom Vorversionspool verarbeitet.

<div>


> [!NOTE]  
> Obwohl Sie Reaktionsgruppen migrieren können, bevor Sie alle Benutzer in den lync Server 2013 Pool verschieben, wird empfohlen, dass Sie zuerst alle Benutzer verschieben. Insbesondere Benutzer, die Reaktionsgruppen-Agents sind, verfügen erst dann über die vollständige Funktionalität der neuen Features, wenn Sie in den lync Server 2013 Pool verschoben werden.



</div>

Bevor Sie Reaktionsgruppen migrieren, müssen Sie einen lync Server 2013-Pool bereitgestellt haben, der das Reaktionsgruppenanwendung enthält. Das Reaktionsgruppenanwendung wird bei der Bereitstellung von Enterprise-VoIP standardmäßig installiert und aktiviert. Sie können sicherstellen, dass der Reaktionsgruppenanwendung durch Ausführen des Cmdlets **Get-CsService – ApplicationServer** installiert wird.

<div>


> [!NOTE]  
> Sie können neue lync Server 2013 Reaktionsgruppen im lync Server 2013-Pool erstellen, bevor Sie Ihre Vorgänger Reaktionsgruppen migrieren.



</div>

Um Reaktionsgruppen aus einem Legacy Pool in die lync Server 2013 zu migrieren, führen Sie das Cmdlet " **verschieben-CsRgsConfiguration** " aus.

<div>


> [!IMPORTANT]  
> Das Cmdlet für die Reaktionsgruppen Migration verschiebt die Reaktionsgruppen Konfiguration für den gesamten Pool. Die Auswahl bestimmter Gruppen, Warteschlangen oder Workflows zum Migrieren ist nicht möglich.



</div>

Nachdem Sie die Reaktionsgruppen migriert haben, müssen Sie lync Server-Systemsteuerung oder lync Server-Verwaltungsshell-Cmdlets verwenden, um zu überprüfen, ob alle Agentgruppen, Warteschlangen und Workflows erfolgreich verschoben wurden.

Wenn Sie Reaktionsgruppen migrieren, werden die lync Server 2010 Reaktionsgruppen nicht entfernt. Wenn Sie Reaktionsgruppen nach der Migration mithilfe von lync Server-Systemsteuerung oder lync Server-Verwaltungsshell verwalten, können Sie sowohl die lync Server 2010 Reaktionsgruppen als auch die lync Server 2013 Reaktionsgruppen anzeigen. Sie sollten Updates nur auf die lync Server 2013 Reaktionsgruppen anwenden. Die lync Server 2010 Reaktionsgruppen werden nur für Rollback-Zwecke beibehalten.

<div>


> [!WARNING]  
> Nachdem die Migration abgeschlossen ist und die neuen Reaktionsgruppen erstellt wurden, werden im lync Server-Systemsteuerung und im lync Server-Verwaltungsshell die lync Server 2010 und lync Server 2013 Versionen der einzelnen Reaktionsgruppen angezeigt. Verwenden Sie nicht lync Server-Systemsteuerung oder lync Server-Verwaltungsshell, um die lync Server 2010 Reaktionsgruppen zu entfernen. Wenn Sie eine entfernen, wird die entsprechende Reaktionsgruppe, die während der Migration erstellt wurde, nicht mehr funktionieren. Die lync Server 2010 Reaktionsgruppen werden entfernt, wenn Sie den lync Server 2010 Pool außer Betrieb nehmen.



</div>

<div>


> [!IMPORTANT]  
> Warten Sie mit dem Entfernen von Daten aus früheren Bereitstellungen, bis Sie den Pool außer Betrieb nehmen. Darüber hinaus wird dringend empfohlen, die Reaktionsgruppen unmittelbar nach der Migration zu exportieren. Wenn eine lync Server 2010 Reaktionsgruppe entfernt werden soll, können Sie Ihre Reaktionsgruppen dann aus der Sicherung wiederherstellen, damit lync Server 2013 Reaktionsgruppen erneut zur Verfügung stehen.



</div>

In lync Server 2013 wird ein neues Reaktionsgruppen Feature mit dem Namen **Workflowtyp**eingeführt. Der **Workflowtyp** kann **Verwaltet** oder **Nicht veraltet** sein. Alle Reaktionsgruppen werden mit dem **Workflowtyp****Nicht verwaltet** und mit leerer Manager-Liste migriert.

Wenn Sie das **Move-CsRgsConfiguration**-Cmdlet ausführen, bleiben die Agent-Gruppen, Warteschlangen, Workflows und Audiodateien zu Wiederherstellungszwecken im Vorversionspool. Wenn Sie jedoch keinen Rollback zum Vorversionspool durchführen müssen, müssen Sie das **Move-CsApplicationEndpoint**-Cmdlet ausführen, um Kontaktobjekte wieder in den Vorversionspool zu verschieben.

Das folgende Verfahren zum Migrieren von Reaktionsgruppen Konfigurationen setzt voraus, dass Sie eine 1:1-Beziehung zwischen Ihren Legacy Pools und den lync Server 2013 Pools haben. Wenn Sie während der Migration und Bereitstellung Pools konsolidieren oder aufteilen möchten, müssen Sie planen, welche Legacy-Pool-Karten lync Server 2013 Pool zugeordnet werden.

<div>

## <a name="to-migrate-response-group-configurations"></a>So migrieren Sie Reaktionsgruppen Konfigurationen

1.  Melden Sie sich auf dem Computer über ein Konto an, das Mitglied der Gruppe RTCUniversalServerAdmins ist oder über entsprechende Administratorrechte und -berechtigungen verfügt.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Ausführen
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Beispiel:
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  Nachdem Sie Reaktionsgruppen und Agents in den lync Server 2013 Pool migriert haben, ist die URL, die Agents zur Anmeldung und Abmeldung verwenden, eine lync Server 2013-URL und steht im Menü **Extras** zur Verfügung. Erinnern Sie Agents daran, sämtliche Referenzen, beispielsweise Lesezeichen, auf die neue URL zu aktualisieren.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>So überprüfen Sie die Reaktionsgruppenmigration mithilfe der Lync Server-Systemsteuerung

1.  Melden Sie sich über ein Konto, das Mitglied der Gruppe "RTCUniversalReadOnlyAdmins" oder mindestens Mitglied der Rolle "CsViewOnlyAdministrator" ist, am Computer an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie im linken Navigationsbereich auf **Reaktionsgruppen**.

4.  Überprüfen Sie auf der Registerkarte **Workflow** , ob alle Workflows in ihrer lync Server 2010 Umgebung in der Liste enthalten sind.

5.  Klicken Sie auf die Registerkarte **Warteschlange** , und stellen Sie sicher, dass alle Warteschlangen in ihrer lync Server 2010 Umgebung in der Liste enthalten sind.

6.  Klicken Sie auf die Registerkarte **Gruppe** , und stellen Sie sicher, dass alle Agentgruppen in ihrer lync Server 2010 Umgebung in der Liste enthalten sind.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a>So überprüfen Sie die Migration von Reaktionsgruppen mithilfe von lync Server-Verwaltungsshell

1.  Melden Sie sich mit einem Konto am Computer an, das Mitglied der Gruppe "RTCUniversalReadOnlyAdmins" oder mindestens Mitglied der Rolle "CsViewOnlyAdministrator" ist.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.
    
    Führen Sie Folgendes aus, um nähere Informationen zu den folgenden Cmdlets zu erhalten:
    
        Get-Help <cmdlet name> -Detailed

3.  Ausführen
    
        Get-CsRgsAgentGroup

4.  Stellen Sie sicher, dass alle Agentengruppen in ihrer lync Server 2010 Umgebung in der Liste enthalten sind.

5.  Ausführen
    
        Get-CsRgsQueue

6.  Stellen Sie sicher, dass alle Warteschlangen in ihrer lync Server 2010 Umgebung in der Liste enthalten sind.

7.  Ausführen
    
        Get-CsRgsWorkflow

8.  Stellen Sie sicher, dass alle Workflows in ihrer lync Server 2010 Umgebung in der Liste enthalten sind.

</div>

</div>

<span> </span>

</div>

</div>

</div>

