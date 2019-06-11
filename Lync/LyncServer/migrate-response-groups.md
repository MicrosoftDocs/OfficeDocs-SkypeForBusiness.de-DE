---
title: Migrieren von Reaktionsgruppen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60a5bb2b2124b84adeb6a494f6f33ce867f7d416
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>Migrieren von Reaktionsgruppen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-09-23_

Nachdem die Benutzer in die lync Server 2013-Pools verschoben wurden, können Sie Ihre Reaktionsgruppen migrieren. Zum Migrieren von Reaktionsgruppen gehören das Kopieren von Agentengruppen, Warteschlangen, Workflows, Audiodateien und Verschieben von Kontaktobjekten der Reaktionsgruppe aus der Legacy Bereitstellung in den lync Server 2013-Pool. Nachdem Sie Ihre Legacy Antwortgruppen migriert haben, werden die Anrufe an die Reaktionsgruppen von der Antwortgruppen Anwendung im lync Server 2013-Pool verarbeitet. Anrufe an Reaktionsgruppen werden nicht mehr vom Legacy Pool verarbeitet.

<div>


> [!NOTE]  
> Obwohl Sie Antwortgruppen migrieren können, bevor Sie alle Benutzer in den lync Server 2013-Pool verschieben, empfiehlt es sich, zuerst alle Benutzer zu verschieben. Insbesondere haben Benutzer, die Reaktionsgruppen-Agents sind, nicht die vollständige Funktionalität der neuen Features, bis Sie in den lync Server 2013-Pool verschoben werden.



</div>

Bevor Sie Antwortgruppen migrieren, müssen Sie einen lync Server 2013-Pool bereitgestellt haben, der die reaktionsgruppenanwendung enthält. Die reaktionsgruppenanwendung wird standardmäßig installiert und aktiviert, wenn Sie Enterprise-VoIP bereitstellen. Sie können sicherstellen, dass die reaktionsgruppenanwendung installiert ist, indem Sie das Cmdlet " **Get-CsService – ApplicationServer** " ausführen.

<div>


> [!NOTE]  
> Sie können neue lync Server 2013-Antwortgruppen im lync Server 2013-Pool erstellen, bevor Sie Ihre Legacy Antwortgruppen migrieren.



</div>

Führen Sie das Cmdlet **Move-CsRgsConfiguration** aus, um Reaktionsgruppen aus einem Legacy Pool auf den lync Server 2013 zu migrieren.

<div>


> [!IMPORTANT]  
> Mit dem Cmdlet "Migration der Reaktionsgruppe" wird die Reaktionsgruppen Konfiguration für den gesamten Pool verschoben. Sie können keine bestimmten Gruppen, Warteschlangen oder Workflows auswählen, die migriert werden sollen.



</div>

Nachdem Sie die Antwortgruppen migriert haben, müssen Sie die lync Server Control Panel-oder lync Server-Verwaltungsshell-Cmdlets verwenden, um zu überprüfen, ob alle Agentengruppen,-Warteschlangen und-Workflows erfolgreich verschoben wurden.

Wenn Sie Antwortgruppen migrieren, werden die lync Server 2010-Antwortgruppen nicht entfernt. Wenn Sie Antwortgruppen nach der Migration mithilfe der lync Server-Systemsteuerung oder der lync Server-Verwaltungsshell verwalten, werden sowohl die lync Server 2010-Antwortgruppen als auch die lync Server 2013-Reaktionsgruppen angezeigt. Sie sollten Updates nur auf die lync Server 2013-Reaktionsgruppen anwenden. Die lync Server 2010-Reaktionsgruppen werden nur für Rollback-Zwecke aufbewahrt.

<div>


> [!WARNING]  
> Nachdem die Migration abgeschlossen und die neuen Reaktionsgruppen erstellt wurden, werden in der lync Server-Systemsteuerung und der lync Server-Verwaltungsshell die Versionen lync Server 2010 und lync Server 2013 jeder Reaktionsgruppe angezeigt. Verwenden Sie die lync Server-Systemsteuerung oder die lync Server-Verwaltungsshell nicht, um die lync Server 2010-Reaktionsgruppen zu entfernen. Wenn Sie eine entfernen, wird die entsprechende Reaktionsgruppe, die während der Migration erstellt wurde, nicht mehr funktionieren. Die lync Server 2010-Reaktionsgruppen werden entfernt, wenn Sie den lync Server 2010-Pool außer Betrieb nehmen.



</div>

<div>


> [!IMPORTANT]  
> Wir empfehlen, dass Sie keine Daten aus Ihrer vorherigen Bereitstellung entfernen, bevor Sie den Pool außer Betrieb nehmen. Darüber hinaus wird dringend empfohlen, dass Sie Reaktionsgruppen unmittelbar nach der Migration exportieren. Wenn eine lync Server 2010-Reaktionsgruppe entfernt werden soll, können Sie Ihre Reaktionsgruppen aus der Sicherung wiederherstellen, damit die lync Server 2013-Reaktionsgruppen erneut ausgeführt werden.



</div>

Lync Server 2013 führt ein neues Reaktionsgruppen Feature namens **Workflowtyp**ein. **** Der Workflowtyp kann **verwaltet** oder **nicht verwaltet**werden. Alle Antwortgruppen werden migriert, **** wobei der Workflowtyp auf **nicht verwaltet** und mit einer leeren Manager Liste gesetzt ist.

Wenn Sie das Cmdlet **Move-CsRgsConfiguration** ausführen, verbleiben die Agentengruppen,-Warteschlangen,-Workflows und-Audiodateien im Legacy Pool für Rollback-Zwecke. Wenn Sie jedoch einen Rollback zum Legacy Pool durchführen müssen, müssen Sie das Cmdlet **Move-CsApplicationEndpoint** ausführen, um die Kontaktobjekte wieder in den Legacy Pool zu verschieben.

Das folgende Verfahren zum Migrieren von Reaktionsgruppen Konfigurationen setzt voraus, dass Sie über eine 1:1-Beziehung zwischen Ihren Legacy Pools und den lync Server 2013-Pools verfügen. Wenn Sie beabsichtigen, Pools während ihrer Migration und Bereitstellung zu konsolidieren oder aufzuteilen, müssen Sie planen, welche Legacy Pool-Zuordnungen dem lync Server 2013-Pool zugeordnet werden.

<div>

## <a name="to-migrate-response-group-configurations"></a>So migrieren Sie Reaktionsgruppen Konfigurationen

1.  Melden Sie sich bei dem Computer mit einem Konto an, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist oder über entsprechende Administratorrechte und-Berechtigungen verfügt.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Beispiel:
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  Nachdem Sie Antwortgruppen und Agents in den lync Server 2013-Pool migriert haben, ist die URL, die Agents zum Anmelden und Abmelden verwenden, eine lync Server 2013-URL und steht im Menü **Extras** zur Verfügung. Erinnern Sie die Agents daran, alle Verweise wie Textmarken auf die neue URL zu aktualisieren.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>So überprüfen Sie die Migration der Reaktionsgruppen mithilfe der lync Server-Systemsteuerung

1.  Melden Sie sich bei dem Computer mit einem Konto an, das Mitglied der RTCUniversalReadOnlyAdmins-Gruppe ist, oder wenn es sich um eine minimale Mitgliedschaft in der CsViewOnlyAdministrator-Rolle handelt.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie im linken Navigationsbereich auf **Reaktionsgruppen**.

4.  Überprüfen Sie auf der Registerkarte **Workflow** , ob alle Workflows in ihrer lync Server 2010-Umgebung in der Liste enthalten sind.

5.  Klicken Sie auf die Registerkarte **Warteschlange** , und stellen Sie sicher, dass alle Warteschlangen in ihrer lync Server 2010-Umgebung in der Liste enthalten sind.

6.  Klicken Sie auf die Registerkarte **Gruppe** , und stellen Sie sicher, dass alle Agentengruppen in ihrer lync Server 2010-Umgebung in der Liste enthalten sind.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a>So überprüfen Sie die Migration der Reaktionsgruppen mithilfe der lync Server-Verwaltungsshell

1.  Melden Sie sich bei dem Computer mit einem Konto an, das Mitglied der RTCUniversalReadOnlyAdmins-Gruppe ist, oder wenn es sich um eine minimale Mitgliedschaft in der CsViewOnlyAdministrator-Rolle handelt.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.
    
    Ausführliche Informationen zu den folgenden Cmdlets finden Sie unter:
    
        Get-Help <cmdlet name> -Detailed

3.  Führen Sie folgenden Befehl aus:
    
        Get-CsRgsAgentGroup

4.  Überprüfen Sie, ob alle Agentengruppen in ihrer lync Server 2010-Umgebung in der Liste enthalten sind.

5.  Führen Sie folgenden Befehl aus:
    
        Get-CsRgsQueue

6.  Überprüfen Sie, ob alle Warteschlangen in ihrer lync Server 2010-Umgebung in der Liste enthalten sind.

7.  Führen Sie folgenden Befehl aus:
    
        Get-CsRgsWorkflow

8.  Überprüfen Sie, ob alle Workflows in ihrer lync Server 2010-Umgebung in der Liste enthalten sind.

</div>

</div>

<span> </span>

</div>

</div>

</div>

